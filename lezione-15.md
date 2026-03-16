# Lezione 15 — Sicurezza base: seed phrase, backup, errori comuni

## Obiettivi della lezione
- Comprendere in profondita cos'e una seed phrase e perche rappresenta il cuore della sicurezza in Bitcoin
- Apprendere le migliori pratiche per la conservazione sicura del backup
- Riconoscere gli errori piu comuni che portano alla perdita di fondi
- Identificare le minacce di ingegneria sociale e phishing rivolte ai possessori di bitcoin

## La seed phrase: il fondamento della sicurezza

La seed phrase, definita dallo standard **BIP39** (Bitcoin Improvement Proposal 39), e una sequenza ordinata di parole selezionate da un dizionario di 2048 termini inglesi. Questa sequenza codifica in forma leggibile dall'uomo l'entropia crittografica necessaria per generare tutte le chiavi private del vostro wallet.

### Perche 12 o 24 parole

Una seed phrase di **12 parole** corrisponde a 128 bit di entropia, mentre una di **24 parole** corrisponde a 256 bit. Per dare un'idea della sicurezza che questi numeri rappresentano: il numero di combinazioni possibili per una seed di 12 parole e circa 2 elevato alla 128, un numero con 39 cifre. Nessun computer esistente o immaginabile nel prossimo futuro potrebbe esplorare tutte le combinazioni in tempo utile.

La scelta tra 12 e 24 parole dipende dal livello di sicurezza desiderato. Per la stragrande maggioranza degli utenti, 12 parole offrono gia un margine di sicurezza enormemente superiore a qualsiasi sistema tradizionale. Le 24 parole sono preferite per la custodia di importi molto elevati o in configurazioni istituzionali.

### Come viene generata

La seed phrase viene generata dal wallet utilizzando un **generatore di numeri casuali crittograficamente sicuro**. L'ultima parola include un checksum che permette di verificare la correttezza della sequenza. Non inventate mai una seed phrase da soli: la mente umana non e capace di produrre casualita sufficiente, e una seed prevedibile metterebbe a rischio i vostri fondi.

## Conservare la seed phrase in sicurezza

La conservazione della seed phrase e il compito piu importante per qualsiasi possessore di bitcoin. Le parole devono essere protette da due minacce opposte: la **perdita** (non poter piu accedere ai fondi) e il **furto** (qualcun altro accede ai fondi).

### Supporti fisici resistenti

La carta e il supporto piu immediato, ma e vulnerabile ad acqua, fuoco e deterioramento nel tempo. Per una protezione superiore, esistono **piastre metalliche** specificamente progettate per incidere o stampare la seed phrase. Prodotti come Cryptosteel, Billfodl o simili sono realizzati in acciaio inossidabile e resistono a temperature superiori ai 1000 gradi, all'acqua e alla corrosione.

### Copie multiple in luoghi diversi

Conservare una singola copia della seed phrase crea un **singolo punto di vulnerabilita**: un incendio, un'alluvione o un furto eliminerebbero l'unico accesso ai vostri fondi. La strategia consigliata prevede almeno **due copie** conservate in luoghi fisicamente separati. Ad esempio, una nella propria abitazione e una presso un familiare di fiducia, in una cassetta di sicurezza bancaria o in un altro luogo protetto.

Per importi significativi, gli utenti avanzati possono considerare schemi di condivisione come **Shamir's Secret Sharing**, che suddivide la seed in piu parti di cui ne serve solo un sottoinsieme per il recupero. Tuttavia, questa tecnica aggiunge complessita e non e consigliata ai principianti.

## Errori comuni che portano alla perdita di fondi

### Screenshot e foto della seed phrase

Fotografare la seed phrase con lo smartphone e uno degli errori piu diffusi e pericolosi. Le foto vengono automaticamente sincronizzate con servizi cloud come iCloud o Google Photos, esponendo la seed phrase a violazioni di dati, accessi non autorizzati e sorveglianza. Un singolo malware sul telefono potrebbe accedere alla galleria fotografica e compromettere i vostri fondi.

### Conservazione in servizi cloud

Salvare la seed phrase in file di testo, note digitali, email o documenti su Google Drive, Dropbox o servizi simili e altrettanto rischioso. Questi servizi sono bersagli costanti di attacchi informatici e i vostri dati sono accessibili ai dipendenti dell'azienda e, potenzialmente, a soggetti governativi.

### Singolo punto di vulnerabilita

Conservare l'unica copia della seed phrase nello stesso luogo del wallet hardware significa che un singolo evento avverso (furto, incendio, alluvione) puo causare la perdita completa e irrecuperabile dei fondi.

### Condivisione con terzi

Nessun servizio legittimo vi chiedera mai la vostra seed phrase. Nessun operatore di assistenza clienti, nessun aggiornamento software, nessuna procedura di sicurezza richiede le vostre 12 o 24 parole. Chiunque le chieda sta tentando di rubare i vostri fondi.

## Attacchi di ingegneria sociale e phishing

I possessori di bitcoin sono bersagli di attacchi sofisticati che sfruttano la psicologia umana piuttosto che vulnerabilita tecniche.

### Phishing mirato

Email o messaggi che imitano comunicazioni ufficiali di produttori di hardware wallet o exchange, chiedendo di "verificare" la seed phrase su un sito web contraffatto. Questi siti sono copie visivamente identiche a quelli originali ma controllati dagli attaccanti.

### Finti servizi di supporto

Truffatori si presentano come operatori di assistenza tecnica su social media, forum o gruppi Telegram, offrendo aiuto per problemi con il wallet e chiedendo la seed phrase per "risolvere" il problema.

### Attacchi fisici

Per importi elevati, esiste il rischio di coercizione fisica (il cosiddetto "attacco con chiave inglese da 5 dollari"). Per questo motivo, e prudente non rivelare pubblicamente la quantita di bitcoin in proprio possesso e considerare l'uso di wallet con **passphrase aggiuntiva** (la cosiddetta "25esima parola"), che permette di creare un wallet nascosto di emergenza.

## Concetti chiave
- La seed phrase BIP39 e una sequenza di 12 o 24 parole che codifica le chiavi private del wallet
- La seed non deve mai essere digitalizzata: niente foto, screenshot, file di testo o servizi cloud
- Le piastre metalliche offrono la protezione fisica piu resistente per la conservazione a lungo termine
- Conservare almeno due copie in luoghi fisicamente separati elimina il singolo punto di vulnerabilita
- Nessun servizio legittimo chiedera mai la vostra seed phrase: qualsiasi richiesta e un tentativo di truffa
- La discrezione sulla quantita di bitcoin posseduti e una misura di sicurezza spesso sottovalutata

## Domande di riflessione
1. Analizzando le vostre abitudini digitali attuali, quali rischi identificate per la conservazione di una seed phrase?
2. Come bilancereste la necessita di accessibilita (poter recuperare la seed in caso di emergenza) con quella di sicurezza (impedire che altri vi accedano)?
3. Perche la sicurezza in Bitcoin richiede un cambiamento di mentalita rispetto ai sistemi bancari tradizionali, dove una password dimenticata puo essere recuperata?
