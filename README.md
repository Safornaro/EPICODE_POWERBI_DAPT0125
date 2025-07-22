# Brazilian E-Commerce Dashboard – Power BI Report

## Dataset

Il progetto si basa sul **Brazilian E-commerce Public Dataset by Olist**, disponibile su [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).  
Il dataset contiene dati reali raccolti tra il 2016 e il 2018 su ordini online effettuati da clienti in Brasile. Comprende informazioni dettagliate su:

- Transazioni e ordini
- Clienti e venditori
- Pagamenti e recensioni
- Prodotti e categorie merceologiche
- Tempi di spedizione e consegna
- Localizzazione geografica

Il dataset è composto da 9 tabelle collegate tra loro tramite relazioni chiave-primaria/chiave-esterna.

---

## Obiettivo del Progetto

Questo report interattivo è stato realizzato nell’ambito del percorso formativo per **Junior Data Analyst** con i seguenti obiettivi:

- Analizzare un dataset reale e complesso
- Progettare una dashboard dinamica e informativa in **Power BI**
- Applicare trasformazioni, misure DAX, filtri e visualizzazioni personalizzate
- Comunicare insight strategici tramite indicatori e grafici

Il report si articola in 4 sezioni principali:

1. **Overview** (panoramica generale)
2. **Orders** (analisi del customer journey)
3. **Logistics** (tempi e ritardi di consegna)
4. **Sellers** (performance dei venditori)

---

# Overview

La sezione **Overview** fornisce una sintesi dei principali KPI e delle metriche temporali più rilevanti del marketplace Olist.  
Tutti i dati sono filtrabili per:

- **State** (es. São Paulo, Rio de Janeiro, etc.)
- **Year** (2016–2018)
- **Order Status** (delivered, canceled, etc.)

### KPI visualizzati

- **Revenue**: somma di prezzo prodotto + costo spedizione
- **Orders**: quantità totale di ordini effettuati
- **Quantity sold**: numero totale di prodotti acquistati
- **Average review score**: media delle valutazioni post-consegna

### Grafici inclusi

- **Monthly Orders and % Change YoY**  
  Confronto mese per mese tra ordini dell’anno corrente e dell’anno precedente, con calcolo della variazione percentuale (YoY).

- **Revenue Trend and % Change YoY**  
  Trend dei ricavi mensili con variazione YoY visualizzata come linea sovrapposta.

- **Review Score Distribution**  
  Grafico a torta che mostra la distribuzione percentuale dei punteggi da 1 a 5 stelle (inclusi i casi senza review).

- **Average Score by Quarter and % Change YoY**  
  Analisi del punteggio medio per trimestre, comparato con l’anno precedente.

---

# Orders

La pagina **Orders** esplora nel dettaglio il comportamento d’acquisto dei clienti e le metriche legate agli ordini effettuati.

### KPI visualizzati

- **Net Sales (excl. Shipping)**: ricavi netti generati escludendo i costi di spedizione.
- **AOV – Average Order Value**: valore medio per ordine, comprensivo di spedizione.
- **Orders**: numero totale di ordini registrati.
- **Quantity Sold**: quantità totale di prodotti venduti.

### Grafici inclusi

- **Monthly Sales Quantity Comparison (YoY)**  
  Confronto tra quantità mensili vendute e lo stesso mese dell’anno precedente, con variazione YoY evidenziata tramite linea arancione.

- **Payment Method Distribution**  
  Grafico a torta che mostra la percentuale d’utilizzo dei vari metodi di pagamento:
  - *credit card* 
  - *boleto* 
  - *voucher*
  - *debit card*

- **Units Sold by Product Category**  
  Grafico a barre orizzontali che mostra le categorie più vendute. Le categorie principali includono:
  - *bed_bath_table*
  - *health_beauty*
  - *sports_leisure*, ecc.

- **Revenue by Customer Location**  
  Mappa geografica che visualizza il totale dei ricavi generati per **stato brasiliano**, utile per individuare aree con maggiore concentrazione di clienti attivi.

### Analisi avanzata

In alto a sinistra sono presenti due pulsanti che consentono di approfondire i dati:

- **View Order Details**  
  Apre la pagina **Order Details**, una tabella interattiva in cui è possibile esplorare ogni singolo ordine con filtri per:
  - *order ID*
  - *product ID*
  - *seller ID*
  - *customer ID*
  - *order status*
  - *intervalli di prezzo, spedizione e data*

  La tabella mostra anche i totali aggregati di:
  - **Ricavi (Price)**
  - **Spese di spedizione (Freight Value)**

