# About
This is code for Gradient-Based Language Model Red Teaming from [this paper](https://openreview.net/pdf?id=SL3ZqaKwkE)

# Setup
Use python3.10
Modify requirements.txt to install the correct version of JAX and TF depending on your hardware. See https://github.com/google/jax#installation for details.
Install from requirements.txt as described in https://pip.pypa.io/en/stable/cli/pip_freeze/#examples

At this point you should be able to run the code by following the steps in the Running section, but the output will be meaningless since the model is randomly initialized.

Train a PAX LM by following the instructions [here](https://github.com/google/paxml/tree/main#example-convergence-runs). The model should be trained to predict a response after the 'SEP' token, and predict the safety score after the 'SAFETY' token.
Change the exp.checkpoint_dir in the config to the checkpoint directory of this model. Also change the self._vocabulary in experirment.py to the vocab your model uses.

# Running
To train locally: `python3.10 experiment.py --config=configs/model_diff_loss_config.py`

You can view the training curves in tensorboard.