# Lezione 7 — Transazioni Bitcoin: input, output, fee

## Obiettivi della lezione
- Comprendere l'anatomia di una transazione Bitcoin e il modello UTXO
- Capire come funzionano input, output e indirizzi di resto nelle transazioni
- Analizzare il meccanismo delle commissioni (fee) e come vengono calcolate
- Conoscere il funzionamento della mempool e la priorita delle transazioni

## Anatomia di una transazione Bitcoin

Una transazione Bitcoin potrebbe sembrare un semplice trasferimento di fondi da un indirizzo a un altro, ma la realta e piu sofisticata. A differenza di un bonifico bancario, dove il saldo di un conto viene semplicemente decrementato e quello di un altro incrementato, Bitcoin utilizza un modello completamente diverso chiamato **UTXO** (Unspent Transaction Output, ovvero "output di transazione non speso").

Per comprendere il modello UTXO, pensiamo al contante fisico. Quando paghi un caffe da 2 euro con una banconota da 10, non "trasferisci" 2 euro: dai la banconota intera e ricevi 8 euro di resto. Le transazioni Bitcoin funzionano in modo analogo.

Ogni transazione e composta da tre elementi fondamentali: uno o piu **input** (da dove provengono i fondi), uno o piu **output** (dove vanno i fondi) e la **commissione** implicita (la differenza tra input e output).

## Input: da dove vengono i fondi

Gli input di una transazione sono riferimenti a **output precedenti non spesi** (UTXO). Quando qualcuno ti invia bitcoin, quell'invio crea un output legato al tuo indirizzo. Quell'output resta "non speso" finche non lo utilizzi come input in una nuova transazione.

Ogni input contiene tre informazioni essenziali. La prima e il **riferimento alla transazione precedente**: l'identificativo (hash) della transazione che ha creato l'UTXO che si sta spendendo. La seconda e l'**indice dell'output**: quale specifico output di quella transazione si sta utilizzando (una transazione puo avere piu output). La terza e la **firma digitale**: la prova crittografica che il proprietario dell'UTXO autorizza la spesa, generata con la chiave privata corrispondente.

Se gli UTXO disponibili non corrispondono esattamente all'importo che si vuole inviare, si possono combinare piu UTXO come input nella stessa transazione, esattamente come si combinano piu banconote per pagare un importo elevato.

## Output: dove vanno i fondi

Gli output definiscono i nuovi UTXO che vengono creati dalla transazione. Ogni output specifica un importo in satoshi (la piu piccola unita di bitcoin, pari a un centomilionesimo di bitcoin) e le condizioni necessarie per spenderlo in futuro, tipicamente associate a un indirizzo Bitcoin del destinatario.

Una transazione puo avere piu output. Ad esempio, una singola transazione potrebbe distribuire fondi a piu destinatari contemporaneamente. Una volta che una transazione viene confermata nella blockchain, i suoi output diventano nuovi UTXO, pronti per essere spesi in transazioni future.

Un aspetto fondamentale e che un UTXO deve essere speso interamente: non puo essere utilizzato parzialmente. Questo ci porta al concetto di indirizzo di resto.

## L'indirizzo di resto (change address)

Supponiamo di possedere un UTXO del valore di 0,5 BTC e di voler inviare 0,3 BTC a un amico. Poiche l'UTXO da 0,5 BTC deve essere speso interamente, la transazione avra due output: 0,3 BTC all'indirizzo dell'amico e circa 0,2 BTC (meno la commissione) a un **indirizzo di resto** controllato da noi stessi.

L'indirizzo di resto e un nuovo indirizzo generato automaticamente dal nostro portafoglio (wallet). Questo meccanismo ha un'importante implicazione per la privacy: dopo la transazione, i nostri fondi rimanenti non saranno piu associati all'indirizzo originale, ma a un nuovo indirizzo. I wallet moderni gestiscono questo processo automaticamente, senza richiedere alcun intervento da parte dell'utente.

