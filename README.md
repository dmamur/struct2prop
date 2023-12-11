# structure2property
This repository presents deep learning models designed to predict the electronic and phonon densities of states in crystals. These models use atomic pair distribution functions (PDF) and atom types (elements) as input data. In the first step, element embedding vectors are created by transforming elements into tokens. The second input, PDF vectors, is fed into bidirectional LSTM layers. The outputs from both branches are combined, and target predictions are generated through dense layers on the concatenation layer. The model's schematic illustration is provided below:
![image](https://github.com/dmamur/struct2prop/assets/129986239/61fdb6df-58f4-4c09-a0ef-829f6e6b10e9)


