---
alias: 
tags: 2022-11-13 BD
---

# Libri di testo consigliati
- Fundamental of Database Systems, 7th ed, Elmasri, Navathe
- Data Warehaouse Design, Rizzi, Golfarelli 
big dataL consepts technology and architecture 1st ed balusamy abirami gadomi


# Databases

## ☞ Definizioni di base

Le definizioni di base da sapere sono:

- ==dato==: **insieme di fatti conosciuti, registrati e con un significato**. È detto dato grezzo visto che si suppone che andrò ad elaborarlo, questo dato **sarà poi archiviato**, sarà un **fatto conosciuto** cioè avremo:
  - **eventi con un significato** per un dato tipologia di utenti
  - sorgente che **produce i dati** con una cerca velocità

- ==DataBase==: **raccolta di dati altamente organizzati, intercorrelati e strutturati**. È una struttura con dei collegamenti strutturati tra i dati

- ==DBMS Data Base Managment System==: insieme di **programmi per accedere ai dati e farci delle operazioni** di 4 tipi: creazione, recupero, aggiornamento e cancellazione, ciclo **CRUD**. Ne favorisce anche il mantenimento.

- ==mini-world==: **parte del mondo reale alla quale si riferiscono i dati presi** andando a **limitare la modellazione** in un numero n di concetti

- ==DataBase System==: insieme di DBMS con i dati

- ==astrazione==: **separare i dati dai collegamenti tra le entità per disporle in un modello** senza che esso si occupi di come salvare i dati

- ==modello concettuale==: formato da entità e relaizoni

- ==modello fisico==: definizione dei tipi dato e dove sono **conservati**

- ==controllo della concorrenza==: garantire che tutte le transazioni sono **correttamente eseguite**

- ==recovery==: se la transazione è stata eseguita è stata conservata nel database


## ☞  Tipologie di DB

Esistono molti tipi di DB:

- numerici o testuali
- multimediali
- Geographic Information Systems (GIS)
- Data Warehouses


## ☞  Ciclo di vita del DB

È opportuno vedere un ==concetto di base dei dati==, cioè il loro ciclo di vita. Il più semplice è:

1. **acquisizione** (scattered data)
2. **aggregazione** (integrated data)
3. **analisi** (knowledge)
4. finisce in un **applicazione** che genera dei "log data" che saranno poi acquisiti come scattered data

Da un ==punto di vista computazionale== queste fasi si devono prendere in un altro modo:

1. storage dei data
2. formattazione e pulizia
3. capire cosa dicono i dati
4. se non mi bastano i dati che ho posso integrare dei dati


## ☞  Livelli di un DB

Quando si ha un DB abbiamo 3 livelli da considerare

1. ==fisico==: dove sono **salvati i dati**
2. ==logico==: indica come i dati sono **collegati tra loro**
3. ==view==: **rappresentazione** che sarà diversa per ogni tipo di utente


## ☞  Data Base Managment System

Un DBMS offre l'opportunità di:

- **salvataggio** dei dati
- **definizione** modelli dati
- **manipolazione** dei dati
- **processare** e condividere i dati

Per quanto riguarda l'==interazione con i DB== avremo 2 strumenti:

- ==query==: accede a parti differenti di dati e formula una richiesta
- ==transazioni==: legge dei dati ed aggiorna alcuni valori, salvandoli nel DB


## ☞  Mini-world

Avremo bisogno di ==identificare delle entità==, cioè i **concetti di base** che rappresentano una parte delle cose che inseriremo nel DB relazionale. Poi andremo a ==connettere tra loro le entità==, dette relazioni (==relationships==) (ER), ==ne derivano delle tabelle dette relation==.

Il tutto ==da derivare dai requisiti== e non dall'esperienza personale.

Le tabelle create dalle entità conterranno i dati che ho a disposizione. Saranno divisi in:

- righe (record)
- colonne (attributi)
- celle (dati grezzi)

Si verrà quindi a creare un ==catalogo== con vincoli, tipo di dati e la relazione di appartenenza degli attributi.



#  Database System Concepts and Architecture

## ☞  Definizioni sui modelli

