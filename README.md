# Botquake
## Sistema di monitoraggio e consultazione degli eventi sismici nell'area etnea mediante Telegram

### 1. Introduzione

**Botquake** è un progetto software sviluppato nell'ambito del corso di *Quality Development*, finalizzato alla realizzazione di un sistema automatizzato per la consultazione delle informazioni relative agli eventi sismici registrati nell'area etnea.

Il progetto si basa sull'integrazione tra la piattaforma di messaggistica Telegram e i dati sismologici resi disponibili dall'Istituto Nazionale di Geofisica e Vulcanologia (INGV). L'obiettivo è fornire agli utenti uno strumento di consultazione accessibile, attraverso un'interfaccia conversazionale, che consenta di ottenere informazioni sugli eventi sismici di interesse.

### 2. Obiettivi del progetto

L'obiettivo principale di Botquake consiste nello sviluppo di un bot Telegram in grado di acquisire, elaborare e restituire informazioni relative agli eventi sismici registrati nell'area geografica dell'Etna.

In particolare, il sistema è progettato per offrire le seguenti funzionalità:

- **Consultazione degli eventi sismici:** possibilità di richiedere informazioni relative all'ultimo evento sismico registrato nell'area geografica di interesse.
- **Filtraggio per magnitudo:** possibilità di circoscrivere la ricerca mediante l'impostazione di un valore massimo di magnitudo.
- **Visualizzazione delle informazioni:** restituzione dei principali dati associati all'evento sismico individuato.
- **Rappresentazione geografica:** generazione di una mappa relativa alla localizzazione dell'evento, accompagnata dall'indicazione della magnitudo rilevata.

### 3. Architettura e funzionamento del sistema

Botquake adotta un'architettura basata sull'interazione tra un'applicazione Python eseguita localmente e l'infrastruttura di comunicazione messa a disposizione da Telegram.

L'applicazione svolge il ruolo di componente applicativo incaricato di ricevere le richieste degli utenti, elaborare i comandi impartiti e predisporre le relative risposte.

Il processo di interazione può essere schematizzato nelle seguenti fasi:

1. L'utente invia un comando attraverso l'interfaccia di Telegram.
2. La richiesta viene gestita attraverso le API della piattaforma Telegram.
3. L'applicazione Botquake, in esecuzione sull'ambiente locale, riceve ed elabora il comando.
4. Il sistema acquisisce e analizza le informazioni sismologiche pertinenti.
5. I risultati vengono restituiti all'utente attraverso la chat Telegram.
6. A corredo delle informazioni testuali, viene fornita una rappresentazione cartografica della localizzazione dell'evento sismico.

### 4. Sorgente dei dati sismologici

Il sistema utilizza le informazioni pubblicate sul portale ufficiale dell'Istituto Nazionale di Geofisica e Vulcanologia (INGV):

- Portale istituzionale: https://terremoti.ingv.it/

I dati disponibili comprendono informazioni relative agli eventi sismici registrati attraverso differenti reti di monitoraggio.

Ai fini del progetto, il dominio geografico di interesse viene circoscritto all'area etnea, in modo da rendere la consultazione maggiormente pertinente al contesto territoriale considerato.

Le informazioni utilizzate sono distribuite secondo la licenza **Creative Commons Attribution 4.0 International (CC BY 4.0)**, che ne consente il riutilizzo nel rispetto degli obblighi di attribuzione della fonte.

Riferimento alla licenza: https://creativecommons.org/licenses/by/4.0/

### 5. Interazione con il sistema

L'interazione con Botquake avviene mediante un insieme di comandi impartiti direttamente attraverso la chat Telegram.

L'utente può richiedere informazioni sull'evento sismico più recente registrato nell'area di interesse oppure specificare un parametro di magnitudo massima per affinare i criteri di ricerca.

A seguito dell'elaborazione della richiesta, il sistema restituisce le informazioni relative all'evento individuato, integrandole con una rappresentazione cartografica che ne evidenzia la posizione geografica e il valore di magnitudo.

#### 5.1 Esempio di interazione

Di seguito vengono riportate alcune schermate esemplificative dell'interazione tra l'utente e il sistema.

![Esempio di interazione con Botquake](images/botquake_01.jpg)

*Figura 1 – Interfaccia conversazionale del bot Telegram.*

![Visualizzazione dei risultati](images/botquake_02.jpg)

*Figura 2 – Esempio di restituzione delle informazioni relative a un evento sismico.*

### 6. Configurazione e inizializzazione del bot

La creazione e la configurazione dell'applicazione Telegram richiedono l'utilizzo del servizio ufficiale **BotFather**, attraverso il quale è possibile registrare un nuovo bot e ottenere le credenziali necessarie alla comunicazione con le API della piattaforma.

#### 6.1 Registrazione del bot tramite BotFather

Per inizializzare il bot è necessario accedere a Telegram, utilizzando il client desktop oppure quello mobile, e individuare il servizio BotFather.

![Ricerca di BotFather](images/botfather_01.jpg)

Attraverso l'interfaccia conversazionale di BotFather è possibile avviare la procedura di creazione di una nuova applicazione bot.

Durante questa fase vengono definiti:

- Il nome identificativo del bot.
- Lo username associato all'applicazione, che deve terminare con il suffisso `bot`.

La procedura guidata consente di completare la registrazione e rendere disponibile il bot sulla piattaforma Telegram.

![Configurazione del bot tramite BotFather](images/botfather_02.jpg)

#### 6.2 Generazione del token di autenticazione

Al termine della procedura di registrazione, BotFather genera un token di autenticazione associato al bot.

Tale credenziale consente all'applicazione di autenticarsi presso le API di Telegram e costituisce un elemento necessario per instaurare la comunicazione tra il software Botquake e l'infrastruttura della piattaforma.

**Nota di sicurezza:** il token deve essere trattato come una credenziale riservata. Non deve essere pubblicato nel repository, condiviso con soggetti non autorizzati o inserito direttamente in file accessibili pubblicamente.

### 7. Tecnologie e dipendenze software

Lo sviluppo del progetto si basa sul linguaggio di programmazione Python e sull'utilizzo della libreria `python-telegram-bot`, che fornisce le funzionalità necessarie per interagire con le API di Telegram.

La libreria costituisce il livello di integrazione tra l'applicazione locale e il servizio di messaggistica, consentendo la gestione dei comandi e lo scambio dei messaggi.

#### 7.1 Requisiti di sistema

| Componente | Versione |
|---|---|
| Python | 3.11.0 |
| python-telegram-bot | 13.13 |

#### 7.2 Verifica dell'ambiente di sviluppo

Per verificare la versione di Python installata nell'ambiente di sviluppo è possibile eseguire il seguente comando:

```bash
python --version
```

Per visualizzare l'elenco delle librerie Python installate:

```bash
pip3 list
```

#### 7.3 Installazione della dipendenza principale

La libreria utilizzata dal progetto può essere installata mediante il package manager `pip`:

```bash
pip install python-telegram-bot==13.13
```

### 8. Riferimenti

- **Istituto Nazionale di Geofisica e Vulcanologia (INGV):** https://terremoti.ingv.it/
- **Telegram:** https://telegram.org/
- **BotFather:** https://t.me/BotFather
- **Python:** https://www.python.org/
- **python-telegram-bot:** https://pypi.org/project/python-telegram-bot/
- **Creative Commons Attribution 4.0 International:** https://creativecommons.org/licenses/by/4.0/

---

*Botquake – Progetto sviluppato nell'ambito del corso di Quality Development.*
