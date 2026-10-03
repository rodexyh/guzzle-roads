# guzzle-roads

<!-- BEGIN generated: summary (tools/road-pack/public-repo/render.py in the app repository; do not edit by hand) -->
Release **v1**: 13 Canadian provinces and territories, 26 packs, 232,753,144 bytes, plus `roads-index.json` (14,033 bytes, sha256 `87da8296ca34b0edf8ef432610d5b383751aff74b92cd6974789948e94c8e6cf`).
OpenStreetMap data as of 2026-09-28T20:23:05Z (Geofabrik extracts); routing tiles built with Valhalla 3.6.3.
<!-- END generated: summary -->

Every province or territory has two packs:

- **Routing tiles**, `roads-<code>-<sha16>.tar.xz`: a tar of [Valhalla](https://github.com/valhalla/valhalla)
  graph tiles covering drivable roads only (motorway, trunk, primary, secondary, tertiary and their links,
  unclassified, residential, living_street, road, plus turn restrictions; no service roads, tracks or paths),
  compressed with xz. The app's offline map matcher reads it.
- **Road geometry**, `roadgeom-<code>-<sha16>.sqlite.xz`: a SQLite database of road segments cut from
  intersection to intersection — OSM node and way ids, a polyline per segment, road names and refs —
  compressed with xz. The app uses it to name and draw the stretches of road that have been driven.

`roads-index.json` lists every pack with its size and sha256, the OSM data timestamp, the source extract
and the Valhalla version. The app reads it first.

**File names are content-addressed.** The `<sha16>` in a name is the first 16 hex digits of that file's
sha256, so a name never comes back with different bytes. A rebuilt province gets new names; an unchanged
one keeps its old ones.

## Licence

**The data in this repository — every pack and `roads-index.json` — is licensed under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/).**
The full text is in [`LICENSE`](LICENSE); who to credit is in [`ATTRIBUTION.md`](ATTRIBUTION.md).

The build pipeline that produces these packs is **not** in this repository and is not covered by this
licence. It lives in the Driveary app repository (`tools/road-pack/`); the ODbL attaches to the database,
not to the tools that made it.

## Files in this release

<!-- BEGIN generated: packs (render.py; do not edit by hand) -->
| Code | Region | Routing tiles | Bytes | Road geometry | Bytes |
| --- | --- | --- | ---: | --- | ---: |
| `ca-ab` | Alberta | `roads-ca-ab-338a5a42138f8cb5.tar.xz` | 23,522,980 | `roadgeom-ca-ab-8ceab32a5913a5a7.sqlite.xz` | 12,896,440 |
| `ca-bc` | British Columbia | `roads-ca-bc-4e12c76b19ae9a0a.tar.xz` | 20,253,836 | `roadgeom-ca-bc-b6c486ddc85adb94.sqlite.xz` | 11,196,080 |
| `ca-mb` | Manitoba | `roads-ca-mb-c3fe58a1cc5d34cf.tar.xz` | 6,836,668 | `roadgeom-ca-mb-340424d430ab72db.sqlite.xz` | 3,707,140 |
| `ca-nb` | New Brunswick | `roads-ca-nb-c99a4be808b3300c.tar.xz` | 4,775,824 | `roadgeom-ca-nb-e4cdc2395668c107.sqlite.xz` | 2,588,528 |
| `ca-nl` | Newfoundland and Labrador | `roads-ca-nl-39a58603f8c0a7ad.tar.xz` | 3,981,428 | `roadgeom-ca-nl-770becd17a9fa1eb.sqlite.xz` | 2,145,464 |
| `ca-ns` | Nova Scotia | `roads-ca-ns-5598f5da08620d97.tar.xz` | 7,506,424 | `roadgeom-ca-ns-f85669117da5bf64.sqlite.xz` | 3,763,832 |
| `ca-nt` | Northwest Territories | `roads-ca-nt-916e103257f1e119.tar.xz` | 508,172 | `roadgeom-ca-nt-a5f5f7ce27078cca.sqlite.xz` | 261,252 |
| `ca-nu` | Nunavut | `roads-ca-nu-f89e5ac14206ff0b.tar.xz` | 347,284 | `roadgeom-ca-nu-d163b245505e45d0.sqlite.xz` | 204,096 |
| `ca-on` | Ontario | `roads-ca-on-062ed70a3148bd19.tar.xz` | 38,343,056 | `roadgeom-ca-on-bd12b13a64a13d09.sqlite.xz` | 21,415,456 |
| `ca-pe` | Prince Edward Island | `roads-ca-pe-f82836e4bb775942.tar.xz` | 1,115,532 | `roadgeom-ca-pe-181279653d8cef1f.sqlite.xz` | 602,764 |
| `ca-qc` | Quebec | `roads-ca-qc-a3471f55244936fd.tar.xz` | 32,455,028 | `roadgeom-ca-qc-2ac1795751c5e7b4.sqlite.xz` | 16,956,176 |
| `ca-sk` | Saskatchewan | `roads-ca-sk-5eaf70fbe9fd3e52.tar.xz` | 10,835,472 | `roadgeom-ca-sk-1ee2f280e51a48b0.sqlite.xz` | 5,391,748 |
| `ca-yt` | Yukon | `roads-ca-yt-16b00501d391ef01.tar.xz` | 753,932 | `roadgeom-ca-yt-5a91ee1f3e2eb6f4.sqlite.xz` | 388,532 |
| | **Total** | | | | **232,753,144** |
<!-- END generated: packs -->