Le definizioni di base da sapere sono:

- ==Data Model==: insieme di **concetti che descrivono struttura, operazioni e vincoli** applicati al DB

- ==Data Model Structure and Constraints==: abbiamo dei **costrutti che definiscono come collegare gli elementi** definiti da: entità, record e tabella

- ==Data Model Operation==: di base (**CRUD**) o definite dall'utente

- ==modello dal concettuale==: di **alto livello** e semantico

- ==modello fisico==: di basso livello, definisce **come i dati sono salvati**

- ==modello implementativo==: usati nel DBMS

- ==modello autodescrivente==: basati su XML


## ☞  Definizioni fondamentali

- ==DataBase schema==: descrizione del database in termini di struttura, tipo dati e vincoli
- ==schema diagram==: **visione rappresentativa** del DB schema

![](Uni/BD/img/schcon.jpeg)

- ==schema construct==: insieme tra **schema e dati** dei DB
- ==database state==: **snapshot** in istante t del DB, si definisce quindi ai suoi contenuti
- ==valid state==: si definisce funzionante se il suo contenuto **soddisfa i vincoli** per quello schema
- ==data dictioraty==: insieme per salvare schema e altre info 


## ☞  Schema

Possiamo avere 3 ==livelli di schema==:

1. **interno (fisico)**: come i dati devono essere salvati e come posso accederci
2. **concettuale**
3. **esterno**: per descrivere le view dell'utente

==Per passare da uno schema ad un altro== ho bisogno di un ==mapping== per capire a cosa corrisponde un elemento. Avremo:

- ==logic data independence==: se voglio **cambiare lo schema concettuale** senza cambiare quello fisico
- ==physical==: devo **cambiare lo schema fisico** senza cambiare quello concettuale


## ☞  Tipologie di DBMS

Possiamo avere più tipologie di DBMS:

- ==centralized==: dove abbiamo tutta l'**elaborazione su un unico nodo**
- ==2-tier==: si specializza in termini di server per ogni blocco di funzionalità che devo offrire
- ==cliets==: per far accedere gli utenti
- ==DBMS server==: per eseguiire query e transazioni tramite API



#  Data Modeling Using the Entity–Relationship (ER) Model

## ☞  Entity-Relationship (ER)

Partendo dal mini-world serve ==capire i requisiti utili==. Bisognerà far gestire, all'applicazione, alcuni dati per poi visualizzarli (requisiti relazionali).

La procedura sarà:

1. acquisizione dei data requirements
2. conversione in un modello concettuale
3. applicazione dell'algoritmo di mapping
4. DBMS si occupa di physics design ed internal schema

in parallelo avremo la ==gestione delle transazioni== del mini-world estraendo i functional requirements per effettuare una functional analysis che genera delle transazioni ad alto livello.

Per la scelta degli elementi avremo:

- ==entità (sostantivi)==: **oggetti o cose specifiche** presenti nel mini-world che bisogna rappresentare
- ==relazioni (verbi)==: **collegano le entità**. Il **grado di tipo** della relazione è il **numero di partecipanti a quella relazione**, identificando quante volte la relazione viene percorsa.

Può:

- essere **ricorsiva** se si riferisce ad una stessa entità
- avere un suo attributo definito dall'azione che sta compiendo
- ==attributi (proprietà)==: **descrittori** per ogni entità
- ==record==: **insieme degli attributi** che si danno ad un entità
- ==dato singolo==: ha un unico valore
- ==dato composto==: dati da un **insieme di più descrittori**, notazione: ...(... , ...)
- ==dato multivalore==: attributi che hanno **n-uple di valori**, notazione: {...}
- ==attributo chiave==: **identificare univocamente tutti i record**. Si può usare anche un'unione tra attributo chiave e un altro attributo
- ==entità debole==: entità che **da sola non può esistere**, quindi dipende da un entità più forte. Le sue relationship saranno deboli anche esse. Questa entità **non ha un attributo chiave** ma ha almeno un **attributo in comune con l'entità forte**.
- ==vincoli==: ci sono dei concetti che fungano da vincoli
    - **impliciti**: come è definito il modello dati (es: non posso avere una lista come valore di un attiributo, allora userò n colonne per quanti sono i possibili numeri di telefono)
    - **espliciti**: aggiunti dal modellista (es: cardinalità min max)
    - **semantici**: vincoli aggiunti dal programmatore che farà l'applicativo sul quale si base il nostro db (es: la psw deve avere un tot di caratteri e non altri)

