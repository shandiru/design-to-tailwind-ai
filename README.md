# Design to Tailwind

Convert one selected Figma frame into a fixed, exact HTML + Tailwind page.

The plugin preserves the selected frame's measured positions, sizes, spacing, typography, colors, images and vectors. It does not use AI, infer responsive layouts, or merge mobile/tablet/desktop frames.

Import `plugin/manifest.json` in Figma, select exactly one Frame, Section, Component, Instance, or Group, and click **Generate**. Use the exact preview, copy the generated code, or download the complete ZIP.

The Express backend URL is configured under **Backend connection**. Use HTTPS for a deployed backend or `http://localhost:3000` for local development.
