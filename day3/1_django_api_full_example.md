# 🔐 Django API with JWT Authentication (Beginner-Friendly Guide)

This documentation shows the **complete working example of a Django API with JWT Authentication**.  
It includes **models.py, serializers.py, views.py, urls.py** with copy-paste-ready code, and explains everything step by step.

---

## ❓ What is this API?

✅ This Django API supports:

- Register new users
- Login with JWT tokens (access + refresh)
- Logout by blacklisting refresh token
- Get user profile
- List and view products
- Manage shopping cart

✅ Authentication is implemented using [Django REST Framework SimpleJWT](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/).

This API is ideal for powering a frontend app (like React) that consumes JSON data.

---

# 📄 models.py

✅ Defines the database tables:

- `Product`: Product data.
- `CartUser`: User’s cart items.
- `PaymenMethod`, `OrderItem`, `ShippingAddress`: For future extensions (not yet implemented).

```python
from django.db import models
from django.contrib.auth.models import User

class Product(models.Model):
    product_id = models.AutoField(primary_key=True)
    product_name = models.CharField(max_length=255)
    product_price = models.DecimalField(max_digits=10, decimal_places=2)
    brand = models.CharField(max_length=255)
    description = models.TextField()
    countInStock = models.IntegerField()
    image = models.ImageField(upload_to='product_images/')
    createdAt = models.DateField(auto_now_add=True)

    def __str__(self):
        return self.product_name


class CartUser(models.Model):
    cart_id = models.AutoField(primary_key=True)
    product = models.ForeignKey(Product, on_delete=models.CASCADE)
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    qty = models.IntegerField()

    def __str__(self):
        return f'{self.user.username} - {self.product.product_name} x {self.qty}'


class PaymenMethod(models.Model):
    payment_id = models.AutoField(primary_key=True)
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    total_price = models.DecimalField(max_digits=10, decimal_places=2)
    is_paid = models.BooleanField(default=False)
    paid_at = models.DateField(null=True, blank=True)
    paymongo_payment_id = models.CharField(max_length=255, null=True, blank=True)
    paymongo_status = models.CharField(max_length=255, null=True, blank=True)

    def __str__(self):
        return f'Payment #{self.payment_id} - {self.user.username}'


class OrderItem(models.Model):
    order_id = models.AutoField(primary_key=True)
    product = models.ForeignKey(Product, on_delete=models.SET_NULL, null=True)
    payment = models.ForeignKey(PaymenMethod, on_delete=models.SET_NULL, null=True)
    qty = models.IntegerField()
    price = models.DecimalField(max_digits=10, decimal_places=2)

    def __str__(self):
        return f'Order #{self.order_id} - {self.product.product_name}'


class ShippingAddress(models.Model):
    shipping_id = models.AutoField(primary_key=True)
    payment = models.ForeignKey(PaymenMethod, on_delete=models.CASCADE)
    full_name = models.CharField(max_length=255)
    address = models.CharField(max_length=255)
    city = models.CharField(max_length=100)
    postal_code = models.CharField(max_length=20)
    country = models.CharField(max_length=100)

    def __str__(self):
        return f'{self.full_name} - {self.address}'
```
## What is UniqueValidator?
 - UniqueValidator is a built-in helper from Django REST Framework (DRF).
 - It is used to check that a field’s value is unique in the database — meaning: no other record already has this value.

## Why do we need it?
 - By default, DRF does not automatically check uniqueness for you in serializers.
 - Even though the database might reject duplicates, we want to show a nice validation error message before saving anything to the DB.

---

# 📄 serializers.py

✅ Defines how data is converted between JSON and Python objects:

- `RegisterSerializer`: Register users.
- `UserSerializer`: Profile info.
- `ProductSerializer`: Product data.
- `CartItemSerializer`: Cart data.

```python
from django.contrib.auth.models import User
from rest_framework import serializers
from rest_framework.validators import UniqueValidator

from .models import Product, CartUser

class RegisterSerializer(serializers.ModelSerializer):
    email = serializers.EmailField(
        required=True,
        validators=[ UniqueValidator(queryset=User.objects.all()) ]
    )
    password = serializers.CharField(write_only=True)

    class Meta:
        model = User
        fields = ['username', 'email', 'password']

    def create(self, validated_data):
        return User.objects.create_user(**validated_data)


class UserSerializer(serializers.ModelSerializer):
    class Meta:
        model = User
        fields = ['id', 'username', 'email']


class ProductSerializer(serializers.ModelSerializer):
    class Meta:
        model = Product
        fields = '__all__'


class CartItemSerializer(serializers.ModelSerializer):
    product = ProductSerializer(read_only=True)
    product_id = serializers.PrimaryKeyRelatedField(
        source='product',
        queryset=Product.objects.all(),
        write_only=True
    )

    class Meta:
        model = CartUser
        fields = ['cart_id', 'product', 'product_id', 'qty']
```

