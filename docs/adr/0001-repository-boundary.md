<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-LAB — repository foundation
-->

# Decision: keep calibrated silicon bring-up and bench measurement human-gated in Circuit Lab

## Context

Physical bench instruments can destroy scarce first-silicon units or create electrical/thermal hazards in milliseconds, while uncalibrated probes or skewed clocks invalidate silicon-to-simulation comparisons.

## Decision

**What Circuit Lab owns:**
- measurement association;
- timebase association;
- measurement request;
- measurement capture;
- calibration certificate;

**What it imports:** only Circuit Core and Circuit Technology.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| admission and person-in-role approvals | Circuit Core |
| facility readiness and board profiles | Circuit Technology |
| equipment input-surface clamps and cell safety | Circuit Automation |
| unit serial genealogy, wafer sort and RMA holds | Circuit Manufacturing |
| statistical acceptance verdicts | Circuit Acceptance |
| fabric timing and bitstream/stream witnesses | Evidence instrument repositories |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Lab owns calibration certificates, timebase associations, bring-up requests and raw captures;
- every physical bench action remains strictly human-approved until dedicated physical-effect verification exists;
- statistical sign-off stays separated in Circuit Acceptance.