Piccoli ==accorgimenti da avere==:

- scritto da **sx a dx** e dall'altro verso il basso
- nomi delle **entità al singolare**
- **verbi alla terza persona** e attivi o passi per capire da che parte si deve leggere la relazione
- per la **carcinalità** mi chiedo per un solo elemento quante entità puotrà avere dell'altro a cui è relazionato. Può essere rappresentata tramite:
    - **vincoli di dipendenza esistenziale**: 1:1, 1:N, M:N dove bisogna mettere la cardinalità nel lato opposto
    - **min max**: dico che posso avere da un min a un max di record che percorrono la relazione dando in vincolo di intervallo (sarà di aiuto a chi farà il database quando dovrà gestire un warning)

I database NoSQL saranno esenti da una modellazione così pesante.

Potremmo incombere in ==relazioni di livello più alto== nel caso in cui ci trovassimo a descrivere relazioni con complessità alto. In gnerale ==si cerca di evitare e di farlo con relazioni binarie== per evitare complicazioni nell'implementazione.

![](Uni/BD/img/relazlivalt.jpeg)



#  The Enhanced Entity–Relationship (EER) Model

## ☞  Superclassi e sottoclassi

L'idea è di andare a creare una ==gerarchia==:

![](Uni/BD/img/gerardisg.jpeg)

Per modellarlo mi chiedo quali siano le ==caratteristiche che hanno in comune alcune entità==, allora tutti gli ==attributi in comune vanno nella superclasse==. ==Ogni entità DEVE avere i suoi attributi specifici== ma non ho un attributo chiave dato che viene preso dalla superclasse.


## ☞  Graficazione superclassi e sottoclassi

La graficazione avrà per:

- ==specializzazione diretta==: si ha un segmento 
- ==gerarchia (IS-A)==: si ha un segmento con un nodo con:
	- **d $\to$ disjoint**: NON POSSO avere un'entità che è contemporaneamente due o più sottoentità (**solo una**)
	- **o $\to$ overlap**: posso avere un'entità che è contemporaneamente due o più sottoentità (**almeno una**)
	- **U $\to$ union**: **raggruppa** entità di tipo diverso
	le quali potranno avere ==partecipazioni totali o parziali== che indicano se la superclasse deve o meno scegliere tra le sottoclassi.

![](Uni/BD/img/union.jpeg)

Il motivo della modellazione è la presenza di alcune ==fasi per i sistemi di gestione delle informazioni==:

- studio di fattibilità
- analisi dei requisiti
- modellazione e design
- prototipo (ciclico)
- implementazione

Per i relazionali le fasi sono:

- application requirements
- modello concettuale
- modello logico
- modello fisico


## ☞  Notazioni

Nella creazione del modello usiamo la notazione:

![](Uni/BD/img/notaz.jpeg)

se un ==attributo può avere solo un numero finito di valori== si usa: $$...[... , ...]$$

Se ho bisogno di ==sostituire una connessione logica con un entità== la chiamo: ==reificazione==. La si usa se si ha la ==necessità di creare un entità sulla quale si baseranno altre relationship==. Se sbaglio il verso delle relationship metto una freccia.

![](Uni/BD/img/reifi.jpeg)

conviene usare delle relation con un nome univoco.

## ☞  Terminologia

| termine informale | termine formale |
|---|---|
| table | relation |
| column header | attribute |
| all possible column values | domain |
| row | tuple "<...>" |
| table definition | schema of a relation |
| populated table | state of the relation |


![](Uni/BD/img/termformtab.jpeg)



#  Basic SQL

SQL è un linguaggio che consente di accedere al db in varie modalità ed ==ha la funzione di creare e gestire i db==.

## ☞  Statement - SELECT

