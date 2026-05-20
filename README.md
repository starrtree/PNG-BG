# PNG-BG

A tiny browser app for checking whether an uploaded image contains real alpha transparency or fake checkerboard transparency baked into the pixels.

## Features

- Upload PNG, WEBP, GIF, SVG, JPG/JPEG, BMP, AVIF, or other browser-supported image files
- Preview images on a light/dark checkerboard background
- Inspect the alpha channel locally in the browser
- Report transparent pixels, fully transparent pixels, semi-transparent pixels, alpha range, dimensions, and file metadata
- Copy/save a reusable transparent-background prompt for ChatGPT Images

## Deployment

This repo includes a GitHub Pages workflow at `.github/workflows/deploy-pages.yml`.

After GitHub Pages finishes deploying, the app should be available at:

```txt
https://starrtree.github.io/PNG-BG/
```

## Privacy

Image inspection happens locally in the browser. Uploaded files are not sent to a server by this static app.

## OpenAI API note

This app only verifies transparency. To generate/edit transparent PNGs with OpenAI, wire a backend endpoint that calls the Images API with:

```json
{
  "background": "transparent",
  "output_format": "png"
}
```

Do not put an OpenAI API key in client-side browser code.
