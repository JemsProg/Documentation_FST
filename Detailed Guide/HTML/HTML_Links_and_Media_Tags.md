
#  HTML Links & Media Tags – Beginner's Guide

This guide explains the most commonly used HTML tags for **links and media**, their purpose, how to use them, and real-world examples.

---

## 1. `<a>` — Hyperlink
**Purpose:** Creates a hyperlink to another webpage, file, or section in the same page.
**Where to Use:** For navigation between pages or linking to external resources.

###  Syntax:
```html
<a href="URL">Link Text</a>
```

###  Attributes:
- `href` – The destination URL.
- `target="_blank"` – Opens the link in a new tab.
- `title` – Tooltip text when hovered.

###  Example:
```html
<a href="https://example.com" target="_blank" title="Go to Example">
Visit Example Website
</a>
```

**Where to Use in Real Projects:**
- Navigation menus.
- Buttons that redirect to another page.
- Linking to external resources like tutorials or documentation.

---

## 2. `<img>` — Image
**Purpose:** Displays an image on a webpage.
**Where to Use:** Anywhere you need to add graphics, icons, or photos.

###  Syntax:
```html
<img src="image.jpg" alt="Description of image">
```

###  Attributes:
- `src` – Path to the image file (local or URL).
- `alt` – Alternative text shown if image fails to load (important for accessibility and SEO).
- `width` & `height` – Optional attributes to define image size.

###  Example:
```html
<img src="logo.png" alt="Company Logo" width="200" height="100">
```

**Where to Use in Real Projects:**
- Company logo in the header.
- Product images in an e-commerce site.
- Illustrations in a blog post.

---

## 3. `<video>` — Video Element
**Purpose:** Embeds a video on a webpage.
**Where to Use:** For tutorials, promotional videos, or media content.

###  Syntax:
```html
<video controls width="400">
  <source src="video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

###  Attributes:
- `controls` – Displays play, pause, and volume controls.
- `autoplay` – Plays the video automatically when the page loads.
- `loop` – Repeats the video when finished.
- `muted` – Starts the video with sound off.

###  Example:
```html
<video controls autoplay loop muted width="500">
  <source src="intro.mp4" type="video/mp4">
  Your browser does not support the video element.
</video>
```

**Where to Use in Real Projects:**
- Intro videos on a landing page.
- Product demonstrations in e-commerce.
- Tutorials in an education platform.

---

## 4. `<audio>` — Audio Element
**Purpose:** Embeds audio content such as music or podcasts.
**Where to Use:** For background music, voice notes, or audio guides.

###  Syntax:
```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  Your browser does not support the audio tag.
</audio>
```

###  Attributes:
- `controls` – Displays play and pause controls.
- `autoplay` – Plays the audio automatically.
- `loop` – Repeats the audio after it finishes.
- `muted` – Starts the audio with sound off.

###  Example:
```html
<audio controls autoplay loop muted>
  <source src="background-music.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

**Where to Use in Real Projects:**
- Background music for a portfolio.
- Podcasts on blogs.
- Audio learning content for e-learning platforms.

---

###  Best Practices:
- Always provide `alt` for images (for SEO and accessibility).
- Always use `controls` for audio and video to give user control.
- Avoid autoplay for videos with sound (can annoy users).
- Optimize media size for faster page loading.

