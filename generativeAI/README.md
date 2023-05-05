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


![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_low_res_35x35_seq.png)

High resolution:


![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_70x70_sequential.png)


Il Sequential Dense Network è composto da un Multilayer Perceptron avente seguente struttura:

ENCODER:
- Input Layer
- 256 Neurons Dense Layer
- 128 Neurons Dense Layer

BOTTLE NECK:
- 128 Neurons Dense Layer

DECODER:
- 128 Neurons Dense Layer
- 258 Neurons Dense Layer
- Output Layer

Questo tipo di neural network come si può vedere dal plotting della loss function è soggetto ad un problema di overfitting, per via della significativa differenza della loss function sul training set e sul validation set (o test set) dei dati. E' stata utilizzata nel running delle epochs su cui avviene il learning della rete una funzione di callback, avente come threshold del learning process un valore della loss pari a **$10^{-4}$**. 

![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/loss_sequential_NN.png)

Ricordiamo che questa tipologia di autoencoders è soggetta ad un problema importante: il posterior collapse. L'autoencoder impara come riprodurre il valor medio dei dati, e ciò dunque significa che questo tipo di encoder è fortemente sensibile a come è composto e bilanciato il training set. In questo caso, la mia immagine non è stata migliorata in maniera soddisfacente in quanto l'autoencoder non riconosce sufficiente similiarità della mia immagine con la media delle immagini che ha imparato nel training set, ed essendo il nostro training set abbastanza biased verso una tipologia specifica di immagini (studenti maschi bianchi, con volto perfettamente centrato), questo tipo di neural network non è quello ottimale!

## Convolutional Neural Network:

Low resolution:


![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_low_res_32x32_conv.png)

High resolution:


![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/generativeAI/imm_64x64_convolutional.png)

