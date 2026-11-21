# Audi Q5 Fixes

Tested fixes, troubleshooting and upgrades for my Japanese-import
2018 Audi Q5.

## Vehicle and MMI

- Vehicle: 2018 Audi Q5
- Original market: Japan
- MMI: MIB2 High, Harman Qualcomm
- Software: MHI2Q_ER_AUG22_P5092
- MU version: 1329
- Location: New Zealand

## Confirmed fixes

### ROW 2026 Australia/New Zealand map update

Successfully updated from ROW 2022/2023, version 0101, to
ROW 2026, version 0433.

The procedure includes the 21 selected components, an initial
“unable to read metainfo — error code 8” failure, and the
successful installation using SD1.

New Zealand address search and route calculation were confirmed
working on 21 November 2026.

[Read the full Australia/New Zealand map update guide](fixes/row-2026-australia-nz-maps/README.md).

## How these guides are documented

Each guide records:

- The exact vehicle/software configuration tested.
- The original problem.
- What worked and what failed.
- How the result was checked.
- Recovery limitations and anything still unverified.

Unresolved investigations will be labelled separately from
confirmed fixes.

## Applicability

These are reports from one vehicle, not universal instructions.
Check your hardware, software, regional configuration and backup
options before applying a procedure.

This repository does not distribute map packages, proprietary
firmware, activation files or vehicle credentials.
