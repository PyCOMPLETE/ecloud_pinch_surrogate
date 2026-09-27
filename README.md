# ecloud_pinch_surrogate

Electron-cloud pinch example copied from PyECLOUD's
`testing/tests_PyEC4PyHT/011_test_multigrid_pinch_record_grid.py`.
The script and its local inputs are included unchanged, along with PyECLOUD's
Apache-2.0 license. No PyECLOUD source checkout is needed to run it.

## Installation

Use Python 3.11 or newer with working C and Fortran compilers. For example,
activate a conda environment containing `c-compiler` and `fortran-compiler`
from conda-forge, then run:

```sh
python -m pip install -r requirements.txt
```

This installs PyECLOUD, its `pypic-poisson` dependency, and the PyHEADTAIL
integration. PyECLOUD and PyPIC compile their native extensions during installation.

## Run

From this directory, with an interactive Matplotlib backend available:

```sh
python 011_test_multigrid_pinch_record_grid.py
```

Use `python -i 011_test_multigrid_pinch_record_grid.py` to inspect the arrays
interactively after closing the figure. The simulation retains electron density,
potential, and electric field on the finest grid, and plots electron number
density in the x=0, y=0, and z=0 planes. It does not save simulation output files.

The example uses 301 slices, 3 million beam macroparticles, approximately
1 million initial electron macroparticles, a sinusoidally distorted bunch, and
a finest grid spacing of `0.05 * sigma_x`.

Included local inputs:

- `machines_for_testing.py`: the LHC machine helper.
- `LHC_chm_ver.mat`: chamber geometry.
- `pyecloud_config_LHC/`: simulation, machine, and secondary-emission settings.

The configuration mentions `beam.beam`, but it is not used here: PyHEADTAIL
provides the bunch and Ecloud initializes PyECLOUD with `skip_beam=True`.
