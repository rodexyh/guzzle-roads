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
