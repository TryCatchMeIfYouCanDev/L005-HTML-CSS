
# Images and Introduction to CSS #

## 1. Graphic Formats ##

Common image formats on the web include **JPEG, GIF, PNG, and SVG**.  
Modern lossy formats like **WebP** and **AVIF** provide better compression with high quality but have limited browser compatibility.

**Key concepts:**
- *Lossy compression*: Reduces file size by discarding some image data.
- *Web performance*: Prefer lighter formats for faster page loading.

---

## 2. Image Tag `<img>` ##

The `<img>` tag inserts an image into an HTML page. It is a **self-closing (void) tag**, meaning it does not contain a closing tag.

**Basic Syntax:**
```html
<img src="media/img/image001.png" alt="LABFORWEB Logo" title="LABFORWEB" width="400px" />
```
**Important Attributes:**
| Attribute | Description | Example / Values |
|------------|-------------|------------------|
| `src` | Path or URL of the image | `"image.jpg"` |
| `alt` | Alternate text for accessibility and fallback | `"A running dog"` |
| `title` | Tooltip displayed on hover | `"Company Logo"` |
| `width` / `height` | Image dimensions (prefer CSS) | `"400px"`, `"50%"` |
| `loading` | Controls image loading behavior | `lazy`, `eager` |
| `srcset` | Responsive images for different displays | `"image-1x.jpg 1x, image-2x.jpg 2x"` |
| `sizes` | Image sizes for various layouts | `"(max-width:600px) 100vw, 50vw"` |
| `usemap` | Links image to an image map | `"#map1"` |
| `longdesc` | URL for a detailed description | `"description.html"` |

**Accessibility Attributes (ARIA):**
- `aria-label`, `aria-describedby`, `aria-labelledby`
- `role`, `aria-hidden`, `tabindex`
- These attributes improve accessibility for users relying on screen readers like **JAWS**.

---

## 3. The `<figure>` and `<figcaption>` Elements ##

The `<figure>` tag semantically groups an image with its caption.  
`<figcaption>` provides the caption text, enhancing accessibility and structure.

**Example:**
```html
<figure>
  <img src="media/img/image001.png" alt="LABFORWEB Logo" title="LABFORWEB" />
  <figcaption>LABFORWEB Logo Description</figcaption>
</figure>
```

---

## 4. The `<picture>` Element (Responsive Images) ##

The `<picture>` tag allows defining multiple image sources for different screen sizes or resolutions.  
This helps load the **most appropriate image** depending on the device.

**Example:**
```html
<picture>
  <source srcset="media/img/003.png" media="(min-width:768px)" />
  <source srcset="media/img/002.png" media="(min-width:480px)" />
  <source srcset="media/img/001.png" />
  <img src="media/img/003.png" alt="Responsive Example" />
</picture>
```

**Notes:**
- `<picture>` is a container.
- `<source>` uses `srcset` and `media` attributes.
- `<img>` acts as a fallback for unsupported browsers.

---

## 5. Image Maps ##

Image maps define clickable areas within an image using `<map>` and `<area>`.

**Example:**
```html
<img src="map.jpg" usemap="#cartina" alt="Clickable Map">
<map name="cartina">
  <area shape="rect" coords="34,44,270,350" href="site1.html" alt="Site 1">
  <area shape="circle" coords="200,200,50" href="site2.html" alt="Site 2">
</map>
```

**Area Shapes:**
- `rect` → Rectangle (x1, y1, x2, y2)
- `circle` → Circle (x, y, radius)
- `poly` → Polygon (multiple coordinates)

---

## 6. Comparison Table — Image Insertion Methods ##

| Tag / Method                  | Description                               | Example                                                                                               |
|-------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------------------|
| `<img>`                       | Basic inline image                        | `<img src="photo.jpg" alt="Sample">`                                                                  |
| `<figure>` + `<figcaption>`   | Semantic image container with caption     | `<figure><img src="photo.jpg"><figcaption>Caption</figcaption></figure>`                              |
| `<picture>` + `<source>`      | Responsive images for different devices   | `<picture><source srcset="photo-600.jpg" media="(max-width:600px)"><img src="photo.jpg"></picture>`   |
| `<map>` + `<area>`            | Clickable zones on an image               | `<map><area shape="circle" ...></map>`                                                                |
| `<svg>`                       | Scalable vector graphics (editable)       | `<svg><circle cx="50" cy="50" r="40"/></svg>`                                                         |
| `<canvas>`                    | Dynamic, script-drawn image               | `<canvas id="draw"></canvas>`                                                                         |
| `<object>`                    | Embeds external image files               | `<object data="graphic.svg"></object>`                                                                |

---

## 7. Layout Rules and Dimensions ##

- The **sum of the widths** of child elements (e.g., `aside`, `article`, `div`) **must not exceed** the parent width (e.g., the `body` width of 1000px).
- Columns can be created using **float**, **flexbox**, or **grid**.
- Legacy methods should still be known for maintenance of older web pages.

**Common relative units:** `%`, `em`.

---

## 8. Placeholder and Utility Tools ##

**Placeholder image generators:**
- [https://placehold.co/](https://placehold.co/)
- [https://dummyimage.com/](https://dummyimage.com/)

**Performance and optimization tools:**
- [Google PageSpeed Insights](https://pagespeed.web.dev/?hl=IT)
- [TinyJPG](https://tinyjpg.com/)
- [ezgif Image Optimizer](https://ezgif.com/)
- [Can I Use](https://caniuse.com/)
- [Image File Type Guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Formats/Image_types)

**Design and icon tools:**
- [CSS3 Button Generator](https://css3buttongenerator.com/)
- [Flaticon](https://www.flaticon.com/)
- [Image Map Generator](https://www.image-map.net/)

---

## 9. Introduction to CSS ##

CSS (Cascading Style Sheets) define the **visual appearance** of HTML elements.  
Three main methods exist:

| Type                      | Description                               | Example                                       | Priority          |
|---------------------------|-------------------------------------------|-----------------------------------------------|-------------------|
| **Inline**                | Style applied directly in the tag         | `<p style="color:red;">Text</p>`              | Highest           |
| **Embedded (Internal)**   | Inside a `<style>` tag in the `<head>`    | `<style>p {color:red;}</style>`               | Medium            |
| **External**              | Linked CSS file                           | `<link rel="stylesheet" href="style.css">`    | Depends on order  |

**Selector Example:**
```css
nav a {
  color: #00f !important;
  background-color: #ff0;
  text-decoration: none;
}
```

**Common CSS properties:**
- `color`, `background-color`, `text-decoration`
- `font-style`, `font-weight`
- `display`, `width`, `height`

**Notes:**
- Avoid inline styles for maintainability.
- Use `!important` only when strictly necessary.
- The latest declared style overrides earlier ones.

---

**End of Document**