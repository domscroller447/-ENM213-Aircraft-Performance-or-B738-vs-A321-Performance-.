# ENM213 Aircraft Performance Project — Group 5

## Project Overview
This repository contains a comprehensive aircraft performance and flight mechanics analysis comparing the **Boeing 737-800 (B738)** and the **Airbus A321 (A321)**. The computational models evaluate aerodynamic properties, thrust capabilities, and mission performance parameters for an intercontinental route between Nairobi (NBO) and Mumbai (BOM).

## Route & Aircraft Specifications

| Parameter | Specification |
| :--- | :--- |
| **Aircraft 1** | Boeing 737-800 (B738) |
| **Aircraft 2** | Airbus A321 (A321) |
| **Origin** | Nairobi JKIA (NBO) |
| **Destination** | Mumbai (BOM) |
| **Route Distance** | ~2,900 nm |
| **Course Unit** | ENM213 |
| **Group Number** | Group 5 |
| **Authors** | Michael Muchemi (ENM213-0158/2024) & Allan Kiprop (ENM213-0154/2024) |

## Technical Implementation
The performance analysis is executed in Python within a Jupyter Notebook. The core aerodynamic and engine modeling relies on the **OpenAP** (Open-source Aircraft Performance) library.

Key computational components include:
* **`openap.prop`**: Extraction of specific airframe dimensions, maximum takeoff weights (MTOW), and engine specifications.
* **`openap.Thrust` & `openap.Drag`**: Calculation of maximum available thrust and aerodynamic drag forces at varying flight levels.
* **`matplotlib.pyplot`**: Visualization of the flight envelope, specific range, and performance degradation curves.
* **`numpy`**: Matrix operations and numerical integration for flight trajectory arrays.

## Key Performance Metrics Analyzed
* **Takeoff & Climb Performance**: Evaluation of required runway length and time-to-climb.
* **Cruise Efficiency**: Assessment of specific fuel consumption (SFC) and optimal cruise altitudes.
* **Payload-Range Limitations**: Analysis of weight trade-offs to complete the 2,900 nm flight without exceeding maximum zero-fuel weight (MZFW) or MTOW.

## How to View and Run the Code
1. View the static results directly on GitHub by opening `Group_5_project.ipynb`. All performance graphs and data tables are embedded within the file.
2. To run the calculations locally:
   * Clone the repository to your local machine.
   * Ensure a Python 3.x environment is active.
   * Install the required dependencies: `pip install openap numpy matplotlib`
   * Open the notebook using Jupyter or Visual Studio Code and execute all cells sequentially.
     ## Comparative Conclusions & Key Findings

### 1. Aerodynamic Performance Comparison
| Aerodynamic Parameter | Boeing 737-800 | Airbus A321 | Engineering Insight |
| :--- | :---: | :---: | :--- |
| **Zero-Lift Drag ($C_{D,0}$)** | **0.0190** | 0.0200 | B738 features cleaner parasite drag geometry. |
| **Induced Drag Factor ($K$)** | 0.0420 | **0.0410** | A321 exhibits slightly better induced wing span loading. |
| **Max Efficiency ($(L/D)_{\text{max}}$)** | **17.7** | 17.5 | B738 achieves a higher overall aerodynamic efficiency peak. |
| **Optimum $C_L$ Point** | 0.675 | **0.699** | A321 operates more efficiently under higher payload targets. |

### 2. Analytical vs. Computational Verification
* **Model Precision:** Hand-derived equations matched OpenAP automated model outputs with less than **0.1% variance** in cruise drag ($39,881\text{ N}$ vs $39,910\text{ N}$), validating the underlying ISA flight physics before conducting full-route trajectory sweeps.
