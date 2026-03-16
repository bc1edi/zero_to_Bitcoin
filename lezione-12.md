# Lezione 12 — Creare il tuo primo wallet e ricevere bitcoin

## Obiettivi della lezione
- Configurare un wallet mobile in modo sicuro seguendo una procedura passo-passo
- Comprendere l'importanza della seed phrase e come conservarla correttamente
- Ricevere i primi bitcoin tramite indirizzo o codice QR
- Verificare una transazione ricevuta utilizzando un block explorer

## Scegliere il wallet giusto per iniziare

Per il primo wallet consigliamo un'applicazione mobile semplice e affidabile. Tra le opzioni migliori per un principiante troviamo **Blue Wallet**, disponibile sia per Android che per iOS. Si tratta di un wallet open source, con un'interfaccia chiara e il supporto sia per transazioni on-chain che per Lightning Network. Altre alternative valide includono **Blockstream Green** e **Muun Wallet**.

La scelta di un wallet open source e importante: significa che il codice sorgente e pubblico e verificabile da chiunque, riducendo il rischio di comportamenti nascosti o malevoli. Assicuratevi sempre di scaricare l'applicazione dal sito ufficiale del progetto o dagli store ufficiali (Google Play Store o Apple App Store), verificando che lo sviluppatore corrisponda a quello autentico.

## Procedura di configurazione passo-passo

### Passo 1: Installazione e creazione del wallet

Scaricate Blue Wallet dallo store del vostro dispositivo. All'apertura, l'applicazione vi proporra di creare un nuovo wallet. Selezionate "Aggiungi wallet", assegnate un nome (ad esempio "Il mio primo wallet") e scegliete il tipo "Bitcoin" per le transazioni on-chain. Confermate la creazione.

### Passo 2: La seed phrase, il vostro backup fondamentale

Immediatamente dopo la creazione, il wallet vi mostrera una sequenza di **12 parole** (in alcuni wallet sono 24). Questa e la vostra **seed phrase** (frase seme), anche chiamata frase mnemonica o frase di recupero. Rappresenta l'unico modo per recuperare i vostri fondi se il telefono viene perso, rubato o danneggiato.

Queste parole sono generate secondo lo standard BIP39 e codificano la vostra chiave privata master, da cui derivano tutte le chiavi e gli indirizzi del wallet.

**Come annotare la seed phrase in sicurezza:**

- Scrivete le 12 parole su carta, a mano, nell'ordine esatto indicato
- Utilizzate una penna a inchiostro resistente su carta di buona qualita
- Non fate fotografie, screenshot o copie digitali
- Non inviate le parole via email, messaggio o chat
- Non salvatele in nessun servizio cloud
- Conservate il foglio in un luogo sicuro, protetto da acqua, fuoco e occhi indiscreti
- Considerate di fare una seconda copia da conservare in un luogo diverso

Il wallet vi chiedera di confermare la seed phrase, selezionando le parole nell'ordine corretto. Questo passaggio verifica che abbiate effettivamente annotato la sequenza.

### Passo 3: Impostare la protezione di accesso

Attivate la protezione dell'applicazione con PIN, impronta digitale o riconoscimento facciale. Questo impedisce a chiunque abbia accesso fisico al vostro telefono di aprire il wallet e spendere i fondi. Ricordate pero che questa protezione non sostituisce la seed phrase: e un livello di sicurezza aggiuntivo.

## Ricevere i primi bitcoin

### Generare un indirizzo di ricezione

Per ricevere bitcoin, aprite il wallet e selezionate "Ricevi". L'applicazione generera un **indirizzo Bitcoin** e il corrispondente **codice QR**. Un indirizzo Bitcoin si presenta come una stringa di caratteri alfanumerici, ad esempio: `bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh`.

Un dettaglio importante: i wallet moderni generano un **nuovo indirizzo per ogni transazione**. Questo non e un errore, ma una funzionalita di privacy. Tutti gli indirizzi generati dal vostro wallet rimangono validi e sotto il vostro controllo.

### Condividere l'indirizzo con chi vi invia bitcoin

Potete condividere il vostro indirizzo in due modi: mostrando il codice QR affinche il mittente lo scansioni con il proprio wallet, oppure copiando e incollando la stringa dell'indirizzo. Se copiate l'indirizzo, verificate sempre che corrisponda a quello generato dal wallet: alcuni malware sono progettati per sostituire gli indirizzi nella clipboard.

### La prima ricezione

Quando il mittente invia i bitcoin, la transazione viene trasmessa alla rete. Nel giro di pochi secondi, il vostro wallet mostrera una transazione **in attesa** (non confermata). Dopo circa 10 minuti, quando un blocco contenente la vostra transazione viene minato, vedrete la prima conferma.

## Verificare la transazione su un block explorer

Un **block explorer** e un sito web che permette di consultare tutte le transazioni registrate sulla blockchain di Bitcoin. Il piu popolare e **mempool.space**, un progetto open source che offre una visualizzazione chiara e dettagliata.

Per verificare la vostra transazione, potete cercare il vostro indirizzo o il **TXID** (Transaction ID, l'identificativo univoco della transazione) nella barra di ricerca del block explorer. Vedrete i dettagli della transazione: l'importo, le commissioni pagate, il numero di conferme e il blocco in cui e stata inclusa.

Questa verifica indipendente e un aspetto fondamentale di Bitcoin: non dovete fidarvi di nessun intermediario per confermare che i fondi siano effettivamente arrivati. Potete verificare voi stessi, direttamente sulla blockchain pubblica.

## Primi passi con cautela

Per il vostro primo esperimento, inviate una **piccola somma**. Pochi euro in bitcoin sono sufficienti per familiarizzare con il processo. Provate a ricevere, verificare la transazione sul block explorer e poi inviare una piccola parte a un altro indirizzo. Questa pratica diretta vale piu di qualsiasi lezione teorica.

Ricordate che le transazioni Bitcoin sono **irreversibili**: non esiste un numero verde da chiamare per annullare un invio. Questa caratteristica rende fondamentale verificare sempre gli indirizzi e procedere con attenzione, specialmente quando si maneggiano somme significative.

## Concetti chiave
- La seed phrase di 12 o 24 parole e l'unico backup del vostro wallet: perderla significa perdere i bitcoin per sempre
- La seed phrase non deve mai essere fotografata, salvata digitalmente o condivisa con nessuno
- Ogni wallet genera nuovi indirizzi per ogni ricezione, migliorando la privacy
- Un block explorer come mempool.space permette di verificare in modo indipendente qualsiasi transazione
- E consigliabile iniziare con piccole somme per prendere confidenza con il processo
- Le transazioni Bitcoin sono irreversibili: la cautela e essenziale

## Domande di riflessione
1. Perche la seed phrase non dovrebbe mai essere conservata in formato digitale, nemmeno in un file criptato sul proprio computer?
2. Quale vantaggio offre la possibilita di verificare personalmente una transazione su un block explorer, rispetto a dover attendere la conferma di una banca?
3. Cosa succederebbe ai vostri bitcoin se perdeste sia il telefono che la seed phrase?
