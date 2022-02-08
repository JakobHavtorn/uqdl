# uqdl

Uncertainty Quantification in Deep Learning.

## Description

This repository has all code in the `uqdl.ipynb` notebook and outlines some different approaches for using neural
networks to model both uncertainty inherent to the data (aleatory uncertainty) and uncertainty stemming from inadequate
modelling (epistemic uncertainty).

Aleatory uncertainty modelling is in some aspects a solved problem whereas the problem of converting epistemic uncertainty into aleatory uncertainty is largely unsolved, as can also be seen from the results of the models presented here:

## Models from the notebook

Here we simulate a certain data generating function

![Data generating function](https://github.com/JakobHavtorn/uqdl/blob/master/plots/data-generating-function.png)

and train a number of different models to predict it along with its aleatory uncertainty and potentialyl the epistemic uncertainty arising in regions of little or no training data.

Below is a short discussion followed by plots from the notebook.

### Discussion and results
All models are able to decently capture the aleatory uncertainty in the data with varying degrees of accuracy, but none of the modelling approaches accurately capture the epistemic uncertainty. The model that gets the closest to useful epistemic uncertainty modelling is the Monte Carlo Dropout based pseudo-ensemble of Distributional Parameter Learning neural networks. However, the models are generally overly confident on out-of-distribution data often exhibiting a high bias but not always an appropriately high variance. 

Another very important observation is the fact that the accuracy on out-of-distribution data for all of these models is extremely dependent on the curvature of the training data at the limits of the training domain and on initial conditions. If the trainnig data exhibits a tendency that continues into the testing-domain, this can sometimes be captured fairly well, although not always. The strength of neural networks lies in interpolation. This is behaviour makes the usefulness of these models in estimating epistemic uncertainty very limited at this time.

### Monte Carlo Dropout Model
![Evaluation of the MCD Model](https://github.com/JakobHavtorn/uqdl/blob/master/plots/MCDModel-evaluation.png)
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
