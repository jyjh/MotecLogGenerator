# MotecLogGenerator Examples

This directory contains some sample files to use with the MoTeC log generator tool.

## CAN
Files:
* `can_sample.log`
* `sample_can_spec.dbc`

Usage:
```bash
python3 ../motec_log_generator.py can_sample.log CAN --dbc sample_can_spec.dbc
```

## CSV
Files:
* `csv_sample.csv`

Usage:
```bash
python3 ../motec_log_generator.py csv_sample.csv CSV
```

## Lap beacons (`.ldx`)
Files:
* `laps_sample.txt`

A laps file lists one end-of-lap timestamp per line, in seconds, using the
same time base as the telemetry (i.e. the first column of the CSV). When
supplied via `--laps-file`, a `.ldx` sidecar is written alongside the `.ld`
file so MoTeC i2 splits the log into laps at those beacons. The `.ld` output
is unaffected.

Usage:
```bash
python3 ../motec_log_generator.py csv_sample.csv CSV --laps-file laps_sample.txt
```

This produces `csv_sample.ld` and `csv_sample.ldx`. Each timestamp marks the
moment of crossing start/finish to complete a lap (a MoTeC BCN beacon); the
final lap runs open-ended to the end of the log.

## Accessport
Files:
* `accessport_sample.log`

Usage:
```bash
python3 ../motec_log_generator.py accessport_sample.csv ACCESSPORT
```
