# Design to Tailwind

Convert one selected Figma frame into a fixed, exact HTML + Tailwind page.

The plugin preserves the selected frame's measured positions, sizes, spacing, typography, colors, images and vectors. It does not use AI, responsive inference, viewport merging, or layout rewriting.

Import `plugin/manifest.json` in Figma, select exactly one Frame, Section, Component, Instance, or Group, and click **Generate**. Inspect the exact preview, copy the code, or download the complete ZIP. Generate mobile and desktop frames separately when separate outputs are required.

The Express backend URL is configured under **Backend connection**. Use HTTPS for a deployed backend or `http://localhost:3000` for local development.
