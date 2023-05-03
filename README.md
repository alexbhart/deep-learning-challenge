# Deep Learning Analysis

## Overview 
The purpose of our analysis is to see if we can design a model that will help us accurately predict whether money AlphabetSoup gives to a venture will be successful, depending on a list of criteria we have from already funded projects with known outcomes.

## Results
* The targets for our model is IS_SUCCESSFUL from the dataset, which is a binary dataset that indicates either success or failure as determined by metrics not available to us.
* The features are Affiliation, Government Classifiction, Use Case, Organization Type, Status (currently active or not), Income Amount, Special Considerations for the application (y/n), and the amount the organization was requesting from AlphabetSoup.
* I dropped the name and EIN from the data, as specific identifiers were not going to improve the quality or accuracy of the model at all.
* Also in preprocessing, reduced the number of unique values in the categorical features by use of binning smaller value counts into a generic "Other" as they didn't have enough values to be useful to any model.

### Evaluating the Model

 * Our initial, self assessed model was ineffective at hitting the target of 75% accuracy with the following hyperparameters:
    * Activation: ReLU
    * Number of Hidden Layers: 3
    * Neurons in First Layer: 80
    * Neurons in Second Layer: 30
    * Third is Output with Sigmoid Activation
    ![First Models Hyperparameters](Images\first_model_shape.png)
    ![First Models Evaluation](Images\first_eval.png)

 * Our step to try and improve the performance of the model was to import keras-tuner and run the function of testing many different layer and neuron combinations. It was not in the best interest of the model to reduce the features set any further, as the categorical features had already been binned. 

 * After running keras-tuner, it was determined that the best model had the following parameters:
    * 'activation': 'relu', 'first_units': 45, 'num_layers': 4, 'units_0': 55, 'units_1': 60, 'units_2': 20, 'units_3': 25, 'units_4': 30
    * Activation: ReLU
    * Number of Hidden Layers: 4
    * Neurons in First Layer: 45
    * Neurons in Second Layer: 55
    * Neurons in Third Layer: 60
    * Fourth Layer Would Be Output Layer, with Sigmoid Activation
    ![Best Models Hyperparameters](Images\best3_ss.png)

 * Even after running the tuner, we were unable to get to the target accuarcy.
    ![Best Models Evaluation](Images\bestmodels_evaluate_ss.png)

 * I think the model we chose is well suited to this task, but I don't think we have enough categorical features to get a better accuracy. Also, the variability of long-term economic decisions make accuracy above certain thresholds difficult and unrealistic. 73% isn't far off our target, and is reasonable for the intended purpose.