---

# 📄 views.py

✅ Defines the logic for each endpoint:

- Handles incoming requests, validates data, queries the database, and returns JSON responses.

```python
from django.shortcuts import get_object_or_404
from rest_framework.permissions import IsAuthenticated
from rest_framework.decorators import api_view, permission_classes
from rest_framework.response import Response
from rest_framework import status

from rest_framework_simplejwt.tokens import RefreshToken

from .models import Product, CartUser
from .serializers import (
    ProductSerializer,
    RegisterSerializer,
    UserSerializer,
    CartItemSerializer,
)

@api_view(['POST'])
def register_user(request):
    serializer = RegisterSerializer(data=request.data)
    if serializer.is_valid():
        serializer.save()
        return Response({'message': 'User registered successfully'}, status=status.HTTP_201_CREATED)
    return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)


@api_view(['POST'])
def logout_user(request):
    refresh_token = request.data.get('refresh')
    if not refresh_token:
        return Response({'error': 'Refresh token required.'}, status=status.HTTP_400_BAD_REQUEST)
    try:
        token = RefreshToken(refresh_token)
        token.blacklist()
        return Response({'message': 'Logged out successfully.'}, status=status.HTTP_205_RESET_CONTENT)
    except Exception:
        return Response({'error': 'Invalid refresh token.'}, status=status.HTTP_400_BAD_REQUEST)


@api_view(['GET'])
def profile_view(request):
    serializer = UserSerializer(request.user)
    return Response(serializer.data)


@api_view(['GET'])
def get_products(request):
    products = Product.objects.all()
    serializer = ProductSerializer(products, many=True)
    return Response(serializer.data)


@api_view(['GET'])
def get_product_detail(request, pk):
    product = get_object_or_404(Product, pk=pk)
    serializer = ProductSerializer(product)
    return Response(serializer.data)


@api_view(['GET'])
def list_cart_items(request):
    items = CartUser.objects.filter(user=request.user)
    serializer = CartItemSerializer(items, many=True)
    return Response(serializer.data)


@api_view(['POST'])
@permission_classes([IsAuthenticated])
def add_to_cart(request):
    serializer = CartItemSerializer(data=request.data)
    if serializer.is_valid():
        product = serializer.validated_data['product']
        qty = serializer.validated_data['qty']
        cart_item, created = CartUser.objects.get_or_create(
            user=request.user,
            product=product,
            defaults={'qty': qty}
        )
        if not created:
            cart_item.qty += qty
            cart_item.save()
        return Response(CartItemSerializer(cart_item).data, status=status.HTTP_201_CREATED)
    return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)


@api_view(['PUT'])
def update_cart_item(request, cart_id):
    cart_item = get_object_or_404(CartUser, pk=cart_id, user=request.user)
    serializer = CartItemSerializer(cart_item, data=request.data, partial=True)
    if serializer.is_valid():
        serializer.save()
        return Response(serializer.data)
    return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)


@api_view(['DELETE'])
def remove_cart_item(request, cart_id):
    cart_item = get_object_or_404(CartUser, pk=cart_id, user=request.user)
    cart_item.delete()
    return Response(status=status.HTTP_204_NO_CONTENT)
```

---

# 📄 urls.py

✅ Maps URLs to view functions.

```python
from django.urls import path
from . import views

from rest_framework_simplejwt.views import (
    TokenObtainPairView,
    TokenRefreshView,
)

urlpatterns = [
    path('register/', views.register_user, name='register'),
    path('api/token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', TokenRefreshView.as_view(), name='token_refresh'),
    path('logout/', views.logout_user, name='logout'),
    path('profile/', views.profile_view, name='profile'),
    path('products/', views.get_products, name='products'),
    path('products/<int:pk>/', views.get_product_detail, name='product_detail'),
    path('cart/', views.list_cart_items, name='cart_list'),
    path('cart/add/', views.add_to_cart, name='cart_add'),
    path('cart/<int:cart_id>/', views.update_cart_item, name='cart_update'),
    path('cart/<int:cart_id>/delete/', views.remove_cart_item, name='cart_delete'),
]
```

---

🎉 That’s it — this is your complete, working Django API with JWT Authentication, ready to copy-paste and learn from!
