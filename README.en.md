# imgAspect

A single-file, browser-based image proportion calculator for frontend work. It helps you split a design image into segments, compare measurements, and convert values to a target width, percentage, and `rem`.

![Main screenshot](docs/screenshot-main.png)
![Dark screenshot](docs/screenshot-dark.png)

## GitHub Pages Demo

Demo link: `https://sergio221110.github.io/imgAspect/`

## Features

- Upload an image by click, drag and drop, or paste
- Read the original dimensions, aspect ratio, and file size
- Set a target width and `rem` base
- Auto-generate image boundary lines for segment calculation
- Drag split lines to adjust every segment in real time
- Show original `px`, converted `px`, percentage, and `rem` in the data panel
- Delete custom split lines when needed
- Export cropped segments as images
- Switch between dark and light themes

## Formula

```text
scale = targetWidth / naturalWidth
convertedPx = originalPx × scale
percent = convertedPx / convertedDimension × 100
rem = convertedPx / remBase
```

## Run locally

Open `index.html` directly in a browser. No install step is required.

## Why this repo is useful

- no runtime dependencies
- one HTML file as the core app
- SVG overlay for lines and labels
- original pixel coordinates are preserved, so zooming does not distort calculations
- boundary lines are fixed and cannot be removed

## License

MIT
