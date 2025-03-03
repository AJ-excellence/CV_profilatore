1 Raccolta dati
   Ricevo un flusso di file CSV con CV dei candidati
   Ricevo anche allegati (in PDF o estensioni aggiuntive) (più facile fare tutto in CSV, ho meno nodi da gestire).
   
BASIC: compilo un form e inserisco i dati a mano (dati da non dover estrarre) -> Requisito: ottenere item json con lista delle keys e values compilata
MEDIUM: prendo il file tutto con la stessa estensione -> Requisito: avere il contenuto del file in forma txt in output
ADVANCED: prendo il file con diverse estensioni (CSV, PDF...) -> Requisito: avere il contenuto del file in forma txt in output

2 Estrazione e Pre-etichettatura
   Requisiti = estraggo i criteri aziendali e obbiettivi prefissati (target minimi per esperienza, competenze richieste).   
   Analizzo e incrocio i CV con i requisiti (es. anni di esperienza, settore, certificazioni).
   Filtro automaticamente i CV che non rispettano la soglia minima (pensavo di dare un voto iniziale poi con un if elimino quelli troppo bassi).

BASIC: i criteri aziendali sono fissi e predefiniti (estraggo un file), poi filtro con IF -> Requisito: il sistema assegna un voto iniziale ai CV e rimuove quelli sotto soglia con un IF.
MEDIUM: come prima ma il punteggio è calcolato con più pesi (es. esperienza = 50%, certificazioni = 30%, settore = 20%...) -> Requisito: stessi di prima
ADVANCED: come prima ma i pesi sono dinamici (cambiano man mano che vengono valutati altri profili) -> Requisito: stessi di prima e tenere sotto controllo come variano i pesi dei punteggi.

3 Profilazione comportamentale
   I candidati selezionati completano un form online per raccogliere dati aggiuntivi (soft skills, motivazioni, preferenze lavorative...).
   Il sistema genera quesiti mirati in base al CV e al form (come un’intervista adattiva) (pensavo tramite a un ciclo).

BASIC: creo un form strutturato con domande fisse -> Requisito: le domande mirate sono scelte in base a condizioni sul CV.
ADVANCED: un loop che genera domande basate su criteri dinamici (sia risposte precedenti che resoconto CV) -> Requisito: uso un nodo "Set" che imposta una lista di domande iniziali, poi un nodo "Loop" che genera nuove domande in base alle risposte precedenti.

4 Analisi e Reporting
   Crei un report dettagliato con i CV più adatti e il loro punteggio rispetto ai target.
   Visualizzi i risultati con grafici e statistiche per facilitare la scelta dei migliori candidati.
      Magari: lista dei migliori candidati con profili ottimizzati.

BASIC: devo generare un report semplice con nomi, punteggi e criteri soddisfatti (semplice in HTML) -> Requisito: pagina html con solo dati tabellari
MEDIUM: come prima ma aggiugno grafici e statistiche -> Requisito: pagina html con dati tabellari e statistiche
ADVANCED: come prima ma aggiungo anche un AI che risponda con un breve resoconto (già fatto) -> Requisito: pagina html e un AI che risponda con il resoconto








Carico CV: Github (get a file) -> Extract from file tipo CSV (+ allegati di che tipo? estensioni diverse?)-> estraggo il contenuto in JSON
In parallelo estraggo  dati da incrociare (obbiettivi da fissare): ?
Lock per organizzare il flusso: merge
Leggo il contenuto: AI agent prende i dati accodati dal merge e li confronta (primo taglio con soglia minima)
Output: HTML?
Riassunto dati: AI agent riassume punti principali e dati da elaborare per la profilazione comportamentale
Importazione rapida dati: excel su github?
FOR   Sistemo variabili per il loop: SET
      Domande mirate: AI agent prende il riassunto e pone quesiti
      Valutazione rispsote: AI agent valuta la risposta (voto da 1 a 100) e ricrea il nuovo contesto (prende anche qui in input il contesto precedente) 
      IF: se bocciato resta nel FOR altrimenti esce dal FOR
Reporting: HTML?
Importazione rapida dati: excel su github?
