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
    * Map markers now sourced from the facilities API, with a labelled ACTRIS National Facility tier for better visibility
    * Checkbox for showcasing and selecting ACTRIS National Facilities - Labelled and Initially Accepted.
    * Results table: frozen header row, always-visible horizontal scrollbar, timeliness/product-type highlighting
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
