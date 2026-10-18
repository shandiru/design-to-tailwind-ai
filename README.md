# Design to Tailwind

Convert selected Mobile + Desktop Figma frames into one exact responsive HTML + Tailwind page.

The plugin preserves each frame's measured positions, sizes, spacing, typography, colors, images and vectors. It does not use AI or guess how layers should merge; it keeps two exact trees and switches them at the desktop breakpoint.

Import `plugin/manifest.json` in Figma, select exactly two differently-sized matching frames (Mobile + Desktop), and click **Generate**. Use the Mobile/Desktop exact previews, copy the responsive code, or download the complete ZIP.

The Express backend URL is configured under **Backend connection**. Use HTTPS for a deployed backend or `http://localhost:3000` for local development.
