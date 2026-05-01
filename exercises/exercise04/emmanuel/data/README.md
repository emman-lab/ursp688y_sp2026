# Project Data Notes

## GTFS

Raw Ride On GTFS ZIP files are stored in `raw/gtfs/`.

Processed stop-level metrics and service-change files are stored in `processed/gtfs/`.

The main Exercise04 comparison is:

- `2025_january`: primary pre-Phase 1 baseline
- `2025_june`: first post-Phase 1 feed

## ACS

ACS outputs are intended to be stored in `processed/acs/`.

The planned Transit Need Index uses:

- percent of households without vehicles
- percent of people below poverty
- percent age 65 and over
- percent disabled

The script reads a Census API key from the local `CENSUS_API_KEY` environment variable if one is available.

## Geography

Montgomery County tract boundaries are stored in `processed/geography/`.

The source file is the 2024 TIGER/Line tract boundary ZIP for Maryland, filtered to Montgomery County.

## Final Analysis Outputs

Final project analysis tables are stored in `processed/final_analysis/`.

The key file is:

```text
processed/final_analysis/tract_service_panel_025mi.csv
```

This panel contains one row per Census tract per GTFS feed. It combines:

- 0.25-mile stop catchment service measures
- ACS Transit Need Index indicators
- GTFS feed labels and service dates

The main change files are:

```text
processed/final_analysis/tract_service_change_phase1_2025jan_to_2025jun_025mi.csv
processed/final_analysis/tract_service_change_current_2025jan_to_2026may_025mi.csv
```

These are the main files for testing whether higher-need tracts received larger scheduled service gains.
