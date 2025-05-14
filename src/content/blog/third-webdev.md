---
title: 'Web Development'
description: 'Building the MikePfunk Website'
pubDate: 'May 11 2025'
heroImage: '/blog-placeholder-3.jpg'
---

# Web Development

## Key Technologies and Tools

- **Vite:** Utilized as the build tool and development server for its fast build times and efficient hot module replacement.
- **Three.js:** Implemented for rendering 3D models, enhancing the visual appeal with interactive graphics.
- **Cloudflare Pages:** Deployed using Cloudflare Pages, providing a fast and secure hosting environment.
- **Custom GPT Integration:** An AI-powered backend integrated for providing dynamic content and user interactions.

The **MikePfunk Website** is a single-page web application built with modern web development technologies.

---

## Using Cloudflare Pages to Host This Site

Cloudflare Pages is a great way to host a static site. It's free, fast, and easy to use.  
I've been using it for a few months now and I'm very happy with it.  
The only downside is that it doesn't support server-side rendering, so if you need that, you'll have to look elsewhere.

---

## Brief Explanation of Building MikePfunk Website

The **MikePfunk Website** is a developer portfolio, structured to look like a hybrid developer website/personal portfolio site.  
Built with modern web development technologies, it specifically leverages Vite for efficient build processes, Three.js for rendering 3D models, and Node.js.  
The website is designed to provide engaging and interactive content, including blog posts and 3D visualizations.

---

### Project Setup

- Initialized the project using Vite, configuring the necessary entry points for a multi-page application.
- Structured the project directory to organize assets, scripts, styles, and HTML files effectively.

### Design and Layout

- Created responsive HTML templates and CSS stylesheets for consistent design across all pages.
- Ensured the layout was user-friendly and accessible.

### 3D Model Integration

- Designed 3D models for logos and other interactive elements using Blender.
- Exported models in GLTF format for web optimization.
- Integrated Three.js to load and render these models on specific pages, providing interactive 3D visualizations.

### Blog Functionality

- Developed a JSON-driven blog post management system.
- Created scripts to dynamically load and display blog posts based on a JSON configuration file.

### AI Integration

- Implemented a Cloudflare Worker to interact with a custom GPT model.
- Set up an endpoint (e.g., `chatgpt.mikepfunk.com`) for AI-powered features, handling user inputs and providing dynamic responses.

### Deployment and Optimization

- Configured Vite to handle asset bundling and optimization, ensuring efficient load times.
- Deployed the site on Cloudflare Pages, leveraging its global CDN for fast content delivery.
- Implemented security measures, including appropriate CORS headers and referrer policies.

### Testing and Debugging

- Performed extensive testing across different browsers and devices to ensure compatibility and performance.
- Debugged issues related to asset loading and script execution to ensure a smooth user experience.

---

## Notable Features

- **Interactive 3D Models:**  
  Enhanced visual appeal with 3D logos and other elements, providing an engaging user experience.

- **Dynamic Blog Content:**  
  Easily manageable blog system using JSON files for content updates.

- **AI Integration:**  
  Custom GPT model integration for interactive user queries and flashcards for studying AWS.

---

## Final Remarks

The MikePfunk Website combines modern web technologies with innovative features to create an interactive and visually appealing platform.  
Continuous updates and improvements ensure that the site remains functional, secure, and engaging for all users.

I built this in order to learn web development, and probably will redo this in React.

---

**tags:** #javascript #webdev #development  
**Author:** Michael Pfundt
