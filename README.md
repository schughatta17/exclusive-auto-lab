# Exclusive Auto Lab — site files

Upload everything in this folder to your web root, keeping the `img/` folder
as a folder. Replaces what's on the server now.

---

## What changed

**Everything now matches the homepage.** Your portal `index.html` is untouched —
byte-for-byte the file you sent. The other 20 pages were still running the old
Legends stylesheet (Arial, lime green `#d6ff00`, old layout). They now share one
stylesheet built from the portal's own design language: Michroma display type,
pure monochrome, hexagon geometry, and the travelling-light hover from your
hexagon doors reused on buttons.

There is no accent colour anywhere. Your logo is pure white, so the site
differentiates with light — glow and contrast — instead of hue.

**One stylesheet instead of twenty.** `styles.css` is shared by every page except
the portal, which stays self-contained. Change a colour once, it changes
everywhere.

**Pages went from 250–550 KB each down to 19–31 KB**, because photos are now
shared files in `img/` instead of base64-embedded into every single page.

---

## Broken things that got fixed

These were live on every page:

| Problem | Was | Now |
|---|---|---|
| Instagram link | `instagram.com/exclusiveautolabct/exclusiveautolabct/` (404) | correct handle |
| Nav "Schedule" | `index.html#appointment` — anchor doesn't exist on the portal | `schedule.html` |
| Nav "Contact" | `index.html#contact` — same problem | `contact.html` |
| Hero CTAs | same dead anchors | real pages |
| Favicon paths | root-relative, breaks on subdirectory hosting | relative |
| Breadcrumbs | current page styled with inline colour | proper `.here` class |

`sitemap.xml` and `robots.txt` were referenced in your last README but weren't in
the zip. Both are here now, covering all 21 pages.

---

## The North Haven problem — fixed with a new page

Your portal homepage is about forty words. It can't rank for "auto body shop
north haven ct" no matter what the title tag says, and that's your single most
valuable search term.

New page: **`auto-body-north-haven-ct.html`**

It's the strongest of the location pages, because North Haven is the home town
rather than a drive-to town. Directions from I-91 exit 12, Route 5 and Route 22,
the Universal Drive / Rebeschi Drive geography, a winter-damage angle specific to
salt off I-91, seven FAQs, and full `AutoBodyShop` + `FAQPage` + `BreadcrumbList`
schema.

Every "North Haven, CT" link in every footer used to point at `index.html`. They
all point here now — that's twenty internal links feeding the page.

