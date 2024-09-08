# Mycobacterium_Tuberculosis-Descriptor-Dataset-Preparation

## Project Overview:
This repository contains the code and resources for preparing a descriptor dataset for Mycobacterium tuberculosis bioactivity data using molecular descriptors. The dataset preparation involves generating molecular descriptors using PaDEL software, cleaning the data, and creating a final dataset containing both molecular descriptors and bioactivity values.

## Steps Involved:
### Download the required resources:
- The script first downloads the necessary files, including the PaDEL software and a shell script for running PaDEL in a Linux environment.
- The code uses wget to download padel.zip and padel.sh from GitHub repositories.
- 
### Unzip the PaDEL software:
- The PaDEL software is unzipped to extract the necessary files.
  
### Prepare the input data:
- The dataset containing bioactivity data for Mycobacterium tuberculosis is read from the CSV file mycobacterium_tuberculosis_bioactivity_data_3class_pIC50.csv.
- The columns canonical_smiles and molecule_chembl_id are selected from the dataset to prepare a file (molecule.smi) containing the molecular structure data in SMILES format.

### Run PaDEL to compute molecular descriptors:
- The PaDEL software is executed using a shell script (padel.sh) to compute molecular descriptors for the SMILES data. The output is saved in descriptors_output.csv.

### Prepare the final dataset:
- The descriptor data from descriptors_output.csv is read and cleaned (dropping the Name column).
- The bioactivity values (pIC50) are extracted from the original dataset.
- The molecular descriptors and bioactivity values are concatenated to form the final dataset (mycobacterium_tuberculosis_bioactivity_data_3class_pIC50_pubchem_fp.csv).

## Applications:
- This descriptor dataset can be used in cheminformatics and drug discovery for building machine learning models to predict bioactivity.
- It can serve as a foundation for QSAR (Quantitative Structure-Activity Relationship) studies focusing on Mycobacterium tuberculosis bioactivity.
