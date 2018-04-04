# SLC Hackathon logo
Scripts and notebooks needed to reproduce the SLC hackathon logo.

Sketch to terrain implementation was done by Eric Guerin. See the complete guide and links to the article [here](https://perso.liris.cnrs.fr/eguerin/deep-terrains-code-and-data/).

## Setup the Python Environment:

- `conda env create -f environment.yml`

## Predict from sketch:

- Download Eric Guerin's trained model from [here](https://liris.cnrs.fr/eric.guerin/download/multi_train.tgz). Uncompress it with `tar -xvzf /path/to/multi_train.tgz`. You will have a directory called `multi_train`.


- Place your own sketches on any subdirectory. **Note:** You need as input an image of size `512x256 px`. The script doesn't actually have a prediction module but you can use the `Test` mode to make predictions. Easiest thing to do is to repeat the sketch two times horizontally to generate the `2*256x256 px` images.


- `source activate SLC`


- From the root directory in this repo, run:
  - `python pix2pix-tensorflow-png16bits-support/pix2pix.py --png16bits --mode test --output_dir multi_test --input_dir PATH_TO_SKETCHES --checkpoint multi_train`