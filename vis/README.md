# Esercizio Visualizzazione:

Il grafico è stato simulato in Python all'interno dello script visualization_exercise_ornstein_uhlenbeck.ipynb presente nella cartella, ed è stata tratta ispirazione da un codice di simulazione di un processo di Ornstein-Uhlenbeck per modelli finanziari disponibile pubblicamente sulla piattaforma Github al link:

https://github.com/cantaro86/Financial-Models-Numerical-Methods/blob/master/6.1%20Ornstein-Uhlenbeck%20process%20and%20applications.ipynb

I due grafici in questione rappresentano la simulazione di un processo di Ornstein-Uhlenbeck **$X_t$**, un processo stocastico regolato dall'equazione differenziale stocastica:

**$dX_t=\kappa (\theta - X_t) dt +\sigma dW_t$**

Nelle equazioni differenziali stocastiche la soluzione è composta dalla somma di una componente deterministica integrata sul tempo **dt** e di una componente stocastica integrata sul moto Browniano **$dW_t$**. Rispettivamente i parametri dell'equazione sono:

- **$\kappa>0$** coefficiente di mean reversion;
- **$\theta$** coefficiente di drift;
- **$\sigma$** coefficiente di volatilità; 

Il processo è Gaussiano, Markoviano e stazionario per tempi sufficientemente lunghi, e rappresenta un decadimento esponenziale deterministico a cui viene aggiunto un white noise. L'equazione differenziale stocastica si può risolvere esattamente mediante la formula di Ito, e si ottiene il seguente risultato per il processo **$X_t$**:

**$X_t = \theta + (X_0 - \theta)e^{-\kappa t} + \int_0^t \sigma e^{\kappa (s-t)}dW_s$**

Il processo di Ornstein-Uhlenbeck ha i seguenti momenti:

- Media **$E[X_t] = \theta + (X_0 - \theta)e^{-\kappa t}$**
- Varianza **$Var[X_t] = \frac{\sigma^2}{2\kappa}(1-e^{-2 \kappa t})$**

Asintoticamente, nel limite per **$t \rightarrow \infty$** la media tende al valore **$\theta$** e la varianza tende al valore **$\frac{\sigma^2}{2\kappa}$**. Nella simulazione si utilizza il metodo di discretizzazione di Eulero-Maruyama per calcolare a step temporali finiti il processo stocastico, seguendo la relazione:

**$X_{n+1}=\theta + (X_n-\theta)e^{-\kappa \Delta t} + \sqrt{\frac{\sigma^2}{2\kappa}(1-e^{-2 \kappa \Delta t})}\epsilon_n$**

Dove fissato **$X_0$** condizione iniziale, decido l'ampiezza dello step temporale **$\Delta t$**, decido il numero di step e calcolo **$\epsilon_n \sim \mathcal{N}(0,1)$** distribuzione Gaussiana con media nulla e varianza unitaria. 

In questi due plot simulo alcuni processi di Ornstein-Uhlenbeck aventi condizione iniziale **$X_0=2$**, parametri **$\theta=0.5$**, **$\kappa=3$** e **$\sigma=0.5$**. Per gioco, ho provato a creare un badplot e un goodplot apportando al primo alcune modifiche:


## Bad Plot:
 
![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/vis/badplot.png)


## Good Plot:

![image](https://github.com/AlbertoBassanoni/MLPNS_ABassanoni/blob/main/vis/goodplot.png)
