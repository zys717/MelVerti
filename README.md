# MelVerti: Melbourne Strategic Vertiport Siting Data

This repository contains the public data archive for a strategic vertiport siting study in metropolitan Melbourne, Australia. It brings together the collected source data, spatially processed datasets, candidate-property records, maximum covering location problem (MCLP) outputs, sensitivity results, and provenance metadata used in the analysis.

The repository is data-only. It does not contain the manuscript, analysis scripts, or publication figures. The complete checkout is approximately 3.2 GB and contains more than 2,600 files.

## Scope and interpretation

The archive supports strategic land-use and ground-transport analysis. Candidate properties in the processed outputs are model-selected analytical candidates, not approved, licensed, developable, or aeronautically feasible vertiport sites. Their identifiers and coordinates are retained to support traceability to the source Vicmap Property records.

Results for 15 facilities represent an exogenously specified planning scenario. They should not be interpreted as evidence that 15 facilities is an optimal network size. Airport-related screening uses 3 km hard buffers around Melbourne, Essendon Fields, and Moorabbin airports, with 4 km and 5 km sensitivity cases. Project-level site selection would require subsequent planning, ownership, engineering, safety, airspace, environmental, and regulatory due diligence.

## Repository structure

| Directory | Contents |
|---|---|
| `01_abs_census` | Australian Bureau of Statistics 2021 Census data used for population and demographic inputs. |
| `02_abs_boundaries` | ABS 2021 SA1 and SA2 boundary packages in GDA2020. |
| `03_gtfs` | Victorian public-transport GTFS feeds and associated source material. |
| `04_vicmap_planning` | Vicmap Planning urban growth boundary, planning zone, overlay, codelist, and service metadata. |
| `05_airports` | Reference points and aerodrome charts for Melbourne, Essendon Fields, and Moorabbin airports. |
| `06_travel_demand` | Victorian Integrated Survey of Travel and Activity (VISTA) resources and ABS Working Population Profile data. |
| `07_transport_patronage` | Annual metropolitan railway-station entry data. |
| `08_poi` | Vicmap Features of Interest point data, classification tables, and download metadata. |
| `09_vicmap_property` | Vicmap Property records and service metadata. The spatial SQLite extract contains 3,046,592 source parcel records. |
| `10_processed` | Study-area layers, demand and transport inputs, screening outputs, candidate properties, MCLP results, robustness checks, and manuscript-facing result tables. |
| `90_provenance` | Collection notes, checksums, download validation, and the reorganisation manifest linking the archived structure to the original collection. |

## Downloading the data

Several files exceed GitHub's standard file-size limit and are stored with Git Large File Storage (Git LFS). Install Git LFS before cloning:

```bash
git lfs install
git clone https://github.com/zys717/MelVerti.git
cd MelVerti
git lfs pull
```

The LFS-managed files include the large SA1 boundary files, one GTFS feed, the Vicmap planning zone and overlay layers, and the Vicmap Property SQLite extract. If a clone contains small text pointers instead of these datasets, run `git lfs pull` from the repository root.

## Data provenance

Source metadata is retained alongside the relevant datasets wherever available. Collection-level notes and integrity records are stored in `90_provenance`. The archive includes data from the Australian Bureau of Statistics, the Victorian Department of Transport and Planning, Vicmap, and Airservices Australia source material.

The source datasets retain their original provider-specific terms, attribution requirements, and temporal coverage. Users should consult the included metadata and the original providers when redistributing or updating individual datasets.

## File formats

The archive contains CSV, GeoJSON, GeoPackage, Shapefile, Parquet, SQLite, JSON, ZIP, XLSX, TXT, and PDF source-document formats. GeoPackage and processed vector layers can be opened in current GIS software. The Vicmap Property database is an Esri spatial SQLite export and may require Esri-compatible spatial extensions for full geometry-level access.

## Citation

If this archive is used in another study, cite the associated paper once bibliographic details are available and identify the repository as the supporting data archive:

> MelVerti: Melbourne Strategic Vertiport Siting Data. GitHub repository: https://github.com/zys717/MelVerti
