# karoo-custom-mapstyle-gravel

A custom map style for Hammerhead Karoo 3, based on the original `offline_v15.xml`, focused on gravel riding, bikepacking, and clearer distinction of roads, paths, surfaces, and useful POIs.

This project starts from the original Hammerhead Karoo 3 V15 style. Inspiration and selected ideas come from [dansoft-ch/karoo-custom-mapstyle](https://github.com/dansoft-ch/karoo-custom-mapstyle).

## Contents

- `offline_v15.xml` - current map style.
- `icons-kmen/` - additional and customized POI icons.
- `docs/legend_kmen_compact.html` - compact legend for quick mobile reference.

## Key changes

- Clearer bike-related paths:
  - `highway=cycleway`
  - `highway=path + bicycle=yes|designated`
  - `highway=path + cycleway=*`
  - bike route networks `icn`, `ncn`, `rcn`, `lcn`
- Better distinction for tracks, rural roads, and unpaved surfaces:
  - `tracktype=grade1..grade5`
  - better unpaved `compacted|gravel|fine_gravel`
  - rougher unpaved `ground|dirt|grass|sand|unpaved`
  - separate styles for non-bike `highway=path`
- Bikepacking-focused POI visibility:
  - camping, caravan site, hostel/hotel/lodging
  - shelter/hut
  - slipway/marina/dock/canoe-kayak access
  - fuel, drinking water, supermarket, coffee, bike service
- Darker forest, more visible sand/beach and natural terrain.
- Stronger town and city labels.
- Brown contour lines with lower elevation-label priority.

## Installation on Hammerhead Karoo 3

1. Connect Karoo 3 to your computer via USB.
2. Enable developer options on Karoo if they are not already enabled.
3. In developer settings, set the default USB mode to file transfer.
4. Open Karoo internal storage.
5. Locate the current style file, for example `offline_v15.xml`.
6. Create a backup, for example `offline_v15.xml.backup`.
7. Copy from this repository to the Karoo storage root:
   - `offline_v15.xml`
   - `icons-kmen` directory
8. Make sure the style filename matches the version expected by your Karoo firmware.
   - for version 15: `offline_v15.xml`
   - if your Karoo uses another version, rename accordingly, e.g. `offline_v16.xml`
9. Disconnect Karoo and reopen map view, or reboot the device.

After major Karoo system updates, the style may be overwritten. In that case, copy the XML again and ensure the filename matches the current `offline_vXX.xml` version.

## Compact legend

The compact legend is available at:

```text
docs/legend_kmen_compact.html
```

You can open it in a mobile browser. It represents the current `karoo-custom-mapstyle-gravel` style only.

### Legend summary (from `docs/legend_kmen_compact.html`)

- **Bike**
  - Cycleway (`highway=cycleway`)
  - Unpaved cycleway overlays
  - Bike-access path (`highway=path + bicycle=yes|designated`)
  - Path with cycleway tagging (`highway=path + cycleway=*`)
  - Bicycle networks (`icn/ncn/rcn/lcn`) with clear colored highlighting

- **Track and non-bike paths**
  - Plain path (`highway=path` without bike tags)
  - Good path surfaces (`compacted|gravel|fine_gravel`)
  - Rough path surfaces (`ground|dirt|grass|unpaved`)
  - Sandy path (`surface=sand`)
  - Track quality levels: `grade1` to `grade5`

- **Regular roads**
  - `motorway|trunk`
  - `primary`
  - `secondary`
  - `tertiary`
  - `residential|living_street`
  - `unclassified|road`
  - service roads (`driveway|parking_aisle|alley`)

- **Unpaved roads**
  - Good unpaved casing (`compacted|gravel|fine_gravel`)
  - Rough unpaved casing (`ground|dirt|grass|sand|unpaved`)
  - Standard local roads without `surface=*`

- **Terrain**
  - forest/wood
  - sand/beach
  - grassland/scrub
  - farmland/meadow/orchard background
  - water
  - glacier/ice shelf

- **Bikepacking POIs (icons-kmen)**
  - camping/caravan
  - slipway/marina
  - lodging/hostel/hotel
  - shelter/hut
  - canoe/kayak access
  - fuel station
  - drinking water
  - bike shop/service
  - supermarket
  - coffee

- **Contours and place names**
  - minor and major contours in brown (`#938945`)
  - place-name emphasis:
    - city: zoom 6, priority 70, size 20
    - town: zoom 7, priority 50, size 18
    - village: zoom 9, priority 40, size 17
    - hamlet: zoom 11, priority 30, size 16

## Notes

The style depends on tags stored in the offline `.map` file. If a tag exists in online OpenStreetMap but is not present in the Karoo offline map extract, the style cannot render it.

Example: if the offline map does not contain `leisure=marina`, the marina rule will not appear, even if marina objects are visible in online OSM.

## Inspiration and installation references

- [dansoft-ch/karoo-custom-mapstyle](https://github.com/dansoft-ch/karoo-custom-mapstyle)
- [Wgranie nowego stylu map do Karoo Hammerhead 3](https://bobiko.blog/2026/02/hammerhead-karoo3-style/)
