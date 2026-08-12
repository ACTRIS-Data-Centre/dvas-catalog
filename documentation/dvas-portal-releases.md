<!--
This is the convention for how the headers should be written, add hierarchically with newest on top.

# Major release vX.0.0
# Minor release vX.Y.0
# Patch release vX.Y.Z
-->


# Major release v2.0.0

Major changes:

* Search:
    * Full migration of search, facility and statistics routes onto the new [ACTRIS metadata API](https://prod-actris-md.nilu.no/swagger-ui/index.html)
    * Hierarchical, tree-select filters for matrix/variable/instrument/object-of-interest
    * Map markers now sourced from the facilities API, with a labelled ACTRIS National Facility tier
    * Results table: frozen header row, always-visible horizontal scrollbar, timeliness/product-type highlighting
    * Start-/End-date filter fixes and info tooltip
* Basket:
    * Clickable facility chips
    * Coverage plotted per facility, grouped by variable/matrix, on a new interactive Plotly chart
    * LocalStorage compression for highly compressible datasets
    * Pagination fix for facilities with more than 10k datasets
* Statistics:
    * New aggregate "User Statistics" pages with dedicated login
    * Canonical, vocabulary-backed statistics filters
* Login: simplified to a single set of credentials, using the shared header/footer layout
* Feedback: replaced the in-portal feedback form with a direct email link to actris@nilu.no
* Footer: portal version number is now shown in the footer
* Documentation: added API info boxes and new tutorial videos
