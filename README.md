# GreenRoots Rain Gardens

GIS tool estimating rain garden capacity across Chelsea, MA for GreenRoots.

## Output contract

### `outputs/parcels.csv` and `outputs/parcels.geojson`

| column | type | notes |
|---|---|---|
| `parcel_id` | string | unique parcel ID |
| `address` | string | street address |
| `owner_type` | string | `public` or `private` |
| `parcel_sqft` | number | total parcel area |
| `impervious_sqft` | number | roofs, pavement, etc. |
| `available_sqft` | number | area usable for a rain garden |
| `priority` | string | `high` / `medium` / `low` |

### `outputs/summary.json`

| field | meaning |
|---|---|
| `total_impervious_sqft` | sum of impervious area |
| `needed_min_sqft` | 1/8 of impervious area |
| `needed_max_sqft` | 1/3 of impervious area |
| `total_available_sqft` | sum of available area |
| `available_public_sqft` | available area on public parcels |
| `available_private_sqft` | available area on private parcels |

## Roles

- **Data** – find and download parcel / land-cover data, drop it in the shared Drive
- **Analysis** – scripts in `analysis/` that produce `outputs/`
- **Map** – web map in `web/` that reads `outputs/parcels.geojson`
- **Pitch** – slides and story in `docs/`

## Shared data

Raw data is too big for git (`data/` is ignored). Get it here:

**Google Drive:** _TODO: paste link_

## Setup

```bash
pip install -r analysis/requirements.txt
```

`outputs/` currently holds fake placeholder data so Map and Pitch can start right away.
