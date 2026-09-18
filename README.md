# Fungi Field Trip Data: Pisgah National Forest, NC

Repository for documenting and managing fungal specimen collection records, field observations, and spatial data from field trips in the Pisgah National Forest, North Carolina.

---

## 🌲 Field Collection Sites Overview

The Southern Appalachian Mountains within Pisgah National Forest represent one of the most biologically diverse temperate forest systems in the world, featuring abundant precipitation, varied topography, and diverse microclimates highly conducive to macrofungi.

### 1. Pink Beds Recreation Area & Trail
- **Coordinates:** `35.3533° N, 82.7801° W` (Trailhead & Picnic Area)
- **Habitat Type:** High-elevation montane bog and wetland swamp forest bordered by mixed cove hardwood-conifer forest (hemlock, white pine, rhododendron, mountain laurel, sphagnum moss).
- **Fungal Profile:** High humidity and wet soils support diverse hygrophilous species, wood-decay polypores, resupinates, bog-associated agarics, and chanterelles.
- **Nearby Amenities:**
  - **Parking:** Paved lot at Pink Beds Picnic Area off US-276.
  - **Restrooms:** Seasonal vault/flush toilets at picnic area.
  - **Food:** Cradle of Forestry Cafe (~1 mi north, seasonal); Pisgah Inn dining room (~4 mi north on Blue Ridge Parkway MP 408.6); full dining in Brevard (~12 mi south).

### 2. Bent Creek Experimental Forest & Lake Powhatan
- **Coordinates:** `35.4985° N, 82.6315° W` (Hard Times / Lake Powhatan Trailhead)
- **Habitat Type:** Southern Appalachian mature oak-hickory forest, mixed pine-hardwood stands, and moist alluvial creek corridors.
- **Fungal Profile:** Premier research area for ectomycorrhizal macrofungi (*Boletaceae*, *Amanitaceae*, *Russulaceae*, *Cortinariaceae*) and saprotrophs on hardwood logs.
- **Nearby Amenities:**
  - **Parking:** Ample trailhead parking (Hard Times, Rice Pinnacle, and Lake Powhatan Day Use).
  - **Restrooms:** Flush toilets at Lake Powhatan recreation area; vault toilets at primary trailheads.
  - **Food:** 10 minutes to South Asheville / Arden (NC-191 corridor) featuring supermarkets, restaurants, and cafes.

### 3. Looking Glass Falls & Moore Cove Corridor
- **Coordinates:** `35.2957° N, 82.7692° W` (US-276 Corridor)
- **Habitat Type:** Shaded, steep cove hardwood forest with spray cliff microclimates, waterfalls, abundant decaying coarse woody debris, and rich humus.
- **Fungal Profile:** Exceptional diversity of wood-rotting polypores, hydnoid fungi (*Hericium*), jelly fungi, coral fungi (*Ramaria*, *Clavulina*), and cup fungi (*Ascomycota*).
- **Nearby Amenities:**
  - **Parking:** Paved parking bays and roadside pull-offs along US-276.
  - **Restrooms:** Restrooms at Looking Glass Falls and nearby Davidson River Campground.
  - **Food:** The Hub and Pisgah Tavern, Hawg Wild BBQ, and downtown Brevard amenities (5–10 min south).

---

## 📋 Specimen Entry Data Schema

Each fungal collection entry should be recorded with the following structured metadata fields:

| Field Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `specimen_id` | String | Yes | Unique collection identifier format `PNF-YYYYMMDD-###` | `PNF-20260918-001` |
| `species_name` | String | Yes | Scientific binomial or working taxonomic identification | `Cantharellus appalachiensis` |
| `common_name` | String | No | Common or vernacular name | `Appalachian Chanterelle` |
| `gps_coordinates` | String / Object | Yes | Latitude and Longitude in decimal degrees (WGS84) + Elevation (m) | `35.3533, -82.7801 (el. 980m)` |
| `substrate_type` | String | Yes | Substrate / host material on which the specimen was growing | `Soil under Quercus alba / Tsuga canadensis` |
| `collection_date` | Date | Yes | Date specimen was collected (`YYYY-MM-DD`) | `2026-09-18` |
| `habitat_notes` | Text | Yes | Microhabitat conditions, slope, moisture, canopy, associated flora | `Moist streamside ravine, heavy leaf litter, damp moss cover` |
| `collector_name` | String | Yes | Full name of collector / field recorder | `Jane Doe` |
| `spore_print_color`| String | No | Observed color of spore deposit | `White to pale cream` |
| `photo_reference` | String | No | Relative path or filename of macro photos | `photos/PNF-20260918-001_macro.jpg` |

### JSON Format Example

```json
{
  "specimen_id": "PNF-20260918-001",
  "species_name": "Cantharellus appalachiensis",
  "common_name": "Appalachian Chanterelle",
  "gps_coordinates": {
    "latitude": 35.3533,
    "longitude": -82.7801,
    "elevation_m": 980
  },
  "substrate_type": "Humus / soil beneath Quercus alba and Tsuga canadensis",
  "collection_date": "2026-09-18",
  "habitat_notes": "North-facing slope near stream bed, dense rhododendron understory, high humidity.",
  "collector_name": "Jane Doe",
  "spore_print_color": "Yellow-ochre",
  "photo_reference": "photos/PNF-20260918-001.jpg"
}
```

### CSV Header Template

```csv
specimen_id,species_name,common_name,latitude,longitude,elevation_m,substrate_type,collection_date,habitat_notes,collector_name,spore_print_color,photo_reference
```

---

## 🎒 Field Protocol & Ethics

1. **Permits:** Scientific collection in Pisgah National Forest requires a valid scientific permit from the USDA Forest Service. Ensure all permits are secured prior to gathering specimens.
2. **Specimen Care:** Wrap specimens individually in wax paper or aluminum foil (avoid plastic bags which cause moisture condensation).
3. **Data Recording:** Record GPS coordinates, substrate, and field photos before disturbing the fruiting body.
4. **Leave No Trace:** Tread lightly on sensitive bog habitats (such as Pink Beds) to preserve delicate mosses and rare vascular plants.
