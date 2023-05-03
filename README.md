# Deep Learning Analysis

## Overview 
The purpose of our analysis is to see if we can design a model that will help us accurately predict whether money AlphabetSoup gives to a venture will be successful, depending on a list of criteria we have from already funded projects with known outcomes.

## Results
* The targets for our model is IS_SUCCESSFUL from the dataset, which is a binary dataset that indicates either success or failure as determined by metrics not available to us.
* The features are Affiliation, Government Classifiction, Use Case, Organization Type, Status (currently active or not), Income Amount, Special Considerations for the application (y/n), and the amount the organization was requesting from AlphabetSoup.
* I dropped the name and EIN from the data, as specific identifiers were not going to improve the quality or accuracy of the model at all.

### Evaluating the Model