Usato per ==recuperare informazioni dal db==. la sua struttura ha 3 clausole (claude):

```sql
SELECT <attribute list>
FROM <table list>
[ WHERE <condition> ]
[ ORDER BY <attribute list> ];
```

Molto utile usare gli ==alias (AS)== per:

- andare a **definire i campi che ci serviranno in modo da dividere gli attributi di una tabella con quelli di un altra**
- **accedere ad una stessa tabella ma con 2 alias diversi** perchè per esempio uno rappresenta l'impiegato e l'altro il supervisore
- **rinominare gli attributi**:

```sql
EMPLOYEE AS E(Fn, Mi, ...)
```

==Keyword== da poter usare:

- **DISTINCT**: restituisce solo valori distinti (diversi) nel set di risultati


## ☞  Statement - WHERE

==Esprime una condizione==, se manca è possibile fare il prodotto cartesiano se si usa:

```sql
SELECT Ssn, Dname
FROM EMPLOYEE, DEPARTMENT
```

Si possono usare delle condizioni di tipo:

- numerico:

```sql
WHERE Dno = 5
```

- pattern matching tra stringhe:

```sql
WHERE Ssn LIKE "yes"
```
se non è un occorrenza esatta usiamo:

- **\\**
- **\_**: indica un solo carattere in una specifica posizione

```sql
WHERE column IN (SELECT Statement)
```

vado a selezionare da Statement gli attributi column

```sql
WHERE column BETWEEN value1 AND value2
```

vado a selezionare i valori tra value1 e value2 gli attributi column


## ☞  Statement - ORDER BY

Per ordinare i risultati con DESC o ASC.


## ☞  Statement - INSERT

Usata per inserire dei nuovi dati nei DB. 


## ☞  Statement - GROUP BY

Usato per raggruppare uno o più attributi in base ad un certo valore.

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
```


## ☞  Statement - HAVING

Usata come un WHERE, quindi filtro, ma usando delle funzioni aggregate

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```


## ☞  Statement - UNION

Usato per combinare il risultato di 2 o più statement SELECT

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;
```


## ☞  Statement - JOIN

Usata per unire più risultati di operazioni disseminate tra più tabelle.

```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
JOIN Customers
ON Orders.CustomerID=Customers.CustomerID;
```


## ☞  Values - NULL

Rappresenta un valore nullo che può dare problemi nel caso di machine learning o raccoglimento di dati.

Usandolo come statement:

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```


## ☞  Function - Aggregate

Eseguono un operazioe su n valori dati e possono essere:

- COUNT
- AVG
- SUM
- MAX
- MIN

```sql
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```


## ☞  Function - Window

- LAG
- LEAD


## ☞  Function - String

- CONCAT
- LEN
- UPPER
- LOWER



#  Distributed Database Concepts

## ☞  Distributed Databases

I dati utilizzati nelle infrastrutture dei big data ==devono essere ACID==. Queste sistemi distribuiti sono ==composte da nodi che collaborano per compiere un task==. In queste infrastrutture andremo a distribuire le risorse sui nodi che cooperano in modo da avere ==ridondanza di dati==.

Esiste una ==relazione logica tra questi database connessi==, ma non tutti i nodi devono essere omogenei quindi possiamo al concetto di ==DISTRIBUTED DBMS== che deve gestire l'avere modelli dati connessi. 

Per quanto riguarda ==le query bisognerà riorganizzarle== per poter gestire i nodi distribuiti.


## ☞  Forme di trasparenza

Abbiamo varie forme di ==trasparenza rispetto all'utente==:

- ==organizzazione dei dati==:
    - local transparency
    - naming transparency
- ==ridondanza==: usata per ridurre la mancanza del servizio
- ==frammentazione dei dati==:
    - **partizione orizzontale**: abbiamo una partizione delle tuple. La struttura dati è la stessa ma cambiano i dati salvati. Sarà completa se siamo in grado attraverso l’operazione di union di riavere la relazione iniziale completa
            
	![](Uni/BD/img/partoriz.jpeg)

    - **partizione verticale**: frammentazione del modello dati attraverso la partizione degli attributi che possono essere dislocati su più nodi


