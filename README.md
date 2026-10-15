# Design to Tailwind

The Figma plugin generates HTML and Tailwind code locally. Generate does not call an AI service and requires no API key. Enhance with AI is a separate optional cleanup step. See [the tracked repository documentation](backend/README.md) for server environment setup, model defaults and tests. Edit `backend/plugin/` for changes that will be committed to GitHub. The preview and full-page export still load Tailwind's CDN and Google Fonts.

## Generate responsive code

1. Import `plugin/manifest.json` through Figma > Plugins > Development.
2. Select matching **mobile and desktop frames** together. Optionally include a tablet frame (maximum three frames, at different widths).
3. Keep **Responsive** enabled and click **Generate**.
4. Inspect Base, sm (640), md (768), lg (1024), xl (1280), and 2xl (1536) using the preview buttons. Copy the HTML body or full page.

Frames are sorted by width. Shared layers are matched by name and Figma node type within their parent, with a text-content fallback for text layers. The output contains one element per matched layer, mobile-first classes, and media rules for changing inline paints and effects. Type and spacing are interpolated at intermediate breakpoints; larger widths inherit the final design styles unless another change is needed. The widest frame sets the root maximum width.

Use matching descriptive layer names (`Header`, `Hero`, `Photo`, etc.) and consistent section nesting. Auto Layout gives the best results. Unmatched layers appear only at their reference viewports and trigger a review message; repeated names are matched in order and also flagged. Different nesting, rich-text segmentation, and arbitrary absolute-positioned designs can need manual adjustment. Inspect the result before using it; deterministic matching cannot infer every design relationship.

Selecting one frame retains the existing single-frame generator. **Exact layout** is available for one frame; combining multiple frames requires Responsive mode.

## Verify

Run `node --test plugin/responsive.test.js` from the repository root. Tests cover shared-tree merging, tablet transitions, changing assets and inline styles, unmatched controls, utility resets, selection ordering, and generation without API calls. These use DOM and Figma fixtures; visual verification in the Figma host is still required.

## Legacy backend

`backend/` retains its existing fix, optional Gemini refinement, and logging endpoints for existing integrations. The plugin Generate flow no longer uses them. Backend configuration is unnecessary for local plugin generation.
