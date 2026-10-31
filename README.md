# Mini-Project 2: Dispatching New York's Grid Under a Carbon Price

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This is the repository for Mini-Project 2 for [BEE 4750](https://envsys.viveks.me/), taught at [Cornell University](https://cornell.edu) in Fall 2026 by [Vivek Srikrishnan](https://viveks.me).

If enrolled in the class, a PDF of your report should be submitted to Gradescope *no later* than the due date at 9:00pm. Submitting up to 24 hours late will result in a 50% penalty. Students in BEE 4750 may work in groups of 2; students in BEE 5750 work individually.

## Learning Objectives

After completing this mini-project, students will be able to:

- formulate a multi-period dispatch problem with hourly availability, ramping limits and an annual energy budget, and solve it in `JuMP`;
- find hourly electricity prices from the demand constraint's shadow price, and say which plant type sets them;
- interpret the shadow price of an annual hydro budget as the value of water;
- find by hand the carbon taxes at which plant types change places in the merit order, and check them against the model;
- extend the dispatch model to decide what to build, and compare an emissions cap with a carbon tax set at the cap's shadow price;
- explain how falling technology costs change what a carbon price does.

## Repository Overview

The repository consists of the following files:

- `mp02.ipynb`: Jupyter Notebook for the mini-project, including the code that loads the system data. This is the only file you should need to edit.
- `mp02.pdf`: PDF version of the mini-project for students who don't want to rely on the Jupyter Notebook.
- `data/`: the system data. `2013_hourly_load_NY.csv` is NYISO's hourly load for 2013 by zone, `wind_solar_capacity_factors.csv` the hourly wind and solar profiles, `nyca_2013_fleet.csv` the existing fleet, and `new_capacity_costs.csv` the annualized costs of new capacity for Part 5.
- `Project.toml`, `Manifest.toml`: Julia environment files. These should just work, but feel free to add other packages as needed using the `Pkg` package manager. This is the only other file that you might typically end up making changes to, though you should do this using `Pkg`, not directly.
- `mp02.qmd`: Source file for Jupyter notebook generation. You shouldn't need to or want to touch this unless you use Quarto to write your report; everything is in the `.ipynb` file.
- `LICENSE`: This material is licensed using the MIT license. You can ignore this for working on the project.
- `README.md`: This file. You shouldn't need to touch this.
- `.gitignore`: This tells `git` what files to ignore. You shouldn't need to touch this.

## Dependencies

This notebook was written using Julia 1.11.5, and depends on the following packages:
- `JuMP.jl` and `HiGHS.jl` (the optimization model and its solver)
- `CSV.jl` and `DataFrames.jl` (reading the data)
- `Statistics` (part of Julia)
- `Plots.jl` and `Measures.jl`
- `IJulia.jl` (runs the notebook; no cell loads it, but keep it in the environment)

## Prerequisites

1. [Install Julia](https://julialang.org/downloads/) before beginning this assignment. This notebook was developed with version 1.11.5, but any 1.11.x should work (there could be some issues with other versions, depending on what's changed; if that occurs, delete `Manifest.toml` before re-evaluating the first notebook cell).
2. If necessary, [install git](https://happygitwithr.com/install-git.html) and [create a GitHub account](https://github.com).
