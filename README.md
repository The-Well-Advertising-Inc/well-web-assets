# well-web-assets

Static assets for The Well's internal/client Apps Script web apps.

## favicons
Served to Apps Script `HtmlOutput.setFaviconUrl()` (which requires a URL ending in an image extension) via jsDelivr:

- `https://cdn.jsdelivr.net/gh/jsthewell/well-web-assets@main/ig.png`
- `https://cdn.jsdelivr.net/gh/jsthewell/well-web-assets@main/integris.png`
- `https://cdn.jsdelivr.net/gh/jsthewell/well-web-assets@main/wwt.png`
- `https://cdn.jsdelivr.net/gh/jsthewell/well-web-assets@main/well.png`

Source/build: `~/Claude/The Well/operations/web-favicons/build_v2.py`

## client logos (Client Context Tool, added 2026-08-03)

Rendered in the stepped Client Context validation tool at 56px, inside a white tile so one
variant reads on both the light cards and the plum masthead.

| slug | file | source |
|---|---|---|
| `wwt` | `wwt.png` | Dropbox `WWT/_Corporate/2021 NEW BRAND ASSETS/Logos/WWT_Monogram/RGB/Color/WWT_Monogram_RGB_Color.svg`, client-provided |
| `presidio` | `presidio.png` | Dropbox `Presidio/04. Logos/PresidioBlue_500x500.png`, client-provided (7.26:1 wordmark, see note) |
| `okta` | `okta.png` | Dropbox `Okta/01. Provided by Okta/Logos/Okta Logos/Okta_Aura_CMYK_Black.png`, client-provided |
| `itonda` | `itonda.png` | Dropbox `Itonda/ITD2601/05_Deliverables/Logo/Itonda Name Only.svg` (The Well designed it) |
| `grabber` | `grabber.png` | Dropbox `Grabber/2026/7. Images & Resources/Grabber logo 2026/Grabber Logo DinCond-BLK-txt.png`, the 2026 asset |
| `studio41` | `studio41.png` | Google's cached wordmark; studio41.com hard-blocks fetches with 429 |
| `shirley-ryan-abilitylab` | `sralab.png` | sralab.org chevron mark |
| `greatwater-garages` | `greatwater.png` | greatwater360autocare.com gear mark (their lockup is white-only) |
| `mission-investment-fund` | `mif.png` | mif.elca.org quad mark (every lockup on their site is reversed white) |
| `optiver` | `optiver.png` | optiver.com triangle mark |

All are 256x256 RGBA, trimmed to the artwork and centred with a small margin. These are the
clients' own marks as published, unlike the `build_v2.py` monogram tiles, which are brand-colored
squares The Well composes rather than client artwork.

## The 56px legibility limit (read before swapping a logo)

The tiles draw at 56px with the art capped at 82%, so about 46px of usable space. What survives that
depends almost entirely on aspect ratio:

- **Square marks (1:1 to 1.5:1) are crisp.** WWT's monogram at 1.98:1 still reads cleanly at 40px.
- **Wide lockups do not.** At 7.26:1, `presidio.png` gets 46x6px: mush at 40px, faint at 56px,
  readable only at 72px. Grabber at 4.3:1 has the same problem.

Judge this by rendering at TRUE pixel size and magnifying with nearest-neighbour. Rendering the tile
at 4x and eyeballing that flatters a fine wordmark and will tell you it is fine when it is not.

Wide lockups are shipped anyway, deliberately: they are the client's authoritative asset, and the
card shows the client name in text beside the logo, so the mark carries recognition rather than
legibility. The real fix, if it is ever wanted, is a wider logo slot for horizontal lockups instead
of forcing every client into the same square.

**Updated 2026-08-03 (Presidio):** `presidio.png` replaced with Presidio's official blue wordmark,
supplied by Jeff from Dropbox, superseding the `build_v2.py` blue "P" tile. Note the source is named
`PresidioBlue_500x500.png` but is **not** square: it is a 501x69 wordmark padded into a 501x501
canvas. Every other asset in that folder is either the same horizontal lockup or a 0-byte Dropbox
placeholder, and the white variants would vanish on the white tile, so this is the only usable
Presidio file. There is no square Presidio symbol to use.

**Updated 2026-08-03 (later):** `wwt.png` replaced with WWT's official monogram, supplied by Jeff from
Dropbox, superseding the `build_v2.py` red "WWT" tile. Rendered from the brand SVG at 4x and
downsampled so the diagonals stay clean. It is 1.98:1, so it no longer fills the tile the way the
composed square did, but it is crisp and legible down to 40px.

`wwt.png` is consumed in three places, all of them "this row is WWT" markers, so the official mark is
right in all three: the Client Context Tool (cards, wizard masthead, hub tiles, validation
dashboard), the Agency AI Operations dashboard, and the tools-portal preview. Despite the favicons
section above listing it, no app actually passes `wwt.png` to `setFaviconUrl` any more, so nothing
changes in any browser tab. That stale listing is worth cleaning up.

**Updated 2026-08-03:** `okta.png` and `grabber.png` replaced with the client-provided files Jeff
supplied from Dropbox, superseding the versions sourced from their public sites. Okta is now the Aura
symbol (square, reads well small). Grabber is the 2026 DinCond wordmark, which is 4.3:1 so it sits
small inside the square tile; the card shows the client name in text beside it, so the logo carries
recognition rather than legibility.
