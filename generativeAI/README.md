# Generative AI Faces:

Riportiamo qui sotto il confronto delle immagini prodotte dal generative autoencoder della mia foto profilo rispettivamente nel caso di un sequential dense neural
network e nel caso di un convolutional neural network.

L'immagine target da cui si parte (a colori) è la seguente:

![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_original.png)

Questa immagine viene abbassata di risoluzione, costruendo rispettivamente nel caso:

- Sequential Dense Neural Network: immagine a low resolution di 35x35 pixels;
- Convolutional Neural Network: immagine a low resolution di 32x32 pixels;

Rispettivamente il nostro autoencoder cercherà di costruire a partire da questi input data il seguente output data:

- Sequential Dense Neural Network: immagine a high resolution di 70x70 pixels;
- Convolutional Neural Network: immagine a high resolution di 64x64 pixels;

Tutte le immagini a low e high resolution sono riportate in bianco e nero. Qui sotto i risultati:

## Sequential Dense Neural Network:

Low resolution:
![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_35x35_seq.png)

High resolution:
![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_70x70_sequential.png)

## Convolutional Neural Network:

Low resolution:
![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_32x32_conv.png)

High resolution:
![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_64x64_convolutional.png)

