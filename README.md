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
| `okta` | `okta.png` | Dropbox `Okta/01. Provided by Okta/Logos/Okta Logos/Okta_Aura_CMYK_Black.png`, client-provided |
| `itonda` | `itonda.png` | Dropbox `Itonda/ITD2601/05_Deliverables/Logo/Itonda Name Only.svg` (The Well designed it) |
| `grabber` | `grabber.png` | Dropbox `Grabber/2026/7. Images & Resources/Grabber logo 2026/Grabber Logo DinCond-BLK-txt.png`, the 2026 asset |
| `studio41` | `studio41.png` | Google's cached wordmark; studio41.com hard-blocks fetches with 429 |
| `shirley-ryan-abilitylab` | `sralab.png` | sralab.org chevron mark |
| `greatwater-garages` | `greatwater.png` | greatwater360autocare.com gear mark (their lockup is white-only) |
| `mission-investment-fund` | `mif.png` | mif.elca.org quad mark (every lockup on their site is reversed white) |
| `optiver` | `optiver.png` | optiver.com triangle mark |

All eight are 256x256 RGBA, trimmed to the artwork and centred with a small margin. These are the
clients' own marks as published, unlike the four above, which `build_v2.py` composes as
brand-colored monogram tiles.

**Updated 2026-08-03:** `okta.png` and `grabber.png` replaced with the client-provided files Jeff
supplied from Dropbox, superseding the versions sourced from their public sites. Okta is now the Aura
symbol (square, reads well small). Grabber is the 2026 DinCond wordmark, which is 4.3:1 so it sits
small inside the square tile; the card shows the client name in text beside it, so the logo carries
recognition rather than legibility.
