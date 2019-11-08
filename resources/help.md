Manager Fattura Elettronica è l'App che permette l'integrazione tra Shopify e i principali provider per la gestione della Fatturazione Elettronica: Fattura24, Fatture in Cloud, Fatturazione Elettronica di Aruba.

L'App Manager Fattura Elettronica è molto semplice da installare, seguendo le nostre istruzioni puoi configurarla da solo in pochi minuti.

Il nostro supporto gratuito in italiano è comunque sempre a disposizione attraverso la casella di posta dedicata così da guidarti passo passo. Se hai bisogno di aiuto scrivi a [supporto@sintra.app](mailto:supporto@sintra.app).

Dopo aver installato Manager Fattura Elettronica sul tuo store, occorre configurarla per integrarla con il tuo provider di fatturazione elettronica.

## La configurazione prevede tre steps:

### 1. CONNESSIONE
Scegli il tuo provider di fatturazione elettronica dal menù a tendina nella tab *Impostazioni* e inserisci le informazioni per connetterlo con l'App.   


Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con **Fattura24**.  

- Vai sul sito di [Fattura24](https://www.fattura24.com/)
- Copia l'Api Key di Fattura24. La trovi nel menù *Configurazione* alla sezione *App e servizi esterni* -> *Api e-commerce* -> *Shopify*. Si apre una finestra nella quale indicare **SI** alla voce **ATTIVO**. A questo punto occorre copiare la **Key** (selezioni la stringa -> tasto destro del mouse -> Copia).
- Torni sulla schermata Impostazioni dell'App e Incolli la Key nel campo **Api Key**
- [Vedi il video](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html#step1)


Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con **Fatture in Cloud**.

- Vai sul sito di [Fatture in Cloud](https://secure.fattureincloud.it/)
- Vai alla sezione *Api* del menù laterale e fai click su *MOSTRA API UID e API KEY*
- Prima copia il codice dell'Api Key, torni nella schermata impostazioni dell'App e incolli il codice nel campo **Api Key**
- Poi copia il codice dell'Api UID, torni nella schermata impostazioni dell'App e incolli il codice nel campo **Api UID**
- Infine occorre che tu scriva il nome del sezionale nel quale vuoi che la fattura sia pre-compilata. Di default le fatture saranno create nel sezionale SHOPIFY.
- [Vedi il video](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html#step1)


Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con la fatturazione elettronica di **Aruba**.

- COMING SOON


### 2. STATO ORDINI
In questa fase devi selezionare gli stati dell'ordine per i quali vuoi inviare la Fattura Elettronica. Puoi selezionare uno o più stati, e puoi comunque modificarli in seguito.

- **Pending:** seleziona questo stato se vuoi che l'ordine sia inviato alla Fatturazione Elettronica quando il pagamento è ancora in pending.
- **Authorized:** selezionando questo stato inoltrerai l'ordine alla Fatturazione Elettronica quando il pagamento sarà autorizzato.
- **Paid:** se scegli questo stato gli ordini verranno inviati alla fatturazione elettronica nel momento in cui il pagamento sarà completato.
- **Fullfilled:** scegliendo questo stato invierai alla fatturazione Elettronica tutti gli ordini che sono stati evasi.


### 3. RICHIEDI FATTURA

Come ultima cosa è necessario inserire il codice per visualizzare la form di richiesta dati nel front-end. Come sai non è possibile personalizzare i campi per la richiesta della fattura sul check-out, così per avere certezza di raccogliere i dati obligatori per la produzione della fattura elettronica è stato necessario creare un form che puoi inserire dove ritieni opportuno. Noi ti consigliamo di inserirlo nel carrello (o nel minicart se il tuo template non prevede la pagina del carrello).

Ci sono due casi.

#### Caso 1 Store solo in Italiano. 

``` 
Inserisci lo snippet di codice


{% include 'fatturazione-elettronica' %}


Il codice deve essere incollato all'interno del codice sorgente del tuo negozio: Negozio Online > Temi > Azioni > Modifica Codice

Cerca il file cart-template.liquid ed inserisci la stringa di codice all'altezza della riga 225.

```

Se non sei sicuro, guarda [il video dedicato](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html) dove ti mostriamo tutti i passaggi da effettuare per inserirlo nella posizione esatta.

#### Caso 2 Store Multilingua. 

``` 
Inserisci lo snippet di codice


{% include 'fatturazione-elettronica-multilingua' %}


Il codice deve essere incollato all'interno del codice sorgente del tuo negozio: Negozio Online > Temi > Azioni > Modifica Codice

Cerca il file cart-template.liquid ed inserisci la stringa di codice all'altezza della riga 225.

```
dopodiché

``` 
Inserisci lo snippet di codice


"fe": {
  "request" : "Richiedi fattura",
  "company" : "Azienda - Ragione Sociale",
  "fiscal-code" : "Codice fiscale",
  "vat" : "Partita Iva",
  "sdi" : "Codice SDI",
  "pec": "Pec",
  "cig": "CIG",
  "cup": "CUP",
  "split-payment": "Split-payment",
  "info": "If inserted informations are correct you can proceed to checkout",
  "customer-type": {
    "private": "Privato",
    "company": "Azienda",
    "public-administration": "Pubblica Amministrazione",
    "no-profit": "No-Profit"
  }
}


Il codice deve essere incollato all'interno del codice sorgente nel file en.default.json all'altezza della riga 391: inserisci una virgola accanto alla penultima parentesi graffa, premi invio e incolla il codice.

Puoi inserire il codice anche nei file delle altre lingue (ad esempio nel file fr.json per il francese), seguendo la stessa procedura e cambiando solo le parti del codice evidenziate in arancione e traducendole nella lingua che hai scelto.

```


# dsfdsfdsf
## dsfdsfdsf
### sdffdsf

- testo 
- testp

1. dddd
2. ddd

*corsivo* **grassetto* 

``` 
codice sorgente
function prova()
{}

```



[TITOLO](URL)

Esempio immagine
![ddd](https://covpk78932.i.lithium.com/html/assets/shopify_logo_og.svg?468313B33FF48F5143229E51EA3AB62A)

https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax


