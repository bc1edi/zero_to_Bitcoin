# Lezione 9 — Nodi: la rete decentralizzata

## Obiettivi della lezione
- Comprendere il ruolo fondamentale dei nodi nella rete Bitcoin e le funzioni che svolgono
- Distinguere tra nodi e minatori, chiarendone i ruoli complementari
- Conoscere i diversi tipi di nodi e le loro caratteristiche
- Capire perche gestire un proprio nodo e un atto di sovranita e come i nodi comunicano tra loro

## Cosa fa un nodo completo (full node)

Un **nodo completo** e un computer che esegue il software Bitcoin e mantiene una copia completa dell'intera blockchain, dalla prima transazione nel blocco genesi fino all'ultimo blocco appena creato. Ma un nodo non si limita ad archiviare dati: il suo ruolo principale e **validare indipendentemente ogni singola transazione e ogni singolo blocco** secondo le regole del protocollo Bitcoin.

Quando un nodo riceve un nuovo blocco dalla rete, non lo accetta ciecamente. Lo esamina in modo rigoroso, verificando una serie di condizioni. Controlla che ogni transazione nel blocco sia valida: le firme digitali sono corrette? Gli input fanno riferimento a UTXO realmente esistenti e non gia spesi? I valori sono coerenti? Verifica che il blocco rispetti le regole di consenso: l'hash dell'intestazione e inferiore al target di difficolta? La ricompensa del minatore non supera l'importo consentito? Il blocco si collega correttamente al blocco precedente?

Se anche una sola di queste verifiche fallisce, il nodo **rifiuta il blocco** e non lo propaga alla rete. Questo meccanismo e cio che rende Bitcoin veramente decentralizzato: nessun minatore, per quanto potente, puo imporre blocchi che violano le regole, perche la rete di nodi li rifiuterebbe unanimemente.

## La differenza tra nodi e minatori

Nodi e minatori sono spesso confusi, ma svolgono funzioni distinte e complementari. I **minatori** creano nuovi blocchi attraverso il processo di Proof of Work e competono per la ricompensa economica. I **nodi** verificano che il lavoro dei minatori rispetti le regole e decidono quale versione della blockchain e valida.

Un'analogia utile: i minatori sono come gli operai che costruiscono i piani di un edificio, mentre i nodi sono gli ispettori che verificano che ogni piano sia costruito secondo le norme edilizie. Un operaio puo essere molto produttivo, ma se il suo lavoro non supera l'ispezione, viene demolito.

Questo rapporto di forza e cruciale. I minatori hanno il potere economico di creare blocchi, ma i nodi hanno il potere di definire quali blocchi sono accettabili. Se tutti i minatori del mondo decidessero di cambiare una regola del protocollo -- ad esempio, aumentare il limite dei 21 milioni di bitcoin -- i nodi della rete rifiuterebbero semplicemente i loro blocchi. I minatori sarebbero costretti a tornare alle regole originali o a operare su una catena che nessuno riconosce.

Questa dinamica fu dimostrata concretamente durante la cosiddetta "guerra della dimensione dei blocchi" del 2017, quando una coalizione di grandi minatori e aziende tento di imporre un aumento della dimensione dei blocchi. La rete di nodi gestiti dagli utenti rifiuto la proposta, affermando il principio che sono gli utenti, non i minatori, a determinare le regole di Bitcoin.

## Tipi di nodi

### Nodo completo (full node)

Il nodo completo scarica e valida l'intera blockchain, che attualmente occupa diverse centinaia di gigabyte di spazio su disco. E il tipo di nodo che offre il massimo livello di sicurezza e indipendenza: non si fida di nessun altro partecipante alla rete, ma verifica tutto autonomamente. Per gestire un nodo completo e sufficiente un computer modesto -- anche un Raspberry Pi -- con spazio su disco adeguato e una connessione internet ragionevole.

### Nodo potato (pruned node)

