# uqdl

Uncertainty Quantification in Deep Learning.

## Description

This repository has all code in the `uqdl.ipynb` notebook and outlines some different approaches for using neural
networks to model both uncertainty inherent to the data (aleatory uncertainty) and uncertainty stemming from inadequate
modelling (epistemic uncertainty).

Aleatory uncertainty modelling is in some aspects a solved problem whereas the problem of converting epistemic uncertainty into aleatory uncertainty is largely unsolved.

## Models from the notebook

Here we simulate a certain data generating function

![Data generating function](https://github.com/JakobHavtorn/uqdl/blob/master/plots/data-generating-function.png)

and train a number of different models to predict it along with its aleatory uncertainty and potentialyl the epistemic uncertainty arising in regions of little or no training data.

### Monte Carlo Dropout Model
![Evaluation of the MCD Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/DPLModel-evaluation.png)
### Distributional Parameter Learning Model
![Evaluation of the DPL Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/DPLModel-evaluation.png)
### Ensemble of DPL Models
![Evaluation of the Ensemble DPL Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/EnsembleDPLModel-evaluation-ensemble.png)
![Evaluation of the Ensemble DPL Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/EnsembleDPLModel-evaluation-func.png)
### Ensemble of DPL Models via Monte Carlo Dropout
![Evaluation of the MCDDPL Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/MCDDPLModel-evaluation.png)

See the notebook for more details and implementation.

## Installation

Make a python 3.7.4 environment and install the requirements:

`pip install -r requirements.txt`
