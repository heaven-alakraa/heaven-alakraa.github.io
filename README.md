# Editing your portfolio — a plain-English guide

You don't need to know how to code to update this site. Almost everything is either
**text between tags** or a **file you swap out**. Here's how to do the common things.

## The files

- `index.html` — the homepage (hero, about, projects list, 3D model, skills)
- `project-*.html` — one page per project (six of them)
- `resume.html` — your resume page
- `styles.css` — all the colors, fonts, and spacing for **every** page
- `README.md` — this guide

> Rule of thumb: **content** lives in the `.html` files. **Looks** (color, size,
> spacing) live in `styles.css`. Change the look once in the CSS and every page updates.

## How to change text

Open any `.html` file. Text shows up between tags like this:

```html
<h1>Hi, my name is Heaven.</h1>
```

Just edit the words between `>` and `<`. So to change your name's greeting you'd edit
`Hi, my name is Heaven.` — leave the `<h1>` and `</h1>` alone.

## How to swap your headshot

In `index.html` find:

```html
<img class="headshot" src="Heaven Alakraa - Headshot.jpg" alt="Heaven Alakraa">
```

The `src="..."` is the filename. Put your photo in the same folder and either name it
exactly `Heaven Alakraa - Headshot.jpg`, or change the `src` to match your file's name.
**Filenames are case- and space-sensitive** — `headshot.jpg` ≠ `Headshot.jpg`.

## How to add images to a project page

Open a `project-*.html` file. You'll see grey placeholder boxes like:

```html
<figure class="media-figure">
  <div class="img-placeholder">Add a hero render here</div>
  <figcaption>Full assembly render (replace with your image)</figcaption>
</figure>
```

To use a real image, delete the `<div class="img-placeholder">...</div>` line and put an
`<img>` in its place:

```html
<figure class="media-figure">
  <img src="canopener/hero.jpg" alt="Can opener render">
  <figcaption>Full assembly render</figcaption>
</figure>
```

Tip: make a folder per project (e.g. `canopener/`) and drop the images there to stay tidy.

## How to add a video

Find a `<div class="video-embed">...</div>` block. Two options:

**YouTube / Vimeo** — paste the embed link:

```html
<div class="video-embed">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" allowfullscreen></iframe>
</div>
```

(Get `VIDEO_ID` from the YouTube share link, or use Share → Embed and copy the `src`.)

**A video file in your repo:**

```html
<div class="video-embed">
  <video src="canopener/demo.mp4" controls></video>
</div>
```

## How to add the 3D model (Sketchfab)

1. Make a free account at sketchfab.com.
2. In SolidWorks: `File > Save As > .STL` (or export the assembly). For an exploded
   *animation*, build an Exploded View, then `Motion Study` and save/upload that.
3. Upload to Sketchfab, open the model, click **Share → Embed**, copy the `<iframe>`.
4. In `index.html` (and `project-can-opener.html`) find the `.embed-frame` box and
   replace the `<div class="embed-placeholder">...</div>` with your `<iframe>`.

## How to update your resume

Export it from Google Docs (`File > Download > PDF`). It should be named exactly
`Heaven Alakraa - Resume.pdf` (the name Google gives it by default), and put it in
the repo root. `resume.html` shows it automatically. To update later, just replace
that one PDF file with the freshly downloaded one — same name, no renaming needed.

## How to change colors or fonts

Open `styles.css`, top section:

```css
:root {
  --black: #111;
  --white: #fff;
  --gray: #666;
  --light: #f5f5f3;
  --border: #e0e0dc;
}
```

Change a hex code (e.g. `--black: #1a2b4c;`) and that color updates everywhere it's used.

## How to add a new project

1. Copy an existing `project-*.html` file and rename it (e.g. `project-new-thing.html`).
2. Edit its text, images, and steps.
3. In `index.html`, copy one of the `<a class="project-card">...</a>` blocks inside
   `<div class="projects-grid">` and point its `href` at your new file.

## Publishing changes

Edit files locally → commit → push to GitHub. Since everything uses relative links
(no full URLs between pages), it works the same on GitHub Pages as on your computer.
To preview locally, just double-click `index.html` to open it in your browser.
