# 🖥️ Project Title: Responsive HBT Hotel Site

## 🧠 Project Overview

This is a self-teaching project aimed at solidifying my understanding of the fundamentals of responsive design through a simple hotel layout.

### 🎯 Learning Goals

- Work with image backgrounds and the `<img>` HTML element  
- Understand and use CSS Floats  
- Master Flexbox  
- Implement responsive design principles  
- Use CSS variables effectively  
- Write cleaner code by generalizing styles  

---

## 🗺️ Workflow: From Design to Code

### 🎨 Design Phase

Before coding, I reviewed the design to identify layout structures and style patterns. The goal was to minimize code repetition by applying reusable styles.

**Layout and Component Breakdown:**

![Layout 1](docs/image-1.png)  
![Layout 2](docs/image-2.png)  
![Layout 3](docs/image-3.png)  
![Layout 4](docs/image-4.png)  
---  
![Layout 5](docs/image-6.png)  
![Layout 6](docs/image-5.png)  
---  
![Layout 7](docs/image-7.png)

---

### 🧰 Utilities and Layout Strategies

**Utilities:**

- `ba-accent`: Used for cards and testimonials  
- `text-accent`: Used for headings  
- `bg-dark`:  
  - section: white text on black background  
  - Button: black text on white background  
- `bg-url-`: Used for three different background images with similar properties; only the URL differs (leveraging CSS variables)

**Layout Classes:**

- `split`:  
  - Sets `display: flex`  
  - Adds `gap` using `var(--gap, 0)`  
  - Makes it easier to handle responsive column layout with a single media query  

- `container`:  
  - Used for giving text margin and centralize content.  
  

- `flow > * + *`:  
  - Adds a 30px gap between sibling elements  

---

### 📚 Design Source

This project is part of the **Traversy Media HTML & CSS Course**.

### ⚙️ Planning & Setup

**Folder structure**:
  * **CSS/:** This folder houses the Cascading Style Sheets files, which are used to control the visual presentation and styling of the HTML content.
    * `about.css`: Styles specific to the "about.html" page.
    * `contact.css`: Styles specific to the "contact.html" page.
    * `index.css`: Styles specific to the main "index.html" page.
    * `style.css`: Likely contains global or shared styles used across multiple pages.
  * **docs/:** This directory is intended for documentation related to the website or project.
  * **img/:** This folder stores image assets used on the website.
  * **about.html:** 
  * **contact.html:**
  * **index.html:** 
  * **README.md:** 

### 🧑‍💻 Development Process
- Initial Setup and Core Structure
- Homepage Completion and Responsiveness
- About Page Development
- Contact Page Development
- Refactoring and fixing bugs

---

## 🧱 Problems & Solutions

### Problem #1: Image Disappears When Flex Direction Changes to Column

**Issue:** I was attempting to create a two-column layout with equal width, where one column contained text and the other displayed an image. The image, implemented as a `background-image` on a `div`, disappeared when the flex direction of the container was changed from `row` to `column`.

**Cause:** The issue arises from how flexbox handles sizing and the nature of using a `background-image`. When the flex direction is set to `column`, the main axis becomes vertical. Flexbox tries to shrink flex items as much as possible along this main axis. Since the `div` containing the `background-image` had no intrinsic content, flexbox considered it the least important element and effectively collapsed its height to zero. Consequently, with no height on the `div`, the `background-image` became invisible. Furthermore, the height of the flex container in a column layout is determined by the height of its children. An empty `div` contributes no inherent height to the container.

**Solution:** The solution was to explicitly set a height on the flex container. This provided a defined space along the main axis (vertical in this case), allowing the `div` with the `background-image` to occupy that space and the image to become visible.


### Problem #2: Inconsistent Width Rendering of `<img/>` in Flex Layout Across Browsers

**Issue:** I implemented a two-column flex layout where one column contained text and the other displayed an image using the `<img/>` tag. I attempted to set the width of the text column to 60% and the image column to 35%. However, I observed significant rendering differences between Firefox and Chrome.

**Cause:** The discrepancy in rendering is likely due to subtle variations in how different browsers, specifically Firefox and Chrome, handle the `width` property applied directly to `<img/>` elements that are also flex items. These browsers might have slightly different interpretations of how the intrinsic dimensions of the image interact with the flexbox layout and the specified percentage widths.

**Solution:** The solution that provided a consistent look across both browsers was to wrap the `<img/>` tag within a container `div`. By applying the flex-basis to this container `div` instead of directly to the `<img/>` tag, the image then scales within its container in a more predictable and consistent manner across different browsers.


## 💡 Things I’d Do Differently

Reflections on what could be improved:
- Code organization
- Better tools or libraries
- UX or performance issues

---


