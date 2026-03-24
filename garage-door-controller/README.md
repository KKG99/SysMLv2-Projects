# Garage Door Controller

This directory contains the SysMLv2 model for the Garage Door Controller (GDC) system.

## Models

| File | Description |
|------|-------------|
| [`model.zip`](./model.zip) | Full GDC model including state machine, structural parts, and requirement traces |

## Overview

The Garage Door Controller manages the up and down movements of a garage door via an electric motor. It handles the following commands:

- **DOWN** – close the door
- **UP** – open the door
- **STOP** – pause movement
- **REVERSE** – reverse direction (triggered by safety sensor)

### Operational Environment

| Component | Signal(s) |
|-----------|-----------|
| Remote Control Device | `ButtonPressed` |
| Garage Door Mechanics | `DoorDown`, `DoorUp` |
| Light Sensor | `BeamCrossed` |
| Electric Motor | `DOWN`, `UP`, `STOP`, `REVERSE` |

### Requirements

**Safety:** The `BeamCrossed` signal from the light sensor must trigger a `REVERSE` command.

**Structural:** A physical barrier around the motor prevents direct physical contact.

**Functional:**
- The remote control can start and stop the door's movement.
- Movement can be paused and resumed at any point.
- A manual override option is available for emergencies.

## Usage

See the [top-level README](../README.md#using-the-models) for import instructions.
