# Attribution

## OpenStreetMap

© OpenStreetMap contributors. Data available under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/) —
see <https://www.openstreetmap.org/copyright>.

<!-- BEGIN generated: osmdate (tools/road-pack/public-repo/render.py in the app repository; do not edit by hand) -->
The packs in release v1 are derived from OpenStreetMap data as of 2026-09-28T20:23:05Z (the `osmBase` of every region in `roads-index.json`).
<!-- END generated: osmdate -->

Both kinds of pack are derived databases of OpenStreetMap:

- the **routing tiles** (`roads-*.tar.xz`), built from the OSM roads by Valhalla;
- the **road geometry** (`roadgeom-*.sqlite.xz`), the same roads cut by us into intersection-to-intersection
  segments.

They are therefore themselves distributed under the ODbL, and so is `roads-index.json`. `LICENSE` in this
repository is that licence. Each geometry pack also carries `license` (`ODbL-1.0`) and
`attribution` (© OpenStreetMap contributors) rows in its own `meta` table.

The OpenStreetMap extracts were downloaded from [Geofabrik](https://download.geofabrik.de/), which
redistributes OpenStreetMap data under the same licence. The exact files are listed in `README.md`
under "Sources".

## Valhalla

The routing tiles were built with [Valhalla](https://github.com/valhalla/valhalla) **3.6.3**
(MIT licence). Valhalla is the tool that made the tiles: none of its code is in the packs, and its licence
does not apply to the data.

## Province and state outlines (release `outlines-v1`)

The outline packs (`outlines-<country>-<sha16>.sqlite.gz` and `outlines-index.json`) are **not**
OpenStreetMap data and **not** under the ODbL. Each country's pack is simplified from one official
boundary file, under that publisher's own terms:

<!-- BEGIN generated: outlines-sources (tools/road-pack/public-repo/render_outlines.py in the app repository; do not edit by hand) -->
- **Canada** (`outlines-ca-df6a7088a5dc16e8.sqlite.gz`): Statistics Canada, 2021 Cartographic Boundary Files, provinces and territories (lpr_000b21a_e), as of 2021-11-17. Licence: Statistics Canada Open Licence.
  Credit line, as the pack's `meta` table carries it: *Adapted from Statistics Canada, 2021 Cartographic Boundary Files, 2021. This does not constitute an endorsement by Statistics Canada of this product.*
- **United States** (`outlines-us-38069eb3bcdc8ea9.sqlite.gz`): U.S. Census Bureau, 2024 Cartographic Boundary Files, states, 1:500,000 (cb_2024_us_state_500k), as of 2024-01-01. Licence: No licence statement on the Census Bureau pages checked 2026-10-07; U.S. federal government work (17 U.S.C. §105).
  Credit line, as the pack's `meta` table carries it: *Source: U.S. Census Bureau, 2024 Cartographic Boundary Files.*
<!-- END generated: outlines-sources -->

### Statistics Canada (Canadian provinces and territories)

Adapted from Statistics Canada, 2021 Cartographic Boundary Files, 2021. This does not constitute an endorsement by Statistics Canada of this product.

Used under the [Statistics Canada Open Licence](https://www.statcan.gc.ca/en/reference/licence). The source is the 2021 Cartographic Boundary File of provinces
and territories (`lpr_000b21a_e`). We reprojected it from Statistics Canada Lambert to latitude and longitude,
dropped islands smaller than 1 km², and simplified every boundary to within 500 m; those changes are ours.

### U.S. Census Bureau (U.S. states and the District of Columbia)

Source: U.S. Census Bureau, 2024 Cartographic Boundary Files.

The source is the 2024 Cartographic Boundary File of states at 1:500,000 (`cb_2024_us_state_500k`). We dropped
islands smaller than 1 km² and simplified every boundary to within 500 m; the five territories in that file are
not in the pack.
<!-- Checked 2026-10-07; details in the app repository, tools/outline-pack/outlines.json (us source, _verified). -->
On 2026-10-07 we checked the Census Bureau's cartographic boundary download page
(<https://www.census.gov/geographies/mapping-files/time-series/geo/cartographic-boundary.html>) and its citation
policy (<https://www.census.gov/about/policies/citation.html>) and found no licence statement on either page. The
citation policy asks that "U.S. Census Bureau" be named as the author, which the credit line above does. Works of
the U.S. federal government are generally not subject to U.S. copyright (17 U.S.C. §105).