## Download

Every file is an asset of this repository's GitHub Release, under its own name:

```text
https://github.com/rodexyh/guzzle-roads/releases/download/v1/<file name>
```

The packs are not committed to the git history (each release is a few hundred MB); the release assets are
the canonical copies here.

**Same bytes as the CDN.** The app downloads these files from a CDN, not from GitHub, at
`roads/v1/<file name>`. The files attached to the release are byte-for-byte the files served there.

## Verify

Every file's sha256 is below (the same numbers are in `roads-index.json`). Save the block as
`SHA256SUMS` next to the downloaded files and run `shasum -a 256 -c SHA256SUMS`
(or `sha256sum -c SHA256SUMS` on Linux).

<!-- BEGIN generated: sha256sums (render.py; do not edit by hand) -->
```text
338a5a42138f8cb5c07cdbddca742bd32326ebb71cab75bc6ef1c9a13fb8c406  roads-ca-ab-338a5a42138f8cb5.tar.xz
8ceab32a5913a5a7adab88078afbd4e2674006b5978ba49a7bcf46c19ff23b87  roadgeom-ca-ab-8ceab32a5913a5a7.sqlite.xz
4e12c76b19ae9a0ac9bfe60d40905108a83c9118665756b97d6af8c4bcf592ad  roads-ca-bc-4e12c76b19ae9a0a.tar.xz
b6c486ddc85adb94dd7a0f0cd710f9cfd0d63a12ebcacfb308b6593f312f8e8d  roadgeom-ca-bc-b6c486ddc85adb94.sqlite.xz
c3fe58a1cc5d34cff236dd7c60961dee262676b111990de9cdc77f7574738e69  roads-ca-mb-c3fe58a1cc5d34cf.tar.xz
340424d430ab72db12d7d090f0e7cbe80f52fc7d473fb0c3164c3c57009fb19a  roadgeom-ca-mb-340424d430ab72db.sqlite.xz
c99a4be808b3300cb05545d875df8bc00a7f25ee041967ada29198a36b17c48f  roads-ca-nb-c99a4be808b3300c.tar.xz
e4cdc2395668c107570aea029b89da4c4a9519a44de9bb0e3bc5cfef9bc25299  roadgeom-ca-nb-e4cdc2395668c107.sqlite.xz
39a58603f8c0a7ad4d470c9f1f8b424703ce115e7d7615f452a878a78b935deb  roads-ca-nl-39a58603f8c0a7ad.tar.xz
770becd17a9fa1eb73d181f06289e39a0557b9be4b60847a52cca53df4ab33bd  roadgeom-ca-nl-770becd17a9fa1eb.sqlite.xz
5598f5da08620d97f0d7372231312c402176e6d5129709d3119ca52dd7ee9341  roads-ca-ns-5598f5da08620d97.tar.xz
f85669117da5bf64e3e67b6ddf28ce3617493e2289c915d9f6faa3235afac6df  roadgeom-ca-ns-f85669117da5bf64.sqlite.xz
916e103257f1e11927b374b9afb3d2f20805a46e51761dc7cdd8e22a6c0b0e5b  roads-ca-nt-916e103257f1e119.tar.xz
a5f5f7ce27078cca32ab5b7cf59f3497e514fe87fab38572fec1d9e87248511b  roadgeom-ca-nt-a5f5f7ce27078cca.sqlite.xz
f89e5ac14206ff0b2ef3213f3c2e639237265b33a7dcc82fa9cbf30ff63c8556  roads-ca-nu-f89e5ac14206ff0b.tar.xz
d163b245505e45d0b60d6c667d119a0f471146dd3326ebc378a579c2f3c4b29e  roadgeom-ca-nu-d163b245505e45d0.sqlite.xz
062ed70a3148bd1993617f4a8535ed289b23ba9212c00512fe662d4eca970e64  roads-ca-on-062ed70a3148bd19.tar.xz
bd12b13a64a13d09a2ea29e7d98e08af9fe7b08c96d522e63e349d7f69de3ef7  roadgeom-ca-on-bd12b13a64a13d09.sqlite.xz
f82836e4bb7759423c60779f7cc0642db7cf0949f1c7f36d22616db639615e17  roads-ca-pe-f82836e4bb775942.tar.xz
181279653d8cef1fddfb8421cb8f79ea329cf51fe35f28753d86f1a623f9c475  roadgeom-ca-pe-181279653d8cef1f.sqlite.xz
a3471f55244936fdf65d4b172e6ddac01e69d7defd7131af2492a1d6d586e33a  roads-ca-qc-a3471f55244936fd.tar.xz
2ac1795751c5e7b49dc079fd7aad935b4b5dbfd4aec83fadd8605212d4eaac51  roadgeom-ca-qc-2ac1795751c5e7b4.sqlite.xz
5eaf70fbe9fd3e52714fb552a65ff176b6d167a45f5088e116d1434135f6a20c  roads-ca-sk-5eaf70fbe9fd3e52.tar.xz
1ee2f280e51a48b097e4dfd41bfd545f864e910094a3110f9846fe6587803823  roadgeom-ca-sk-1ee2f280e51a48b0.sqlite.xz
16b00501d391ef0166fa835c655e728dd7b0fbf21131b77db44cf957df97b609  roads-ca-yt-16b00501d391ef01.tar.xz
5a91ee1f3e2eb6f4e9336523c4b777bdf96eff495b99a7e74a109f872c616bef  roadgeom-ca-yt-5a91ee1f3e2eb6f4.sqlite.xz
87da8296ca34b0edf8ef432610d5b383751aff74b92cd6974789948e94c8e6cf  roads-index.json
```
<!-- END generated: sha256sums -->

