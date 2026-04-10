# ProgettoACC (Annaro-Casale-Chicco)
# Student performance prediction
**Progetto di Analisi predittiva e Machine Learning**

Questo progetto analizza un dataset relativo ai fattori che influenzano i risultati accademici degli studenti. L'obiettivo è costruire un modello in grado di prevedere l'**Exam Score** finale basandosi su variabili comportamentali, socio-economiche e scolastiche.

## Obiettivi del progetto
* Effettuare la pulizia e il preprocessing dei dati grezzi.
* Esplorare le relazioni tra variabili (ore di studio, coinvolgimento dei genitori, risorse, ecc.) e il successo accademico.
* Confrontare le performance di due modelli di regressione: **Linear Regression** e **Random Forest**.
* Valutare la robustezza dei modelli tramite tecniche di **Cross-Validation**.

## Il dataset
Il file `StudentPerformanceFactors.csv` contiene dati su:
- **Fattori Accademici:** Ore di studio, frequenza, sessioni di tutoring.
- **Fattori Socio-Economici:** Reddito familiare, livello di istruzione dei genitori, accesso alle risorse.
- **Fattori Comportamentali:** Ore di sonno, attività extra-curriculari, motivazione.

## Pipeline di lavoro

### 1. Preprocessing & cleaning
Il dataset è stato pulito e trasformato per essere digeribile dagli algoritmi:
- **Gestione missing values:** Imputazione dei valori nulli tramite la **mediana** (per le numeriche) e la **moda** (per le categoriche).
- **Ordinal Encoding:** Mappatura manuale per variabili con un ordine logico (es. *Low* → 0, *Medium* → 1, *High* → 2).
- **One-Hot Encoding:** Trasformazione delle variabili nominali (es. *Gender*, *School Type*) in valori numerici 0/1.
- **Boolean conversion:** Tutti i valori booleani sono stati convertiti in interi (0/1).

### 2. Modellazione
Sono stati implementati due approcci differenti:
- **Regressione Lineare:** Modello baseline per valutare relazioni lineari semplici.
- **Random Forest Regressor:** Modello ensemble basato su alberi di decisione per catturare relazioni non lineari più complesse.

### 3. Valutazione
La valutazione è stata effettuata utilizzando:
- **R² Score:** Per misurare la varianza spiegata dal modello.
- **MAE (Mean Absolute Error):** Per quantificare l'errore medio puro nelle previsioni del voto.
- **RMSE (Root Mean Squared Error):** Per quantificare la radice dell'MSE (l'errore quadratico medio) nelle previsioni del voto.
- **5-Fold Cross-Validation:** Per garantire che i risultati siano stabili e non dipendano dalla singola divisione dei dati.

## Risultati
I risultati mostrano come il modello **Random Forest** riesca a fornire previsioni più accurate rispetto alla regressione lineare, evidenziando l'importanza cruciale di fattori come l'attendance, le ore di studio e i punteggi precedenti.

## Struttura del repository
- `progettoacc.ipynb`: Jupyter Notebook con l'intero flusso di analisi e codice.
- `StudentPerformanceFactors.csv`: Dataset originale.
- `StudentPerformance_Cleaned.csv`: Dataset dopo la fase di preprocessing.
- `README.md`: Documentazione del progetto.

## Requisiti
Per eseguire il notebook è necessario avere installato:
- Python 3.x
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn

---
**Autori:** Eleonora Casale, Emma Chicco, Flavia Annaro
