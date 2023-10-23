Manager Fattura Elettronica è l'App che permette l'integrazione tra Shopify e i principali provider per la gestione della Fatturazione Elettronica: Fattura24, Fatture in Cloud, Fatturazione Elettronica di Aruba.
<br/>

L'App Manager Fattura Elettronica è molto semplice da installare, seguendo le nostre istruzioni puoi configurarla da solo in pochi minuti.
<br/>

Il nostro supporto gratuito in italiano è comunque sempre a disposizione attraverso la casella di posta dedicata così da guidarti passo passo. Se hai bisogno di aiuto scrivi a [supporto@sintra.app](mailto:supporto@sintra.app).
<br/>

Dopo aver installato Manager Fattura Elettronica sul tuo store, occorre configurarla per integrarla con il tuo provider di fatturazione elettronica.
<br/>

## La configurazione prevede tre steps:
<br/>

### 1. CONNESSIONE
Scegli il tuo provider di fatturazione elettronica dal menù a tendina nella tab *Impostazioni* e inserisci le informazioni per connetterlo con l'App.   
<br/>

Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con **Fattura24**.  

- Vai sul sito di [Fattura24](https://www.fattura24.com/)
- Copia l'Api Key di Fattura24. La trovi nel menù *Configurazione* alla sezione *App e servizi esterni* -> *Api e-commerce* -> *Shopify*. Si apre una finestra nella quale indicare **SI** alla voce **ATTIVO**. A questo punto occorre copiare la **Key** (selezioni la stringa -> tasto destro del mouse -> Copia).
- Torni sulla schermata Impostazioni dell'App e Incolli la Key nel campo **Api Key**
- [Vedi il video](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html#step1)

<br/>
Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con **Fatture in Cloud**.

- Vai sul sito di [Fatture in Cloud](https://secure.fattureincloud.it/)
- Vai alla sezione *Api* del menù laterale e fai click su *MOSTRA API UID e API KEY*
- Prima copia il codice dell'Api Key, torni nella schermata impostazioni dell'App e incolli il codice nel campo **Api Key**
- Poi copia il codice dell'Api UID, torni nella schermata impostazioni dell'App e incolli il codice nel campo **Api UID**
- Infine occorre che tu scriva il nome del sezionale nel quale vuoi che la fattura sia pre-compilata. Di default le fatture saranno create nel sezionale SHOPIFY.
- [Vedi il video](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html#step1)

<br/>
Come configurare le impostazioni di Manager Fattura Elettronica per integrarlo con la fatturazione elettronica di **Aruba**.
!! Stiamo lavorando per completare la configurazione di Aruba.
Se sei interessato a questo provider in particolare, contatta il nostro supporto: ti ricontatteremo appena sarà disponibile!!

- Scegli se sei un LIBERO PROFESSIONISTA o un'AZIENDA
- Compila **tutti** i campi richiesti nella form. La username e la password sono quelle del tuo account Aruba.
- [Vedi il video](https://managerfatturaelettronica.sintra.app/guida-all_installazione.html#step1)


### 2. STATO ORDINI
In questa fase devi selezionare gli stati dell'ordine per i quali vuoi inviare la Fattura Elettronica. Puoi selezionare uno o più stati, e puoi comunque modificarli in seguito.

- **Pending:** seleziona questo stato se vuoi che l'ordine sia inviato alla Fatturazione Elettronica quando il pagamento è ancora in pending.
- **Authorized:** selezionando questo stato inoltrerai l'ordine alla Fatturazione Elettronica quando il pagamento sarà autorizzato.
- **Paid:** se scegli questo stato gli ordini verranno inviati alla fatturazione elettronica nel momento in cui il pagamento sarà completato.
- **Fullfilled:** scegliendo questo stato invierai alla fatturazione Elettronica tutti gli ordini che sono stati evasi.


### 3. RICHIEDI FATTURA

Come ultima cosa è necessario inserire il codice per visualizzare la form di richiesta dati nel front-end. Come sai non è possibile personalizzare i campi per la richiesta della fattura sul check-out, così per avere certezza di raccogliere i dati obbligatori per la produzione della fattura elettronica è stato necessario creare una form che puoi inserire dove ritieni opportuno. Noi ti consigliamo di inserirla nel carrello (o nel minicart se il tuo template non prevede la pagina del carrello).

Ricorda che i passaggi sono pensati per il tema standard di Shopify, Dawn.

Ci sono due casi.

#### Caso 1 Store solo in Italiano. 

Inserisci lo snippet di codice

<pre><code>
{% render 'fatturazione-elettronica' %}
</code></pre>

Il codice deve essere incollato all'interno del codice sorgente del tuo negozio: 
Negozio Online > Temi > Azioni > Modifica Codice
<br/>

 Cerca il file main-cart-item.liquid ed inserisci la stringa di codice all'interno del tag /form>.
<br/>
<br/>

#### Caso 2 Store Multilingua. 

Inserisci lo snippet di codice

<pre><code>
{% render 'fatturazione-elettronica-multilingua' %}
</code></pre>

Il codice deve essere incollato all'interno del codice sorgente del tuo negozio: 
Negozio Online > Temi > Azioni > Modifica Codice
<br/>

Cerca il file main-cart-item.liquid ed inserisci la stringa di codice all'interno del tag /form>.
<br/>

dopodiché inserisci lo snippet di codice seguente:

<pre><code>
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
"required" : "Completa i campi della fatturazione elettronica",
"customer-type-required": "Deve essere selezionato almeno un tipo di cliente",

"fiscal-code-required": "Codice Fiscale Richiesto",

"fiscal-code-error": "Codice Fiscale Non Valido",

"company-required": "Nome compagnia richiesto",

  "fiscal-code-vat-required": "Richiesta Partita IVA o Codice Fiscale",
  "vat-error": "Partita Iva non valida", 
  "pec-error": "PEC non valida", 
  "fiscal-code-vat-required": "Richiesta Partita IVA o Codice Fiscale",

  "sdi-charcount": "SDI richiede 7 lettere", 
  "cig-charcount": "CIG richiede 10 lettere",
  "cup-charcount": "CUP richiede 15 lettere",

"pec-sdi-required": "Richiesta PEC o SDI",
  "customer-type": {
    "private": "Privato",
    "company": "Azienda",
    "public-administration": "Pubblica Amministrazione",
    "no-profit": "No-Profit"
  }
}
</code></pre>

Questa parte deve essere inserita nel file en.default.json: inserisci una virgola accanto alla penultima parentesi graffa, premi invio e incolla il codice.

<br/>

Puoi inserire il codice anche nei file delle altre lingue (ad esempio nel file fr.json per il francese), seguendo la stessa procedura e cambiando solo le parti del codice evidenziate in arancione, traducendole nella lingua che hai scelto.
<br/>

### Adesso devi solo iniziare ad usare Manager Fattura Elettronica!

