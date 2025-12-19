# CR3BP / N-body 3D Simulator

## 1) Project overview

Celestial Choreography is a winter project under the Astronomy Club, IIT Kanpur focused on the Circular Restricted Three-Body Problem and its role in orbital motion and stability.
The repository contains deliverables for Lagrange point computation, Jacobi effective potential visualization, and trajectory simulation in rotating-frame CR3BP-style setups.
The codebase is organised around notebooks to keep experiments accessible and reusable.

## 2) Theory notes

The repository includes a theory section under the folder name `theory_notes/`.
The theory coverage follows the project sequence: basic astronomy context, two-body and n-body overview, two-body derivations from orbital mechanics, CR3BP derivation and Lagrange points, then numerical methods used for simulation.
The focus stays on core results, key observations, and enough derivation structure to connect equations to the plotted outputs.

## 3) Notebooks

The repository keeps notebooks as the main interface for the work, since the outputs are parameter-driven and visualization-heavy.
Each notebook keeps parameters, plots, and results together to support comparison across systems and runs.

Notebook set:
- `cr3bp_lagrange_points.ipynb` 
  Scope: numerical computation of L1 to L3 via a Newton solve along the x-axis, plus geometric construction of L4 and L5.
  Outputs: L-point coordinates for a chosen mass ratio, plus plane plots used for verification and comparisons across systems.

- `cr3bp_effective_potential.ipynb` 
  Scope: computation and plotting of the Jacobi effective potential on a grid, including stability-region structure and visual comparison across different mass ratios or physical mass pairs.
  Outputs: consistent multi-view plots per case, including equipotential contours, a colormap representation of height, and a 3D surface view.

- `cr3bp_nbody_simulator.ipynb` 
  Scope: numerical integration of trajectories under the CR3BP-style setup, including starts near L-points and additional initial condition experiments.
  Outputs: 3D trajectories and run configurations suitable for repeatable comparisons across initial conditions and solver settings.

## 4) How to run

### Step 1, set up an environment
- Install Python 3.x.
- Create a virtual environment.
- Install dependencies: 
  - `pip install numpy scipy matplotlib astropy` 
  - `pip install notebook jupyterlab` 

### Step 2, run notebooks
- Launch Jupyter: 
  - `jupyter lab` 
  - or `jupyter notebook`
- VScode may be used instead.
- Open a notebook and run cells in order.

## 5) Improvements

Improvements, fixes, and extensions are welcome.
Share your changes through a pull request or a short write-up with plots and parameter settings.

## 6) Layout, troubleshooting, license

### Layout
- `notebooks/`  
  Notebooks for interactive runs.
- `theory_notes/`  
  Project theory and handouts.

### Troubleshooting
- Large accelerations or unstable trajectories: increase softening, avoid extremely close approaches, adjust solver tolerances, reduce runtime.
- Slow runs: reduce grid resolution for potential plots, reduce output points for trajectories, shorten total integration time.
- Confusing results: re-check units and normalization, confirm `mu` selection, verify rotating-frame initial conditions.

### License
- MPL 2.0, see `LICENSE`.
