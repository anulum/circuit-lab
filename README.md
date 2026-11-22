<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-LAB — repository foundation
-->

# Circuit Lab

Circuit Lab is being built to govern first-silicon bring-up plans, instrument calibration certificates, shared laboratory timebase associations, high-voltage galvanic probe isolation and calibrated bench measurement captures — operating deterministically without AI while keeping every physical bench action strictly human-approved. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed bench-measurement runner, timebase synchroniser, calibration verifier or qualified record schema.

**What does not exist yet:**
- an instrument driver runner, bring-up sequencer or capture recorder;
- a registered runtime record schema;
- a self-driving autonomous laboratory bench or connected test instrument.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Measurement association | Binding of raw silicon or wafer-test channels to schematic nets, sensor calibrations, systematic uncertainty `U` (and differential `U_diff`) and held-out error parity bounds |
| Timebase association | Cross-instrument clock, trigger, phase-offset and drift mapping linking oscilloscopes, logic analysers, fabric counters and event loggers |
| Measurement request | First-silicon bring-up plan, shmoo voltage/frequency/temperature grid, high-voltage `GaN`/`SiC` galvanic differential/optical probe check, current-limit compliance and destructive failure-analysis sample quarantine |
| Measurement capture | Immutable raw waveforms, shmoo matrices, high-temperature operating-life (`HTOL`) bracket readouts and serial-numbered device/board provenance |
| Calibration certificate | Traceable calibration date, expiry window, uncertainty budget and serial identity of each bench instrument, probe and thermal chamber |

**Static imports:** only Circuit Core and Circuit Technology.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core and Circuit Technology | entity references, operation requests, admissions, data-handling profiles, operation profiles, person approvals, facility readiness, technology profiles and board profiles |
| Circuit Automation | equipment profiles, state observations, input-surface clamp envelopes and resource reservations |
| Circuit Digital, Circuit Mixed-Signal, Circuit Assembly, Circuit Devices and Circuit Prototyping | DFT/JTAG manifests, vector traces, firmware bindings, coupled expectations, carrier/load-board packages, compact models and prototype run records |
| Circuit Manufacturing and Circuit Acceptance | material states, change proposals, wafer-sort/serial-genealogy/RMA records, qualifications and acceptance reports |
| Loop Timing Witness and Spike Log | on-fabric timing witness and event-log formats |

**Capability registration and handoffs:** Registers the measurement tool-profile manifest with Circuit Core and connects over registered interfaces to Loop Timing Witness, Sim-Real Witness, Spike Groundtruth, Spike Log, AER Link Witness, Plasticity Witness, Randomness Witness, Reliability Witness, Spike Encoder Characteriser and Neuro Evidence Bench.

**Explicit non-claims and operating boundaries:**
- Because the coordination layer has no physical-effect verification operation today, every physical bench action requires an enrolled person-in-role approval, and an autonomous self-driving laboratory bench is not available today.
- Every bring-up and measurement workflow runs deterministically without machine learning.
- Silicon bench captures are immutable evaluation witnesses only — never reinforcement-learning reward signals, and debug captures can never be relabelled as promotion evidence.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
