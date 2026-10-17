# Design to Tailwind

Figma to responsive HTML + Tailwind with mobile/desktop reference merging, `sm` through `2xl` previews, optional Gemini layout review, live generation logs and ZIP downloads.

Import `plugin/manifest.json` in Figma. Save mobile and desktop frames separately (or select both), keep **Responsive** enabled, and click **Generate**. The generator uses normal document flow, flex and grid; custom `<style>` blocks and inline styles are not emitted for design markup.

Gemini polish is optional. Configure `GEMINI_API_KEY` only in the backend hosting environment (such as Vercel project settings); no `.env` file is used. The key is never sent to the Figma plugin, stored in generated output, or committed. The backend defaults to `gemini-3.8-flash` and accepts a `GEMINI_MODEL` override. Rotate any credential that has been pasted into chat or shared publicly.

The backend is configured separately in **Backend connection**. Use an HTTPS URL, or `http://localhost:3000` for local development. The plugin enables **Gemini polish** only when backend health reports that AI is configured.