## ☞  Affidabilità e disponibilità

Per poter rispettare affidabilità e disponibilità usiamo la ==ridondanza==.

Eseguiamo una distribuzione dei dati ==per avere la possibilità di scalare i dati in modo orizzontale o verticale== a seconda dell'uso che dobbiamo farne. Parliamo di:

- ==horizzontal scalability==: poter **espandere il numero di nodi** del sistema
- ==vertical scalability==: poter espandere la **capacità di un singolo nodo**
- ==partition tolerance==: il sistema è **capace di operare anche se partizionato**


## ☞  Autonomia

La caratteristica principale della distribuzione è l'==autonomia di ogni nodo rispetto agli altri==, quindi lo deve essere anche il loro contenuto, tenendo conto di:

- ==design autonomy==: rappresenta indipendenza dei modelli dei dati e la **gestione delle transazioni tra i nodi**
- ==communication autonomy==: dà la possibilità di condividere le informazioni
- ==execution autonomy==: mi assicura che posso **eseguire una query**

Il ==vantaggio delle architetture distribuite== è una migliore facilità di sviluppo, disponibilità e performance.


## ☞  Frammenti

I frammenti sono le ==unità logiche dei database== e possono essere:

- ==frammentazione orizzontale==: divide le relazioni in orizzontale (**tuple**)
- ==frammentazione verticale==: divide le relazioni in verticale (**colonne**)
- ==frammentazione orizzontale completa==: se tramite **union** possiamo ricostruire la nostra lezione completamente
- ==frammentazione verticale completa==: usiamo la **join**

Spesso nella ricostruzione di un db possiamo trovare sia frammentazioni verticali che orizzontali, parliamo allora di ==frammentazione dello schema==.

Un DDBMS è in grado di gestire una frammentazione usando un ==ALLOCATION SCHEMA== che ==specifica come i frammenti del db sono distribuiti su quali nodi==.

Quando abbiamo dei dati possiamo avere la necessità di ridondanza. Questo non è il metodo migliore per chi si occupa di ==grandi moli di dati==, infatti bisognerà fare delle ==repliche a caldo che ogni tempo t== su un altro sito. In questi casi ==ci viene in soccorso il database journal== che ==tiene traccia dei log/modifiche== fatte al db, andando a prevenire eventuali errori dato che si potrà accedere ad una versione immediatamente precedente dei dati.

Potremo avere delle ==repliche totali o parziali==, replicando struttura e dati a secondo dello schema di replica presente del DDBMS.


## ☞  DDBMS

Potrebbero esserci dei problemi:

- eccessive copie dei dati
- ==two phase commit==: dove un nodo quando ne aggiorna un altro ha la possibilità che fallisca e gli sia mandato un ACK -1, in questo casi bisognerà rincominciare tutto dall'inizio

Nella gestione delle ridondanza si utilizza un ==sito primario== che può essere sostituito, nel caso di malfunzionamenti, da uno secondario, andando a ==gestire le tabelle in modo parallelo==. Per capire chi sarà il nuovo responsabile del locking si usa un ==sistema a voto==. 

Quando noi ==eseguiamo una query in ambiente distribuito== possiamo usare il:

- ==query mapping==: per capire **quali dati vengono utilizzati** dalla query e **dove si trovano** sui vari frammenti eseguendo quindi una **mappatura**. Successivamente **esegue la query in modo decentralizzato**

Da notare che il DDBMS permette l’==ottimizzazione delle query==, indicano i valori più richiesti su un database. Per esempio l'utilizzo di indici sulle chiavi primarie ed ereditate per velocizzare il processo della query.

Per riuscire a ==ridurre la quantità di dati che devo trasmettere==, usiamo un costrutto particolare: ==semi-join== che ==riduce il numero di tuple che trasmetto mandando soltanto la colonna di join== e prendendo unicamente i valori che mi vengono dalla join della tabella di partenza. 

Nei DDBMS relazionali sono usati i ==database federati== dove ho un ==modello dati condiviso== da tutti ma i ==singoli nodi dispongono di modelli dati indipendenti==, quindi ogni nodo mantiene uno schema generale che permette di comunicare con gli altri. Abbiamo ==3 dimesioni per il database distribuito==:

