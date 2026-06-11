# 🍣👨‍🍳 Macrobiotics of Macros
Quasiquotation and the Art of Code Assembly: A Culinary Guide to Lisp Metaprogramming 


---


![AST à la carte](https://img.shields.io/badge/AST-à%20la%20carte-brown)
![Lambda Cuisine](https://img.shields.io/badge/λ-cuisine-orange)
![Quasiquote Chef](https://img.shields.io/badge/quasiquote-chef-yellow)
![Curry–Howard Pairing](https://img.shields.io/badge/Curry–Howard-wine%20pairing-red)
![Macrobiotic Macros](https://img.shields.io/badge/macros-macrobiotic-blueviolet)
![Structural Sharing Bistro](https://img.shields.io/badge/structural%20sharing-bistro-brown)



***Buonasera, signore e signori. Sono lo Chef della Programmazione, e stasera vi presento il mio capolavoro, l'Homoicinicity à la Récursive. Prima di servirlo, devo spiegarvi gli ingredienti con precisione formale. Preparatevi, perché questo piatto ha una genealogia che risale ai logici del '36 e si estende fino alle strutture categoriali della teoria dei tipi moderna.*** 


P.S. Nel regno dove il codice è dato e il dato è codice, anche i badge devono essere metaprogrammati.


---
![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-blue)



L'homoiconicity nasce con la logica formale e del lambda calcolo (Church, 1936), quando Alonzo Church dimostrò con il suo sistema formale che ogni computazione poteva essere rappresentata come funzione nel senso di funzione totale su un dominio, e ogni funzione poteva ricevere altre funzioni come argomenti, realizzando così una **stratificazione funzionale di ordine superiore** che rendeva la sintassi della definizione isomorfa alla forma della computazione stessa. Allora fermi, una funzione di ordine superiore è solo una funzione che accetta altre funzioni come input. Comunque Church pubblicò i suoi risultati nella *Annals of Mathematics*, e colui che aveva gettato i fondamenti logici, mediante la dimostrazione della computabilità universale del λ-calcolo, si rese conto solo in seguito che stava descrivendo il principio alla base di quello che sarebbe diventato il piatto più elegante e concettualmente puro della storia della programmazione. Successivamente, McCarthy lesse i lavori di Church e ragionando sulle strutture matematiche sottostanti mediante la teoria degli **S-espressioni** si rese conto che se il codice fosse rappresentato come lista, e se la lista costituisse il tipo di dato primitivo e universale di un linguaggio, il quale avrebbe dovuto possedere una **semantica denotazionale isomorfa alla sua sintassi concreta**, allora il codice stesso diverrebbe dato in senso strettamente letterale e strutturale, abolendo la distinzione categoriale tra fase sintattica e fase semantica. McCarthy prese questa intuizione folgorante e la rese vera nel linguaggio LISP (acronimo di "LISt Processing"), creando così il primo linguaggio homoiconic della storia mediante una semantica costruttiva in cui la valutazione stessa è operazione strutturale su dati S-espressivi, anche se il termine tecnico sarebbe stato coniato per decenni ancora.

Aspetta ma non ho spiegato cosa significa sintassi astratta e concreta, questa è una delle prime cose che si fanno quando si studiano i linguaggi. La sintassi astratta è la struttura interna che il linguaggio utilizza per rappresentare il programma e viene mappata su un albero di sintassi astratta (AST) che cattura la semantica dell'espressione indipendentemente dai dettagli superficiali della notazione, questi dettagli superficiali sono la sintassi concreta che è la forma esteriore del codice, quella che il programmatore digita e che specifica la grammatica del linguaggio. Quando si vede per la prima volta la sintassi astratta, di solito tutti incontrano lo stesso esempio, una calcolatrice in notazione polacca, che poi non è altro che una notazione in cui gli operatori precedono gli operandi. L'esempio più banale è che l'espressione infissa `3 + 2` diventa `+ 3 2`. E sapete perché questa notazione è così potente? Perchè è già, in forma di sintassi astratta. Guardate cosa succede se prendiamo lèAST di `3 + 2` e lo rappresentiamo in ASCII:

```
      (+)
     /   \
   (3)   (2)
```

Un nodo radice che rappresenta lèoperazione, e due figli che rappresentano gli argomenti. Ora, se appiattiamo questo albero leggendo prima la radice e poi i figli da sinistra a destra, otteniamo

```
+ 3 2
```

Cioè la notazione polacca che appunto è la forma lineare più vicina possibile alla struttura dellèalbero. E' per questo che quando si introduce la sintassi concreta e la sintassi astratta si parte da qui e qui si capisce anche quanto fosse radicale lèintuizione di McCarthy. Infatti se la sintassi concreta di un linguaggio non è solo una notazione, ma è già una struttura dati canonica, allora la sintassi astratta non deve essere costruita, perché coincide con ciò che il programmatore scrive. E le S‑espressioni di Lisp trasformano ogni programma in una lista annidata che è contemporaneamente codice e dato, sintassi concreta e sintassi astratta, rappresentazione e struttura semantica, così in Lisp, lèAST è letteralmente ciò che scrivi e non va trasformato da un programma che lo stampa in modo più carino, un PrettyPrinter appunto.

Detto quensto andiamo alla definizione matematica rigorosa del piatto che sto preparando. Un linguaggio L si dice **homoiconic** se e solo se esiste un **isomorfismo strutturale naturale** tra la sintassi astratta del programma (in senso categoriale di morfismo che preserva composizione e identità) e la sua rappresentazione interna come dato manipolabile in L medesimo, formalizzabile nella seguente maniera: 

**per ogni programma p ∈ Programs(L), esiste un'entità d ∈ Data(L) tale che la forma sintattica concreta di p coincida con la forma strutturale di d senza alcuna trasformazione intermedia e senza fasi nascoste di parsing o compilazione simbolica**.

Inoltre, per ogni operazione strutturale op : Data(L) → Data(L) nel reticolo delle operazioni su dati, esiste una corrispondente sequenza di riduzioni β (nel senso del λ-calcolo) che produce il medesimo risultato. In notazione di teoria dei tipi e teoria delle categorie: **Code ≅ Data**, dove l'isomorfismo ≅ denota un'equivalenza strutturale tra categorie **C_Code** e **C_Data**, e così abbiamo che le categorie matematiche di "codice" e "dato" in realtà sono la stessa cosa vista da angolazioni categorialmente distinte modulo un funtore covariante naturale. Questa equivalenza implica l'esistenza di **functori naturali biaggiunti** che preservano la composizione e l'identità a tutti i livelli categoriali pertinenti, generando una catena di trasformazioni naturali che connettono la sintassi alle sue riduzioni semantiche. Ma devo fare una pausa, qualcuno potrebbe spaventarsi, cosa significa funtori naturali biaggiunti? È facile anche se sembra un aggettivo uscito da un rituale esoterico... Un funtore è un modo ordinato di tradurre oggetti e frecce da una categoria a un'altra, la naturalità è la garanzia che questa traduzione non dipende da trucchi locali o scelte arbitrarie, ma rispetta la struttura globale e l'aggiunzione è la condizione per cui ogni mappa da un lato corrisponde in modo canonico a una mappa dall'altro, come se le due categorie fossero due lingue diverse che però condividono la stessa grammatica profonda. Dire che sono biaggiunti significa che questa corrispondenza funziona in entrambe le direzioni, senza perdita di informazione e senza ambiguità, come un dizionario perfetto che traduce avanti e indietro senza mai cambiare il significato, se avessi detto isomorfe avrei fatto prima. Ma torniamo a noi, se Code e Data sono categorie collegate da funtori naturali biaggiunti, significa che ogni trasformazione sintattica ha un corrispettivo semantico e ogni trasformazione semantica ha un corrispettivo sintattico. Allora la sintassi è semantica vista da vicino, la semantica è sintassi vista da lontano e questo è quello che McCarthy aveva intuito senza usare il linguaggio della teoria delle categorie.

In LISP, come detto, ogni entità computazionale assume la forma di una **S-expression** (espressione simbolica, termine che McCarthy coniò per mancanza di nomenclatura più idonea), definita ricorsivamente come una S-expression è o un atomo simbolico appartenente all'**algebra di Herbrand** generata da una segnatura infinita di simboli primitivi, oppure una lista ordinata (a₁, a₂, ..., aₙ) di S-expression, dove ogni aᵢ è a sua volta una S-expression o un valore primitivo appartenente ai tipi base del dominio semantico (interi, reali, stringhe, booleani). 

Considerate questa forma: `(+ 1 2)`, una lista composta da tre elementi ordinati—il simbolo `+` (elemento dell'algebra di Herbrand), il numero intero 1, il numero intero 2, è pura struttura dati appartenente al monoide libero generato dai simboli e dai costruttori di lista di Data(LISP) (monoide libero sarebbe più facile, tutti i linguaggi formali sono monoidi liberi, una struttura con unèoperazione binaria associativa e unèunità). Quando l'interprete LISP incontra questa medesima forma, la esegue come istruzione computazionale mediante riduzione β e applicazione di funzioni: "Applica la **valutazione ordinaria** (applicative evaluation) della funzione denotata dal simbolo `+` agli argomenti numerici 1 e 2, producendo il risultato 3 mediante composizione funzionale." La S-expression è contemporaneamente il dato e l'AST, realizzando così concretamente l'identità Code ≅ Data. Questa simultaneità costitutiva è l'homoicinicity.

Ora vi mostro come si cucina con questa proprietà fondamentale con un po' semantica alla piastra... Esiste un operatore linguistico detto **`quote`**, denotato tipograficamente mediante un apice singolo `'`, il quale implementa un meccanismo di sospensione della valutazione (lazy evaluation suspension) e un'elevazione del livello metalinguistico... ok sembra che stia parlando di magia ma è semplice, più o meno, quando scrivo `'(+ 1 2)`, comunico al sistema interpretativo mediante una direttiva sintattica di trattarla come dato strutturale puro, senza sottoporre gli elementi costituenti a riduzione semantica. In questo momento, posseggo una struttura dati che rappresenta il codice `(+ 1 2)`, e ci posso eseguire operazioni di **introspezione sintattica** e **riflessione strutturale**. L'operazione `(first '(+ 1 2))` mi restituisce il simbolo `+` come termine non valutato. l'operazione `(rest '(+ 1 2))` mi restituisce invece la sottolista `(1 2)` come struttura dati manipolabile. L'operazione `(second '(+ 1 2))` estrae l'elemento 1. Sto applicando operazioni standard di manipolazione lista, e quella lista che sto ispezionando *rappresenta il codice stesso*, creando così una stratificazione ricorsiva del metalinguaggio all'interno del linguaggio medesimo.

E esiste il duale perfetto di questo operatore nel contesto della teoria dei funtori aggiunti denominato **`eval`**, il quale realizza l*operazione inversa di sollevamento semantico (semantic lowering), che fa, quando scrivo `(eval '(+ 1 2))`, prendo un dato, una lista strutturale appartenente a Data(LISP), e ordino al sistema di sottoporre questo termine al motore di valutazione ordinaria, trasformandolo da dato a risultato computazionale. Così l'interprete ritorna il valore 3, il risultato dell'applicazione della funzione `+` mediante riduzione β. Ho semplicemente preso il dato, l'ho trasmesso all'interprete tramite un passaggio di controllo tra livelli semantici, e l'interprete ha eseguito il compito che avrebbe eseguito identicamente se avessi scritto `(+ 1 2)` nel codice sorgente stesso. La bellezza teorica consiste nel fatto che `eval` è un'interfaccia verso il meccanismo interpretativo già esistente, una porta verso la dinamica computazionale già intrinseca al sistema, operando una rotazione nel **fibrato semantico** del linguaggio se mi permettete la citazione colta. Quote e eval sono i duali costruttivi e logicamente reciproci della proprietà di homoicinicity, formando una coppia aggiuntiva e una coppia sottrattiva nel senso della teoria delle categorie, dove risultano essere aggiunti sinistri e destri di un funtore di elevazione/abbassamento semantico. Lisp in questa metafora ha una struttura in cui ogni punto sintattico ha una fibra semantica associata, e quote/eval sono le mappe che ti fanno cambiare sezione.

Tuttavia il piatto non è ancora servito nella sua pienezza concettuale e qui arriviamo ai **quasiquote e unquote**, sofisticazioni introdotte negli anni '80 da Bawden e Rees e che elevarono il potere espressivo della manipolazione simbolica parametrica e introdussero una **semantica di quasi-citazione** di straordinaria potenza. Quasiquote, denotato con un backtick `` ` ``, si comporta come quote, con la differenza che introduce buchi strutturali deliberati nel contesto sintattico e permette il calcolo parziale all'interno di strutture dati quasi-quotate. Unquote invece rappresentato una virgola `,` perché a noi piace spigarle bene le cose mica con un simbolo che si fa confusione... comqune dicevo, questo riempie i buchi con valori calcolati dinamicamente mediante riduzione semantica ordinaria, operando una composizione di livelli di astrazione semantica. La quasiquote è semplicemente un template, ci scrivi la forma del codice che vuoi ottenere e la tieni come dato, senza valutarla. Lèunquote (,) è il punto dove invece esegui qualcosa e inserisci il risultato dentro quel template. Lèunquote‑splice (,@) prende una lista risultante e la sparge dentro il template come più elementi. In pratica costruisci lo scheletro del codice e poi, solo nei buchi segnati, cucini e infili i risultati prima di servire. Comqunque, quando scrivo:

```lisp
(let ((op '+)
      (a 5)
      (b 3))
  `(,op ,a ,b))
```

ottengo il valore `(+ 5 3)`, una lista strutturata che rappresenta un'espressione computazionale, costruita mediante valori legati durante l'esecuzione e mediante interpolazione parametrica nel template strutturale. Ho manipolato dati che rappresentano strutturalmente computazione mediante una algebra di generazione di termini guidata dai dati (data-driven term generation). Questo è quello che si chiama metaprogramming strutturale e simbolico. Arriviamo ora al piatto principale della nostra presentazione le macro macrobiotiche, la più potente astrazione nel arsenale LISP e la realizzazione concreta della metaprogrammazione sintattica. Una macro è una **funzione di trasformazione sintattica ricorsiva** che riceve codice non valutato (non ridotto secondo la semantica ordinaria) come dato strutturale di input e ritorna codice (nella forma di S-expression) come output da sottoporre ulteriormente a valutazione secondo le regole del sistema. Il tipo della macro può essere espresso come:

```
macro : (Data(L) × Env(L)) → Code(L)
```

dove Env(L) rappresenta l'ambiente lessicale catturato al momento della definizione, e Code(L) denota il codominio delle S-espressioni sottoposte a riduzione. Quando definisco:

```lisp
(defmacro when (test body)
  `(if ,test (progn ,@body)))
```

e successivamente la invoco come:

```lisp
(when (> x 0)
  (print "positivo")
  (return x))
```

il meccanismo operativo funziona come segue: la macro riceve il dato strutturale non valutato composto da `((> x 0) (print "positivo") (return x))`—il test e il body permangono nello stato di **forma dati pura** senza alcuna riduzione intermedia trasforma questo dato mediante quasiquote e unquote in una nuova lista strutturale generata da parametri, producendo `(if (> x 0) (progn (print "positivo") (return x)))`, e ritorna questa forma come termine sintattico da sottoporre a valutazione interpretativa ordinaria. Così ho appena esteso il linguaggio stesso manipolando dati strutturali e simbolici mediante algoritmi deterministici, trasformando strutture matematiche simboliche secondo regole di trasformazione sintattiche nel linguaggio stesso. Paul Graham dedicherà interi capitoli della sua opera fondazionale "On Lisp" all'esplorazione delle capacità espressive delle macro, concludendo che il limite della manipolazione simbolica coincide essenzialmente con i limiti della computabilità nel senso di Church-Turing dicendo che qualsiasi cosa tu possa immaginare nella manipolazione di strutture simboliche puoi realizzarla mediante macro.

Il piatto si complica ulteriormente quando consideriamo gli sviluppi contemporanei in linguaggi di tipo dipendente come Agda e Idris dove la homoicinicity arriva a livelli di astrazione categoriale assurdi con il type-level computation e l'intrinsic metatheory. In questi sistemi i tipi sono valori appartenenti a universi tipizzati, e possono essere computati mediante algoritmi, manipolati come dati, e passati come argomenti a funzioni polimorfiche di ordine superiore. La proposizione `Type : Type`—il tipo `Type` è un valore di tipo `Type` stesso, è un principio costitutivo nel contesto di una **gerarchia infinita di universi stratificati** (Type : Type₁ : Type₂ : ...), sebbene generi ricorsione impredicativa che richiede gestione attenta della stratificazione per evitare paradossi teorici. Posso scrivere una funzione computazionale a livello di tipo che calcola e ritorna un tipo intero in base al valore di un input:

```idris
makeType : Bool -> Type
makeType true = Nat
makeType false = String
```

Ho scritto una funzione il cui codominio è Type stesso, e la cui realizzazione è una computazione che produce tipi con la riduzione sintattica. Il tipo è calcolato dinamicamente in funzione degli argomenti usando una valutazione ordinaria al momento del controllo di tipo. Qui codice, dato, tipo, metatipo, meta-metatipo e pure il tipo che abita nel palazzo di fronte si collassano in un'unica struttura matematica autoconsistente e stratificata mediante eliminator principles della teoria dell'informazione di Martin-Löf. E... BOOOM.... Se ci metti Martin-Löf dentro è la fine... non lo dovevo fare...

*A proposito, sapete cos'è il Curry nella Curry-Howard correspondence? Sì, la spezia! No, scherzando: è dal nome di Haskell Curry, il logico che scoprì le proprietà della currying mediante l'osservazione della dualità tra applicazione funzionale e implicazione logica, ma vi assicuro che una buona spezia curry avrebbe reso il piatto ancora più aromatico. Comunque, proseguiamo con la ricetta teorica.*

Questo sviluppo si fonda sulla Curry-Howard correspondence che stabilisce un isomorfismo strutturale naturale tra proposizioni logiche e tipi nel senso della teoria costruttiva, e tra dimostrazioni formali e programmi nel senso del lambda calcolo tipizzato, cioè se dimostri una proposizione logica usando una sequenza di inferenze costruttive in una teoria dei tipi intuizionista, stai scrivendo un programma il cui tipo esprime proprio quella proposizione come **proposizione come tipo** (propositions-as-types), viceversa, se scrivi un programma correttamente tipizzato, stai costruendo una dimostrazione formale, laddove il tipo del programma è la proposizione dimostrata. Programmi e dimostrazioni sono così il medesimo oggetto matematico osservato attraverso lenti teoriche diverse modulo il funtore di interpretazione proposizionale. L'homoicinicity a livello di tipo realizza questa identità strutturale a ogni strato della gerarchia infinita di universi concettuale, generando una catena infinita di correspondenze tra i livelli. Guardiamo brevemente il panorama del menu completo facendo una rassegna categoriale. 

LISP e Scheme rappresentano l'homoicinicity nella sua forma più pura, codice e dato sono intrinsecamente indistinguibili e intercambiabili mediante quote/eval. Clojure preserva questa proprietà anche nel contesto di strutture dati immutabili e persistence strutturale, operando una fusione tra immutabilità e manipolazione simbolica tramita **structural sharing**, è la ricetta moderna dello stesso piatto fondamentale. Racket poi estende Scheme con homoicinicity applicata universalmente in sintassi, moduli, macro, operatori di controllo, ovunque anche nel sistema di tipi stesso, tutto è dato manipolabile attraverso il reticolo delle funzioni meta-linguistiche. Poi c'è Ruby che permette forme di homoicinicity dinamica usando symbol e hash, raggiungendo una profondità espressiva notevole tramite **reflection a runtime** e **dynamic dispatch**, anche se senza la purezza teorica di LISP. Ma non dimentichiamo Python che ci da accesso con `ast` e `eval()`, che operano al livello di rappresentazione sintattica intermedia. Le macro di Rust che non potevamo dimenticare operano a livello di TokenStream, una homoicinicity implementata al livello sintattico dei token usando **procedural macros**, una scelta architetturale ricca di conseguenze teoriche che preserva la **sicurezza di tipo** durante la metaprogrammazione. C'è anche Julia che realizza homoicinicity cone `Expr` e `eval()`, permettendo una generazione di codice a livello di espressione e **multiple dispatch**, creando un ambiente dove specializzazione e metaprogramming coesistono.

In ciascuno di questi linguaggi l'eliminazione della distinzione tra codice e dato usando funtori naturali che mappano il livello sintattico al livello semantico è l'invariante. Alcuni linguaggi mantengono questa proprietà in forma esplicita e universale (LISP, Scheme, Racket), altri la realizzano parzialmente con meccanismi localizzati (Rust, Python) e altri ancora la manifestano dinamicamente a runtime (Ruby, Julia). La profondità teorica varia inversamente con la staticità del sistema di tipi, man mano che un linguaggio incorpora più struttura tipizzata, deve sacrificare una certa immediatezza homoionica per guadagnare garanzie formali di correttezza.

Ecco il vostro piatto, profumato, macrobiotico, semplice, ricorsivo nella sua essenza come funzione priva di caso base evidente, delizioso nella sua semplicità formale, una sola operazione primitiva (applicazione funzionale) che genera un intero universo della computazione, e quando lo mangiate, ascoltate bene, questo è il punto più importante, il piatto vi insegna a cucinare, trasformandovi da consumatori passivi in creatori attivi, da esecutori in architetti di linguaggi e sistemi.

Buon appetito 😋



---

## 📜 License

© 2025 FabioFGBuono, Chef Metalinguistico e Curatore della Pagina.  
Rilasciato sotto licenza Creative Commons Attribution 4.0 International (CC BY 4.0).

This work is licensed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**.  
You are free to share and adapt the material for any purpose, even commercially, provided that appropriate credit is given.

For details, see the full license text: https://creativecommons.org/licenses/by/4.0/

