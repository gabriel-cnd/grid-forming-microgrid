# Grid-Forming Microgrid Unit for Critical Loads

[![Project status: early development](https://img.shields.io/badge/status-early%20development-orange)](#project-status)
[![Documentation: in progress](https://img.shields.io/badge/documentation-in%20progress-blue)](#documentation)

Design, simulation, and Hardware-in-the-Loop (HIL) validation of a decentralized
grid-forming power unit for critical loads.

> [!IMPORTANT]
> This repository documents an ongoing thesis project. Models, interfaces,
> parameters, and results may change as the system requirements are refined.
> They must not be treated as production-ready designs or safety-certified
> control implementations.

## Overview

This project investigates a decentralized power unit combining photovoltaic
generation, a power converter, and energy storage. Its purpose is to improve
the resilience of critical services such as hospitals, cold storage, and
emergency communications during grid disturbances and outages.

Unlike a conventional grid-following inverter, which disconnects when the
utility grid is lost, the proposed unit should be able to:

- transition from grid-connected to islanded operation;
- establish local voltage and frequency;
- supply critical loads and share power with other units;
- remain stable under weak-grid and disturbed-grid conditions;
- resynchronize safely when the utility grid returns.

The work is conducted in the context of a collaboration between **HES-SO** and
**Birzeit University**.

## Project status

**Current phase:** project definition and literature review.

Requirements, system ratings, converter topology, control parameters, and
validation criteria have not yet been finalized. Progress and major decisions
will be documented in this repository as the project develops.

| Work package                 | Status      |
| ---------------------------- | ----------- |
| Requirements and use cases   | In progress |
| System sizing                | Not started |
| Single-unit PLECS model      | Not started |
| Grid-forming control         | Not started |
| Multi-unit load sharing      | Not started |
| Grid resynchronization       | Not started |
| Real-time HIL validation     | Not started |
| Final analysis and reporting | Not started |

The table above reflects the current public state of the project and will be
updated regularly.

## Objectives

- Size the inverter, output filter, and energy-storage system.
- Develop and verify a PLECS model of a single power unit.
- Design a grid-forming controller using droop control and virtual impedance.
- Implement operating-mode transitions and grid resynchronization.
- Extend the model to multiple units and evaluate load sharing.
- Assess stability under representative weak-grid and disturbance scenarios.
- Validate the control strategy in real time using a Plexim RT Box HIL setup.

## Technical scope

The preliminary system concept is shown below. Its final architecture is still
to be determined.

```text
PV source ─┐
           ├── DC link ── Grid-forming inverter ── Output filter ── AC bus
Storage ───┘                                                    ├── Critical loads
                                                                └── Utility grid
```

Planned research topics include:

- converter and filter sizing;
- inner voltage and current control loops;
- active- and reactive-power droop control;
- virtual impedance;
- islanding and operating-mode management;
- multi-converter power sharing;
- grid synchronization and reconnection;
- small-signal or simulation-based stability assessment;
- real-time HIL testing.

## Repository structure

The repository is organized by engineering responsibility. Each top-level
directory contains a short README describing its scope; specialized
subdirectories are populated progressively as the project develops.

```text
.
├── README.md               # Public project overview and status
├── description.md          # Initial project statement in French
├── docs/                   # Requirements, decisions, notes, and test protocols
├── models/                 # PLECS component and system models
├── control/                # Grid-forming control implementations
├── config/                 # Parameters and reproducible test scenarios
├── scripts/                # Sizing, automation, analysis, and plotting tools
├── hil/                    # RT Box interfaces and experiments
├── data/
│   ├── raw/                # Unmodified simulation and HIL acquisitions
│   └── processed/          # Data produced by documented processing steps
├── results/                # Selected figures, tables, and result summaries
└── report/                 # Thesis sources and supporting material
```

## Roadmap

1. Define system requirements, use cases, and performance criteria.
2. Select and size the converter topology, filter, and storage system.
3. Build and verify a single-unit model.
4. Design and tune the grid-forming controller.
5. Extend the model to multiple units and assess load sharing.
6. Define reproducible disturbance and transition scenarios.
7. Validate the design through real-time HIL experiments.
8. Publish the analysis, limitations, and conclusions.

## Tools

The expected toolchain currently includes:

- **PLECS** for power-electronics and control-system modelling;
- **Plexim RT Box** for real-time HIL validation;
- additional analysis and plotting tools to be selected later.

Exact software versions, dependencies, and setup instructions will be added
when the first executable models and scripts are published.

## Reproducing the work

The project is not yet at a reproducible release stage. Future simulation and
HIL studies will include, where possible:

- the model or script version used;
- all configurable parameters;
- a named test scenario;
- software and hardware versions;
- processing and plotting instructions;
- expected outputs or acceptance criteria.

Scenario names will follow a stable identifier convention, for example:

```text
S01_grid_loss
S02_load_step
S03_weak_grid
S04_multi_unit_load_sharing
S05_grid_resynchronization
```

## Results

No validated results are available yet. Selected results will be added here as
the corresponding milestones are completed, with links to the relevant model,
configuration, data, and analysis.

## Documentation

The initial French project statement is available in
[`description.md`](description.md). Requirements, design decisions, experiment
protocols, and technical notes will be added under `docs/`.

Major assumptions and unresolved questions will be recorded explicitly so that
the evolution of the design remains traceable.

## Contributing

The repository is currently developed as part of an academic thesis. Questions,
technical feedback, and suggestions are welcome through GitHub Issues once the
repository is published.

Before contributing code or models, please open an issue to discuss the proposed
change. Contribution guidelines may be added when the project reaches a more
stable stage.

## Academic information

- **Institution:** HEIG-VD
- **Academic partner:** Birzeit University
- **Student:** Gabriel Conde Garea
- **Supervisors:** Daniel Siemaszko

If you use material from this repository in academic work, please cite the
project. A formal citation file will be added when the bibliographic information
is finalized.

## License

A license has not yet been selected. Until a `LICENSE` file is added, the source
code, models, documentation, and other materials remain protected by copyright
and are not automatically licensed for reuse or redistribution.

Third-party software, models, and datasets remain subject to their respective
licenses.
