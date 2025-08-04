# Git & GitHub Documentation (Beginner Guide)

This guide covers the **essential Git & GitHub steps** for beginners, including creating repositories, pushing and pulling code, and using `.gitignore`.

---

## **1. Install Git**

Download and install Git from [https://git-scm.com/downloads](https://git-scm.com/downloads).  
Verify installation:

```bash
git --version
```

---

## **2. Configure Git (First Time Only)**

Set your name and email (used in commits):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## **3. Create a New Repository on GitHub**

1. Go to [GitHub](https://github.com/).
2. Click **New Repository**.
3. Enter repository name (e.g., `my-project`).
4. Click **Create Repository**.

---

## **4. Initialize Git in Your Local Project**

In your project folder, run:

```bash
git init
```

This creates a `.git` folder for version control.

---

## **5. Connect Your Project to GitHub**

Add the remote repository (copy the URL from GitHub):

```bash
git remote add origin https://github.com/your-username/my-project.git
```

Check remote:

```bash
git remote -v
```

---

## **6. Add and Commit Your Code**

```bash
git add .         # Adds all files
git commit -m "Initial commit"
```

---

## **7. Push Code to GitHub**

For the first push:

```bash
git branch -M main    # Rename branch to main
git push -u origin main
```

For later updates:

```bash
git push
```

---

## **8. Pull Latest Changes from GitHub**

```bash
git pull origin main
```

---

## **9. Change Remote Repository**

If you need to change the GitHub repo:

```bash
git remote set-url origin https://github.com/your-username/new-repo.git
```

---

## **10. Git Version Control Basics**

### Check status:

```bash
git status
```

### View commit history:

```bash
git log
```

### Create a new branch:

```bash
git branch feature-branch
```

### Switch branch:

```bash
git checkout feature-branch
```

### Merge branches:

```bash
git merge feature-branch
```

---

## **11. Using .gitignore**

`.gitignore` tells Git which files to ignore (not track).

Example `.gitignore`:

```
node_modules/
.env
.DS_Store
build/
```

Create this file in your project root and add files/folders you don’t want to push.

---

## **Summary Commands**

```bash
# Initialize repo
git init

# Connect to GitHub
git remote add origin <repo-url>

# Add and commit changes
git add .
git commit -m "message"

# Push code
git push origin main

# Pull latest changes
git pull origin main
```

---

### Best Practices

✔ Commit often with clear messages.  
✔ Use `.gitignore` for sensitive and large files.  
✔ Always pull before you push to avoid conflicts.

---
