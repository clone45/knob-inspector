# Knob Inspector

A tiny browser-based tool for checking how round and how centered a knob image
really is. Built originally to audit AI-generated knob artwork — which often
looks right at a glance but turns out to be a few pixels off true circle or
true center — but useful for any case where you need to overlay precise guide
circles on an image.

No build step, no dependencies. One HTML file.

## Use cases

- Comparing AI-generated knob renders against an ideal circle
- Eyeballing whether a hand-drawn knob is symmetric
- Measuring the outer radius of features in any image (in pixels)
- Sanity-checking that exported sprites are actually centered in their canvas

## Running it

Open `index.html` in any modern browser. That's it.

If you'd rather serve it locally:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Features

- **Load any image** (PNG, JPG, SVG, WebP...) — drawn centered on the canvas
- **Scale** the image uniformly from 10% to 300% — aspect ratio is preserved
- **Opacity** slider — fade the knob in and out to compare its edge against
  the guide circles underneath
- **Drag** the image anywhere on the canvas to fine-tune alignment
- **Add guide circles** that always stay locked to the canvas center
  - Click *Add circle*, then move the mouse — radius = distance from center
  - Click to commit, or press <kbd>Esc</kbd> to cancel
  - Scroll wheel nudges the live radius by ±1 px for precision
- **Edit any circle** — click it in the sidebar list to change its radius,
  color, stroke width, or alpha live. Scroll wheel still nudges the radius
  while editing.
- **Backgrounds**: checker / dark / light — different backgrounds reveal
  different edge artifacts (especially on knobs with soft anti-aliased edges)
- **Crosshair** at the canvas center, toggleable

## Why this exists

AI image generators are great at producing knobs that *look* round and *look*
centered but are subtly off — usually a few pixels of eccentricity, sometimes
a slight horizontal/vertical bias. Those defects are easy to miss in a
thumbnail but glaring once a row of knobs is on a synth panel. This tool just
slaps a true circle on top so the difference is obvious.

## License

MIT
