# ecloud_pinch_surrogate

## Setup

Here is how to set up a conda environment to run the example:

```sh
conda create -n ecloud-pinch -c conda-forge python=3.13 pip
conda activate ecloud-pinch
conda install -c conda-forge c-compiler cxx-compiler fortran-compiler
conda install -c conda-forge numpy scipy matplotlib
pip install --upgrade pyheadtail
pip install --upgrade pyecloud
```

## Run

From the repository directory:

```sh
# (edit the script to change settings)
python 000_example_pinch_record.py
```