A few more checks that need no special tools:

```sh
xz -t roads-ca-ab-*.tar.xz                                   # the archive is intact
tar -tJf roads-ca-ab-*.tar.xz | head                         # index.bin first, then tiles in path order
xz -dc roadgeom-ca-ab-*.sqlite.xz > ab.sqlite
sqlite3 ab.sqlite "SELECT key, value FROM meta;"             # licence, attribution, source sha256, OSM timestamp
```

## Sources

Each province was built from one [Geofabrik](https://download.geofabrik.de/) extract of OpenStreetMap.
The dated URL is the exact file; its sha256 is what the build checked before starting.

<!-- BEGIN generated: sources (render.py; do not edit by hand) -->
| Code | OSM data as of | Source extract (dated URL) | Source sha256 |
| --- | --- | --- | --- |
| `ca-ab` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/alberta-260928.osm.pbf> | `11e306de40f2e56f697e4e5e77fca79b6d16f3049efdba122b92405256ed9da5` |
| `ca-bc` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/british-columbia-260928.osm.pbf> | `dc6693b909016f75921b7ea0ae7faa62782e42b596c853226a8babe3fb0ce2ed` |
| `ca-mb` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/manitoba-260928.osm.pbf> | `262898319dd378a64b41ad2de5f0415f68ccab70771c79abf59a601e9fdc242c` |
| `ca-nb` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/new-brunswick-260928.osm.pbf> | `9c8ba0a33c1889eafa7341ee041c63997d5eb0882eaa3a9521c6e91bfaeb3e4a` |
| `ca-nl` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/newfoundland-and-labrador-260928.osm.pbf> | `16b86ba370d7087ef901e58771c51720f703a2fbcffbf4771ff1f2f3127e5564` |
| `ca-ns` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/nova-scotia-260928.osm.pbf> | `c13060a950fda36807dbd05447aa95d3c2682aedf5f938c2940ebd8651cb2bf2` |
| `ca-nt` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/northwest-territories-260928.osm.pbf> | `74fa0fbcd971071871953ed05c00c1a633fb90b8b4f620e169a8b3d16674edf9` |
| `ca-nu` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/nunavut-260928.osm.pbf> | `cb6a173f471f9c936db9d5fa83a1fe52a753457e7f00332e3075671128459a23` |
| `ca-on` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/ontario-260928.osm.pbf> | `f480570bcc7b60f3ca2bcea01b379b979788f7b84cba0734f083556e2e754acd` |
| `ca-pe` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/prince-edward-island-260928.osm.pbf> | `a7b8c3439a7f637ad2b8081718a4933aa57729624b23e3cca9e851231ba059f5` |
| `ca-qc` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/quebec-260928.osm.pbf> | `b1c0e5e99dd068efc308d3cc726b8bff3961dfba73528d7b85373636b1dfda71` |
| `ca-sk` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/saskatchewan-260928.osm.pbf> | `825d5d9c5536d33955ed2cda07bf9ef6209fed16825bd43d28d40b503c4f3220` |
| `ca-yt` | 2026-09-28T20:23:05Z | <https://download.geofabrik.de/north-america/canada/yukon-260928.osm.pbf> | `12d9a09a79bc0786a2c21ac91e29b0684100c20a6f45ba8200c7fe1b353ce6c4` |
<!-- END generated: sources -->

## How the packs were made

For each extract: keep drivable roads and turn restrictions (`osmium tags-filter`), build routing tiles with
Valhalla 3.6.3 (`valhalla_build_tiles`), pack them into a tar laid out like `valhalla_build_extract` does,
cut the same filtered roads into intersection-to-intersection segments, compress both with `xz -6`
(single-threaded, so the same input gives the same bytes), and name each file after its sha256.

The step-by-step instructions, the exact filter and the checks the packs pass live in the Driveary app
repository, `tools/road-pack/README.md`.

One thing worth knowing if you rebuild: **Valhalla 3.6.3 routing tiles are not byte-for-byte reproducible**
— building the same extract twice changes a few tiles by a few bytes (matching results are the same). The
road geometry packs are reproducible byte for byte.

## Relationship to the app

- The app fetches `roads-index.json`, then downloads the whole-province packs it needs, checks each
  one's sha256 against the index and discards any file that does not match.
- **There is no user data here.** Every byte in every pack comes from the OpenStreetMap extracts listed
  above. Matching a drive to roads happens on the phone; which roads anyone drove is never uploaded —
  not to this repository and not anywhere else.
- Downloading a pack is an ordinary file download: like any web request, the CDN sees the address it
  came from and which file was asked for. The request carries nothing about the drive itself.

## Reporting a problem

The roads come from OpenStreetMap; we do not draw them. A missing or wrong road is best fixed in
[OpenStreetMap](https://www.openstreetmap.org/) — the correction reaches the next rebuild.
If a pack itself looks wrong (it fails its checksum, or a road that exists in OSM is missing from it),
open an issue in this repository.
