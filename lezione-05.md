# Lezione 5 — Bitcoin vs sistema bancario tradizionale

## Obiettivi della lezione
- Comprendere il funzionamento del sistema bancario a riserva frazionaria e le sue implicazioni
- Analizzare le inefficienze del sistema di pagamenti tradizionale (tempi, costi, intermediari)
- Identificare i rischi di censura, confisca e controparte nel sistema bancario convenzionale
- Confrontare sistematicamente ogni aspetto con l'approccio proposto da Bitcoin

## La riserva frazionaria: le banche non hanno i tuoi soldi

Uno degli aspetti meno compresi del sistema bancario moderno e il meccanismo della **riserva frazionaria**. Quando depositi 1.000 euro in banca, la banca non li custodisce in una cassaforte in attesa che tu li richieda. La banca e autorizzata a prestare la maggior parte di quel denaro ad altri clienti, trattenendo solo una piccola frazione come riserva -- tipicamente tra l'1% e il 10%, a seconda delle normative vigenti.

Questo significa che se tutti i correntisti di una banca si presentassero contemporaneamente per ritirare i propri depositi, la banca non sarebbe in grado di soddisfare le richieste. Questo scenario, noto come **corsa agli sportelli** (bank run), non e un'ipotesi teorica: e accaduto piu volte nella storia, incluso il caso della Silicon Valley Bank nel 2023 e le restrizioni ai prelievi imposte in Grecia nel 2015 e a Cipro nel 2013.

In Bitcoin, ogni satoshi (la piu piccola unita di bitcoin) esiste realmente sulla blockchain. Non c'e nessuna riserva frazionaria, nessun moltiplicatore monetario. Se possiedi 1 bitcoin e controlli le tue chiavi private, quel bitcoin e interamente tuo -- non e un credito verso nessuna istituzione, ma una proprieta digitale verificabile da chiunque.

## Come funzionano i trasferimenti bancari tradizionali

Quando invii un bonifico bancario, il processo e molto piu complesso di quanto appaia. Il denaro non si "muove" realmente: cio che avviene e un aggiornamento coordinato di registri contabili tra diverse istituzioni. Per un trasferimento internazionale, il percorso tipico coinvolge la tua banca, una banca corrispondente nel paese di origine, il sistema SWIFT come rete di messaggistica, una banca corrispondente nel paese di destinazione e infine la banca del destinatario.

Il sistema **SWIFT** (Society for Worldwide Interbank Financial Telecommunication), fondato nel 1973, e la spina dorsale dei pagamenti internazionali. Non trasferisce denaro direttamente, ma invia messaggi standardizzati tra le banche per coordinare il regolamento. Ogni intermediario nella catena aggiunge tempo, costi e potenziali punti di errore.

Con Bitcoin, una transazione avviene direttamente tra il mittente e il destinatario, senza alcun intermediario. Che tu stia inviando valore alla persona seduta accanto a te o a qualcuno dall'altra parte del mondo, il processo e identico: una singola transazione, registrata sulla blockchain, verificabile da tutti.

## Tempi di regolamento e costi

Un bonifico SEPA all'interno dell'area euro richiede tipicamente uno o due giorni lavorativi per il regolamento finale. Un trasferimento internazionale tramite SWIFT puo richiedere da tre a cinque giorni lavorativi, talvolta di piu se coinvolge valute minori o paesi con sistemi bancari meno sviluppati. Durante i fine settimana e i giorni festivi, il sistema bancario semplicemente non opera.

Le commissioni per un trasferimento internazionale possono variare da 15 a 50 euro o piu, a cui si aggiungono i margini sui tassi di cambio applicati dalle banche intermediarie. Per importi piccoli, le commissioni possono rappresentare una percentuale significativa del trasferimento, rendendo le rimesse dei lavoratori migranti particolarmente costose.

Una transazione Bitcoin viene trasmessa alla rete in pochi secondi e raggiunge il regolamento finale (conferma irreversibile) tipicamente entro un'ora, con sei conferme. Funziona 24 ore su 24, 365 giorni all'anno. Le commissioni dipendono dalla congestione della rete e dalla dimensione della transazione in byte, non dal valore trasferito: inviare un milione di euro costa quanto inviare dieci euro.

