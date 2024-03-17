# Model-Validation-eos30f3

## :derelict_house: Structure

This repository is organised by folders:

- Data: Contains the raw data, processed data and Model predictions.
- Figures: Contains a collection of visualizations presented in PNG format..
- Notebooks: Houses the jupyter notebook files where most of the developmen took place.
- Src: Contains important functions I will re-use throughout the repository, to avoid typing them each time.

## Model Abstract

This model leverages the ChemProp network (D-MPNN, see original Stokes et al, Cell, 2020 for more information) to build a predictor of hERG-mediated cardiotoxicity. The model has been trained using a dataset published by Cai et al, J Chem Inf Model, 2019, which contains 7889 molecules with several cut-offs for hERG blocking activity. The authors select a 10 uM cut-off. This implementation of the model does not use any specific featurizer, though the authors suggest the moe206 descriptors (closed-source) improve performance even further.

## Model Characteristics

- Input: `Compound`
- Input Shape: `Single`
- Task: `Classification`
- Output: `Score`
- Output Type: `Float`
- Output Shape: `Single`
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

## Data Availability

- ChEMBL: A Manually curated database of bioactive molecules with drug-like properties. It brings together chemical, bioactivity and genomic data to aid the translation of genomic information into effective new drugs.



## Data Procurement Process

1. ChEMBL Data Procurement:

   - A Datasets of `3592` Small Molecules Compounds that has been aproved for Use was Downloaded in a CSV format, and stored in /data/Raw.

2. DMPNN-hERG Datasets Procurement:

   - The Model was trained on `7889` compounds with well-defined experimental data on the hERG and with diverse chemical structures assembled by Cai et al in their work published in J Chem Inf Model, 2019 [here](https://pubmed.ncbi.nlm.nih.gov/30715873/), it provides target variables with various cutoffs for hERG blocking activity. 


## References

     - [DPMN-hERG GitHub page](https://github.com/AI-amateur/DMPNN-hERG)
     - [Publication](https://pubs.rsc.org/en/content/articlehtml/2022/ra/d1ra07956e#imgfig2)
     - [eos30f3 GitHub page](https://github.com/ersilia-os/eos30f3)

## License

All the code in this repository is licensed under a GPLv3 License.
