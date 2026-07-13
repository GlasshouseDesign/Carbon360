# Carbon ThreeSixty — Website Redesign

Static HTML/CSS working files for the new carbonthreesixty.com. No build step —
open any `index.html` directly in a browser, or run a local server (see below).

## How to view

Open `index.html` in the project root — it's a concept-chooser page linking to
three homepage directions. Or jump straight to a concept:

- `concepts/option-1-industrial-edge/index.html` — dark, bold, motorsport/aerospace mood
- `concepts/option-2-clean-corporate/index.html` — light, spacious, premium consultancy mood
- `concepts/option-3-technical-blueprint/index.html` — engineering-drawing / blueprint mood

Optional local server (avoids any relative-path/font-loading quirks in some browsers):

```
cd "Carbon Three Sixty"
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Structure

```
Carbon Three Sixty/
├── index.html                 # concept chooser / pitch page
├── concepts/
│   ├── option-1-industrial-edge/index.html
│   ├── option-2-clean-corporate/index.html
│   └── option-3-technical-blueprint/index.html
└── assets/
    ├── css/
    │   ├── base.css            # shared reset, fonts, brand colour variables
    │   ├── chooser.css         # styles for the root chooser page only
    │   ├── option-1.css        # Industrial Edge theme
    │   ├── option-2.css        # Clean Corporate theme
    │   └── option-3.css        # Technical Blueprint theme
    ├── js/
    └── img/
```

All three concepts share the same brand variables defined once in
`assets/css/base.css` (`--c-yellow-*`, `--c-grey-*`), so changing a colour
there updates every concept at once. Fonts: **Space Grotesk** for headings,
**Inter** for body text (plus **JetBrains Mono** for accents in Concept 3),
loaded from Google Fonts.

Copy and structure (sectors, capabilities, contact details) is pulled from
the current live site. No real photography is used yet — texture and colour
carry the visuals for now (including a CSS-generated carbon-fibre weave
pattern, `.carbon-weave`, used across all three concepts) so nothing breaks
if real photos aren't ready.

## Next steps once a direction is picked

1. Merge the chosen concept's CSS into a single theme, delete the other two.
2. Swap in real photography/renders and finalised copy (About, Careers,
   full Capabilities detail, News/Case Studies listing).
3. Break `index.html` into the full site (About, Sectors, Capabilities,
   News, Contact) using the same header/footer markup.
4. For blogs/CMS later: this structure drops cleanly into a static site
   generator (e.g. Eleventy/Astro) or a headless CMS (e.g. Sanity,
   Contentful, WordPress-as-headless) — the HTML is already broken into
   consistent header/hero/section/footer blocks that map to templates.
