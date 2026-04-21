# Free Toast Host (FTH) Platform Guide

## What is FTH?

Free Toast Host is the official website platform provided to all Toastmasters clubs.
Each club gets a subdomain (e.g., `clubname.toastmastersclubs.org`).

## Page Layout Zones

An FTH site has three fixed zones:

```
+------------------------------------------+
|              HEADER (FTH-managed)        |
+----------+-------------------------------+
|          |                               |
| SIDEBAR  |     HOMEPAGE (editable)       |
| (FTH)    |     <-- HTML goes here        |
|          |                               |
+----------+-------------------------------+
```

- **Header**: Managed by FTH. Shows club name and TI banner. Not editable via HTML paste.
- **Sidebar**: Managed by FTH. Contains navigation links, login, member-only sections.
- **Homepage**: The main content area. This is where the generated HTML is pasted.

## How to Paste the HTML

1. Log in to the FTH admin panel
2. Navigate to **Site Administration**
3. Find the **Main Heading** field (it has a rich text editor)
4. Click the **Source** button (looks like `<>`) to switch to HTML mode
5. Select all existing content and delete it
6. Paste the new HTML code
7. Click **Save** or **Close**

## Critical Technical Constraints

**What FTH supports:**
- Standard HTML elements
- `<style>` tags with embedded CSS (must be inside the HTML body or head)
- `<link>` tags for Google Fonts (external URL references are fine)
- Simple inline `<script>` tags (very limited JS)

**What FTH does NOT support:**
- Separate `.css` files (no external stylesheets)
- Separate `.js` files (no external script files)
- Complex JavaScript frameworks (React, Vue, etc.)
- iframes from untrusted sources

**Performance warning:**
Keep JS to a minimum. Complex scripts or heavy animations can cause the page
to hang or load very slowly. Prefer CSS animations over JavaScript where possible.

**Image hosting:**
- Upload images via the FTH media manager first
- Use the resulting URL in `<img src="...">` tags
- Or reference images from external CDNs (e.g., official TI brand portal)

## HTML Structure Recommendation

Since the HTML is injected into the FTH page body (not a standalone page),
structure it as a series of `<div>` sections -- no need for `<html>`, `<head>`, or `<body>` tags.
However, `<style>` and `<link>` tags in the content area are typically honored by FTH.

Example minimal structure:
```html
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700&display=swap" rel="stylesheet">
<style>
  .fth-hero { background: #004165; color: white; padding: 40px; text-align: center; }
  /* ... more styles ... */
</style>

<div class="fth-hero">
  <h1>Club Name</h1>
  <p>Tagline here</p>
</div>

<!-- more sections -->

<div class="fth-disclaimer">
  The information on this website is for the sole use of Toastmasters' members...
</div>
```

## CSS Scoping

Prefix all CSS class names with `fth-` to avoid conflicts with FTH's own stylesheet.
Example: `.fth-hero`, `.fth-card`, `.fth-meeting` instead of generic `.hero`, `.card`.
