<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-LAB — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- bring-up plans and shmoo grids;
- calibration certificates and timebase logs;
- raw instrument waveforms and wafer-test summaries.

They grant no authority to:
- actuate a power supply, probe station or thermal chamber without person-in-role approval;
- admit captures from expired or uncalibrated instruments;
- use silicon captures as reinforcement-learning rewards or relabel debug runs as acceptance runs;
- self-certify regulatory compliance or publish.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Unattended agent actuation of laboratory power supplies, probes or thermal chambers | Clamped instrument endpoints refuse software effects from agents; every physical bench action requires an enrolled person-in-role approval |
| Uncalibrated instruments, skewed clocks, high-voltage ground-loop damage or lost FA units | Admission checks unexpired calibration certificates, explicit timebase associations, high-voltage galvanic probe isolation and destructive-FA serial quarantine |
| Relabelling exploratory debug captures as promotion or sign-off evidence | Captures bind their pre-declared request digest, unit serial number and shmoo error parity immutably at acquisition |

## Residuals named, not removed

- **Fixture parasitics.** De-embedding accuracy rests on the calibrated probe-card or load-board characterisation from Circuit Assembly.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