- autonomia
- distribuzione
- eterogeneità

![](Uni/BD/img/dimddbms.jpeg)



#  Introduction to Transaction Processing Concepts and Theory

## ☞  Introduzione alle transazioni

Il concetto di transazione è in ==contrapposizione con il concetto di query== dato che:

- query: esecuzione di iscruzioni per ottenere delle informazioni
- ==transazione==: **descrive l'unità di elaborazione del DB** cioè un insieme di query con 2 stadi fissi (inizio e fine)

Ci troveremo in un ==sistema transazionale== se ho 2 ==utenti concorrenti== (multiuser DBMS) che vogliono accedere allo stesso DB. Quindi se avrò dei DB molto ampi, con centinauia di possibili utenti che vogliono accedervi contemporaneamente dovrò avere 2 ==requisiti== prestazionali:

- alta **disponibilità**
- alta **velocità di risposta**

oppure posso usare il ==multiprogramming== consentendo al OS di mandare in esecuzione istruzioni di più processi in parallelo o in interleaved (interlacciato).

![](Uni/BD/img/multiuser.jpeg)

I ==tipi di transazione== che possiamo avere sono in:

- sola lettura
- lettura e scrittura

e possono avvenire su item, record, attributi di un database, o anche su un blocco del disco. Quando si eseguono queste operazioni, i ==buffer vengono salvati nel DBMS== che una volta pieni vengono sostituiti tramite il ==last recently used==. Tutto ciò ==indipendentemente dalla granularità dell'item==, con notazione:

```
operazione_item(x)
```

e chiamaremo:

- **read set**: tutto quello letto in una transazione
- **write set**: tutto quello scritto in una transazione 

![](Uni/BD/img/2trans.jpeg)


## ☞  Problemi durante le transazioni

Possono essere:

- ==lost update==: quando le **esecuzioni della transazione $i$ sono interleaved con la $i+1$**

    ![](Uni/BD/img/lostupdate.jpeg)

    con $T_2$ che legge il valore originale e l'aggiornamento di $T_1$ viene sovrascritto a quello di $T_2$

- ==temporary update (dirty read)==: quando una transazione accede ad un dato e poi fallisce e nello stesso tempo un'altra accede allo stesso dato, questa **continua a leggere il valore della transazione fallista** (dirty data)
    
    ![](Uni/BD/img/dirtyread.jpeg)

- ==incorrect summary==: quando cerco di accedere a dei dati che stanno essendo modificati **leggendo alcuni dati già modificati e altro no**
    
    ![](Uni/BD/img/incsum.jpeg)


- ==unrepeatable read==: quando si effettua una **lettura doppia del dato** ma il **valore della funzione ripetuta** ad intervalli di tempo differenti **è diversa**



## ☞  Le operazioni di una transazione

Possono essere:


- ==BEGIN\_TRANSACTION==: fa iniziare la transazione
- ==READ or WRITE==: operazioni di lettura o scirttura sul DB
- ==END\_TRANSACTION==: segna la fine della transazione e delle operazioni di lettura/scrittura. fa anche un **check sui cambiamente effettuati** come può essere l'interleaved
- ==COMMIT\_TRANSACTION==: segnala una **fine con successo** e l'invio del commit delle transazioni, ottenendo un **commit point** che affiancato all'Id della transazione mi permette di capire queli di queste sono fallite
- ==ROLLBACK==: segnala un **fail della transazione** e quindi la successiva **cancellazione dei cambiamenti**


![](Uni/BD/img/opertrans.jpeg)


## ☞  Proprietà delle transazioni

Le proprietà fondamentali per ogni transazione sono dette ==ACID==:


- ==Atomicity==: dove o **esegui la transazione intera** o non la esegui
- ==Consistency==: quando la transazione termina **non lascia inconsistenza**
- ==Isolation==: dove la transazione **non interferisce** con altre transazioni
- ==Durability/permanency==: dalla transazione devo avere delle **modifiche permamnenti nel DB**



