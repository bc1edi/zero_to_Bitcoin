# Lezione 6 — Cos'e una blockchain: blocchi, catena, immutabilita

## Obiettivi della lezione
- Comprendere la struttura interna di un blocco Bitcoin e i suoi componenti
- Capire come i blocchi si collegano tra loro formando una catena sicura e verificabile
- Spiegare perche la blockchain e considerata immutabile e cosa renderebbe necessario per alterarla
- Conoscere i parametri fondamentali della blockchain di Bitcoin: tempo di blocco e dimensione

## Che cos'e un blocco

Immagina la blockchain come un registro contabile, un grande libro mastro. Ogni pagina di questo libro e un **blocco**: un contenitore di dati che raccoglie un gruppo di transazioni avvenute sulla rete Bitcoin in un determinato periodo di tempo. Ma a differenza di un semplice elenco di transazioni, un blocco ha una struttura precisa e sofisticata.

Ogni blocco e composto da due parti principali: l'**intestazione** (header) e il **corpo** (body).

### L'intestazione del blocco

L'intestazione contiene le informazioni critiche che identificano il blocco e lo collegano al resto della catena. I suoi elementi principali sono:

- **Hash del blocco precedente**: un'impronta digitale crittografica del blocco che precede nella catena. Questo e il collegamento che crea la "catena" nella blockchain.
- **Merkle root**: un riassunto crittografico di tutte le transazioni contenute nel blocco, organizzato in una struttura ad albero che permette di verificare l'inclusione di qualsiasi transazione in modo efficiente.
- **Timestamp**: la marcatura temporale che indica approssimativamente quando il blocco e stato creato.
- **Target di difficolta**: il valore che definisce quanto deve essere "difficile" il puzzle crittografico che i minatori devono risolvere.
- **Nonce**: un numero che i minatori modificano ripetutamente nel tentativo di trovare un hash valido. E il cuore del processo di mining.

### Il corpo del blocco

Il corpo contiene l'elenco effettivo delle transazioni. Un blocco Bitcoin puo contenere da una singola transazione (la transazione coinbase che premia il minatore) fino a diverse migliaia di transazioni, a seconda della loro dimensione in byte. La prima transazione in ogni blocco e sempre la **transazione coinbase**, che crea nuovi bitcoin come ricompensa per il minatore che ha trovato il blocco.

## L'hash: l'impronta digitale crittografica

Per comprendere la blockchain, e essenziale capire il concetto di **hash crittografico**. Una funzione hash prende qualsiasi quantita di dati in input e produce un output di lunghezza fissa -- nel caso di Bitcoin, una stringa di 64 caratteri esadecimali generata dall'algoritmo SHA-256.

Le proprieta fondamentali di un hash sono tre. La prima e la **determinismo**: lo stesso input produce sempre lo stesso output. La seconda e l'**irreversibilita**: dall'output e praticamente impossibile risalire all'input. La terza e l'**effetto valanga**: anche la minima modifica all'input produce un output completamente diverso. Cambiare un singolo carattere in un blocco di migliaia di transazioni produce un hash totalmente diverso. Questa proprieta e la chiave dell'immutabilita della blockchain.

## Come i blocchi formano una catena

Ogni blocco contiene nella propria intestazione l'hash del blocco precedente. Questo crea un collegamento crittografico indissolubile tra i blocchi, formando una catena che risale fino al blocco genesi creato da Satoshi Nakamoto il 3 gennaio 2009.

Visualizziamo la struttura in modo schematico. Il Blocco 100 contiene l'hash del Blocco 99 nella sua intestazione. Il Blocco 101 contiene l'hash del Blocco 100. Il Blocco 102 contiene l'hash del Blocco 101. E cosi via.

Questa concatenazione e il meccanismo che trasforma un semplice database in una struttura praticamente inviolabile. Ogni blocco "sigilla" crittograficamente tutti quelli precedenti.

## Perche la blockchain e immutabile

Supponiamo che un attaccante voglia modificare una transazione nel Blocco 100 -- ad esempio, per cancellare un pagamento gia effettuato. Ecco cosa accadrebbe:

