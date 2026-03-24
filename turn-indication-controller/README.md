# Turn Indication Controller

This directory contains SysMLv2 models for the Turn Indication Controller system.

## Models

| File | Description |
|------|-------------|
| [`behavioural-model.zip`](./behavioural-model.zip) | State-machine-based behavioral model managing flashing indication logic |
| [`structural-model.zip`](./structural-model.zip) | Structural model with parts, ports, and interfaces for the controller |

## Overview

The Turn Indication Controller manages the flashing of indication lights in a vehicle. It reacts to:

- **BatteryVoltagePort** – monitors available power
- **TurnIndicationLeverPort** – detects left/right turn requests
- **EmergencyFlashButtonPort** – triggers hazard/emergency flashing
- **IgnitionPort** – tracks ignition state

### Behavioural Model

Completes the `AutomotiveDomainLibrary/ApplicationLogic/ControlLogic` perform action used in the rear controller. A `CanController` model ensures that switching between active flashing modes sends an `OFF` command first, followed by a 50 ms delay before the new mode command.

### Structural Model

Defines part definitions, part usages, port definitions, port usages, and interfaces connecting the ports. A `SatisfactionRelations` package traces structural requirements to concrete model element usages.

## Usage

See the [top-level README](../README.md#using-the-models) for import instructions.