- **View Decomposition Tree**  
  Apre un **grafico ad albero interattivo (Decomposition Tree)** che consente di esplorare in modo gerarchico i driver delle vendite.  
  L’utente può analizzare i ricavi per:
  - *mese*
  - *stato e città del cliente*
  - *categoria prodotto*

---

# Logistics

Questa sezione della dashboard è dedicata all’analisi delle **performance logistiche** relative agli ordini effettuati sulla piattaforma Olist. Vengono monitorati i tempi di spedizione, di consegna e i costi logistici, offrendo una panoramica sia aggregata che dettagliata a livello geografico.

### **KPI principali**

- **Orders**: quantità di ordini ricevuti  
- **AVG Shipping Time (days)**: media dei giorni impiegati per effettuare la spedizione   
- **AVG Delivery Time (days)**: media dei giorni impiegati per effettuare la consegna   
- **AVG Freight Value**: media delle spese di spedizione

### **Grafici**

- **Average Shipping Cost by City**: città con i costi medi di spedizione più elevati.
- **Average Delivery Time by City**: città con i tempi medi di consegna più lunghi.
Attraverso due pulsanti è possibile visualizzare i grafici per Stato

- **Average Shipping vs Delivery Time per Month**: confronto mensile tra tempi di spedizione e consegna.
- **On-Time Delivery Rate**: percentuale di consegne puntuali rispetto a quelle in ritardo.
- **Order Processing Status**: distribuzione degli ordini nei diversi stati (escluse le consegne concluse e gli ordini cancellati).
- **AVG Delivery Time (days) of late orders by State**: mappa che mostra i tempi medi di consegna in ritardo, per stato.

### **Filtri disponibili**

Nella barra laterale sinistra è possibile filtrare i dati per:

- **Order Status**
- **Year**
- **State**

In alto, due pulsanti consentono di navigare verso pagine di dettaglio:

- **View shipping statistics** → rimanda alla pagina *Shipping Statistics*
- **View shipping details** → rimanda alla pagina *Shipping Details*

---

## Shipping Statistics

Pagina dedicata alla visualizzazione aggregata delle **statistiche di spedizione per Stato**.

### **Colonne disponibili**

- **State**
- **Orders**
- **AVG Shipping Time (day)**
- **AVG Delivery Time (day)**
- **AVG Shipping Value**
- **% Late Deliveries**

### **Filtri disponibili**

- **Year**

---

## Shipping Details

Pagina di dettaglio che mostra **le informazioni logistiche a livello di singolo ordine/prodotto**.

### **Colonne disponibili**

- **Order ID**
- **Order Item ID**
- **Freight Value**
- **Order Status**
- **Order Date**
- **Estimated Delivery Date**
- **Delivered Carrier Date**
- **Delivered Customer Date**

### **Filtri disponibili**

- **Order ID**
- **Order Status**
- **Freight Value**
- **Order Date Range**
- **KPI Delivery** (On time / Late)

In fondo alla tabella è visibile il **totale complessivo del valore di spedizione**.


# Sellers

In questa sezione viene analizzata la performance dei venditori attivi sulla piattaforma Olist. Considerando che il dataset è **anonimizzato** (i seller ID sono stringhe alfanumeriche casuali), è stata scelta un'impostazione **statistica** anziché nominativa.

### **KPI principali**

- **Active Sellers**: Totale venditori registrati  
- **AVG Orders per Seller**: la media di ordini processati da ciascun venditore
- **AVG Revenue per Seller**: la media dei ricavi di ciascun venditore
- **Median Revenue per Seller**: la mediana dei ricavi di ciascun venditore

### **Grafici**

- **Sales Distribution per Seller**: istogramma che mostra la distribuzione degli importi di vendita per venditore, con evidenziata la media (linea verde) e la mediana (linea rossa).
- **Orders vs Revenue per Seller**: scatter plot che mostra la correlazione tra numero di ordini e fatturato generato per ciascun venditore.
- **Sellers Classified as Normal or Outlier**: grafico a barre che mostra la classificazione dei seller in base alla loro performance (normali vs outlier), utile per contare gli outlier.

### **Nota metodologica**

L'approccio adottato consente di:

- Identificare eventuali **outlier** in termini di vendite.
- Valutare la **distribuzione della performance** economica.
- Analizzare **correlazioni** tra quantità di ordini gestiti e fatturato.

Questa impostazione permette di trarre insight significativi anche in assenza di nomi o etichette riconoscibili.

---
