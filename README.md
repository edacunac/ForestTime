# ForestTime v5.0.1

A mobile platform for IUFRO-standardized time studies in mechanized forest operations.

## Overview

ForestTime is an Android mobile application designed for conducting IUFRO-standardized time studies of mechanized forest operations. The application implements the time classification hierarchy defined by Björheden et al. (1995), with machine-specific sub-element decomposition for predefined equipment profiles.

## Features

- Machine-specific profiles: Harvester, Forwarder, Skidder, Processor, Feller-Buncher, Chainsaw, Yarder, and Custom.
- IUFRO-standardized time classification.
- Real-time sample size estimation.
- Automated R script generation.
- Millisecond precision using a monotonic system clock.
- Bilingual interface: English / Spanish.
- GPS geolocation at study initiation.
- Crash recovery with automatic saving after each event.
- Complete export package including CSV, JSON, and R script files.

## Installation

Download the APK from the latest GitHub Release and install it on an Android 7.0 or higher device.

## Machine Profiles

| Machine | Main work sub-elements | Production variables |
|---|---|---|
| Harvester | Move to tree, Felling, Delimbing, Bucking, Stacking | DBH, species, tree volume, number of logs |
| Forwarder | Travel empty, Loading, Travel loaded, Unloading | Distance, load volume, number of logs |
| Skidder | Travel empty, Choking/Grapple, Skid loaded, Unhook, Decking | Skid distance, number of pieces, volume, slope |
| Processor | Feed/Grab, Delimbing, Bucking, Stacking | DBH, species, log volume |
| Feller-Buncher | Move to tree, Felling, Accumulate, Dump bunch | Number of trees, DBH, species, slope |
| Chainsaw | Felling, Limbing, Bucking | DBH, species, height, slope |
| Yarder | Outhaul, Lateral in, Hook, Inhaul, Unhook/Deck | Yarding distance, number of logs, volume, slope |

## Export Format

The application exports a ZIP archive containing:

- `events_data.csv`: individual event records with IUFRO codes.
- `production_data.csv`: per-cycle production variables.
- `metadata.json`: study metadata, GPS coordinates, and computed indicators.
- `analysis_ForestTime.R`: dynamically generated R analysis script.

## Example Dataset

The supplementary dataset corresponds to a Tigercat LS855C shovel logger using the Feller-Buncher profile. It includes 7,353 events and 6,426 cycles collected over 8 working days.

## Citation

If you use ForestTime in your research, please cite:

Acuña, E., Cancino, J., Acuña, C., & Ambrosio, Y. ForestTime: A mobile platform for IUFRO-standardized time studies in mechanized forest operations. *International Journal of Forest Engineering*. Submitted.

## Authors

- Eduardo Acuña — Departamento de Manejo de Bosques y Medio Ambiente, Universidad de Concepción, Chile.
- Jorge Cancino — Departamento de Manejo de Bosques y Medio Ambiente, Universidad de Concepción, Chile.
- Cristóbal Acuña — Facultad de Ingeniería Agrícola, Universidad de Concepción, Chile.
- Yolanda Ambrosio — Departamento de Ingeniería y Gestión Forestal y Ambiental, Universidad Politécnica de Madrid, Spain.

## Laboratory

LASeR-EF — Laboratorio de Algoritmos y Sensoramiento Remoto en Ecosistemas Forestales  
Facultad de Ciencias Forestales, Universidad de Concepción, Chile.

## License

This project is licensed under the GNU General Public License v3.0. See the `LICENSE` file for details.
