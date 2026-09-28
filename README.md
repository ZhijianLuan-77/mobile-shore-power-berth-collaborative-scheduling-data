# Mobile Shore Power–Berth Collaborative Scheduling Data

This repository provides the test instances and instance-level computational results used in the paper on collaborative berth allocation and Mobile Shore Power Outlet (MSPO) scheduling.

## Repository Structure

The repository contains two main folders:

- **Instances/**: input data for all computational experiments.
- **Results/**: instance-level computational results corresponding to the experiments reported in the paper.

Both folders are further divided into three types of instances.

## Instance Sets

### Regular Instances

These instances are used for the main algorithmic experiments and sensitivity analyses.

The following 12 groups are included:

10-4, 10-8, 20-10, 20-15, 30-15, 30-17, 40-20, 40-30, 50-27, 50-30, 60-30, and 60-40.

The first number denotes the number of vessels and the second denotes the number of berths. Each group contains five instances.

### MSPO-Congestion Instances

These instances are designed to create stronger competition for shared MSPO resources and are used to evaluate algorithmic performance and MSPO scheduling decisions.

The following four groups are included:

10-5, 20-10, 30-15, and 40-20.

Each group contains five instances.

### Berth-Congestion Instances

These instances are designed to create stronger berth-side congestion and are used to evaluate algorithmic performance under limited berth availability.

The following four groups are included:

15-5, 30-10, 51-17, and 60-20.

Each group contains five instances.

## Instance File Naming

Each instance is represented by four CSV files:

- `ship_X-Y-Z.csv`: vessel-related data.
- `berth_X-Y-Z.csv`: berth-related data.
- `mobile_X-Y-Z.csv`: MSPO-related data.
- `task_X-Y-Z.csv`: vessel–berth task and compatibility data.

Here:

- `X` denotes the number of vessels;
- `Y` denotes the number of berths;
- `Z` denotes the instance index.

For example, `ship_40-20-3.csv` contains the vessel data for the third instance with 40 vessels and 20 berths.

## Computational Results

The `Results/Regular Instances/` folder contains the instance-level results for the main computational experiments, including:

- Fast TLBBD;
- Exact TLBBD;
- Gurobi;
- S-LBBD;
- TLBBD with BSP-MILP;
- ALNS and GVNS;
- FCFS, OPS-Priority, and Berth-First OPS-Second practical scheduling rules;
- sensitivity analyses on OPS coverage, fixed-to-mobile OPS ratio, carbon tax, shore-power subsidy, carbon-emission cap, and MSPO power capacity.

The `Results/MSPO-Congestion Instances/` folder contains the results for:

- Fast TLBBD, Exact TLBBD, Gurobi, ALNS, and GVNS;
- BSP-MILP-based experiments;
- simultaneous MSPO and berth release;
- individual MSPO assignment and sequencing;
- explicit MSPO relocation time.

The `Results/Berth-Congestion Instances/` folder contains the results for Fast TLBBD, Exact TLBBD, Gurobi, ALNS, and GVNS.

## Main Result Fields

Depending on the experiment, the result files report some or all of the following indicators:

- **Obj. / Total Cost**: objective value or generalized operating cost.
- **Gap (%)**: reported optimality or internal search gap, according to the corresponding algorithm.
- **CPU / Runtime (s)**: computational time in seconds.
- **Average Waiting Time**: average vessel waiting time.
- **Average Excess Waiting Time**: average waiting time beyond the prescribed threshold.
- **CO₂**: total carbon emissions.
- **MSPO Utilization**: utilization level of mobile shore power resources.
- **Service Share**: proportion of vessels served by the corresponding OPS resource.
- **Cmax**: makespan of the resulting schedule.

The interpretation of algorithm-specific gap and optimality measures follows the definitions provided in the paper.
