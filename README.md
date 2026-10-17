# Design to Tailwind

Figma to responsive HTML + Tailwind with mobile/desktop reference merging, `sm` through `2xl` previews, optional Gemini layout review, live generation logs and ZIP downloads.

Import `plugin/manifest.json` in Figma. Save mobile and desktop frames separately (or select both), keep **Responsive** enabled, and click **Generate**. The generator uses normal document flow, flex and grid; custom `<style>` blocks and inline styles are not emitted for design markup.

Gemini polish is optional. Rotate any key that has been shared publicly, then paste the replacement into **Gemini AI settings**. It is stored only in Figma `clientStorage`; no `.env` file is required and the key is never written to this repository or generated output. The model identifier is fixed in the plugin source.

The backend is configured separately in **Backend connection**. Use an HTTPS URL, or `http://localhost:3000` for local development.
