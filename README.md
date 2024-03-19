# structure2property

This repository presents deep learning models designed to predict the electronic and phonon densities of states in crystals (eDOS and phDOS). These models use atomic pair distribution functions (PDF) and atom types (elements) as input data. In the first step, element embedding vectors are created by transforming elements into tokens. The second input, PDF vectors, is fed into bidirectional LSTM layers. The outputs from both branches are combined, and target predictions are generated through dense layers on the concatenation layer. The model's schematic illustration is provided below:

![Figure_2revised](https://github.com/dmamur/struct2prop/assets/129986239/cd7579e5-18b5-4e13-81c3-118456ab4449)

The main three notebooks are presented on the main page:
- create_input_data.ipynb: This file provides a step-by-step guide on generating input data from CIF files.

- embed_mat2spec.ipynb: This notebook performs edos predictions on the [Mat2Spec](https://github.com/gomes-lab/Mat2Spec) dataset (PDFs are calculated using the ASE library).
  
- embed_mat2spec_simpleRDF.ipynb: This notebook performs edos predictions on the [Mat2Spec](https://github.com/gomes-lab/Mat2Spec) dataset (PDFs are calculated manually).

## Perfomance
eDOS examples, taken from the test set of the Mat2Spec (black), and predicted spectra (colored). The examples are five representative materials chosen from each quartile from low Mean Absolute Error (MAE,top) to high MAE (bottom) of our model predictions. The chemical sum formula and ID number of each material are shown above each subplot

![embed_rdf_mat2spec_T0_E_128_H_4_L_4_results_edos_TestSet_Figure3](https://github.com/dmamur/struct2prop/assets/129986239/c0002b88-d49e-4107-953a-8470cc436215)







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

## Model Validation
We have performed further tests on our model using diverse datasets collected from various sources. Subsequent sections will describe each dataset in brief.
### STO-eDOS dataset
The eDOS spectra for SrTiO3 structures retrieved from the study titled ["Physically Informed Machine Learning Prediction of Electronic Density of States"](https://pubs.acs.org/doi/abs/10.1021/acs.chemmater.1c04252) were analyzed using our model. 
Training from the beginning, including downloading and preprocessing initial structures, can be initiated from [embed_sto.ipynb](https://github.com/dmamur/struct2prop/blob/main/add/embed_sto.ipynb).

The MAE achieved by our model is **0.070**.

The figure below shows examples of eDOS predictions for the test sets of SrTiO3 dataset. Both original spectra (in black) and model predictions (in color) are displayed for four representative materials selected from the four quintiles, ranging from low MAE (left) to high MAE (right). The ID number is provided above each plot.
![embed_rdfV2_edosSrTiO3_A1N_E_128_H_4_L_4_results_TestSetFull](https://github.com/dmamur/struct2prop/assets/129986239/e645c56d-3236-4203-a979-40072eb99546)
### Surface-eDOS dataset
The eDOS spectra for alloy surface structures available from the same work. Training from the scratch can be done from [embed_surface.ipynb](https://github.com/dmamur/struct2prop/blob/main/add/embed_surface.ipynb). 

The MAE achieved by our model is **0.0094**. 

The figure below illustrates prediction results similar to the previous figure.
![embed_rdfV2_edosBulk_A1N_E_128_H_4_L_4_results_TestSetFull](https://github.com/dmamur/struct2prop/assets/129986239/91bf044d-932d-43a7-a465-e63a538ed047)
### E3NN-phDOS dataset
Phonon densities of states predictions for the [E3NN](https://github.com/zhantaochen/phonondos_e3nn) dataset. The training can be performed with [embed_e3nn_phdos.ipynb](https://github.com/dmamur/struct2prop/blob/main/add/embed_e3nn_phdos.ipynb). 

The MAE achieved by our model is **0.083**. 

The figure below illustrates prediction results similar to the previous figures.
![embed_phdos_rdf_T5_E_128_H_4_L_4_e3nn_results_testSetV2](https://github.com/dmamur/struct2prop/assets/129986239/9adbad45-c6ce-479d-a085-6c257b50f54e)
