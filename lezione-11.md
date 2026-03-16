# Lezione 11 — Wallet: tipologie (hot, cold, hardware, paper)

## Obiettivi della lezione
- Comprendere che un wallet non contiene bitcoin, ma custodisce le chiavi private
- Distinguere tra wallet hot (caldi) e cold (freddi)
- Conoscere le principali tipologie: mobile, desktop, web, hardware e paper wallet
- Valutare vantaggi e svantaggi di ciascuna soluzione in base alle proprie esigenze

## Che cos'e davvero un wallet?

Il termine "wallet" (portafoglio) e fuorviante. Un wallet Bitcoin non contiene monete digitali, cosi come un portafoglio fisico contiene banconote. I bitcoin esistono esclusivamente sulla blockchain, registrati come output di transazioni non spesi (UTXO). Cio che il wallet custodisce sono le **chiavi private**: stringhe crittografiche che dimostrano la proprieta dei fondi e permettono di autorizzare le transazioni.

Ogni wallet genera una coppia di chiavi: una **chiave privata**, che deve rimanere segreta, e una **chiave pubblica**, da cui derivano gli indirizzi Bitcoin che possiamo condividere per ricevere pagamenti. Chi possiede la chiave privata controlla i fondi associati. Da qui il celebre motto della comunita Bitcoin: "Not your keys, not your coins" (non le tue chiavi, non i tuoi bitcoin).

## Hot wallet: sempre connessi

I wallet "hot" (caldi) sono quelli collegati a Internet. Offrono praticita e velocita di utilizzo, ma presentano una superficie di attacco maggiore rispetto alle soluzioni offline.

### Wallet mobile

Sono applicazioni installate sullo smartphone, come Blue Wallet, Blockstream Green o Muun. Rappresentano la scelta piu comune per chi inizia, perche permettono di inviare e ricevere bitcoin con la stessa facilita con cui si usa un'app di messaggistica. La maggior parte supporta la scansione di codici QR e offre un'interfaccia intuitiva. Il rischio principale e legato alla sicurezza del dispositivo: se il telefono viene compromesso, rubato o danneggiato, i fondi possono essere a rischio.

### Wallet desktop

Sono programmi installati sul computer, come Sparrow Wallet o Electrum. Offrono funzionalita piu avanzate rispetto ai wallet mobile, tra cui la gestione dettagliata delle UTXO, il coin control e il supporto per configurazioni multifirma. Sono apprezzati dagli utenti intermedi che desiderano maggiore controllo sulle proprie transazioni. La sicurezza dipende dalla protezione del computer: malware, keylogger e accessi non autorizzati rappresentano le minacce principali.

### Wallet web

Sono accessibili tramite browser, senza installare alcun software. Molti exchange offrono wallet web integrati. Questa tipologia e la meno sicura per la custodia a lungo termine, perche le chiavi private possono essere gestite da terzi (custodia delegata) oppure esposte ad attacchi informatici come il phishing. Il loro utilizzo dovrebbe essere limitato a piccole somme e operazioni rapide.

## Cold wallet: la sicurezza offline

I wallet "cold" (freddi) mantengono le chiavi private completamente offline, eliminando il rischio di attacchi informatici da remoto. Sono la soluzione consigliata per conservare quantita significative di bitcoin a lungo termine.

### Hardware wallet

Gli hardware wallet sono dispositivi fisici dedicati alla firma delle transazioni in un ambiente isolato. I modelli piu noti sono **Ledger** (Nano S Plus, Nano X), **Trezor** (Model One, Model T, Safe 3) e **ColdCard** (particolarmente apprezzato dai bitcoiner per la sua filosofia open source e Bitcoin-only).

Il funzionamento e semplice: il dispositivo genera e conserva le chiavi private al suo interno, senza mai esporle al computer o allo smartphone. Quando si vuole effettuare una transazione, questa viene creata sul software companion (ad esempio Sparrow Wallet o Ledger Live), inviata al dispositivo hardware per la firma e poi trasmessa alla rete. Le chiavi private non lasciano mai il dispositivo.

I vantaggi sono notevoli: resistenza a malware, protezione tramite PIN, verifica fisica delle transazioni sullo schermo del dispositivo. Il costo varia generalmente tra i 60 e i 200 euro, un investimento ragionevole per proteggere i propri risparmi.

### Paper wallet

Un paper wallet e semplicemente la chiave privata (o la seed phrase) stampata o scritta su un foglio di carta. In passato era considerato un metodo valido di conservazione a freddo, ma oggi e largamente sconsigliato. I motivi sono molteplici: la carta si degrada nel tempo, puo bruciare o bagnarsi, la generazione sicura richiede competenze tecniche specifiche e la spesa parziale dei fondi e complessa e soggetta a errori. Gli hardware wallet hanno reso i paper wallet sostanzialmente obsoleti.

## Come scegliere il wallet giusto

La scelta del wallet dipende da tre fattori principali: la quantita di bitcoin da custodire, la frequenza di utilizzo e il livello di competenza tecnica.

Per le **piccole somme** e l'uso quotidiano, un wallet mobile rappresenta la scelta migliore. Pensate a questo come al contante nel portafoglio fisico: portate con voi solo cio che vi serve per le spese correnti.

Per i **risparmi a medio e lungo termine**, un hardware wallet e fortemente consigliato. E l'equivalente di una cassaforte domestica: richiede uno sforzo iniziale per la configurazione, ma offre un livello di sicurezza molto superiore.

Per **importi significativi**, gli utenti avanzati possono considerare configurazioni multifirma, che richiedono piu dispositivi per autorizzare una transazione, eliminando il singolo punto di vulnerabilita.

Un approccio comune e quello di utilizzare piu wallet contemporaneamente: un wallet mobile per le spese quotidiane e un hardware wallet per il risparmio. Questa strategia bilancia praticita e sicurezza.

## Concetti chiave
- Un wallet Bitcoin custodisce le chiavi private, non i bitcoin stessi: i fondi esistono sulla blockchain
- I wallet hot (mobile, desktop, web) sono comodi ma esposti ai rischi della connessione a Internet
- I wallet cold (hardware, paper) mantengono le chiavi offline, garantendo maggiore sicurezza
- Gli hardware wallet come Ledger, Trezor e ColdCard sono la soluzione raccomandata per la custodia a lungo termine
- I paper wallet sono ormai considerati obsoleti e sconsigliati
- La strategia migliore combina piu wallet: uno hot per l'uso quotidiano e uno cold per il risparmio

## Domande di riflessione
1. Perche e importante capire che un wallet non "contiene" bitcoin? In che modo questa comprensione cambia il tuo approccio alla sicurezza?
2. Quale combinazione di wallet sarebbe piu adatta alle tue esigenze attuali, e come potrebbe evolversi nel tempo?
3. Quali rischi specifici comporta lasciare i propri bitcoin su un wallet web di un exchange, e perche molti esperti lo sconsigliano?
