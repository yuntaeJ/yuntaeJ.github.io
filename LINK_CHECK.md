# Link audit — 2026-09-18

Audited the page promoted from `v2.html` to `index.html`.

## Local checks

- Main-page section anchors resolve.
- Portrait, rocket favicon and Safari mask icon exist.
- The replacement 404 page links back to `/`.
- Inline JavaScript passes syntax validation.
- No remaining references to `v2.html`, `projects.html`, old CSS/JS, localhost or the missing web manifest.

## External checks

| Target | Result |
| --- | --- |
| Google Fonts stylesheet; Font Awesome and Academicons stylesheets | HTTP 200 |
| Google Scholar | HTTP 200; Yuntae Jeon profile title matches |
| GitHub | HTTP 200; Yuntae Jeon profile title matches |
| LinkedIn | HTTP 999 (automated access blocked); profile identity not independently verified |
| Automation in Construction and Advanced Engineering Informatics papers | DOI redirects resolve to Elsevier article endpoints (HTTP 200); publisher redirect pages limit content inspection |
| ASCE paper | Direct request blocked (403); publisher search result confirms matching title, author and DOI |
| MSD project | HTTP 200; matching project title |
| CVPR 2024 and CVPR 2023 papers | HTTP 200 at the corresponding CVF paper URLs |
| NeRF-Con | HTTP 200; matching paper title |
| SPIE paper | HTTP 200; response did not provide a readable title, so content verification is limited |
| US patent | HTTP 200; patent number and title match |
| Two Korean patents | DOI redirects resolve to KIPRIS (HTTP 200) with the corresponding application numbers; interactive record content not independently verified |
| VizWiz 2024 and CVAAD competition | HTTP 200; matching event pages |
| SKKU President's List | Direct request timed out; web retrieval confirms the 2022 list includes 전윤태. Removed duplicate query separator |
| SKKU graduation paper award | Connection failed; web retrieval also failed. Original URL preserved pending manual verification |
| KSCE scholarship news | HTTP 200; title identifies 전윤태 and the Park Chang-ho scholarship |

Google Fonts preconnect origins return 404 at their bare root URLs; these are connection hints, not page links. The actual stylesheet returns 200.

## Cleanup

Removed the previous homepage, legacy CSS/JS, `_site` build output, obsolete theme gemspec and browser tile configuration. Previously deleted project pages remain deleted. Updated 404 and Jekyll configuration to avoid depending on the removed theme. `_site` is now ignored by Git.

Tracked deleted files can be recovered from Git history. The former untracked `v2.html` content is retained as `index.html`. No changes have been published.
