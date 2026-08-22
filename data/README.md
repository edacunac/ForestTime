# ForestTime public demonstration dataset

This directory contains the anonymized dataset used to demonstrate the ForestTime workflow with observations of a Tigercat LS855C feller-buncher. Because this machine was not represented by a dedicated predefined option, ForestTime was configured using the Custom profile. Move to Tree, Felling, and Accumulate were defined as main-work elements, while Clear Brush was defined as complementary work.

## Files

- `foresttime_ls855c_events_anonymized.csv`: 7,353 coded event records.
- `foresttime_ls855c_summary.csv`: study-level and cycle-time summary statistics.
- `foresttime_ls855c_data_dictionary.csv`: field definitions and units.
- `foresttime_ls855c_anonymization_log.csv`: transformations applied before publication.

The data contain 6,426 felling cycles across eight coded study days. Seven cycles above 120 seconds are identified by a flag and retained; one zero-duration record from the source was excluded. Direct personal identifiers, company and location names, stand identifiers, calendar dates, clock times, and free-text notes are not included.

Study days and event identifiers are synthetic sequential codes. `start_offset_seconds` is relative to the first retained event of each study day and cannot be used to reconstruct a calendar date.

## Reproducibility

The summary values were calculated from the anonymized event table. Values in seconds use the original recorded durations; rounded values in the summary file are provided for reporting convenience. The CSV files are the authoritative public data.

## Archive

The dataset accompanies ForestTime v5.4.0 and is permanently archived at [https://doi.org/10.5281/zenodo.22062332](https://doi.org/10.5281/zenodo.22062332).

## License

These data are available under the [Creative Commons Attribution 4.0 International license](LICENSE.md). Please cite the ForestTime software and associated article when using them.
