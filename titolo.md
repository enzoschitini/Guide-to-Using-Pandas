# 🐼 Guide to Using Pandas Methods and Functions
This guide provides a practical overview of the main Pandas methods and functions for data analysis. From DataFrame management to cleaning and transformation, you will find useful examples to manipulate and analyze data in Python efficiently.

By [Enzo Schitini]('https://www.linkedin.com/in/enzoschitini/')

Data Scientist & Data Analyst • SQL • Expert Bubble.io • UX & UI @ Scituffy creator

Pandas è una delle librerie più potenti e ampiamente utilizzate per la manipolazione e l'analisi dei dati in Python. Che tu sia un aspirante data scientist, un analista esperto o semplicemente qualcuno che lavora con i dati, padroneggiare Pandas può migliorare notevolmente la tua produttività e le capacità di elaborazione dei dati. Questa guida ha l'obiettivo di fornire una panoramica completa dei metodi e delle funzioni essenziali di Pandas, permettendoti di affrontare operazioni complesse sui dati con facilità ed efficienza.

In questa guida esplorerai concetti fondamentali, come la pulizia dei dati, la trasformazione, l'aggregazione e le tecniche di visualizzazione utilizzando Pandas. Attraverso esempi pratici e istruzioni passo-passo, acquisirai una comprensione più profonda di come sfruttare al massimo il potenziale di Pandas per semplificare e potenziare i tuoi flussi di lavoro con i dati. Iniziamo!
### `Useremo:` ddddddddddddddddd
| order_id                            | customer_state | product_category_name | product_weight_g | review_score | price | freight_value | payment_value | order_approved_at     | order_purchase_timestamp |
|-------------------------------------|----------------|-----------------------|------------------|--------------|-------|---------------|---------------|-----------------------|-------------------------|
| 00010242fe8c5a6d1ba2dd792cb16214    | RJ             | cool_stuff            | 650.0            | 5            | 58.9  | 13.29         | 72.19         | 2017-09-13 09:45:35   | 2017-09-13 08:59:02     |
| 130898c0987d1801452a8ed92a670612    | GO             | cool_stuff            | 650.0            | 5            | 55.9  | 17.96         | 73.86         | 2017-06-29 02:44:11   | 2017-06-28 11:52:20     |
| 532ed5e14e24ae1f0d735b91524b98b9    | MG             | cool_stuff            | 650.0            | 4            | 64.9  | 18.33         | 83.23         | 2018-05-18 12:31:43   | 2018-05-18 10:25:53     |
| 6f8c31653edb8c83e1a739408b5ff750    | PR             | cool_stuff            | 650.0            | 5            | 58.9  | 16.17         | 75.07         | 2017-08-01 18:55:08   | 2017-08-01 18:38:42     |
| 7d19f4ef4d04461989632411b7e588b9    | MG             | cool_stuff            | 650.0            | 5            | 58.9  | 13.29         | 72.19         | 2017-08-10 22:05:11   | 2017-08-10 21:48:40     |
``` python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/enzoschitini/Guide-to-Using-Pandas/refs/heads/main/pandas_csv_guide.csv').drop(columns='Unnamed: 0')

```

