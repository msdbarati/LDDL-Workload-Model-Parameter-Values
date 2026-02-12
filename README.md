# LDDL Workload Model Parameter Values

This repository provides parameter values for modeling **Large Data Center Deep Learning (LDDL)** workloads in power system dynamic simulations (e.g., IEEE 68-bus test system). These parameters represent realistic AI/ML data center load behaviors connected at specific buses, useful for studying grid impacts such as load fluctuations, subsynchronous resonance, torsional dynamics, and interactions with synchronous generators.

The data is extracted from the provided PDF document and reformatted here for easy reference.

## PDF Document

Full formatted tables and details (including original layout):  
**[System_Configuration_and_LDDL_Workload_Model_Parameter_Values.pdf](./System_Configuration_and_LDDL_Workload_Model_Parameter_Values.pdf)**  
(Click to view directly in browser or download)

## Key Tables

### Table 1: IEEE 68-Bus System Configuration and Simulation Parameters

| Parameter                          | Value          | Unit    |
|------------------------------------|----------------|---------|
| System base power                  | 100            | MVA     |
| System base frequency              | 60             | Hz      |
| Total generation capacity          | 184.08         | pu      |
| Total load demand                  | 184.08         | pu      |
| Transmission line reactance        | 0.50           | pu      |
| Compensation level                 | 50             | %       |
| Capacitor reactance                | 0.25           | pu      |
| Electrical resonance frequency     | 42.43          | Hz      |
| Subsynchronous frequency           | 17.57          | Hz      |
| Simulation duration                | 5.0            | s       |
| Integration time step              | 0.1            | ms      |
| Integration method                 | RK45 adaptive  | —       |
| Relative tolerance                 | 10<sup>-6</sup>| —       |
| Absolute tolerance                 | 10<sup>-9</sup>| —       |

### Table 2: Multi-Mass Shaft Model Parameters for Torsional Dynamics

| Mass Section              | Inertia H (s) | Shaft Stiffness K (pu) | Damping D (pu) |
|---------------------------|---------------|------------------------|----------------|
| High Pressure (HP)        | 0.0929        | —                      | 0.0            |
| HP-IP coupling            | —             | 19.303                 | —              |
| Intermediate Pressure (IP)| 0.1556        | —                      | 0.0            |
| IP-LPA coupling           | —             | 34.929                 | —              |
| Low Pressure A (LPA)      | 0.8587        | —                      | 0.0            |
| LPA-LPB coupling          | —             | 52.038                 | —              |
| Low Pressure B (LPB)      | 0.8842        | —                      | 0.0            |
| LPB-GEN coupling          | —             | 70.858                 | —              |
| Generator (GEN)           | 0.8685        | —                      | 0.5            |
| GEN-EXC coupling          | —             | 2.822                  | —              |
| Exciter (EXC)             | 0.0342        | —                      | 0.0            |

**Total system inertia:** H<sub>total</sub> = 2.894 s

### Table 3: Workload Model Parameters for LDDL Facilities

| Parameter                      | LDDL1 (Bus 9) AI Inference | LDDL2 (Bus 36) ML Training | LDDL3 (Bus 37) Batch Jobs |
|--------------------------------|----------------------------|----------------------------|---------------------------|
| Rated capacity (MW)            | 57.5                       | 51.7                       | 46.0                      |
| Number of racks N              | 500                        | 450                        | 400                       |
| Servers per rack M             | 40                         | 40                         | 40                        |
| Idle power P<sub>idle</sub> (kW/server) | 0.15                  | 0.15                       | 0.15                      |
| Peak power P<sub>peak</sub> (kW/server) | 0.50                  | 0.50                       | 0.50                      |
| Poisson arrival rate η (jobs/s)| 12.0                       | —                          | —                         |
| Job duration γ (s)             | 0.08                       | —                          | —                         |
| Job duration spread γ<sub>1</sub> (s) | 0.02                | —                          | —                         |
| Training epoch period (s)      | —                          | 1.5                        | —                         |
| Epoch amplitude (LF variation) | —                          | 0.15                       | —                         |
| Batch step interval (s)        | —                          | —                          | 0.8                       |
| Batch step size (LF change)    | —                          | —                          | 0.10                      |
| Cooling ratio α<sub>1</sub>    | 0.15                       | 0.15                       | 0.15                      |
| Cooling response rate α<sub>2</sub> | 0.05                  | 0.05                       | 0.05                      |
| Power supply time const τ<sub>s</sub> (s) | 0.01             | 0.01                       | 0.01                      |
| Mean load factor (pu)          | 0.775                      | 0.829                      | 0.840                     |
| Std. dev. load factor (pu)     | 0.107                      | 0.103                      | 0.090                     |


## Citation

If you use these parameters in your research, please cite this repository:

@misc{barati2026lddl,
author = {Masoud Barati},
title = {LDDL Workload Model Parameter Values},
year = {2026},
publisher = {GitHub},
journal = {GitHub repository},
howpublished = {\url{https://github.com/msdbarati/LDDL-Workload-Model-Parameter-Values}}
}
