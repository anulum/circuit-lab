<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-LAB — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Measurement association | Binding of raw silicon or wafer-test channels to schematic nets, sensor calibrations, systematic uncertainty `U` (and differential `U_diff`) and held-out error parity bounds | Equal held-out measurement-error parity across shmoo operating points |
| Timebase association | Cross-instrument clock, trigger, phase-offset and drift mapping linking oscilloscopes, logic analysers, fabric counters and event loggers | Verified trigger-skew and reference-oscillator lock before capture admission |
| Measurement request | First-silicon bring-up plan, shmoo voltage/frequency/temperature grid, high-voltage `GaN`/`SiC` galvanic differential/optical probe check, current-limit compliance and destructive failure-analysis sample quarantine | Facility readiness, valid instrument calibration certificates and person-in-role approval before any power-on or probe step |
| Measurement capture | Immutable raw waveforms, shmoo matrices, high-temperature operating-life (`HTOL`) bracket readouts and serial-numbered device/board provenance | Cryptographic capture digest, calibrated scale factors and non-relabelled debug-versus-evaluation mode |
| Calibration certificate | Traceable calibration date, expiry window, uncertainty budget and serial identity of each bench instrument, probe and thermal chamber | Automatic refusal of expired or uncalibrated instruments at admission |

## Human-gated bench safety and licence isolation

- **Zero unapproved agent actuation.** All five software-effect classes are refused on clamped bench instrument endpoints; every power supply, thermal chamber, signal generator or JTAG action requires an enrolled person-in-role approval.
- **High-voltage and destructive-FA guards.** Measurements above safe extra-low voltage require verified galvanic probe isolation before power-on, and destructive decapsulation or cross-sectioning quarantines the unit serial number permanently.
- **Licence isolation.** Permissive `VISA`/`SCPI` adapters run in-process, while any copyleft or proprietary vendor instrument daemon runs in a separate process.

## Planned record schemas

- `circuit_lab.measurement_association.v1`
- `circuit_lab.timebase_association.v1`
- `circuit_lab.measurement_request.v1`
- `circuit_lab.measurement_capture.v1`
- `circuit_lab.calibration_certificate.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