Un **nodo potato** funziona esattamente come un nodo completo durante la validazione: scarica e verifica ogni singolo blocco dall'inizio della catena. La differenza e che, una volta validati, i blocchi piu vecchi vengono eliminati dal disco per risparmiare spazio. Un nodo potato potrebbe conservare solo gli ultimi 550 blocchi (circa quattro giorni), occupando pochi gigabyte invece di centinaia. Offre lo stesso livello di sicurezza nella validazione, ma non puo servire la storia completa della blockchain ad altri nodi.

### Nodo leggero (SPV/light node)

I **nodi SPV** (Simplified Payment Verification), descritti dallo stesso Satoshi nel whitepaper, non scaricano l'intera blockchain ma solo le intestazioni dei blocchi. Quando devono verificare una transazione, chiedono a nodi completi una prova crittografica (merkle proof) che la transazione sia effettivamente inclusa in un blocco. I nodi SPV offrono un buon compromesso tra praticita e sicurezza per i dispositivi mobili con risorse limitate. Tuttavia, si fidano parzialmente dei nodi completi a cui si connettono, il che li rende meno sovrani rispetto a un nodo completo.

## Perche gestire un proprio nodo

Gestire un proprio nodo non e solo un esercizio tecnico: e un atto di **sovranita finanziaria**. Quando utilizzi il nodo di qualcun altro -- che sia un servizio online, un exchange o un wallet che si connette a server di terze parti -- stai delegando la verifica delle tue transazioni a un'altra entita. Ti stai fidando del fatto che quel nodo sia onesto e aggiornato.

Con il tuo nodo, verifichi personalmente che ogni transazione che ricevi sia reale e confermata, che le regole del protocollo vengano rispettate e che nessuno stia tentando di ingannarti. Il tuo nodo e il tuo giudice personale della verita nella rete Bitcoin.

Inoltre, ogni nodo aggiuntivo rafforza la rete nel suo complesso. Piu nodi esistono, piu la rete e resiliente contro attacchi, censura e tentativi di modificare le regole del protocollo. Gestire un nodo e un contributo diretto alla decentralizzazione e alla sicurezza di Bitcoin.

## Come comunicano i nodi: il protocollo gossip

I nodi Bitcoin comunicano tra loro attraverso un **protocollo gossip** (pettegolezzo). Quando un nodo riceve una nuova transazione o un nuovo blocco e lo valida con successo, lo inoltra ai nodi a cui e connesso, che a loro volta lo inoltrano ai propri vicini, e cosi via. In pochi secondi, l'informazione si propaga all'intera rete, come un pettegolezzo che si diffonde in una comunita.

Ogni nodo si connette tipicamente a otto o piu altri nodi (peer). Non esiste un server centrale che distribuisce le informazioni: la rete si auto-organizza in una topologia dinamica dove i nodi possono unirsi e disconnettersi liberamente. Questa architettura rende la rete estremamente resistente: anche se una porzione significativa dei nodi venisse disattivata, il resto della rete continuerebbe a funzionare senza interruzioni.

## Concetti chiave
- Un nodo completo valida indipendentemente ogni transazione e ogni blocco, senza fidarsi di nessun altro partecipante alla rete
- I minatori creano i blocchi, ma sono i nodi a determinare quali blocchi sono validi e quali regole devono essere rispettate
- Esistono tre tipi principali di nodi: completi (massima sicurezza), potati (stesso livello di validazione con meno spazio su disco) e leggeri/SPV (compromesso tra praticita e verifica autonoma)
- Gestire un proprio nodo e un atto di sovranita finanziaria che permette di verificare personalmente le proprie transazioni
- Il protocollo gossip permette la propagazione delle informazioni in modo decentralizzato, senza server centrali
- Ogni nodo aggiuntivo rafforza la resilienza, la decentralizzazione e la sicurezza dell'intera rete Bitcoin

## Domande di riflessione
1. Se i minatori decidessero collettivamente di modificare il limite dei 21 milioni di bitcoin, perche questa modifica non avrebbe successo?
2. Quali sono i compromessi pratici tra gestire un nodo completo e utilizzare un nodo leggero sul proprio smartphone?
3. In che modo la struttura peer-to-peer e il protocollo gossip rendono Bitcoin resistente alla censura governativa?
