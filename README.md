# EnergetiQ

**Exploring the computational steps between a molecular description and a variational quantum energy estimate.**

EnergetiQ contains two quantum-chemistry notebooks motivated by molecular simulation and battery-material research. They expose fermionic Hamiltonians, qubit mappings and variational optimization in code, providing a starting point for investigating what a materials calculation would require.

## Notebook guide

| Notebook | Focus |
|---|---|
| [nyuad2.ipynb](nyuad2.ipynb) | PySCF molecular integrals, construction of an electronic operator, Jordan–Wigner mapping and a VQE helper |
| [molecules_qiskit (1).ipynb](molecules_qiskit%20%281%29.ipynb) | Manually specified molecular Hamiltonian examples, parameterized ansätze, SPSA optimization and animated illustrations |

The smaller notebook defines a Li₂S geometry, which motivates the battery-material direction. Its supplied example call evaluates helium; defining a candidate geometry does not establish a completed Li₂S calculation or a battery-performance result.

## Computational workflow

1. Specify a molecular geometry or an illustrative fermionic Hamiltonian.
2. Map the fermionic operator to qubits with the Jordan–Wigner transformation.
3. Build a parameterized `TwoLocal` circuit.
4. Optimize an estimated energy with VQE and SPSA.
5. Inspect the resulting energy and the notebook's visualizations.

## Open the notebooks

Use Jupyter Notebook or JupyterLab in an isolated Python environment. Dependencies used by the cells include NumPy, Matplotlib, Qiskit, Qiskit Nature, Qiskit Aer, Qiskit Algorithms and, for `nyuad2.ipynb`, PySCF. Pillow supports GIF export.

```bash
python -m pip install jupyterlab
python -m jupyter lab
```

Open the chosen notebook, inspect its installation/import cells and use a compatible Qiskit environment. The notebooks use legacy primitives and do not include a pinned environment, so installing the newest SDK versions is not a guaranteed reproduction path.

## How to interpret the study

These are exploratory notebooks. Manually simplified Hamiltonians require independent chemistry validation, and randomly sampled electron-cloud illustrations are not computed molecular orbital densities. A validated materials study would additionally need consistent orbital conventions, electron-number treatment, energy offsets, classical reference calculations and an appropriate active space.

The repository does not report battery voltage, capacity, cycle life or a demonstrated quantum advantage.

## Project provenance

This repository is a fork of [epelaaez/EnergetiQ](https://github.com/epelaaez/EnergetiQ). Preserve upstream and collaborator attribution when reusing the notebooks. No standalone license file is currently included here; consult the upstream project before redistributing its content.
