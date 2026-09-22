# 2026-09-17 supplementary collection

This collection adds demand, activity, public-transport usage, POI and parcel-source metadata to the existing Melbourne vertiport data package. Source contents were retained without analytical transformation.

## Acquired

- DTP VISTA 2024–25: household, person, trip, stop, journey-to-work and journey-to-education CSV resources, explanatory document and CKAN package metadata.
- ABS 2021 Working Population Profile for Victoria, all available geographies, plus the untouched source ZIP.
- ABS 2021 SA2 GDA2020 national boundary package, plus the untouched source ZIP.
- DTP annual metropolitan train station entries for FY2018–19 through FY2024–25 and CKAN package metadata.
- Vicmap Features of Interest point records intersecting the bounding box of the downloaded PLAN_UGB line layer, with service/layer metadata and classification reference tables.
- Vicmap Property service, layer and LGA reference metadata, plus a completed Esri spatial SQLite export of parcels intersecting the PLAN_UGB bounding box.

## Scope cautions

- VISTA is a weighted household travel survey. Its public trip resource identifies origin and destination LGA and is suitable for aggregate travel-pattern evidence; it is not a fine-resolution observed OD census.
- ABS Working Population Profile describes the population counted at place of work. It is not an origin-destination commuting flow table.
- Station-entry CSVs measure entries at metropolitan train stations and do not cover tram/bus boardings or transfers.
- The Vicmap FOI file is a bounding-box extraction. It includes locations outside the final UGB polygon and must be clipped after a valid UGB polygon is constructed.
- The Vicmap Property file uses the same bounding-box logic and contains 3,046,592 parcels. It must be clipped to the final UGB polygon before parcel screening.
- POI counts measure mapped facilities, not trip demand. Facility type, duplication, currency and relevance must be screened before use.

## Integrity checks

- Both newly downloaded ABS ZIP archives passed `unzip -t`.
- The FOI export contains 19,249 GeoJSON features, matching its download manifest.
- The root `SHA256SUMS.txt` was regenerated after the collection and excludes itself and `.DS_Store` files.
- The Vicmap Property server job and local feature table both report 3,046,592 records; all OBJECTID values in the local table are unique.
- The parcel database is an Esri spatial SQLite file and requires Esri-compatible spatial extensions for full database-level validation. Its main feature table is readable with system SQLite, and the downloaded file SHA-256 is `09130dfabfd561e76a8fa4bba916cc8940309db21935d840e2ba9320373d9a43`.