## ☞  Scheduling basato sulla recoverability

Lo scheduling ==contiente==:


- **ordine di esecuzione delle operazioni** da tutte le transazioni
- operazioni di **transazioni diverse**


Potremo avere due ==operazioni in conflitto== se:


- appartengono a **transazioni diverse**
- accedono allo **stesso elemento $X$**
- ha un'operazione di **write**




## ☞  La serializzazione

È importante perché ==non permette l'interleaved== tra le transazioni, eliminando i problemi sopra citati. Se presa ==come unica risorsa non è realizzabile==, allora ci si chiede quali siano le schcedulazioni che si posso serializzare (solo $n$ transazioni).








#  NOSQL (Not Only SQL)


## ☞  Introduzione

Sono dei ==database distributi== con:


- storage semistrutturato
- alta replicazione dei dati
- alte prestazioni


Non sarà richiesto uno schema ER, e ha come ==tipi==:


- documentali
- chiave valore
- colonnari
- a grafo
- ibridi
- a oggetti
- xml



## ☞  CAP Theorem

Se ho modelli diversi di DB vorrei poter avere ==diversi livelli di consistenza dello stato del DB== e voler forzare la transazione. Allora dovremo avere:


- ==consistenza==: in tutti i DB distribuiti **ciscuna istanza deve fornire gli stessi dati**
- ==disponibilità==: **un fail del nodo master non deve intaccare gli altri**
    ![](Uni/BD/img/masterslave.jpeg)
    
- ==partizione==: il sistema continua a **funzionare nonostante la perdita di messaggi, o problemi di connessione**


Se ho un sistema distribuito ==non possono garatire tutte e 3 le cose==, allora possono essere garantite ==solo 2 alla volta==:

![](Uni/BD/img/cap.jpeg)

tutto questo vale solo se il DB è distribuito.

Le combinaiozni sono:
- CA: non soddisfatta la partition tollerance, cioe1 che quella funzione viene meno per qualche motivo posso allora avere dei piccoli sistemi che non devono indertagire ed altre che dovrebbero non possono. ci sono allora i dbms che in assenza di comunicazione garantiscono consistenza e disponibilita
- CP: non soddisfa la disponibilita1 e quindi se non devo garantire la disponibilita allora ad un isstemsta e1 consetito di non rispondere a tutte le richeiste in lettura e scrittura, in pratica vincola la transazione dato che sacrififcanos la disponibilita nela transazione npn posso leggere i dati 
- AP: perdo la consistenza, quindi all'istante t i pari client possono vedere dati diversi, ogni parte del sistema fa vaedere i dati ai quali ha accesso. Allora non e1 garantito che in qualsiasi istante tutte le aprtizioni grataniscno la stessa vista sugli stessi dati

riportare consequence of cap

l'idea ala base del CAP theorem cdel poter avere solo 2 punti ora come ora e1 meno importante perceh se ho poche partizioni non e1 importante perdere Co A se il sistema non e1 partizionato (cosa che succedeva prika,a) oopure si verifica ceh scegliere tra C e A si verifica piu volte infatti il sistema e1 portato da richieste  tante richeiste dato ceh succede ceh C o A possono essere richieste insieme tante volte per ogni interazione allora bisogna sempre switcahre 


per mettere insieme queste idee inseme: vado a pefinire a priori delle casistiche nele quali una delle 3 caratteristiche viene sacartata (il porgettita lo fa)



BASE: conseguenza del cap teheorem che al posto di vincolarmi ai 3 vertici del triangolo faccio n trade-offe trovo non una perfetta dispoinibilita dei 2 punti ma una buona di base:
basically available:
soft state: dico che volgi oi dati consistenti solo alla fine e non per forza in ogni istante alora devo assicurarmi che al sistema no narrivino altri input qunado sto craeando la consistenza
softstate ????

vedere slide torino

ACID: focus sulla consistenza ...
BASE: alta disponibilita al posto di consistenza assoluto, quindi garantiere scrittura e lettura semrep








non0relational databases for data managment:
dividon in piccole unita le mie strutture dati allora la struttura la conosco in anticipo dato che ho fatto pirma concettuael poi logico e pi i lfiscio 
... slide 5


