# Dalian University of Technology High-Speed Bearing Fault Diagnosis Dataset
This repository contains a laboratory high-speed rolling bearing fault diagnosis dataset. The dataset was collected from a modular high-speed bearing fault simulation test rig and is intended for machine learning, signal processing, and rotating machinery fault diagnosis research.

## Overview

The dataset includes vibration signals measured under different bearing health conditions. A 6205 rolling bearing was installed in the bearing housing and replaced with artificially damaged bearings to simulate multiple fault modes. Acceleration signals were collected in three directions under a fixed high-speed operating condition.

The dataset can be used for tasks such as:

- Bearing health condition classification
- Fault feature extraction from vibration signals
- Deep learning model training and evaluation
- Multi-axis vibration signal analysis
- High-speed rotating machinery fault diagnosis

## Experimental Test Rig

The experiments were conducted on a laboratory high-speed bearing fault simulation test rig. The test rig uses a modular design and mainly consists of:

- Electric spindle
- Torque and speed sensor
- Rotor shaft system
- Rolling bearing housing
- Shaft load disk
- Radial loading device
- Sensor mounting bracket
- Coupling
- Test platform base
- Control system

Key test rig specifications:

| Item | Specification |
|---|---:|
| Electric spindle rated voltage | 380 V |
| Electric spindle rated power | 5.5 kW |
| Maximum spindle speed | 15,000 rpm |
| Radial loading range | 0–2,000 N, continuously adjustable |
| Torque-speed sensor range | 50 Nm |
| Bearing type | 6205 rolling bearing |
| Sensor mounting | Magnetic mounting on the bearing housing |
| Measured directions | X, Y, and Z acceleration signals |

## Bearing Health Conditions

The dataset contains vibration signals for the following bearing conditions:

| Label | Condition | Description |
|---:|---|---|
| 0 | Normal | Healthy bearing |
| 1 | Inner race fault | Artificially induced inner race defect |
| 2 | Outer race fault | Artificially induced outer race defect |
| 3 | Rolling element fault | Artificially induced rolling element defect |
| 4 | Cage fault | Artificially induced bearing cage defect |

> Note: Label IDs are recommended for consistency. If your released data files use a different label mapping, please update the table above accordingly.

## Data Acquisition Settings

The vibration signals were collected under the following operating condition:

| Parameter | Value |
|---|---:|
| Rotational speed | 6,000 rpm |
| Sampling frequency | 25.6 kHz |
| Sampling duration | 60 s per condition |
| Signal type | Acceleration |
| Channels | X-axis, Y-axis, Z-axis |
| Bearing type | 6205 rolling bearing |

For each bearing condition, vibration signals from the three acceleration directions were recorded and organized into samples suitable for neural network training.

## Suggested Data Format

A recommended data organization is shown below. Adjust this section if your repository uses a different file structure.

```text
.
├── README.md
├── data/
│   ├── normal/
│   ├── inner_race_fault/
│   ├── outer_race_fault/
│   ├── rolling_element_fault/
│   └── cage_fault/
├── labels.csv
└── scripts/
```

A recommended metadata file format is:

| Column | Description |
|---|---|
| `file_name` | Name of the signal file |
| `label` | Numeric class label |
| `condition` | Bearing health condition |
| `speed_rpm` | Rotational speed in rpm |
| `sampling_frequency_hz` | Sampling frequency in Hz |
| `duration_s` | Acquisition duration in seconds |
| `channels` | Signal channels, such as `x,y,z` |

## Usage Notes

When using this dataset, please ensure that:

- Training, validation, and test sets are split without data leakage.
- Signal segmentation parameters, such as window length and overlap ratio, are clearly reported.
- Channel usage is specified, for example single-axis input or three-axis input.
- Preprocessing methods such as normalization, filtering, or time-frequency transformation are documented.
