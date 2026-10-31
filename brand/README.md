# csi-rs brand assets

The canonical source for every csi-rs logo. Reference these files by their raw URL from any
repository rather than copying them, so a change here reaches the whole organization:

```
https://raw.githubusercontent.com/csi-rs/.github/main/brand/<path>
```

**Mark:** a monoline breath pulse in Connected Motion's visual system (round caps, −12° slant,
terminal dot).
**Colors:** purple `#4C4081` · flame `#F24822` · ink `#211F2A` · off-white `#F7F7FF`.
**Wordmark:** Montserrat Bold / SemiBold, converted to outlines (no font dependency).

## Files

| Use | File |
|---|---|
| GitHub org avatar | `avatar/csi-rs-avatar-512.png` (also `-1024.png` and `.svg`) |
| GitHub social preview (repo Settings → Social preview) | `png/csi-rs-social-preview@1x.png` (1280×640) |
| Repository README header, auto light/dark | `svg/csi-rs-lockup-light-nocaption.svg` + `svg/csi-rs-lockup-dark-nocaption.svg` |
| Lockup with the "by Connected Motion" caption | `svg/csi-rs-lockup-light.svg` + `svg/csi-rs-lockup-dark.svg` |
| Centred hero (organization profile) | `svg/csi-rs-stacked-light.svg` + `svg/csi-rs-stacked-dark.svg` |
| Mark only, transparent | `svg/csi-rs-mark.svg` (purple) · `svg/csi-rs-mark-white.svg` |

`png/` holds @2x rasters of every SVG for places that cannot render vector graphics.

## README header snippet

Switches with the viewer's GitHub theme; put it above the repository's own `# title`:

```html
<p align="center">
  <a href="https://github.com/csi-rs">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/csi-rs/.github/main/brand/svg/csi-rs-lockup-dark-nocaption.svg">
      <img alt="csi-rs" src="https://raw.githubusercontent.com/csi-rs/.github/main/brand/svg/csi-rs-lockup-light-nocaption.svg" width="320">
    </picture>
  </a>
</p>
```

## Clear space & minimum size

Keep clear space equal to the stroke width around the mark. Don't use the mark below 20 px; use
the square avatar tile instead.

Don't recolor the dot: it is always flame on purple or white, and the stroke is always purple
(light) or off-white (dark).