[Link Data](https://github.com/enzoschitini/Guide-to-Using-Pandas/blob/main/pandas_csv_guide.csv)
### 1. **Caricamento dei Dati**

- `pd.read_csv()` – Carica dati da un file CSV.
- `pd.read_excel()` – Carica dati da un file Excel.
- `pd.read_sql()` – Carica dati da un database SQL.
- `pd.read_json()` – Carica dati da un file JSON.
- `pd.read_parquet()` – Carica dati da un file Parquet, utile per grandi dataset.
- `pd.read_html()` – Analizza le tabelle HTML da una pagina web.
- `pd.read_pickle()` – Carica dati salvati in formato pickle di Python.
- `pd.read_feather()` – Carica dati da un file in formato Feather, utile per input/output veloci.
- `pd.read_sas()` – Carica dati da file SAS.
- `pd.read_hdf()` – Carica dati da file in formato HDF5.

### 2. **Ispezione dei Dati**

- `.head(n)` – Mostra le prime `n` righe del DataFrame (valore predefinito: 5).
- `.tail(n)` – Mostra le ultime `n` righe del DataFrame.
- `.shape` – Restituisce le dimensioni (righe, colonne) del DataFrame.
- `.columns` – Elenca i nomi delle colonne.
- `.info()` – Mostra informazioni sul DataFrame (tipi di colonne, conteggio dei valori non nulli).
- `.describe()` – Fornisce statistiche descrittive per le colonne numeriche.
- `.dtypes` – Restituisce i tipi di dati di tutte le colonne.
- `.index` – Restituisce l'indice (etichette delle righe) del DataFrame.
- `.value_counts()` – Conta le occorrenze di valori unici in una colonna.
- `.isnull()` / `.notnull()` – Verifica la presenza di valori mancanti.
- `.duplicated()` – Controlla le righe duplicate.
- `.nunique()` – Conta il numero di valori unici per colonna.
- `.sample(n)` – Estrae `n` righe casuali dal DataFrame.

### 3. **Selezione e Indicizzazione dei Dati**

- `.loc[]` – Accede a gruppi di righe e colonne per etichette.
- `.iloc[]` – Accede a gruppi di righe e colonne per posizione (basato su numeri interi).
- `.at[]` – Accede a un singolo valore per una coppia di etichette riga/colonna.
- `.iat[]` – Accede a un singolo valore per una coppia di posizione riga/colonna.
- `.filter()` – Sottoselezione del DataFrame basata su etichette di righe/colonne.
- `.xs()` – Ottieni sezioni trasversali da un MultiIndex.
- `.query()` – Filtra il DataFrame con un'espressione stringa.
- `.get()` – Recupera elementi da una Serie per chiave.
- `.isin()` – Filtra righe in base al fatto che i valori siano in una lista.
- `.where()` – Imposta valori in base a una condizione.
- `.mask()` – Sostituisce i valori dove una condizione è `True`.
- `.squeeze()` – Converte un DataFrame con una sola colonna in una Serie.

### 4. **Pulizia dei Dati**

- `.drop()` – Rimuove etichette specifiche da righe o colonne.
- `.dropna()` – Rimuove righe/colonne con valori mancanti.
- `.fillna()` – Sostituisce i valori mancanti con un valore specificato.
- `.replace()` – Sostituisce valori nel DataFrame.
- `.rename()` – Rinomina colonne o indici.
- `.interpolate()` – Sostituisce valori NaN con valori interpolati.
- `.bfill()` / `.ffill()` – Riempimento all'indietro o in avanti dei valori NaN.
- `.convert_dtypes()` – Converte le colonne nei migliori tipi di dati possibili.
- `.clip()` – Limita i valori al di sotto o al di sopra di una soglia.
- `.abs()` – Calcola il valore assoluto delle colonne numeriche.
- `.round(decimals)` – Arrotonda i valori a un determinato numero di decimali.

### 5. **Trasformazione dei Dati**

- `.astype()` – Cambia il tipo di dati delle colonne.
- `.apply()` – Applica una funzione lungo un asse (righe/colonne).
- `.applymap()` – Applica una funzione elemento per elemento.
- `.map()` – Associa valori da una colonna a un'altra.
- `.sort_values()` – Ordina il DataFrame in base alle colonne.
- `.sort_index()` – Ordina il DataFrame in base all'indice.
- `.reset_index()` – Reimposta l'indice del DataFrame.
- `.pivot()` – Ristruttura i dati in base ai valori delle colonne.
- `.rank()` – Classifica i valori in ogni colonna.
- `.cumsum()` / `.cumprod()` – Calcola somma/prodotto cumulativi.
- `.diff()` – Calcola la differenza tra righe successive.
- `.expanding()` – Applica trasformazioni espansive (es. somma cumulativa).
- `.pipe()` – Utilizza funzioni personalizzate sul DataFrame.
- `.eval()` – Valuta un'espressione Python come colonna del DataFrame.

### 6. **Aggregazione e Raggruppamento**

- `.groupby()` – Raggruppa il DataFrame in base a una o più colonne.
- `.agg()` – Applica funzioni di aggregazione come somma, media, minimo, massimo sui dati raggruppati.
- `.sum()`, `.mean()`, `.min()`, `.max()`, `.count()` – Calcola direttamente queste statistiche.
- `.pivot_table()` – Crea una tabella pivot con righe, colonne e valori specificati.
- `.transform()` – Applica funzioni a colonne raggruppate da `groupby()`.
- `.size()` – Ottieni la dimensione di ogni gruppo.
- `.cumcount()` – Conta le occorrenze cumulative di valori unici.
- `.nsmallest(n, columns)` – Trova i `n` valori più piccoli in una colonna.
- `.nlargest(n, columns)` – Trova i `n` valori più grandi in una colonna.
- `.mad()` – Deviazione assoluta media per i dati raggruppati.
- `.rolling(window).apply()` – Applica una funzione su una finestra mobile.

### 7. **Unione e Merging dei Dati**

- `pd.merge()` – Unisce DataFrame su colonne specificate.
- `.join()` – Unisce DataFrame sugli indici.
- `pd.concat()` – Concatena DataFrame lungo righe o colonne.
- `.merge_as

### 8. **Esplorazione dei Dati Temporali**

- `.resample()` – Raggruppa e riassume i dati basati su una frequenza temporale.
- `.to_datetime()` – Converte le stringhe in oggetti datetime.
- `.dt` accessor – Accede a componenti delle date come anno, mese, giorno.
- `.rolling()` – Applica operazioni su finestre mobili temporali.
- `.shift()` – Sposta i dati nel tempo (es., spostamento di periodi).
- `.diff()` – Calcola la differenza di valori successivi in serie temporali.
- `.asfreq()` – Modifica la frequenza di un indice di serie temporali.
- `.tshift()` (obsoleto) – Sposta i dati lungo l'asse temporale.
- `.between_time()` – Estrae righe in base a un intervallo di tempo specifico.
- `.at_time()` – Estrae righe per un orario specifico.
- `.truncate()` – Trancia le righe prima o dopo una data specificata.

### 9. **Esportazione dei Dati**

- `.to_csv()` – Esporta i dati in un file CSV.
- `.to_excel()` – Esporta i dati in un file Excel.
- `.to_sql()` – Esporta i dati in un database SQL.
- `.to_json()` – Esporta i dati in formato JSON.
- `.to_parquet()` – Esporta i dati in formato Parquet.
- `.to_pickle()` – Esporta i dati in un file pickle di Python.
- `.to_html()` – Esporta i dati in una tabella HTML.
- `.to_latex()` – Esporta i dati in formato LaTeX.
- `.to_dict()` – Converte i dati in un dizionario Python.
- `.to_markdown()` – Esporta i dati in formato Markdown.
- `.to_clipboard()` – Copia i dati negli appunti per incollare altrove.
- `.to_string()` – Converte il DataFrame in una stringa.
- `.to_records()` – Converte il DataFrame in un array di record.
- `.to_feather()` – Esporta i dati in formato Feather.

### 10. **Gestione degli Indici Multi-level (MultiIndex)**

- `.set_index()` – Imposta una o più colonne come indice del DataFrame.
- `.reset_index()` – Reimposta l'indice di un DataFrame, riportando l'indice corrente come colonne.
- `.sort_index()` – Ordina un DataFrame in base ai valori dell'indice.
- `.swaplevel()` – Scambia i livelli di un MultiIndex.
- `.stack()` – Comprime i livelli di colonne in righe.
- `.unstack()` – Espande i livelli di righe in colonne.
- `.reorder_levels()` – Riordina i livelli di un MultiIndex.
- `.index.get_level_values()` – Estrae i valori di un livello specifico da un MultiIndex.
- `.droplevel()` – Rimuove un livello da un MultiIndex.
- `.groupby(level=...)` – Raggruppa i dati in base ai livelli di un MultiIndex.
























# 🐼 Guide to Using Pandas Methods and Functions
This guide provides a practical overview of the main Pandas methods and functions for data analysis. From DataFrame management to cleaning and transformation, you will find useful examples to manipulate and analyze data in Python efficiently.

By [Enzo Schitini]('https://www.linkedin.com/in/enzoschitini/')

Data Scientist & Data Analyst • SQL • Expert Bubble.io • UX & UI @ Scituffy creator

Pandas is one of the most powerful and widely used libraries for manipulating and analyzing data in Python. Whether you are an aspiring data scientist, an experienced analyst, or simply someone who works with data, mastering Pandas can greatly improve your productivity and data processing skills. This guide aims to provide a comprehensive overview of Pandas' essential methods and functions, enabling you to tackle complex data operations with ease and efficiency.

In this guide, you will explore fundamental concepts such as data cleansing, transformation, aggregation, and visualization techniques using Pandas. Through practical examples and step-by-step instructions, you will gain a deeper understanding of how to leverage Pandas' full potential to simplify and enhance your data workflows.





### `Dataset:` For this guide, we will use data from an online store, although with fewer rows and columns than the original. We have 2022 rows and 10 columns.
Link Dataset: https://github.com/enzoschitini/Guide-to-Using-Pandas/blob/main/pandas_csv_guide.csv






| order_id                            | customer_state | product_category_name | product_weight_g | review_score | price | freight_value | payment_value | order_approved_at     | order_purchase_timestamp |
|-------------------------------------|----------------|-----------------------|------------------|--------------|-------|---------------|---------------|-----------------------|-------------------------|
| 00010242fe8c5a6d1ba2dd792cb16214    | RJ             | cool_stuff            | 650.0            | 5            | 58.9  | 13.29         | 72.19         | 2017-09-13 09:45:35   | 2017-09-13 08:59:02     |
| 130898c0987d1801452a8ed92a670612    | GO             | cool_stuff            | 650.0            | 5            | 55.9  | 17.96         | 73.86         | 2017-06-29 02:44:11   | 2017-06-28 11:52:20     |
| 532ed5e14e24ae1f0d735b91524b98b9    | MG             | cool_stuff            | 650.0            | 4            | 64.9  | 18.33         | 83.23         | 2018-05-18 12:31:43   | 2018-05-18 10:25:53     |
| 6f8c31653edb8c83e1a739408b5ff750    | PR             | cool_stuff            | 650.0            | 5            | 58.9  | 16.17         | 75.07         | 2017-08-01 18:55:08   | 2017-08-01 18:38:42     |
| 7d19f4ef4d04461989632411b7e588b9    | MG             | cool_stuff            | 650.0            | 5            | 58.9  | 13.29         | 72.19         | 2017-08-10 22:05:11   | 2017-08-10 21:48:40     |






### Description of columns:

- **order_id**: Unique identifier for the order. Each row represents a specific order made by the customer.

- **customer_state**: Brazilian state where the customer resides. It is represented by a two-letter code (e.g., RJ for Rio de Janeiro).

- **product_category_name**: Category of the purchased product. For example, "cool_stuff" indicates a specific product category.

- **product_weight_g**: Weight of the product in grams. This provides information about the weight of the ordered product.

- **review_score**: Review score given by the customer for the order, typically on a scale from 1 to 5.

- **price**: Price of the product in the local currency (Brazilian reais). This indicates the cost of the purchased product.

- **freight_value**: Shipping cost in the local currency. This represents the shipping charge for the order.

- **payment_value**: Total amount paid for the order, including the product price and the shipping cost.

- **order_approved_at**: Date and time when the order was approved for shipping.

- **order_purchase_timestamp**: Date and time when the order was placed by the customer.





``` python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/enzoschitini/Guide-to-Using-Pandas/refs/heads/main/pandas_csv_guide.csv').drop(columns='Unnamed: 0')

```





## Argomenti da trattare in questa guida:  
Ho scelto i 10 argomenti che, secondo me, sono più utilizzati in Pandas per analizzare i dati.  

### 1. **Caricamento dei Dati**  

- `pd.read_csv()` – Carica dati da un file CSV.  
- `pd.read_excel()` – Carica dati da un file Excel.  
- `pd.read_sql()` – Carica dati da un database SQL.  
- `pd.read_json()` – Carica dati da un file JSON.  
- `pd.read_parquet()` – Carica dati da un file Parquet, utile per dataset di grandi dimensioni.  
- `pd.read_html()` – Analizza tabelle HTML da una pagina web.  
- `pd.read_pickle()` – Carica dati salvati in formato pickle di Python.  
- `pd.read_feather()` – Carica dati da un file in formato Feather, adatto per input/output veloci.  
- `pd.read_sas()` – Carica dati da file SAS.  
- `pd.read_hdf()` – Carica dati da file in formato HDF5.  

### 2. **Ispezione dei Dati**  

- `.head(n)` – Mostra le prime `n` righe del DataFrame (predefinito: 5).  
- `.tail(n)` – Mostra le ultime `n` righe del DataFrame.  
- `.shape` – Restituisce le dimensioni (righe, colonne) del DataFrame.  
- `.columns` – Elenca i nomi delle colonne.  
- `.info()` – Mostra informazioni sul DataFrame (tipi di colonna, conteggi non nulli).  
- `.describe()` – Fornisce statistiche descrittive per le colonne numeriche.  
- `.dtypes` – Restituisce i tipi di dati di tutte le colonne.  
- `.index` – Restituisce l'indice (etichette delle righe) del DataFrame.  
- `.value_counts()` – Conta i valori univoci in una colonna.  
- `.isnull()` / `.notnull()` – Controlla i valori mancanti.  
- `.duplicated()` – Controlla righe duplicate.  
- `.nunique()` – Conta il numero di valori univoci per colonna.  
- `.sample(n)` – Seleziona casualmente `n` righe dal DataFrame.  

### 3. **Selezione e Indicizzazione dei Dati**  

- `.loc[]` – Accede a gruppi di righe e colonne tramite etichette.  
- `.iloc[]` – Accede a gruppi di righe e colonne tramite posizioni (basate su interi).  
- `.at[]` – Accede a un singolo valore tramite una coppia etichetta riga/colonna.  
- `.iat[]` – Accede a un singolo valore tramite una coppia posizione riga/colonna.  
- `.filter()` – Sottoseleziona il DataFrame in base alle etichette di riga/colonna.  
- `.xs()` – Estrae sezioni trasversali da un MultiIndex.  
- `.query()` – Filtra il DataFrame usando un'espressione in formato stringa.  
- `.get()` – Recupera elementi da una Serie tramite chiave.  
- `.isin()` – Filtra righe in base alla presenza di valori in una lista.  
- `.where()` – Imposta valori in base a una condizione.  
- `.mask()` – Sostituisce valori dove una condizione è `True`.  
- `.squeeze()` – Converte un DataFrame con una sola colonna in una Serie.  

### 4. **Pulizia dei Dati**  

- `.drop()` – Rimuove etichette specificate da righe o colonne.  
- `.dropna()` – Elimina righe/colonne con valori mancanti.  
- `.fillna()` – Sostituisce i valori mancanti con un valore specificato.  
- `.replace()` – Sostituisce valori all'interno del DataFrame.  
- `.rename()` – Rinomina colonne o indici.  
- `.interpolate()` – Riempie valori NaN con valori interpolati.  
- `.bfill()` / `.ffill()` – Riempimento a ritroso o in avanti di valori NaN.  
- `.convert_dtypes()` – Converte colonne nei tipi di dati ottimali.  
- `.clip()` – Limita i valori al di sotto o al di sopra di una soglia.  
- `.abs()` – Calcola il valore assoluto delle colonne numeriche.  
- `.round(decimals)` – Arrotonda i valori a un numero specificato di decimali.  

### 5. **Trasformazione dei Dati**  

- `.astype()` – Cambia il tipo di dato delle colonne.  
- `.apply()` – Applica una funzione lungo un asse (righe/colonne).  
- `.applymap()` – Applica una funzione elemento per elemento.  
- `.map()` – Mappa valori da una colonna a un'altra.  
- `.sort_values()` – Ordina il DataFrame per colonne.  
- `.sort_index()` – Ordina il DataFrame per il suo indice.  
- `.reset_index()` – Reimposta l'indice del DataFrame.  
- `.pivot()` – Rimodella i dati in base ai valori delle colonne.  
- `.rank()` – Classifica i valori all'interno di ciascuna colonna.  
- `.cumsum()` / `.cumprod()` – Calcola somme/prodotti cumulativi.  
- `.diff()` – Calcola la differenza tra righe successive.  
- `.expanding()` – Applica trasformazioni progressive (es. somma cumulativa).  
- `.pipe()` – Applica funzioni personalizzate al DataFrame.  
- `.eval()` – Valuta un'espressione Python come colonna nel DataFrame.  

### 6. **Aggregazione e Raggruppamento**  

- `.groupby()` – Raggruppa il DataFrame in base a una o più colonne.  
- `.agg()` – Applica funzioni di aggregazione come somma, media, min, max sui dati raggruppati.  
- `.sum()`, `.mean()`, `.min()`, `.max()`, `.count()` – Calcola direttamente queste statistiche.  
- `.pivot_table()` – Crea una tabella pivot con righe, colonne e valori specificati.  
- `.transform()` – Applica funzioni a colonne raggruppate usando `groupby()`.  
- `.size()` – Restituisce la dimensione di ogni gruppo.  
- `.cumcount()` – Conta le occorrenze cumulative di valori univoci.  
- `.nsmallest(n, columns)` – Trova i `n` valori più piccoli in una colonna.  
- `.nlargest(n, columns)` – Trova i `n` valori più grandi in una colonna.  
- `.mad()` – Deviazione assoluta media per dati raggruppati.  
- `.rolling(window).apply()` – Applica una funzione su una finestra mobile.  

### 7. **Unione e Combinazione dei Dati**  

- `pd.merge()` – Unisce DataFrame su colonne specificate.  
- `.join()` – Unisce DataFrame sugli indici.  
- `pd.concat()` – Concatena DataFrame lungo righe o colonne.  

### 8. **Esplorazione dei Dati Temporali**  

- `.resample()` – Raggruppa e riassume i dati in base a una frequenza temporale.  
- `.to_datetime()` – Converte stringhe in oggetti datetime.  
- `.dt` accessor – Accede a componenti di data come anno, mese, giorno.  
- `.rolling()` – Applica operazioni su una finestra temporale mobile.  
- `.shift()` – Sposta i dati nel tempo (es. periodi).  
- `.diff()` – Calcola la differenza di valori successivi in una serie temporale.  
- `.asfreq()` – Cambia la frequenza di un indice temporale.  
- `.between_time()` – Estrae righe in base a un intervallo di tempo specifico.  
- `.at_time()` – Estrae righe per un'ora specifica.  
- `.truncate()` – Riduce righe prima o dopo una data specifica.  

### 9. **Esportazione dei Dati**  

- `.to_csv()` – Esporta i dati in un file CSV.  
- `.to_excel()` – Esporta i dati in un file Excel.  
- `.to_sql()` – Esporta i dati in un database SQL.  
- `.to_json()` – Esporta i dati in formato JSON.  
- `.to_parquet()` – Esporta i dati in formato Parquet.  
- `.to_pickle()` – Esporta i dati in un file pickle di Python.  
- `.to_html()` – Esporta i dati in una tabella HTML.  
- `.to_latex()` – Esporta i dati in formato LaTeX.  
- `.to_dict()` – Converte i dati in un dizionario Python.  
- `.to_markdown()` – Esporta i dati in formato Markdown.  
- `.to_clipboard()` – Copia i dati negli appunti.  
- `.to_string()` – Converte il DataFrame in una stringa.  
- `.to_records()` – Converte il DataFrame in un array di record.  
- `.to_feather()` – Esporta i dati in formato Feather.  

### 10. **Gestione degli Indici Multi-Livello (MultiIndex)**  

- `.set_index()` – Imposta una o più colonne come indice del DataFrame.  
- `.reset_index()` – Reimposta l'indice del DataFrame, spostando gli attuali indici nelle colonne.  
- `.sort_index()` – Ordina il DataFrame in base ai valori dell'indice.  
- `.swaplevel()` – Scambia i livelli di un MultiIndex.  
- `.stack()` – Comprime i livelli delle colonne in righe.  
- `.unstack()` – Espande i livelli delle righe in colonne.  
- `.reorder_levels()` – Riordina i livelli di un MultiIndex.  
- `.index.get_level_values()` – Estrae i valori di un livello specifico da un MultiIndex.  
- `.droplevel()` – Rimuove un livello da un MultiIndex.  
- `.groupby(level=...)` – Raggruppa i dati in base ai livelli del MultiIndex.  