Ecco un esempio completo di transazione: un input (UTXO da 0,5 BTC), un primo output di 0,3 BTC verso l'indirizzo del destinatario, un secondo output di 0,1995 BTC verso il nostro indirizzo di resto. La differenza di 0,0005 BTC tra input e output e la commissione per il minatore.

## Le commissioni di transazione (fee)

Le commissioni in Bitcoin non sono stabilite da nessuna autorita centrale ma emergono da un **mercato libero** tra gli utenti e i minatori. La commissione di una transazione e calcolata come la differenza tra la somma degli input e la somma degli output. Qualsiasi valore non assegnato esplicitamente a un output viene automaticamente incamerato dal minatore che include la transazione in un blocco.

Le commissioni non sono proporzionali al valore trasferito (come nel sistema bancario), ma alla **dimensione della transazione in byte** (o, piu precisamente, in unita di peso virtuali dopo SegWit). Una transazione che combina molti piccoli UTXO sara piu grande in byte e quindi piu costosa di una transazione con un singolo input, indipendentemente dal valore trasferito.

Le commissioni si esprimono tipicamente in **satoshi per byte virtuale** (sat/vB). Se una transazione pesa 250 byte virtuali e la tariffa corrente e di 20 sat/vB, la commissione totale sara di 5.000 satoshi (circa 0,00005 BTC).

## La mempool: la sala d'attesa delle transazioni

Quando una transazione viene trasmessa alla rete Bitcoin, non viene immediatamente inclusa in un blocco. Entra invece nella **mempool** (memory pool), una sorta di sala d'attesa dove le transazioni non confermate attendono di essere selezionate da un minatore.

Ogni nodo della rete mantiene la propria mempool, che puo differire leggermente da quella degli altri nodi. I minatori, quando costruiscono un nuovo blocco, selezionano le transazioni dalla mempool dando priorita a quelle con le commissioni piu alte per byte, poiche il loro obiettivo e massimizzare il proprio guadagno.

Quando la rete e poco congestionata, anche transazioni con commissioni basse vengono confermate rapidamente. Durante i periodi di alta domanda, la mempool si riempie e le transazioni con commissioni insufficienti possono rimanere in attesa per ore o persino giorni. In questi momenti, gli utenti che necessitano di conferme rapide devono offrire commissioni piu elevate, creando una vera e propria asta competitiva per lo spazio limitato nei blocchi.

Alcuni wallet avanzati offrono la possibilita di utilizzare la funzione **RBF** (Replace-By-Fee), che permette di sostituire una transazione non confermata con una nuova versione che include una commissione piu alta, accelerandone la conferma.

## Concetti chiave
- Bitcoin utilizza il modello UTXO: ogni transazione consuma output precedenti non spesi e ne crea di nuovi
- Gli input di una transazione fanno riferimento a UTXO precedenti e includono una firma digitale come prova di autorizzazione
- Poiche un UTXO deve essere speso interamente, le transazioni creano un output di "resto" che ritorna al mittente
- Le commissioni sono calcolate in base alla dimensione della transazione in byte, non al valore trasferito
- La mempool e lo spazio in cui le transazioni attendono di essere selezionate dai minatori e incluse in un blocco
- I minatori danno priorita alle transazioni con commissioni piu alte per byte, creando un mercato competitivo per lo spazio nei blocchi

## Domande di riflessione
1. In che modo il modello UTXO di Bitcoin differisce dal modello a saldo utilizzato dalle banche tradizionali e quali vantaggi offre in termini di verifica e trasparenza?
2. Perche le commissioni Bitcoin sono basate sulla dimensione della transazione in byte piuttosto che sul valore trasferito, e come questo influenza il costo di transazioni con molti piccoli UTXO?
3. Come potrebbe un utente gestire strategicamente i propri UTXO per minimizzare le commissioni nelle transazioni future?