## Censura e congelamento dei conti

Nel sistema bancario tradizionale, i tuoi fondi possono essere congelati, sequestrati o limitati per una varieta di ragioni. I governi possono imporre sanzioni, le banche possono chiudere conti in base a politiche interne, e le autorita possono sequestrare fondi sulla base di un sospetto, prima ancora di una condanna. Nel 2022, durante le proteste dei camionisti in Canada, il governo congelo i conti bancari di donatori e partecipanti senza procedimento giudiziario.

Bitcoin e **resistente alla censura** per progettazione. Nessuna autorita puo impedire una transazione valida dall'essere trasmessa alla rete e inclusa in un blocco. Nessuno puo congelare un indirizzo Bitcoin o confiscare fondi senza possedere le chiavi private del proprietario. Questo non significa che Bitcoin sia al di sopra della legge, ma che il controllo dei propri fondi e una prerogativa dell'individuo, non di un'istituzione.

## Il rischio di controparte

Ogni volta che affidi il tuo denaro a una banca, stai assumendo un **rischio di controparte**: il rischio che l'istituzione fallisca, venga compromessa o non onori i propri obblighi. I sistemi di garanzia dei depositi (come il fondo interbancario che copre fino a 100.000 euro nell'UE) mitigano questo rischio, ma non lo eliminano: in caso di crisi sistemica, anche questi fondi di garanzia possono risultare insufficienti.

Bitcoin elimina il rischio di controparte attraverso il principio fondamentale dell'auto-custodia. Quando detieni le tue chiavi private, non stai affidando i tuoi fondi a nessuno. "Not your keys, not your coins" ("non le tue chiavi, non le tue monete") e uno dei motti piu importanti della comunita Bitcoin: se non controlli le chiavi private, non possiedi realmente i tuoi bitcoin.

## Una visione d'insieme

Il sistema bancario tradizionale e stato costruito in un'epoca in cui la fiducia centralizzata era l'unico modello disponibile. Ha servito l'umanita per secoli, ma presenta limitazioni strutturali che diventano sempre piu evidenti nell'era digitale: intermediari che aggiungono costi e ritardi, orari di operativita limitati, esclusione di miliardi di persone senza accesso bancario, rischi di censura e confisca, e il problema fondamentale della riserva frazionaria.

Bitcoin propone un paradigma radicalmente diverso: un sistema aperto, accessibile a chiunque abbia una connessione internet, operativo senza interruzioni, resistente alla censura e privo di rischio di controparte. Non e un miglioramento incrementale del sistema esistente, ma un'architettura completamente nuova per il trasferimento di valore.

## Concetti chiave
- La riserva frazionaria significa che le banche non possiedono realmente tutti i depositi dei clienti, creando un rischio sistemico in caso di corse agli sportelli
- I trasferimenti internazionali passano attraverso molteplici intermediari (sistema SWIFT), con tempi di giorni e costi elevati
- Bitcoin permette transazioni dirette tra le parti, senza intermediari, 24 ore su 24, con regolamento finale in circa un'ora
- Nel sistema tradizionale, i fondi possono essere congelati o sequestrati; Bitcoin e resistente alla censura per progettazione
- Il rischio di controparte e intrinseco al sistema bancario; Bitcoin lo elimina attraverso l'auto-custodia delle chiavi private
- "Not your keys, not your coins" sintetizza il principio fondamentale della sovranita finanziaria in Bitcoin

## Domande di riflessione
1. Se la tua banca permettesse a tutti i clienti di ritirare contemporaneamente i propri depositi, pensi che sarebbe in grado di soddisfare tutte le richieste? Cosa ci dice questo sulla natura del denaro in banca?
2. Pensa a una situazione in cui il congelamento di un conto bancario potrebbe essere giustificato e a una in cui potrebbe rappresentare un abuso di potere. Come bilanceresti sicurezza e liberta?
3. In che modo l'eliminazione degli intermediari nei pagamenti potrebbe beneficiare le persone nei paesi in via di sviluppo o senza accesso al sistema bancario?
