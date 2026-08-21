<!--
This is the convention for how the headers should be written, add hierarchically with newest on top.

# Major release vX.0.0
# Minor release vX.Y.0
# Patch release vX.Y.Z

Directly under each header, add a plain italic metadata line (not a code block):
*Launched YYYY-MM-DD*

Portal releases and metadata API releases aren't intrinsically tied, so don't restate the
API version on every entry. Only when a release actually adopts a new metadata API version,
reference it inline in the relevant change bullet, like:
[Metadata API vN](https://prod-actris-md.nilu.no/vN/api-docs)

Only add a one-off "*Updated YYYY-MM-DD: <what changed>*" line if retroactively editing an
already-published entry -- this file's own git history is the normal edit trail.
-->


# Patch release v2.0.2

*Launched 2026-08-21*

* v2.0.1 failed to deploy to production — a memory issue in the search index caused repeated crashes. This release fixes the underlying cause: the code that keeps search working when the metadata API is temporarily unavailable now runs separately, so it can no longer take the whole portal down with it
* Basket: fixed "Download all files" not including every file for large baskets, caused by a hidden per-cookie size limit, and added a clearer error page (instead of a raw server error) for the rare case a request is still too large to process
* Downloads: fixed ARES file names to correctly use the dataset's PID
* Search: clearer error message when the metadata API is briefly unavailable (503)

# Patch release v2.0.1

*Launched 2026-08-19*

* Basket: downloads are now more resilient — per-file timeout, concurrent fetching, and automatic recovery from a stale/corrupted basket cookie
* Search map: faster initial load and no more grey-out while the layout settles, plus clearer loading feedback
* Releases page: caches the changelog file to avoid GitHub rate-limit errors
* Privacy: added a placeholder notice for the Matomo opt-out box when it fails to load (e.g. private browsing, ad/tracker blockers)
* SEO: added meta descriptions, canonical URLs and a sitemap across pages, to improve search-engine discoverability and make pages easier for AI tools to summarize correctly
* Services page: moved to server-side rendering, with bug fixes
* Removed the unmaintained `/nrt` page
* Various server-side error logging and user-facing notification improvements across search, facility, and statistics pages

# Major release v2.0.0

*Launched 2026-08-13*

Major changes:

* Search:
    * Full migration of search, facility and statistics routes onto the new [ACTRIS metadata API](https://prod-actris-md.nilu.no/v3/api-docs)
    * Hierarchical, tree-select filters for matrix/variable/instrument/object-of-interest, with a clear selection option for each filter
    * Map markers now sourced from the facilities API, with a labelled ACTRIS National Facility tier for better visibility
    * Checkbox for showcasing and selecting ACTRIS National Facilities - Labelled and Initially Accepted.
    * Results table: frozen header row, always-visible horizontal scrollbar, timeliness/product-type highlighting, clickable facility chips
    * Start-/End-date filter fixes and info tooltip
* Basket:
    * Clickable facility chips
    * Coverage plotted per facility, grouped by variable/matrix, on a new interactive Plotly chart
    * LocalStorage compression for highly compressible datasets
    * Pagination fix for facilities with more than 10k datasets
* Dataset inspect pages:
    * Personnel information added
    * Updated file information
    * New “Add to basket” button
* Facility pages:
    * New “Add all facility data to basket” button
    * Added BSC Dust model products to all ACTRIS National Facilities that are initially accepted or labelled, both BSC Dust Forecast Timeseries and BSC Dust Forecast Vertical Profile by MONARCH model
* Statistics:
    * New aggregate "User Statistics" pages with dedicated login
    * Canonical, vocabulary-backed statistics filters
* Login: simplified to a single set of credentials, using the shared header/footer layout
* Feedback: replaced the in-portal feedback form with a direct email link to actris@nilu.no
* Footer: portal version number is now shown in the footer
* Documentation: added API info boxes and new tutorial videos
