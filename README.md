# NotifyMe
# 1 INTRODUZIONE
# 1.1 Scopo
Analisi preliminare per la progettazione di un sistema che sia
in grado di segnalare ad un operatore alert urgenti in ambiente lavorativo.  

# 1.2 Definizioni, abbreviazioni e sigle
Il sistema viene pensato per un punto vendita della società "Leroy Merlin",
a cui ci si riferirà con il termine "negozio".

Il negozio è diviso in due aree:
- area vendita
- area logistica

Nell'area vendita lavorano i Consiglieri di vendita, da ora "cv".
Indichiamo con il termine "operatore/i" chi lavora nell'area logistica.

L'area vendita è costituita da scaffali organizzati in corsie sui quali è presente della merce. 
La merce è suddivisa tra gli scaffali per famiglie di prodotto, che a loro volta sono raggruppate
in reparti.

I reparti sono 14:
- 01 Edilizia
- 02 Falegnameria
- 03 
- 04 
- 05 Cucine
- 06 Pavimenti e piastrelle
- 07 Sanitari
- 08 Idraulica
- 09 Giardino
- 10 
- 11 
- 12 Decorazione
- 13
- 14 Sistemazione

Ogni cv appartiene ad uno o più reparti.
Ogni cv gestisce la merce del reparto di appartenenza.
Il negozio possiede un programma erp (enerprise resource planning) custom denominato Pixys,
dal quale ogni cv può gestire la merce.

Ogni prodotto disponibile alla vendita è caratterizzato da un nome, un codice "referenza", un codice "ean" e prezzo.

E' sufficiente avere o la referenza o l'ean per poter di identificare univocamente un prodotto.


La merce viene suddivisa in tre tipologie:
* RSS: . Merce ubicata nell'area vendita.
* CS: Command Special. Merce disponibile su ordinazione.
* EM: Emporté Merchandise. Merce ubicata nell'area logistica.

La merce EM e CS è gestita dagli operatori.
La merce RSS è gestita dai cv.

Il negozio permette l'ingresso di clienti nell'area vendita.
Il cliente può prelevare merce dagli scaffali di ogni reparto per poi dirigersi alle casse
ed effettuare il pagamento.

Un cliente può rivolgersi al cv per l'acquisto di merce disponibile solo su ordinazione.
Questo tipo di merce viene registrata in Pyxis come CS.

Il negozio offre, inoltre, il servizio di posa ("posa"): il cv insieme al cliente prepara un
progetto per il lavoro da eseguire per conto del cliente. 
La posa consiste nell'ingaggiare un artigiano specializzato autorizzato dall'azienda che
si occuperà di eseguire i lavori.
Offre il servizio di consegna a domicilio.
Offre la possibilità di far acquistare merce disponibile solo su ordinazione.
In tutti e tre i casi, nel momento in cui il cliente sceglie almeno uno dei tre servizi, viene
creato un ordine cliente (OC), esso è un documento identificato univocamente da un codice numerico.
Ogni OC contiene le seguenti informazioni:
- numero OC
- anagrafica cliente
- referenza, nome, quantità, prezzo e reparto del prodotto
- data di consegna

[screen schermata OC]

Un OC può contenere sia prodotti di tipo CS, EM sia RSS.

Gli OC sono salvati in Pixys e sono visibili sia dai cv che dagli operatori.
Una volta che l'OC è convalidato, quindi che è stato confermato dal cliente. 
Gli operatori si occupano di gestire la merce di ogni OC garantendo la data di consegna indicata nell'OC
ricevendo la merce nell'area logistica e ubicandola nelle apposite zone di stoccaggio.

La merce RSS, che è gestita dai cv, deve essere portata fisicamente nell'area logistica dai cv entro e non oltre la data
di consegna indicata nell'OC






# 2 DOCUMENTO DI DEFINIZIONE DEI REQUISITI
 
Attualmente la scadenza delle RSS viene letta da Pyxis da un operatore.
L'operatore esporta un file excel da pyxis, nel quale sono elencate tutte le linee dei prodotti con le relative scadenze. Il file viene filtrato dall'operatore per reparto e per data di scadenza. L'operatore stampa un foglio per ogni reparto e lo consegna manualmente ai cv con l'obiettivo che i cv portino la merce in logistica il prima possibile.
La nuova applicazione deve ricevere in ingresso lo stesso file excel e permettere di gestire il filtraggio dei dati attraverso un pannello di controllo visibile dal pc dell'operatore addetto alle RSS. Nel pannello di controllo deve essere possibile filtrare per reparto, data di scadenza, ordine alfabetico per ogni dato. Deve essere possibile selezionare reparto per reparto una o più referenza, fare un riepilogo delle referenze selezionate e decidere di o stampare o inviare una notifica a tutti i dispositivi loggati di un determinato reparto. 
La notifica vista dal cv sul proprio smartphone deve poter essere aperta, all'apertura una semplice schermata deve fornire i dati necessari per preparare la merce RSS da portare in magazzino: numero OC, referenza prodotto, ean, prodotto, quantità e data di scadenza.
La notifica non può essere rimossa finchè il cv non ha preso in carico la notifica e portato la merce in logistica. Il cv può eventualmente prendere in carico e annullare la preparazione.
Sul pannello di controllo dell'operatore è presente una schermata con le notifiche pendenti, cioè che sono state inviate, ma che il cv non ha preparato. In questa schermata è possibile annullare la notifica (quindi la notifica viene rimossa dallo smartphone, ma non viene rimossa dall'elenco di prodotti urgenti), oppure confermare l'avvenuta ricezione della merce (quindi la notifica sparisce dallo smartphone del cv e la relativa riga viene tolta dall'elenco di prodotti urgenti) oppure inviare di nuovo la notifica, in modo che il telefono del cv suoni di nuovo.
Non deve essere possibile rimuovere la notifica dal cv. (Sarebbe bello che dopo il tentativo di rimuovere una notifica compaia un toast che dica "non fare il furbo, prepara la merce" o qualcosa di simile).
Il pannello di controllo deve essere disponibile anche da smartphone, solo per gli operatori, in versione ridotta: ovvero deve solo mostrare le notifiche pendenti e i tre bottoni per annullare, confermare o reinviare la notifica.


# 3 ANALISI DEL CONTESTO
# 3.1 Situazione attuale
# 3.2 Limiti della situazione attuale
# 3.3 Obiettivi

# 4 SPECIFICHE FUNZIONALI
# 4.1 Modello delle interfacce funzionali con le applicazioni preesistenti
# 4.2 Descrizione delle classi di utilizzatori
# 4.3 Elenco e descrizione delle funzioni

# 5 SPECIFICHE NON FUNZIONALI

# 6 VINCOLI
# 6.1 Vincoli tecnici
# 6.2 Altri vincoli

# 7 SCENARI/CASI D'USO
