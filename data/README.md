# ForestTime public demonstration dataset

This directory contains the anonymized dataset used to demonstrate the ForestTime workflow with a Tigercat LS855C shovel logger. The Feller-Buncher profile was used because the specific machine was not available among the predefined profiles.

## Files

- `foresttime_ls855c_events_anonymized.csv`: 7,353 coded event records.
- `foresttime_ls855c_summary.csv`: study-level and cycle-time summary statistics.
- `foresttime_ls855c_data_dictionary.csv`: field definitions and units.
- `foresttime_ls855c_anonymization_log.csv`: transformations applied before publication.

The data contain 6,426 productive cycles across eight coded study days. Seven cycles above 120 seconds are identified by a flag and retained; one zero-duration record from the source was excluded. Direct personal identifiers, company and location names, stand identifiers, calendar dates, clock times, and free-text notes are not included.

Study days and event identifiers are synthetic sequential codes. `start_offset_seconds` is relative to the first retained event and cannot be used to reconstruct a calendar date.

## Reproducibility

The summary values were calculated from the anonymized event table. Values in seconds use the original recorded durations; rounded values in the summary file are provided for reporting convenience.

## License

These data are available under the [Creative Commons Attribution 4.0 International license](LICENSE.md). Please cite the ForestTime software and associated article when using them.
