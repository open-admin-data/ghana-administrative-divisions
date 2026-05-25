# Ghana Administrative Divisions / Ghana



## Overview

| Item | Details |
|------|---------|
| Region | 16 |
| District | 260 |
| Town | 2,079 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-25 |

## Browse by Region

| # | Region | Districts | Towns | Link |
|---|----|----|----|------|
| 1 | Ahafo | 6 | 34 | [Browse](divisions/ahafo-gh01/) |
| 2 | Ashanti | 43 | 389 | [Browse](divisions/ashanti-gh02/) |
| 3 | Bono | 12 | 76 | [Browse](divisions/bono-gh03/) |
| 4 | Bono East | 11 | 47 | [Browse](divisions/bono-east-gh04/) |
| 5 | Central | 22 | 147 | [Browse](divisions/central-gh05/) |
| 6 | Eastern | 33 | 260 | [Browse](divisions/eastern-gh06/) |
| 7 | Greater Accra | 29 | 222 | [Browse](divisions/greater-accra-gh07/) |
| 8 | Northern | 16 | 93 | [Browse](divisions/northern-gh08/) |
| 9 | Northern East | 6 | 31 | [Browse](divisions/northern-east-gh09/) |
| 10 | Oti | 8 | 58 | [Browse](divisions/oti-gh10/) |
| 11 | Savannah | 7 | 42 | [Browse](divisions/savannah-gh11/) |
| 12 | Upper East | 15 | 169 | [Browse](divisions/upper-east-gh12/) |
| 13 | Upper West | 11 | 109 | [Browse](divisions/upper-west-gh13/) |
| 14 | Volta | 18 | 173 | [Browse](divisions/volta-gh14/) |
| 15 | Western | 14 | 144 | [Browse](divisions/western-gh15/) |
| 16 | Western North | 9 | 85 | [Browse](divisions/western-north-gh16/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 16 region records |
| [all-district.json](data/all-district.json) | JSON | All 260 district records |
| [all-town.json](data/all-town.json) | JSON | All 2,079 town records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=district, 3=town |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{district-slug}/
```

Towns are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Ghana Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/ghana-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
