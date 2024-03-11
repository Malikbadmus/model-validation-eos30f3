# Model-Validation-eos30f3

## :derelict_house: Structure

This repository is organised by folders:

- Data: Contains the raw data, processed data and Model predictions.
- Notebooks: Houses the jupyter notebook files where most of the developmen took place.
- Src: Contains important functions I will re-use throughout the repository, to avoid typing them each time.

## Model Abstract

This model leverages the ChemProp network (D-MPNN, see original Stokes et al, Cell, 2020 for more information) to build a predictor of hERG-mediated cardiotoxicity. The model has been trained using a dataset published by Cai et al, J Chem Inf Model, 2019, which contains 7889 molecules with several cut-offs for hERG blocking activity. The authors select a 10 uM cut-off. This implementation of the model does not use any specific featurizer, though the authors suggest the moe206 descriptors (closed-source) improve performance even further.

## Model Characteristics

- Model ID: Eos30f3
- Model Slug: dmpnn-herg
- Task: Classification
- Interpretation: Probability of blocking hERG (cut-off: 10uM)

## Installation Environment

Check [here](https://github.com/Malikbadmus/model-validation-eos30f3/blob/main/requirements.txt)

## Getting Started

1. Install Ersilia Model Hub
     - Follow this [step](https://ersilia.gitbook.io/ersilia-book/ersilia-model-hub/installation) to install the Hub.

2. Fetch the Model and Install it locally

   ```
   ersilia -v fetch eos30f3
   ```
3. Serve the Model

   ```
   ersilia -v serve eos30f3
   ```
4. Make predictions with the Processed Datasets [here](https://github.com/Malikbadmus/model-validation-eos30f3/blob/main/data/Processed/100_Molecules.csv)

   ```
   ersilia -v api run -i data/Processed/1000_Molecules.csv -o data/Model_predictions/eos30f3_output.csv
