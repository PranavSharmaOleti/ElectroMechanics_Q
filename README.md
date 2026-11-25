# ElectroMechanics_Q — Legacy Simscape Artifact

> **Status: historical artifact.** This repository contains one Simulink model and two supporting binary files, with no source scripts, parameter files, documentation or validation record. It is not a standalone engineering project and should be treated as an earlier electromechanical modelling snapshot.

## Contents

| File | Size | SHA-256 (model) | What it is |
|---|---:|---|---|
| `ElectroMechanics_GIT.slx` | 310,883 B | `87f1672aa8b1edd132437eaf1baf3c71a60ee2aae8ce32d40be86a62e7bd3ffa` | Simulink/Simscape model (binary `.slx` archive) |
| `ElectroMechanics.fig` | 25,145 B | — | MATLAB figure file |
| `Screenshot 2026-07-28 145240.png` | 24,683 B | — | 553 × 500 image capture from the same date |

## What the model contains

`ElectroMechanics_GIT.slx` is a zip container. Its readable XML shows a hierarchical model with five system files. The top level contains:

- a constant named `TC` producing a signal labelled "Torque Comand";
- a subsystem `ELECTROMECHANICS` with one input and one output (SOC);
- an Ideal Force Sensor and mechanical translational reference;
- a PS-Simulink Converter;
- a Record block logging two signals ("ELECTROMECHANICS" and the converter output).

Inside `ELECTROMECHANICS` there is an electrical reference and a table-based battery named `Panasonic:NCA593446`. Four further subsystems exist but are not documented here because their contents are not described by any text file in this repository.

No run instructions, parameter register, script or result table is present. The model requires MATLAB/Simulink with Simscape to open; it cannot be executed or independently verified from this repository alone.

## Relationship to the later quadrotor work

This is **not** the same model as the legacy propulsion model preserved in [`Quadrotor_System_Modelling`](https://github.com/PranavSharmaOleti/Quadrotor_System_Modelling) at `models/original/ElectroMechanics_Q.slx`, nor the `HoverLock/ElectroMechanics.slx` in [`HoverLock`](https://github.com/PranavSharmaOleti/HoverLock):

| Model | Size | SHA-256 | Structure |
|---|---:|---|---|
| This repo, `ElectroMechanics_GIT.slx` | 310,883 B | `87f1672a…` | Hierarchical (5 system XMLs), torque-command input, force sensor and logging |
| HoverLock `HoverLock/ElectroMechanics.slx` / QSM `models/original/ElectroMechanics_Q.slx` | 179,577 B | `9d9e1301…` | Flat (single system), propeller block, same Panasonic battery table |

The two are byte-for-byte different. The only verified common element is the Panasonic NCA593446 battery table. The QSM legacy model is the one that was formally audited and retired; this repository's model was not part of that audit record.

No evidence here establishes whether this model predates or parallels the HoverLock model. It should not be presented as the source of the QSM propulsion model, nor as a validated electromechanical design.

## Recommendation

Keep the repository as a frozen historical artifact with this README. If the files are not needed for future reference, archiving the repository on GitHub is the most accurate treatment — this requires an explicit owner decision and has not been done here.

No parameter values, performance figures or validation claims are made in this document because none are supported by the repository contents.
