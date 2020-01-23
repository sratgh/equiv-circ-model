# Equivalent circuit model

This repository contains Python code for running an equivalent circuit model (ECM) developed for a 2013 Nissan Leaf battery cell. Model parameters are determined from hybrid pulse power characterization (HPPC) tests conducted at ORNL. The battery cell and its specifications were provided by NREL.

## Installation

The [Anaconda][] or [Miniconda][] distribution of Python 3.7 is recommended for this project. After setting up Python, the following packages are required: Matplotlib, NumPy, Pandas, and SciPy.

## Usage

The main entry point for the program is `__main__.py` which is located in the `ecm` package. As an example, to run the ECM for a single battery cell and compare the results to HPPC data:

```bash
# Run this command from within the `equiv-circ-model` directory
$ python ecm --runhppc
```

Use the optional `--help` command to view the available arguments:

```bash
$ python ecm --help

usage: ecm [-h] [-vd] [-vh] [-rf] [-rc] [-rs] [-rh]

optional arguments:
  -h, --help            show this help message and exit
  -vd, --viewdischarge  view discharge data
  -vh, --viewhppc       view HPPC data
  -rf, --runfit         run curve fit of HPPC data
  -rc, --runrctau       run RC parameters for HPPC data
  -rs, --runsococv      run RC parameters for HPPC data
  -rh, --runhppc        run cell ECM and compare to HPPC data
```

A requirements file is provided for running the ECM in a virtual environment using pip.

```bash
# Create a new virtual environment
python -m venv env

# Activate the environment
source env/bin/activate

# Install packages needed for the ECM
pip install -r requirements.txt

# Deactivate the environment
deactivate

# Remove the environment by deleting the `env` folder
```

An environment yaml file is also provided for running the ECM in a conda environment.

```bash
# Create a new conda environment and install packages needed for the ECM
conda env create -f environment.yml

# Activate the environment
conda activate ecm

# Deactivate the environment
conda deactivate

# Remove the environment and its installed packages
conda env remove -n ecm
```

## Project structure

**data** - This folder contains the experiment data for developing the ECM.

**ecm** - Python package containing components of the ECM.

**ecm/params.py** - Parameters that define the battery cell along with other variables needed to run the model.

## Contributing

Comments, suggestions, and other feedback can be submitted on the [Issues](https://github.com/batterysim/equiv-circ-model/issues) page.

## License

This code is available under the MIT License - see the [LICENSE](LICENSE) file for more information.

[anaconda]: https://www.anaconda.com
[miniconda]: https://conda.io/miniconda.html