The portal keeps its brand-term title ("Exclusive Auto Lab | Collision Repair &
Customization"), so the two pages don't compete.

---

## Photos — read this part

The photo library came from your old site. I de-duplicated it: 23 embedded files
turned out to be only 10 actual distinct photos at different resolutions.

**Two were removed and you should not put them back:**

- One shop-floor photo had a **BOOSTIN Performance banner** hanging on the wall.
  That's another company's shop. Running it on your site is a real liability.
- One was a **Lamborghini Countach collection** in a white showroom — reads as a
  car museum, not a body shop.

**Two are plausibly your actual work** and now lead the customization pages:

- The red **AMG G 63** — hero on Paint Protection Film and Custom Builds
- The black **Kia Stinger** — hero on Vehicle Tint, Chrome Delete and North Haven

I cropped landscape hero versions of both (`g-wagon-hero.jpg`,
`stinger-hero.jpg`) since the originals are portrait phone photos.

**The remaining six are stock** — the paint booth, the spray gun, the technician
in blue coveralls, the red hatchback on a jack. They're generic collision-shop
stock photography. They read as "process" rather than "our shop," which is why
they're only on the collision pages, never the customization ones.

I also replaced all **68 hotlinked Unsplash images** in the photo strips with
these local files. The site no longer depends on an external image host, and
nothing is generic-stock-on-top-of-generic-stock any more.

**What I could not do:** get you new car photos. I have no way to pull from your
Instagram, and I'm not going to generate fake ones. Send me real shots from
`@exclusiveautolabct` — jobs coming through the shop, before/afters, cars in your
actual bay — and every stock image on the site can be replaced. That's the single
biggest upgrade left.

Ideal shots to send:
- 3–4 landscape (wide) shots for page heroes
- 4–6 portrait or square shots for the feature panels and strips
- Anything showing your building or bay, so the location pages look like *your* location

---

## Files

```
index.html                        your portal — unchanged
auto-body-north-haven-ct.html     NEW
styles.css                        shared design system
img/                              10 photos, 3.3 MB total
sitemap.xml  robots.txt           NEW

collision-repair.html      dent-repair.html
auto-body-paint.html       insurance-claims.html
paint-protection-film.html ceramic-coating.html
vehicle-tint.html          vinyl-wraps.html
chrome-delete.html         paint-correction.html
wheels-calipers.html       custom-builds.html
auto-body-new-haven-ct.html    auto-body-hamden-ct.html
auto-body-wallingford-ct.html  auto-body-east-haven-ct.html
auto-body-branford-ct.html
schedule.html              contact.html
favicons, logo, site.webmanifest
```

---

---

## Favicons — replaced

Every icon file on the site was still the **Legends Auto Body** logo. That's what
was showing in browser tabs, bookmarks and on any phone home screen. All of them
are now built from your hexagon mark.

Every size uses the same monogram: the hexagon frame with the X blade inside. The
full "EXCLUSIVE AUTO LAB" wordmark is deliberately not used in the icons — it is
unreadable below roughly 200px and just turns the icon into a grey smudge. The
wordmark stays where it belongs, in the site header.

| File | Size | Used by |
|---|---|---|
| `favicon.ico` | 16 / 32 / 48 multi-res | older browsers, bookmarks |
| `favicon-16x16.png` | 16 | standard tab |
| `favicon-32x32.png` | 32 | retina tab, bookmark bar |
| `favicon-48x48.png` | 48 | Windows shortcuts, some readers |
| `apple-touch-icon.png` | 180 | iOS home screen |
| `android-chrome-192x192.png` | 192 | Android |
| `android-chrome-512x512.png` | 512 | Android splash, PWA |
| `icon-maskable-512.png` | 512 | Android adaptive icons — art inside the 80% safe zone so it isn't clipped by round or squircle masks |

All 21 pages now carry the same six-line icon block, and `theme-color` is a
consistent `#020204` sitewide instead of three different values.

**`site.webmanifest` said "Legends Auto Body."** That's the name that appears when
someone adds the site to a phone home screen. Rewritten with the correct name,
description, `start_url`, `scope`, the maskable icon entry, and matching theme
colours.

## Removed

- `READ-ME-FIRST.md` — stale duplicate of this file, and not something you want
  sitting on a public web root anyway.

No orphaned image or icon files remain — every asset on disk is referenced by at
least one page.

---

## The Legends homepage content — restored and split

The old Legends homepage carried 1,344 words and 30 headings. When it became the
portal, all of it went: the insurance carrier marquee, the four-step accident
guide, the services mosaic, the nine-card customization grid, the trustbar, the
claim checklist, the gallery and the local keyword block.

For the record, none of the 19 service and city pages lost anything. Titles, meta
descriptions and meta keywords are byte-identical to the batch you sent, and body
copy is within a couple of words on every page. Only the homepage was hollowed out.

That content now lives on the two pages the portal doors open onto:

**`collision-insurance.html`** — 978 words
Hero, trustbar, the 18-carrier insurance marquee, "here is what to do next"
(the four accident steps), the five-card services mosaic, the claim checklist,
the collision-plus-customization bridge panel, a local keyword block written for
collision terms, and the gallery. Links out to Collision Repair, Dent Repair,
Paint & Refinishing and Insurance Claims.

**`customization.html`** — 782 words
Hero, a trustbar rewritten for customization (the collision version talked about
towing and insurance claims, which made no sense here), the customization intro
with the G-Wagon panel, all nine service cards, the lighting-tint feature, a
local keyword block for customization terms, and the gallery. Links out to all
eight customization pages.

Both are lifted from the original Legends markup rather than rewritten, so the
phrasing you had is intact — only the shop name, the address and the dead anchor
links changed. Each carries `AutoBodyShop` + `Service` + `BreadcrumbList` schema.

### Wiring

- The portal's two hexagon doors now open onto these hubs rather than dropping
  people straight into a single service page
- Both nav dropdowns gained an overview entry at the top pointing at the hub
- Both hubs are in the footer services column on all 23 pages
- Sitemap updated, both at priority 0.95

Fixed while porting: the bridge panel's photo was a hardcoded Unsplash background
in the old stylesheet and came through empty; "Learn more" was an inline link
sitting inside the `<h3>` and ran into the heading text; and the G-Wagon shot was
re-cropped past the neighbouring building's "MILLION" sign.

## After uploading

1. Google Search Console → Sitemaps → submit `sitemap.xml`
2. Request indexing on `auto-body-north-haven-ct.html` specifically
3. Google Business Profile → link `auto-body-north-haven-ct.html` as the primary
   service-area page, and the individual service pages under matching services
4. Run one page through Google's Rich Results Test — FAQ schema should be detected

## Still open

- **Business hours** aren't in the schema on any page. Send them and they go in
  as `openingHoursSpecification` — the one local-SEO field Google actively uses
  that's currently blank on all 21 pages.
- **Connecticut tint law** — still no VLT percentages on `vehicle-tint.html`, on
  purpose. Those change, and a wrong number on your own site is a liability.
  Confirm with CT DMV and they can be added.
- **Don't clone the city pages** for more towns by swapping the name. Google
  treats near-identical location pages as doorway spam. Cheshire or Meriden would
  each need its own angle written, like North Haven got.