quidi se volgio garantier ele join tra le trabelle e tle transazioni ho bisogno di un dsistema centralizzato. posso allora pensare a quei casi in cui voglio rilassare alcunidi queti vincoli.

ne rientrano i no qsl

1. tenere in sieme fisiicamente nellastessa partizoini i dati che saranno acceduti insieme
2. garanzia che la lettura sia piu rapida
3. rilassare la resistenza che sara1 locale 
4. il modello dati  dei db puo variare e son o4" chiave valore, documento, colonnale, grafo

dove i pirami 3 sono basati su aggregaione


caratteristiche\;
non mi servono le join
no schemi
garantisce la scalabilita orizzontale


confronto:
ralazionali / non relazionali
- ogni record ha una riga / soluzione diversa per ogni dbms
- sceham predefinito per ognitabela con scambio costoso dato ceh devo fermare tutto / schema dinamico cosi non devo per forza acccedere ai campi per come sono stati srcitti
- scalaboilita verticale: per aumentare le prestazionei del db deviaumetntare le capacita dell'hardware (aumento la potenza dle singolo server / piu volgio aumentare le prestazioni piu aumento i nodi (server) 
- ogniuno ha un suo linguaggio di query / custom query focus sulle collection dei documenti
- serve per dati piatti dove conosco la struttura / per dati gerarchici con file json o xml con un nodo radice e delle diramazioni


relazionane ha tutte le cAP quando lo distribuisco perdo la P(aggiungere su)


pro dei nosql:
- vanno beene per dati semistrutturati o gerarchici
- in quali sistuaizoni: applicazionie online (per i file json ecc)
- se voglio incrementare le prestazione delle query in parallelo ed avere dati ridondanti
- alto livello di accesso concorrente
- molte letture e scritture
- letture e scrittura consistenti

contro:
- a linelo di transazioni consistenza non sepre garantita
- datio denjormalizzati, cioe collegati con piu colegamenti tra loro, allora dobbiamo accedere a piu dati rispetto al ralzzionale
- no chiavi esterne
- caso di aggiornamento di molti dati questo sara molto lento (scrievere o modificatre dati quindi) e serve piu stazio fisico + 10/50 volte del relazionele
- se decido di cambiare la struttura non riesco a tracciarli facilemte dato ceh no c'e il cpncetto di schema


si usa perche1 
1. le grandi software house le usano
2. in alcunie situaizoni il vantaggio e1 oggettivo : in quelle in cui posso sfruttare
- buona scalabilit (piu server)
- gestire scehmi diversi
- leggere rapidamente(azioni web)
- non serve pompare il server e qindi funzionano anche su hardare anceh che non cosano troppo


challeges of nosql:
1. tecnologia non troppo matura dato che esiset da -20 anni
2. no supporto all'utenza ma ci son ole community
3. a parte di amministrzione e1 piu difficile 
4. mancano degli standard tra i vari nosql


img slide 23

chiave valore: ad ogni chiave e1 associato un solo valore
cononnale: ad ogni chiave sono associati piu valori, ma le colonne non hanno dei conecetti valori 
documentale: albero binario 
grafo: posso andare ovunquwe infatti e1 orienteato e possiamo decidere se dargli un verso di percorrenza



documentale: si basa sul concetto di aggregazione e basato su un sieme di coppie chiave valore, allora un documento sara un aggrergazione di isatnze di coppie chiave valoreci accedo a queste aggregazioni in base ai campi che ho.
ogni documento e1 un sisnsieme di dati autoconsistente. non ho dati sparpagliati n varie trabelle.


mongodb: CP

gerarchia:

fig slide 21


relational / mongodb
database / database
tavle, view / collection
row /document BSON
comun / field
index / index
join / embedded document
foreing key / reference al documento che server
partition / shard

mongodb -> database instance
mongos -> sharding process

aggreghiamo in una stessa collection dei documenti che per l'implementatore hanno senso

per effettuare delle operazioni:
db.collection_name.operatoion

create operation:
save, update, insert

read operation:
find=SELECT, 