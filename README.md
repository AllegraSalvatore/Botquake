# Botquake
### Sistema automatizzato per la consultazione degli eventi sismici nell'area etnea mediante Telegram

## 1. Introduzione

Botquake è un progetto software finalizzato alla progettazione e alla realizzazione di un'applicazione basata sull'integrazione con la piattaforma di messaggistica Telegram.

Il sistema si propone di fornire uno strumento automatizzato per la consultazione delle informazioni relative agli eventi sismici, attraverso un'interfaccia conversazionale che consente agli utenti di interagire con un servizio applicativo dedicato. L'ambito geografico di interesse è circoscritto all'area etnea, con l'obiettivo di facilitare l'accesso alle informazioni sismologiche relative a tale territorio.

## 2. Obiettivi progettuali

L'obiettivo principale consiste nella realizzazione di un *bot Telegram*, ossia un'applicazione software in grado di ricevere, elaborare e gestire richieste provenienti dagli utenti attraverso l'infrastruttura di comunicazione della piattaforma Telegram.

Dal punto di vista architetturale, l'applicazione viene eseguita su una macchina esterna all'infrastruttura di Telegram, assumendo il ruolo di componente applicativo responsabile dell'elaborazione delle richieste ricevute.

Il modello di interazione previsto si articola secondo il seguente flusso operativo:

1. L'utente impartisce un comando attraverso l'interfaccia di chat del client Telegram.
2. La richiesta viene trasmessa attraverso i servizi di comunicazione della piattaforma Telegram.
3. Il comando viene inoltrato all'applicazione Botquake, in esecuzione sulla macchina predisposta.
4. L'applicazione interpreta ed elabora la richiesta, predisponendo una risposta coerente con il comando ricevuto.
5. Il risultato dell'elaborazione viene trasmesso nuovamente attraverso le API di Telegram e reso disponibile all'utente mediante il client di messaggistica.

Tale architettura consente di separare il livello di interazione con l'utente dalla logica applicativa, delegando a Botquake la gestione delle funzionalità specifiche del servizio.

## 3. Specifiche dell'applicazione

L'applicazione Botquake è progettata per acquisire ed elaborare le informazioni sismologiche pubblicate dall'Istituto Nazionale di Geofisica e Vulcanologia (INGV), disponibili attraverso il portale istituzionale:

https://terremoti.ingv.it/

Le informazioni utilizzate sono rese disponibili dall'INGV secondo i termini della licenza *Creative Commons Attribution 4.0 International (CC BY 4.0)*, che ne consente la condivisione e il riutilizzo, anche in ambito applicativo, nel rispetto degli obblighi di attribuzione della fonte.

Riferimento alla licenza: https://creativecommons.org/licenses/by/4.0/

Il database di riferimento comprende informazioni relative agli eventi sismici rilevati attraverso differenti reti di monitoraggio sismologico, distribuite su scala nazionale e internazionale.

Considerata la finalità applicativa del progetto, il dominio geografico di analisi viene circoscritto all'area etnea. Tale delimitazione consente di concentrare l'elaborazione sui fenomeni sismici di maggiore interesse per il contesto territoriale individuato, riducendo l'ambito di consultazione rispetto alla totalità degli eventi disponibili nel database.

Il sistema si pone pertanto l'obiettivo di rendere maggiormente accessibili le informazioni sismologiche relative al territorio etneo, attraverso un'interfaccia di consultazione semplice e immediata, integrata direttamente nell'ambiente Telegram.

## 4. Funzionalità principali

Il sistema mette a disposizione funzionalità per la consultazione degli eventi sismici registrati nell'area geografica di interesse.

In particolare, le funzionalità previste comprendono:

- **Consultazione degli eventi sismici:** individuazione e visualizzazione dell'evento sismico più recente registrato nell'area etnea.
- **Filtraggio per magnitudo:** possibilità di limitare la ricerca degli eventi mediante la specificazione di una soglia massima di magnitudo.
- **Restituzione delle informazioni:** visualizzazione dei principali parametri associati all'evento sismico individuato.
- **Rappresentazione cartografica:** generazione di una mappa per la localizzazione geografica dell'evento, con indicazione della relativa magnitudo.

## 5. Tecnologie e dipendenze

Il progetto è sviluppato utilizzando il linguaggio di programmazione Python e si avvale della libreria `python-telegram-bot` per l'integrazione con le API di Telegram.

La libreria consente di gestire la comunicazione tra il bot e la piattaforma di messaggistica, permettendo la ricezione dei comandi e la restituzione delle risposte agli utenti.

### 5.1 Requisiti software

| Componente | Versione |
|---|---|
| Python | 3.11.0 |
| python-telegram-bot | 13.13 |

### 5.2 Verifica dell'ambiente

Per verificare la versione di Python installata nel sistema è possibile utilizzare il seguente comando:

```bash
python --version
```

Per visualizzare le librerie installate nell'ambiente Python:

```bash
pip3 list
```

### 5.3 Installazione delle dipendenze

L'installazione della libreria principale può essere effettuata mediante il package manager `pip`:

```bash
pip install python-telegram-bot==13.13
```

## 6. Configurazione e inizializzazione

Per utilizzare Botquake è necessario predisporre un bot Telegram mediante il servizio ufficiale BotFather, responsabile della registrazione e della configurazione delle applicazioni bot sulla piattaforma.

### 6.1 Creazione del bot

La procedura di registrazione può essere avviata accedendo a Telegram, attraverso il client desktop o mobile, e individuando il servizio ufficiale BotFather.

Attraverso l'interfaccia conversazionale è possibile avviare la creazione di una nuova applicazione bot, specificandone il nome identificativo e lo username.

Quest'ultimo deve rispettare le convenzioni previste dalla piattaforma Telegram e terminare con il suffisso `bot`.

### 6.2 Generazione del token di autenticazione

Al termine della procedura di registrazione, BotFather genera un token di autenticazione associato all'applicazione.

Tale credenziale consente al software di autenticarsi presso le API di Telegram e costituisce un requisito indispensabile per instaurare la comunicazione tra Botquake e l'infrastruttura della piattaforma.

**Nota di sicurezza:** il token di autenticazione deve essere considerato una credenziale riservata. Non deve essere pubblicato all'interno del repository né condiviso con soggetti non autorizzati.

## 7. Riferimenti

- **Istituto Nazionale di Geofisica e Vulcanologia (INGV):** https://terremoti.ingv.it/
- **Telegram:** https://telegram.org/
- **BotFather:** https://t.me/BotFather
- **Python:** https://www.python.org/
- **python-telegram-bot:** https://pypi.org/project/python-telegram-bot/
- **Creative Commons Attribution 4.0 International:** https://creativecommons.org/licenses/by/4.0/

---

*Botquake – Sistema software per la consultazione degli eventi sismici nell'area etnea.*
