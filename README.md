##  MixedSolverBench Benchmark

MixedSolverBench is an open-source MATLAB benchmark for fist-order convex optimization solvers. MixedSolverBench implements the alternating direction method of multipliers (ADMM) and the Proximal-gradient Descent (PGD) under different floating-point and fixed-point machine representations. 

**Current version:** 1.0.1

**Release notes:** 

* The current version only implements PGD and ADMM for the LASSO problem.

* Other first-order solvers and other problems will be added in future releases. 

## Contents
* [Description](#Description)
* [Quick start](#QuickStart)
* [How to cite](#References)
* [Contact us](#Contacts)
* [Licence](#Licence)


## Description<a name="Description"></a>

MixedSolverBench Benchmark implements PG and ADMM to solve the LASSO problem

<img src="https://latex.codecogs.com/svg.latex?\Large&space;(1)\quad\quad\text{minimize}\quad\quad\frac{1}{2}\|Ax-b\|_2^2+\|x\|_p" title="\Large \text{minimize}\quad\quad\frac{1}{2}\|Ax-b\|_2^2 + \|x\|_p" />

where p = 1 or 0.

MixedSolverBench Benchmark offers a choice to solve problem (1) using different custom data types and compares the output of each to the default double precision floating-point representation.

## Requirement<a name="Requirement"></a>

* CVX
* Fixed-point Designer

## Quick start<a name="QuickStart"></a>

Type
 	`>> pg_benchmark`

OR
	`>> admm_benchmark`
	
with custom problem data (modify the data) or use the default randomly generated problem data to compare the LASSO function values under different machine representations. The default benchmark implements PG and ADMM under 'double precision', 'single precision', '12 bits fixed-point' and  '16 bits fixed-point' representations. 

To add custom data types add a case statement with custom data type name. To invoke a specific type within another function use  
	`>> T = mytypes('data type')`

then use casting as follows:
	`>> x = cast(x0, 'like', T.x)`

To optimize the data type for a specific application run 'pg_solv_mex'. Note that an html static version and a Matlab data export file version of the instrumentation report are generated by default which can be found in the 'instrumentation' folder. The report is updated with new data after each benchmarking run.
	
for a complete list of solver options.
	
**NOTE:** _this is a research code, and is under active development. You may find 
some undocumented inputs and options that are being used for development 
purposes, in the hope that they will become part of the "official" release. If 
you have any suggestions for improvement, or find any bugs, feel free to [contact us](#Contacts)!_


## How to cite<a name="References"></a>

If you find RPFOSolver Benchmark useful, please cite the following paper as appropriate:

```
@inproceedings{hamadouche2021approximate,
  title={Approximate Proximal-Gradient Methods},
  author={Hamadouche, Anis and Wu, Yun and Wallace, Andrew M and Mota, Jo{\~a}o FC},
  booktitle={2021 Sensor Signal Processing for Defence Conference (SSPD)},
  pages={1--6},
  year={2021},
  organization={IEEE}
}
	
```

## Contact us<a name="Contacts"></a>
To contact us about RPFOSolver Benchmark, suggest improvements and report bugs, email either [Anis Hamadouche] (mailto:ah225@hw.ac.uk?Subject=RPFOSolverBenchmark) or [Yun Wu] (mailto:y.wu@hw.ac.uk?Subject=RPFOSolverBenchmark).


## Licence<a name="Licence"></a>

RPFOSolver Benchmark is free software; you can redistribute it and/or modify it under the terms 
of the [GNU Lesser General Public Licence (LGPL)](https://www.gnu.org/licenses/lgpl-3.0.en.html) as published by the Free Software
Foundation; either version 3 of the Licence, or (at your option) any later version.

RPFOSolver Benchmark is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY;
without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
PURPOSE. [See the GNU General Public License for more details](https://www.gnu.org/licenses/gpl-3.0.en.html).

You should have received a copy of the GNU Lesser General Public License along 
with RPFOSolver Benchmark; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA.
