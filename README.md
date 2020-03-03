# Molecular Gym Environment

Minimal port of the [MolDQN approach of Zhou et al.](http://www.nature.com/articles/s41598-019-47148-x) from Tensorflow with a custom environment description to Keras with OpenAI Gym environment specifications.

This port is currently missing the bootstrapped version of the DQN used by Zhou et al.

**DISCLAIMER**: The main logic for this package is copied from [Google's implementation of DQN](https://github.com/google-research/google-research/blob/master/mol_dqn/chemgraph/dqn/molecules.py). 
Files directly taken from Google's repository are marked with the original Google copyright and license headers in the files.

## Installation

The necessary packages for running this package are listed in `electrolyte_env.yml`.
Install them with Conda:

```bash
conda env create --file electrolyte_env.yml
```

## Training the RL Agent

The `run_electrolyte.py` script trains the RL agent and has a few command line options for expeirmenting with the training process.
Run `python run_electrolyte.py --help` to see the command line options.

Running the script with default settings (i.e., `python run_electrolyte.py`) should take less than 10 minutes.

Each run of this agent will produce a subdirectory of `./rl_tests/` that contains the configuration used for the experiment
and a log containing records at each step:

- `episode`: Episode number
- `step`: Step number within that episode
- `epsilon`: Degree of randomness used in selecting next step
- `smiles`: State of th emolecule after choosing an action in this step
- `reward`: Observed reward value for choosing that action
- `loss`: Training loss for the Q network at each step
