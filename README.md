# Finager

## Descrizione del progetto

**Finager** è una web application sviluppata per consentire agli utenti di monitorare e gestire le proprie finanze personali.

L'applicazione permette di registrare le proprie **entrate e uscite economiche**, organizzandole all'interno di diversi **conti personali**. I dati finanziari vengono poi elaborati e rappresentati attraverso una dashboard grafica, permettendo all'utente di avere una visione chiara dell'andamento delle proprie spese e disponibilità.

L'obiettivo principale di Finager è fornire uno strumento semplice e intuitivo per il controllo delle proprie finanze, consentendo di analizzare le proprie abitudini di spesa tramite grafici e riepiloghi.

---

# Funzionalità principali

* Registrazione e autenticazione degli utenti
* Gestione del proprio profilo personale
* Creazione e gestione di diversi conti
* Inserimento di transazioni economiche:

  * entrate
  * uscite
* Organizzazione delle transazioni tramite categorie
* Visualizzazione dei dati finanziari tramite grafici interattivi
* Dashboard riepilogativa della situazione economica dell'utente
* Gestione sicura delle sessioni tramite autenticazione JWT

---

# Tecnologie utilizzate

## Frontend

L'interfaccia grafica è sviluppata utilizzando:

* **Vue.js 3**
* **Vue Router** per la gestione della navigazione
* **Vuex** per la gestione dello stato globale dell'applicazione
* **Axios** per la comunicazione con il server
* **Bootstrap 5** per la parte grafica e il layout
* **Chart.js / Vue-chartjs** per la generazione dei grafici
* **Vue Toastification** per le notifiche all'utente

Il frontend si trova nella cartella:

```
client/
```

---

## Backend

La logica applicativa è implementata tramite:

* **Node.js**
* **Express.js**
* **PostgreSQL** come database relazionale
* **pg** per la connessione al database
* **JWT (JSON Web Token)** per la gestione dell'autenticazione
* **Argon2** per l'hashing sicuro delle password
* **Nodemailer** per l'invio di email
* **XLSX** per la gestione di file Excel

Il backend si trova nella cartella:

```
server/
```

---

# Struttura del progetto

```
Finager-Progetto-LTW/
│
├── client/              # Applicazione frontend Vue
│
├── server/              # Backend Node.js + Express
│   ├── src/
│   ├── .env.example
│   └── package.json
│
└── pg.sql               # Script per la creazione del database PostgreSQL
```

---

# Requisiti

Prima di avviare il progetto è necessario installare:

* Node.js (versione consigliata: LTS)
* npm
* PostgreSQL
* pgAdmin (opzionale, per la gestione del database)

---

# Configurazione del database

1. Avviare PostgreSQL.

2. Creare il database utilizzando lo script presente nella repository:

```
pg.sql
```

Lo script può essere eseguito tramite **pgAdmin** oppure tramite il terminale PostgreSQL.

Il database creato deve chiamarsi:

```
finager
```

---

# Configurazione Backend

Entrare nella cartella server:

```bash
cd server
```

Installare le dipendenze:

```bash
npm install
```

Creare un file `.env` nella cartella `server` partendo dal file `.env.example`:

```bash
cp .env.example .env
```

Configurare le variabili d'ambiente:

```env
PG_USER="postgres"
PG_HOST="localhost"
PG_DATABASE="finager"
PG_PASSWORD="password_database"
PG_PORT="5432"

JWT_KEY="chiave_segreta"
```

---

## Avvio del server

Per avviare il backend in modalità sviluppo:

```bash
npm run dev
```

oppure:

```bash
npm start
```

Il server sarà disponibile sulla porta configurata nell'applicazione.

---

# Configurazione Frontend

Aprire un nuovo terminale e spostarsi nella cartella client:

```bash
cd client
```

Installare le dipendenze:

```bash
npm install
```

---

## Avvio dell'interfaccia grafica

Avviare il frontend con:

```bash
npm run serve
```

L'applicazione sarà disponibile all'indirizzo mostrato dal terminale, generalmente:

```
http://localhost:8080
```

---

# Avvio completo dell'applicazione

Per utilizzare Finager è necessario avviare entrambi i componenti:

### Terminale 1 - Backend

```bash
cd server
npm run dev
```

### Terminale 2 - Frontend

```bash
cd client
npm run serve
```

Dopo l'avvio sarà possibile accedere all'applicazione tramite il browser.

---

# Database

Il database PostgreSQL contiene le informazioni relative a:

* utenti
* conti personali
* transazioni
* categorie
* dati necessari alla generazione dei grafici

La struttura completa del database è definita nel file:

```
pg.sql
```

---

Università degli Studi di Roma "La Sapienza"
