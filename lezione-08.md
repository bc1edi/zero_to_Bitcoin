# Lezione 8 — Mining e Proof of Work -- chi valida cosa

## Obiettivi della lezione
- Comprendere il ruolo dei minatori nella rete Bitcoin e cosa fanno concretamente
- Spiegare il puzzle crittografico della Proof of Work e come funziona la ricerca dell'hash
- Analizzare il meccanismo di aggiustamento della difficolta e la sua importanza
- Capire perche il dispendio energetico non e uno spreco ma una garanzia di sicurezza

## Cosa fanno i minatori

I minatori sono i partecipanti alla rete Bitcoin che svolgono il lavoro computazionale necessario per aggiungere nuovi blocchi alla blockchain. Il termine "mining" (estrazione mineraria) e una metafora: cosi come i cercatori d'oro spendono energia e risorse per estrarre oro dalla terra, i minatori di Bitcoin spendono energia computazionale per "estrarre" nuovi bitcoin.

In concreto, un minatore svolge queste operazioni: raccoglie le transazioni non confermate dalla mempool, le organizza in un blocco candidato, costruisce l'intestazione del blocco con tutti i dati necessari e poi inizia a cercare una soluzione al puzzle crittografico della Proof of Work. Il primo minatore che trova una soluzione valida trasmette il blocco alla rete, che lo verifica e lo aggiunge alla catena.

Il minatore vincente riceve due forme di compenso: la **ricompensa di blocco** (block subsidy), ovvero nuovi bitcoin appena creati dal protocollo, e le **commissioni** (fee) di tutte le transazioni incluse nel blocco. Questa struttura di incentivi e il cuore del meccanismo che rende Bitcoin sicuro e funzionante senza un'autorita centrale.

## Il puzzle crittografico: trovare un hash sotto il target

Il puzzle che i minatori devono risolvere e concettualmente semplice ma computazionalmente intenso. L'obiettivo e trovare un valore -- il **nonce** -- che, combinato con gli altri dati dell'intestazione del blocco e passato attraverso la funzione hash SHA-256, produca un hash che sia numericamente inferiore a un valore prestabilito chiamato **target**.

In termini pratici, il minatore prende l'intestazione del blocco, inserisce un nonce (un numero arbitrario), calcola l'hash SHA-256 e verifica se il risultato inizia con un numero sufficiente di zeri. Se l'hash non soddisfa il requisito, il minatore incrementa il nonce e riprova. Questo processo viene ripetuto miliardi di volte al secondo.

Non esiste alcuna scorciatoia per trovare la soluzione. La natura della funzione hash SHA-256 rende impossibile prevedere quale input produrra un determinato output. L'unica strategia e la **forza bruta**: provare un numero enorme di combinazioni finche non se ne trova una che funziona. E come cercare di lanciare un dado con miliardi di facce e ottenere un numero inferiore a un certo valore: piu tentativi fai, piu probabilita hai di riuscirci.

Quando un minatore trova un nonce che produce un hash valido, la verifica da parte degli altri nodi della rete e istantanea: basta calcolare un singolo hash per confermare che la soluzione e corretta. Questa asimmetria -- trovare la soluzione e estremamente difficile, verificarla e immediato -- e una proprieta fondamentale della Proof of Work.

## L'aggiustamento della difficolta

La rete Bitcoin e progettata per produrre un nuovo blocco in media ogni 10 minuti. Ma se piu minatori si uniscono alla rete con hardware piu potente, i blocchi verrebbero trovati piu velocemente. Se i minatori abbandonano la rete, i blocchi verrebbero trovati piu lentamente. Per mantenere l'intervallo di 10 minuti costante, Bitcoin utilizza un meccanismo automatico di **aggiustamento della difficolta**.

Ogni **2.016 blocchi** (circa due settimane), il protocollo ricalcola il target di difficolta. Se i 2.016 blocchi precedenti sono stati trovati in meno di due settimane, la difficolta aumenta, rendendo il puzzle piu arduo. Se sono stati trovati in piu di due settimane, la difficolta diminuisce, rendendo il puzzle piu facile. L'aggiustamento massimo per singolo periodo e di un fattore 4 in entrambe le direzioni.

