Cursor Zoo

A tiny interactive field guide where hovering over an enclosure swaps your mouse cursor for a custom-drawn one — a marigold at dawn, a chili pepper at noon, a firefly at night. Six habitats, six pointers, one specimen plate tracking whichever creature you're currently holding.

Description

Cursor Zoo is a single-page, single-file web toy. Each of the six "habitats" corresponds to a rough time of day (dawn, noon, afternoon slump, evening, night, and deep-focus/anytime) and carries its own hand-drawn SVG cursor, styled around a shared botanical-dark palette. There's no build step, no dependencies, and no backend — just HTML, CSS, and vanilla JS generating data-URI cursors on the fly.

Visuals

Open cursor-zoo.html in a desktop browser and hover over any of the six cards in the grid — the system cursor will change shape for as long as your pointer stays inside that card, and a small plate at the bottom names the current resident.

Installation

No installation or dependencies required.

bash
git clone <your-repo-url>
cd cursor-zoo

Then just open cursor-zoo.html in a browser (double-click it, or serve it locally):

bash
python3 -m http.server 8000
# visit http://localhost:8000/cursor-zoo.html
Requirements
Any modern desktop browser (Chrome, Firefox, Safari, Edge)
A mouse or trackpad — custom cursors don't render on touch devices, so this won't do much on mobile
Usage

Hover over a habitat card to "become" its cursor:

html
<!-- each habitat sets its own cursor via a base64 SVG data URI -->
el.style.cursor = `url('${cursorUrl}') 16 16, auto`;

To add a new habitat, add an object to the habitats array in the <script> block with a name, time, desc, color, and svg (a small 32×32 viewBox SVG string) — the grid renders itself from that array.

Roadmap
 Swap in Fruit Almanac fruits as an alternate cursor set
 Make each habitat clickable to reveal a short story or fact
 Detect actual local time and highlight the "current" habitat
 Add a reduced-motion / static fallback for touch devices
Support

This is a personal side project — open an issue in the repo, or just reach out directly with feedback or ideas.

Contributing

Pull requests are welcome, especially new habitat/cursor pairs. If you're adding one, keep the SVGs small (viewBox 32×32), stick to the existing color tokens, and update the habitats array only — no other markup changes should be needed.

Authors and acknowledgment

Built by Soundarya. Cursor illustrations and palette inspired by the botanical-dark aesthetic of The Fruit Almanac.

License

MIT

Project status

Active — small and finished for now, but open to fun additions.
