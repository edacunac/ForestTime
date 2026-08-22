# ForestTime v5.4.0

A mobile platform for IUFRO-standardized time studies in forest operations.

## Overview

ForestTime is an Android mobile application for conducting direct-observation time studies in mechanized, motor-manual, and manual forest operations. It implements the International Union of Forest Research Organizations (IUFRO) time-classification hierarchy together with machine-specific and user-defined work elements.

## ForestTime 5.4.0

Version 5.4.0 introduces and clarifies:

- Retrospective completed-element recording: activity buttons label the interval that has just ended.
- Start observation (SO) arms the study while the timer remains at zero until the first activity is selected.
- Continuous timing across activity transitions.
- Cycle-boundary handling that assigns data-entry time to the first completed element of the next cycle rather than automatically classifying it as delay.
- Configurable allowable relative error for live sample-size estimation (5% default).
- Metric and Imperial unit systems.
- Updated recovery, diagnostics, guidance, branding, and version information.

Voice control is not included in this release. It remains a future-development option requiring validation under noisy field conditions.

## Core features

- Predefined profiles: Harvester, Forwarder, Skidder, Processor, Feller-Buncher, Chainsaw, and Yarder.
- Custom profile for machines or operations not represented by a predefined template.
- IUFRO-standardized time classification.
- Real-time sample-size estimation.
- Automated R-script generation.
- Millisecond-resolution timing using a monotonic system clock.
- English and Spanish interface.
- Optional GPS geolocation at study initiation.
- Crash recovery with automatic persistence after each event.
- Export package containing CSV, JSON, and R files.

## Installation

Download `ForestTime-5.4.0-release.apk` from the [v5.4.0 GitHub release](https://github.com/edacunac/ForestTime/releases/tag/v5.4.0). Android 7.0 (API 24) or later is required.

ForestTime 5.4.0 uses a new application-signing key. Devices with ForestTime 5.3.0 or an earlier release installed must uninstall the previous version before installing 5.4.0. Export any studies that must be retained before uninstalling.

## Observation workflow

1. Define Identification, Study Conditions, and Machine Type.
2. Press SO to arm the observation; the timer remains at zero.
3. Select the first activity when it actually begins.
4. At each subsequent boundary, select the activity that has just been completed.
5. Press New Cycle at the cycle boundary and enter the selected production variables.
6. Review the live indicators and export the study package.

## Machine profiles

| Machine | Main-work sub-elements | Example production variables |
|---|---|---|
| Harvester | Move to Tree, Felling, Delimbing, Bucking, Stacking | DBH, species, tree volume, number of logs |
| Forwarder | Travel Empty, Loading, Travel Loaded, Unloading | Distance, load volume, number of logs |
| Skidder | Travel Empty, Choking/Grapple, Skid Loaded, Unhook, Decking | Skid distance, number of pieces, volume, slope |
| Processor | Feed/Grab, Delimbing, Bucking, Stacking | DBH, species, log volume |
| Feller-Buncher | Move to Tree, Felling, Accumulate, Dump Bunch | Number of trees, DBH, species, slope |
| Chainsaw | Felling, Limbing, Bucking | DBH, species, height, slope |
| Yarder | Outhaul, Lateral In, Hook, Inhaul, Unhook/Deck | Yarding distance, number of logs, volume, slope |

## Export format

The application exports a ZIP archive containing:

- `events_data.csv`: individual event records and IUFRO codes.
- `production_data.csv`: cycle-level production variables.
- `metadata.json`: study metadata, optional GPS coordinates, configuration, and indicators.
- `analysis_ForestTime.R`: generated R analysis script intended as a reproducible analytical starting point.

CSV remains the authoritative tabular format because it is open, lightweight, inspectable, and directly compatible with R, Python, spreadsheets, and statistical software.

## Demonstration dataset

The public anonymized dataset demonstrates the workflow using observations of a Tigercat LS855C feller-buncher. Because the machine was not represented by a dedicated predefined option, the Custom profile was used. The dataset contains 7,353 coded event records and 6,426 felling cycles across eight anonymized study-day codes. Calendar dates, clock times, personal identifiers, company and location names, and free-text notes are not included.

See the [data documentation](data/README.md).

## Citation and archive

ForestTime v5.4.0 and the accompanying anonymized example data are archived at:

[https://doi.org/10.5281/zenodo.22062128](https://doi.org/10.5281/zenodo.22062128)

If you use ForestTime in research, please cite:

Acuña, E., Cancino, J., Acuña, C., & Ambrosio, Y. *ForestTime: A mobile platform for IUFRO-standardized time studies in forest operations*. International Journal of Forest Engineering. Manuscript under review.

## Authors

- Eduardo Acuña — Departamento de Manejo de Bosques y Medio Ambiente, Universidad de Concepción, Chile.
- Jorge Cancino — Departamento de Manejo de Bosques y Medio Ambiente, Universidad de Concepción, Chile.
- Cristóbal Acuña — Facultad de Ingeniería Agrícola, Universidad de Concepción, Chile.
- Yolanda Ambrosio — Departamento de Ingeniería y Gestión Forestal y Ambiental, Universidad Politécnica de Madrid, Spain.

## Laboratory

LASeR — Facultad de Ciencias Forestales, Universidad de Concepción, Chile.

## Licenses

The ForestTime APK is distributed under the [ForestTime Academic Use License 1.0](LICENSE). It may be installed and used, without modification, for non-commercial academic research and teaching. Modification, reverse engineering, redistribution, sublicensing, and commercial use are not permitted except where applicable law requires otherwise or prior written permission is obtained from the copyright holders.

The demonstration data in the `data` directory are distributed separately under the Creative Commons Attribution 4.0 International license.