Modificando anche un solo byte dei dati nel Blocco 100, l'hash di quel blocco cambierebbe completamente (per l'effetto valanga). Ma l'hash originale del Blocco 100 e registrato nell'intestazione del Blocco 101. Quindi il Blocco 101 risulterebbe invalido, perche conterrebbe un riferimento a un hash che non corrisponde piu. L'attaccante dovrebbe quindi ricalcolare anche il Blocco 101, il che invaliderebbe il Blocco 102, e cosi via fino all'ultimo blocco della catena.

Ogni ricalcolo richiede la stessa enorme quantita di lavoro computazionale (Proof of Work) necessaria per creare il blocco originale. E mentre l'attaccante ricalcola, il resto della rete continua ad aggiungere nuovi blocchi alla catena legittima. Per avere successo, l'attaccante dovrebbe possedere piu del 50% della potenza computazionale dell'intera rete -- il cosiddetto **attacco del 51%** -- un'impresa che, per Bitcoin, richiederebbe investimenti nell'ordine di miliardi di euro e un consumo energetico paragonabile a quello di interi stati.

Questa e la ragione per cui una transazione Bitcoin diventa progressivamente piu sicura con ogni nuovo blocco aggiunto alla catena. Una transazione con sei conferme (sei blocchi successivi) e considerata praticamente irreversibile.

## Tempo di blocco e dimensione

La rete Bitcoin e progettata per produrre un nuovo blocco in media ogni **10 minuti**. Questo intervallo non e fisso ma e una media statistica, mantenuta attraverso un meccanismo di aggiustamento della difficolta che vedremo in dettaglio nella lezione sul mining.

La scelta dei 10 minuti rappresenta un compromesso tra velocita e sicurezza. Un tempo piu breve renderebbe le conferme piu rapide ma aumenterebbe il rischio che piu minatori trovino un blocco quasi simultaneamente, creando biforcazioni temporanee della catena. Un tempo piu lungo offrirebbe maggiore sicurezza ma rallenterebbe eccessivamente le transazioni.

Per quanto riguarda la dimensione, i blocchi Bitcoin hanno un limite massimo di circa **4 megabyte** di peso (introdotto con l'aggiornamento SegWit nel 2017, che ha sostituito il precedente limite di 1 MB con un sistema di "peso" piu flessibile). In pratica, i blocchi contengono tipicamente tra 2.000 e 4.000 transazioni.

Questo limite di dimensione e una scelta progettuale deliberata: blocchi piu grandi permetterebbero piu transazioni per blocco, ma richiederebbero piu risorse per validare e archiviare la blockchain, rendendo piu difficile per gli utenti comuni gestire un nodo completo e rischiando di centralizzare la rete.

## Concetti chiave
- Un blocco Bitcoin e composto da un'intestazione (contenente hash del blocco precedente, merkle root, timestamp, target di difficolta e nonce) e da un corpo (contenente le transazioni)
- La funzione hash SHA-256 produce un'impronta digitale unica e irreversibile; qualsiasi modifica ai dati produce un hash completamente diverso
- I blocchi sono collegati tra loro tramite gli hash, formando una catena crittograficamente sicura fino al blocco genesi
- Modificare un blocco passato richiederebbe il ricalcolo di tutti i blocchi successivi, un'impresa praticamente impossibile grazie alla Proof of Work
- Il tempo medio tra i blocchi e di circa 10 minuti, un compromesso tra velocita e sicurezza
- La dimensione massima del blocco (circa 4 MB di peso) e un compromesso tra capacita transazionale e decentralizzazione della rete

## Domande di riflessione
1. Perche l'effetto valanga della funzione hash e fondamentale per la sicurezza della blockchain?
2. Se potessi modificare il tempo medio tra i blocchi, quali conseguenze avrebbe un intervallo di 1 minuto rispetto ai 10 minuti attuali?
3. In che modo il limite di dimensione dei blocchi protegge la decentralizzazione della rete Bitcoin?
