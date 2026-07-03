# lucas.yan — personal portfolio

Single-file portfolio site: `index.html`. Zero dependencies, zero build step —
the display font (Unbounded) is inlined as a data URI, all CSS/JS is hand-rolled,
so the file works offline and deploys anywhere as-is.

## Deploy

Any static host works. The three easiest:

- **GitHub Pages** — push this folder to a repo, Settings → Pages → deploy from branch.
- **Netlify** — drag the folder onto https://app.netlify.com/drop
- **Vercel** — `npx vercel` in this folder.

## Customize

- **Photo**: in the About section, replace `<span class="monogram">LY</span>` inside
  `.portrait-inner` with `<img src="you.jpg" alt="Lucas Yan" style="width:100%;height:100%;object-fit:cover">`.
- **Contact form**: currently opens the visitor's mail client (`mailto:`). To receive
  submissions directly, swap the submit handler for a [Formspree](https://formspree.io)
  or Netlify Forms POST.
- **Colors**: everything derives from the CSS variables at the top of the `<style>`
  block (`--cyan`, `--violet`, `--magenta`, `--bg0`…).
- **Phone number**: intentionally not published; add it in the Contact section if you
  want it public.

## Performance notes

- Two canvases: a fixed starfield (pauses when the tab is hidden) and the hero
  icosahedron (pauses when scrolled out of view). Pixel ratio capped at 2×.
- All animation is transform/opacity only; `prefers-reduced-motion` disables the
  loader, canvases and reveals.
