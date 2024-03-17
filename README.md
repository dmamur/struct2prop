# structure2property

This repository presents deep learning models designed to predict the electronic and phonon densities of states in crystals (eDOS and phDOS). These models use atomic pair distribution functions (PDF) and atom types (elements) as input data. In the first step, element embedding vectors are created by transforming elements into tokens. The second input, PDF vectors, is fed into bidirectional LSTM layers. The outputs from both branches are combined, and target predictions are generated through dense layers on the concatenation layer. The model's schematic illustration is provided below:

![Figure_2revised](https://github.com/dmamur/struct2prop/assets/129986239/cd7579e5-18b5-4e13-81c3-118456ab4449)

The main three notebooks are presented on the main page:
- create_input_data.ipynb: This file provides a step-by-step guide on generating input data from CIF files.

- embed_mat2spec.ipynb: This notebook performs edos predictions on the [Mat2Spec](https://github.com/gomes-lab/Mat2Spec) dataset (PDFs are calculated using the ASE library).
  
- embed_mat2spec_simpleRDF.ipynb: This notebook performs edos predictions on the [Mat2Spec](https://github.com/gomes-lab/Mat2Spec) dataset (PDFs are calculated manually).

- embed_phdos_colab.ipynb:  This notebook performs phDOS predictions on e3nn [dataset](https://github.com/zhantaochen/phonondos_e3nn).  

## Perfomance
eDOS examples, taken from the test set of the Mat2Spec (black), and predicted spectra (colored). The examples are five representative materials chosen from each quartile from low MAE (top) to high MAE (bottom) of our model predictions. The chemical sum formula and ID number of each material are shown above each subplot

![image](https://github.com/dmamur/struct2prop/assets/129986239/40df60a8-5981-4274-9010-5ba1b101b896)






Further information concerning the development of model and extended dataset from the Materials Porject can be found in our [publication]([https://arxiv.org/abs/2309.09355](https://chemrxiv.org/engage/chemrxiv/article-details/6564ef0c29a13c4d47208248)):
```
 @article{shermukhamedov_mamurjonova_maihom_probst_2023,
      place={Cambridge},
      title={Structure to Property: Machine Learning Methods for Predicting Electronic Properties of Crystals},
      DOI={10.26434/chemrxiv-2023-gq77g},
      journal={ChemRxiv},
      publisher={Cambridge Open Engage},
      author={Shermukhamedov, Shokirbek and Mamurjonova, Dilorom and Maihom, Thana and Probst, Michael},
      year={2023}}.
```
