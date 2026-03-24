# Kiran Kumar's SysMLv2 Projects

Welcome to my portfolio! Here you'll find a curated collection of SysMLv2 models demonstrating my expertise in model-based systems engineering.

## About Me

I am a Master's student at the University of Bremen specialising in Space Engineering, with a solid foundation in Mechanical Engineering. Through diverse, user-centric projects I've honed my skills and continue to explore various areas within the engineering realm. I'm committed to continuous learning and staying abreast of the latest advancements in technology.

## Projects

| Directory | Project | Description |
|-----------|---------|-------------|
| [`turn-indication-controller/`](./turn-indication-controller/) | Turn Indication Controller | Behavioural and structural SysMLv2 models for a vehicle turn-indication system |
| [`garage-door-controller/`](./garage-door-controller/) | Garage Door Controller | Full SysMLv2 model (state machine + structure + requirements) for a GDC system |

---

## Turn Indication Controller

📁 [`turn-indication-controller/`](./turn-indication-controller/)

| Model | File |
|-------|------|
| Behavioural model | [`turn-indication-controller/behavioural-model.zip`](./turn-indication-controller/behavioural-model.zip) |
| Structural model | [`turn-indication-controller/structural-model.zip`](./turn-indication-controller/structural-model.zip) |

### Behavioural Model

Completes the `AutomotiveDomainLibrary/ApplicationLogic/ControlLogic` perform action used in the rear controller to decide commands sent over the CAN bus. The decision logic depends on:

- `BatteryVoltagePort`
- `TurnIndicationLeverPort`
- `EmergencyFlashButtonPort`
- `IgnitionPort`

State machines manage the transitions and control logic. A `CanController` model ensures that switching between active flashing modes sends an `OFF` command first, followed by a 50 ms delay before the new mode command.

### Structural Model

Defines part definitions, part usages, port definitions, port usages, and interfaces. A `SatisfactionRelations` package traces structural requirements to concrete model element usages.

---

## Garage Door Controller

📁 [`garage-door-controller/`](./garage-door-controller/)

| Model | File |
|-------|------|
| Full GDC model | [`garage-door-controller/model.zip`](./garage-door-controller/model.zip) |

The Garage Door Controller (GDC) manages the up/down movement of a garage door via an electric motor, handling commands `DOWN`, `UP`, `STOP`, and `REVERSE` based on inputs from a remote control, door sensors, and a light sensor for safety.

### Requirements

- **Safety:** The `BeamCrossed` signal from the light sensor triggers a `REVERSE` command.
- **Structural:** A physical barrier around the motor prevents direct physical contact.
- **Functional:** Remote-controlled start/stop, pause/resume at any point, and manual override for emergencies.

### Operational Environment

| Component | Signal(s) |
|-----------|-----------|
| Remote Control Device | `ButtonPressed` |
| Garage Door Mechanics | `DoorDown`, `DoorUp` |
| Light Sensor | `BeamCrossed` |
| Electric Motor | `DOWN`, `UP`, `STOP`, `REVERSE` |

---

## Using the Models

### Prerequisites

- **Eclipse IDE** – [Download](https://www.eclipse.org/downloads/)
- **SysMLv2 Plugin** – Install via *Help › Eclipse Marketplace*, search for **SysMLv2**

### Steps

1. **Download** the `.zip` file for the model you want to explore.
2. **Extract** the archive to a local folder.
3. **Open Eclipse** and go to *File › Import › Existing Projects into Workspace*.
4. **Select** the extracted folder and confirm all project files are visible in the Project Explorer.
5. **Open** any `.sysml` file, right-click it, and choose *Open with SysML Editor* to start exploring the model.
