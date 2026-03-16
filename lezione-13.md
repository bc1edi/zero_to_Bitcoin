# Lezione 13 — Inviare bitcoin: anatomia di una transazione

## Obiettivi della lezione
- Comprendere il processo completo di invio di una transazione Bitcoin, dalla creazione alla conferma
- Capire il ruolo della mempool, delle commissioni e delle conferme
- Conoscere la funzione Replace-by-Fee (RBF) per gestire transazioni bloccate
- Identificare gli errori piu comuni nell'invio di bitcoin e come evitarli

## Il processo di invio passo dopo passo

Inviare bitcoin puo sembrare semplice come premere un pulsante, ma dietro ogni transazione si nasconde un processo crittografico e di rete articolato. Comprenderlo vi rendera utenti piu consapevoli e sicuri.

### Passo 1: Preparare la transazione

Aprite il vostro wallet e selezionate "Invia". Dovrete inserire due informazioni fondamentali: l'**indirizzo del destinatario** e l'**importo** da inviare. L'indirizzo puo essere inserito scansionando un codice QR (metodo consigliato per evitare errori di battitura) oppure copiando e incollando la stringa alfanumerica. Verificate sempre le prime e le ultime cifre dell'indirizzo dopo averlo incollato.

### Passo 2: Scegliere la commissione

A differenza dei bonifici bancari con commissioni fisse, in Bitcoin la commissione (fee) e variabile e determina la **priorita** della vostra transazione. La commissione si misura in **satoshi per byte virtuale** (sat/vB) e dipende dalla congestione della rete in quel momento.

La maggior parte dei wallet offre tre opzioni: priorita **alta** (conferma nel prossimo blocco, circa 10 minuti), **media** (conferma entro pochi blocchi) e **bassa** (conferma entro ore o il giorno successivo). Strumenti come **mempool.space** mostrano in tempo reale le commissioni consigliate.

### Passo 3: Firma e trasmissione

Quando confermate l'invio, il wallet utilizza la vostra chiave privata per **firmare digitalmente** la transazione. Questa firma dimostra matematicamente che siete i legittimi proprietari dei fondi, senza rivelare la chiave privata stessa. La transazione firmata viene poi trasmessa ai nodi della rete Bitcoin.

## La mempool: la sala d'attesa delle transazioni

Una volta trasmessa, la transazione non entra immediatamente in un blocco. Viene prima raccolta nella **mempool** (memory pool), una sorta di sala d'attesa dove le transazioni non confermate attendono di essere selezionate dai miner.

Ogni miner costruisce un blocco candidato scegliendo le transazioni dalla mempool. Naturalmente, i miner hanno un incentivo economico a selezionare per prime le transazioni con le commissioni piu alte. Per questo motivo, una commissione maggiore corrisponde a una conferma piu rapida.

La dimensione della mempool varia costantemente. In periodi di scarsa attivita, anche transazioni con commissioni minime vengono confermate rapidamente. Nei momenti di forte domanda, la mempool si riempie e le transazioni con commissioni basse possono attendere ore o giorni.

## Il processo di conferma

### La prima conferma

Quando un miner include la vostra transazione in un blocco e quel blocco viene aggiunto alla blockchain, la transazione riceve la **prima conferma**. Questo avviene mediamente ogni 10 minuti, ma il tempo effettivo puo variare significativamente.

### Da 1 a 6 conferme

Ogni nuovo blocco aggiunto alla blockchain dopo quello che contiene la vostra transazione rappresenta una conferma aggiuntiva. Il livello di sicurezza cresce esponenzialmente con ogni conferma:

- **1 conferma**: sufficiente per transazioni di piccolo importo. La probabilita di inversione e gia molto bassa.
- **3 conferme**: livello di sicurezza adeguato per la maggior parte delle transazioni.
- **6 conferme**: standard storico per considerare una transazione definitivamente irreversibile. Utilizzato per importi molto elevati.

La ragione e matematica: per invertire una transazione con N conferme, un attaccante dovrebbe ricalcolare la proof-of-work di N blocchi superando la velocita dell'intera rete. Con 6 conferme, questa impresa e praticamente impossibile.

## Replace-by-Fee (RBF)

Cosa succede se avete inviato una transazione con una commissione troppo bassa e questa rimane bloccata nella mempool? Qui interviene il meccanismo **Replace-by-Fee (RBF)**.

Se la transazione originale e stata creata con il flag RBF attivato (molti wallet moderni lo fanno automaticamente), potete creare una **nuova versione** della stessa transazione con una commissione piu alta. La rete accettera la nuova versione e scartera quella precedente.

Per utilizzare RBF, il vostro wallet deve supportare questa funzionalita. In Sparrow Wallet, Electrum e Blue Wallet e generalmente disponibile. Se la transazione non era stata segnalata come sostituibile, l'unica alternativa e attendere che venga confermata o, dopo un certo periodo, che venga espulsa dalla mempool.

## Errori comuni e come evitarli

**Indirizzo errato**: una volta confermata, una transazione Bitcoin e irreversibile. Se inviate fondi a un indirizzo sbagliato, non esiste alcun meccanismo di rimborso. Verificate sempre l'indirizzo con estrema attenzione, confrontando le prime e le ultime cifre.

**Commissione inadeguata**: una commissione troppo bassa in un periodo di alta congestione puo lasciare la transazione in sospeso per giorni. Consultate sempre mempool.space prima di scegliere la fee.

**Invio alla rete sbagliata**: attenzione a non confondere indirizzi Bitcoin con indirizzi di altre criptovalute. Fondi inviati alla rete sbagliata sono generalmente irrecuperabili.

**Mancata verifica dell'importo**: controllate due volte sia l'importo che la commissione prima di confermare. Alcuni errori di digitazione possono avere conseguenze costose.

**Dimenticare il change output**: quando il wallet spende una UTXO di valore superiore all'importo da inviare, crea automaticamente un "resto" (change) verso un vostro indirizzo. Questo processo e gestito dal software, ma e utile comprenderne il meccanismo per leggere correttamente le transazioni sul block explorer.

## Concetti chiave
- La commissione di una transazione e variabile e determina la velocita di conferma
- La mempool e la coda in cui le transazioni attendono di essere incluse in un blocco
- Una conferma corrisponde a un blocco aggiunto dopo quello della transazione; 6 conferme sono lo standard per la massima sicurezza
- Replace-by-Fee (RBF) permette di sostituire una transazione non confermata con una a commissione piu alta
- Le transazioni Bitcoin sono irreversibili: verificare indirizzo e importo prima dell'invio e fondamentale
- Strumenti come mempool.space aiutano a scegliere la commissione corretta in base alla congestione della rete

## Domande di riflessione
1. In quali situazioni potrebbe essere accettabile pagare una commissione alta per una conferma rapida, e quando invece conviene attendere?
2. Perche il meccanismo delle conferme multiple rende Bitcoin piu sicuro rispetto a un sistema di pagamento tradizionale?
3. Come cambierebbe il vostro comportamento nell'invio di bitcoin sapendo che le transazioni sono completamente irreversibili?