Questo meccanismo e uno degli elementi piu eleganti del design di Bitcoin. Garantisce che, indipendentemente da quanta potenza computazionale venga aggiunta o rimossa dalla rete, la produzione di blocchi -- e quindi l'emissione di nuovi bitcoin -- proceda a un ritmo prevedibile e costante. Nessuna quantita di hardware aggiuntivo puo accelerare la creazione di bitcoin: un principio che lo distingue radicalmente dall'oro, dove una tecnologia di estrazione migliore produce effettivamente piu oro.

## La ricompensa di blocco

Quando un minatore trova un blocco valido, il protocollo gli permette di creare una transazione speciale -- la **transazione coinbase** -- che genera nuovi bitcoin dal nulla. Questa e l'unica modalita con cui nuovi bitcoin entrano in circolazione.

La ricompensa di blocco e composta da due parti: il **sussidio** (subsidy) e le **commissioni** (fee). Il sussidio e la parte di nuovi bitcoin creati, che si dimezza ogni 210.000 blocchi (circa ogni quattro anni) in un evento noto come halving. Le commissioni sono la somma di tutte le fee pagate dagli utenti le cui transazioni sono state incluse nel blocco.

Inizialmente, il sussidio era di 50 BTC per blocco. Dopo il primo halving nel 2012 e sceso a 25, poi a 12,5 nel 2016, a 6,25 nel 2020 e a 3,125 nel 2024. Man mano che il sussidio diminuisce, le commissioni assumeranno un ruolo sempre piu importante nel compensare i minatori e nel garantire la sicurezza della rete.

## Il dispendio energetico come garanzia di sicurezza

Una delle critiche piu frequenti a Bitcoin riguarda il suo consumo energetico. Tuttavia, e fondamentale comprendere che questo dispendio non e un difetto del sistema ma la sua caratteristica di sicurezza principale.

L'energia spesa nel mining rappresenta un **costo reale e irreversibile** che protegge la blockchain. Per attaccare la rete e riscrivere la storia delle transazioni, un malintenzionato dovrebbe spendere almeno la stessa quantita di energia gia investita dalla rete onesta -- e continuare a superarla. Questo rende l'attacco non solo tecnicamente difficile ma anche economicamente irrazionale: il costo dell'attacco supererebbe di gran lunga qualsiasi beneficio ottenibile.

In altre parole, la sicurezza di Bitcoin e **ancorata al mondo fisico** attraverso il consumo di energia. Non e basata sulla fiducia in un'istituzione, sulla reputazione di un'azienda o sulla promessa di un governo, ma sulle leggi della termodinamica. L'energia spesa non puo essere falsificata, simulata o stampata dal nulla -- esattamente come Bitcoin stesso.

E utile anche notare che una percentuale crescente del mining di Bitcoin utilizza fonti di energia rinnovabile o energia altrimenti sprecata, come il gas naturale che verrebbe bruciato in torcia (flaring) nei siti di estrazione petrolifera.

## Concetti chiave
- I minatori competono per trovare un nonce che produca un hash inferiore al target di difficolta, un processo che richiede miliardi di tentativi
- Trovare la soluzione e estremamente difficile, ma verificarla e istantaneo: questa asimmetria e il fondamento della Proof of Work
- La difficolta si aggiusta automaticamente ogni 2.016 blocchi per mantenere un tempo medio di 10 minuti tra i blocchi
- La ricompensa del minatore e composta dal sussidio (nuovi bitcoin) e dalle commissioni delle transazioni incluse nel blocco
- Il consumo energetico del mining non e uno spreco ma la garanzia di sicurezza fondamentale della rete, ancorata alle leggi della fisica
- Nessuna quantita di potenza computazionale aggiuntiva puo accelerare la produzione di bitcoin, grazie al meccanismo di aggiustamento della difficolta

## Domande di riflessione
1. Perche l'asimmetria tra la difficolta di trovare una soluzione e la facilita di verificarla e essenziale per il funzionamento di Bitcoin?
2. In che modo il meccanismo di aggiustamento della difficolta rende Bitcoin diverso dall'oro in termini di prevedibilita dell'offerta?
3. Come risponderesti a qualcuno che sostiene che il consumo energetico di Bitcoin e uno "spreco"?
