<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-LAB — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Lab is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Calibration and timebase setup** verify unexpired instrument calibration certificates and establish cross-instrument trigger/clock associations.
2. **Human-approved bring-up preparation** checks facility readiness, high-voltage galvanic probe isolation, current-compliance clamps and destructive-FA sample holds before requesting person-in-role approval.
3. **Calibrated capture** records raw bench waveforms, shmoo sweeps and `HTOL` bracket points bound to the unit's serial number and systematic uncertainty.
4. **Post-silicon feedback** delivers immutable captures to Circuit Acceptance, Circuit Devices, Circuit Technology, Circuit Manufacturing and the evidence witnesses.

## Ownership

**This project owns** the planned Circuit Lab records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| admission and person-in-role approvals | Circuit Core |
| facility readiness and board profiles | Circuit Technology |
| equipment input-surface clamps and cell safety | Circuit Automation |
| unit serial genealogy, wafer sort and RMA holds | Circuit Manufacturing |
| statistical acceptance verdicts | Circuit Acceptance |
| fabric timing and bitstream/stream witnesses | Evidence instrument repositories |

## Interpretation

- **Single unit.** A bench capture characterises the serial-numbered unit tested under its stated uncertainty `U`.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
