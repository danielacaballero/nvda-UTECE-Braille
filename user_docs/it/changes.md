# ﻿Novità in NVDA

## 2024.4

This release includes a number of improvements in Microsoft Office, braille, and document formatting.

In Word or Excel, it is now possible to double-press the comment gesture to read the comment or note in a browsable dialog.
You can now use the review cursor selection command to select text in PowerPoint.
NVDA also no longer brailles garbage characters when showing row or column header text in tables in Word when using the object model.

NVDA can now be configured to report font attributes in speech and braille separately.

A new setting has been added to configure the timeout to perform a multiple press gesture, such as the report time/date command.

You can now configure how NVDA shows text formatting in braille, and set NVDA to show the start of paragraphs in braille.
NVDA can now speak the character at the cursor when performing a braille cursor routing action.
Cursor routing reliability has been improved, and support for routing keys in PowerPoint has been added.
All lines of cells will now be used when using a multi-line braille display via HID braille.
NVDA is no longer unstable after restarting NVDA during an automatic Braille Bluetooth scan.

The minimum required version of Poedit that works with NVDA is now version 3.5.

eSpeak NG has been updated, adding support for the Faroese and Xextan languages.

LibLouis has been updated, adding new Braille tables for Thai and Greek international braille with single-cell accented letters.

There have also been a number of fixes, including to mouse tracking in Firefox, and the on-demand speech mode.

### New Features

* New braille features:
  * It is now possible to change the way NVDA displays certain text formatting attributes in braille.
    The available options are:
    * Liblouis (default): Uses formatting markers defined in the selected braille table.
    * Tags: Uses start and end tags to denote where certain font attributes begin and end. (#16864)
  * When the "Read by paragraph" option is enabled, NVDA can now be configured to indicate the start of paragraphs in braille. (#16895, @nvdaes)
  * When performing a braille cursor routing action, NVDA can now automatically speak the character at the cursor. (#8072, @LeonarddeR)
    * This option is disabled by default.
      You can enable "Speak character when routing cursor in text" in NVDA's braille settings.
* The comment command in Microsoft Word and notes command in Microsoft Excel can now be pressed twice to show the comment or note in a browsable message. (#16800, #16878, @Cary-Rowen)
* NVDA can now be configured to report font attributes in speech and braille separately. (#16755)
* The timeout to perform a multiple keypress is now configurable; this may be especially useful for people with dexterity impairment. (#11929, @CyrilleB79)

### Changes

* The `-c`/`--config-path` and `--disable-addons` command line options are now respected when launching an update from within NVDA. (#16937)
* Component updates:
  * Updated LibLouis Braille translator to [3.31.0](https://github.com/liblouis/liblouis/releases/tag/v3.31.0). (#17080, @LeonarddeR, @codeofdusk)
    * Fixed translation of numbers in Spanish Braille.
    * New Braille tables:
      * Thai grade 1
      * Greek international Braille (single-cell accented letters)
    * Renamed tables:
      * "Thai 6 dot" was renamed to "Thai grade 0" for consistency reasons.
      * The existing "Greek international braille" table was renamed to "Greek international braille (2-cell accented letters)" to clarify the distinction between the two Greek systems.
  * eSpeak NG has been updated to 1.52-dev commit `961454ff`. (#16775)
    * Added new languages Faroese and Xextan.
* When using a multi-line braille display via the standard HID braille driver, all lines of cells will be used. (#16993, @alexmoon)
* The stability of NVDA's Poedit support has been improved with the side effect that the minimum required version of Poedit is now version 3.5. (#16889, @LeonarddeR)

### Bug Fixes

* Braille fixes:
  * It is now possible to use braille display routing keys to move the text cursor in Microsoft PowerPoint. (#9101)
  * When accessing Microsoft Word without UI Automation, NVDA no longer outputs garbage characters in table headers defined with the set row and column header commands. (#7212)
  * The Seika Notetaker driver now correctly generates braille input for space, backspace and dots with space/backspace gestures. (#16642, @school510587)
  * Cursor routing is now much more reliable when a line contains one or more Unicode variation selectors or decomposed characters. (#10960, @mltony, @LeonarddeR)
  * NVDA no longer throws an error when panning the braille display forward in some empty edit controls. (#12885)
  * NVDA is no longer unstable after restarting NVDA during an automatic Braille Bluetooth scan. (#16933)
* It is now possible to use the review cursor selection commands to select text in Microsoft PowerPoint. (#17004)
* In on-demand speech mode, NVDA does not talk any more when a message is opened in Outlook, when a new page is loaded in a browser, or when displaying a new slide in a PowerPoint slideshow. (#16825, @CyrilleB79)
* In Mozilla Firefox, moving the mouse over text before or after a link now reliably reports the text. (#15990, @jcsteh)
* NVDA no longer occasionally fails to open browsable messages (such as pressing `NVDA+f` twice). (#16806, @LeonarddeR)
* Updating NVDA while add-on updates are pending no longer results in the add-on being removed. (#16837)
* It is now possible to interact with Data validation dropdown lists in Microsoft Excel 365. (#15138)
* NVDA is no longer as sluggish when arrowing up and down through large files in VS Code. (#17039)
* NVDA no longer becomes unresponsive after holding down an arrow key for a long time while in browse mode, particularly in Microsoft Word and Microsoft Outlook. (#16812)
* NVDA no longer reads the last line when the cursor is on the second-last line of a multiline edit control in Java applications. (#17027)

### Changes for Developers

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* Component updates:
  * Updated py2exe to 0.13.0.2 (#16907, @dpy013)
  * Updated setuptools to 72.0 (#16907, @dpy013)
  * Updated Ruff to 0.5.6. (#16868, @LeonarddeR)
  * Updated nh3 to 0.2.18 (#17020, @dpy013)
* Added a `.editorconfig` file to NVDA's repository in order for several IDEs to pick up basic NVDA code style rules by default. (#16795, @LeonarddeR)
* Added support for custom speech symbol dictionaries. (#16739, #16823, @LeonarddeR)
  * Dictionaries can be provided in locale specific folders in an add-on package, e.g. `locale\en`.
  * Dictionary metadata can be added to an optional `symbolDictionaries` section in the add-on manifest.
  * Please consult the [Custom speech symbol dictionaries section in the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#AddonSymbolDictionaries) for more details.
* It is now possible to redirect objects retrieved from on-screen coordinates, by using the `NVDAObject.objectFromPointRedirect` method. (#16788, @Emil-18)
* Running SCons with the parameter `--all-cores` will automatically pick the maximum number of available CPU cores. (#16943, #16868, @LeonarddeR)
* Developer info now includes information on app architecture (such as AMD64) for the navigator object. (#16488, @josephsl)

#### Deprecations

* The `bool` configuration key `[documentFormatting][reportFontAttributes]` is deprecated for removal in 2025.1, instead use `[fontAttributeReporting]`. (#16748)
  * The new key has an `int` value matching an `OutputMode` `enum` with options for speech, braille, speech and braille and off.
  * API consumers can use the `bool` value as previously, or check the `OutputMode` if handling speech or braille specifically.
  * These keys are currently synchronized until 2025.1.
* `NVDAObjects.UIA.InaccurateTextChangeEventEmittingEditableText` is deprecated with no replacement. (#16817, @LeonarddeR)

## 2024.3.1

This is a patch release to fix a bug with the automatic add-on update notification.

### Bug Fixes

* When automatically checking for add-on updates, NVDA no longer freezes on poor connections. (#17036)

## 2024.3

Nel caso in cui vi siano aggiornamenti per gli add-on installati, si verrà avvisati all'avvio di NVDA.

Sono ora disponibili opzioni per applicare la normalizzazione Unicode sia per sintesi vocale che braille.
Ciò può risultare utile quando si incontrano caratteri non presenti in una tabella braille o sconosciuti alla sintesi vocale e che hanno un'alternativa compatibile, come i caratteri in grassetto e corsivo comunemente utilizzati sui social media.
Consente inoltre la lettura delle equazioni nell'editor di equazioni di Microsoft Word.

Sono ora supportati I display braille Help Tech Activator Pro.

Aggiunti comandi non assegnati per scorrere la rotellina del mouse in verticale e in orizzontale.

Sono disponibili diverse correzioni di bug, in particolare per il pannello Emoji di Windows 11 e la cronologia degli Appunti.
Per i browser Web, sono state apportate correzioni per la segnalazione di messaggi di errore, figure, didascalie, etichette di tabelle e voci di menu con caselle di controllo/pulsanti di opzione.

LibLouis è stata aggiornata, aggiungendo nuove tabelle Braille per il cirillico serbo, lo yiddish, diverse lingue antiche, il turco e l'alfabeto fonetico internazionale.
Anche eSpeak porta con sé aggiornamenti, aggiungendo il supporto per la lingua Karakalpak.
Infine, aggiornato anche unicode CLDR.

### Novità

* Nuovi comandi da tastiera:
  * Aggiunti comandi non assegnati per lo scorrimento verticale e orizzontale della rotella del mouse, per migliorare la navigazione su pagine web e app con contenuti dinamici, come Dism++.(#16462, @Cary-Rowen)
* Aggiunto il supporto per la normalizzazione Unicode sia per sintesi vocale che display braille. (#11570, #16466 @LeonarddeR).
  * Ciò può risultare utile quando si incontrano caratteri non presenti in una tabella braille o sconosciuti alla sintesi vocale e che hanno un'alternativa compatibile, come i caratteri in grassetto e corsivo comunemente utilizzati sui social media.
  * Consente inoltre la lettura delle equazioni nell'editor di equazioni di Microsoft Word. (#4631)
  * è possibile abilitare questa funzionalità sia per la sintesi che per il braille nelle rispettive categorie di impostazioni nella finestra di dialogo Impostazioni NVDA.
* Da impostazioni predefinite, all'avvio di NVDA si riceverà una notifica nel caso in cui siano presenti aggiornamenti per gli add-on installati. (#15035)
  * Ciò può essere disabilitato nella categoria delle impostazioni "Add-on store".
  * NVDA verifica quotidianamente la presenza di aggiornamenti.
  * Verranno controllati solo gli aggiornamenti all'interno dello stesso canale (ad esempio, se sono stati installati add-on in versione beta, questi riceveranno aggiornamenti appartenenti esclusivamente al canale beta.
* Aggiunto il supporto per i display Help Tech Activator Pro. (#16668)

### Cambiamenti

* Aggiornamento ai componenti:
  * eSpeak NG è stato aggiornato a 1.52-dev commit `54ee11a79`. (#16495)
    * Aggiunta la nuova lingua Karakalpak.
  * Aggiornato Unicode CLDR alla versione 45.0. (#16507, @OzancanKaratas)
  * Aggiornato fast_diff_match_patch (utilizzato per rilevare modifiche nei terminali e altri contenuti dinamici) alla versione 2.1.0. (#16508, @codeofdusk)
  * Aggiornata LibLouis braille translator a [3.30.0](https://github.com/liblouis/liblouis/releases/tag/v3.30.0). (#16652, @codeofdusk)
    * Nuove tabelle braille:
      * Serbo cirillico.
      * yiddish.
      * Diverse lingue antiche: ebraico biblico, accadico, siriaco, ugaritico e testo cuneiforme traslitterato.
      * Turco grado 2. (#16735)
      * Alfabeto fonetico internazionale. (#16773)
  * NSIS aggiornato a 3.10 (#16674, @dpy013)
  * Aggiornato markdown a 3.6 (#16725, @dpy013)
  * Aggiornato nh3 a 0.2.17 (#16725, @dpy013)
* La tabella di input Braille di riserva è ora uguale alla tabella di output di riserva, che è il codice Braille inglese unificato di grado 1. (#9863, @JulienCochuyt, @LeonarddeR)
* NVDA ora annuncerà le figure senza oggetti figli accessibili, ma con un'etichetta o una descrizione. (#14514)
* Durante la lettura riga per riga in modalità navigazione, non verrà più annunciata la parola "didascalia" quando si esplorano figure con molto testo al loro interno. (#14874)
* Nella console Python, non andrà più perso l'ultimo comando non eseguito quando ci si sposta nella cronologia degli input. (#16653, @CyrilleB79)
* Viene ora inviato un ID anonimo ed univoco come parte della raccolta facoltativa delle statistiche sull'utilizzo di NVDA. (#16266)
* Per impostazione predefinita, verrà creata una nuova cartella quando si crea una copia portable.
Si riceverà un messaggio d'avviso nel caso in cui si provi a scrivere in una directory non vuota. (#16686)

### Bug Corretti

* Correzioni a Windows 11:
  * NVDA non si bloccherà più quando si chiude la cronologia degli appunti e il pannello emoji. (#16346, #16347, @josephsl)
  * NVDA annuncerà nuovamente i caratteri candidati visibili all'apertura dell'interfaccia IME. (#14023, @josephsl)
  * NVDA non leggerà più due volte la "cronologia degli appunti" durante la navigazione tra le voci del menu del pannello emoji. (#16532, @josephsl)
  * NVDA non interromperà più la sintesi vocale e la lettura Braille quando si esaminano kaomojis e simboli nel pannello delle emoji. (#16533, @josephsl)
* Correzioni nei browser Web:
  * I messaggi di errore a cui si fa riferimento con `aria-errormessage` ora vengono segnalati in Google Chrome e Mozilla Firefox. (#8318)
  * Se presente, NVDA ora utilizzerà `aria-labelledby` per fornire nomi accessibili per le tabelle in Mozilla Firefox. (#5183)
  * NVDA annuncerà correttamente gli elementi relativi alle caselle di controllo o pulsanti radio nei menu quando si accede per la prima volta ai sottomenu in Google Chrome e Mozilla Firefox. (#14550)
  * La funzionalità di ricerca in modalità navigazione di NVDA è ora più precisa quando la pagina contiene emoji. (#16317, @LeonarddeR)
  * In Mozilla Firefox, NVDA ora riporta correttamente il carattere, la parola e la riga correnti quando il cursore si trova nel punto di inserimento alla fine di una riga. (#3156, @jcsteh)
  * Lo screen reader non causa più l'arresto anomalo di Google Chrome quando si chiude un documento o si esce da Chrome. (#16893)
* NVDA annuncerà correttamente i suggerimenti di completamento automatico in Eclipse e in altri ambienti basati su Eclipse su Windows 11. (#16416, @thgcode)
* Maggiore affidabilità della lettura automatica del testo, in particolare nelle applicazioni terminali. (#15850, #16027, @Danstiv)
* È nuovamente possibile ripristinare in modo affidabile la configurazione alle impostazioni di fabbrica. (#16755, @Emil-18)
* NVDA annuncerà correttamente le modifiche alla selezione durante la modifica del testo di una cella in Microsoft Excel. (#15843)
* Nelle applicazioni che utilizzano Java Access Bridge, NVDA ora leggerà correttamente l'ultima riga vuota di un testo invece di ripetere la riga precedente. (#9376, @dmitrii-drobotov)
* In LibreOffice Writer (versione 24.8 e successive), quando si attiva/disattiva la formattazione del testo (grassetto, corsivo, sottolineato, pedice/apice, allineamento) utilizzando la scorciatoia da tastiera corrispondente, NVDA annuncia il nuovo attributo di formattazione (ad esempio "Grassetto attivato", "Grassetto disattivato" ). (#4248, @michaelweghorn)
* Quando si naviga con i tasti freccia nelle caselle di testo in applicazioni che fanno uso di UI Automation, NVDA non annuncerà più per errore il carattere, la parola o la riga errata. (#16711, @jcsteh)
* Quando si incolla qualcosa nella calcolatrice di Windows 10/11, NVDA ora leggerà correttamente il numero completo appena incollato. (#16573, @TristanBurchett)
* Corretto un errore che zittiva la sintesi vocale dopo la disconnessione e la riconnessione a una sessione di Desktop remoto. (#16722, @jcsteh)
* Aggiunto supporto per i comandi di revisione del testo per il nome di un oggetto in Visual Studio Code. (#16248, @Cary-Rowen)
* è ora possibile ascoltare i suoni generati da NVDA anche sui dispositivi mono. (#16770, @jcsteh)
* NVDA segnalerà gli indirizzi quando si scorrono i campi A/CC/BCC in outlook.com/Modern Outlook. (#16856)
* NVDA ora gestisce gli errori di installazione dei componenti aggiuntivi in modo più efficace. (#16704)

### Cambiamenti per sviluppatori, in inglese

* NVDA now uses Ruff instead of flake8 for linting. (#14817)
* Fixed NVDA's build system to work properly when using Visual Studio 2022 version 17.10 and above. (#16480, @LeonarddeR)
* A fixed width font is now used in Log Viewer and in the NVDA Python Console so that the cursor remains in the same column during vertical navigation.
It is especially useful to read the error location markers in tracebacks. (#16321, @CyrilleB79)
* Support for custom braille tables has been added. (#3304, #16208, @JulienCochuyt, @LeonarddeR)
  * Tables can be provided in the `brailleTables` folder in an add-on package.
  * Table metadata can be added to an optional `brailleTables` section in the add-on manifest or to a `.ini` file with the same format found in the brailleTables subdirectory of the scratchpad directory.
  * Please consult the [braille translation tables section in the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#BrailleTables) for more details.
* When a `gainFocus` event is queued with an object that has a valid `focusRedirect` property, the object pointed to by the `focusRedirect` property is now held by `eventHandler.lastQueuedFocusObject`, rather than the originally queued object. (#15843)
* NVDA will log its executable architecture (x86) at startup. (#16432, @josephsl)
* `wx.CallAfter`, which is wrapped in `monkeyPatches/wxMonkeyPatches.py`, now includes proper `functools.wraps` indication. (#16520, @XLTechie)
* There is a new module for scheduling tasks `utils.schedule`, using the pip module `schedule`. (#16636)
  * You can use `scheduleThread.scheduleDailyJobAtStartUp` to automatically schedule a job that happens after NVDA starts, and every 24 hours after that.
  Jobs are scheduled with a delay to avoid conflicts.
  * `scheduleThread.scheduleDailyJob` and `scheduleJob` can be used to schedule jobs at custom times, where a `JobClashError` will be raised on a known job scheduling clash.
* It is now possible to create app modules for apps hosting Edge WebView2 (msedgewebview2.exe) controls. (#16705, @josephsl)

## 2024.2

Introdotta una nuova funzionalità chiamata hbilanciamento audio.
Ciò consente di impostare i suoni di NVDA in un canale (ad esempio sinistro) mentre i suoni di tutte le altre applicazioni vengono diretti all'altro canale (ad esempio destro).

Vi sono nuovi comandi per modificare le impostazioni al volo del sintetizzatore, consentendo agli utenti di passare al primo o all'ultimo elemento e di aumentare o diminuire l'impostazione corrente con incrementi più ampi.
Sono inoltre disponibili nuovi comandi di navigazione veloce, che consentono agli utenti di associare gesti per passare rapidamente tra: paragrafo, paragrafo allineato verticalmente, testo con lo stesso stile, testo con stile diverso, voce di menu, interruttore, barra di avanzamento, figura e formula matematica.

Sono presenti molte nuove funzionalità braille e correzioni di bug.
È stata aggiunta una modalità braille denominata "mostra output sintesi vocale".
Quando attiva, sul display braille si visualizzerà esattamente ciò che dice NVDA.
Aggiunto anche il supporto per i display BrailleEdgeS2 e BrailleEdgeS3.
LibLouis è stato aggiornato, con nuove tabelle dettagliate (con lettere maiuscole indicate) in Braille bielorusso e ucraino, una tabella laotiana e una tabella spagnola per la lettura di testi greci.

eSpeak riceve un aggiornamento che prevede l'aggiunta della nuova lingua Tigrinya.

Sono disponibili numerose correzioni di bug minori per applicazioni come Thunderbird, Adobe Reader, browser Web, Nudi e Geekbench.

### Novità

* Nuovi tasti di scelta rapida:
  * Nuovo comando di navigazione veloce `p` per passare al paragrafo di testo successivo/precedente in modalità navigazione. (#15998, @mltony)
  * Nuovi comandi di navigazione veloce non assegnati, che possono essere utilizzati per passare all'elemento  successivo/precedente indicati di seguito:
    * figura (#10826)
    * paragrafo allineato verticalmente (#15999, @mltony)
    * voce di menu (#16001, @mltony)
    * Interruttore (#16001, @mltony)
    * barra di avanzamento (#16001, @mltony)
    * Formula matematica (#16001, @mltony)
    * Testo con lo stesso stile (#16000, @mltony)
    * testo con stile diverso (#16000, @mltony)
  * Aggiunti comandi relativi alle impostazioni al volo del sintetizzatore per saltare al primo elemento, all'ultimo, avanti e indietro. (#13768, #16095, @rmcpantoja)
    * Nessuna assegnazione di gesti per andare al primo o all'ultimo elemento delle impostazioni al volo del sintetizzatore. (#13768)
    * Aumentare/diminuire il parametro corrente del sintetizzatore con un incremento maggiore/minore. (#13768):
      * Desktop: `NVDA+control+paginaSu` e `NVDA+control+paginaGiù`.
      * Laptop: `NVDA+control+shift+paginaSu` e `NVDA+control+shift+paginaGiù`.
  * Aggiunto un nuovo gesto di immissione non assegnato per attivare/disattivare la segnalazione di figure e didascalie. (#10826, #14349)
* Braille:
  * Introdotto il supporto per i display BrailleEdgeS2 and BrailleEdgeS3. (#16033, #16279, @EdKweon)
  * Aggiunta una nuova modalità braille denominata "Mostra output sintesi vocale". (#15898, @Emil-18)
    * Quando attiva, sul display braille si visualizzerà esattamente ciò che dice NVDA.
    * Può essere abilitata attraverso la combinazione di tasti `NVDA+alt+t`, o dalla finestra impostazioni braille.
* bilanciamento del suono: (#12985, @mltony)
  * Consente di impostare i suoni di NVDA in un canale (ad esempio sinistro) mentre i suoni di tutte le altre applicazioni vengono diretti all'altro canale (ad esempio destro).
  * Per attivarlo/disattivarlo, usare `NVDA+alt+s`.
* Viene ora supportata la segnalazione di intestazioni di righe e colonne negli elementi html con contenuto modificabile. (#14113)
* Aggiunta un'opzione per disabilitare la lettura di figure e didascalie nelle impostazioni formato documento. (#10826, #14349)
* In Windows 11, NVDA annuncerà gli avvisi derivanti dalla digitazione vocale e le azioni suggerite, incluso il suggerimento principale quando si copiano dati come i numeri di telefono negli appunti (Windows 11 2022 Update e versioni successive). (#16009, @josephsl)
* NVDA manterrà attiva la scheda audio dopo che la sintesi vocale ha smesso di parlare, per evitare che l'inizio della frase successiva venga troncata con alcuni dispositivi audio come le cuffie Bluetooth. (#14386, @jcsteh, @mltony)
* Supporto per HP Secure Browser. (#16377)

### Cambiamenti

* Add-on Store:
  * vengono ora visualizzate nell'area "altri dettagli" La versione minima e l'ultima testata di NVDA per un add-on. (#15776, @Nael-Sayegh)
  * Disponibile in tutte le schede dello store la funzione recensione degli utenti. (#16179, @nvdaes)
* Aggiornamento dei componenti:
  * Aggiornato LibLouis Braille translator alla versione [3.29.0](https://github.com/liblouis/liblouis/releases/tag/v3.29.0). (#16259, @codeofdusk)
    * Nuove tabelle Braille bielorusse e ucraine dettagliate (con le lettere maiuscole indicate).
    * Nuova tabella spagnola per la lettura di testi greci.
    * Nuova tabella per Lao Grado 1. (#16470)
  * eSpeak NG è stato aggiornato al commit 1.52-dev `cb62d93fd7`. (#15913)
    * Aggiunta la nuova lingua Tigrinya.
* Modificati diversi gesti per i dispositivi BrailleSense per evitare conflitti con i caratteri della tabella braille francese. (#15306)
  * `alt+frecciaSinistra` è ora mappato su `punto2+punto7+spazio`
  * `alt+frecciadestra` è ora mappato su `punto5+punto7+spazio`
  * `alt+frecciaSu` è ora mappato su `punto2+punto3+punto7+spazio`
  * `alt+frecciaGiù` è ora mappato su `punto5+punto6+punto7+spazio`
* I punti di riempimento comunemente utilizzati nei sommari non vengono più inseriti nei livelli di punteggiatura più bassi. (#15845, @CyrilleB79)

### Bug Corretti

* Correzioni per Windows 11:
  * NVDA annuncerà nuovamente i suggerimenti per l'immissione da tastiera hardware. (#16283, @josephsl)
  * Nella versione 24H2 (aggiornamento 2024 e Windows Server 2025), l'interazione con mouse e tocco può essere utilizzata nelle impostazioni rapide. (#16348, @josephsl)
* Add-on Store:
  * Quando si preme `ctrl+tab`, lo stato attivo si sposta correttamente sul nuovo titolo della scheda corrente. (#14986, @ABuffEr)
  * Se i file della cache non sono corretti, NVDA non si riavvierà più. (#16362, @nvdaes)
* Correzioni per i browser basati su Chromium se utilizzati con UIA:
  * Risolti i bug che causavano il blocco di NVDA. (#16393, #16394)
  * Il tasto Backspace ora funziona correttamente nei campi di login di Gmail. (#16395)
* Il tasto backspace ora funziona correttamente quando si utilizza Nudi 6.1 con l'impostazione "Gestisci tasti da altre applicazioni" di NVDA abilitata. (#15822, @jcsteh)
* Risolto un bug per cui, nonostante un'applicazione si trovasse in modalità riposo, venivano erroneamente emessi i segnali acustici con l'opzione "coordinate audio quando il mouse si sposta" attivata. (#8059, @hwf1324)
* In Adobe Reader, NVDA non ignora più il testo alternativo impostato nelle formule nei PDF. (#12715)
* Risolto un bug che impediva a NVDA di leggere la barra multifunzione e le opzioni all'interno di Geekbench. (#16251, @mzanm)
* Risolto un bug piuttosto raro in cui il salvataggio della configurazione non salvava tutti i profili. (#16343, @CyrilleB79)
* Nei browser basati su Firefox e Chromium, NVDA entrerà correttamente in modalità focus quando si preme Invio se posizionati all'interno di un elenco di presentazione (ul / ol) dentro al contenuto modificabile. (#16325)
* La modifica dello stato delle colonne ora viene letta correttamente quando si scelgono le colonne da visualizzare nell'elenco dei messaggi di Thunderbird. (#16323)
* L'opzione a riga di comando `-h`/`--help` funziona di nuovo correttamente. (#16522, @XLTechie)
* Il supporto di NVDA per il software di traduzione Poedit versione 3.4 o successiva gestisce correttamente la traduzione di lingue con 1 o più di 2 forme plurali (ad esempio cinese, polacco). (#16318)

### Cambiamenti per sviluppatori, in ingleseChanges for Developers

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* Instantiating `winVersion.WinVersion` objects with unknown Windows versions above 10.0.22000 such as 10.0.25398 returns "Windows 11 unknown" instead of "Windows 10 unknown" for release name. (#15992, @josephsl)
* Make the AppVeyor build process easier for NVDA forks, by adding configurable variables in appveyor.yml to disable or modify NV Access specific portions of the build scripts. (#16216, @XLTechie)
* Added a how-to document, explaining the process of building NVDA forks on AppVeyor. (#16293, @XLTechie)

## 2024.1

Aggiunta una nuova modalità per la sintesi vocale, chiamata su richiesta.
Se l'utente la attiva, NVDA non parlerà in automatico (ad esempio quando si sposta il cursore) ma lo farà soltanto nel momento in cui verranno utilizzati comandi che richiedano esplicitamente un riscontro vocale (un esempio può essere conoscere il titolo della finestra).
è ora possibile escludere le modalità vocali indesiderate, quando si preme `NVDA+s`, dalla categoria Voce delle impostazioni di NVDA.

è ora disponibile una nuova modalità di selezione nativa (che si attiva con `NVDA+shift+f10`) durante la navigazione con Mozilla Firefox.
Quando è attivata, la selezione del testo in modalità navigazione funzionerà come se si stesse evidenziando del testo direttamente con Firefox stesso..
La copia del testo con `control+c` verrà gestita da Firefox, il che consente di copiare tutto il contenuto comprensivo di formattazione, tabelle, elementi grafici, piuttosto che soltanto il testo semplice.

Lo Store dei componenti aggiuntivi ora supporta le azioni collettive (come l'installazione o l'abilitazione degli add-on) selezionandone più di uno.
È disponibile una nuova azione per aprire una pagina Web di recensioni per il componente aggiuntivo selezionato.

Le opzioni del dispositivo audio di uscita e della modalità attenuazione sono state rimosse dalla finestra di dialogo "Seleziona sintetizzatore".
Si trovano nel pannello delle impostazioni audio che può essere aperto con `NVDA+control+u`.

Aggiornati eSpeak-NG, LibLouis braille translator e Unicode CLDR.
Sono disponibili nuove tabelle braille: tailandese, filippino e rumeno.

Sono stati risolti numerosi bug, in particolare per l'add-on store, braille, Libre Office, Microsoft Office e audio.

### Note importanti

* Questa versione interrompe la compatibilità con i componenti aggiuntivi esistenti.
* Windows 7 e Windows 8 non sono più supportati.
Windows 8.1 è la versione minima di Windows supportata.

### Novità

* Add-on Store:
  * L'Add-on Store ora supporta le azioni di massa (ad esempio installazione o attivazione di più add-on).  (#15350, #15623, @CyrilleB79)
  * È stata aggiunta una nuova azione per aprire una pagina Web dedicata, allo scopo di visualizzare o fornire feedback sul componente aggiuntivo selezionato. (#15576, @nvdaes)
* Aggiunto il supporto per i display Braille HID Bluetooth a bassa energia. (#15470)
* è ora disponibile una nuova modalità di selezione nativa (che si attiva con `NVDA+shift+f10`) durante la navigazione con Mozilla Firefox.
Quando è attivata, la selezione del testo in modalità navigazione funzionerà come se si stesse evidenziando del testo direttamente con Firefox stesso..
La copia del testo con `control+c` verrà gestita da Firefox, il che consente di copiare tutto il contenuto comprensivo di formattazione, tabelle, elementi grafici, piuttosto che soltanto il testo semplice.
Si noti tuttavia che poiché Firefox gestisce la copia effettiva, non potremo ascoltare il classico messaggio: "copiato negli appunti", fornito da NVDA. (#15830)
* Quando si copia testo in Microsoft Word con la modalità navigazione di NVDA abilitata, ora è inclusa anche la formattazione.
Un effetto collaterale di ciò è che NVDA non annuncerà più il messaggio "copia negli appunti" quando si preme `control+c` nella modalità di navigazione di Microsoft Word / Outlook, poiché ora è l'applicazione a gestire la copia, non NVDA. (#16129)
* Aggiunta una nuova modalità per la sintesi vocale, chiamata su richiesta.
Se l'utente la attiva, NVDA non parlerà in automatico (ad esempio quando si sposta il cursore) ma lo farà soltanto nel momento in cui verranno utilizzati comandi che richiedano esplicitamente un riscontro vocale (un esempio può essere conoscere il titolo della finestra).
* è ora possibile escludere le modalità vocali indesiderate, quando si preme `NVDA+s`, dalla categoria Voce delle impostazioni di NVDA.
  * Se si sta utilizzando il componente aggiuntivo NoBeepsSpeechMode, si consiglia di disinstallarlo e disabilitare le modalità "bip" e "su richiesta" nelle impostazioni.

### Cambiamenti

* NVDA non supporta più Windows 7 e Windows 8.
Windows 8.1 è la versione minima di Windows supportata. (#15544)
* Aggiornamento dei componenti:
  * Aggiornato LibLouis braille translator alla versione [3.28.0](https://github.com/liblouis/liblouis/releases/tag/v3.28.0). (#15435, #15876, @codeofdusk)
    * Aggiunte nuove tabelle Braille tailandese, rumeno e filippino.
  * eSpeak NG è stato aggiornato a 1.52-dev commit `530bf0abf`. (#15036)
  * Le emoji e le annotazioni dei simboli CLDR sono state aggiornate alla versione 44.0. (#15712, @OzancanKaratas)
  * Aggiornato Java Access Bridge alla versione 17.0.9+8Zulu (17.46.19). (#15744)
* Comandi da tastiera:
  * I seguenti comandi supportano la doppia e tripla pressione per effettuare lo spelling delle informazioni annunciate e della descrizione dei caratteri: Leggi selezione, Annuncia testo negli appunti e Leggi l'oggetto focalizzato. (#15449, @CyrilleB79)
  * Il comando per attivare/disattivare la tenda schermo ha un gesto predefinito associato: `NVDA+control+escape`. (#10560, @CyrilleB79)
  * Se premuto quattro volte, il comando "leggi selezione" ora mostra la selezione in una finestra navigabile. (#15858, @Emil-18)
* Microsoft Office:
  * Quando si richiedono informazioni sulla formattazione delle celle di Excel, i bordi e lo sfondo verranno annunciati solo se è presente tale formattazione. (#15560, @CyrilleB79)
  * NVDA non leggerà più i raggruppamenti senza etichetta come nelle versioni recenti dei menu di Microsoft Office 365. (#15638)
* Le opzioni del dispositivo audio di uscita e della modalità attenuazione sono state rimosse dalla finestra di dialogo "Seleziona sintetizzatore".
Si trovano nel pannello delle impostazioni audio che può essere aperto con `NVDA+control+u`. (#15512, @codeofdusk)
* Nella finestra impostazioni Mouse di NVDA, L'opzione "Annuncia ruoli quando il mouse entra in un oggetto" è stata rinominata in  "Leggi tipo e ruolo dell'oggetto sotto il mouse".
Questa opzione ora fornisce ulteriori informazioni rilevanti su un oggetto quando il mouse vi entra, come lo stato (selezionato/premuto) o le coordinate della cella in una tabella. (#15420, @LeonarddeR)
* Sono stati aggiunti nuovi elementi al menu Aiuto per la pagina "Ottieni aiuto" e il negozio di NV Access. (#14631)
* Il supporto per [Poedit](https://poedit.net) è stato adeguato per Poedit versione 3 e successive.
Gli utenti di Poedit 1 sono fortemente pregati ad aggiornare a Poedit 3 se desiderano godere dell'accessibilità migliorata, come le scorciatoie per leggere le note e i commenti dei traduttori. (#15313, #7303, @LeonarddeR)
* Il visualizzatore Braille e il visualizzatore sintesi vocale sono ora disabilitati in modalità protetta. (#15680)
* Nella navigazione ad oggetti, gli oggetti disabilitati (non disponibili) non saranno più ignorati. (#15477, @CyrilleB79)
* Aggiunto il sommario al documento dei comandi da tastiera. (#16106)

### Bug Corretti

* Add-on Store:
  * Quando lo stato di un componente aggiuntivo viene modificato mentre è attivo, ad es. da "in download" diventa "scaricato", l'elemento aggiornato viene ora annunciato correttamente. (#15859, @LeonarddeR)
  * Quando si installano componenti aggiuntivi, le richieste di installazione non vengono più sovrapposte alla finestra di dialogo di riavvio. (#15613, @lukaszgo1)
  * Quando si reinstalla un componente aggiuntivo incompatibile, non viene più forzatamente disabilitato. (#15584, @lukaszgo1)
  * I componenti aggiuntivi disabilitati e incompatibili ora possono essere aggiornati. (#15568, #15029)
  * NVDA ora visualizza un errore nel caso in cui un componente aggiuntivo non venga scaricato correttamente. (#15796)
  * NVDA non presenta più un problema intermitttente nel riavviarsi dopo l'apertura e la chiusura dell'add-on store. (#16019, @lukaszgo1)
* Audio:
  * NVDA non si blocca più di tanto in tanto quando vengono riprodotti più suoni in rapida successione. (#15311, #15757, @jcsteh)
  * se un dispositivo audio diverso da quello predefinito, dopo  essere stato disconnesso, diventa nuovamente disponibile,  NVDA riprenderà ad utilizzarlo. (#15759, @jcsteh)
  * NVDA ora è in grado di ripristinare l'audio nel caso in cui la configurazione del dispositivo d'uscita viene modificata, o un'altra applicazione ne rilascia il controllo esclusivo. (#15758, #15775, @jcsteh)
* Braille:
  * I display Braille con più righe non bloccano più il driver BRLTTY e vengono trattati come un display continuo. (#15386)
  * Vengono rilevati più oggetti che contengono testo utile, inoltre il contenuto del testo viene visualizzato in Braille. (#15605)
  * L'input Braille contratto funziona di nuovo correttamente. (#15773, @aaclause)
  * Quando si sposta il navigatore ad oggetti tra le celle di una tabella, il contenuto in braille viene aggiornato in maniera migliore. (#15755, @Emil-18)
  * Viene ora mostrato in braille il risultato dei comandi "leggi l'oggetto che ha il focus", leggi l'oggetto su cui è il navigatore e  leggi selezione corrente. (#15844, @Emil-18)
  * Il driver braille Albatross non gestisce più un microcontrollore Esp32 come un display Albatross. (#15671)
* LibreOffice:
  * Vengono annunciate correttamente le parole cancellate con  `control+backspace`, anche quando la parola è seguita da spazi bianchi (come spazi e tabulazioni). (#15436, @michaelweghorn)
  * La lettura della barra di stato tramite `NVDA+fine` adesso funziona anche per le finestre di dialogo in LibreOffice versione 24.2 e successive. (#15591, @michaelweghorn)
  * Tutti gli attributi di testo previsti sono ora supportati nelle versioni LibreOffice 24.2 e successive.
  Ciò fa sì che l'annuncio degli errori di ortografia funzioni quando viene letta una riga in Writer. (#15648, @michaelweghorn)
  * L'annuncio dei livelli di intestazione ora funziona anche per le versioni di LibreOffice 24.2 e successive. (#15881, @michaelweghorn)
* Microsoft Office:
  * In Excel con UIA disabilitata, alla pressione dei tasti rapidi `control+y`, `control+z` o `alt+backspace`, il contenuto della cella attiva verrà sia letto che aggiornato conseguentemente sul display braille. (#15547)
  * In Word con UIA disabilitata, il contenuto braille sarà aggiornato alla pressione delle combinazioni di tasti `control+v`, `control+x`, `control+y`, `control+z`, `alt+backspace`, `backspace` o `control+backspace`.
  Verrà aggiornato anche con UIA abilitata, quando il braille segue il cursore di controllo  il cursore di controllo segue quello di sistema. (#3276)
  * In Word, la cella di destinazione verrà ora letta correttamente quando si utilizzano i comandi nativi di Word per la navigazione nella tabella `alt+home`, `alt+end`, `alt+paginaSu` e `alt+paginaGiù`. (#15805, @CyrilleB79)
* È stata migliorata la segnalazione dei tasti di scelta rapida degli oggetti. (#10807, #15816, @CyrilleB79)
* Il sintetizzatore SAPI4 ora supporta correttamente i cambiamenti di volume, velocità e tono incorporati nel parlato. (#15271, @LeonarddeR)
* Viene segnalato correttamente lo stato multiriga nelle applicazioni che utilizzano Java Access Bridge. (#14609)
* NVDA annuncerà il contenuto delle finestre di dialogo per molte più finestre di Windows 10 e 11. (#15729, @josephsl)
* NVDA non commetterà più errori nella lettura di una nuova pagina web appena caricata in Microsoft Edge quando si utilizza UI Automation. (#15736)
* Quando si utilizza la funzione Dire Tutto o i comandi che gestiscono il testo, le pause tra le frasi o i caratteri non diminuiscono più gradualmente nel tempo. (#15739, @jcsteh)
* NVDA non si blocca più nel leggere enormi quantità di testo. (#15752, @jcsteh)
* Quando si accede a Microsoft Edge utilizzando UI Automation, NVDA è in grado di attivare più controlli nella modalità navigazione. (#14612)
* NVDA non avrà più problemi nell'avviarsi quando il file di configurazione è danneggiato, ma ripristinerà la configurazione predefinita come in passato. (#15690, @CyrilleB79)
* Risolto il problema con il supporto per i controlli della visualizzazione Elenco di sistema (`SysListView32`) nelle applicazioni Windows Forms. (#15283, @LeonarddeR)
* Non è più possibile sovrascrivere la cronologia della console Python di NVDA. (#15792, @CyrilleB79)
* NVDA dovrebbe rimanere reattivo anche quando viene inondato da molti eventi di UI Automation, ad es. quando vengono stampate grandi porzioni di testo su un terminale o quando si ascoltano messaggi vocali in WhatsApp Messenger. (#14888, #15169)
  * Questo nuovo comportamento può essere disabilitato utilizzando la nuova impostazione "Utilizza elaborazione eventi avanzata" nelle impostazioni avanzate di NVDA.
* NVDA è nuovamente in grado di seguire il focus nelle applicazioni in esecuzione all'interno di Windows Defender Application Guard (WDAG). (#15164)
* Il testo parlato non viene più aggiornato quando il mouse si sposta nel Visualizzatore vocale. (#15952, @hwf1324)
* NVDA tornerà nuovamente alla modalità navigazione quando si chiudono le caselle combinate con `escape` o `alt+freccia su` in Firefox o Chrome. (#15653)
* L'utilizzo delle freccie su e giù nelle caselle combinate di iTunes non attiverà più erroneamente la modalità navigazione. (#15653)

### Changes for Developers

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* Note: this is an Add-on API compatibility breaking release.
Add-ons will need to be re-tested and have their manifest updated.
* Building NVDA now requires Visual Studio 2022.
Please refer to the [NVDA docs](https://github.com/nvaccess/nvda/blob/release-2024.1/projectDocs/dev/createDevEnvironment.md) for the specific list of Visual Studio components. (#14313)
* Added the following extension points:
  * `treeInterceptorHandler.post_browseModeStateChange`. (#14969, @nvdaes)
  * `speech.speechCanceled`. (#15700, @LeonarddeR)
  * `_onErrorSoundRequested` (should be retrieved calling `logHandler.getOnErrorSoundRequested()`) (#15691, @CyrilleB79)
* It is now possible to use plural forms in an add-on's translations. (#15661, @beqabeqa473)
* Included python3.dll in the binary distribution for use by add-ons with external libraries utilizing the [stable ABI](https://docs.python.org/3.11/c-api/stable.html). (#15674, @mzanm)
* The `BrailleDisplayDriver` base class now has `numRows` and `numCols` properties to provide information about multi line braille displays.
Setting `numCells` is still supported for single line braille displays and `numCells` will return the total number of cells for multi line braille displays. (#15386)
* Updated BrlAPI for BRLTTY to version 0.8.5, and its corresponding python module to a Python 3.11 compatible build. (#15652, @LeonarddeR)
* Added the `speech.speakSsml` function, which allows you to write NVDA speech sequences using [SSML](https://www.w3.org/TR/speech-synthesis11/). (#15699, @LeonarddeR)
  * The following tags are currently supported and translated to appropriate NVDA speech commands:
    * `Prosody` (`pitch`, `rate` and `volume`). Only multiplication (e.g. `200%` are supported.
    * `say-as` with the `interpret` attribute set to `characters`
    * `voice` with the `xml:lang` set to an XML language
    * `break` with the `time` attribute set to a value in milliseconds, e.g. `200ms`
    * `mark` with the `name` attribute set to a mark name, e.g. `mark1`, requires providing a callback
  * Example: `speech.speakSsml('<speak><prosody pitch="200%">hello</prosody><break time="500ms" /><prosody rate="50%">John</prosody></speak>')`
  * The SSML parsing capabilities are backed by the `SsmlParser` class in the `speechXml` module.
* Changes to the NVDA Controller Client library:
  * The file names of the library no longer contain a suffix denoting the architecture, i.e. `nvdaControllerClient32/64.dll` are now called `nvdaControllerClient.dll`. (#15718, #15717, @LeonarddeR)
  * Added an example to demonstrate using nvdaControllerClient.dll from Rust. (#15771, @LeonarddeR)
  * Added the following functions to the controller client: (#15734, #11028, #5638, @LeonarddeR)
    * `nvdaController_getProcessId`: To get the process id (PID) of the current instance of NVDA the controller client is using.
    * `nvdaController_speakSsml`: To instruct NVDA to speak according to the given SSML. This function also supports:
      * Providing the symbol level.
      * Providing the priority of speech to be spoken.
      * Speaking both synchronously (blocking) and asynchronously (instant return).
    * `nvdaController_setOnSsmlMarkReachedCallback`: To register a callback of type `onSsmlMarkReachedFuncType` that is called in synchronous mode for every `<mark />` tag encountered in the SSML sequence provided to `nvdaController_speakSsml`.
  * Note: the new functions in the controller client only support NVDA 2024.1 and above.
* Updated `include` dependencies:
  * detours to `4b8c659f549b0ab21cf649377c7a84eb708f5e68`. (#15695)
  * ia2 to `3d8c7f0b833453f761ded6b12d8be431507bfe0b`. (#15695)
  * sonic to `8694c596378c24e340c09ff2cd47c065494233f1`. (#15695)
  * w3c-aria-practices to `9a5e55ccbeb0f1bf92b6127c9865da8426d1c864`. (#15695)
  * wil to `5e9be7b2d2fe3834a7107f430f7d4c0631f69833`. (#15695)
* Device info yielded by `hwPortUtils.listUsbDevices` now contain the bus reported description of the USB device (key `busReportedDeviceDescription`). (#15764, @LeonarddeR)
* For USB serial devices, `bdDetect.getConnectedUsbDevicesForDriver` and `bdDetect.getDriversForConnectedUsbDevices` now yield device matches containing a `deviceInfo` dictionary enriched with data about the USB device, such as `busReportedDeviceDescription`. (#15764, @LeonarddeR)
* When the configuration file `nvda.ini` is corrupted, a backup copy is saved before it is reinitialized. (#15779, @CyrilleB79)
* When defining a script with the script decorator, the `speakOnDemand` boolean argument can be specified to control if a script should speak while in "on-demand" speech mode. (#481, @CyrilleB79)
  * Scripts that provide information (e.g. say window title, report time/date) should speak in the "on-demand" mode.
  * Scripts that perform an action (e.g. move the cursor, change a parameter) should not speak in the "on-demand" mode.
* Fixed bug where deleting git-tracked files during `scons -c` resulted in missing UIA COM interfaces on rebuild. (#7070, #10833, @hwf1324)
* Fix a bug where some code changes were not detected when building `dist`, that prevented a new build from being triggered.
Now `dist` always rebuilds. (#13372, @hwf1324)
* A `gui.nvdaControls.MessageDialog` with default type of standard, no longer throws a None conversion exception because no sound is assigned. (#16223, @XLTechie)

#### API Breaking Changes

These are breaking API changes.
Please open a GitHub issue if your Add-on has an issue with updating to the new API.

* NVDA is now built with Python 3.11. (#12064)
* Updated pip dependencies:
  * configobj to 5.1.0dev commit `e2ba4457c4651fa54f8d59d8dcdd3da950e956b8`. (#15544)
  * Comtypes to 1.2.0. (#15513, @codeofdusk)
  * Flake8 to 4.0.1. (#15636, @lukaszgo1)
  * py2exe to 0.13.0.1dev commit `4e7b2b2c60face592e67cb1bc935172a20fa371d`. (#15544)
  * robotframework to 6.1.1. (#15544)
  * SCons to 4.5.2. (#15529, @LeonarddeR)
  * sphinx to 7.2.6. (#15544)
  * wxPython to 4.2.2a commit `0205c7c1b9022a5de3e3543f9304cfe53a32b488`. (#12551, #16257)
* Removed pip dependencies:
  * typing_extensions, these should be supported natively in Python 3.11 (#15544)
  * nose, instead unittest-xml-reporting is used to generate XML reports. (#15544)
* `IAccessibleHandler.SecureDesktopNVDAObject` has been removed.
Instead, when NVDA is running on the user profile, track the existence of the secure desktop with the extension point: `winAPI.secureDesktop.post_secureDesktopStateChange`. (#14488)
* `braille.BrailleHandler.handlePendingCaretUpdate` has been removed with no public replacement. (#15163, @LeonarddeR)
* `bdDetect.addUsbDevices and bdDetect.addBluetoothDevices` have been removed.
Braille display drivers should implement the `registerAutomaticDetection` class method instead.
That method receives a `DriverRegistrar` object on which the `addUsbDevices` and `addBluetoothDevices` methods can be used. (#15200, @LeonarddeR)
* The default implementation of the check method on `BrailleDisplayDriver` now requires both the `threadSafe` and `supportsAutomaticDetection` attributes to be set to `True`. (#15200, @LeonarddeR)
* Passing lambda functions to `hwIo.ioThread.IoThread.queueAsApc` is no longer possible, as functions should be weakly referenceable. (#14627, @LeonarddeR)
* `IoThread.autoDeleteApcReference` has been removed. (#14924, @LeonarddeR)
* To support capital pitch changes, synthesizers must now explicitly declare their support for the `PitchCommand` in the `supportedCommands` attribute on the driver. (#15433, @LeonarddeR)
* `speechDictHandler.speechDictVars` has been removed. Use `NVDAState.WritePaths.speechDictsDir` instead of `speechDictHandler.speechDictVars.speechDictsPath`. (#15614, @lukaszgo1)
* `languageHandler.makeNpgettext` and `languageHandler.makePgettext` have been removed.
`npgettext` and `pgettext` are supported natively now. (#15546)
* The app module for [Poedit](https://poedit.net) has been changed significantly. The `fetchObject` function has been removed. (#15313, #7303, @LeonarddeR)
* The following redundant types and constants have been removed from `hwPortUtils`: (#15764, @LeonarddeR)
  * `PCWSTR`
  * `HWND` (replaced by `ctypes.wintypes.HWND`)
  * `ULONG_PTR`
  * `ULONGLONG`
  * `NULL`
  * `GUID` (replaced by `comtypes.GUID`)
* `gui.addonGui.AddonsDialog` has been removed. (#15834)
* `touchHandler.TouchInputGesture.multiFingerActionLabel` has been removed with no replacement. (#15864, @CyrilleB79)
* `NVDAObjects.IAccessible.winword.WordDocument.script_reportCurrentHeaders` has been removed with no replacement. (#15904, @CyrilleB79)
* The following app modules are removed.
Code which imports from one of them, should instead import from the replacement module. (#15618, @lukaszgo1)

| Removed module name |Replacement module|
|---|---|
|`azardi-2.0` |`azardi20`|
|`azuredatastudio` |`code`|
|`azuredatastudio-insiders` |`code`|
|`calculatorapp` |`calculator`|
|`code - insiders` |`code`|
|`commsapps` |`hxmail`|
|`dbeaver` |`eclipse`|
|`digitaleditionspreview` |`digitaleditions`|
|`esybraille` |`esysuite`|
|`hxoutlook` |`hxmail`|
|`miranda64` |`miranda32`|
|`mpc-hc` |`mplayerc`|
|`mpc-hc64` |`mplayerc`|
|`notepad++` |`notepadPlusPlus`|
|`searchapp` |`searchui`|
|`searchhost` |`searchui`|
|`springtoolsuite4` |`eclipse`|
|`sts` |`eclipse`|
|`teamtalk3` |`teamtalk4classic`|
|`textinputhost` |`windowsinternal_composableshell_experiences_textinput_inputapp`|
|`totalcmd64` |`totalcmd`|
|`win32calc` |`calc`|
|`winmail` |`msimn`|
|`zend-eclipse-php` |`eclipse`|
|`zendstudio` |`eclipse`|

#### Deprecations

* Using `watchdog.getFormattedStacksForAllThreads` is deprecated - please use `logHandler.getFormattedStacksForAllThreads` instead. (#15616, @lukaszgo1)
* `easeOfAccess.canConfigTerminateOnDesktopSwitch` has been deprecated, as it became obsolete since Windows 7 is no longer supported. (#15644, @LeonarddeR)
* `winVersion.isFullScreenMagnificationAvailable` has been deprecated - use `visionEnhancementProviders.screenCurtain.ScreenCurtainProvider.canStart` instead. (#15664, @josephsl)
* The following Windows release constants has been deprecated from winVersion module (#15647, @josephsl):
  * `winVersion.WIN7`
  * `winVersion.WIN7_SP1`
  * `winVersion.WIN8`
* The `bdDetect.KEY_*` constants have been deprecated.
Use `bdDetect.DeviceType.*` instead. (#15772, @LeonarddeR).
* The `bdDetect.DETECT_USB` and `bdDetect.DETECT_BLUETOOTH` constants have been deprecated with no public replacement. (#15772, @LeonarddeR).
* Using `gui.ExecAndPump` is deprecated - please use `systemUtils.ExecAndPump` instead. (#15852, @lukaszgo1)

## 2023.3.4

This is a patch release to fix a security issue and installer issue.
Please responsibly disclose security issues following NVDA's [security policy](https://github.com/nvaccess/nvda/blob/master/security.md).

### Security Fixes

* Prevents loading custom configuration while secure mode is forced.
([GHSA-727q-h8j2-6p45](https://github.com/nvaccess/nvda/security/advisories/GHSA-727q-h8j2-6p45))

### Bug Fixes

* Fixed bug which caused the NVDA process to fail to exit correctly. (#16123)
* Fixed bug where if the previous NVDA process failed to exit correctly, an NVDA installation could fail to an unrecoverable state. (#16122)

## 2023.3.3

This is a patch release to fix a security issue.
Please responsibly disclose security issues following NVDA's [security policy](https://github.com/nvaccess/nvda/blob/master/security.md).

### Security Fixes

* Prevents possible reflected XSS attack from crafted content to cause arbitrary code execution.
([GHSA-xg6w-23rw-39r8](https://github.com/nvaccess/nvda/security/advisories/GHSA-xg6w-23rw-39r8))

## 2023.3.2

This is a patch release to fix a security issue.
The security patch in 2023.3.1 was not resolved correctly.
Please responsibly disclose security issues following NVDA's [security policy](https://github.com/nvaccess/nvda/blob/master/security.md).

### Security Fixes

* The security patch in 2023.3.1 was not resolved correctly.
Prevents possible system access and arbitrary code execution with system privileges for unauthenticated users.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3.1

This is a patch release to fix a security issue.
Please responsibly disclose security issues following NVDA's [security policy](https://github.com/nvaccess/nvda/blob/master/security.md).

### Security Fixes

* Prevents possible system access and arbitrary code execution with system privileges for unauthenticated users.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3

Questa versione include miglioramenti alle prestazioni, alla reattività e alla stabilità dell'uscita audio.
Sono state aggiunte opzioni per controllare il volume dei suoni e dei segnali acustici di NVDA o per fare in modo che siano identici al volume della voce.

NVDA ora può aggiornare periodicamente i risultati dell'OCR, pronunciando il nuovo testo man mano che appare.
Questo può essere configurato nella categoria OCR di Windows della finestra di dialogo delle impostazioni di NVDA.

Sono state apportate diverse correzioni al braille, migliorando il rilevamento del dispositivo e il movimento del cursore.
Ora è possibile escludere i driver indesiderati dal rilevamento automatico, per migliorarne le prestazioni.
Ci sono anche nuovi comandi BRLTTY.

Sono state apportate correzioni di bug anche per l'addon store, Microsoft Office, i menu contestuali di Microsoft Edge e la calcolatrice di Windows.

### Novità

* Miglioramenti nella gestione del suono:
  * Un nuovo pannello Impostazioni audio:
    * Può essere aperto con `NVDA+control+u`. (#15497)
    * Un'opzione nelle Impostazioni audio consente di fare in modo che il volume dei suoni e dei segnali acustici di NVDA segua l'impostazione del volume della voce. (#1409)
    * Un'opzione nelle impostazioni Audio per configurare separatamente il volume dei suoni di NVDA. (#1409, #15038)
    * Le impostazioni per modificare il dispositivo audio di uscita e per attivare/disattivare l'attenuazione audio sono state spostate dalla finestra seleziona sintetizzatore al nuovo pannello Impostazioni audio.
    Queste opzioni verranno rimosse dalla finestra di dialogo "seleziona sintetizzatore" nella versione 2024.1. (#15486, #8711)
  * NVDA adesso produrrà l'audio tramite Windows Audio Session API (WASAPI), che va a migliorare la reattività, le prestazioni e la stabilità del parlato e dei suoni di NVDA. (#14697, #11169, #11615, #5096, #10185, #11061)
  * Nota: WASAPI non è compatibile con alcuni componenti aggiuntivi.
  Sono disponibili aggiornamenti per questi componenti aggiuntivi, quindi è necessario effettuare l'aggiornamento per continuare ad usarli.
  Le versioni incompatibili di questi add-on verranno disabilitate durante l'aggiornamento di NVDA:
    * Tony's Enhancements versione 1.15 o precedente. (#15402)
    * NVDA global commands extension 12.0.8 o precedente. (#15443)
* NVDA è ora in grado di aggiornare continuamente il risultato durante l'esecuzione del riconoscimento ottico dei caratteri (OCR), pronunciando il nuovo testo man mano che compare. (#2797)
  * Per abilitare questa funzionalità, abilitare l'opzione "Aggiorna periodicamente il contenuto riconosciuto" nella categoria OCR di Windows della finestra di dialogo delle impostazioni di NVDA.
  * Una volta abilitata, è possibile attivare o disattivare la pronuncia del nuovo testo (premendo `NVDA+5`).
* Quando si utilizza il rilevamento automatico dei display Braille, è ora possibile disattivare il rilevamento dei driver dalla finestra di dialogo di selezione del display Braille. (#15196)
* Una nuova opzione nelle impostazioni di formattazione del documento, "Ignora le righe vuote nel segnalare i rientri". (#13394)
* Aggiunto un gesto non assegnato per navigare per raggruppamenti di schede in modalità navigazione. (#15046)

### Cambiamenti

* Braille:
  * Quando il testo in un terminale cambia senza aggiornare il cursore, il testo su un display braille ora si aggiornerà correttamente quando ci si posiziona su una riga modificata.
  Ciò è valido anche quando il braille segue il cursore di controllo. (#15115)
  * Vi sono ulteriori mappature per BRLTTY nei i comandi di NVDA (#6483):
    * `learn`: attiva/disattiva menu aiuto di NVDA
    * `prefmenu`: apre il menu NVDA
    * `prefload`/`prefsave`: Carica/salva la configurazione di NVDA
    * `time`: Mostra l'ora
    * `say_line`: Pronuncia la riga corrente in cui si trova il cursore di controllo
    * `say_below`: Dire tutto usando cursore di controllo
  * Il driver BRLTTY è disponibile solo quando è in esecuzione un'istanza BRLTTY con BrlAPI abilitata. (#15335)
  * L'impostazione avanzata per abilitare il supporto per HID braille è stata rimossa a favore di una nuova opzione.
  Ora si può disabilitare driver specifici per il rilevamento automatico del display Braille nella finestra di dialogo selezione del display Braille. (#15196)
* Add-on Store: I componenti aggiuntivi installati verranno ora elencati nella scheda Componenti aggiuntivi disponibili, se presenti nello store. (#15374)
* Alcuni tasti di scelta rapida sono stati aggiornati nel menu di NVDA. (#15364)

### Bug Corretti

* Microsoft Office:
  * Risolto il problema relativo al crash in Microsoft Word quando le opzioni di formattazione documento "leggi intestazioni" e "leggi note e commenti" non erano abilitate. (#15019)
  * In Word ed Excel, l'allineamento del testo verrà segnalato correttamente in più situazioni. (#15206, #15220)
  * Risolve la lettura di alcune scorciatoie per la formattazione delle celle in Excel. (#15527)
* Microsoft Edge:
  * NVDA non tornerà più all'ultima posizione della modalità navigazione quando si apre il menu contestuale in Microsoft Edge. (#15309)
  * NVDA è nuovamente in grado di leggere i menu contestuali dei download in Microsoft Edge. (#14916)
* Braille:
  * Il cursore braille e gli indicatori di selezione verranno ora sempre aggiornati correttamente dopo aver mostrato o nascosto i rispettivi indicatori con un gesto. (#15115)
  * Risolto un bug per cui i display braille Albatross tentavano di inizializzarsi anche se era collegato un altro dispositivo braille. (#15226)
* Add-on Store:
  * Risolto bug per cui deselezionando "includi componenti aggiuntivi incompatibili", essi risultavano ancora elencati nello store. (#15411)
  * Gli add-on bloccati per motivi di compatibilità ora dovrebbero essere filtrati correttamente quando si attiva/disattiva il filtro per lo stato (#15416)
  * Risolto un bug che impediva l'aggiornamento o la sostituzione di componenti aggiuntivi incompatibili abilitati sovrascritti utilizzando lo strumento di installazione esterno. (#15417)
  * Risolto un bug per cui NVDA non parlava più fino al riavvio, dopo l'installazione del componente aggiuntivo. (#14525)
  * Risolto un bug per cui i componenti aggiuntivi non venivano installati a causa di un errore nel download o di  annullamento dello stesso (#15469)
  * Risolti i problemi relativi alla gestione dei componenti aggiuntivi incompatibili durante l'aggiornamento di NVDA. (#15414, #15412, #15437)
* NVDA è di nuovo in grado di annunciare i risultati dei calcoli nella calcolatrice Windows a 32 bit sulle versioni Server, LTSC e LTSB di Windows. (#15230)
* NVDA non ignora più i cambiamenti di focus quando una finestra nidificata (finestra figlia) viene messa a fuoco. (#15432)
* Risolta una potenziale causa di arresto anomalo durante l'avvio di NVDA. (#15517)

### Changes for Developers

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* `braille.handler.handleUpdate` and `braille.handler.handleReviewMove` have been changed in order not to update instantly.
Before this change, when either of these methods was called very often, this would drain many resources.
These methods now queue an update at the end of every core cycle instead.
They should also be thread safe, making it possible to call them from background threads. (#15163)
* Added official support to register custom braille display drivers in the automatic braille display detection process.
Consult the `braille.BrailleDisplayDriver` class documentation for more details.
Most notably, the `supportsAutomaticDetection` attribute must be set to `True` and the `registerAutomaticDetection` `classmethod` must be implemented.  (#15196)

#### Deprecations

* `braille.BrailleHandler.handlePendingCaretUpdate` is now deprecated with no public replacement.
It will be removed in 2024.1. (#15163)
* Importing the constants `xlCenter`, `xlJustify`, `xlLeft`, `xlRight`, `xlDistributed`, `xlBottom`, `xlTop` from `NVDAObjects.window.excel` is deprecated.
Use `XlHAlign` or `XlVAlign` enumerations instead. (#15205)
* The mapping `NVDAObjects.window.excel.alignmentLabels` is deprecated.
Use the `displayString` methods of `XlHAlign` or `XlVAlign` enumerations instead. (#15205)
* `bdDetect.addUsbDevices` and `bdDetect.addBluetoothDevices` have been deprecated.
Braille display drivers should implement the `registerAutomaticDetection` classmethod instead.
That method receives a `DriverRegistrar` object on which the `addUsbDevices` and `addBluetoothDevices` methods can be used. (#15200)
* The default implementation of the check method on `BrailleDisplayDriver` uses `bdDetect.driverHasPossibleDevices` for devices that are marked as thread safe.
Starting from NVDA 2024.1, in order for the base method to use `bdDetect.driverHasPossibleDevices`, the `supportsAutomaticDetection` attribute must be set to `True` as well. (#15200)

## 2023.2

Questa versione introduce l'Add-on Store, che va a sostituire il vecchio gestore componenti aggiuntivi.
Nell'add-On Store è possibile sfogliare, cercare, installare e aggiornare i componenti aggiuntivi della community.
Si possono inoltre ignorare manualmente i problemi di incompatibilità con i componenti aggiuntivi obsoleti a proprio rischio e pericolo.

Sono disponibili nuove funzionalità per il braille, comandi aggiuntivi e supporto per nuovi modelli.
Vi sono anche nuovi gesti e tasti rapidi per la navigazione ad oggetti e l'OCR.
Migliorati l'esplorazione e il rilevamento della formattazione nei documenti in Microsoft Office.

Vi sono molte correzioni di bug, in particolare per braille, Microsoft Office, browser Web e Windows 11.

Come sempre, aggiornati eSpeak-NG, LibLouis braille translator, e Unicode CLDR.

### Novità

* Realizzato un Add-on Store per NVDA. (#13985)
  * Sfoglia, cerca, installa e aggiorna i componenti aggiuntivi della community.
  * risolvi manualmente i problemi di incompatibilità con i componenti aggiuntivi obsoleti, con possibilità di abilitarli ugualmente.
  * Il Gestore dei componenti aggiuntivi è stato rimosso e sostituito dall'add-on store.
  * Per ulteriori informazioni, leggere la guida utente aggiornata.
* Nuovi gesti di immissione:
  * Un gesto non associato per scorrere tra le lingue disponibili dell'OCR di Windows. (#13036)
  * Un gesto non associato per passare tra le modalità di visualizzazione dei messaggi in braille. (#14864)
  * Un gesto non associato per attivare o disattivare l'indicatore di selezione per il braille. (#14948)
  * Un gesto associato per spostarsi tra gli oggetti in modalità semplificata senza tener conto della gerarchia.  (#15053)
    * Desktop: `NVDA+9TastierinoNumerico` e `NVDA+3TastierinoNumerico` per passare rispettivamente all'oggetto precedente e successivo.
    * Laptop: `shift+NVDA+à` e `shift+NVDA+ù` per passare rispettivamente all'oggetto precedente e successivo.
* Nuove funzioni braille:
  * Aggiunto il supporto per il display Braille Help Tech Activator. (#14917)
  * Una nuova opzione Braille per attivare o disattivare l'indicatore di selezione (punti 7 e 8). (#14948)
  * Una nuova opzione per spostare il cursore di sistema tramite cursor routing anche quando il braille segue il cursore di controllo. (#14885, #3166)
  * Quando si preme `2 del tastierino numerico` tre volte per ascoltare il valore numerico del carattere alla posizione del cursore di controllo, l'informazione è ora fornita anche in braille. (#14826)
  * Aggiunto il supporto per l'attributo `aria-brailleroledescripti\on` ARIA 1.3, che consente ai webmaster di sovrascrivere il tipo di un elemento mostrato sul display Braille. (#14748)
  * Driver Baum Braille: aggiunti diversi gesti per l'esecuzione di comandi comuni da tastiera come `windows+d`, `alt+tab` ecc.
  Fare riferimento alla guida utente di NVDA per un elenco completo. (#14714)
* Aggiunta pronuncia dei nuovi simboli Unicode:
  * simboli braille quali `⠐⠣⠃⠗⠇⠐⠜`. (#14548)
  * Simbolo del tasto Opzione Mac `⌥`. (#14682)
* Aggiunti gesti per i display Braille di Tivomatic Caiku Albatross. (#14844, #15002)
  * mostra la finestra di dialogo impostazioni braille
  * Accedere alla barra di stato
  * Passare tra le varie forme del cursore braille
  * passare tra le modalità di visualizzazione dei messaggi in braille
  * attivare/disattivare il cursore braille
  * Attivare/disattivare la visualizzazione dell'indicatore di selezione in braille
  * spostare il cursore di sistema tramite cursor routing anche quando il braille segue il cursore di controllo.
* Novità Microsoft Office:
  * Nella finestra impostazioni formattazione documento, se la casella di controllo testo evidenziato risulta attiva, i colori di evidenziazione vengono ora riportati in Microsoft Word. (#7396, #12101, #5866)
  * Nella finestra impostazioni formattazione documento, se la casella di controllo colori è attiva, in Microsoft Word vengono annunciati anche i colori di sfondo. (#5866)
  * NVDA ora è in grado di segnalare correttamente i cambiamenti di formattazione dovuti alla pressione delle combinazioni di tasti che vanno ad attivare o disattivare aspetti in una cella quali grassetto, corsivo, sottolineato e barrato. (#14923)
* Gestione del suono avanzata e sperimentale:
  * NVDA ora emette l'audio tramite Windows Audio Session API (WASAPI), che può migliorare la reattività, le prestazioni e la stabilità del parlato e dei suoni di NVDA. (#14697)
  * L'utilizzo di WASAPI può essere abilitato nelle Impostazioni avanzate.
  Inoltre, se WASAPI è abilitato, possono essere configurate anche le seguenti impostazioni avanzate.
    * Un'opzione che consente al volume dei suoni e dei beep di NVDA di seguire l'impostazione del volume della voce in uso. (#1409)
    * Un'opzione che consente di separare il volume della voce da quello dei suoni e di gestirli separatamente. (#1409, #15038)
  * Esiste un problema noto che provoca arresti anomali casuali quando WASAPI è abilitato. (#15150)
* In Mozilla Firefox e Google Chrome, NVDA ora segnala se un controllo apre una finestra di dialogo, una griglia, un elenco o un albero, purché l'autore lo abbia specificato utilizzando `aria-haspopup`. (#14709)
* Ora è possibile utilizzare variabili di sistema (come `%temp%` o `%homepath%`) quando si specifica il percorso durante la creazione di copie portable di NVDA. (#14680)
* In Windows 10 May 2019 Update e versioni successive, NVDA è in grado di leggere i nomi dei desktop virtuali durante l'apertura, la modifica e la chiusura. (#5641)
* È stato aggiunto un parametro a livello di sistema per consentire agli utenti e agli amministratori di forzare l'avvio di NVDA in modalità protetta. (#10018)

### Cambiamenti

* Aggiornamenti dei componenti:
  * eSpeak NG è stata aggiornata a 1.52-dev commit `ed9a7bcf`. (#15036)
  * Aggiornato LibLouis braille translator alla versione [3.26.0](https://github.com/liblouis/liblouis/releases/tag/v3.26.0). (#14970)
  * CLDR aggiornato alla versione 43.0. (#14918)
* Cambiamenti per LibreOffice:
  * In LibreOffice Writer, versione maggiore o guale alla 7.6, quando viene annunciata la posizione del cursore di controllo, la posizione del cursore di sistema sarà segnalata in relazione alla pagina attuale, similmente a ciò che avviene per Microsoft Word. (#11696)
  * Funziona regolarmente la lettura della barra di stato (ad esempio invocata con i tasti `NVDA+fine`). (#11698)
  * Se ci si sposta su una cella diversa in LibreOffice Calc, NVDA non annuncia più erroneamente le coordinate della cella precedente quando la lettura delle coordinate della cella è disabilitata nelle impostazioni di NVDA. (#15098)
* Cambiamenti per il braille:
  * Quando si utilizza un display Braille tramite il driver braille HID standard, ci si può servire anche del dPad per emulare i tasti freccia e invio.
  Anche `spazio+punto1` e `spazio+punto4` ora sono mappati rispettivamente alla freccia su e giù. (#14713)
  * Gli aggiornamenti ai contenuti web dinamici (regioni live ARIA) possono ora essere visualizzati in braille.
  La funzione è disattivabile dalle impostazioni avanzate. (#7756)
* I simboli trattino e trattino lungo verranno sempre inviati al sintetizzatore. (#13830)
* La lettura della distanza in Microsoft Word ora rispetterà l'unità definita nelle opzioni avanzate di Word, anche quando si utilizza UIA per accedere ai documenti di Word. (#14542)
* NVDA risponde più velocemente quando si sposta il cursore nei controlli editazione. (#14708)
* Lo script che legge la destinazione di un link ora fa riferimento alla posizione del cursore di sistema, non del navigatore ad oggetti. (#14659)
* La creazione di una copia portable non richiede più l'immissione di una lettera di unità come parte del percorso assoluto. (#14681)
* Se Windows è configurato per visualizzare i secondi nell'orologio della barra delle applicazioni, il comando `NVDA+f12` ora rispetta tale impostazione. (#14742)
* NVDA ora leggerà i gruppi senza etichetta che contengono informazioni utili sulla posizione, come nelle recenti versioni dei menu di Microsoft Office 365. (#14878)

### Bug Corretti

* Braille:
  * Diverse correzioni sulla gestione input/output braille, mirate a rendere meno frequenti eventuali errori e crash di NVDA. (#14627)
  * NVDA non attiverà più inutilmente la funzione "nessun display braille" più volte durante il rilevamento automatico, il che consente di disporre di un log più pulito. (#14524)
  * NVDA utilizzerà la connessione via USB nel caso in cui  venga rilevato automaticamente un dispositivo HID Bluetooth (come ad esempio HumanWare Brailliant o APH Mantis)  e diventi disponibile una connessione USB.
  In precedenza funzionava solo per le porte seriali Bluetooth. (#14524)
  * Quando non è collegato alcun display braille e il visualizzatore braille viene chiuso premendo `alt+f4` o facendo clic sul pulsante di chiusura, la dimensione del display del sottosistema braille verrà nuovamente reimpostata su nessuna cella. (#15214)
* Browser Web:
  * NVDA non provoca più occasionalmente l'arresto anomalo o il blocco di Mozilla Firefox. (#14647)
  * In Mozilla Firefox e Google Chrome, non vengono più annunciati i caratteri digitati in alcune caselle di testo anche quando la lettura dei caratteri digitati è disattivata. (#8442)
  * Ora è possibile utilizzare la modalità  navigazione nei controlli Chromium Embedded, laddove in precedenza NVDA falliva. (#13493, #8553)
  * In Mozilla Firefox, viene annunciato correttamente il testo quando si sposta il mouse su di un testo dopo un collegamento. (#9235)
  * La destinazione dei collegamenti grafici è ora segnalata con precisione nella maggior parte dei casi in Chrome e Edge. (#14783)
  * NVDA non rimane più in silenzio nel segnalare l'URL di un collegamento senza un attributo href.
  Piuttosto, annuncerà che il collegamento non ha destinazione. (#14723)
  * In modalità navigazione, NVDA non ignorerà più erroneamente il focus dando priorità invece ad un controllo genitore o figlio, ad es. passando da un controllo alla sua voce di elenco padre o cella della griglia. (#14611)
    * Si noti tuttavia che questa correzione si applica solo quando l'opzione "Modalità focus automatica per i cambiamenti del focus" nelle impostazioni navigazione è disattivata (che è il valore predefinito).
* Correzioni per Windows 11:
  * NVDA è di nuovo in grado di leggere il contenuto della barra di stato del Blocco note. (#14573)
  * Quando si passa tra le schede in BloccoNote ed Esplora file, NVDA ne leggerà il nome e la nuova posizione. (#14587, #14388)
  * NVDA è in grado nuovamente di leggere gli elementi suggeriti quando si inserisce il testo in lingue come il cinese e il giapponese. (#14509)
  * È nuovamente possibile aprire le voci "Collaboratori" e "Licenza" nel menu Aiuto di NVDA. (#14725)
* Correzioni di Microsoft Office:
  * Quando ci si sposta rapidamente tra le celle in Excel, ora è meno probabile che NVDA segnali la cella o la selezione sbagliata. (#14983, #12200, #12108)
  * Quando si giunge su una cella di Excel da un'altra posizione al di fuori del foglio di lavoro, il visualizzatore Braille e l'evidenziatore del focus non vengono più aggiornati in modo superfluo all'oggetto che aveva il focus in precedenza, migliorando così l'esperienza dell'utente. (#15136)"
  * NVDA non ha più difficoltà nel segnalare quando il focus si trova sui campi password  in Microsoft Excel e Outlook. (#14839)
* Per quei simboli che non dispongono di una descrizione nella lingua in uso, verrà utilizzata quella predefinita in inglese. (#14558, #14417)
* È ora possibile utilizzare il carattere barra rovesciata nel campo di sostituzione di una voce di dizionario, quando il tipo non è impostato su espressione regolare. (#14556)
* Nella calcolatrice di Windows 10 e 11, non verranno più riprodotti toni d'errore da una copia portable di NVDA, quando si immettono espressioni standard in modalità visualizzazione compatta. (#14679)
* NVDA gestisce correttamente molte situazioni, come applicazioni che smettono di rispondere, e che in precedenza ne causavano il blocco completo. (#14759)
* Quando si forza il supporto UIA con determinati terminali e console, è stato corretto un bug che causava il blocco e riempiva il file di log. (#14689)
* NVDA non si rifiuterà più di salvare la configurazione dopo che quest'ultima è stata ripristinata. (#13187)
* Quando si esegue una versione temporanea dal programma di avvio, NVDA non indurrà gli utenti a pensare di poter salvare la configurazione. (#14914)
* NVDA ora risponde leggermente più velocemente ai comandi e alle operazioni con il focus. (#14928)
* La visualizzazione delle impostazioni OCR non provocherà più errori su alcuni sistemi. (#15017)
* Risolto un bug relativo al salvataggio e al caricamento della configurazione di NVDA, incluso il cambio di sintetizzatore. (#14760)
* Risolto un bug inerente il comando touch di revisione "scorri su": si spostava erroneamente per pagine, invece di andare alla riga precedente. (#15127)

### Cambiamenti per sviluppatori, in inglese

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* Suggested conventions have been added to the add-on manifest specification.
These are optional for NVDA compatibility, but are encouraged or required for submitting to the Add-on Store. (#14754)
  * Use `lowerCamelCase` for the name field.
  * Use `<major>.<minor>.<patch>` format for the version field (required for add-on datastore).
  * Use `https://` as the schema for the url field (required for add-on datastore).
* Added a new extension point type called `Chain`, which can be used to iterate over iterables returned by registered handlers. (#14531)
* Added the `bdDetect.scanForDevices` extension point.
Handlers can be registered that yield `BrailleDisplayDriver/DeviceMatch` pairs that don't fit in existing categories, like USB or Bluetooth. (#14531)
* Added extension point: `synthDriverHandler.synthChanged`. (#14618)
* The NVDA Synth Settings Ring now caches available setting values the first time they're needed, rather than when loading the synthesizer. (#14704)
* You can now call the export method on a gesture map to export it to a dictionary.
This dictionary can be imported in another gesture by passing it either to the constructor of `GlobalGestureMap` or to the update method on an existing map. (#14582)
* `hwIo.base.IoBase` and its derivatives now have a new constructor parameter to take a `hwIo.ioThread.IoThread`.
If not provided, the default thread is used. (#14627)
* `hwIo.ioThread.IoThread` now has a `setWaitableTimer` method to set a waitable timer using a python function.
Similarly, the new `getCompletionRoutine` method allows you to convert a python method into a completion routine safely. (#14627)
* `offsets.OffsetsTextInfo._get_boundingRects` should now always return `List[locationHelper.rectLTWH]` as expected for a subclass of `textInfos.TextInfo`. (#12424)
* `highlight-color` is now a format field attribute. (#14610)
* NVDA should more accurately determine if a logged message is coming from NVDA core. (#14812)
* NVDA will no longer log inaccurate warnings or errors about deprecated appModules. (#14806)
* All NVDA extension points are now briefly described in a new, dedicated chapter in the Developer Guide. (#14648)
* `scons checkpot` will no longer check the `userConfig` subfolder anymore. (#14820)
* Translatable strings can now be defined with a singular and a plural form using `ngettext` and `npgettext`. (#12445)

#### Deprecations

* Passing lambda functions to `hwIo.ioThread.IoThread.queueAsApc` is deprecated.
Instead, functions should be weakly referenceable. (#14627)
* Importing `LPOVERLAPPED_COMPLETION_ROUTINE` from `hwIo.base` is deprecated.
Instead import from `hwIo.ioThread`. (#14627)
* `IoThread.autoDeleteApcReference` is deprecated.
It was introduced in NVDA 2023.1 and was never meant to be part of the public API.
Until removal, it behaves as a no-op, i.e. a context manager yielding nothing. (#14924)
* `gui.MainFrame.onAddonsManagerCommand` is deprecated, use `gui.MainFrame.onAddonStoreCommand` instead. (#13985)
* `speechDictHandler.speechDictVars.speechDictsPath` is deprecated, use `NVDAState.WritePaths.speechDictsDir` instead. (#15021)
* Importing `voiceDictsPath` and `voiceDictsBackupPath` from `speechDictHandler.dictFormatUpgrade` is deprecated.
Instead use `WritePaths.voiceDictsDir` and `WritePaths.voiceDictsBackupDir` from `NVDAState`. (#15048)
* `config.CONFIG_IN_LOCAL_APPDATA_SUBKEY` is deprecated.
Instead use `config.RegistryKey.CONFIG_IN_LOCAL_APPDATA_SUBKEY`. (#15049)

## 2023.1

È stata aggiunta una nuova opzione, "Stile paragrafo" in "Navigazione documento".
Può essere utilizzata con quegli editor di testo che non supportano la navigazione tra paragrafi in modo nativo, come Notepad e Notepad++.

Introdotto un nuovo comando globale per fornire la destinazione di un link, corrispondente alla combinazione di tasti `NVDA+k`.

Migliorato il supporto per i contenuti Web con annotazioni (come commenti e note a piè di pagina).
è possibile premere `NVDA+d` più volte per ascoltare i vari riepiloghi in presenza di annotazioni (ad esempio contiene commenti, contiene note a piè di pagina).

Introdotto il supporto per i display braille Tivomatic Caiku Albatross 46/80.

Migliorato anche il supporto per le versioni ARM64 e AMD64 di Windows.

Sono stati risolti anche molti bug soprattutto inerenti a windows11..

Come sempre, eSpeak, LibLouis, Sonic rate boost e Unicode CLDR sono stati aggiornati.
Miglioramenti sul fronte braille con l'introduzione di tabelle quali georgiano, swahili (Kenya) e chichewa (Malawi).

Nota:

* Questa versione interrompe la compatibilità con i componenti aggiuntivi esistenti.

### Novità

* Microsoft Excel tramite UI Automation: annuncio automatico delle intestazioni di colonne e righe nelle tabelle. (#14228)
  * Nota: Si riferisce alle tabelle formattate tramite il pulsante "Tabella" nel riquadro Inserisci della barra multifunzione.
  "Prima colonna" e "intestazione riga" nelle "Opzioni Stile Tabella" corrispondono alle rispettive intestazioni di righe e colonne.
  * Questo non si riferisce alle intestazioni specifiche dello screen reader tramite intervalli nominati, che attualmente non sono supportati tramite UI Automation..
* È stato aggiunto uno script non assegnato per passare tra le descrizioni ritardate dei caratteri. (#14267)
* Aggiunta un'opzione sperimentale per sfruttare il supporto di notifica UIA in Windows Terminal per segnalare testo nuovo o modificato nel terminale, con conseguente miglioramento della stabilità e della reattività. (#13781)
  * Consultare la guida utente per leggere le limitazioni di questa opzione sperimentale.
* Su Windows 11 ARM64, è ora disponibile la modalità di navigazione nelle app AMD64 come Firefox, Google Chrome e 1Password. (#14397)
* È stata aggiunta una nuova opzione, "Stile paragrafo" in "Navigazione documento".
Ciò aggiunge il supporto per la navigazione di paragrafo con interruzione di riga singola (normale) e interruzione di riga multipla (blocco).
Può essere utilizzato con editor di testo che non supportano la navigazione tra paragrafi in modo nativo, come Notepad e Notepad++. (#13797)
* Viene ora segnalata la presenza di più annotazioni.
Se un'origine ha più di un'annotazione, ora è possibile passarle in rassegna con il comando `NVDA+d`.
Ad esempio, quando al testo sono associati un commento e una nota a piè di pagina, usare questo comando per leggerle in successione. (#14507, #14480)
* Aggiunto il supporto per i display braille Tivomatic Caiku Albatross 46/80. (#13045)
* introdotto un nuovo comando globale per fornire la destinazione di un link, corrispondente alla combinazione di tasti `NVDA+k`.
Una pressione singola segnalerà tramite sintesi vocale e braille la destinazione del link su cui è situato il navigatore ad oggetti.
La doppia pressione presenterà il contenuto in una finestra, per una più agevole consultazione (#14583)
* Nuovo comando globale non assegnato (categoria strumenti): Mostra la destinazione di un link in una finestra.
è come premere `NVDA+k` due volte, ma può essere più utile per gli utenti che si servono di display braille. (#14583)

### Cambiamenti

* Aggiornato LibLouis braille translator to [3.24.0](https://github.com/liblouis/liblouis/releases/tag/v3.24.0). (#14436)
  * Grosse migliorie per Ungherese, UEB, e Cinese bopomofo.
  * Supporto per lo standard braille danese 2022.
  * Nuove tabelle braille per il braille letterario georgiano, swahili (Kenya) e chichewa (Malawi).
* Aggiornate librerie Sonic rate boost alla commit `1d70513`. (#14180)
* CLDR è stato aggiornato alla versione 42.0. (#14273)
* Aggiornata eSpeak NG alla commit 1.52-dev commit `a51235aa`. (#14281)
  * Risolto il problema con la segnalazione di grandi numeri. (#14241)
* Le applicazioni Java dotate di controlli selezionabili informeranno l'utente quando un elemento non è selezionato; in precedenza il controllo veniva segnalato sempre come selezionato. (#14336)

### Bug risolti

* Correzioni per Windows 11:
  * NVDA segnalerà i momenti salienti della ricerca quando si preme il tasto start (esempio, oggi è Sant'Anselmo). (#13841)
  * In ARM, le app x64 non sono più identificate come applicazioni ARM64. (#14403)
  * è possibile accedere alle funzioni appartenenti alla cronologia del menu appunti come "fissa elemento" (#14508)
  * In Windows 11 22H2 e versioni successive, è nuovamente possibile servirsi del mouse e del tocco per interagire con aree quali la finestra di overflow della barra delle applicazioni e la finestra di dialogo "Apri con". (#14538, #14539)
* Vengono segnalati i suggerimenti quando si digita una @menzione nei commenti di Microsoft Excel. (#13764)
* Nella barra degli indirizzi di Google Chrome, i controlli dei suggerimenti (passa alla scheda, rimuovi suggerimento ecc.) vengono ora segnalati se selezionati. (#13522)
* Quando vengono richieste informazioni di formattazione, saranno esplicitamente annunciati i colori reali in WordPad e Visualizzatore Log  piuttosto di quello predefinito, . (#13959)
* In Firefox, l'attivazione del pulsante "Mostra opzioni" nelle pagine Issues di GitHub ora funziona in modo affidabile. (#14269)
* Nella finestra di dialogo Ricerca avanzata di Outlook 2016/365, è possibile conoscere l'etichetta e il valore dei controlli di selezione di data/ora. (#12726)
* In Firefox, Chrome e Edge, i controlli Aria segnalati come "interruttori" vengono ora trattati come tali piuttosto che caselle di controllo. (#11310)
* NVDA annuncerà automaticamente lo stato di ordinamento dell'intestazione di una colonna di tabella HTML se modificato premendo un pulsante interno. (#10890)
* Verrà sempre annunciato il nome del punto di riferimento o di una regione quando ci si arriva dall'esterno usando un tasto di navigazione veloce o tramite il focus. (#13307)
* Se sono attivate le funzioni "leggi cap prima delle maiuscole" oppure "emetti un beep per le maiuscole" con la descrizione ritardata dei caratteri, NVDA non emetterà più due volte il segnale acustico, né dirà la parola "cap" due volte. (#14239)
* NVDA ora segnalerà in modo più accurato i controlli nelle tabelle per le applicazioni Java. (#14347)
* Non ci saranno più differenze inattese nelle impostazioni quando si utilizzano più profili. (#14170)
  * In particolare, Sono stati risolti problemi con le seguenti impostazioni:
    * Rientri riga nelle impostazioni formattazione documento.
    * Bordi della cella nelle impostazioni formattazione documento.
    * Mostra messaggi nelle impostazioni braille
    * Inseguimento Braille nelle impostazioni braille
  * In alcuni rari casi, queste impostazioni utilizzate nei profili potrebbero essere modificate per errore durante l'installazione di questa versione di NVDA.
  * Si consiglia di controllare queste opzioni nei profili dopo aver aggiornato NVDA a questa versione.
* Le emoji saranno annunciate in più lingue. (#14433)
* La presenza di un'annotazione non viene più omessa in braille per alcuni elementi. (#13815)
* Risolto un problema in cui le modifiche alla configurazione non venivano salvate correttamente quando si passava da un'opzione "Predefinita" al valore dell'opzione "Predefinita". (#14133)
* Durante la configurazione di NVDA, ci sarà sempre almeno un tasto definito come tasto NVDA. (#14527)
* Se si accede al menu di NVDA tramite l'area di notifica, non verrà più suggerito un aggiornamento in sospeso qualora non ve ne siano di disponibili. (#14523)
* Viene segnalato correttamente per i file audio più lunghi di un giorno in Foobar2000 il tempo rimanente, trascorso e totale (#14127)
* Nei browser quali Chrome e Firefox, vengono mostrati anche in braille oltre ad essere annunciati alcuni avvisi quali il completamento del download di un file. (#14562)
* Risolto un bug nella navigazione della prima e l'ultima colonna in una tabella in Firefox (#14554)
* Quando NVDA viene eseguito con il parametro `--lang=Windows`, è nuovamente possibile aprire la finestra di dialogo Impostazioni generali di NVDA. (#14407)
* NVDA non interrompe più la lettura su Kindle per PC dopo aver voltato pagina. (#14390)

### Changes for Developers

Note: this is an Add-on API compatibility breaking release.
Add-ons will need to be re-tested and have their manifest updated.
Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* System test should now pass when run locally on non-English systems. (#13362)
* In Windows 11 on ARM, x64 apps are no longer identified as ARM64 applications. (#14403)
* It is no longer necessary to use `SearchField` and `SuggestionListItem` `UIA` `NVDAObjects` in new UI Automation scenarios, where automatic reporting of search suggestions, and where typing has been exposed via UI Automation with the `controllerFor` pattern.
This functionality is now available generically via `behaviours.EditableText` and the base `NVDAObject` respectively. (#14222)
* The UIA debug logging category when enabled now produces significantly more logging for UIA event handlers and utilities. (#14256)
* NVDAHelper build standards updated. (#13072)
  * Now uses the C++20 standard, was C++17.
  * Now uses the `/permissive-` compiler flag which disables permissive behaviors, and sets the `/Zc` compiler options for strict conformance.
* Some plugin objects (e.g. drivers and add-ons) now have a more informative description in the NVDA python console. (#14463)
* NVDA can now be fully compiled with Visual Studio 2022, no longer requiring the Visual Studio 2019 build tools. (#14326)
* More detailed logging for NVDA freezes to aid debugging. (#14309)
* The singleton `braille._BgThread` class has been replaced with `hwIo.ioThread.IoThread`. (#14130)
  * A single instance `hwIo.bgThread` (in NVDA core) of this class provides background i/o for thread safe braille display drivers.
  * This new class is not a singleton by design, add-on authors are encouraged to use their own instance when doing hardware i/o.
* The processor architecture for the computer can be queried from `winVersion.WinVersion.processorArchitecture attribute.` (#14439)
* New extension points have been added. (#14503)
  * `inputCore.decide_executeGesture`
  * `tones.decide_beep`
  * `nvwave.decide_playWaveFile`
  * `braille.pre_writeCells`
  * `braille.filter_displaySize`
  * `braille.decide_enabled`
  * `braille.displayChanged`
  * `braille.displaySizeChanged`
* It is possible to set useConfig to False on supported settings for a synthesizer driver. (#14601)

#### API Breaking Changes

These are breaking API changes.
Please open a GitHub issue if your Add-on has an issue with updating to the new API.

* The configuration specification has been altered, keys have been removed or modified:
  * In `[documentFormatting]` section (#14233):
    * `reportLineIndentation` stores an int value (0 to 3) instead of a boolean
    * `reportLineIndentationWithTones` has been removed.
    * `reportBorderStyle` and `reportBorderColor` have been removed and are replaced by `reportCellBorders`.
  * In `[braille]` section (#14233):
    * `noMessageTimeout` has been removed, replaced by a value for `showMessages`.
    * `messageTimeout` cannot take the value 0 anymore, replaced by a value for `showMessages`.
    * `autoTether` has been removed; `tetherTo` can now take the value "auto" instead.
  * In `[keyboard]` section  (#14528):
    * `useCapsLockAsNVDAModifierKey`, `useNumpadInsertAsNVDAModifierKey`, `useExtendedInsertAsNVDAModifierKey` has been removed.
    They are replaced by `NVDAModifierKeys`.
* The `NVDAHelper.RemoteLoader64` class has been removed with no replacement. (#14449)
* The following functions in `winAPI.sessionTracking` are removed with no replacement. (#14416, #14490)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`
* It is no longer possible to enable/disable the braille handler by setting `braille.handler.enabled`.
To disable the braille handler programatically, register a handler to `braille.handler.decide_enabled`. (#14503)
* It is no longer possible to update the display size of the handler by setting `braille.handler.displaySize`.
To update the displaySize programatically, register a handler to `braille.handler.filter_displaySize`.
Refer to `brailleViewer` for an example on how to do this. (#14503)
* There have been changes to the usage of `addonHandler.Addon.loadModule`. (#14481)
  * `loadModule` now expects dot as a separator, rather than backslash.
  For example "lib.example" instead of "lib\example".
  * `loadModule` now raises an exception when a module can't be loaded or has errors, instead of silently returning `None` without giving information about the cause.
* The following symbols have been removed from `appModules.foobar2000` with no direct replacement. (#14570)
  * `statusBarTimes`
  * `parseIntervalToTimestamp`
  * `getOutputFormat`
  * `getParsingFormat`
* The following are no longer singletons - their get method has been removed.
Usage of `Example.get()` is now `Example()`. (#14248)
  * `UIAHandler.customAnnotations.CustomAnnotationTypesCommon`
  * `UIAHandler.customProps.CustomPropertiesCommon`
  * `NVDAObjects.UIA.excel.ExcelCustomProperties`
  * `NVDAObjects.UIA.excel.ExcelCustomAnnotationTypes`

#### Deprecations

* `NVDAObjects.UIA.winConsoleUIA.WinTerminalUIA` is deprecated and usage is discouraged. (#14047)
* `config.addConfigDirsToPythonPackagePath` has been moved.
Use `addonHandler.packaging.addDirsToPythonPackagePath` instead. (#14350)
* `braille.BrailleHandler.TETHER_*` are deprecated.
Use `configFlags.TetherTo.*.value` instead. (#14233)
* `utils.security.postSessionLockStateChanged` is deprecated.
Use `utils.security.post_sessionLockStateChanged` instead. (#14486)
* `NVDAObject.hasDetails`, `NVDAObject.detailsSummary`, `NVDAObject.detailsRole` has been deprecated.
Use `NVDAObject.annotations` instead. (#14507)
* `keyboardHandler.SUPPORTED_NVDA_MODIFIER_KEYS` is deprecated with no direct replacement.
Consider using the class `config.configFlags.NVDAKey` instead. (#14528)
* `gui.MainFrame.evaluateUpdatePendingUpdateMenuItemCommand` has been deprecated.
Use `gui.MainFrame.SysTrayIcon.evaluateUpdatePendingUpdateMenuItemCommand` instead. (#14523)

## 2022.4

Questa versione contiene diversi nuovi comandi da tastiera, in special modo quelli dedicati alla funzione "dire tutto" nelle tabelle.
è stata aggiunta al manuale utente una sezione chiamata "guida rapida".
Ci sono naturalmente anche diverse correzioni di bug.

Sono stati aggiornati sia Espeak che LibLouis.
Introdotte nuove tabelle braille: cinese, svedese, luganda e kinyarwanda.

### Novità

* Aggiunta la sezione "guida rapida" al manuale utente. (#13934)
* Introdotto un nuovo comando per conoscere il tasto rapido assegnato al focus attuale. (#13960)
  * Desktop: `Maiusc+2 del tastierino numerico`.
  * Laptop: `NVDA+ctrl+maiusc+.`.
* Introdotti nuovi comandi per spostare il cursore di controllo di pagina in pagina laddove l'app lo consente. (#14021)
  * Vai alla pagina precedente:
    * Desktop: `NVDA+paginaSu`.
    * Laptop: `NVDA+maiusc+paginaSu`.
  * Vai alla pagina successiva:
    * Desktop: `NVDA+paginaGiù`.
    * Laptop: `NVDA+maiusc+paginaGiù`.
* Aggiunti i seguenti nuovi comandi per le tabelle. (#14070)
  * Dire tutto in colonna: `NVDA+control+alt+frecciaGiù`
  * Dire tutto in riga: `NVDA+control+alt+frecciaDestra`
  * Leggi colonna intera: `NVDA+control+alt+frecciaSu`
  * Leggi riga intera: `NVDA+control+alt+frecciaSinistra`
* Microsoft Excel con UI Automation: NVDA ora avverte quando si esce da una tabella all'interno di un foglio di calcolo. (#14165)
* L'annuncio delle intestazioni tabella può essere ora configurato separatamente per righe e colonne. (#14075)

### Cambiamenti

* eSpeak NG è stata aggiornata alla versione 1.52-dev commit `735ecdb8`. (#14060, #14079, #14118, #14203)
  * Risolto il problema con la segnalazione di caratteri latini quando si utilizzava il mandarino. (#12952, #13572, #14197)
* Aggiornato LibLouis braille translator alla versione [3.23.0](https://github.com/liblouis/liblouis/releases/tag/v3.23.0). (#14112)
  * Tabelle braille aggiunte:
    * Braille cinese comune (caratteri cinesi semplificati)
    * Braille letterario Kinyarwanda
    * Braille letterario Luganda
    * Braille svedese non contratto
    * Braille svedese parzialmente contratto
    * Braille svedese contratto
    * Cinese (Cina, Mandarino) Sistema Braille attuale (nessun tono) (#14138)
* NVDA ora include l'architettura del sistema operativo come parte del tracciamento delle statistiche degli utenti. (#14019)

### Bug Corretti

* Quando si aggiorna lo screen reader servendosi di utility quali Winget, le versioni stabili di NVDA non verranno più considerate più nuove rispetto a qualsiasi versione alpha installata. (#12469)
* NVDA ora annuncerà correttamente le caselle di gruppo nelle applicazioni Java. (#13962)
* Il cursore segue correttamente il testo letto dallo screen reader nella modalità  "dire tutto" in applicazioni come Bookworm, WordPad o il visualizzatore di log NVDA. (#13420, #9179)
* Nei programmi che si servono di UiAutomation, le caselle di controllo parzialmente selezionate verranno segnalate correttamente. (#13975)
* Prestazioni e stabilità migliorate in Microsoft Visual Studio, Windows Terminal e altre applicazioni basate su Ui Automation. (#11077, #11209)
  * Queste correzioni si applicano a Windows 11 Sun Valley 2 (versione 22H2) e versioni successive.
  * L'impostazione "Registrazione per eventi Ui Automation e cambiamenti di proprietà" viene impostata su "selettivo" per impostazione predefinita..
* La lettura del testo, la visualizzazione braille e la soppressione delle password ora funzionano correttamente nel terminale Windows incorporato in  Visual Studio 2022. (#14194)
* NVDA ora è in grado di gestire i DPI quando si utilizzano monitor multipli.
Vi sono state diverse correzioni quando si utilizza un'impostazione DPI più alta del 100% o monitor multipli.
Potrebbero persistere problemi con le versioni di Windows precedenti a Windows 10 1809.
Affinché queste correzioni funzionino, anche le applicazioni con cui NVDA interagisce devono gestire correttamente i DPI.
Si tenga presente che ci sono ancora problemi noti con Chrome e Edge. (#13254)
  * I riquadri per l'evidenziazione visiva dovrebbero venir posizionati correttamente nella maggior parte delle applicazioni. (#13370, #3875, #12070)
  * Ora l'interazione con il touch screen dovrebbe essere accurata per la maggior parte delle applicazioni. (#7083)
  * Il tracciamento del mouse ora dovrebbe funzionare per la maggior parte delle applicazioni. (#6722)
* Vengono ignorati tutti quei cambiamenti di orientamento (orizzontale/verticale) non veritieri causati prevalentemente dall'aggiunta o rimozione di un monitor). (#14035)
* NVDA annuncerà il trascinamento di elementi sullo schermo in situazioni come la riorganizzazione dei riquadri del menu Start di Windows 10 e dei desktop virtuali in Windows 11. (#12271, #14081)
* Nelle impostazioni avanzate, l'opzione "Riproduci un suono per gli errori loggati" ora viene ripristinata correttamente al suo valore predefinito quando si preme il pulsante "Ripristina impostazioni predefinite". (#14149)
* NVDA ora può selezionare il testo utilizzando la scorciatoia da tastiera `NVDA+f10` nelle applicazioni Java. (#14163)
* NVDA non rimarrà più bloccato in un menu quando ci si sposta con le freccie verticali tra le conversazioni in thread in Microsoft Teams. (#14355)

### Cambiamenti per sviluppatori, in inglese

Please refer to [the developer guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) for information on NVDA's API deprecation and removal process.

* The [NVDA API Announcement mailing list](https://groups.google.com/a/nvaccess.org/g/nvda-api/about) was created. (#13999)
* NVDA no longer processes `textChange` events for most UI Automation applications due to their extreme negative performance impact. (#11002, #14067)

#### Deprecations

* `core.post_windowMessageReceipt` is deprecated, use `winAPI.messageWindow.pre_handleWindowMessage` instead.
* `winKernel.SYSTEM_POWER_STATUS` is deprecated and usage is discouraged, this has been moved to `winAPI._powerTracking.SystemPowerStatus`.
* `winUser.SM_*` constants are deprecated, use `winAPI.winUser.constants.SystemMetrics` instead.

## 2022.3.3

Si tratta di una versione minore che risolve alcuni problemi inerenti le versioni 2022.3.2, 2022.3.1 e 2022.3.
Viene anche sistemato un problema di sicurezza.

### Correzioni di sicurezza

* Impedisce ad utenti non autorizzati possibili accessi al sistema (ad esempio la Console Python di NVDA.
([GHSA-fpwc-2gxx-j9v7](https://github.com/nvaccess/nvda/security/advisories/GHSA-fpwc-2gxx-j9v7))

### Bug Corretti

* Risolto un bug per cui se NVDA si bloccava quando contestualmente si accedeva alla schermata di lock screen, lo screen reader permetteva l'accesso al desktop dell'utente nonostante ci si trovasse nella schermata di blocco. (#14416)
* Risolto un bug per cui se NVDA si bloccava quando contestualmente si accedeva alla lock screen, lo screen reader non reagiva correttamente, nonpermettendo una gestione ideale della schermata di blocco. (#14416)
* Risolti i problemi di accessibilità con il processo "Ho dimenticato il PIN" di Windows e l'esperienza di aggiornamento/installazione del sistema operativo. (#14368)
* Risolto un bug che si manifestava nel tentare di installare NVDA in alcuni ambienti Windows particolari, ad esempio Windows Server. (#14379)

### Cambiamenti per gli sviluppatori

#### Deprecations

* `utils.security.isObjectAboveLockScreen(obj)` is deprecated, instead use `obj.isBelowLockScreen`. (#14416)
* The following functions in `winAPI.sessionTracking` are deprecated for removal in 2023.1. (#14416)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`

## 2022.3.2

Questa è una versione minore per correggere un problema con la 2022.3.1 e risolvere un problema di sicurezza.

### Correzioni di sicurezza

* Impedisce il possibile accesso a livello di sistema per gli utenti non autenticati.
([GHSA-3jj9-295f-h69w](https://github.com/nvaccess/nvda/security/advisories/GHSA-3jj9-295f-h69w))

### Bug corretti

* Risolve una regressione dalla versione 2022.3.1 in cui alcune funzionalità erano disabilitate su schermi protetti. (#14286)
* Risolve una regressione dalla 2022.3.1 in cui alcune funzionalità erano disabilitate dopo l'accesso, se NVDA si avviava sulla schermata di blocco. (#14301)

## 2022.3.1

Questa è una versione minore per risolvere diversi problemi di sicurezza.
Si prega di segnalare i problemi di sicurezza a <info@nvaccess.org>.

### Correzioni di sicurezza

* Sistemato un exploit che consentiva ad un utente di elevare i propri privilegi ad amministratore.
([GHSA-q7c2-pgqm-vvw5](https://github.com/nvaccess/nvda/security/advisories/GHSA-q7c2-pgqm-vvw5))
* Risolto un problema di sicurezza che permetteva l'accesso alla console Python sulla schermata di blocco tramite una race condition per l'avvio di NVDA.
([GHSA-72mj-mqhj-qh4w](https://github.com/nvaccess/nvda/security/advisories/GHSA-72mj-mqhj-qh4w))
* Risolto il problema per cui il testo del visualizzatore vocale veniva memorizzato nella cache durante il blocco di Windows.
([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

### Bug Corretti

* Impedisce ad un utente non autenticato di aggiornare le impostazioni per il visualizzatore vocale e Braille nella schermata di blocco. ([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

## 2022.3

Per questa versione di NVDA, molte modifiche sono state rese possibili grazie al contributo degli sviluppatori appartenenti alla community.
Ciò comprende la descrizione ritardata dei caratteri e il supporto migliorato per la console di Windows.

Questa versione include anche diverse correzioni di bug.
In particolare, le versioni aggiornate di Adobe Acrobat/Reader non si arrestano più in modo anomalo durante la lettura di un documento PDF.

Espeak è stata aggiornata, con l'introduzione di 3 nuove lingue: bielorusso, lussemburghese e totontepec Mixe.

### Novità

* Per quanto riguarda l'host della console di Windows utilizzato dal Prompt dei comandi, da PowerShell e dal sottosistema Windows per Linux su Windows 11 versione 22H2 (Sun Valley 2) e successive:
  * Prestazioni e stabilità notevolmente migliorate. (#10964)
  * Quando si preme `control+f` per trovare del testo, la posizione del cursore di controllo viene aggiornata e spostata sul termine trovato. (#11172).
  * Da impostazione predefinita, viene disattivata la segnalazione del testo digitato che non appare sullo schermo (come le password)
Può essere riattivata nel pannello delle impostazioni avanzate di NVDA. (#11554)
  * è possibile esaminare il testo non più presente a schermo senza dover far scorrere indietro la Console. (#12669)
  * Sono disponibili informazioni più dettagliate sulla formattazione del testo. ([microsoft/terminal PR 10336](https://github.com/microsoft/terminal/pull/10336))
* È stata aggiunta una nuova opzione vocale per leggere le descrizioni dei caratteri dopo un ritardo. (#13509)
* Aggiunta una nuova opzione Braille per determinare se lo scorrimento del display avanti/indietro debba o meno interrompere la sintesi vocale. (#2124)

### Cambiamenti

* eSpeak NG è stata aggiornata alla versione 1.52-dev commit `9de65fcb`. (#13295)
  * Lingue aggiunte:
    * Bielorusso
    * Lussemburghese
    * Totontepec Mixe
* Quando si utilizza UIA per accedere ai controlli del foglio di calcolo di Microsoft Excel, NVDA è ora in grado di segnalare quando una cella viene unita. (#12843)
* Piuttosto di annunciare "contiene dettagli", ora quando possibile viene annunciato il dettaglio stesso, ad esempio "contiene commenti". (#13649)
* La dimensione dell'installazione di NVDA è ora mostrata nella sezione Programmi e funzionalità di Windows. (#13909)

### Bug Fixes

* Adobe Acrobat / Reader 64 bit non si arresta più in modo anomalo durante la lettura di un documento PDF. (#12920)
  * Si noti che è necessaria anche la versione più aggiornata di Adobe Acrobat/Reader per evitare il crash.
* Le misure della grandezza caratteri sono ora traducibili in NVDA. (#13573)
* Vengono ignorati gli eventi Java Access Bridge laddove non sia possibile trovare alcun handle di finestra per le applicazioni Java.
Ciò migliorerà le prestazioni per alcune applicazioni Java, tra cui IntelliJ IDEA. (#13039)
* La lettura delle celle selezionate per LibreOffice Calc risulta più efficiente e non provoca più un blocco del programma quando vengono selezionate molte celle. (#13232)
* Microsoft Edge non risulta più inaccessibile se eseguito da un utente diverso. (#13032)
* quando l'aumento di velocità è disattivato, la velocità di Espeak non rallenta quando ci si trova tra  99% e 100%. (#13876)
* Risolto un bug che consentiva l'apertura di 2 finestre di dialogo dei gesti di immissione. (#13854)

### Cambiamenti per sviluppatori, in inglese

* Updated Comtypes to version 1.1.11. (#12953)
* In builds of Windows Console (`conhost.exe`) with an NVDA API level of 2 (`FORMATTED`) or greater, such as those included with Windows 11 version 22H2 (Sun Valley 2), UI Automation is now used by default. (#10964)
  * This can be overridden by changing the "Windows Console support" setting in NVDA's advanced settings panel.
  * To find your Windows Console's NVDA API level, set "Windows Console support" to "UIA when available", then check the NVDA+F1 log opened from a running Windows Console instance.
* The Chromium virtual buffer is now loaded even when the document object has the MSAA `STATE_SYSTEM_BUSY` exposed via IA2. (#13306)
* A config spec type `featureFlag` has been created for use with experimental features in NVDA. See `devDocs/featureFlag.md` for more information. (#13859)

#### Deprecations

There are no deprecations proposed in 2022.3.

## 2022.2.4

Questa è una versione patch per risolvere un problema di sicurezza.

### Bug Fixes

* Risolto un problema per cui era possibile aprire la console Python di NVDA tramite il visualizzatore di log nella schermata di blocco.
([GHSA-585m-rpvv-93qg](https://github.com/nvaccess/nvda/security/advisories/GHSA-585m-rpvv-93qg))

## 2022.2.3

Questa è una versione che va a correggere un errore presente nelle API della versione 2022.2.1.

### Bug Corretti

* Risolto un bug per cui NVDA non annunciava "Desktop sicuro" quando si accedeva a un desktop sicuro.
In questo modo quando si usava NVDA Remote non venivano riconosciuti i Desktop Sicuri. (#14094)

## 2022.2.2

Questa è una patch per correggere un bug introdotto nella versione 2022.2.1 con i gesti di input.

### Bug Fixes

* Fixed a bug where input gestures didn't always work. (#14065)

## 2022.2.1

This is a minor release to fix a security issue.
Please responsibly disclose security issues to <info@nvaccess.org>.

### Security Fixes

* Fixed exploit where it was possible to run a python console from the lockscreen. (GHSA-rmq3-vvhq-gp32)
* Fixed exploit where it was possible to escape the lockscreen using object navigation. (GHSA-rmq3-vvhq-gp32)

### Changes for Developers

#### Deprecations

These deprecations are currently not scheduled for removal.
The deprecated aliases will remain until further notice.
Please test the new API and provide feedback.
For add-on authors, please open a GitHub issue if these changes stop the API from meeting your needs.

* `appModules.lockapp.LockAppObject` should be replaced with `NVDAObjects.lockscreen.LockScreenObject`. (GHSA-rmq3-vvhq-gp32)
* `appModules.lockapp.AppModule.SAFE_SCRIPTS` should be replaced with `utils.security.getSafeScripts()`. (GHSA-rmq3-vvhq-gp32)

## 2022.2

Questa versione si è focalizzata nel risolvere un gran numero di bug.
In particolare, vi sono notevoli miglioramenti nelle app che si basano su Java, nel supporto ai display braille e ad alcune funzioni di Windows.

Sono stati introdotti nuovi comandi di navigazione nelle tabelle.
è stato aggiornato il supporto Unicode CLDR.
Come sempre, aggiornate anche le tabelle LibLouis, con il supporto ad una nuova tabella braille tedesca.

### Novità

* Supporto e gestione dei componenti Microsoft Loop nei prodotti Microsoft Office. (#13617)
* Sono stati aggiunti nuovi comandi di esplorazione tabelle. (#957)
 * `control+alt+home/end` per andare alla prima/ultima colonna.
 * `control+alt+pageUp/pageDown` per andare alla prima/ultima riga.
* Aggiunto uno script non assegnato per passare tra le modalità di cambio automatico lingua e dialetti. (#10253)

### Cambiamenti

* NSIS è stato aggiornato alla versione 3.08. (#9134)
* CLDR è stato aggiornato alla versione 41.0. (#13582)
* Aggiornato Liblouis alla versione [3.22.0](https://github.com/liblouis/liblouis/releases/tag/v3.22.0). (#13775)
  * Nuova tabella braille: Tedesco grado 2 (dettagliato)
* Aggiunto un nuovo ruolo per i controlli "barre di avanzamento non determinabili". (#10644)
* NVDA ora annuncia quando un'azione NVDA non può essere eseguita. (#13500)
  * Questo include quando:
    * Si utilizza la versione NVDA per Windows Store.
    * In un contesto protetto.
    * Si attende una risposta per una finestra modale.

### Bug Corretti

* Correzioni per applicazioni basate su Java:
  * NVDA ora annuncerà lo stato di sola lettura. (#13692)
  * NVDA ora annuncerà lo stato disabilitato/abilitato correttamente. (#10993)
  * NVDA ora annuncerà le scorciatoie dei tasti funzione. (#13643)
  * NVDA ora può emettere un segnale acustico o parlare sulle barre di avanzamento. (#13594)
  * NVDA non rimuoverà più erroneamente il testo dai widget durante la presentazione all'utente. (#13102)
  * NVDA ora annuncia lo stato degli interruttori . (#9728)
  * NVDA ora sarà in grado di identificare la finestra in un'applicazione Java con finestre multiple. (#9184)
  * NVDA ora annuncerà le informazioni sulla posizione nei controlli a scheda. (#13744)
* Problemi risolti inerenti il braille:
  * Risolto il problema con la lettura durante la navigazione in un testo nei controlli editazione avanzati di Mozilla, come la bozza di un messaggio in Thunderbird. (#12542)
  * Quando l'inseguimento braille è impostato su automatico e e il mouse viene spostato con la funzione di tracciamento mouse attiva, i comandi di revisione del testo ora aggiornano correttamente il display braille con ciò che la sintesi vocale legge.
   i comandi di revisione del testo ora aggiornano il display braille con il contenuto parlato. (#11519)
  * Risulta ora possibile scorrere il display braille in un contenuto dopo che sono stati utilizzati i comandi di revisione del testo (#8682)
* Il programma di installazione di NVDA ora può essere eseguito da directory con caratteri speciali. (#13270)
* In Firefox, NVDA non incontra più problemi nel segnalare gli elementi nelle pagine Web quando gli attributi aria-rowindex, aria-colindex, aria-rowcount o aria-colcount non risultano validi. (#13405)
* Il cursore non cambia più riga o colonna quando si utilizza la navigazione in una tabella per spostarsi tra le celle unite. (#7278)
* Durante la lettura di PDF non interattivi in Adobe Reader, vengono ora riportati il tipo e lo stato dei campi del modulo (come caselle di controllo e pulsanti radio). (#13285)
* La funzione "Ripristina la configurazione alle impostazioni di fabbrica" risulta ora accessibile dal menu di NVDA anche in modalità protetta. (#13547)
* Eventuali tasti del mouse bloccati verranno sbloccati all'uscita da NVDA, in precedenza sarebbero rimasti bloccati. (#13410)
* Visual Studio ora segnala i numeri di riga. (#13604)
  * Si tenga presente che affinché la lettura avvenga correttamente, la visualizzazione dei numeri di riga deve essere abilitata sia in Visual Studio che in NVDA.
* Visual Studio ora segnala correttamente i rientri della riga. (#13574)
* NVDA leggerà nuovamente i dettagli dei risultati di ricerca del menu Start nelle recenti versioni di Windows 10 e 11. (#13544)
* Nella Calcolatrice versione 10.1908 e successive in Windows 10 e 11, NVDA annuncerà i risultati quando vengono premuti più comandi, come quelli della modalità scientifica. (#13386)
NVDA annuncerà i risultati quando vengono premuti più comandi, come i comandi dalla modalità scientifica. (#13383)
* In Windows 11, è nuovamente possibile navigare e interagire con gli elementi dell'interfaccia utente,
come la barra delle applicazioni e la visualizzazione attività utilizzando il mouse o l'interazione a tocco. (#13508)
* NVDA annuncerà il contenuto della barra di stato nel Blocco note di Windows 11. (#13688)
* L'evidenziazione del navigatore ad oggetti ora si attiverà istantaneamente subito dopo l'attivazione della funzione.. (#13641)
* Sistemata la lettura della prima colonna nella visualizzazione ad elenco degli elementi. (#13659, #13735)
* Sistemato il cambio lingua automatico in eSpeak per Inglese e Francese che selezioneranno British English and French (France). (#13727)
* Risolto il problema con il cambio automatico della lingua di OneCore quando si tenta di passare a una lingua precedentemente installata. (#13732)

### Changes for Developers

* Compiling NVDA dependencies with Visual Studio 2022 (17.0) is now supported.
For development and release builds, Visual Studio 2019 is still used. (#13033)
* When retrieving the count of selected children via accSelection,
the case where a negative child ID or an IDispatch is returned by `IAccessible::get_accSelection` is now handled properly. (#13277)
* New convenience functions `registerExecutableWithAppModule` and `unregisterExecutable` were added to the `appModuleHandler` module.
They can be used to use a single App Module with multiple executables. (#13366)

#### Deprecations

These are proposed API breaking changes.
The deprecated part of the API will continue to be available until the specified release.
If no release is specified, the plan for removal has not been determined.
Note, the roadmap for removals is 'best effort' and may be subject to change.
Please test the new API and provide feedback.
For add-on authors, please open a GitHub issue if these changes stop the API from meeting your needs.

* `appModuleHandler.NVDAProcessID` is deprecated, use `globalVars.appPid` instead. (#13646)
* `gui.quit` is deprecated, use `wx.CallAfter(mainFrame.onExitCommand, None)` instead. (#13498)
  -
* Some alias appModules are marked as deprecated.
Code which imports from one of them, should instead import from the replacement module.  (#13366)

| Removed module name |Replacement module|
|---|---|
|azuredatastudio |code|
|azuredatastudio-insiders |code|
|calculatorapp |calculator|
|code - insiders |code|
|commsapps |hxmail|
|dbeaver |eclipse|
|digitaleditionspreview |digitaleditions|
|esybraille |esysuite|
|hxoutlook |hxmail|
|miranda64 |miranda32|
|mpc-hc |mplayerc|
|mpc-hc64 |mplayerc|
|notepad++ |notepadPlusPlus|
|searchapp |searchui|
|searchhost |searchui|
|springtoolsuite4 |eclipse|
|sts |eclipse|
|teamtalk3 |teamtalk4classic|
|textinputhost |windowsinternal_composableshell_experiences_textinput_inputapp|
|totalcmd64 |totalcmd|
|win32calc |calc|
|winmail |msimn|
|zend-eclipse-php |eclipse|
|zendstudio |eclipse|

## 2022.1

Questa versione include importanti miglioramenti al supporto UIA con MS Office.
Per Microsoft Office 16.0.15000 e versioni successive su Windows 11, NVDA utilizzerà la tecnologia UI Automation per accedere ai documenti di Microsoft Word per impostazione predefinita.
Ciò fornisce un notevole miglioramento delle prestazioni rispetto al vecchio modello ad oggetti..

Sono stati apportati miglioramenti ai driver per i display braille Seika Notetaker, Papenmeier e HID Braille.
Troveremo anche varie correzioni di bug in Windows 11, per app come Calcolatrice, Console, Terminale, Posta e Pannello Emoji.

Aggiornate come sempre eSpeak-NG e LibLouis, con l'aggiunta delle tabelle giapponesi, tedesche e catalane.

Nota:

 * Questa versione interrompe la compatibilità con i componenti aggiuntivi esistenti che dovranno essere quindi aggiornati.

### Novità

* Supporto al rilevamento delle note in MS Excel con UI Automation abilitata in Windows 11. (#12861)
* Nelle versioni recenti di Microsoft Word via UI Automation in Windows 11, vengono rilevati segnalibri, bozze di commenti e commenti risolti, sia tramite sintesi vocale che braille. (#12861)
* Il nuovo parametro a riga di comando `--lang` consente di non tener conto della lingua configurata in NVDA. (#10044)
* NVDA ora avvisa l'utente in caso di parametri della riga di comando che risultano sconosciuti e non utilizzati da alcun componente aggiuntivo. (#12795)
* In Microsoft Word con UI Automation attivato, NVDA ora utilizzerà mathPlayer per leggere e navigare all'interno delle equazioni matematiche di Office. (#12946)
  * Affinché funzioni, è necessario eseguire Microsoft Word 365/2016 build 14326 o successiva.
  * Si noti che anche le equazioni MathType devono essere convertite manualmente nel formato MathOffice selezionando ciascuna equazione, aprendo il menu di contesto, scegliere opzioni equazione, Converti in Office Math.
* La funzionalità che avvisa l'utente della presenza di dettagli ed il relativo comando associato ora ha effetto anche in modalità focus. (#13106)
* I Notetaker Seika ora possono essere individuati automaticamente quando connessi via USB o Bluetooth. (#13191, #13142)
  * Ciò riguarda i seguenti dispositivi: MiniSeika (16, 24 celle), V6, e V6Pro (40 celle)
  * Ora è supportata anche la selezione manuale della porta COM Bluetooth.
* Aggiunto un comando per attivare/disattivare il visualizzatore braille; non esiste alcun tasto rapido assegnato di default. (#13258)
* Aggiunti comandi per attivare/disattivare più tasti modificatori contemporaneamente con un display braille (#13152)
* La finestra di dialogo Dizionari ora presenta un pulsante "Rimuovi tutto" per cancellare un intero dizionario. (#11802)
* Aggiunto il supporto per la Calcolatrice di Windows 11. (#13212)
* In Microsoft Word con Ui automation abilitata in Windows 11, è supportato l'annuncio dei numeri di riga e di sezioni. (#13283)
* Per Microsoft Office 16.0.15000 e versioni successive su Windows 11, NVDA utilizzerà la tecnologia UI Automation per accedere ai documenti di Microsoft Word per impostazione predefinita, Ciò fornisce un notevole miglioramento delle prestazioni rispetto al vecchio modello ad oggetti..
 * Ciò include i documenti in Microsoft Word stesso e le finestre di lettura messaggi e composizione in Microsoft Outlook.

### Cambiamenti

* Espeak-ng è stata aggiornata alla versione 1.51-dev commit `7e5457f91e10`. (#12950)
* Aggiornato liblouis braille translator alla versione [3.21.0](https://github.com/liblouis/liblouis/releases/tag/v3.21.0). (#13141, #13438)
  * Aggiunta nuova tabella braille: Giapponese (Kantenji) braille letterario.
  * Aggiunta la nuova tabella braille computer tedesca a 6 punti.
  * Aggiunta tabella braille catalana di grado 1. (#13408)
* NVDA sarà in grado di annunciare la selezione e l'unnione di celle in LibreOffice Calc 7.3 e successive. (#9310, #6897)
* Aggiornato Unicode Common Locale Data Repository (CLDR) a 40.0. (#12999)
* `NVDA+canc del tastierino numerico` fornisce informazioni sulla posizione del cursore di sistema o sull'oggetto che ha il focus per impostazioni predefinite. (#13060)
* `NVDA+Shift+Canc del tastierino numerico` fornisce informazioni sulla posizione del cursore di controllo. (#13060)
* Aggiunti i riferimenti predefiniti per attivare/disattivare i tasti modificatori ai display di Freedom Scientific (#13152)
* Non vengono più fornite informazioni sulla baseline quando si preme `nvda-f` . (#11815)
* Non esiste più un tasto rapido dedicato per la funzione di attivazione long description. (#13380)
* è stato introdotto un tasto rapido per la funzione "Annuncia un riepilogo dei dettagli" (`NVDA+d`). (#13380)
* NVDA deve essere riavviato dopo aver installato MathPlayer. (#13486)

### Bug corretti

* Il riquadro Gestione appunti non dovrebbe più erroneamente ottenere il focus quando si aprono alcuni programmi di Office. (#12736)
* Su un sistema in cui l'utente ha scelto di scambiare il pulsante principale del mouse dal sinistro al destro, NVDA non visualizzerà più accidentalmente un menu contestuale invece di attivare un elemento, in applicazioni come i browser web. (#12642)
* Quando si sposta il cursore di controllo oltre la fine dei controlli di testo, come ad esempio in Microsoft Word con UI Automation, viene annunciata in più situazioni la dicitura "alla fine". (#12808)
* NVDA può segnalare il nome e la versione dell'applicazione per i file binari inseriti in system32 durante l'esecuzione con la versione a 64 bit di Windows. (#12943)
* Maggiore coerenza della lettura dell'output nei programmi del terminale. (#12974)
  * Si noti che in alcune situazioni, quando si inseriscono o si eliminano caratteri nel mezzo di una riga, è possibile che i caratteri dopo il cursore vengano nuovamente letti.
* MS word con UIA: quando si naviga per intestazioni in modalità navigazione, NVDA non si blocca più sull'ultima intestazione, né essa viene riportata due volte nell'elenco elementi. (#9540)
* In Windows 8 e versioni successive, la barra di stato di Esplora file può ora essere letta utilizzando la combinazione standard NVDA+fine (desktop) / NVDA+shift+fine (laptop). (#12845)
* Vengono nuovamente letti i messaggi in arrivo nella chat di Skype for Business (#9295)
* NVDA può di nuovo attenuare l'audio quando si utilizza il sintetizzatore SAPI5 su Windows 11. (#12913)
* Nella Calcolatrice di Windows 10, NVDA leggerà le etichette per la cronologia e gli elementi dell'elenco di memoria. (#11858)
* Gesti quali lo scorrimento e la pressione dei cursor routing funzionano nuovamente con i dispositivi braille HID. (#13228)
* Posta di Windows 11: Dopo essere passati da un'app all'altra , durante la lettura di un'e-mail lunga, NVDA non si blocca più su una riga dell'e-mail. (#13050)
* HID braille: I gesti con la pressione dello spazio (ad esempio `spazio+punto4`) possono ora essere effettuati dal display braille. (#13326)
* Risolto un problema che provocava l'apertura di più finestre impostazioni nello stesso tempo (#12818)
* Risolto un problema che impediva ad alcuni modelli di display braille Focus Blue di funzionare correttamente dopo che il pc era passato dallo stato di Standby a quello di accensione. (#9830)
* Non viene più annunciata sporadicamente la parola "Baseline" quando l'opzione "Segnala apice e pedice" è attiva. (#11078)
* In Windows 11, NVDA non impedirà più la navigazione nel pannello emoji quando si selezionano le emoji. (#13104)
* Risolto un bug che causava la doppia lettura delle informazioni quando si utilizza Windows Console e Terminal. (#13261)
* Risolte diverse situazioni in cui gli elementi di un elenco non venivano annunciati nelle applicazioni a 64 bit, come REAPER. (#8175)
* Nel gestore download di Microsoft Edge, NVDA ora passerà automaticamente alla modalità focus non appena l'elemento dell'elenco con il download più recente ottiene il focus. (#13221)
* NVDA non causa più l'arresto anomalo delle versioni a 64 bit di Notepad++ 8.3 e versioni successive. (#13311)
* Adobe Reader non si arresta più in modo anomalo all'avvio se la modalità protetta di Adobe Reader è abilitata. (#11568)
* Risolto un bug per cui la selezione del driver del Display Braille Papenmeier causava l'arresto anomalo di NVDA. (#13348)
* In Microsoft Word con UIA: il numero di pagina e altre informazioni di formattazione non vengono più annunciate in modo inappropriato quando si passa da una cella vuota di una tabella a una cella con contenuto o dalla fine del documento al contenuto esistente. (#13458, #13459)
* NVDA non avrà più difficoltà nel riportare il titolo della pagina e ne inizierà automaticamente la lettura dopo il caricamento  n Google chrome 100. (#13571)
* NVDA non andrà più in crash quando si ripristina la configurazione ai valori di fabbrica con l'opzione leggi i tasti di comando attiva. (#13634)

### Cambiamenti per sviluppatori, in inglese

* Note: this is a Add-on API compatibility breaking release. Add-ons will need to be re-tested and have their manifest updated.
* Although NVDA still requires Visual Studio 2019, Builds should no longer fail if a newer version of Visual Studio (E.g. 2022) is installed along side 2019. (#13033, #13387)
* Updated SCons to version 4.3.0. (#13033)
* Updated py2exe to version 0.11.1.0. (#13510)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` has been removed. Use `apiLevel` instead. (#12955, #12660)
* `TVItemStruct` has been removed from `sysTreeView32`. (#12935)
* `MessageItem` has been removed from the Outlook appModule. (#12935)
* `audioDucking.AUDIODUCKINGMODE_*` constants are now a `DisplayStringIntEnum`. (#12926)
  * usages should be replaced with `AudioDuckingMode.*`
  * usages of `audioDucking.audioDuckingModes` should be replaced with `AudioDuckingMode.*.displayString`
* `audioDucking.ANRUS_ducking_*` constants usages should be replaced with `ANRUSDucking.*`. (#12926)
* `synthDrivers.sapi5` changes (#12927):
  * `SPAS_*` usages should be replaced with `SPAudioState.*`
  * `constants.SVSF*` usages should be replaced with `SpeechVoiceSpeakFlags.*`
    * Note: `SVSFlagsAsync` should be replaced with `SpeechVoiceSpeakFlags.Async` not `SpeechVoiceSpeakFlags.lagsAsync`
  * `constants.SVE*` usages should be replaced with `SpeechVoiceEvents.*`
* The `soffice` appModule has the following classes and functions removed `JAB_OOTableCell`, `JAB_OOTable`, `gridCoordStringToNumbers`. (#12849)
* `core.CallCancelled` is now `exceptions.CallCancelled`. (#12940)
* All constants starting with RPC from `core` and `logHandler` are moved into `RPCConstants.RPC` enum. (#12940)
* It is recommended that `mouseHandler.doPrimaryClick` and `mouseHandler.doSecondaryClick` functions should be used to click the mouse to perform a logical action such as activating (primary) or secondary (show context menu),
rather than using `executeMouseEvent` and specifying the left or right mouse button specifically.
This ensures code will honor the Windows user setting for swapping the primary mouse button. (#12642)
* `config.getSystemConfigPath` has been removed - there is no replacement. (#12943)
* `shlobj.SHGetFolderPath` has been removed - please use `shlobj.SHGetKnownFolderPath` instead. (#12943)
* `shlobj` constants have been removed. A new enum has been created, `shlobj.FolderId` for usage with `SHGetKnownFolderPath`. (#12943)
* `diffHandler.get_dmp_algo` and `diffHandler.get_difflib_algo` have been replaced with `diffHandler.prefer_dmp` and `diffHandler.prefer_difflib` respectively. (#12974)
* `languageHandler.curLang` has been removed - to get the current NVDA language use `languageHandler.getLanguage()`. (#13082)
* A `getStatusBarText` method can be implemented on an appModule to customize the way NVDA fetches the text from the status bar. (#12845)
* `globalVars.appArgsExtra` has been removed. (#13087)
  * If your add-on need to process additional command line arguments see the documentation of `addonHandler.isCLIParamKnown` and the developer guide for details.
* The UIA handler module and other UIA support modules are now part of a UIAHandler package. (#10916)
  * `UIAUtils` is now `UIAHandler.utils`
  * `UIABrowseMode` is now `UIAHandler.browseMode`
  * `_UIAConstants` is now `UIAHandler.constants`
  * `_UIACustomProps` is now `UIAHandler.customProps`
  * `_UIACustomAnnotations` is now `UIAHandler.customAnnotations`
* The `IAccessibleHandler` `IA2_RELATION_*` constants have been replaced with the `IAccessibleHandler.RelationType` enum. (#13096)
  * Removed `IA2_RELATION_FLOWS_FROM`
  * Removed `IA2_RELATION_FLOWS_TO`
  * Removed `IA2_RELATION_CONTAINING_DOCUMENT`
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` and `LOCALE_SLANGDISPLAYNAME` are removed from `languageHandler` - use members of `languageHandler.LOCALE` instead. (#12753)
* Switched from Minhook to Microsoft Detours as a hooking library for NVDA. Hooking with this library is mainly used to aid the display model. (#12964)
* `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` is removed. (#13211)
* SCons now warns to build with a number of jobs that is equal to the number of logical processors in the system.
This can dramatically decrease build times on multi core systems. (#13226, #13371)
* `characterProcessing.SYMLVL_*` constants are removed - please use `characterProcessing.SymbolLevel.*` instead. (#13248)
* Functions `loadState` and `saveState` are removed from addonHandler - please use `addonHandler.state.load` and `addonHandler.state.save` instead. (#13245)
* Moved the UWP/OneCore interaction layer of NVDAHelper [from C++/CX to C++/Winrt](https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/move-to-winrt-from-cx). (#10662)
* It is now mandatory to subclass `DictionaryDialog` to use it. (#13268)
* `config.RUN_REGKEY`, `config.NVDA_REGKEY` are deprecated, please use `config.RegistryKey.RUN`, `config.RegistryKey.NVDA` instead. These will be removed in 2023. (#13242)
* `easeOfAccess.ROOT_KEY`, `easeOfAccess.APP_KEY_PATH` are deprecated, please use`easeOfAccess.RegistryKey.ROOT`, `easeOfAccess.RegistryKey.APP` instead. These will be removed in 2023. (#13242)
* `easeOfAccess.APP_KEY_NAME` has been deprecated, to be removed in 2023. (#13242)
* `DictionaryDialog` and `DictionaryEntryDialog` are moved from `gui.settingsDialogs` to `gui.speechDict`. (#13294)
* IAccessible2 relations are now shown in developer info for IAccessible2 objects. (#13315)
* `languageHandler.windowsPrimaryLCIDsToLocaleNames` has been removed, instead use `languageHandler.windowsLCIDToLocaleName` or `winKernel.LCIDToLocaleName`. (#13342)
* `UIAAutomationId` property for UIA objects should be preferred over `cachedAutomationId`. (#13125, #11447)
  * `cachedAutomationId` can be used if obtained directly from the element.
* `NVDAObjects.window.scintilla.CharacterRangeStruct` has moved to `NVDAObjects.window.scintilla.Scintilla.CharacterRangeStruct`. (#13364)
* Boolean `gui.isInMessageBox` is removed, please use the function `gui.message.isModalMessageBoxActive` instead. (#12984, #13376)
* `controlTypes` has been split up into various submodules. (#12510, #13588)
  * `ROLE_*` and `STATE_*` have been replaced with `Role.*` and `State.*`.
  * Although still available, the following should be considered deprecated:
    * `ROLE_*` and `STATE_*`, use `Role.*` and `State.*` instead.
    * `roleLabels`, `stateLabels` and `negativeStateLabels`, usages like `roleLabels[ROLE_*]` should be replaced with their equivalent `Role.*.displayString` or `State.*.negativeDisplayString`.
    * `processPositiveStates` and `processNegativeStates` should use `processAndLabelStates` instead.
* Excel cell state constants (`NVSTATE_*`) are now values in the `NvCellState` enum, mirrored in the `NvCellState` enum in `NVDAObjects/window/excel.py` and mapped to `controlTypes.State` via _nvCellStatesToStates. (#13465)
* `EXCEL_CELLINFO` struct member `state` is now `nvCellStates`.
* `mathPres.ensureInit` has been removed, MathPlayer is now initialized when NVDA starts. (#13486)

## 2021.3.5

Questa è una versione minore che risolve un problema di sicurezza.
Si prega di segnalare con precisione i problemi di sicurezza a <info@nvaccess.org>.

### Correzioni di sicurezza

* Risolta segnalazione di sicurezza  `GHSA-xc5m-v23f-pgr7`.
  * La finestra di dialogo pronuncia punteggiatura/simboli è ora disabilitata in modalità protetta.

## 2021.3.4

Questa è una versione minore che risolve diversi problemi di sicurezza emersi.
Si prega di segnalare con precisione i problemi di sicurezza a <info@nvaccess.org>.

### Correzioni di sicurezza

* risolto avviso di sicurezza `GHSA-354r-wr4v-cx28`. (#13488)
  * Eliminata la possibilità di avviare NVDA con il debug dei log abilitato quando lo screen reader viene eseguito in modalità protetta.
  * Rimossa la possibilità di aggiornare NVDA quando lo screen reader viene eseguito in modalità protetta.
* Risolto avviso di sicurezza `GHSA-wg65-7r23-h6p9`. (#13489)
  * Rimossa la possibilità di aprire la finestra tasti e gesti di immissione in modalità protetta.
  * Rimossa la possibilità di aprire le finestre di dialogo dei dizionari standard, voce e temporaneo.
* Risolto avviso di sicurezza `GHSA-mvc8-5rv9-w3hx`. (#13487)
  * In modalità protetta ora è disattivato lo strumento di ispezione della GUI wx.

## 2021.3.3

Questa versione è identica alla 2021.3.2.
Esisteva un bug in NVDA 2021.3.2 che identificava erroneamente NVDA come 2021.3.1.
Questa versione si identifica correttamente come 2021.3.3.

## 2021.3.2

Questa è una versione minore per risolvere diversi problemi di sicurezza emersi.
Si prega di segnalare con precisione i problemi di sicurezza a <info@nvaccess.org>.

### Bug Risolti

* Correzione di sicurezza: Impedisce la navigazione degli oggetti al di fuori della schermata di blocco su Windows 10 e Windows 11. (#13328)
* Correzione di sicurezza: la finestra di dialogo gestione componenti aggiuntivi è disabilitata in modalità protetta. (#13059)
* Correzione di sicurezza: L'aiuto contestuale di NVDA non è più disponibile nelle schermate in modalità protetta. (#13353)

## 2021.3.1

Questa è una versione minore per risolvere diversi problemi individuati nella 2021.3.

### Cambiamenti

* Nel caso in cui un display braille disponga del suo driver proprietario e di quello del protocollo Hid, verrà sempre selezionato di default il primo, anziché il protocollo Hid. (#13153)
* Il nuovo protocollo HID Braille può essere disabilitato tramite un'impostazione nel pannello delle impostazioni avanzate. (#13180)

### Bug Risolti

* Landmark verrà nuovamente  abbreviato in braille. #13158
* Risolte le instabilità presenti nel rilevamento automatico per i display braille Humanware Brailliant e APH Mantis Q40 quando usati tramite Bluetooth. (#13153)

## 2021.3

Questa versione introduce il supporto per un nuovo protocollo denominato HID Braille.
Tale specifica mira a standardizzare il supporto per i display Braille senza bisogno di driver individuali.
Ci sono aggiornamenti per eSpeak-NG e LibLouis, incluse nuove tabelle russe e Tshivenda.
I suoni di errore possono essere abilitati nelle build stabili di NVDA tramite una nuova opzione nelle impostazioni avanzate.
La modalità dire tutto in Word ora farà scorrere la visualizzazione in modo da mantenere sempre visibile la posizione corrente.
Vi sono molti miglioramenti quando si usa Office con UIA.
Uno di questi riguarda Outlook, che adesso è in grado di ignorare molte tabelle di layout nei messaggi..

Note importanti:

A causa di un aggiornamento del nostro certificato di sicurezza, è stato riscontrato che un esiguo numero di utenti riceve un errore quando NVDA 2021.2 verifica la disponibilità di aggiornamenti.
NVDA ora chiede a Windows di aggiornare i certificati di sicurezza, in questo modo tale errore sarà evitato in futuro.
Gli utenti interessati dovranno scaricare questo aggiornamento manualmente.

### Novità

* Aggiunto un gesto di immissione che permette di attivare/disattivare la segnalazione dello stile dei bordi delle celle. (#10408)
* Supporto per la nuova specifica HID Braille che mira a standardizzare il supporto per i display Braille. (#12523)
  * I dispositivi che supportano questa funzionalità verranno rilevati automaticamente da NVDA.
  * Per ulteriori informazioni tecniche su come NVDA implementa questa nuova funzionalità, si veda https://github.com/nvaccess/nvda/blob/master/devDocs/hidBrailleTechnicalNotes.md
* Aggiunto il supporto per la nuova barra braille Vario 4 VisioBraille. (#12607)
* Possono essere abilitate le notifiche per gli errori (opzioni avanzate) in tutte le versioni di NVDA. (#12672)
* In Windows 10 e versioni successive, NVDA annuncerà il conteggio dei suggerimenti quando si immettono i termini di ricerca in app come Impostazioni e Microsoft Store. (#7330, #12758, #12790)
* Viene supportata la navigazione per tabelle nei controlli a griglia creati usando Out-GridView cmdlet in PowerShell. (#12928)

### Cambiamenti

* Espeak-ng è stata aggiornata alla versione 1.51-dev commit `74068b91bcd578bd7030a7a6cde2085114b79b44`. (#12665)
* NVDA utilizzerà ESpeak nel caso in cui nessuna voce OneCore installata sia in grado di parlare nella lingua scelta in NVDA. (#10451)
* Se le voci OneCore dovessero smettere di parlare, verrà caricata automaticamente la sintesi Espeak. (#11544)
* Quando si legge la barra di stato con `NVDA+fine`, il cursore di controllo non sarà più spostato in quella posizione.
Se si necessita di questa funzione si prega di assegnare un gesto allo script appropriato nella categoria navigazione ad oggetti della finestra di dialogo tasti e gesti di immissione. (#8600)
* Se si apre la finestra di dialogo delle impostazioni ed essa risulta già aperta, NVDA imposta il focus su tale finestra di dialogo piuttosto che provocare un errore. (#5383)
* Aggiornato liblouis braille translator alla versione [3.19.0](https://github.com/liblouis/liblouis/releases/tag/v3.19.0). (#12810)
  * Nuove tabelle braille: russo grado 1, Tshivenda grado 1, Tshivenda grado 2
* Anziché annunciare "contenuto contrassegnato" o "mrkd", ora viene usata la dicitura "evidenziato" o "hlght". (#12892)
* NVDA non tenterà più di chiudersi quando le finestre di dialogo sono in attesa di un'azione richiesta (es. Conferma/Annulla). (#12984)

### Bug Corretti

* Il monitoraggio dei tasti modificatori (come Control, o Insert) risulta più affidabile quando viene ripristinato il watchdog. (#12609)
* Ora risulta nuovamente possibile controllare se vi sono aggiornamenti di NVDA su alcuni sistemi; ad esempio installazioni pulite di Windows. (#12729)
* NVDA rileva correttamente le celle nelle tabelle vuote in Microsoft Word quando si usa UI automation. (#11043)
* Nel web, nelle celle con griglie di dati ARIA, il tasto Escape avrà effetto sulla griglia e non disattiverà più la modalità focus. (#12413)
* Durante la lettura di una cella di intestazione di una tabella in Chrome, corretto un problema che provocava l'annuncio del nome della colonna due volte. (#10840)
* NVDA non annuncia più un valore numerico per i cursori di avanzamento UIA che hanno una rappresentazione testuale del loro valore. (Viene quindi preferita UIA ValuePattern rispetto a RangeValuePattern). (#12724)
* NVDA non considera più il valore dei cursori di avanzamento UIA sempre basati su percentuale.
* Funziona nuovamente l'annuncio della posizione di una cella in Microsoft Excel se ci si serve di UI Automation in Windows 11. (#12782)
* NVDA non imposta più localizzazioni Python non valide. (#12753)
* Se un componente aggiuntivo disabilitato viene disinstallato e poi reinstallato, esso sarà riabilitato. (#12792)
* Risolti gli errori sulla rimozione e l'aggiornamento dei componenti aggiuntivi nel caso in cui la cartella degli addon sia stata rinominata o contenga file aperti. (#12792, #12629)
* Quando si utilizza UI Automation per accedere ai controlli dei fogli di lavoro in Microsoft Excel, NVDA non annuncerà più continuamente che una cella è stata selezionata. (#12530)
* In LibreOffice Writer NVDA è in grado di annunciare una maggiore quantità di testo nelle finestre di conferma. (#11687)
* La lettura e l'esplorazione in Microsoft Word nella modalità navigazione via UI automation ora gestisce correttamente lo scrolling del documento in modo che la posizione del cursore virtuale risulti sempre visibile, e che la posizione del cursore di sistema coincida con quella di navigazione (#9611)
* Quando si utilizza la modalità dire tutto in Microsoft Word tramite UI Automation, il documento viene ora automaticamente fatto scorrere e la posizione del cursore viene aggiornata correttamente. (#9611)
* Quando si leggono le e-mail in Outlook e NVDA accede al messaggio tramite UI Automation, alcune tabelle saranno marcate come "tabelle di layout", il che significa che non saranno annunciate per impostazioni predefinite. (#11430)
* È stato corretto un errore piuttosto raro durante il cambio di un dispositivo audio. (#12620)
* L'immissione tramite tabelle braille letterarie dovrebbe comportarsi in modo più affidabile nei campi editazione. (#12667)
* Durante la navigazione nel calendario della barra delle applicazioni di Windows, NVDA ora riporta il giorno della settimana per intero. (#12757)
* Quando ci si serve di un metodo di immissione cinese come Taiwan - Microsoft Quick in Microsoft Word, ora lo scorrimento avanti e indietro del display braille non porta più la barra di continuo alla posizione originale del cursore. (#12855)
* Quando si accede a documenti Microsoft Word tramite UIA, è nuovamente possibile navigare per frase (alt+freccia su / alt+freccia giù). (#9254)
* Quando si accede a documenti Microsoft Word tramite UIA, vengono ora segnalati i rientri dei paragrafi. (#12899)
* Quando si accede a documenti Microsoft Word tramite UIA, vengono segnalati sia alcuni comandi localizzati che funzioni di tracciamento delle modifiche. (#12904)
* Risolta la doppia lettura sia per la sintesi che per il braille quando 'descrizione' risulta identica a 'contenuto' o 'nome'. (#12888)
* In MS Word con  UIA abilitata, è stata implementata una segnalazione più accurata degli errori di ortografia durante la digitazione. (#12161)
* In Windows 11, NVDA non annuncerà più "riquadro" quando si preme Alt+Tab per spostarsi tra le finestre. (#12648)
* Supporto per il nuovo riquadro laterale dei commenti in Microsoft Word quando non si accede al documento tramite UIA. Premere alt+f12 per spostarsi tra il riquadro laterale e il documento. (#12982)

### Changes for Developers

* Building NVDA now requires Visual Studio 2019 16.10.4 or later.
To match the production build environment, update Visual Studio to keep in sync with the [current version AppVeyor is using](https://www.appveyor.com/docs/windows-images-software/#visual-studio-2019). (#12728)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` has been deprecated for removal in 2022.1. (#12660)
  * Instead use `apiLevel` (see the comments at `_UIAConstants.WinConsoleAPILevel` for details).
* Transparency of text background color sourced from GDI applications (via the display model), is now exposed for add-ons or appModules. (#12658)
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` and `LOCALE_SLANGDISPLAYNAME` are moved to the `LOCALE` enum in languageHandler.
They are still available at the module level but are deprecated and to be removed in NVDA 2022.1. (#12753)
* The usage of functions `addonHandler.loadState` and `addonHandler.saveState` should be replaced with their equivalents `addonHandler.state.save` and `addonHandler.state.load` before 2022.1. (#12792)
* Braille output can now be checked in system tests. (#12917)

## 2021.2

Questa versione introduce il supporto preliminare per Windows 11!
Nonostante tale sistema operativo non sia ancora stato rilasciato, sono stati effettuati numerosi test con la versione 2021.2 di NVDA per le edizioni in sviluppo di Windows11.
Ciò comprende la risoluzione di un bug molto importante inerente la tenda schermo (si vedano le note di seguito).
L'utility di risoluzione registrazione Com di sistema è in grado di sistemare un numero molto più ampio di problemi quando NVDA è in esecuzione.
Ci sono aggiornamenti al sintetizzatore eSpeak e alle tabelle di braille LibLouis.
Inoltre, varie correzioni di bug e miglioramenti, in particolare per il supporto braille, terminali Windows, calcolatrice, pannello emoji e cronologia degli appunti.

### Note importanti

A causa di alcuni cambiamenti nelle api dell'ingranditore di Windows, è risultato necessario aggiornare la tenda schermo in modo che potesse funzionare correttamente.
Perciò, è obbligatorio servirsi di NVDA 2021.2 per attivare la tenda schermo con versioni di Windows 10 21H2 (10.0.19044) o successive.
Ciò comprende anche Windows 10 Insiders e Windows 11.
Per sicurezza, sarebbe meglio avere una conferma da una persona vedente che lo schermo sia effettivamente oscurato quando si aggiorna Windows ad una nuova versione.

### Novità

* Supporto sperimentale per le annotazioni ARIA:
  * aggiunto un comando che consente di ottenere un riepilogo dei dettagli di un oggetto contenente aria-details. (#12364)
  * aggiunta un'opzione nella sezione avanzate delle preferenze per annunciare se un oggetto contiene dettagli in modalità navigazione. (#12439)
* In Windows 10 Versione 1909 e successive (incluso Windows 11), NVDA annuncerà il conteggio dei suggerimenti durante l'esecuzione di ricerche in Esplora file. (#10341, #12628)
* In Microsoft Word, NVDA ora annuncia ciò che accade dopo aver premuto le combinazioni di tasti relative ai rientri ed ai rientri sporgenti (non in italiano a causa della mancanza di questi tasti rapidi nella versione italiana di Word. (#6269)

### Cambiamenti

* Espeak-ng è stata aggiornata alla versione 1.51-dev commit `ab11439b18238b7a08b965d1d5a6ef31cbb05cbb`. (#12449, #12202, #12280, #12568)
* Se nelle impostazioni di formattazione documento viene abilitata la casella di controllo articoli, NVDA annuncerà "articolo" dopo il contenuto. (#11103)
* Aggiornato liblouis braille translator alla versione [3.18.0](https://github.com/liblouis/liblouis/releases/tag/v3.18.0). (#12526)
  * Nuove tabelle braille: Bulgaro grado 1, Burmese grado 1, Burmese grado 2, Kazako grado 1, Khmer grado 1, curdo del nord grado 0, Sepedi grado 1, Sepedi grado 2, Sesotho grado 1, Sesotho grado 2, Setswana grado 1, Setswana grado 2, Tatar grado 1, Vietnamita grado 0, Vietnamita grado 2, vietnamita del sud  grado1, Xhosa grado 1, Xhosa grado 2, Yakut grado 1, Zulu grado 1, Zulu grado 2
* L'OCR di Windows10  è stato rinominato in OCR Windows. (#12690)

### Bug Corretti

* Nella calcolatrice di Windows 10, NVDA visualizzerà correttamente il risultato delle espressioni anche su display braille. (#12268)
* Nei programmi terminale su Windows 10 versione 1607 e successive, quando si inseriscono o si eliminano caratteri nel mezzo di una riga, i caratteri a destra del cursore non vengono più letti. (#3200)
  * Diff Match Patch ora abilitata di default. (#12485)
* L'immissione braille funziona correttamente con le seguenti tabelle contratte: Arabo grado 2, Spagnolo grado 2, Urdu grado 2, Cinese (Cina, Mandarino) grado 2. (#12541)
* L'utility di risoluzione registrazione Com di sistema è in grado di sistemare un numero molto più ampio di problemi quando NVDA è in esecuzione. (#12560)
* Miglioramenti nella gestione dei pulsanti dei notetaker braille Seika di Nippon Telesoft. (#12598)
* Miglioramenti nella lettura del pannello emoji di Windows e della cronologia appunti. (#11485)
* Aggiornate le descrizioni per l'alfabeto Bengali. (#12502)
* NVDA si chiude in sicurezza quando viene avviato un nuovo processo. (#12605)
* Non ci sono più errori nel riselezionare il driver del display braille Handy Tech dalla finestra di dialogo Seleziona display braille. (#12618)
* Le versioni di Windows 10.0.22000 o successive vengono riconosciute come Windows11, non Windows 10. (#12626)
* La funzionalità di tenda schermo è stata sistemata e testata fino alla versione Windows 10.0.22000. (#12684)
* Se non vengono mostrati risultati  durante il filtraggio dei gesti di immissione, la finestra di configurazione gesti continua a funzionare regolarmente. (#12673)
* Risolto un bug per cui la prima voce di menu di un sottomenu non veniva annunciata in alcuni contesti. (#12624)

### Changes for Developers

* `characterProcessing.SYMLVL_*` constants should be replaced using their equivalent `SymbolLevel.*` before 2022.1. (#11856, #12636)
* `controlTypes` has been split up into various submodules, symbols marked for deprecation must be replaced before 2022.1. (#12510)
  * `ROLE_*` and `STATE_*` constants should be replaced to their equivalent `Role.*` and `State.*`.
  * `roleLabels`, `stateLabels` and `negativeStateLabels` have been deprecated, usages such as `roleLabels[ROLE_*]` should be replaced to their equivalent `Role.*.displayString` or `State.*.negativeDisplayString`.
  * `processPositiveStates` and `processNegativeStates` have been deprecated for removal.
* On Windows 10 Version 1511 and later (including Insider Preview builds), the current Windows feature update release name is obtained from Windows Registry. (#12509)
* Deprecated: `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` will be removed in 2022.1, there is no direct replacement. (#12544)

## 2021.1

Questa versione include un supporto sperimentale opzionale per la tecnologia UIA in Excel e nei browser basati su Chromium.
Sono state effettuate numerose correzioni su diverse lingue e per l'accesso ai collegamenti in Braille.
Aggiornamenti anche per le Emoji Unicode CLDR, per i simboli matematici, e alle tabelle braille di LibLouis.
Naturalmente sono stati risolti numerosi bug , specie in Office, Visual Studio, e molto altro.

Nota:

 * Questa versione non risulta più compatibile con numerosi componenti aggiuntivi esistenti, che dovranno essere aggiornati.
 * Viene anche eliminato qualsiasi supporto ad Adobe Flash.

### Novità

* supporto sperimentale alla tecnologia UIA con i browser basati su Chromium (come Edge). (#12025)
* Supporto sperimentale opzionale per Microsoft Excel tramite UI Automation. Raccomandato solo per Microsoft Excel build 16.0.13522.10000 o superiore. (#12210)
* Esplorazione semplificata dell'output relativo alla Console Python . (#9784)
  * alt+su/giù va al risultato output successivo o precedente (aggiungere Shift per selezionare).
  * control+l cancella il riquadro di output.
* NVDA ora annuncia le categorie assegnate a un appuntamento in Microsoft Outlook, se presenti. (#11598)
* Supporto per i display braille e i Notetaker Seika prodotti dalla Nippon Telesoft. (#11514)

### Cambiamenti

* In modalità navigazione, è possibile usare i cursor routing di un display braille per attivare i controlli, premendo sulla descrizione del controllo stesso (ad esempio "lnk" per un link). Ciò risulta molto utile anche per attivare caselle di controllo senza un'etichetta specifica. (#7447)
* NVDA non permette l'utilizzo dell'OCR di Windows10 nel caso in cui la tenda schermo sia attiva. (#11911)
* Aggiornato Unicode Common Locale Data Repository (CLDR) alla versione  39.0. (#11943, #12314)
* Aggiunti diversi simboli matematici al dizionario simboli. Per l'Italia si ringrazia il Dipartimento di Matematica "Tullio Levi Civita", Università di Padova, nelle persone delle prof.sse Ombretta Gaggi ed Alessandra Buratto. (#11467)
* Migliorato l'aspetto della guida utente, del file delle novità e dei comandi di scelta rapida. (#12027)
* Se si cerca di usare la funzione di modifica layout schermo (NVDA+v) in applicazioni che non la gestiscono come Microsoft Word, NVDA ora lo segnalerà dicendo "non supportato". (#7297)
* Viene attivata per impostazione predefinita la funzione 'Tenta di non leggere informazioni obsolete concernenti il focus', presente nella finestra "avanzate" delle impostazioni di NVDA. (#10885)
  * Questo comportamento può essere disabilitato impostando l'opzione su "No".
  * Applicazioni web (come Gmail) non forniscono più informazioni obsolete quando si sposta velocemente il focus.
* Aggiornate le tabelle di traduzione Braille Liblouis braille translator alla versione [3.17.0](https://github.com/liblouis/liblouis/releases/tag/v3.17.0). (#12137)
  * Nuove tabelle braille: Braille letterario bielorusso, computer braille bielorusso, urdu grado 1, urdu grado 2.
* Cessato il supporto per i contenuti Adobe Flash, la stessa Adobe non ne consiglia più l'uso. (#11131)
* NVDA ora è in grado di chiudersi correttamente anche nel caso vi siano finestre di dialogo dello screen reader ancora aperte; all'uscita, queste saranno chiuse automaticamente. (#1740)
* è possibile chiudere il visualizzatore sintesi vocale con `alt+F4`, inoltre è stato aggiunto un pulsante di chiusura per agevolare chi utilizza mouse o dispositivi di puntamento. (#12330)
* Il visualizzatore Braille ora dispone di un pulsante di chiusura per agevolare chi utilizza mouse o dispositivi di puntamento. (#12328)
* Nell'elenco elementi, il tasto di scelta rapida sul pulsante "Attiva" è stato rimosso per alcune lingue per evitare conflitti con l'etichetta di un pulsante radio di tipo elemento. Quando disponibile, si potrà comunque attivare il pulsante semplicemente premendo invio sempre dall'elenco elementi. (#6167)

### Bug corretti

* Risulta nuovamente leggibile l'elenco messaggi in Outlook 2010. (#12241)
* Nei programmi di tipo terminale in Windows 10 versione 1607 e successive, all'inserimento o alla cancellazione dei caratteri nel mezzo di una riga, non saranno più letti anche i caratteri alla destra del cursore. (#3200)
  * Questa correzione sperimentale deve essere abilitata manualmente nel pannello delle impostazioni avanzate di NVDA modificando l'algoritmo diff in Diff Match Patch.
* In MS Outlook, non dovrebbe più essere annunciata la distanza quando si preme Shift+tab per andare dal corpo del messaggio all'oggetto (#10254)
* Nella Console Python, vengono supportate operazioni quali l'inserimento di tabulazioni per effettuare rientri all'inizio di una riga non vuota, oltre alla possibilità di gestire l'autocompletamento nel mezzo di una riga. (#11532)
* Quando il layout dello schermo è disattivato, le informazioni di formattazione e altri messaggi navigabili non presentano più righe vuote. (#12004)
* Ora è possibile leggere i commenti in MS Word con UIA abilitato. (#9285)
* Migliorate le prestazioni durante l'interazione con Visual Studio. (#12171)
* Risolti bug grafici come elementi mancanti quando si utilizza NVDA con un layout da destra a sinistra. (#8859)
* Per quel che concerne la direzione del layout dell'interfaccia utente di NVDA, Viene rispettata la scelta dell'utente effettuata in base alla lingua dello screen reader piuttosto che fare riferimento a quella di sistema.  (#638)
  * problema noto per le lingue da destra a sinistra: il bordo destro dei raggruppamenti non è ben gestito con etichette/controlli. (#12181)
* La localizzazione di Python è impostata per corrispondere alla lingua selezionata nelle preferenze in modo coerente. (#12214)
* TextInfo.getTextInChunks non si blocca più quando incontrato sui controlli Rich Edit come il visualizzatore di log di NVDA. (#11613)
* È nuovamente possibile utilizzare NVDA nelle lingue che contengono caratteri di sottolineatura nel nome, come de_CH su Windows 10 1803 e 1809. (#12250)
* In WordPad, ora funziona come previsto la lettura degli apici e pedici. (#12262)
* NVDA legge ora correttamente il nuovo contenuto appena focalizzato in una pagina web in cui il vecchio focus viene sostituito dal nuovo. (#12147)
* Viene letta correttamente la formattazione di tipo barrato, apice e pedice nelle celle intere di Excel se l'opzione corrispondente è abilitata. (#12264)
* Risolto il problema con la copia della configurazione durante l'installazione da una versione portable quando la directory di di destinazione predefinita è vuota. (#12071, #12205)
* Risolto un problema che provocava la lettura non corretta di alcune lettere con accenti o diacritici quando l'opzione 'Leggi Cap prima delle maiuscole' è selezionata. (#11948)
* risolto il problema con il cambio pitch nelle sintesi vocali Sapi4.. (#12311)
* Il programma di installazione di NVDA ora rispetta anche il parametro della riga di comando `--minimal` e non riproduce il suono di avvio, seguendo lo stesso comportamento documentato di una copia dell'eseguibile NVDA installato o portatile. (#12289)
* In MS Word o Outlook, il tasto di navigazione rapida della tabella può ora passare alla tabella di layout se l'opzione "Includi tabelle di layout" è abilitata nelle impostazioni della modalità di navigazione. (#11899)
* NVDA non dirà più "↑↑↑" per le emoji in alcune lingue particolari. (#11963)
* Espeak ora supporta nuovamente il cantonese e il mandarino. (#10418)
* Nel nuovo Microsoft Edge basato su Chromium, vengono letti correttamente i campi di testo come la barra degli indirizzi quando vuoti. (#12474)
* Sistemati i problemi con il driver Seika per le barre braille. (#10787)

### Changes for Developers

* Note: this is an Add-on API compatibility breaking release. Add-ons will need to be re-tested and have their manifest updated.
* NVDA's build system now fetches all Python dependencies with pip and stores them in a Python virtual environment. This is all done transparently.
  * To build NVDA, SCons should continue to be used in the usual way. E.g. executing scons.bat in the root of the repository. Running `py -m SCons` is no longer supported, and `scons.py` has also been removed.
  * To run NVDA from source, rather than executing `source/nvda.pyw` directly, the developer should now use `runnvda.bat` in the root of the repository. If you do try to execute `source/nvda.pyw`, a message box will alert you this is no longer supported.
  * To perform unit tests, execute `rununittests.bat [<extra unittest discover options>]`
  * To perform system tests: execute `runsystemtests.bat [<extra robot options>]`
  * To perform linting, execute `runlint.bat <base branch>`
  * Please refer to readme.md for more details.
* The following Python dependencies have also been upgraded:
  * comtypes updated to 1.1.8.
  * pySerial updated to 3.5.
  * wxPython updated to 4.1.1.
  * Py2exe updated to 0.10.1.0.
* `LiveText._getTextLines` has been removed. (#11639)
  * Instead, override `_getText` which returns a string of all text in the object.
* `LiveText` objects can now calculate diffs by character. (#11639)
  * To alter the diff behaviour for some object, override the `diffAlgo` property (see the docstring for details).
* When defining a script with the script decorator, the 'allowInSleepMode' boolean argument can be specified to control if a script is available in sleep mode or not. (#11979)
* The following functions are removed from the config module. (#11935)
  * canStartOnSecureScreens - use config.isInstalledCopy instead.
  * hasUiAccess and execElevated - use them from the systemUtils module.
  * getConfigDirs - use globalVars.appArgs.configPath instead.
* Module level REASON_* constants are removed from controlTypes - please use controlTypes.OutputReason instead. (#11969)
* REASON_QUICKNAV has been removed from browseMode - use controlTypes.OutputReason.QUICKNAV instead. (#11969)
* `NVDAObject` (and derivatives) property `isCurrent` now strictly returns Enum class `controlTypes.IsCurrent`. (#11782)
  * `isCurrent` is no longer Optional, and thus will not return None.
    * When an object is not current `controlTypes.IsCurrent.NO` is returned.
* The `controlTypes.isCurrentLabels` mapping has been removed. (#11782)
  * Instead use the `displayString` property on a `controlTypes.IsCurrent` enum value.
    * For example: `controlTypes.IsCurrent.YES.displayString`.
* `winKernel.GetTimeFormat` has been removed - use `winKernel.GetTimeFormatEx` instead. (#12139)
* `winKernel.GetDateFormat` has been removed - use `winKernel.GetDateFormatEx` instead. (#12139)
* `gui.DriverSettingsMixin` has been removed - use `gui.AutoSettingsMixin`. (#12144)
* `speech.getSpeechForSpelling` has been removed - use `speech.getSpellingSpeech`. (#12145)
* Commands cannot be directly imported from speech as `import speech; speech.ExampleCommand()` or `import speech.manager; speech.manager.ExampleCommand()` - use `from speech.commands import ExampleCommand` instead. (#12126)
* `speakTextInfo` will no longer send speech through `speakWithoutPauses` if reason is `SAYALL`, as `SayAllHandler` does this manually now. (#12150)
* The `synthDriverHandler` module is no longer star imported into `globalCommands` and `gui.settingsDialogs` - use `from synthDriverHandler import synthFunctionExample` instead. (#12172)
* `ROLE_EQUATION` has been removed from controlTypes - use `ROLE_MATH` instead. (#12164)
* `autoSettingsUtils.driverSetting` classes are removed from `driverHandler` - please use them from `autoSettingsUtils.driverSetting`. (#12168)
* `autoSettingsUtils.utils` classes are removed from `driverHandler` - please use them from `autoSettingsUtils.utils`. (#12168)
* Support of `TextInfo`s that do not inherit from `contentRecog.BaseContentRecogTextInfo` is removed. (#12157)
* `speech.speakWithoutPauses` has been removed - please use `speech.speechWithoutPauses.SpeechWithoutPauses(speakFunc=speech.speak).speakWithoutPauses` instead. (#12195, #12251)
* `speech.re_last_pause` has been removed - please use `speech.speechWithoutPauses.SpeechWithoutPauses.re_last_pause` instead. (#12195, #12251)
* `WelcomeDialog`, `LauncherDialog` and `AskAllowUsageStatsDialog` are moved to the `gui.startupDialogs`. (#12105)
* `getDocFilePath` has been moved from `gui` to the `documentationUtils` module. (#12105)
* The gui.accPropServer module as well as the AccPropertyOverride and ListCtrlAccPropServer classes from the gui.nvdaControls module have been removed in favor of WX native support for overriding accessibility properties. When enhancing accessibility of WX controls, implement wx.Accessible instead. (#12215)
* Files in `source/comInterfaces/` are now more easily consumable by developer tools such as IDEs. (#12201)
* Convenience methods and types have been added to the winVersion module for getting and comparing Windows versions. (#11909)
  * isWin10 function found in winVersion module has been removed.
  * class winVersion.WinVersion is a comparable and order-able type encapsulating Windows version information.
  * Function winVersion.getWinVer has been added to get a winVersion.WinVersion representing the currently running OS.
  * Convenience constants have been added for known Windows releases, see winVersion.WIN* constants.
* IAccessibleHandler no longer star imports everything from IAccessible and IA2 COM interfaces - please use them directly. (#12232)
* TextInfo objects now have start and end properties which can be compared mathematically with operators such as < <= == != >= >. (#11613)
  * E.g. ti1.start <= ti2.end
  * This usage is now prefered instead of ti1.compareEndPoints(ti2,"startToEnd") <= 0
* TextInfo start and end properties can also be set to each other. (#11613)
  * E.g. ti1.start = ti2.end
  * This usage is prefered instead of ti1.SetEndPoint(ti2,"startToEnd")
* `wx.CENTRE_ON_SCREEN` and `wx.CENTER_ON_SCREEN` are removed, use `self.CentreOnScreen()` instead. (#12309)
* `easeOfAccess.isSupported` has been removed, NVDA only supports versions of Windows where this evaluates to `True`. (#12222)
* `sayAllHandler` has been moved to `speech.sayAll`. (#12251)
  * `speech.sayAll.SayAllHandler` exposes the functions `stop`, `isRunning`, `readObjects`, `readText`, `lastSayAllMode`.
  * `SayAllHandler.stop` also resets the `SayAllHandler` `SpeechWithoutPauses` instance.
  * `CURSOR_REVIEW` and `CURSOR_CARET` has been replaced with `CURSOR.REVIEW` and `CURSOR.CARET`.
* `speech.SpeechWithoutPauses` has been moved to `speech.speechWithoutPauses.SpeechWithoutPauses`. (#12251)
* `speech.curWordChars` has been renamed `speech._curWordChars`. (#12395)
* the following have been removed from `speech` and can be accessed through `speech.getState()`. These are readonly values now. (#12395)
  * speechMode
  * speechMode_beeps_ms
  * beenCanceled
  * isPaused
* to update `speech.speechMode` use `speech.setSpeechMode`. (#12395)
* the following have been moved to `speech.SpeechMode`. (#12395)
  * `speech.speechMode_off` becomes `speech.SpeechMode.off`
  * `speech.speechMode_beeps` becomes `speech.SpeechMode.beeps`
  * `speech.speechMode_talk` becomes `speech.SpeechMode.talk`
* `IAccessibleHandler.IAccessibleObjectIdentifierType` is now `IAccessibleHandler.types.IAccessibleObjectIdentifierType`. (#12367)
* The following in `NVDAObjects.UIA.WinConsoleUIA` have been changed (#12094)
  * `NVDAObjects.UIA.winConsoleUIA.is21H1Plus` renamed `NVDAObjects.UIA.winConsoleUIA.isImprovedTextRangeAvailable`.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfo` renamed to start class name with upper case.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfoPre21H1` renamed `NVDAObjects.UIA.winConsoleUIA.ConsoleUIATextInfoWorkaroundEndInclusive`
    * The implementation works around both end points being inclusive (in text ranges) before [microsoft/terminal PR 4018](https://github.com/microsoft/terminal/pull/4018)
    * Workarounds for `expand`, `collapse`, `compareEndPoints`, `setEndPoint`, etc

## 2020.4

Questa versione introduce nuovi metodi di input cinesi, un aggiornamento alle tabelle braille Liblouis e la possibilità di eseguire la funzione elenco elementi nelle pagine web anche in modalità focus (NVDA+f7).
Quando ci si trova nelle finestre di dialogo delle impostazioni di NVDA, il tasto f1 aprirà l'aiuto contestuale per quella particolare sezione.
Vi sono poi dei sensibili miglioramenti nelle regole di pronuncia dei simboli, nei dizionari, nei messaggi braille e nella lettura rapida.
Sono inoltre stati risolti bug che riguardavano Mail, Outlook, Teams, Visual Studio, Azure Data Studio, Foobar2000.
Per ciò che concerne il web i miglioramenti riguardano Google Docs, oltre ad un miglior supporto ad ARIA.
Di seguito l'elenco di tutte le novità.

### Novità

* Se si Preme F1 nelle finestre di dialogo di NVDA, verrà aperta la guida nella sezione più pertinente. (#7757)
* Supporto per i suggerimenti di completamento automatico (IntelliSense) in Microsoft SQL Server Management Studio più Visual Studio 2017 e versioni successive. (#7504)
* Pronuncia simboli: possibilità di definire raggruppamenti di simboli complessi con conseguente capacità di referenziarli nel campo voce in sostituzione; in questo modo si possono ottenere regole più semplici e potenti. (#11107)
* Gli utenti ora vengono avvisati quando tentano di creare voci del dizionario con sostituzioni di espressioni regolari non valide. (#11407)
  * Vengono ora rilevati errori specifici di raggruppamento.
* Aggiunto supporto per i nuovi metodi di immissione cinese tradizionale Quick and Pinyin in Windows 10. (#11562)
* Le intestazioni delle schede sono considerate campi di un form quando si preme il tasto di navigazione veloce f. (#10432)
* Aggiunto un comando per attivare / disattivare la segnalazione del testo contrassegnato (evidenziato); Non esiste alcun gesto associato predefinito. (#11807)
* Aggiunto il parametro a riga di comando --copy-portable-config che permette di copiare automaticamente la configurazione fornita all'interno del profilo utente quando si installa NVDA in maniera silenziosa. (#9676)
* Vengono ora supportate le operazioni di cursor routing nel visualizzatore braille, facendo passare il mouse sopra le celle. (#11804)
* NVDA è in grado di individuare automaticamente i display braille Humanware Brailliant BI 40X e 20X via USB e Bluetooth. (#11819)

### Cambiamenti

* Aggiornate le tabelle di traduzione braille Liblouis alla versione 3.16.1:
 * Risolti diversi crash
 * Aggiunta la tabella Bashkir grado 1
 * Aggiunta la tabella Copto a otto punti
 * Aggiunte le tabelle per il braille letterario russo e letterario dettagliato.
 * Rimossa la tabella russo grado 1.
 * Aggiunta tabella braille afrikaans di grado 2
* Mentre si utilizza la funzione dire tutto in modalità navigazione, i comandi cerca testo successivo o precedente non interrompono più la lettura nel caso in cui sia attiva l'opzione consenti navigazione rapida in lettura; essa riprenderà subito dopo aver letto il termine di ricerca richiesto. (#11563)
* Per i display braille Hims, il tasto f3 è stato rimappato alla combinazione Spazio + punti 148. (#11710)
* Migliorata la presentazione delle funzioni di "timeout messaggi braille" e "Mostra messaggi a tempo indeterminato" (#11602)
* Nei browser web ealtre applicazioni che supportano la modalità navigazione, la finestra elenco elementi (NVDA+f7) può essere richiamata anche dalla modalità focus. (#10453)
* Non vengono più annunciati gli aggiornamenti alle regioni live Aria nel caso in cui l'opzione "leggi cambiamenti contenuti dinamici" è disabilitata. (#9077)
* NVDA annuncerà "copiato negli appunti" prima del testo stesso; per esempio, quando si preme nvda+t 3 volte per copiare il titolo negli appunti, adesso lo screen reader prima dirà "copiato negli appunti" e poi leggerà cosa è stato copiato. (#6757)
* La presentazione della tabella di visualizzazione grafica nella gestione del disco è stata migliorata. (#10048)
* Le etichette per i controlli sono ora disattivate (in grigio) quando il controllo è disabilitato. (#11809)
* Aggiornata alla versione 38 CLDR emoji annotation. (#11817)
* Cambiamenti per alcune lingue sulla terminologia delle preferenze della sezione Visione, non coinvolgono l'italiano. (#11700)

### Bug Corretti

* NVDA funziona di nuovo correttamente con i campi editazione quando si utilizza l'applicazione Fast Log Entry. (#8996)
* In FooBar2000, se non è disponibile il tempo totale, viene annunciato il tempo trascorso, ad esempio durante un live streaming. (#11337)
* NVDA ora rispetta l'attributo  aria-roledescription negli elementi in modalità editazione nelle pagine web. (#11607)
* Non viene più annunciata ripetutamente la parola 'elenco' per ciascuna riga di un elenco in Google Docs o altri contenuti modificabili in Google Chrome. (#7562)
* Nei campi editazione web, quando ci si sposta con le frecce per caratteri o parole, ora si verrà avvisati quando si passa da un elemento di elenco ad un altro (#11569)
* NVDA ora legge la riga corretta quando il cursore è posizionato alla fine di un link di una voce di elenco in Documenti Google o altri contenuti modificabili Web. (#11606)
* In Windows 7, il focus viene sempre posizionato correttamente quando si apre o chiude il menu avvio dal desktop. (#10567)
* Se l'opzione "Tenta di non leggere informazioni obsolete concernenti il focus" risulta attiva, viene nuovamente letto il titolo della scheda corrente quando si preme ctrl-tab in Firefox. (#11397)
* Se ci si trova in un elenco, NVDA ora gestisce correttamente la lettura dell'elemento dopo aver digitato un carattere  quando si utilizzano le sintesi vocali Ivona di SAPI5. (#11651)
* È nuovamente possibile utilizzare la modalità di navigazione durante la lettura delle e-mail in Windows 10 Mail 16005.13110 e versioni successive. (#11439)
* Quando si utilizzano le voci SAPI5 Ivona da harposoftware.com, NVDA è ora in grado di salvare la configurazione, cambiare sintetizzatore e non rimarrà più in silenzio dopo il riavvio. (#11650)
* Ora è possibile inserire il numero 6 con il computer braille dalla tastiera sui display HIMS. (#11710)
* Grossi miglioramenti delle prestazioni in Azure Data Studio. (#11533, #11715)
* Viene letto nuovamente il titolo della finestra trova di NVDA anche quando l'opzione "Tenta di non leggere informazioni obsolete concernenti il focus" è attiva. (#11632)
* NVDA non dovrebbe più bloccarsi quando si riattiva il computer e il focus si trova su un documento Microsoft Edge. (#11576)
* Non risulta più necessario premere tab o spostare il focus dopo aver chiuso un menu di contesto in MS Edge per avere di nuovo la modalità navigazione funzionante. (#11202)
* NVDA non ha più problemi nel leggere gli elementi nelle visualizzazioni elenco all'interno di un'applicazione a 64 bit come Tortoise SVN. (#8175)
* Gli elementi ARIA treegrids vengono ora presentati come tabelle normali in modalità navigazione sia in Firefox che in Chrome. (#9715)
* È ora possibile avviare una ricerca inversa attraverso la funzione "trova precedente" tramite NVDA + MAIUSC + F3 (#11770)
* Uno script di NVDA non viene più considerato ripetuto se si verifica una pressione di un tasto non correlata tra le due esecuzioni dello script. (#11388)
* è possibile non farsi più annunciare la presenza dei tag strong e di enfasi in Internet Explorer disattivando la casella di controllo Enfasi nelle impostazioni di formattazione del documento di NVDA. (#11808)
* In Excel, quando ci si spostaacon le frecce, non si dovrebbero più verificare blocchi di alcuni secondi, cosa sperimentata da una piccola percentuale di utenti. (#11818)
* In Microsoft Teams con numero di versione 1.3.00.28xxx, NVDA non presenta più problemi nella lettura di messaggi in chat o canali Teams dovuti ad una focalizzazione errata di un menu. (#11821)
* Il testo contrassegnato contemporaneamente come errore di ortografia e di grammatica in Google Chrome verrà opportunamente annunciato. (#11787)
* Quando si utilizza Outlook (lingua francese), la scorciatoia per "Rispondi a tutti" (CTRL + MAIUSC + R) funziona di nuovo. (#11196)
* In Visual Studio, i suggerimenti che forniscono dettagli aggiuntivi sull'elemento IntelliSense attualmente selezionato vengono ora segnalati solo una volta. (#11611)
* Nella calcolatrice di In Windows 10, NVDA non annuncerà l'avanzamento dei calcoli nel caso in cui la digitazione caratteri sia disattivata. (#9428)
* NVDA non si arresta più nel caso in cui si stia utilizzando la tabella Us-English grado 2 computer Braille con il cursore attivo, mentre ci si trova su stringhe di caratteri quali gli URL. (#11754)
* È nuovamente possibile conoscere le informazioni di formattazione per la cella Excel focalizzata utilizzando NVDA + F. (#11914)
* Nei Display Braille Papenmeier è nuovamente possibile servirsi della modalità qwerty, se supportata dalla barra, non causando più il blocco random dello screen reader. (#11944)
* Nei browser basati su Chromium, sono stati risolti diversi casi in cui la navigazione nella tabella non funzionava e NVDA non riportava il numero di righe/colonne della tabella. (#12359)\n

### Changes for Developers

* System tests can now send keys using spy.emulateKeyPress, which takes a key identifier that conforms to NVDA's own key names, and by default also blocks until the action is executed. (#11581)
* NVDA no longer requires the current directory to be the NVDA application directory in order to function. (#6491)
* The aria live politeness setting for live regions can now be found on NVDA Objects using the liveRegionPoliteness property. (#11596)
* It is now possible to define separate gestures for Outlook and Word document. (#11196)

## 2020.3

Questa versione include diversi miglioramenti alla stabilità e alle prestazioni, in particolare nelle applicazioni di Microsoft Office. Sono disponibili nuove impostazioni per attivare/disattivare il supporto al touchscreen e la lettura dei grafici.
Nei browser è possibile farsi annunciare la presenza di contenuto contrassegnato (evidenziato), inoltre sono disponibili nuove tabelle braille tedesche.

### Novità

* È ora possibile attivare o disattivare la lettura dei grafici dalle impostazioni formattazione documento di NVDA. Notare che disabilitando questa opzione verrà comunque letto il testo alternativo dei grafici. (#4837)
* Possibilità di attivare o disattivare il supporto al touchscreen in NVDA. È stata aggiunta un'opzione al pannello Interazioni Tocco delle impostazioni. Il tasto rapido predefinito è NVDA+control+alt+t. (#9682)
* Aggiunte nuove tabelle braille tedesche. (#11268)
* NVDA ora è in grado di intercettare i controlli UIA di testo di sola lettura. (#10494)
* Viene annunciato in tutti i browser web l'esistenza di contenuto contrassegnato (evidenziato), sia tramite sintesi vocale che in braille. (#11436)
 * Ciò può essere attivato e disattivato da una nuova opzione nelle impostazioni formattazione documento per l'evidenziazione.
* Possono essere aggiunti nuovi comandi di sistema simulati con combinazioni di tasti dalla finestra di dialogo Gesti di Immissione di NVDA. (#6060)
  * Per fare questo, premere il pulsante aggiungi dopo aver selezionato la categoria Emulazione comandi di sistema.
* Aggiunto il supporto al Display Braille Handy Tech Active Braille con joystick. (#11655)
* "La modalità focus automatica per i movimenti del cursore" ora è compatibile con la disattivazione del parametro "sposta automaticamente il focus sugli elementi focalizzabili". (#11663)

### Cambiamenti

* Lo script per conoscere la formattazione del carattere (NVDA+f) ora riporta le informazioni relative al cursore di sistema, non del cursore di controllo. Per conoscere la formattazione relativa al cursore di controllo, servirsi della combinazione di tasti NVDA+Shift+f. (#9505)
* In modalità navigazione, NVDA non sposta più di default il focus di sistema sugli elementi focalizzabili, il che va a migliorare prestazioni e stabilità. (#11190)
* Aggiornamento CLDR dalla versione 36.1 alla versione 37. (#11303)
* Aggiornata eSpeak-NG a 1.51-dev, commit 1fb68ffffea4
* Ora è possibile servirsi dei comandi di navigazione tabella nelle caselle ad elenco con elementi attivabili, se quel particolare elenco dispone di colonne multiple. (#8857)
* Nel gestore componenti aggiuntivi, quando viene richiesto di confermare la rimozione di un componente, ora  l'impostazione predefinita è "NO". (#10015)
* In Microsoft Excel, la finestra di dialogo dell'elenco elementi ora visualizza le formule nella lingua originale. (#9144)
* NVDA ora riporta la terminologia corretta per le note in MS Excel. (#11311)
* In modalità navigazione, quando si utilizza il comando "sposta il cursore di controllo al focus", la posizione del cursore di controllo coinciderà con quella del cursore virtuale. (#9622)
* Le informazioni riportate in modalità navigazione, come quelle relative alla formattazione, vengono ora visualizzate in una finestra leggermente più grande posizionata a centro schermo. (#9910)

### Bug Corretti

* NVDA ora non smette più di parlare se ci si sposta parola per parola e si finisce su un simbolo seguito da uno spazio vuoto, quale che sia il livello di verbosità.. (#5133)
* Nelle applicazioni che utilizzano QT 5.11 o più recenti, vengono nuovamente annunciate le descrizioni degli oggetti. (#8604)
* Se si cancella una parola con control+canc, NVDA non rimarrà più erroneamente in silenzio. (#3298, #11029)
  * Ora viene annunciata la parola a destra di quella eliminata.
* Nel pannello delle impostazioni generali, è stato riordinato correttamente l'elenco lingue. (#10348)
* Nella finestra di dialogo tasti e gesti di immissione, sono notevolmente migliorate le prestazioni quando si filtrano i dati. (#10307)
* è ora possibile inviare caratteri unicode da un display braille oltre U+FFFF. (#10796)
* NVDA gestisce correttamente il contenuto della finestra "Apri con" nell'aggiornamento di Windows 10 maggio 2020. (#11335)
* Una nuova funzionalità sperimentale nelle impostazioni avanzate (Abilita la registrazione selettiva per eventi UI Automation e cambiamenti di proprietà) può fornire prestazioni migliori in Microsoft Visual Studio e altre applicazioni basate su UIAutomation. (#11077, #11209)
* Per gli elementi elenco selezionabili, non viene più annunciato in maniera ridondante lo stato selezionato, e se applicabile, viene riportato lo stato "non selezionato". (#8554)
* In Windows 10 aggiornamento Maggio 2020, NVDA ora propone anche Microsoft Sound Mapper nell'elenco dei dispositivi d'uscita nella finestra sintetizzatori. (#11349)
* In Internet Explorer, i numeri vengono ora annunciati correttamente negli gli elenchi ordinati se l'elenco non inizia con 1. (#8438)
* In Google chrome, NVDA annuncerà non selezionato in tutti i controlli potenzialmente selezionabili (non solo le caselle di controllo). (#11377)
* ripristinata la possibilità di navigare in vari controlli se NVDA viene impostato con lingua aragonese. (#11384)
* NVDA non si dovrebbe più bloccare in  Microsoft Word se ci si sposta rapidamente su e giù con le frecce o si digitano dei caratteri e si sta utilizzando un display braille.. (#11431, #11425, #11414)
* NVDA non aggiunge più degli spazi se si copia il contenuto del navigatore ad oggetti negli appunti. (#11438)
* NVDA non attiva più il profilo Dire Tutto nel caso in cui non ci sia nulla da leggere. (#10899, #9947)
* NVDA è di nuovo in grado di leggere l'elenco caratteristiche in Internet Information Services (IIS) Manager. (#11468)
* NVDA ora mantiene il dispositivo audio attivo migliorando le prestazioni su alcune schede audio (#5172, #10721)
* NVDA non si blocca più o non si chiude se viene premuta la combinazione di tasti control+shift+FrecciaGiù in Microsoft Word. (#9463)
* NVDA è in grado di annunciare correttamente lo stato espanso/non espanso della visualizzazione dell'albero delle cartelle in drive.google.com. (#11520)
* NVDA riconoscerà automaticamente il Display Braille NLS eReader Humanware via bluetooth. (#11561)
* Grossi miglioramenti delle prestazioni in Visual Studio Code. (#11533)

### Changes For Developers

* The GUI Helper's BoxSizerHelper.addDialogDismissButtons supports a new "separated" keyword argument, for adding a standard horizontal separator to dialogs (other than messages and single input dialogs). (#6468)
* Additional properties were added to app modules, including path for the executable (appPath), is a Windows Store app (isWindowsStoreApp), and machine architecture for the app (appArchitecture). (#7894)
* It is now possible to create app modules for apps hosted inside wwahost.exe on Windows 8 and later. (#4569)
* A fragment of the log can now be delimited and then copied to clipboard using NVDA+control+shift+F1. (#9280)
* NVDA-specific objects that are found by Python's cyclic garbage collector are now logged when being deleted by the collector to aide in removing reference cycles from NVDA. (#11499)
 * The majority of NVDA's classes are tracked including NVDAObjects, appModules, GlobalPlugins, SynthDrivers, and TreeInterceptors.
 * A class that needs to be tracked should inherit from garbageHandler.TrackedObject.
* Significant debug logging for MSAA events can be now enabled in NVDA's Advanced settings. (#11521)
* MSAA winEvents for the currently focused object are no longer filtered out along with other events if the event count for a given thread is exceeded. (#11520)

## 2020.2

Le caratteristiche più rilevanti di questa versione comprendono il supporto ad un nuovo display braille prodotto dalla Nattiq, la gestione migliorata dell'interfaccia grafica dell'antivirus Eset e di Windows Terminal, prestazioni più performanti in 1Password e con le sintesi vocali OneCore di Windows. Oltre naturalmente ad un gran numero di bug risolti.

### Novità

* Supporto per nuovi display braille:
  * Nattiq nBraille (#10778)
* Aggiunto uno script per aprire la cartella di configurazione di NVDA (Nessun gesto predefinito assegnato). (#2214)
* Miglior supporto per l'interfaccia grafica di ESET antivirus. (#10894)
* Aggiunto il supporto a Windows Terminal. (#10305)
* Aggiunto un comando per annunciare il profilo di configurazione attivo (nessun gesto di default assegnato). (#9325)
* Aggiunto un comando per attivare/disattivare la lettura di apici/pedici (nessun gesto assegnato di default). (#10985)
* Le applicazioni Web (ad esempio Gmail) non annunciano più informazioni obsolete se si sposta il focus con rapidità. (#10885)
  * Questa correzione sperimentale deve essere attivata manualmente tramite la casella di controllo 'tenta di non leggere informazioni obsolete concernenti il focus' nella finestra di dialogo avanzate.
* Sono stati aggiunti molti nuovi simboli al dizionario predefinito. (#11105)

### Cambiamenti

* Aggiornata liblouis braille translator da 3.12 a [3.14.0](https://github.com/liblouis/liblouis/releases/tag/v3.14.0). (#10832, #11221)
* A causa di modifiche in VS Code, NVDA non disabilita più la modalità navigazione in Code di default. (#10888)
* La segnalazione di apici e pedici è gestita separatamente dagli attributi carattere. (#10919)
* NVDA non annuncia più "all'inizio" e "alla fine" quando si sposta il cursore di controllo direttamente alla prima o all'ultima riga dell'oggetto corrente con gli script vai all'inizio e vai alla fine relativi al cursore di controllo. (#9551)
* NVDA non annuncia più "destra" o "sinistra" quando si sposta il cursore di controllo direttamente al primo o all'ultimo carattere della riga dell'oggetto corrente con gli script vai a inizio riga e vai a fine riga relativi al cursore di controllo. (#9551)

### Bug Corretti

* NVDA si avvia correttamente anche quando non può essere creato un file di log. (#6330)
* Nelle ultime versioni di Microsoft Word 365, NVDA non annuncerà più "parola precedente cancellata" se viene premuto Control+Backspace mentre si modifica un documento. (#10851)
* In Winamp, NVDA annuncerà nuovamente lo stato di shuffle e ripetizione. (#10945)
* NVDA non è più estremamente lento quando ci si sposta all'interno dell'elenco elementi in 1Password. (#10508)
* Il sintetizzatore vocale Windows OneCore non effettua più lunghe pause tra le frasi. (#10721)
* NVDA non si blocca più quando si apre il menu di scelta rapida di 1Password dalla SystemTray. (#11017)
* In Office 2013 e versioni precedenti:
  * I menu ribbon vengono letti quando il focus si sposta su di essi per la prima volta. (#4207)
  * Vengono nuovamente lette correttamente le voci relative al menu di contesto. (#9252)
  * Le sezioni ribbon sono lette in maniera omogenea quando ci si sposta con control-frecce. (#7067)
* In modalità navigazione in Mozilla Firefox e Google Chrome, il testo non viene più erroneamente visualizzato su una riga separata quando il contenuto Web utilizza la visualizzazione CSS: inline-flex. (#11075)
* In modalità navigazione con la funzione "spostamento del focus durante la navigazione" disattivata, risulta ora possibile attivare elementi su cui non può essere portato il focus.
* In modalità navigazione con la funzione "spostamento del focus durante la navigazione" disattivata, risulta ora possibile attivare elementi raggiunti con la pressione del tasto tab. (#8528)
* In modalità navigazione con la funzione "spostamento del focus durante la navigazione" disattivata, l'attivazione di determinati elementi non comporta più il click in una posizione errata. (#9886)
* Non si ascolteranno più suoni di errore di NVDA quando si accede ai controlli di testo DevExpress. (#10918)
* Non vengono più annunciati i suggerimenti relativi alle icone del System Tray mentre si naviga con la tastiera, se il testo in essi contenuto è uguale a quello delle icone, evitando così la doppia lettura. (#6656)
* In modalità navigazione con la funzione "spostamento del focus durante la navigazione" disattivata, il passaggio alla modalità focus con NVDA-spazio ora focalizza l'elemento sotto il cursore. (#11206)
* È di nuovo possibile verificare la presenza di aggiornamenti NVDA su alcuni sistemi; per esempio installazioni di Windows pulite. (#11253)
* Il focus non si sposta in applicazioni Java quando la selezione viene posta in un albero, tabella o elenco non focalizzati. (#5989)

### Changes For Developers

* execElevated and hasUiAccess have moved from config module to systemUtils module. Usage via config module is deprecated. (#10493)
* Updated configobj to 5.1.0dev commit f9a265c4. (#10939)
* Automated testing of NVDA with Chrome and a HTML sample is now possible. (#10553)
* IAccessibleHandler has been converted into a package, OrderedWinEventLimiter has been extracted to a module and unit tests added (#10934)
* Updated BrlApi to version 0.8 (BRLTTY 6.1). (#11065)
* Status bar retrieval may now be customized by an AppModule. (#2125, #4640)
* NVDA no longer listens for IAccessible EVENT_OBJECT_REORDER. (#11076)
* A broken ScriptableObject (such as a GlobalPlugin missing a call to its base class' init method) no longer breaks NVDA's script handling. (#5446)

## 2020.1

Le principali migliorie presenti in questa versione si concentrano sul supporto per molti nuovi display braille prodotti da HumanWare e APH, oltre a molti importanti bug risolti , come la possibilità di leggere nuovamente i contenuti di tipo matematico presenti in Microsoft Word usando MathPlayer / MathType.

### Novità

* L'elemento selezionato nelle caselle combinate di Google Chrome viene nuovamente mostrato anche in modalità navigazione, così come avveniva in NVDA 2019.1. (#10713)
* Ora è possibile eseguire clic con il tasto destro del mouse sui dispositivi touch toccando e tenendo premuto un dito. (#3886)
* Supporto per nuovi Display Braille: APH Chameleon 20, APH Mantis Q40, HumanWare BrailleOne, BrailleNote Touch v2, e NLS eReader. (#10830)

### Cambiamenti

* NVDA impedisce al sistema di bloccarsi o andare in modalità di sospensione durante la modalità dire tutto. (#10643)
* Supporto per iframe fuori processo in Mozilla Firefox. (#10707)
* Aggiornato liblouis braille translator alla versione 3.12. (#10161)

### Bug Corretti

* Risolto il problema con NVDA che non annunciava il simbolo meno Unicode (U+2212). (#10633)
* Durante l'installazione di un addon da Gestione componenti aggiuntivi, i nomi dei file e cartelle nella finestra di ricerca non vengono più annunciati due volte. (#10620, #2395)
* In Firefox, quando si carica Mastodon con l'interfaccia Web avanzata abilitata, tutte le varie cronologie ora vengono visualizzate correttamente in modalità navigazione. (#10776)
* In modalità navigazione, NVDA ora dirà "non attivato" per le caselle di controllo non selezionate, correggendo un bug che talvolta le faceva pronunciare come attivate. (#10781)
* Non vengono piu' fornite informazioni errate sugli interruttori dei controlli Aria, come "non premuto attivato" o "premuto attivato". (#9187)
* Le voci SAPI4 non dovrebbero piu' presentare problemi nella pronuncia di alcune sezioni di testo. (#10792)
* NVDA può di nuovo leggere ed interagire con le equazioni matematiches in Microsoft Word. (#10803)
* NVDA annuncerà nuovamente  che il testo viene deselezionato in modalità navigazione se viene premuto un tasto freccia quando vi è del testo selezionato. (#10731).
* NVDA non si chiuderà più nel caso in cui vi sia un errore durante l'inizializzazione di Espeak. (#10607)
* Nel caso in cui vi siano errori unicode nelle traduzioni internazionali sui tasti rapidi, il programma di installazione non si bloccherà più e passerà alla lingua inglese. (#5166, #6326)
* Migliorata la gestione di tabelle ed elenchi in modalità dire tutto, ora NVDA risulta meno prolisso. (#10706)
* Risolto il problema con il tracciamento del mouse per alcuni elementi MSHTML in Internet Explorer. (#10736)

### Changes for Developers

* Developer documentation is now build using sphinx. (#9840)
* Several speech functions have been split into two. (#10593)
  The speakX version remains, but now depends on a getXSpeech function which returns a speech sequence.
  * speakObjectProperties now relies on getObjectPropertiesSpeech
  * speakObject now relies on getObjectSpeech
  * speakTextInfo now relies on getTextInfoSpeech
  * speakWithoutPauses has been converted into a class, and refactored, but should not break compatibility.
  * getSpeechForSpelling is deprecated (though still available) use getSpellingSpeech instead.
  Private changes that should not affect addon developers:
  * _speakPlaceholderIfEmpty is now _getPlaceholderSpeechIfTextEmpty
  * _speakTextInfo_addMath is now _extendSpeechSequence_addMathForTextInfo
* Speech 'reason' has been converted to an Enum, see controlTypes.OutputReason class. (#10703)
  * Module level 'REASON_*' constants are deprecated.
* Compiling NVDA dependencies now requires Visual Studio 2019 (16.2 or newer). (#10169)
* Updated SCons to version 3.1.1. (#10169)
* Again allow behaviors._FakeTableCell to have no location defined (#10864)

## 2019.3

NVDA 2019.3 è una versione molto importante e significativa che contiene diversi cambiamenti sotto il cofano, in special modo è stato riscritto il sottosistema che gestisce le sintesi vocali ed è stata effettuata la transizione da Python2 a Python3.
Sebbene questi cambiamenti abbiano reso molti componenti aggiuntivi non più compatibili, essi sono stati necessari sia per ragioni di sicurezza, sia per lo sviluppo di funzionalità interessanti nell'immediato futuro.
 Altre novità di questa versione comprendono il supporto a 64 bit per Java VMS, l'introduzione della tenda schermo, funzioni di evidenziazione del focus, supporto per nuovi display braille e un visualizzatore braille, oltre ad un gran numero di correzioni.

### Novità

* è stata migliorata l'accuratezza dello spostamento del mouse sul navigatore ad oggetti nei campi di testo in applicazioni Java. (#10157)
* Aggiunto il supporto per i seguenti display braille di Handy Tech (#8955):
 * Basic Braille Plus 40
 * Basic Braille Plus 32
 * Connect Braille
* Tutti i gesti definiti dall'utente ora possono essere rimossi tramite il nuovo pulsante "Ripristina impostazioni predefinite" nella finestra tasti e gesti di immissione. (#10293)
* In Microsoft Word nelle informazioni carattere viene segnalato se il testo è marcato come "nascosto". (#8713)
* Aggiunto un comando per spostare il cursore di controllo nella posizione precedentemente impostata come marcatore di inizio selezione o copia: NVDA+Maiusc+F9. (#1969)
* In Internet Explorer, Microsoft Edge e versioni recenti di Firefox e Chrome, i punti di riferimento sono ora riportati sia in modalità focus che in navigazione oggetti. (#10101)
* In Internet Explorer, Google Chrome e Mozilla Firefox, ora è possibile navigare per articoli e raggruppamenti utilizzando i tasti di navigazione rapida. Di default, Questi script non sono associati ad alcun tasto, bisogna perciò servirsi della finestra "tasti e gesti di immissione", da aprirsi quando ci si trova in un documento in modalità navigazione. (#9485, #9227)
 * Vengono inoltre annunciate anche le Figure. Esse sono considerate alla stregua degli oggetti e raggiungibili sempre con la lettera "o".
* In Internet Explorer, Google Chrome e Mozilla Firefox, vengono segnalati con la modalità navigazione ad oggetti gli elementi degli articoli, e facoltativamente anche in modalità navigazione se la funzione è attivata nelle impostazioni formattazione documento. (#10424)
* Aggiunta la funzione "tenda schermo"; quando attiva rende lo schermo nero in Windows8 e versioni successive. (#7857)
 * Aggiunto uno script per abilitare la tenda schermo (la pressione singola lo rende efficace fino al riavvio di NVDA, la doppia pressione per sempre mentre lo screen reader è in esecuzione), a questo script non è stato assegnato alcun tasto o gesto predefinito.
 * Può essere abilitato e configurato tramite la categoria 'visione' nella finestra di dialogo delle impostazioni di NVDA.
* Aggiunte funzioni di evidenziazione schermo. (#971, #9064)
 * Dalla finestra impostazioni di NVDA, categoria visione,  possono essere abilitate funzioni quali evidenziazione del focus, del navigatore ad oggetti e della posizione del cursore di navigazione.
 * Nota: questa funzione non è compatibile con il componente aggiuntivo Focus Highlight. è comunque ancora possibile servirsi di quell'addon disattivando l'evidenziatore incorporato.
* Aggiunto uno strumento chiamato visualizzatore braille, che consente di mostrare ciò che appare sul display braille in una finestra a schermo. (#7788)

### cambiamenti

* La guida utente ora descrive come utilizzare NVDA nella console di Windows. (#9957)
* L'esecuzione di nvda.exe ora chiuderà e sostituirà di default un'eventuale copia già in esecuzione di NVDA. Il parametro a riga di comando -r | --replace è ancora accettato, ma ignorato. (#8320)
* Su Windows 8 e versioni successive, NVDA ora è in grado di leggere il nome del prodotto e le informazioni sulla versione anche per le app scaricate da Microsoft Store, utilizzando le informazioni fornite dall'app stessa. (#4259, #10108)
* In Microsoft Word, se si attiva o disattiva la funzione di tracciamento modifiche tramite la tastiera, NVDA annuncerà lo stato dell'impostazione. (#942)
* Il numero di versione di NVDA è ora salvato come primo messaggio nel log. Ciò si verifica anche se le funzionalità di logging sono state disabilitate dalla GUI. (#9803)
* La finestra di dialogo delle impostazioni non consente più di modificare il livello di log se è stato specificato dalla riga di comando. (#10209)
* In Microsoft Word, NVDA ora annuncia lo stato di visualizzazione dei caratteri non stampabili quando si preme la combinazione di tasti Ctrl+Maiusc+8. (#10241)
* Aggiornato Liblouis braille translator alla commit 58d67e63. (#10094)
* Quando la lettura dei caratteri CLDR (come le emoji) è abilitata, essi vengono riportati su tutti i livelli di punteggiatura. (#8826)
* I pacchetti python di terze parti inclusi in NVDA, come comtype, ora salvano eventuali avvisi ed errori nel log di NVDA. (#10393)
* Aggiornate le annotazioni Emoji Unicode Common Locale Data Repository alla versione 36.0. (#10426)
* Quando viene focalizzato un raggruppamento in modalità navigazione, viene letta anche la descrizione. (#10095)
* Java Access Bridge viene sempre distribuito con NVDA per permettere ed abilitare l'accesso alle applicazioni Java, comprese JAVA VMS a 64 bit. (#7724)
* Se Java Access Bridge non è abilitato per l'utente, NVDA lo attiverà automaticamente all'avvio dello screen reader. (#7952)
* Aggiornata eSpeak-NG alla versione 1.51-dev, commit ca65812ac6019926f2fbd7f12c92d7edd3701e0c. (#10581)

### Bug corretti

* Le Emoji e altri caratteri unicode a 32 bit occupano meno spazio in un display braille quando mostrati come valore esadecimale. (#6695)
* In Windows 10, NVDA annuncerà i suggerimenti dalle app universali se la funzione "leggi i tooltip" è attiva. (#8118)
* In Windows 10 Anniversary Update e versioni successive, il testo digitato viene ora riportato in Mintty. (#1348)
* In Windows 10 Anniversary Update e versioni successive, NVDA non ripeterà più volte i caratteri presenti vicini al cursore nella Console di Windows. (#513)
* Vengono ora letti correttamente i controlli nella finestra di dialogo del compressore in Audacity. (#10103)
* NVDA non tratta più gli spazi come parole durante la navigazione ad oggetti negli editor basati su Scintilla come Notepad++. (#8295)
* NVDA impedirà al sistema di accedere alla modalità di sospensione durante lo scorrimento del testo con un display braille. (#9175)
* In Windows10, il braille segue correttamente il focus durante la modifica delle celle in Microsoft Excel. (#9749)
* NVDA è in grado di annunciare nuovamente i suggerimenti della barra degli indirizzi di Microsoft Edge. (#7554)
* NVDA non smette più di parlare quando il focus si trova in un'intestazione di un controllo html in Internet Explorer. (#8898)
* In Microsoft Edge basato su EdgeHTML, quando la finestra viene ingrandita, NVDA non riprodurrà più il suono dei suggerimenti di ricerca. (#9110, #10002)
* Le caselle combinate ARIA 1.1 sono ora supportate in Mozilla Firefox e Google Chrome. (#9616)
* NVDA non segnalerà più il contenuto di colonne nascoste per gli elementi dell'elenco nei controlli SysListView32. (#8268)
* Nella finestra impostazioni di NVDA il livello di log non viene più visualizzato come "info" in modalità protetta. (#10209)
* Nel menu Start per Windows 10 Anniversary Update e versioni successive, NVDA annuncerà i dettagli dei risultati della ricerca. (#10232)
* In modalità navigazione, se lo spostamento del cursore o l'utilizzo della navigazione rapida provoca la modifica del documento, NVDA non leggerà più contenuti inappropriati in alcuni casi. (#8831, #10343)
* Sono stati corretti alcuni nomi degli elenchi puntati in Microsoft Word. (#10399)
* In Windows 10 aggiornamento maggio 2019 e versioni successive, NVDA annuncerà di nuovo la prima emoji selezionata o l'elemento degli appunti quando si aprono rispettivamente la cronologia del pannello emoji e degli appunti. (#9204)
* In Poedit, è di nuovo possibile visualizzare alcune traduzioni per le lingue con scrittura da destra a sinistra. (#9931)
* Nell'app Impostazioni nell'aggiornamento di Windows 10 aprile 2018 e versioni successive, NVDA non annuncerà più le informazioni sulla barra di avanzamento per i misuratori di volume presenti nella pagina Sistema / Suono. (#10284)
* Eventuali espressioni regolari non corrette presenti nei dizionari di NVDA non causano più l'arresto delle funzionalità di sintesi vocale. (#10334)
* Durante la lettura degli elementi negli elenchi puntati in Microsoft Word con UIA abilitato,  non viene più annunciato l'elemento successivo invece di quello attuale. (#9613)
* Sono stati risolti alcuni rari problemi di traduzione braille ed errori con liblouis. (#9982)
* Le applicazioni Java avviate prima di NVDA sono ora accessibili senza la necessità di riavviare l'app Java. (#10296)
* In Mozilla Firefox, quando l'elemento focalizzato viene contrassegnato come corrente (aria-current), non viene più annunciato diverse volte. (#8960)
* NVDA ora considera alcuni caratteri unicode composti come la "e-acuta" come un carattere singolo mentre ci si sposta nel testo. (#10550)
* Introdotto il supporto per Spring Tool Suite Versione 4. (#10001)
* Risolto un problema di doppia pronuncia di un elemento con le etichette e le relazioni aria. (#10552)
* Su Windows 10 versione 1607 e successive, i caratteri digitati tramite la tastiera Braille vengono pronunciati correttamente in più situazioni. (#10569)
* Quando si modifica il dispositivo audio di uscita, i toni emessi da NVDA ora verranno riprodotti attraverso il dispositivo appena selezionato. (#2167)
* In Mozilla Firefox, è stata migliorata sensibilmente la velocità di spostamento del focus in modalità navigazione. (#10584)

### Cambiamenti per sviluppatori, in inglese

* Updated Python to 3.7. (#7105)
* Updated pySerial to version 3.4. (#8815)
* Updated wxPython to 4.0.3 to support Python 3.5 and later. (#9630)
* Updated six to version 1.12.0. (#9630)
* Updated py2exe to version 0.9.3.2 (in development, commit b372a8e from albertosottile/py2exe#13). (#9856)
* Updated UIAutomationCore.dll comtypes module to version 10.0.18362. (#9829)
* The tab-completion in the Python console only suggests attributes starting with an underscore if the underscore is first typed. (#9918)
* Flake8 linting tool has been integrated with SCons reflecting code requirements for Pull Requests. (#5918)
* As NVDA no longer depends on pyWin32, modules such as win32api and win32con are no longer available to add-ons. (#9639)
 * win32api calls can be replaced with direct calls to win32 dll functions via ctypes.
 * win32con constants should be defined in your files.
* The "async" argument in nvwave.playWaveFile has been renamed to "asynchronous". (#8607)
* speakText and speakCharacter methods on synthDriver objects are no longer supported.
 * This functionality is handled by SynthDriver.speak.
* SynthSetting classes in synthDriverHandler have been removed. Now use driverHandler.DriverSetting classes instead.
* SynthDriver classes should no longer expose index via the lastIndex property.
 * Instead, they should notify the synthDriverHandler.synthIndexReached action with the index, once all previous audio has finished playing before that index.
* SynthDriver classes must now notify the synthDriverHandler.synthDoneSpeaking action, once all audio from a SynthDriver.speak call has completed playing.
* SynthDriver classes must support the speech.PitchCommand in their speak method, as changes in pitch for speak spelling now depends on this functionality.
* The speech function getSpeechTextForProperties has been renamed to getPropertiesSpeech. (#10098)
* The braille function getBrailleTextForProperties has been renamed to getPropertiesBraille. (#10469)
* Several speech functions have been changed to return speech sequences. (#10098)
 * getControlFieldSpeech
 * getFormatFieldSpeech
 * getSpeechTextForProperties now called getPropertiesSpeech
 * getIndentationSpeech
 * getTableInfoSpeech
* Added a textUtils module to simplify string differences between Python 3 strings and Windows unicode strings. (#9545)
 * See the module documentation and textInfos.offsets module for example implementations.
* Deprecated functionality now removed. (#9548)
 * AppModules removed:
  * Windows XP sound recorder.
  * Klango Player, which is abandoned software.
 * configobj.validate wrapper removed.
  * New code should use from configobj import validate instead of import validate
 * textInfos.Point and textInfos.Rect replaced by locationHelper.Point and locationHelper.RectLTRB respectively.
 * braille.BrailleHandler._get_tether and braille.BrailleHandler.set_tether have been removed.
 * config.getConfigDirs has been removed.
 * config.ConfigManager.getConfigValidationParameter has been replaced by getConfigValidation
 * inputCore.InputGesture.logIdentifier property has been removed.
   * Use _get_identifiers in inputCore.InputGesture instead.
 * synthDriverHandler.SynthDriver.speakText/speakCharacter have been removed.
 * Removed several synthDriverHandler.SynthSetting classes.
   * Previously kept for backwards compatibility (#8214), now considered obsolete.
   * Drivers that used the SynthSetting classes should be updated to use the DriverSetting classes.
 * Some legacy code has been removed, particularly:
  * Support for the Outlook pre 2003 message list.
  * An overlay class for the classic start menu, only found in Windows Vista and earlier.
  * Dropped support for Skype 7, as it is definitely not working any more.
* Added a framework to create vision enhancement providers; modules that can change screen contents, optionally based on input from NVDA about object locations. (#9064)
 * Add-ons can bundle their own providers in a visionEnhancementProviders folder.
 * See the vision and visionEnhancementProviders modules for the implementation of the framework and examples, respectively.
 * Vision enhancement providers are enabled and configured via the 'vision' category in NVDA's settings dialog.
* Abstract class properties are now supported on objects that inherit from baseObject.AutoPropertyObject (e.g. NVDAObjects and TextInfos). (#10102)
* Introduced displayModel.UNIT_DISPLAYCHUNK as a textInfos unit constant specific to DisplayModelTextInfo. (#10165)
 * This new constant allows walking over the text in a DisplayModelTextInfo in a way that more closely resembles how the text chunks are saved in the underlying model.
* displayModel.getCaretRect now returns an instance of locationHelper.RectLTRB. (#10233)
* The UNIT_CONTROLFIELD and UNIT_FORMATFIELD constants have been moved from virtualBuffers.VirtualBufferTextInfo to the textInfos package. (#10396)
* For every entry in the NVDA log, information about the originating thread is now included. (#10259)
* UIA TextInfo objects can now be moved/expanded by the page, story and formatField text units. (#10396)
* External modules (appModules and globalPlugins) are now less likely to be able to break the creation of NVDAObjects.
 * Exceptions caused by the "chooseNVDAObjectOverlayClasses" and "event_NVDAObject_init" methods are now properly caught and logged.
* The aria.htmlNodeNameToAriaLandmarkRoles dictionary has been renamed to aria.htmlNodeNameToAriaRoles. It now also contains roles that aren't landmarks.
* scriptHandler.isCurrentScript has been removed due to lack of use. There is no replacement. (#8677)

## 2019.2.1

Si tratta di una versione minore che corregge diversi arresti anomali presenti nella versione 2019.2. Le correzioni includono:

* Sono stati risolti numerosi problemi con Gmail individuati sia in Firefox che in Chrome durante l'interazione con determinati menu popup, ad esempio durante la creazione di filtri o la modifica di alcune impostazioni di Gmail. (#10175, #9402, #8924)
* In Windows 7, NVDA non causa più l'arresto anomalo di Esplora risorse quando si utilizza il mouse nel menu Start. (#9435)
* Esplora risorse su Windows 7 non si blocca più quando si accede ai campi di modifica dei metadati. (#5337)
* NVDA non si blocca più quando si interagisce con le immagini con un URI base64 in Mozilla Firefox o Google Chrome. (#10227)

## 2019.2

Le novità più interessanti di questa versione riguardano il rilevamento automatico dei Display Braille Freedom Scientific, una nuova impostazione sperimentale situata nella scheda avanzate che impedisce al focus di spostarsi assieme al cursore virtuale durante la navigazione (il che può migliorare moltissimo la velocità di gestione delle pagine web), una nuova funzione chiamata "aumento velocità" nelle voci Windows OneCore in Windows10 che consente al sintetizzatore di leggere molto più rapidamente, e molti altri bug risolti.

### Novità

* Il supporto per Miranda NG funziona di nuovo con le ultime versioni del client. (#9053)
* Una nuova opzione permette di disattivare la modalità navigazione per impostazioni predefinite,  smarcando la casella di controllo "abilita modalità navigazione al caricamento delle pagine", situata in impostazioni > modalità navigazione. (#8716)
 * Si noti che quando questa opzione è disabilitata, è sempre possibile abilitare la modalità di navigazione manualmente premendo NVDA + spazio.
* È ora possibile filtrare i simboli nella finestra di dialogo pronuncia punteggiatura/simboli, in modo analogo a come funziona il filtro nell'elenco elementi e nella finestra gesti di immissione. (#5761)
* è stato aggiunto un comando per modificare al volo la quantità di testo letta al passaggio del mouse. Non è stato associato ad alcun tasto rapido, quindi nel caso serva, bisogna provvedere nella finestra tasti e gesti di immissione. (#9056)
* La finestra di impostazioni Sintetizzatore OneCore ha una nuova opzione chiamata aumento velocità, se attivata la sintesi vocale parlerà in maniera molto più rapida. (#7498)
* La funzione di aumento velocità delle sintesi OneCore è controllabile anche dalle impostazioni al volo del sintetizzatore. Attualmente questo parametro è modificabile solo con le sintesi Espeak-NG e Windows Onecore. (#8934)
* I profili di configurazione possono essere attivati manualmente servendosi di gesti o tasti rapidi. (#4209)
 * Naturalmente bisogna configurare un gesto appropriato nella finestra gesti e tasti di immissione.
* In Eclipse, è stato introdotto il supporto all'autocompletamento nell'editor del codice. (#5667)
 * In aggiunta, Le informazioni Javadoc possono essere lette dall'editor quando presenti utilizzando NVDA+d.
* Aggiunta una nuova impostazione sperimentale situata nella scheda avanzate che impedisce al focus di spostarsi assieme al cursore virtuale durante la navigazione; la funzione si chiama "sposta automaticamente il focus durante la navigazione", (#2039). Benché la disattivazione di questa casella di controllo potrebbe non essere indicata per tutti i siti web, quando funziona va a risolvere parecchi problemi, tra i quali:
 * Effetto elastico: NVDA talvolta ritorna alla posizione precedente invece di eseguire il comando di navigazione indicato.
 * Difficoltà di passare tra le caselle editazione in alcuni siti con il focus che si attiva di colpo quando non richiesto.
 * Lentezza in risposta dei tasti di navigazione.
* Per quei driver di Display Braille che lo supportano, la finestra delle impostazioni braille può contenere opzioni aggiuntive relative solo a quel driver, per esempio la resistenza del punto. (#7452)
* Il rilevamento automatico Display Braille ora riconosce anche le barre della Freedom Scientific. (#7727)
* Aggiunto un comando per visualizzare la sostituzione di un simbolo alla posizione del cursore di controllo. (#9286)
* Aggiunta un'opzione sperimentale nella finestra impostazioni avanzate che consente di provare il nuovo supporto alla console di Windows servendosi delle UI Automation API. (#9614)
* Nella console Python, è possibile incollare più righe nel campo di immissione. (#9776)

### Cambiamenti

* Il volume della voce aumenta o diminuisce di 5 anziché di 10 quando lo si modifica con le impostazioni al volo del sintetizzatore. (#6754)
* è stato reso più chiaro il testo che appare nel gestore componenti aggiuntivi quando NVDA viene eseguito con l'opzione --disable-addons. (#9473)
* Il tasto di scelta rapida per il campo filtro nell'elenco elementi in modalità navigazione è stato modificato in alt + y. (#8728)
* Quando un display braille rilevato automaticamente viene collegato tramite Bluetooth, NVDA continuerà a cercare display USB supportati dallo stesso driver e passerà a una connessione USB se disponibile. (#8853)
* Dopo che si è selezionato del testo, NVDA dirà:: "selezionato". (#9028)
* In Microsoft Visual Studio Code, la modalità di navigazione è disattivata da impostazioni predefinite. (#9828)
* Aggiornate le annotazioni emoji di Unicode Common Locale Repository Data alla versione 35.0. (#9445)
* Aggiornato liblouis braille translator alla versione 3.9.0. (#9439)
* Aggiornata eSpeak-NG alla commit 67324cc.

### Bug Corretti

* NVDA non crasha più se una cartella di componenti aggiuntivi è vuota. (#7686)
* Non vengono più riportati in braille o tramite percentuale con la voce i segni di marcatura da sinistra a destra e da destra a sinistra quando si accede alla finestra delle proprietà. (#8361)
* Quando si utilizza un tasto rapido per andare direttamente ad un form in modalità navigazione, viene annunciato l'intero campo del form anziché soltanto la prima riga. (#9388)
* NVDA non rimarrà più in silenzio dopo essere uscito dall'app Posta di Windows 10. (#9341)
* NVDA non avrà più problemi ad avviarsi quando  le impostazioni regionali dell'utente sono impostate in una lingua che NVDA non conosce, ad esempio Inglese (Paesi Bassi). (#8726)
* Quando la modalità di navigazione è abilitata in Microsoft Excel e si passa a un browser in modalità focus o viceversa, lo stato della modalità di navigazione viene ora segnalato in modo appropriato. (#8846)
* NVDA ora annuncia correttamente la riga sulla quale si trova il mouse in Notepad++ e altri editor basati su Scintilla. (#5450)
* In Google Docs (e altri editor web), non viene più mostrata in Braille prima del cursore la dicitura "lst end" nel mezzo di un elenco elementi. (#9477)
* In Windows10 Aggiornamento Maggio 2019, NVDA non annuncerà più notifiche di continuo inerenti il cambio del volume quando effettuato con tasti fisici, con l'app Esplora File in primo piano. (#9466)
* è stato reso molto più rapido il caricamento della finestra di dialogo pronuncia/punteggiatura simboli anche nel caso in cui si utilizzi un dizionario simboli contenente più di 1000 valori. (#8790)
* Nei controlli Scintilla come in Notepad++, NVDA leggerà la riga esatta anche quando la funzione a capo automatico è attiva. (#9424)
* In Microsoft Excel, viene annunciata la posizione della cella quando modificata dai tasti Shift+Enter o Shift+NumPadEnter. (#9499)
* In Visual Studio 2017 e successivi, nella finestra esplora oggetti, viene annunciato correttamente l'oggetto selezionato nell'albero degli oggetti o nell'albero dei membri con le categorie. (#9311)
* Due componenti aggiuntivi con lo stesso nome ma con differenze nelle maiuscole non saranno più trattati come addon diversi. (#9334)
* Per le voci Windows OneCore, la velocità impostata in NVDA non è più influenzata dalla velocità impostata nelle impostazioni vocali di Windows 10. (#7498)
* Ora il log può essere aperto con NVDA +F1 anche quando non vi sono informazioni per gli sviluppatori relative al navigatore ad oggetti. (#8613)
* è di nuovo possibile servirsi dei comandi di navigazione tabella di NVDA in Google Docs, Firefox e Chrome. (#9494)
* I tasti bumper funzionano di nuovo correttamente per i Display Braille di Freedom Scientific. (#8849)
* Quando si legge il primo carattere di un documento in Notepad++ 7.7 X64, NVDA non si blocca più per un tempo massimo di dieci secondi. (#9609)
* Il software HtCom usato dai display Braille HandiTech funziona anche con NVDA. (#9691)
* In Mozilla Firefox, non vengono più annunciati gli aggiornamenti di una live region se quest'ultima risulta in background. (#1318)
* La finestra di dialogo Trova di NVDA ora è in grado di funzionare anche se la finestra "informazioni su" risulta aperta in background. (#8566)

### Changes for Developers

* You can now set the "disableBrowseModeByDefault" property on app modules to leave browse mode off by default. (#8846)
* The extended window style of a window is now exposed using the `extendedWindowStyle` property on Window objects and their derivatives. (#9136)
* Updated comtypes package to 1.1.7. (#9440, #8522)
* When using the report module info command, the order of information has changed to present the module first. (#7338)
* Added an example to demonstrate using nvdaControllerClient.dll from C#. (#9600)
* Added a new isWin10 function to the winVersion module which returns whether or not this copy of NVDA is running on (at least) the supplied release version of Windows 10 (such as 1903). (#9761)
* The NVDA Python console now  contains more useful modules in its namespace (such as appModules, globalPlugins, config and textInfos). (#9789)
* The result of the last executed command in the NVDA Python console is now accessible from the _ (line) variable. (#9782)
 * Note that this shadows the gettext translation function also called "_". To access the translation function: del _

## 2019.1.1

Questa versione minore risolve i seguenti bug:

* NVDA non causa più il crash di Excel 2007 o rifiuta di segnalare se una cella contiene una formula. (#9431)
* Google Chrome non si blocca più quando interagisce con determinate caselle di riepilogo. (#9364)
* È stato risolto un problema che impediva di copiare la configurazione di un utente nel profilo di configurazione del sistema. (#9448)
* In Microsoft Excel, NVDA utilizza nuovamente il messaggio localizzato quando segnala la posizione delle celle unite. (#9471)

## 2019.1

Le novità principali di questa versione si possono riassumere in un grosso miglioramento delle prestazioni quando si accede a Microsoft Word ed Excel, miglioramenti di stabilità e sicurezza come il supporto per i componenti aggiuntivi con informazioni sulla compatibilità della versione e molte altre correzioni di bug.

Si tenga presente che a partire da questa versione di NVDA, non verranno più caricati automaticamente gli appmodules personalizzati, i globalplugins, i driver per barre braille e sintesi vocali che si trovano nella propria cartella delle impostazioni utente.
Sarà necessario costruire un componente aggiuntivo per continuare ad usare questi elementi. Per coloro che svilupperanno componenti aggiuntivi, il codice di test può essere inserito in una nuova cartella dello sviluppatore chiamata scratchpad situata nella directory di configurazione utente di NVDA, purché l'opzione scratchpad dello sviluppatore sia attiva nel nuovo pannello delle impostazioni avanzate di NVDA.
Queste modifiche sono necessarie per migliorare la compatibilità del codice personalizzato, in modo che NVDA non vada in crash o abbia problemi quando questo codice diventa incompatibile con le nuove versioni.
Si prega di fare riferimento all'elenco delle modifiche più in basso per maggiori dettagli sull'argomento e su come sono stati migliorati i componenti aggiuntivi.

### Novità

* Nuove Tabelle Braille: Afrikaans, Arabo 8 punti computer braille, Arabo grado 2, Spagnolo grado 2. (#4435, #9186)
* Aggiunta un'opzione alle impostazioni del mouse di NVDA per far sì che lo screen reader gestisca situazioni in cui il mouse è controllato da un'altra applicazione. (#8452)
 * Ciò consentirà a NVDA di tracciare il mouse quando il sistema viene controllato da remoto utilizzando TeamViewer o un altro software di controllo.
* Aggiunto un nuovo parametro a riga di comando `--enable-start-on-logon` per consentire alle installazioni silenziose di NVDA di scegliere se lo screen reader debba essere eseguito al login di Windows o meno. Specificare true in caso affermativo o false per non far partire NVDA al login. Se l'argomento --enable-start-on-logon non viene specificato, NVDA verrà eseguito al login, a meno che non sia stato configurato in maniera diversa in un'installazione precedente. (#8574)
* È possibile disattivare le funzionalità di log di NVDA impostando il livello di log su "disabilitato" dal pannello delle impostazioni generali. (#8516)
* Viene ora annunciata la presenza di formule nei fogli di lavoro di LibreOffice ed Apache OpenOffice. (#860)
* In Mozilla Firefox e Google Chrome, in modalità navigazione ora viene annunciato l'elemento selezionato nelle caselle ad elenco e nelle visualizzazioni ad albero.
 * Funziona su Firefox 66 e versioni successive.
 * Non funziona invece per alcune caselle elenco (controlli di selezione html) in Chrome.
* Supporto embrionale per app come Mozilla Firefox su computer con processori ARM64 (ad esempio Qualcomm Snapdragon). (#9216)
* è stata aggiunta una nuova categoria nella finestra impostazioni di NVDA chiamata "avanzate", che tra le altre cose comprende un'opzione per provare il nuovo supporto di NVDA per Microsoft Word tramite Microsoft UI Automation API. (#9200)
* Aggiunto il supporto per la visualizzazione grafica in Gestione disco di Windows. (#1486)
* Aggiunto supporto per Handy Tech Connect Braille e Basic Braille 84. (#9249)

### Cambiamenti

* Aggiornato liblouis braille translator alla versione 3.8.0. (#9013)
* Gli autori dei componenti aggiuntivi ora possono specificare una versione minima richiesta di NVDA per i loro addon. NVDA si rifiuterà di installare o caricare un componente aggiuntivo la cui versione minima richiesta sia superiore alla versione attuale di NVDA. (#6275)
* Gli autori dei componenti aggiuntivi ora possono specificare l'ultima versione di NVDA su cui è stato testato il componente aggiuntivo. Se un componente aggiuntivo è stato testato solo con una versione di NVDA inferiore a quella corrente, NVDA si rifiuterà di installare o caricare l'add-on. (#6275)
* Questa versione di NVDA consentirà ancora di utilizzare componenti aggiuntivi che non contengono al proprio interno informazioni sulla versione minima e la versione testata di NVDA, ma è necessario porre molta attenzione per il futuro perché ad esempio la versione 2019.2 dello screen reader renderà obbligatori questi parametri, rendendo impossibile utilizzare addon molto datati.
* Il comando sposta il mouse alla posizione del navigatore ad oggetti è ora disponibile in Microsoft Word e per i controlli UIA, in particolare Microsoft Edge. (#7916, #8371)
* è stato migliorato l'annuncio del testo situato alla posizione del mouse in Microsoft Edge e altre applicazioni UIA.  (#8370)
* Quando NVDA viene avviato con il parametro a riga di comando `--portable-path`, il percorso fornito viene inserito automaticamente quando si tenta di creare una copia portable utilizzando il menu NVDA. (# 8623)
* Aggiornato il percorso alla tabella Braille Norvegese in modo da adeguarsi agli standard in vigore dall'anno 2015. (#9170)
* Quando ci si sposta per paragrafi (control freccia su o freccia giù) oppure per celle in una tabella (control-alt-frecce direzionali), non verranno più annunciati gli errori di ortografia, anche nel caso in cui NVDA sia configurato allo scopo. Questo perché paragrafi e tabelle possono risultare abbastanza grandi e rilevare errori di ortografia in alcune applicazioni può essere molto costoso in termini di risorse. (#9217)
* non verranno più caricati automaticamente gli appmodules personalizzati, i globalplugins, i driver per barre braille e sintesi vocali che si trovano nella propria cartella delle impostazioni utente. Il codice dovrà invece essere incluso in un componente aggiuntivo con informazioni corrette sulla versione, assicurandosi nel contempo che eventuale codice non compatibile non possa venir eseguito con la versione corrente di NVDA.
 * Per i programmatori che devono testare il codice mentre è in fase di sviluppo, è necessario abilitare una nuova opzione chiamata directory scratchpad per sviluppatori, situata nella categoria Avanzate delle impostazioni di NVDA; inserire quindi il codice nella cartella "scratchpad" presente nella directory di configurazione dell'utente.

### Bug Corretti

* Quando si utilizzano le sintesi vocali OneCore di Windows10 a partire dall'aggiornamento aprile2018 e successivi, non ci saranno più grossi blocchi di silenzio in mezzo ad un discorso. (#8985)
* Quando ci si sposta carattere per carattere nei controlli di testo semplice (tipo il blocconote) o in modalità navigazione, verranno letti correttamente i caratteri emoji a 32 bit composti da due punti di codice UTF-16 (ad esempio ðŸ¤¦) (#8782)
* Migliorata la finestra di dialogo che si presenta dopo aver modificato la lingua dell'interfaccia di NVDA. Il testo e le etichette dei pulsanti appaiono ora più concisi e meno confusi. (#6416)
* Se un sintetizzatore vocale di terze parti provoca un errore durante il caricamento, NVDA utilizzerà le voci OneCore di Windows10 piuttosto di Espeak. (#9025)
* Rimossa la voce "Finestra di benvenuto" dal menu di NVDA quando ci si trova in modalità Desktop sicuro. (#8520)
* In modalità navigazione se ci si serve del tasto tab o dei tasti rapidi, vengono riportate in modo più coerente le legende su pannelli a schede. (#709)
* NVDA è ora in grado di annunciare i cambiamenti di selezione per alcuni controlli sull'orario  in app quali Orologio e Sveglia in Windows10. (#5231)
* Nel Centro operativo di Windows 10, NVDA annuncerà i messaggi di stato quando si attivano azioni rapide come la luminosità e l'assistente messa a fuoco. (#8954)
* Nel centro operativo di Windows10 a partire dall'aggiornamento ottobre2018 e successivi, NVDA riconoscerà il controllo rapido della luminosità come un pulsante piuttosto che un interruttore. (#8845)
* NVDA seguirà di nuovo il cursore correttamente e leggerà i caratteri cancellati in Microsoft Excel nei campi editazione Vai ae Trova. (#9042)
* Risolto un crash piuttosto raro in modalità navigazione in Firefox. (#9152)
* NVDA non commetterà più errori nell'annunciare il focus per alcuni controlli nella barra multifunzione in Office 2016, quando compressa.
* NVDA non commetterà più errori nell'annunciare un contatto suggerito durante l'inserimento degli indirizzi nella finestra nuovo messaggio di Outlook 2016. (#8502)
* Gli ultimi tasti cursor routing dei display braille Eurobraille a 80 celle ora funzionano correttamente, piuttosto che portare il cursore in una posizione random o a inizio riga. (#9160)
* Corretta la navigazione per tabelle nelle visualizzazioni delle discussioni in Mozilla Thunderbird. (#8396)
* In Mozilla Firefox e Google Chrome, sistemato un problema che riguardava l'attivazione della modalità focus per alcune caselle ad elenco e visualizzazioni ad albero (laddove queste ultime non potevano essere focalizzate ma gli elementi al proprio interno sì). (#3573, #9157)
* Viene correttamente attivata la modalità navigazione durante la lettura dei messaggi in Outlook 2016/365 nel caso si utilizzi il nuovo supporto sperimentale UI Automation per i documenti Word. (#9152)
* Limitate notevolmente le occasioni in cui, a causa di crash di NVDA, per ritornare ad utilizzare il computer correttamente era necessario chiudere la propria sessione di Windows. (#6291)
* In Windows 10 aggiornamento ottobre 2018 e successivo, quando si apre la cronologia degli appunti cloud con gli appunti vuoti, NVDA annuncerà lo stato degli appunti. (#9103)
* In Windows 10 aggiornamento ottobre 2018 e successivo, durante la ricerca di emoji nel pannello emoji, NVDA annuncerà i risultati di ricerca migliori. (9105)
* NVDA non si blocca più nella finestra principale di  Oracle VirtualBox 5.2 e versioni successive. (#9202)
* potrebbe essere notevolmente migliorata in alcuni documenti la reattività in Microsoft Word durante la navigazione per riga, paragrafo o tabella. Si consiglia,  per prestazioni ottimali, di impostare Microsoft Word in visualizzazione Bozza dopo aver aperto un documento. (#9217)
* In Mozilla Firefox e Google Chrome, non verranno più annunciati avvisi con contenuto vuoto. (#5657)
* Migliorate sensibilmente le prestazioni in Microsoft Excel durante la navigazione tra le celle, specialmente in presenza di commenti o elenchi a discesa. (#7348)
* Non è più necessario disattivare l'opzione "modifica celle in tempo reale" per poter accedere alla finestra di modifica celle con il tasto f2, in Office 2016/365. (#8146).
* Risolto un problema molto raro in Firefox che avveniva quando ci si spostava per punti di riferimento e nel sistema era installato il componente aggiuntivo Enhanced Aria. (#8980)

### Cambiamenti per sviluppatori (in inglese)

* NVDA can now  be built with all editions of Microsoft Visual Studio 2017 (not just the Community edition). (#8939)
* You can now include log output from liblouis into the NVDA log by setting the louis boolean flag in the debugLogging section of the NVDA configuration. (#4554)
* Add-on authors are now able to provide NVDA version compatibility information in add-on manifests. (#6275, #9055)
 * minimumNVDAVersion: The minimum required version of NVDA for an add-on to work properly.
 * lastTestedNVDAVersion: The last version of NVDA an add-on has been tested with.
* OffsetsTextInfo objects can now implement the _getBoundingRectFromOffset method to allow retrieval of bounding rectangles per characters instead of points. (#8572)
* Added a boundingRect property to TextInfo objects to retrieve the bounding rectangle of a range of text. (#8371)
* Properties and methods within classes can now be marked as abstract in NVDA. These classes will raise an error if instantiated. (#8294, #8652, #8658)
* NVDA can log the time since input when text is spoken, which helps in measuring perceived responsiveness. This can be enabled by setting the timeSinceInput setting to True in the debugLog section of the NVDA configuration. (#9167)

## 2018.4.1

Questa versione risolve un problema che si riscontrava all'avvio di NVDA nel caso in cui l'interfaccia fosse impostata in lingua aragonese. (#9089)

## 2018.4

Le migliorie più significative di questa versione si concentrano in un notevole aumento delle prestazioni per le versioni più recenti di Mozilla Firefox, lettura delle emoji con qualsiasi sintetizzatore, lettura dello stato "risposto-inoltrato" in outlook, annuncio della distanza del cursore fino al bordo della pagina in un documento Word, e molte altre correzioni di bug..

### Novità

* Nuove tabelle braille: Cinese (Cina, Mandarino) grado 1 e grado 2. (#5553)
* In Microsoft Outlook quando ci si trova nell'elenco messaggi, ne viene annunciato lo stato (risposto - inoltrato). (#6911)
* NVDA è ora in grado di  leggere le descrizioni delle emoji e di altri caratteri che fanno parte dell'Unicode Common Locale Data Repository. (#6523)
* In Microsoft Word, è possibile conoscere la distanza del cursore dai bordi sinistro e superiore della pagina tramite la combinazione di tasti NVDA+Canc del tastierino numerico. (#1939)
* In Google Fogli con la modalità braille attivata, NVDA non dirà più la parola "selezionata" ogni qualvolta ci si sposta tra le celle con le frecce. (#8879)
* Aggiunto il supporto ai programmi Foxit Reader e Foxit Phantom PDF. (#8944)
* Aggiunto il supporto alle utility per i database DBeaver. (#8905)

### Cambiamenti

* L'opzione "Leggi i fumetti d'aiuto" nella finestra di dialogo presentazione oggetti è stata rinominata in "annuncia notifiche"" per includere lo stile delle notifiche toast di Windows8 e Windows10. (#5789)
* Nelle impostazioni tastiera di NVDA, le caselle di controllo per abilitare o disabilitare il tasto funzione NVDA vengono visualizzate in un elenco piuttosto che come elementi singoli separati.
* NVDA non leggerà più informazioni ridondanti durante l'esplorazione dell'orologio nella system tray in alcune versioni di Windows. (#4364)
* Aggiornato liblouis braille translator alla versione 3.7.0. (#8697)
* Aggiornata Espeak-NG alla commit 919f3240cbb.

### Bug corretti

* In Outlook 2016/365, viene annunciato se un messaggio è contrassegnato o meno e la categoria di appartenenza. (#8603)
* Se NVDA viene impostato in una lingua quale il Kirgyz, il mongolo o il macedone, non verrà più visualizzato un messaggio all'avvio che avverte l'utente che la lingua selezionata non è supportata dal sistema operativo. (#8064)
* Lo spostamento del mouse alla posizione del navigatore ad oggetti risulterà molto più accurato, specie quando si porta il mouse al cursore in Google Chrome, Mozilla Firefox e Acrobat Reader DC. (#6460)
* Migliorata notevolmente l'interazione con le caselle combinate in Firefox, Chrome e Internet Explorer. (#8664)
* Quando lo screen reader viene eseguito in versioni giapponesi di Windows Xp o Vista, NVDA visualizzerà correttamente i messaggi dei requisiti di sistema. (#8771)
* Grosso miglioramento delle prestazioni durante la navigazione in documenti web molto complessi con cambiamenti di tipo dinamico in Mozilla Firefox. (#8678)
* Non vengono più visualizzati gli attributi dei caratteri in Braille se essi sono stati disabilitati nelle impostazioni di formattazione documento. (#7615)
* NVDA non avrà più problemi di gestione del focus in Esplora File ed altre applicazioni che si servono della UI Automation quando un'altra app risulta occupata. (#7345)
* Nei menu Aria delle pagine web, il tasto Esc chiuderà il menu, invece che disattivare incondizionatamente la modalità focus.. (#3215)
* Nella nuova interfaccia web di Gmail, mentre si utilizza la navigazione veloce tra i messaggi e li si legge, non viene più letto ogni volta tutto il corpo del messaggio quando ci si sposta tra i vari controlli. (#8887)
* Dopo aver aggiornato NVDA, i browser Chrome e Firefox non dovrebbero più crashare, ed inoltre la modalità navigazione dovrebbe aggiornarsi correttamente anche con eventuali cambiamenti effettuati ad un documento. (#7641)
* NVDA non annuncerà più la parola "cliccabile" tutte le volte quando ci si trova in modalità navigazione in una riga con diversi controlli cliccabili. (#7430)
* Risolti i problemi con le combinazioni e i gesti su display braille baum Vario 40. (#8894)
* In Google Slides con Mozilla Firefox, NVDA non dirà più "selezionato" ogni qualvolta ci si sposta in un controllo. (#8964)

### Cambiamenti per sviluppatori (in inglese)

* gui.nvdaControls now contains two classes to create accessible lists with check boxes. (#7325)
 * CustomCheckListBox is an accessible subclass of wx.CheckListBox.
 * AutoWidthColumnCheckListCtrl adds accessible check boxes to an AutoWidthColumnListCtrl, which itself is based on wx.ListCtrl.
* If you need to make a wx widget accessible which isn't already, it is possible to do so by using an instance of gui.accPropServer.IAccPropServer_impl. (#7491)
 * See the implementation of gui.nvdaControls.ListCtrlAccPropServer for more info.
* Updated configobj to 5.1.0dev commit 5b5de48a. (#4470)
* The config.post_configProfileSwitch action now takes the optional prevConf keyword argument, allowing handlers to take action based on differences between configuration before and after the profile switch. (#8758)

## 2018.3.2

Si tratta di una versione minore per aggirare un arresto anomalo di Google Chrome durante la navigazione nei tweet su [www.twitter.com](http://www.twitter.com). (#8777)

## 2018.3.1

Questa è una versione minore per correggere un bug critico in NVDA che causava il crash delle versioni a 32 bit di Mozilla Firefox. (#8759)

## 2018.3

Le principali migliorie che caratterizzano questa versione di N VDA si possono riassumere nel riconoscimento automatico di molti display braille, nel supporto a nuove funzioni di Windows10 come l'immissione nel pannello Emoji, e sulla risoluzione di bug e problematiche varie.

### Novità

* NVDA è in grado di leggere gli errori grammaticali se esposti dalle pagine web in maniera appropriata nei browser Mozilla Firefox e Google Chrome. (#8280)
* In Google Chrome, vengono supportati gli attributi "inserito" e "cancellato" che fanno riferimento ad un testo. (#8558)
* Aggiunto il supporto alle rotelle di scorrimento per il BrailleNote QT e Apex BT quando Braillenote viene usato come display Braille in NVDA. (#5992, #5993)
* Aggiunti gli script per annunciare il tempo trascorso e quello totale durante la riproduzione di una traccia in Foobar2000. (#6596)
* Il simbolo del tasto Command dei Mac (⌘) ora viene interpretato correttamente durante la lettura con qualsiasi sintesi vocale. (#8366)
* Vengono supportati in tutti i browser web i ruoli personalizzati tramite l'attributo aria-roledescription (#8448)
* Nuove tabelle braille: Ceco 8 punti, Curdo centrale, Esperanto, Ungherese, Svedese computer Braille 8 punti. (#8226, #8437)
* è stato aggiunto il supporto al rilevamento automatico dei display braille in background. (#1271)
 * Sono attualmente supportati i display ALVA, Baum/HumanWare/APH/Orbit, Eurobraille, Handy Tech, Hims, SuperBraille e HumanWare BrailleNote e Brailliant BI/B.
 * è possibile abilitare questa funzione selezionando la voce "automatico" dall'elenco di Display Braille nella finestra di dialogo Selezione Display Braille di NVDA..
 * Si veda la documentazione per ulteriori dettagli.
* Aggiunto il supporto a nuovi metodi di immissione introdotti nelle versioni più recenti di Windows 10. Nel dettaglio: pannello emoji (Fall Creators Update), dettatura (Fall Creators Update), suggerimenti di immissione con tastiere hardware (aggiornamento di Aprile 2018), e appunti basati sul cloud (Aggiornamento di ottobre 2018). (#7273)
* Viene supportato in Mozilla Firefox 63 il contenuto marcato come "blocco tra virgolette" tramite l'attributo ARIA (role blockquote). (#8577)

### Cambiamenti

* L'elenco delle lingue disponibili nelle impostazioni generali di NVDA ora è ordinato alfabeticamente piuttosto che seguendo il codice ISO 639. (#7284)
* Aggiunti tasti di scelta rapida e gesti predefiniti per le combinazioni Alt+Shift+Tab e Windows+Tab con tutti i display braille di Freedom Scientific supportati. (#7387)
* Per i display Braille ALVA BC680 e protocol converter, ora è possibile assegnare funzioni differenti per gli smart pad di destra e sinistra, nonché per i tasti etouch e quelli vicini al pollice. (#8230)
* Per i Display Braille ALVA BC6, la combinazione di tasti sp2+sp3 fornirà ora la data e l'ora corrente, mentre sp1+sp2 simulerà il tasto Windows. (#8230)
* Al primo avvio di NVDA, verrà chiesto all'utente il consenso per inviare dati statistici alla NvAccess durante il controllo aggiornamenti dello screen reader. (#8217)
* Durante il controllo aggiornamenti, nel caso in cui l'utente abbia acconsentito a mandare informazioni statistiche di utilizzo alla NvAccess, NVDA invierà il nome del driver di sintesi vocale e del display braille in uso, per aiutare nel processo di prioritizzazione nel miglioramento degli stessi. (#8217)
* Aggiornate le tabelle di traduzione braille liblouis alla versione 3.6.0. (#8365)
* Aggiornato il percorso alla tabella braille corretta russo 8 punti. (#8446)
* Aggiornata eSpeak-ng alla versione 1.49.3dev commit 910f4c2. (#8561)

### Bug Corretti

* Le etichette accessibili relative ai controlli in Google Chrome vengono annunciate in maniera più leggibile in modalità navigazione. (#4773)
* Sono supportate le notifiche in Zoom. Per esempio, si verrà avvisati in caso di attivazione/disattivazione microfono, o di messaggi in arrivo. (#7754)
* Quando ci si trova in modalità navigazione, il passaggio tra le varie modalità di presentazione braille ora funziona correttamente, consentendo al display braille di seguire il cursore di navigazione. (#7741)
* Risolti errori di inizializzazione del display braille ALVA BC680. (#8106)
* Da impostazioni predefinite, la pressione dei tasti sp2+sp3 nei display braille ALVA BC6 permetterà di attivare funzioni interne, piuttosto che essere vista come una pressione di tasti simulati. (#8230)
* La pressione del tasto sp2 nei display ALVA BC6 per simulare il tasto ALT funziona ora correttamente. (#8360)
* NVDA non annuncerà più cambi ridondanti di layout tastiera. #8419)
* Il tracciamento del mouse risulta molto più accurato in Blocconote e in altri controlli di testo modificabile, nel caso in cui ci si trovi in un documento di più di 65535 caratteri. (#8397)
* NVDA è in grado di riconoscere un maggior numero di finestre di dialogo in Windows10 e altre applicazioni moderne. (#8405)
* In Windows 10 aggiornamento Ottobre 2018 e Server 2019 e successivi, NVDA non ha più problemi nel seguire il focus di sistema nel caso in cui un'applicazione si blocca o inonda il sistema con eventi. (#7345, #8535)
* Gli utenti Vengono ora informati nel caso in cui tentino di leggere o copiare una barra di stato vuota. (#7789)
* Risolto un problema che si verificava nei controlli con stato "non selezionato"; essi non venivano annunciati dalla sintesi vocale se il controllo risultava prima parzialmente selezionato. (#6946)
* Nell'elenco lingue della finestra impostazioni generali di NVDA, il nome della lingua Burmese viene visualizzato correttamente in Windows 7. (#8544)
* In Microsoft Edge, NVDA annuncerà notifiche quali la disponibilità della modalità di lettura, nonché l'avanzamento del caricamento delle pagine. (#8423)
* Quando ci si trova in un elenco web, NVDA ne leggerà l'etichetta nel caso in cui il webmaster ne abbia inserita una. (#7652)
* Quando si assegnano manualmente funzioni ai tasti di un determinato display braille, quelle combinazioni saranno ora assegnate effettivamente alla barra braille desiderata; in precedenza, venivano sempre assegnate al display braille attivo. (#8108)
* è ora supportata la versione a 64 bit di Media Player Classic. (#6066)
* Moltissime migliorie inerenti il supporto braille a Microsoft Word con UI Automation abilitata:
 * Similmente a quanto accade per altri tipi di campo multilinea, quando ci si posiziona all'inizio del documento in braille, NVDA farà in modo che il primo carattere del documento coincida con la prima cella del proprio display braille. (#8406)
 * Quando viene evidenziato un documento word (ad esempio alt-tab), sono state Ridotte sensibilmente le informazioni ridondanti di presentazione focus, sia con sintesi vocale che con display braille.. (#8407)
 * Quando ci si trova in un elenco di Microsoft Word, i cursor routing ora funzionano correttamente. (#7971)
 * Vengono ora gestiti correttamente gli elenchi numerati e puntati appena inseriti, sia con sintesi vocale che con barra braille. (#7970)
* In Windows 10 1803 e successivi, è ora possibile installare componenti aggiuntivi se la caratteristica "utilizza Unicode UTF-8 per le lingue internazionali" è abilitata. (#8599)
* NVDA non renderà più iTunes 12.9 e versioni successive completamente inutilizzabili per interagire. (#8744)\n

### Cambiamenti per sviluppatori, solo inglese

* Added scriptHandler.script, which can function as a decorator for scripts on scriptable objects. (#6266)
* A system test framework has been introduced for NVDA. (#708)
* Some changes have been made to the hwPortUtils module: (#1271)
 * listUsbDevices now yields dictionaries with device information including hardwareID and devicePath.
 * Dictionaries yielded by listComPorts now also contain a usbID entry for COM ports with USB VID/PID information in their hardware ID.
* Updated wxPython to 4.0.3. (#7077)
* As NVDA now only supports Windows 7 SP1 and later, the key "minWindowsVersion" used to check if UIA should be enabled for a particular release of Windows has been removed. (#8422)
* You can now register to be notified about configuration saves/reset actions via new config.pre_configSave, config.post_configSave, config.pre_configReset, and config.post_configReset actions. (#7598)
 * config.pre_configSave is used to be notified when NVDA's configuration is about to be saved, and config.post_configSave is called after configuration has been saved.
 * config.pre_configReset and config.post_configReset includes a factory defaults flag to specify if settings are reloaded from disk (false) or reset to defaults (true).
* config.configProfileSwitch has been renamed to config.post_configProfileSwitch to reflect the fact that this action is called after profile switch takes place. (#7598)
* UI Automation interfaces updated to Windows 10 October 2018 Update and Server 2019 (IUIAutomation6 / IUIAutomationElement9). (#8473)

## 2018.2.1

Questa versione include aggiornamenti di traduzione dovuti alla rimozione dell'ultimo minuto di una funzionalità che causava problemi.

## 2018.2

Le caratteristiche principali di questa versione comprendono il supporto per le tabelle in Kindle per Pc,  la gestione dei Display Braille della HumanWare Braillenote Touch e BI14, grossi miglioramenti sulle voci Onecore e Sapi5, un sensibile miglioramento al supporto di Microsoft Outlook e molto altro.

### novità

* Vengono gestiti sia tramite sintesi vocale che braille gli intervalli di righe e colonne nelle celle delle tabelle di Microsoft Excel. (#2642)
* I comandi di navigazione tabella di NVDA ora funzionano anche in Google Docs (con la modalità braille attiva). (#7946)
* Aggiunta la possibilità di leggere ed esplorare le tabelle in Kindle per Pc. (#7977)
* Supporto per i display braille HumanWare BrailleNote touch e Brailliant BI 14 sia tramite USB che bluetooth. (#6524)
* In Windows 10 Fall Creators Update e versioni successive, NVDA è ora in grado di leggere le notifiche provenienti da app quali calcolatrice o Windows Store. (#7984)
* Nuove tabelle di traduzione braille: Lituano 8 punti, Ucraino, Mongolo grado 2. (#7839)
* Aggiunto uno script che permette di ottenere le informazioni di formattazione del testo in una cella braille specifica. (#7106)
* Durante l'aggiornamento di NVDA, è ora possibile posticipare il processo di installazione ad un secondo momento. (#4263)
* Nuove lingue: Mongolo, Tedesco svizzero.
* è ora possibile attivare o disattivare i tasti control, shift, Alt, Windows e NVDA dalla propria tastiera braille ed usarli in concomitanza con altre lettere (ad esempio ctrl-s scritto direttamente dalla barra braille). (#7306)
 * Questi nuovi interruttori possono essere assegnati usando i comandi che si trovano nella sezione pressione tasti simulata nella finestra tasti e gesti di immissione.
* Ripristinato il supporto ai Display Braille di Handy Tech Braillino e Modular (con firmware vecchio). (#8016)
* NVDA si occuperà di sincronizzare automaticamente l'ora e la data per alcuni display braille Handytech (quali Active Braille e Active Star), nel caso in cui queste informazioni siano fuori sincro di almeno 5 secondi. (#6911)
* è possibile assegnare un nuovo gesto/combinazione di tasti per disattivare tutti i profili di configurazione in base agli eventi. (#4935)

### Cambiamenti

* La colonna "stato" nel gestore componenti aggiuntivi è stata modificata in modo da indicare se l'addon è attivato o disattivato, invece che "in esecuzione" o "sospeso". (#7929)
* Aggiornate le librerie liblouis braille translator alla versione 3.5.0. (#7839)
* La tabella braille lituano è stata rinominata in lituano 6 punti per evitare confusione con la nuova tabella a 8 punti. (#7839)
* Sono state rimosse le tabelle braille Francese (canadese) grado1 e grado2. Al loro posto, verranno usate le tabelle Francese unificato 6 punti braille computer e grado 2. (#7839)
* La seconda fila di cursor routing nei display braille Alva BC6, EuroBraille e Papenmeier ora serve per mostrare informazioni di formattazione del testo in corrispondenza della cella sotto il cursor routing premuto.  (#7106)
* Si passerà automaticamente dalle tabelle di immissione con braille contratto a quelle standard in presenza di campi di testo non editabili  (ad esempio in controlli dove non esiste il cursore o in modalità navigazione). (#7306)
* NVDA ora risulterà molto meno prolisso in presenza di un appuntamento del calendario di Microsoft Outlook che dura per l'intera giornata. (#7949)
* Tutte le preferenze di NVDA sono state raggruppate in un'unica finestra impostazioni, raggiungibile dal menu NVDA -> Preferenze -> Impostazioni, in modo da non disperdere le opzioni in tante finestre diverse. (#577)
* Quando si utilizza Windows10, ora la sintesi vocale predefinita sarà Microsoft OneCore piuttosto che Espeak. (#8176)

### Bug corretti

* NVDA non commette più errori nel leggere i controlli su cui viene posizionato il focus nella finestra di login account Microsoft richiamata da impostazioni, dopo aver inserito l'indirizzo email. (#7997)
* NVDA non ha più problemi nel leggere una pagina in Microsoft Edge anche quando si torna ad una pagina precedente. (#7997)
* NVDA non annuncerà più l'ultima cifra del pin quando si effettua l'accesso dalla schermata di sblocco di Windows10. (#7908)
* Non vengono più annunciate due volte le etichette di pulsanti radio o caselle di controllo in Chrome e Firefox in modalità navigazione quando si preme il tasto tab. (#7960)
* Un elemento aria-current con un valore falso verrà annunciato come "falso" invece di "vero". (#7892).
* Il sintetizzatore OneCore di Windows si caricherà ugualmente anche nel caso in cui la voce utilizzata è stata disinstallata. (#7553)
* Il cambio di voce nel pacchetto voci OneCore ora avviene molto più velocemente. (#7999)
* Sistemate alcune occorrenze non valide nelle tabelle braille, compresi i segni di maiuscola nella tabella 8 punti braille contratto Danese. (#7526, #7693)
* NVDA ora è in grado di riconoscere un numero maggiore di elenchi puntati in Microsoft Word. (#6778)
* L'attivazione dello script per ottenere le informazioni di formattazione non crea più alcun problema, né modificando erroneamente la posizione del cursore di controllo, né leggendo informazioni errate nel caso in cui lo script venga attivato più volte velocemente. (#7869)
* Non risulta più possibile servirsi del braille contratto in fase di immissione quando non è supportato. (#7306)
* Risolti i problemi di stabilità della connessione con i display braille Handy Tech  Easy Braille e BrailleWave. (#8016)
* In Windows8 e versioni successive, NVDA non annuncerà più la parola "sconosciuto" quando si cerca di aprire il menu rapido con la combinazione di tasti Windows+x. (#8137)
* I gesti e le combinazioni di tasti associati ai pulsanti dei display braille Hims ora funzionano correttamente come descritti nella guida utente. (#8096)
* NVDA ora tenterà di correggere errori di registrazione Com di sistema che rendevano inaccessibili programmi quali Internet Explorer e Firefox; la conseguenza era che NVDA pronunciava sempre e solo la parola "sconosciuto" in ogni occasione. (#2807)
* Sistemato un bug nel Task Manager che non consentiva agli utenti di NVDA di accedere al contenuto di specifici dettagli sui processi. (#8147)
* Le nuove voci Sapi5 di Microsoft non hanno più rallentamenti alla fine di una frase, rendendo la navigazione molto più agevole. (#8174)
* NVDA non leggerà più (marcatore da sinistra a destra o da destra a sinistra) quando si accede all'orologio delle ultime versioni di Windows10, sia per quel che concerne sintesi vocale che braille. (#5729)
* Sistemati i problemi nel rilevamento dei tasti di scorrimento per i display braille Smart Beetle di Hims. (#6086)
* In alcuni controlli di testo, in particolare nelle applicazioni Delphi, le informazioni fornite durante la navigazione e la modifica del testo risultano molto più accurate. (#636, #8102)
* In Windows 10 rs5, NVDA non annuncerà più informazioni ridondanti quando si passa da un programma all'altro (#8258)

### Cambiamenti per sviluppatori (in inglese)

* The developer info for UIA objects now contains a list of the UIA patterns available. (#5712)
* App modules can now force certain windows to always use UIA by implementing the isGoodUIAWindow method. (#7961)
* The hidden boolean flag "outputPass1Only" in the braille section of the configuration has again been removed. Liblouis no longer supports pass 1 only output. (#7839)

## 2018.1.1

Questa è una versione speciale di NVDA che risolve un bug nel driver del sintetizzatore vocale Onecore Windows, che lo faceva parlare con un tono e una velocità più elevati in Windows 10 Redstone 4 (1803). (#8082)

## 2018.1

Le caratteristiche principali di questa versione riguardano la gestione dei grafici in Microsoft Word e Powerpoint, il supporto a display braille quali Eurobraille e Optelec protocol converter, migliorato il supporto ai modelli Hims e Optelec, prestazioni decisamente più performanti in Firefox58 e versioni successive, e molto altro ancora.

### Novità

* Ora è possibile interagire con i grafici in Microsoft Word e Microsoft PowerPoint, similmente a come accade già per i grafici in Microsoft Excel. (#7046)
 * In Microsoft Word: Quando ci si trova in modalità navigazione, posizionare il cursore su un grafico e premere invio per interagire con esso.
 * In Microsoft PowerPoint mentre si modifica una diapositiva: premere tab fino a trovare un grafico, dopodiché premere invio o barra spazio per interagire con esso.
 * Per terminare l'interazione con un grafico, premere escape.
* Nuova lingua: Kyrgyz.
* Aggiunto il supporto per VitalSource Bookshelf. (#7155)
* Aggiunto il supporto per il convertitore di protocollo Optelec, un dispositivo che permette di utilizzare Braille Voyager e Alva Satellite tramite il protocollo di comunnicazione ALVA BC6. (#6731)
* Ora è possibile utilizzare l'immissione braille anche con il display ALVA 640 Comfort. (#7733)
 * La funzionalità di immissione braille di NVDA può essere usata sia con questi modelli sia con altri display BC6 con  firmware 3.0.0 e superiore.
* Supporto preliminare per Google Fogli con la modalità braille abilitata. (#7935)
* Supporto per le barre Eurobraille Esys, Esytime e Iris. (#7488)

### Cambiamenti

* Ora esiste un unico driver per i Display Braille della Hims (Braille Sense/Braille EDGE/Smart Beetle e Sync Braille). Il nuovo driver sarà automaticamente attivato per tutti, compresi utenti Sync Braille che in precedenza ne usavano uno di diverso. (#7459)
 * Alcuni tasti, soprattutto quelli di scorrimento, sono stati riassegnati per adeguarsi alle convenzioni standard di HIMS. Si veda il manuale utente per ulteriori dettagli.
* Durante la digitazione con una tastiera touch, ora l'impostazione predefinita è quella di dover effettuare un doppio tap per ciascuna lettera, così come per gli altri controlli. (#7309)
 * Per fare in modo che le lettere vengano inserite non appena si solleva il dito, è necessario modificare la relativa opzione presente nelle impostazioni di interazione al tocco nel menu preferenze.
* Non è più necessario selezionare manualmente se il braille debba seguire il focus o il cursore di controllo, in quanto ora viene gestito tutto automaticamente. (#2385)
 * Si noti che questa funzione automatica si attiva solo quando vengono usati comandi di navigazione ad oggetti o di gestione del cursore di controllo, non è quindi sufficiente premere un tasto di scorrimento sul display braille.

### Bug Corretti

* I messaggi di NVDA che consentono un'esplorazione con le frecce, per esempio quando si preme due volte NVDA-f per ottenere informazioni sulla formattazione, non presentano più problemi quando lo screen reader è installato in un percorso contenente caratteri non ascii. (#7474)
* Il focus viene ripristinato correttamente quando si passa da una qualsiasi applicazione a Spotify. (#7689)
* In Windows 10 Fall Creaters Update, NVDA non presenta più errori di aggiornamento quando è abilitata la funzione di accesso protetto alle cartelle in Windows Defender Security Center. (#7696)
* La funzione di rilevamento dei tasti di scorrimento nel display braille Hims Smart Beetle ora funziona correttamente. (#6086)
* Migliorate leggermente le prestazioni in presenza di grandi quantità di contenuti da gestire in Mozilla Firefox 58 e successivi. (#7719)
* In Microsoft Outlook, sistemati gli errori in lettura di email contenenti tabelle. (#6827)
* Migliorata la gestione del braille nella finestra gesti e tasti di immissione. (#7783)
* In Mozilla Firefox, la modalità navigazione opera correttamente anche nei pop-up creati da estensioni quali LastPass e bitwarden. (#7809)
* NVDA non va più in crash e non si blocca ad ogni cambiamento di focus nel caso in cui Firefox o Chrome smettono di funzionare. (#7818)
* Nei client Twitter come Chicken Nugget, NVDA non ignorerà più gli ultimi 20 caratteri su 280 durante la lettura dei tweet. (#7828)
* NVDA ora utilizza la lingua corretta  nella lettura dei simboli quando il testo è selezionato. (#7687)
* Nelle versioni più recenti di Office 365, è di nuovo possibile esplorare i grafici Excel utilizzando i tasti freccia. (#7046)
* Sistemato un problema di sincronizzazione braille/sintesi vocale nell'annunciare informazioni di controllo. (#7076)
* In app quali Windows 10 Mail, NVDA non avrà più problemi nel leggere i caratteri eliminati quando si preme backspace. (#7456)
* Tutti i tasti del display braillesense Polaris prodotto da Hims funzionano correttamente. (#7865)
* NVDA non fallisce più nell'avvio su Windows 7 lamentandosi di una dll api-ms interna, quando una particolare versione dei ridistribuibili di Visual Studio 2017 è stata installata da un'altra applicazione. (#7975)

### Cambiamenti per sviluppatori (in inglese)

* Added a hidden boolean flag to the braille section in the configuration: "outputPass1Only". (#7301, #7693, #7702)
 * This flag defaults to true. If false, liblouis multi pass rules will be used for braille output.
* A new dictionary (braille.RENAMED_DRIVERS) has been added to allow for smooth transition for users using drivers that have been superseded by others. (#7459)
* Updated comtypes package to 1.1.3. (#7831)
* Implemented a generic system in braille.BrailleDisplayDriver to deal with displays which send confirmation/acknowledgement packets. See the handyTech braille display driver as an example. (#7590, #7721)
* A new "isAppX" variable in the config module can be used to detect if NVDA is running as a Windows Desktop Bridge Store app. (#7851)
* For document implementations such as NVDAObjects or browseMode that have a textInfo, there is now a new documentBase.documentWithTableNavigation class that can be inherited from to gain standard table navigation scripts. Please refer to this class to see which helper methods must be provided by your implementation for table navigation to work. (#7849)
* The scons batch file now better handles when  Python 3 is also installed, making use of the launcher to specifically launch python 2.7 32 bit. (#7541)
* hwIo.Hid now takes an additional parameter exclusive, which defaults to True. If set to False, other applications are allowed to communicate with a device while it is connected to NVDA. (#7859)

## 2017.4

Le principali migliorie di questa versione riguardano un supporto molto più completo alle pagine web contenenti app o finestre di dialogo al proprio interno, una gestione migliore delle etichette dei campi raggruppati in modalità navigazione, supporto a nuove tecnologie presenti in Windows10 come Windows Defender Application Guard e Windows 10 con processori ARM64, lettura automatica del cambio di orientamento dello schermo e anche dello stato di carica della batteria.
Si prega di fare attenzione al fatto che questa versione di NVDA non supporta più Windows XP o Windows Vista. Il requisito minimo per NVDA è ora windows 7 con Service Pack 1.

### Novità

* In modalità navigazione, è ora possibile saltare all'inizio o alla fine del contenuto presente nei punti di riferimento, servendosi dei comandi (virgola/shift+virgola). (#5482)
* In Firefox, Chrome e Internet Explorer, la navigazione veloce verso campi editazione e form  ora comprende anche i contenuti di tipo rich text (ad esempio contentEditable). (#5534)
* Nei browser web, l'elenco elementi può mostrare anche campi dei moduli e pulsanti. (#588)
* Supporto iniziale per Windows 10 nei sistemi ARM64. (#7508)
* Supporto di base alla lettura e alla navigazione interattiva nei contenuti di tipo matematico per i libri Kindle con matematica accessibile. (#7536)
* Aggiunto supporto per Azardi e-book reader. (#5848)
* Vengono ora annunciate le informazioni sulla versione durante l'aggiornamento dei componenti aggiuntivi. (#5324)
* Aggiunto un nuovo parametro a riga di comando per creare una copia portable di NVDA. (#6329)
* Supporto per Microsoft Edge quando eseguito all'interno di Windows Defender Application Guard in Windows 10 Fall Creators Update. (#7600)
* Se si sta eseguendo NVDA in un portatile o in un tablet, lo screen reader adesso notifica l'utente in caso di cambio di orientamento dello schermo, e anche nel caso in cui viene connesso o disconnesso l'adattatore di corrente. (#4574, #4612)
* Nuova lingua: Macedone.
* Nuove tabelle di traduzione braille: Croato grado 1, Vietnamita grado 1. (#7518, #7565)
* Aggiunto il supporto al display braille Actilino prodotto da Handy Tech. (#7590)
* Viene ora supportata l'immissione tramite tastiera braille nei Display Handy Tech. (#7590)

### Cambiamenti

* NVDA abbandona il supporto a Windows Xp e Windows vista, prendendo come sistema operativo minimo Windows 7 Service Pack 1, o Windows Server 2008 R2 Service Pack 1. (#7546)
* Le finestre di dialogo web nei browser Firefox e Chrome adesso attiveranno in automatico la modalità navigazione, a meno che non ci si trovi all'interno di un'applicazione web. (#4493)
* In modalità navigazione, sono state rimosse o abbreviate alcune frasi che NVDA annunciava quando si usciva da un elenco o da una tabella per rendere la navigazione più rapida. (#2591)
* In modalità navigazione per Firefox e Chrome, viene annunciato il nome dei raggruppamenti per i campi dei moduli quando si entra o si esce da essi con il tasto tab o con la navigazione veloce. (#3321)
* In modalità navigazione, il comando per spostarsi tra gli oggetti incorporati (o e shift+o) ora comprende anche elementi audio e video, ed elementi con ruoli Aria applicazione e finestre di dialogo. (#7239)
* Espeak-ng è stata aggiornata alla versione 1.49.2. #7583)
* Una tripla pressione del comando "leggi barra di stato" farà in modo che il contenuto verrà copiato negli appunti. (#1785)
* Durante l'assegnamento di gesti personalizzati ai tasti dei Display Baum, è ora possibile limitarli al modello specifico in uso, (ad esempio VarioUltra o Pronto). (#7517)
* Nell'elenco elementi, è stato cambiato il tasto rapido per raggiungere la funzione "filtra per campi", ora assegnato a alt+e. (#7569)
* è stato aggiunto un comando assegnabile dall'utente per quel che concerne la modalità navigazione per attivare o disattivare la rilevazione delle tabelle di layout. Questo comando si trova nella categoria navigazione della finestra gesti di immissione. (#7634)
* Aggiornato liblouis braille translator alla versione 3.3.0. (#7565)
* è stato modificato il tasto caldo per raggiungere il pulsante radio inerente le espressioni regolari nella finestra di dialogo dei dizionari, ora è alt+e. (#6782)
* I file dei dizionari inerenti la voce ora hanno il loro numero di versione e sono stati spostati nella cartella 'speechDicts/voiceDicts.v1'. (#7592)
* Quando NVDA viene eseguito direttamente dal file di installazione, non verranno più salvati i file dizionari o di configurazione utente. (#7688)
* I display braille Braillino, Bookworm e Modular (con firmware vecchio) non sono più supportati nativamente da NVDA. Risulta comunque ancora possibile utilizzarli scaricando il driver universale USB di Handytech ed installando anche il relativo componente aggiuntivo. (#7590)

### Bug Corretti

* Vengono ora indicati in braille i link nelle applicazioni quali Microsoft Word. (#6780)
* NVDA non diventa più molto lento in presenza di diverse schede aperte in Firefox o Chrome. (#3138)
* Risolto un problema con i tasti cursor routing con il display braille Lilli che facevano spostare il cursore un carattere avanti rispetto alla posizione corretta. (#7469)
* In Internet Explorer e altri documenti MSHTML, viene supportato l'attributo HTML5 "required", che sta ad indicare nei moduli un campo obbligatorio. (#7321)
* Ora i display braille si aggiornano correttamente durante la digitazione di caratteri arabi in un documento allineato a sinistra in Wordpad. (#511)
* in Mozilla Firefox le etichette accessibili relative ai controlli vengono riportate in maniera più leggibile in modalità navigazione. (#4773)
* in windows 10 Creators Update, NVDA è in grado nuovamente di accedere a Firefox dopo un riavvio dello screen reader. (#7269)
* Quando si riavvia NVDA con Mozilla Firefox focalizzato,, la modalità navigazione sarà nuovamente disponibile, anche se bisognerà premere alt tab una o due volte per ripristinarne il funzionamento. (#5758)
* è ora possibile accedere ai contenuti matematici su Google Chrome anche in un sistema dove non è installato Mozilla Firefox. (#7308)
* Dopo aver installato NVDA, il sistema e le relative applicazioni dovrebbero essere più stabili anche alla prima esecuzione dello screen reader, quando il pc non è ancora stato riavviato. (#7563)
* Quando si utilizza un comando di riconoscimento testi come l'OCR (NVDA+r), NVDA segnalerà un errore nel caso in cui il navigatore ad oggetti  dovesse trovarsi in un'area invisibile. In precedenza non accadeva nulla. (#7567)
* Sistemato un problema con lo scorrimento indietro per i display braille Freedom Scientific che dispongono di una bumper bar a sinistra. (#7713)

### Cambiamenti per sviluppatori (in inglese)

* "scons tests" now checks that translatable strings have translator comments. You can also run this alone with "scons checkPot". (#7492)
* There is now a new extensionPoints module which provides a generic framework to enable code extensibility at specific points in the code. This allows interested parties to register to be notified when some action occurs (extensionPoints.Action), to modify a specific kind of data (extensionPoints.Filter) or to participate in deciding whether something will be done (extensionPoints.Decider). (#3393)
* You can now register to be notified about configuration profile switches via the config.configProfileSwitched Action. (#3393)
* Braille display gestures that emulate system keyboard key modifiers (such as control and alt) can now be combined with other emulated system keyboard keys without explicit definition. (#6213)
 * For example, if you have a key on your display bound to the alt key and another display key to downArrow, combining these keys will result in the emulation of alt+downArrow.
* The braille.BrailleDisplayGesture class now has an extra model property. If provided, pressing a key will generate an additional, model specific gesture identifier. This allows a user to bind gestures limited to a specific braille display model.
 * See the baum driver as an example for this new functionality.
* NVDA is now compiled with Visual Studio 2017 and the Windows 10 SDK. (#7568)

## 2017.3

Le migliorie di questa versione possono essere riassunte nel supporto alle voci incluse in Windows10 chiamate CoreVoices, al supporto per l'OCR incluso in Windows10 per il riconoscimento di testo in documenti e app non accessibili, all'immissione di testo con braille contratto (usato in Stati Uniti e Regno Unito), e moltissimi miglioramenti sulla navigazione web e sul braille.

### Novità

* è stata introdotta una nuova impostazione braille che permette o meno di visualizzare i messaggi di stato o di errore per un tempo indefinito. (#6669)
* Nell'elenco messaggi di Microsoft Outlook, NVDA è in grado di annunciare se un messaggio sia contrassegnato o meno. (#6374)
* In Microsoft Powerpoint, viene letto il tipo di forma esatta durante la modifica di una diapositiva (come triangolo, cerchio, video, freccia) invece che semplicemente la parola "figura". (#7111)
* I contenuti di tipo matematico forniti da MathMl vengono gestiti anche in Google Chrome. (#7184)
* NVDA può utilizzare in maniera diretta le voci presenti in Windows10 chiamate CoreVoices, conosciute anche come Microsoft Mobile voices. Per utilizzarle andare nella finestra sintetizzatore e selezionare Windows CoreVoices. (#6159)
* I file della configurazione di NVDA possono essere ora salvati anche nella cartella utente dati applicazione (application data). Per attivare questa impostazione è necessario modificare il registro. Si veda la sezione "parametri di sistema" del manuale utente per ulteriori informazioni. (#6812)
* Nei browser web, ora NVDA legge i valori dei segnaposti per i campi (nello specifico, è supportato aria-placeholder). (#7004)
* In modalità navigazione mentre si usa Microsoft Word, è possibile passare da un errore di ortografia all'altro con i tasti rapidi di navigazione w o Shift-w. (#6942)
* Aggiunto il supporto per la selezione della data nella finestra appuntamenti di Microsoft Outlook. (#7217)
* In Mail di Windows10 viene ora letto il suggerimento selezionato dei campi to, cc, e questo vale anche per la casella di ricerca della finestra impostazioni di Windows10. (#6241)
* Viene riprodotto un suono per indicare la comparsa di suggerimenti in alcuni campi di ricerca in Windows 10 ( ad esempio schermata del menu avvio, ricerca nelle impostazioni, campi to e cc in Mail, etc). (#6241)
* NVDA adesso leggerà automaticamente le notifiche in Skype for Business, ad esempio quando qualcuno inizia una conversazione. (#7281)
* NVDA ora annuncia i messaggi in arrivo in Skype For Business, se ci si trova all'interno di una conversazione. (#7286)
* NVDA legge automaticamente le notifiche provenienti da Microsoft Edge, come quando un download ha inizio. (#7281)
* è possibile digitare il testo sia con il braille non contratto che con quello contratto, nel caso si possieda un display braille munito di tastiera perkins. La funzione è utile prevalentemente in Regno Unito e Stati Uniti. Si veda la sezione immissione del testo in braille del manuale utente per ulteriori informazioni. (#2439)
* è possibile immettere anche caratteri unicode usando una tastiera braille, selezionando come tabella in scrittura la tabella unicode nelle impostazioni braille. (#6449)
* Aggiunto il supporto al display braille SuperBraille, diffuso prevalentemente in Taiwan. (#7352)
* Nuove tabelle di traduzione braille: Danese Braille Computer 8 punti,  Lituano, Persiano braille computer 8 punti, Persiano grado 1, Sloveno braille Computer 8 punti. (#6188, #6550, #6773, #7367)
* Migliorata la tabella inglese Braille Computer 8 punti, con l'aggiunta del supporto per gli elenchi puntati, il simbolo dell'euro e e le lettere accentate. (#6836)
* NVDA può utilizzare il sistema di OCR incluso in Windows10 per riconoscere il testo presente in documenti o app non accessibili. (#7361)
 * La lingua può essere selezionata attraverso la finestra di dialogo OCR Windows 10 presente nel menu preferenze di NVDA.
 * Per riconoscere il contenuto presente all'interno del navigatore ad oggetti, premere la combinazione NVDA+r.
 * Si veda la sezione OCR di Windows10 nel manuale utente per ulteriori informazioni.
* è ora possibile stabilire quali informazioni di contesto siano mostrate in un display braille quando un oggetto riceve il focus utilizzando la nuova impostazione "presentazione delle informazioni di contesto" nella finestra di dialogo impostazioni braille. (#217)
 * Ad esempio, le nuove opzioni "riempi il display braille se il contesto cambia" e "solo quando si scorre indietro" permettono di lavorare con menu ed elenchi in maniera più efficiente, poiché gli elementi non cambieranno più di posizione nel display braille.
 * Si veda la sezione "presentazione delle informazioni di contesto" presente nel manuale utente per ulteriori informazioni ed esempi.
* In Firefox e Chrome, NVDA supporta griglie e tabelle dinamiche molto complesse come fogli di lavoro, anche quando solo parte del contenuto viene caricato o visualizzato (nello specifico, gli attributi aria-rowcount, aria-colcount, aria-rowindex e aria-colindex, introdotti in ARIA 1.1). (#7410)

### Cambiamenti

* è stato aggiunto un comando per riavviare NVDA, al momento non assegnato ad alcun tasto.  Lo si può trovare nella categoria varie della finestra gesti e tasti di immissione del menu preferenze di NVDA. (#6396)
* è possibile selezionare il layout tastiera dalla schermata di benvenuto di NVDA. (#6863)
* Sono stati abbreviati in braille un gran numero di tipi di controlli e stati. Anche i punti di riferimento dispongono di abbreviazioni. Si prega di consultare la sezione "tipi di controlli, stato e punti di riferimento" nella sezione dedicata al braille nel manuale utente di NVDA. (#7188, #3975)
* Aggiornata eSpeak NG alla versione 1.49.1. (#7280)
* Le tabelle di scrittura e lettura nelle impostazioni braille sono ora ordinate alfabeticamente. (#6113)
* Aggiornato liblouis braille translator alla versione 3.2.0. (#6935)
* La tabella braille predefinita è Braille inglese unificato grado 1. (#6952)
* Da impostazioni predefinite, NVDA ora mostra nel display braille solo le parti di informazioni di contesto che sono cambiate quando un oggetto riceve il focus. (#217)
 * In precedenza, veniva visualizzato il numero più ampio di informazioni di contesto possibile, non tenendo conto del fatto che quelle informazioni erano già state mostrate all'utente.
 * è possibile ritornare alle impostazioni delle versioni precedenti modificando la nuova funzione "presentazione delle informazioni di contesto per il focus", nelle impostazioni Braille, selezionando "riempi sempre il display".
* Quando si utilizza il braille, il cursore può essere configurato in modo tale da apparire con una forma diversa per distinguere tra cursore di sistema e cursore di controllo (#7112)
* Il logo di NVDA è stato aggiornato. Il nuovo logo è un disegno stilizzato delle lettere NVDA in bianco, su di uno sfondo viola. Questo assicura una visibilità completa con qualsiasi colore di sfondo, e il viola richiama il logo di NvAccess. (#7446)

### Bug corretti

* L'etichetta degli elementi div editabili in Chrome non viene più annunciata con il suo valore, bensì con il nome dell'etichetta stessa, in modalità navigazione. (#7153)
* In modalità navigazione, la pressione del tasto fine in un documento vuoto di Microsoft Word non causa più la comparsa di un errore di runtime. (#7009)
* Viene supportata correttamente la modalità navigazione in Microsoft Edge, laddove ad un documento è stato assegnato il ruolo specifico ARIA (document. (#6998)
* In modalità navigazione, è ora possibile selezionare o deselezionare  fino alla fine della riga servendosi di Shift+fine, anche quando il cursore si trova nell'ultimo carattere della riga. (#7157)
* Se una finestra contiene una barra di avanzamento, il testo adesso viene aggiornato anche nel display braille quando vi sono dei cambiamenti. Questo significa, per esempio, che si può leggere il tempo rimanente per lo scaricamento nella finestra di aggiornamento di NVDA. (#6862)
* NVDA è in grado di annunciare i cambiamenti di selezione per alcune caselle combinate di Windows 10 come AutoPlay nelle impostazioni. (#6337)
* Non vengono più lette informazioni inutili nella finestra di creazione di meeting o appuntamenti in Microsoft Outlook. (#7216)
* Migliorata la gestione dei segnali acustici nelle barre d'avanzamento come la finestra di download aggiornamenti di NVDA. (#6759)
* In Microsoft Excel 2003 e 2007, le celle vengono di nuovo lette mentre si esplora un foglio di lavoro con le frecce. (#7243)
* In Windows 10 Creators Update e successivi, viene di nuovo attivata automaticamente la modalità navigazione per la lettura delle email in Posta di Windows10. (#7289)
* In quasi tutti i modelli di display braille muniti di tastiera perkins, il punto 7 ora elimina l'ultimo carattere inserito in braille, mentre il punto 8 simula la pressione del tasto invio. (#6054)
* In presenza di testi editabili, quando si sposta il cursore,  NVDA risulterà più preciso nel fornire le informazioni, specialmente in Chrome e nelle finestre di terminale. (#6424)
* è possibile ora leggere il contenuto del campo firma in Microsoft Outlook 2016. (#7253)
* Nelle applicazioni Java Swing, NVDA non causa più il crash dell'applicazione di tanto in tanto durante l'esplorazione delle tabelle. (#6992)
* In Windows 10 Creators Update, NVDA non annuncerà più la medesima  notifica ripetutamente. (#7128)
* Nel menu avvio di Windows 10, quando si preme invio per effettuare una ricerca e ovviamente chiudere il menu start, NVDA non ripeterà più volte il testo appena cercato. (#7370)
* La navigazione per intestazioni in Microsoft Edge è stata migliorata moltissimo e risulta più rapida. (#7343)
* In Microsoft Edge, l'esplorazione di una pagina web in modalità navigazione funziona correttamente anche in siti con tema Wordpress 2015; in precedenza molti contenuti venivano omessi. (#7143)
* In Microsoft Edge, vengono gestiti correttamente i punti di riferimento, traducendoli nel caso non siano di lingua inglese. (#7328)
* Il Braille ora segue correttamente la selezione anche quando l'evidenziazione va oltre la larghezza del display. Per esempio, se si selezionano più righe con shift+freccia giù, il braille mostrerà l'ultima riga selezionata. (#5770)
* In Firefox, NVDA non annuncerà di continuo la parola "sezione" quando viene aperta la finestra dettagli di un tweet in twitter.com (#5741)
* I comandi di navigazione tabella non sono più disponibili nelle tabelle di layout, in modalità navigazione,  a meno che non sia espressamente attivata l'opzione "leggi tabelle di layout". (#7382)
* In Firefox e Chrome, i comandi di navigazione tabelle salteranno le celle nascoste di tale tabella. (#6652, #5655)

### Cambiamenti per sviluppatori, in inglese

* Timestamps in the log now include milliseconds. (#7163)
* NVDA must now be built with Visual Studio Community 2015. Visual Studio Express is no longer supported. (#7110)
 * The Windows 10 Tools and SDK are now also required, which can be enabled when installing Visual Studio.
 * See the Installed Dependencies section of the readme for additional details.
* Support for content recognizers such as OCR and image description tools can be easily implemented using the new contentRecog package. (#7361)
* The Python json package is now included in NVDA binary builds. (#3050)

## 2017.2

Le principali novità di questa versione comprendono  il supporto completo alla funzione di attenuazione audio nell'aggiornamento Windows10 Creators; risolti molti problemi sulla selezione del testo in modalità navigazione, compresi quelli con il seleziona tutto; grossissimi miglioramenti al supporto per Microsoft Edge; inoltre potenziato il supporto web nell'individuazione dello stato di un elemento, in particolare quello corrente (utilizzando aria-current).

### Novità

* NVDA può annunciare le informazioni inerenti i bordi delle celle in Microsoft Excel tramite la combinazione NVDA+f. (#3044)
* Aggiunto il supporto per l'attributo aria-current. (#6358)
* In Microsoft Edge viene supportato il cambio automatico della lingua. (#6852)
* Supporto per la calcolatrice in Windows 10 Enterprise LTSB (ramo Long-Term Servicing) e Server. (#6914)
* Migliorato il  comando di lettura riga corrente, la tripla pressione effettuerà lo spelling servendosi della descrizione avanzata delle lettere (Ancona, Bari, Como, Domodossola, etc). (#6893)
* Nuova lingua: Burmese.
* Vengono letti correttamente i simboli unicode inerenti freccia su e giù, nonché le frazioni matematiche. (#3805)

### Cambiamenti

* Durante l'esplorazione in modalità semplice nelle applicazioni che usano la tecnologia UI Automation, vengono scartati elementi che non contengono alcun oggetto al loro interno, rendendo quindi la navigazione più fluida. (#6948, #6950)

### Bug corretti

* Gli elementi dei  menu contenuti nelle pagine web, (ad esempio caselle di controllo o pulsanti radio), possono ora essere attivati direttamente in modalità navigazione, senza passare per la modalità focus. (#6735)
* La pressione del tasto esc ora chiude la finestra di conferma cancellazione di un profilo. (#6851)
* Risolti alcuni crash che avvenivano durante l'uso di Mozilla Firefox o altre app Gecko con la funzione di multiprocesso attivata. (#6885)
* Risulta molto più accurata la lettura del colore dello sfondo quando si esplora con il cursore di controllo, anche in condizioni dove il testo viene visualizzato su uno sfondo trasparente. (#6467)
* Migliorato il supporto per l'attributo aria-describedby in Internet Explorer 11, compreso supporto a iframe e ID multipli. (#5784)
* Nell'aggiornamento Windows Creators, la caratteristica di attenuazione audio di NVDA funziona normalmente come nelle precedenti versioni di Windows. (#6933)
* NVDA non avrà più difficoltà nell'esplorare o annunciare controlli (uia) dove non è stato associato alcun tasto rapido. (#6779)
* Non saranno più aggiunti due spazi vuoti nelle informazioni su un tasto caldo che fa riferimento ad un controllo (uia). (#6790)
* Risolti i problemi che si verificavano in maniera intermittente nella gestione di alcune combinazioni di tasti sui display braille  Hims (ad esempio spazio+punto 4). (#3157)
* Risolto un problema che si verificava durante la connessione alla porta seriale di un display braille in sistemi con lingue diverse dall'inglese. (#6845)
* Migliorata la gestione dei file di configurazione di NVDA per evitarne la corruzione o il danneggiamento nel momento in cui il sistema si spegne o si riavvia. Ora i file di configurazione vengono prima scritti in un file temporaneo prima del salvataggio. (#3165)
* Quando si esegue il comando leggi riga corrente con la doppia pressione per ottenere lo spelling della riga stessa, viene utilizzata la lingua appropriata durante lo spelling. (#6726)
* La navigazione riga per riga in Microsoft Edge risulta tre volte più veloce a partire dall'aggiornamento Creators di Windows. (#6994)
* NVDA non annuncerà più la frase "Web Runtime grouping" quando il focus si posiziona in un documento Microsoft Edge, nell'aggiornamento Creators di Windows. (#6948)
* Sono supportate tutte le versioni esistenti di SecureCRT. (#6302)
* Adobe Acrobat Reader non andrà più in crash in presenza di alcuni documenti pdf (nello specifico quelli contenenti attributi actualtext vuoti). (#7021, #7034)
* In modalità navigazione in Microsoft Edge, non vengono più saltate le tabelle interattive (griglie Aria) quando si raggiungono le tabelle con i tasti t e Shift-t. (#6977)
* In modalità navigazione, la pressione della combinazione shift-inizio, dopo che si è effettuata una selezione in avanti, deselezionerà tutto il testo a partire dall'inizio della riga, come dovrebbe essere. (#5746)
* In modalità navigazione, la pressione della combinazione ctrl-a per selezionare tutto si comporta in maniera corretta, anche quando il cursore non si trova all'inizio del testo. (#6909)
* Sistemati altri problemi abbastanza rari sulla selezione in modalità navigazione. (#7131)

### Cambiamenti per sviluppatori, in inglese

* Commandline arguments are now processed with Python's argparser module, rather than optparser. This allows certain options such as -r and -q to be handled exclusively. (#6865)
* core.callLater now queues the callback to NVDA's main queue after the given delay, rather than waking the core and executing it directly. This stops possible freezes due to the  core accidentally going to sleep after processing a callback, in the midle of  a modal call such as the desplaying of a message box. (#6797)
* The InputGesture.identifiers property has been changed so that it is no longer normalized. (#6945)
 * Subclasses no longer need to normalize identifiers before returning them from this property.
 * If you want normalized identifiers, there is now an InputGesture.normalizedIdentifiers property which normalizes the identifiers returned by the identifiers property .
* The InputGesture.logIdentifier property is now deprecated. Callers should use InputGesture.identifiers[0] instead. (#6945)
* Deprecated code removed:
 * `speech.REASON_*` constants, `controlTypes.REASON_*` should be used instead. (#6846)
 * `i18nName` for synth settings, `displayName` and `displayNameWithAccelerator` should be used instead. (#6846, #5185)
 * `config.validateConfig`. (#6846, #667)
 * `config.save`: si dovrebbe utilizzare `config.conf.save`. (#6846)
* The list of completions in the autocomplete context menu of the PythonConsole no longer shows  any objec path leading up to the final symbol being completed. (#7023)
* There is now a unit testing framework for NVDA. (#7026)
 * Unit tests and infrastructure are located in the tests/unit directory. See the docstring in the tests\unit\init.py file for details.
 * You can run tests using "scons tests". See the "Running Tests" section of readme.md for details.
 * If you are submitting a pull request for NVDA, you should first run the tests and ensure they pass.

## 2017.1

Le principali caratteristiche di questa versione comprendono  la segnalazione delle sezioni e colonne di testo in Microsoft Word; il Supporto per la lettura, la navigazione e le funzioni di annotazione nei libri in Kindle per PC; grossi miglioramenti al supporto per Microsoft Edge.

### Novità

* In Microsoft Word possono ora essere annunciati il numero di sezione o il tipo di interruzione sezione. Ciò può essere attivato tramite l'opzione "leggi i numeri di pagina" presente nella finestra impostazioni formattazione documento di NVDA. (#5946)
* In Microsoft Word è possibile farsi annunciare le colonne di testo. Ciò può essere attivato tramite l'opzione "leggi i numeri di pagina" presente nella finestra impostazioni formattazione documento di NVDA. (#6555)
* La funzione di cambio lingua automatica è ora supportata anche in Wordpad. (#6555)
* Il comando Trova di NVDA (ctrl-NVDA-f) è ora funzionante anche nella modalità navigazione in Microsoft Edge. (#6580)
* Le funzioni di navigazione veloce con i tasti b e Shift+b ora sono operative anche in Microsoft Edge. (#6577)
* Quando si copia un foglio in Microsoft Excel, vengono ricordate le intestazioni di riga e colonna. (#6628)
* Supporto alla lettura e alla navigazione dei libri in Kindle per Pc versione 1.19, il che comprende l'accesso ai link, note a piè di pagina, i grafici, il testo evidenziato e le note dell'utente. Per ulteriori informazioni, Si prega di fare riferimento alla sezione Kindle per Pc del manuale utente di NVDA. (#6247, #6638)
* Supporto all'esplorazione delle tabelle in modalità navigazione in Microsoft Edge. (#6594)
* In Microsoft Excel, il comando "annuncia posizione del cursore di controllo" (desktop: NVDA+Canc del tastierino numerico, laptop: NVDA+Canc) ora leggerà il nome del foglio di lavoro e la posizione della cella. (#6613)
* Aggiunta un'opzione alla finestra di dialogo di uscita di NVDA per riavviare lo screen reader con il debugging nel log. (#6689)

### Cambiamenti

* La velocità minima di lampeggio del cursore braille ora è impostata a 200ms. I profili con valori di configurazione più bassi di questo saranno automaticamente modificati a 200. (#6470)
* è stata aggiunta una casella di controllo alla finestra di dialogo delle impostazioni braille per permettere di abilitare/disabilitare il cursore lampeggiante. In precedenza veniva usato il valore 0 per implementare questa funzione.  (#6470)
* Aggiornata  eSpeak NG (commit e095f008, 10 gennaio 2017). (#6717)
* A causa di alcune modifiche nell'aggiornamento Windows 10 Creators, non è più disponibile la funzione "attenua sempre" nelle impostazioni di attenuazione audio di NVDA. Risulta ancora presente nelle versioni precedenti di Windows 10. (#6684)
* A causa di alcune modifiche nell'aggiornamento Windows 10 Creators, la funzione "Attenua quando vengono riprodotti suoni assieme alla voce", presente nelle impostazioni di attenuazione audio, non può più assicurare una diminuzione dell'audio corretta nel momento in cui la sintesi vocale inizia a parlare, e il conseguente aumento del suono in maniera graduale quando la voce ha terminato; in sostanza questa funzione esiste ancora, ma può provocare sbalzi inaspettati di volume. Queste modifiche non devono preoccupare gli utenti che utilizzano versioni precedenti di Windows10. (#6684)

### Bug corretti

* Sistemato un problema che causava il congelamento di NVDA quando ci si spostava per paragrafi in Microsoft Word in documenti molto estesi. (#6368)
* Le tabelle che venivano copiate da Microsoft Excel a Microsoft Word non sono più rilevate come tabelle di layout e comunque non vengono più ignorate. (#5927)
* Quando si cerca di scrivere in un documento protetto da scrittura in Microsoft Excel, NVDA ora emetterà un segnale acustico piuttosto che annunciare lettere che in realtà non vengono scritte. (#6570)
* La pressione del tasto Esc in Microsoft Excel non causerà più l'attivazione della modalità navigazione, a meno che l'utente non abbia preventivamente deciso di impostare la modalità navigazione con NVDA+spazio e poi sia entrato in modalità focus premendo invio su un campo di tipo form. (#6569)
* NVDA non si blocca più in un foglio di lavoro in Microsoft Excel nel quale si trova una riga o una colonna cui è stata applicata la funzione unisci. (#6216)
* L'annuncio di eventuale testo sporgente o ritagliato nelle celle di Microsoft Excel dovrebbe adesso risultare più accurato. (#6472)
* NVDA ora annuncerà se una casella di controllo risulta di sola lettura. (#6563)
* All'esecuzione di NVDA non verrà più mostrato un avviso nel caso in cui non sia possibile riprodurre il suono di avvio in quanto non risulta disponibile alcun dispositivo audio. (#6289)
* I controlli ribbon in Microsoft Excel che risultano non disponibili ora vengono segnalati correttamente. (#6430)
* NVDA non annuncerà più la parola "pannello" quando si riducono tutte le finestre ad icona. (#6671)
* Ora vengono annunciati i caratteri digitati anche nelle app Universal Windows Platform (UWP)  (inclusa Microsoft Edge) nell'aggiornamento Windows 10 Creators. (#6017)
* Il tracciamento del mouse ora funziona anche in computer a cui sono collegati più monitor. (#6598)
* NVDA non diventa più inutilizzabile all'uscita da Windows Media Player,  nel caso il focus fosse posizionato su un cursore d'avanzamento. (#5467)

### Cambiamenti per sviluppatori

* I profili e i file di configurazione verranno automaticamente aggiornati per adeguarsi alle modifiche inerenti schema e struttura degli stessi. Se c'è un errore durante l'aggiornamento, viene visualizzata una notifica, la configurazione è ripristinata, i vecchi file di configurazione saranno disponibili nei log di NVDA al 'livello info'. (#6470)

## 2016.4

Le principali caratteristiche di questa versione si focalizzano su un supporto molto migliorato per Microsoft Edge; modalità navigazione nell'app Posta di Windows10; miglioramenti significativi all'interfaccia delle finestre di dialogo di NVDA.

### Novità

* NVDA è in grado di indicare i rientri delle righe utilizzando dei toni, ossia segnali acustici. Questa funzione può essere configurata tramite l'opzione "Annuncia rientri righe con", presente nella finestra formattazione documento all'interno delle preferenze di NVDA. (#5906)
* Supporto per il Display Braille Orbit Reader 20. (#6007)
* è stata introdotta una funzione che permette all'occorrenza di aprire all'avvio il visualizzatore sintesi vocale. è possibile configurarla tramite una casella di controllo nella finestra "Visualizzatore sintesi vocale". (#5050)
* Quando si riapre la finestra visualizzatore sintesi vocale, verranno ora ripristinate la posizione e le dimensioni. (#5050)
* I campi contenenti riferimenti incrociati in Microsoft Word vengono ora trattati come collegamenti ipertestuali. Vengono annunciati come "link" e naturalmente possono essere attivati. (#6102)
* Supporto per i Display Braille della Baum Supervario2, Vario340 e HumanWare Brailliant2. (#6116)
* Supporto iniziale per Microsoft Edge Anniversary Update. (#6271)
* Durante la lettura delle email, verrà utilizzata la modalità navigazione nell'app Posta di Windows10. (#6271)
* Nuova lingua: lituano.

### Cambiamenti

* Aggiornate le librerie Braille di traduzione liblouis alla versione 3.0.0. Questo comporta un miglioramento significativo per il braille inglese, Unified English Braille. (#6109, #4194, #6220, #6140)
* Nel gestore componenti aggiuntivi, i pulsanti Abilita e Disabilita componente aggiuntivo sono provvisti di tasto rapido (alt-a e alt-d). (#6388)
* Risolti molti problemi di visualizzazione e a llineamento nelle finestre di dialogo di NVDA. (#6317, #5548, #6342, #6343, #6349)
* La finestra di dialogo formattazione documento è stata sistemata in modo da poter scorrere fluidamente mentre si esplorano le opzioni. (#6348)
* Sistemato il layout della finestra "pronuncia/punteggiatura simboli" di modo da utilizzare l'intera larghezza della finestra per l'elenco dei simboli. (#6101)
* Nella modalità navigazione dei browser web, i tasti rapidi per muoversi tra i campi editazione "e, shift-e, f e shift-f" ora supportano anche i campi di sola lettura, per cui la loro pressione farà in modo che ci si sposti anche su quei campi se esistenti. (#4164)
* Nella finestra formattazione documento di NVDA, la funzione "Leggi i cambiamenti di formattazione dopo il cursore", è stata rinominata in "Notifica cambiamenti di formattazione dopo il cursore", in quanto il messaggio appare anche sui Display Braille oltre che annunciato tramite sintesi vocale. (#4164)
* Effettuate correzioni sull'aspetto della finestra di benvenuto di NVDA. (#6350)
* I pulsanti "ok" e "annulla" delle finestre di dialogo di NVDA vengono ora allineati a destra rispetto alla finestra. (#6333)
* Per i campi ad immissione numerica vengono ora utilizzati i pulsanti spin, un esempio è il parametro "percentuale cambio di tono per le maiuscole" della finestra impostazioni voce. Per inserire il valore sarà possibile o utilizzare le frecce su/giù, oppure digitarlo direttamente come si trattasse di un campo editazione. (#6099)
* Migliorato nei browser web il sistema di analisi e gestione degli iframe (documenti incorporati all'interno di altri documenti). In Firefox un "iframe" viene annunciato come "frame". (#6047)

### Bug Corretti

* Sistemato un errore insolito che accadeva quando si usciva da NVDA con il visualizzatore sintesi vocale attivo. (#5050)
* Le mappe immagini vengono riportate correttamente ora in Mozilla Firefox. (#6051)
* Mentre ci si trova nella finestra di dialogo dizionari, la pressione del tasto invio salverà ogni cambiamento effettuato e chiuderà la finestra. In precedenza, il tasto invio non aveva alcuna funzione. (#6206)
* Vengono mostrati in braille i messaggi inerenti il cambio del metodo di immissione (immissione con caratteri alfanumerici, Modalità cursore a forma piena, Modalità cursore  a forma dimezzata, etc). (#5892, #5893)
* Quando si disabilita e si riabilita velocemente un componente aggiuntivo, o viceversa, lo stato del componente si aggiorna correttamente. (#6299)
* Quando si utilizza Microsoft Word, possono essere letti i campi dei numeri di pagina nelle intestazioni. (#6004)
* Il mouse può venir utilizzato per spostare il focus tra l'elenco simboli e i campi editazione nella finestra pronuncia punteggiatura/simboli. (#6312)
* In modalità navigazione in Microsoft Word, sistemato un problema che impediva l'apertura dell'elenco elementi nel caso un documento contenesse un collegamento ipertestuale non corretto. (#5886)
* Dopo essere stata chiusa attraverso la barra delle applicazioni o con alt-f4, la casella di controllo visualizzatore sintesi vocale nel menu di NVDA rispecchierà lo stato della finestra. (#6340)
* Il comando ricarica componenti aggiuntivi non causerà più problemi ai profili con eventi associati, ai nuovi documenti nei browser web e allamodalità di navigazione in linea. (#2892, #5380)
* Nell'elenco delle lingue delle impostazioni generali di NVDA, alcune lingue come l'Aragonese vengono visualizzate correttamente in Windows10. (#6259)
* I tasti di sistema emulati (ad esempio un pulsante di un display braille che simula la pressione del tasto tab) vengono ora mostrati nella lingua configurata per NVDA sia nell'aiuto tastiera che nella finestra di dialogo gesti di immissione. In precedenza, venivano presentati sempre in inglese.  (#6212)
* La modifica della lingua di NVDA (dalla finestra di dialogo impostazioni generali) non avrà alcun effetto fino al riavvio dello screen reader. (#4561)
* Non è più possibile lasciare vuoto il campo "voce", ossia il primo,  nella finestra di inserimento nuovi termini nei dizionari di NVDA. (#6412)
* Sistemato un problema occasionale che impediva il corretto riconoscimento di alcuni display braille su porta seriale. (#6462)
* In Microsoft Word, gli elenchi numerati nelle celle di una tabella vengono letti correttamente quando ci si sposta tra le celle. (#6446)
* Ora è possibile assegnare gesti personalizzati ai comandi forniti dal driver del	 display braille Handy Tech nella finestra Gesti di immissione di NVDA. (#6461)
* In Microsoft Excel, durante l'esplorazione di un foglio elettronico, la pressione di Invio o dell'Invio del tastierino numerico farà annunciare correttamente la linea successiva. (#6500)
* Risolto un problema che provocava talvolta il blocco di Itunes con NVDA in modalità navigazione in iTunes Store, Apple Music, etc. (#6502)
* Sistemati i crash nelle applicazioni a 64 bit basate su Google Chrome e Mozilla. (#6497)
* In Firefox con la modalità multiprocesso attiva, ora funzionano correttamente la modalità navigazione e i campi editazione. (#6380)

### Cambiamenti per sviluppatori (in inglese)

* It is now possible to provide app modules for executables containing a dot (.) in their names. Dots are replaced with underscores (_). (#5323)
* The new gui.guiHelper module includes utilities to simplify the creation of wxPython GUIs, including automatic management of spacing. This facilitates better visual appearance and consistency, as well as easing creation of new GUIs for blind developers. (#6287)

## 2016.3

Le principali caratteristiche di questa versione si focalizzano sulla possibilità di disabilitare i singoli componenti aggiuntivi, sul supporto per i campi modulo in Microsoft Excel, su un grosso miglioramento inerente la gestione e l'individuazione dei colori, sulla risoluzione e l'aggiunta di funzioni per alcuni display braille ed infine su un ulteriore sviluppo delle funzionalità per microsoft Word.

### Novità

* è possibile utilizzare la modalità navigazione per leggere i documenti pdf con il Browser Microsoft Edge in Windows10 Anniversary Update (#5740)
* Implementato l'annuncio del barrato e del doppio barrato in Microsoft Word. (#5800)
* In Microsoft Word, viene annunciato correttamente il titolo di una tabella se ne è stato assegnato uno. Se esiste una descrizione, può essere letta utilizzando il comando di lettura long description (NVDA+d) in modalità navigazione. (#5943)
* In Microsoft Word, NVDA ora è in grado di annunciare le informazioni sulla posizione quando ci si sposta per paragrafi (alt-shift-freccia su/giù). (#5945)
* In Microsoft Word, NVDA è in grado di annunciare la spaziatura righe, configurabile dalle impostazioni formato documento, e ascoltabile con la solita combinazione NVDA-f. Questo sia quando ci si sposta semplicemente con le frecce, sia quando si modifica la spaziatura righe con i tasti rapidi di Microsoft Word. (#2961)
* In Internet Explorer, vengono riconosciuti i documenti con struttura HTML5. (#5591)
* L'annuncio dei commenti in Microsoft Word può essere disabilitato tramite una casella di controllo presente nelle impostazioni formattazione documento di NVDA. . (#5108
* è ora possibile disattivare singoli componenti aggiuntivi dal gestore componenti. (#3090)
* Sono stati assegnati nuovi tasti rapidi per i modelli di display braille Alva bc640/680. (#5206)
* è stato introdotto un nuovo comando per spostare il display braille alla posizione del focus. Per adesso soltanto i modelli Alva640/680 contengono una combinazione tasti appropriata, ma è possibile assegnarne una attraverso la finestra tasti e gesti di immissione. (#5250)
* In Microsoft Excel è ora possibile interagire con i campi. Ci si sposta sui campi tramite l'elenco elementi oppure con i tasti appropriati di navigazione rapida per carattere, in modalità navigazione. (#4953)
* è possibile assegnare una combinazione di tasti o gesti alla funzione "il display braille segue": focus o cursore di controllo. Lo si fa tramite le impostazioni tasti e gesti di immissione. (#6173)

### Cambiamenti

* NVDA ora annuncia colori di base con una serie completa di 9 toni e 3 sfumature di colore, con le variazioni di luminosità e intensità. Questo risulta più comprensibile rispetto ad utilizzare  nomi di colori più soggettivi e meno intelligibili. (#6029)
* Modificato il funzionamento della combinazione nvda+f9/f10. Adesso una pressione della combinazione nvda-f10 selezionerà il testo, e una doppia pressione lo copierà negli appunti. (#4636)
* Aggiornata eSpeak NG alla versione Master 11b1a7b (22 Giugno 2016). (#6037)

### Bug corretti

* In modalità navigazione in Microsoft Word, verrà conservata la formattazione del contenuto quando viene copiato negli appunti. (#5956)
* In Microsoft Word, NVDA ora riporta correttamente le informazioni quando si utilizzano i comandi di Word per esplorare le tabelle (alt+home, alt+end, alt+paginaSu e alt+paginaGiù) e quelli per la selezione di tabelle (shift aggiunto ai comandi di navigazione). (#5961)
* Nelle finestre di dialogo di Microsoft Word, è stata enormemente migliorata la navigazione ad oggetti di NVDA. (#6036)
* In alcune applicazioni quali Visual Studio 2015, i tasti di scelta rapida (ad esempio control+c per copiare) vengono annunciati come ci si aspetta. (#6021)
* Risolto un bug molto raro  che si presentava durante la scansione per la ricerca di display braille collegati a porte seriali che rendeva i driver di tali braille non più utilizzabili. (#6015)
* Ora risulta molto più accurato il riconoscimento dei colori in Microsoft Word in quanto viene tenuto conto anche del tema utilizzato per Microsoft Office. (#5997)
* Risultano di nuovo funzionanti sia il supporto alla modalità navigazione in Microsoft Edge  sia la lettura dei risultati e dei suggerimenti di ricerca nel menu avvio in Windows10, con Build successive ad aprile 2016. (#5955)
* In Microsoft Word, la lettura automatica delle intestazioni tabella funziona meglio anche in concomitanza di unione di celle. (#5926)
* Nell'app Mail di Windows 10, NVDA non commette più errori durante la lettura dei messaggi. (#5635)
* Quando la funzione leggi tasti di comando è attiva, il tasto Blocca Maiuscole non viene più annunciato due volte. (#5490)
* Vengono letti di nuovo correttamente  i controlli nella finestra utente in Windows 10 Anniversary update. (#5942)
* Nel plugin Web Conference (ad esempio quello usato in out-of-sight.net) NVDA non leggerà di continuo le barre di progresso inerenti il segnale d'ingresso del microfono. (#5888)
* Quando si effettua una ricerca in modalità navigazione, sia successiva che precedente, NVDA distingue ora correttamente tra maiuscole e minuscole se la ricerca lo richiede. (#5522)
* Quando si modifica un valore del dizionario, vengono forniti degli avvisi nel caso di espressioni regolari non corrette. Inoltre NVDA non crasha più nel caso sia presente un file dizionario con espressioni regolari non corrette al proprio interno. (#4834)
* Se NVDA non è più in grado di comunicare con un Display Braille, (ad esempio perché è stato disconnesso), verrà automaticamente disattivato l'utilizzo del display braille senza provocare errori. (#1555)
* Migliorate leggermente le prestazioni di filtraggio nella finestra elenco elementi della modalità navigazione. (#6126)
* In Microsoft Excel, i valori dei nomi di sfondo annunciati da NVDA sono identici a quelli di Excel. (#6092)
* Migliorato il supporto alla schermata di Logon in Windows 10, compresi gli annunci per gli avvisi e l'attivazione dei campi password in modalità touch. (#6010)
* NVDA riconosce ora correttamente la seconda fila di cursor routing nei modelli ALVA BC640/680. (#5206)
* NVDA annuncia nuovamente le notifiche che appaiono nelle versioni più recenti di Windows 10. (#6096)
* Risolto un problema che occasionalmente non permetteva più a NVDA di riconoscere le pressioni dei tasti nei display braille Baum e HumanWare. (#6035)
* Se viene attivata la lettura dei numeri di riga nelle impostazioni formattazione documento di NVDA, i numeri di riga vengono mostrati anche sulle barre braille. (#5941)
* Quando la modalità voce è spenta, comandi come NVDA+tab per la lettura del focus vengono visualizzati correttamente nel visualizzatore sintesi vocale. (#6049)
* Nell'elenco messaggi di Outlook 2016, non vengono più annunciate informazioni associate con le bozze. (#6219)
* Nel browser Google Chrome, NVDA sarà in grado di funzionare anche quando la lingua del browser è diversa dall'inglese, sebbene questo bug non sia da attribuire a NVDA. (#6249)

### Cambiamenti per sviluppatori (in inglese)

* Logging information directly from a property no longer results in the property  being called recursively over and over again. (#6122)

## 2016.2.1

Questa versione risolve alcuni crash in Microsoft Word:

* NVDA non causa più crash all'avvio di Microsoft Word in Windows Xp. (#6033)
* Rimossa la funzione di rilevazione errori di grammatica, in quanto era la causa dei crash in Microsoft Word. #5877)

## 2016.2

Le principali novità di questa versione riguardano la capacità di annunciare gli errori di ortografia durante la scrittura; il supporto agli errori grammaticali in Microsoft Word; inoltre miglioramenti e correzioni di bug in Microsoft Office

### Novità

* In modalità navigazione in Microsoft Internet Explorer e altri controlli Mshtml, la pressione dei tasti a e shift-A per spostarsi tra le annotazioni successive e precedenti ora sposterà il cursore virtuale tra il testo inserito e cancellato. (#5691)
* In Microsoft Excel, NVDA ora annuncia il livello di un gruppo di celle, espanso o non espanso. (#5690)
* Premendo la combinazione di tasti (NVDA+f) due volte, le informazioni verranno mostrate in modalità navigazione. (#4908)
* In Microsoft Excel 2010 e successivi, viene ora annunciato l'ombreggiatura e il riempimento delle celle. Queste informazioni sono controllate dal parametro annuncia colori nella finestra impostazioni formattazione documento di NVDA. (#3683)
* Nuove tabelle di traduzione braille: Greco Koine. (#5393)
* Nel visualizzatore log è ora possibile salvare il log con la combinazione di tasti ctrl-s. (#4532)
* Se la lettura degli errori di ortografia è attiva e supportata dal controllo focalizzato, NVDA emetterà un suono per avvisare l'utente dell'errore commesso in fase di scrittura. La funzione può essere disabilitata dalla finestra di dialogo impostazioni tastiera, opzione "emetti segnale acustico in fase di scrittura per gli errori di ortografia". (#2024)
* In Microsoft Word vengono annunciati gli errori di grammatica. La funzione può essere disattivata dalla finestra di dialogo impostazioni formattazione documento, opzione Annuncia errori grammaticali. (#5877)

### Cambiamenti

* In modalità navigazione e nei campi di testo editabili, NVDA tratta il tasto Invio e il tasto Invio del tastierino numerico allo stesso modo. (#5385)
* NVDA è passato alla sintesi eSpeak NG. (#5651)
* In Microsoft Excel, NVDA non ignora più un'intestazione di colonna per una cella quando c'è una riga vuota tra la cella e l'intestazione. (#5396)
* In Microsoft Excel, le coordinate sono ora annunciate prima delle intestazioni per eliminare qualsiasi ambiguità tra intestazioni e contenuto. (#5396)

### Bug corretti

* In modalità navigazione, quando si tenta di utilizzare un tasto singolo per spostarsi in un elemento che non è supportato per il documento corrente, NVDA avvertirà che la funzione non è supportata piuttosto di dire che non c'è alcun controllo in quella direzione. (#5691)
* Quando si visualizzano i fogli nell'elenco elementi in Microsoft Excel, ora vengono inclusi anche i fogli contenenti soltanto grafici. (#5698)
* NVDA non fornisce più informazioni senza senso quando si cambia finestra in un'applicazione Java con finestre multiple come IntelliJ o Android Studio. (#5732)
* Nei controlli editazione Scintilla come ad esempio Notepad++, il braille si aggiorna correttamente quando si sposta il cursore con i tasti del display braille. (#5678)
* NVDA non andrà più in crash sporadicamente all'attivazione della modalità Braille Output. (#4457)
* In Microsoft Word, verrà rispettata l'unità di misura scelta dall'utente (centimetri o pollici) per annunciare il rientro dei paragrafi. (#5804)
* Quando si utilizza un display braille, molti messaggi che venivano gestiti solo dalla sintesi vocale ora verranno visualizzati anche in braille. (#5557)
* Nelle applicazioni Java accessibili, viene ora annunciato il livello di una visualizzazione ad albero. (#5766)
* Sistemato un crash nelle applicazioni Flash con Mozilla Firefox. (#5367)
* In Google Chrome e browser basati su  Chrome, i documenti all'interno di finestre di dialogo di applicazioni vengono gestiti anche in modalità navigazione. (#5818)
* In Google Chrome e browser basati su  Chrome, è possibile forzare la modalità navigazione per NVDA nei documenti all'interno di applicazioni o finestre di dialogo. (#5818)
* In Internet Explorer e altri controlli MSHTML, lo spostamento del focus su certi controlli (nello specifico, dove viene usato aria-activedescendant) non attiverà più inavvertitamente la modalità navigazione. Questo capitava, per esempio, quando ci si spostava tra i suggerimenti di un campo contenente indirizzi durante la composizione di un messaggio in Gmail. (#5676)
* In Microsoft Word, NVDA non rallenterà più vistosamente in tabelle molto grandi quando è attivata la funzione di annuncio intestazioni righe/colonne. (#5878)
* In Microsoft word, NVDA non annuncerà più il testo come intestazione, quando il testo presenta un rientro ma non ha uno stile di intestazione definito. #5186)
* In modalità navigazione in Microsoft Word, i tasti , e Shift-, funzionano correttamente anche per le tabelle. (#5883)

### Cambiamenti per sviluppatori (in inglese)

* NVDA's C++ components are now built with Microsoft Visual Studio 2015. (#5592)
* You can now present a text or HTML message to the user in browse mode using ui.browseableMessage. (#4908)
* In the User Guide, when a <!-- KC:setting command is used for a setting which has a common key for all layouts, the key may now be placed after a full-width colon (：) as well as the regular colon (:). (#5739) -->

## 2016.1

Le novità di questa versione si concentrano principalmente sulla possibilità di abbassare il volume di altre applicazioni quando la sintesi vocale è in funzione; su un miglioramento della visualizzazione braille; sono stati corretti alcuni errori nell'uso con Microsoft Office e, non da ultimo, miglioramenti della modalità navigazione in Itunes.

### Novità

* Nuove tabelle di traduzione Braille: Polacco computer 8 punti, Mongolo. (#5537, #5574)
* è possibile modificare l'aspetto del cursore Braille oppure disattivarlo del tutto tramite le due voci di configurazione apposite aggiunte alla finestra di preferenze, braille. (#5198)
* NVDA ora può connettersi al Display Braille  HIMS Smart Beetle via Bluetooth. (#5607)
* NVDA è in grado di abbassare il volume di altri suoni quando la sintesi vocale è in funzione grazie ad una nuova caratteristica chiamata attenuazione audio, solo sui sistemi che fanno girare Windows8 o versioni successive. L'attenuazione audio può essere configurata o nella finestra sintetizzatore, oppure premendo la combinazione di tasti NVDA+Shift+d. (#3830, #5575)
* Supporto per i Display Braille APH Refreshabraille in modalità HID e Baum VarioUltra e Pronto! quando connessi via USB. (#5609)
* Supporto per i display braille HumanWare Brailliant BI/B quando il protocollo è impostato su  OpenBraille. (#5612)

### Cambiamenti

* L'annuncio del testo enfatizzato è ora disattivato da impostazioni predefinite. (#4920)
* Nella lista elementi di Microsoft Excel, il tasto caldo per le formule è cambiato in alt+r di modo da diversificarlo da quello del filtro. (#5527)
* Aggiornato liblouis braille translator alla versione 2.6.5. (#5574)
* La parola "testo" non viene più annunciata quando  si sposta il focus o il cursore di controllo su oggetti di testo. (#5452)

### Bug Corretti

* In iTunes 12, la modalità navigazione si aggiorna correttamente quando viene caricata una pagina nuova in Itunes Store (#5191)
* In Internet Explorer e altri controlli MSHTML, quando il livello di un'intestazione è sostituito per migliorare l'accessibilità, lo spostamento su livelli di intestazioni specifici con le lettere singole  ora si comporta come dovrebbe (nello specifico, se il livello ARIA si sovrappone al livello del tag h).  (#5434)
* In Spotify, il focus non finisce più in oggetti sconosciuti. (#5439)
* Il Focus viene ripristinato correttamente quando si ritorna da un'altra applicazione a Spotify. (#5439)
* Quando si commuta tra modalità focus e navigazione, viene indicato anche in Braille oltre che con la sintesi vocale. (#5239)
* Il pulsante Start nella barra delle applicazioni non viene più annunciato come un elenco e/o come selezionato in alcune versioni di Windows. (#5178)
* Non viene più visualizzato il messaggio "inserito" quando si scrive un nuovo messaggio in Microsoft Outlook. (#5486)
* Se mentre si utilizza un display braille viene selezionato del testo nella riga attuale (per esempio durante una ricerca di testo che compare sulla stessa riga in un editor),il display braille effettuerà uno scorrimento se necessario. (#5410)
* NVDA non si chiuderà più inaspettatamente quando si esce da una finestra del prompt dei comandi con alt+f4 in Windows10. (#5343)
* Nell'elenco elementi in modalità navigazione, quando viene modificato il tipo di elemento, il campo "filtra per" viene pulito. (#5511)
* Nei campi editazione nelle applicazioni Mozilla,  il mouse leggerà di nuovo righe o parole quando lo si sposta, piuttosto che l'intero documento.  (#5535)
* Quando si sposta il mouse nei campi editazione delle applicazioni Mozilla, la lettura non si interrompe più in presenza di link all'interno di una riga. (#2160, #5535)
* In Internet Explorer, il sito web shoprite.com viene gestito anche in modalità navigazione.) (#5569)
* Risolto un bug inerente il tracciamento delle modifiche in Microsoft Word. (#5566)
* Se viene visualizzato un pulsante ciclico, ora NVDA avvertirà se questo è premuto o non premuto. (#5441)
* Viene annunciata di nuovo correttamente un eventuale cambiamento della forma del mouse. (#5595)
* Quando vengono annunciati i rientri riga, è stata migliorata la gestione della lettura degli spazi. (#5610)
* Sistemato un problema con i metodi candidate list per i caratteri asiatici durante la chiusura. (#4145)
* In Microsoft Office 2013 e successivi, se un menu ribbon viene impostato per mostrare soltanto le schede, ora gli elementi di quel ribbon saranno di nuovo annunciati  quando una scheda verrà attivata. (#5504)
* Miglioramenti con i gesti e le assegnazioni degli stessi sui touch screen. (#5652)
* Touch screen hovers are no longer reported in input help. (#5652)
* NVDA non commetterà più errori nell'elencare i commenti nell'elenco elementi di Microsoft Excel se un commento appartiene ad una cella unita. (#5704)
* In casi molto rari, NVDA non commetterà più errori nella lettura del contenuto di fogli in Microsoft Excel quando sono attivate le funzioni di annuncio intestazioni riga/colonna. (#5705)
* In Google Chrome, la navigazione in un campo candidate per l'immissione di caratteri asiatici ora funziona correttamente. (#4080)
* Durante la ricerca di musica in Itunes, la modalità navigazione viene aggiornata come dovrebbe. (#5659)
* In Microsoft Excel, la pressione della combinazione di tasti shift+f11 per creare un nuovo foglio ora annuncia la nuova posizione piuttosto che non dire nulla. (#5689)
* Sistemato un problema nell'immissione di caratteri coreani in Braille. (#5640)

### Cambiamenti per sviluppatori, in inglese

* The new audioDucking.AudioDucker class allows code which outputs audio to indicate when background audio should be ducked. (#3830)
* nvwave.WavePlayer's constructor now has a wantDucking keyword argument which specifies whether background audio should be ducked while audio is playing. (#3830)
 * When this is enabled (which is the default), it is essential that WavePlayer.idle be called when appropriate.
* Enhanced I/O for braille displays: (#5609)
 * Thread-safe braille display drivers can declare themselves as such using the BrailleDisplayDriver.isThreadSafe attribute. A driver must be thread-safe to benefit from the following features.
 * Data is written to thread-safe braille display drivers in the background, thus improving performance.
 * hwIo.Serial extends pyserial to call a callable when data is received instead of drivers having to poll.
 * hwIo.Hid provides support for braille displays communicating via USB HID.
 * hwPortUtils and hwIo can optionally provide detailed debug logging, including devices found and all data sent and received.
* There are several new properties accessible from touch screen gestures: (#5652)
 * MultitouchTracker objects now contain a childTrackers property which contains the MultiTouchTrackers the tracker was composed of. For example, 2 finger double tap has child trackers for two 2-finger taps. The 2-finger taps themselves have child trackers for two taps.
 * MultiTouchTracker objects now also contain a rawSingleTouchTracker property if the tracker was the result of one single finger doing a tap, flick or hover. The SingleTouchTracker allows access to the underlying ID assigned to the finger by the operating system and whether or not the finger is still in contact at the current time.
 * TouchInputGestures now have x and y properties, removing the need to access the tracker for trivial cases.
 * TouchInputGesturs now contain a preheldTracker property, which is a MultitouchTracker object representing the other fingers held while this action was being performed.
* Two new touch screen gestures can be emitted: (#5652)
 * Plural tap and holds (e.g. double tap and hold)
 * A generalized identifier with finger count removed for holds (e.g. hold+hover for 1finger_hold+hover).

## 2015.4

Le principali migliorie presenti in questa versione si concentrano su un notevole incremento delle prestazioni in Windows10; nella possibilità di poter scegliere NVDA nel centro accessibilità a partire da Windows8 in poi; grossi miglioramenti in Microsoft Excel, con la possibilità di elencare e rinominare i fogli ed accedere al contenuto delle celle di sola lettura anche in documenti protetti; inoltre, supporto alla modifica per i campi rich text in Mozilla Firefox, Google Chrome e Mozilla Thunderbird.

### Novità

* NVDA compare nel centro accessibilità a partire da Windows8 in poi. (#308)
* Se le opzioni di annuncio dei cambiamenti di formattazione sono attive, NVDA è in grado di riportarle quando ci si muove tra le celle in Excel. (#4878)
* Una nuova opzione chiamata "leggi testo enfatizzato" è stata aggiunta alla finestra delle impostazioni di formattazione documento di NVDA. Per impostazione predefinita, questa opzione consente di segnalare automaticamente l'esistenza di testo enfatizzato nei documenti. Al momento, questo è supportato solo per i tag em e strong per Internet Explorer e altri controlli MSHTML. (#4920)
* viene ora annunciato se del testo è inserito o cancellato  in modalità navigazione in Internet Explorer e nei controlli MSHTML, se l'opzione Leggi revisioni è attiva nella finestra formattazione documento. (#4920)
* In Microsoft Word Quando si esaminano le modifiche nell'elenco elementi di NVDA, ora vengono fornite più informazioni, compresi quali cambiamenti alla formattazione sono stati effettuati durante le varie modifiche. (#4920)
* Microsoft Excel: è ora possibile elencare e rinominare i fogli dall'elenco elementi di NVDA (NVDA+f7). (#4630, #4414)
* è ora possibile stabilire se il simbolo attuale debba essere inviato al sintetizzatore, magari per ottenere una pausa o per un cambio di inflessione, nella finestra pronuncia punteggiatura/simboli. (#5234)
* In Microsoft Excel, NVDA ora segnala gli eventuali messaggi di input stabiliti dall'autore del foglio nelle celle. (#5051)
* Supporto per le barre braille Pronto! v4 e Vario Ultra, prodotte dalla Baum, quando connesse via Bluetooth. (#3717)
* Supporto per la modifica di campi rich text in app quali Google Docs, quando si utilizza Mozilla Firefox e Mozilla Thunderbird e si utilizza un display braille. (#1668)
* Supporto per la modifica di campi rich text in app quali Google Docs, quando si utilizza Google Chrome e si usa un display braille. (#2634)
 * è richiesto Chrome dalla versione 47 in su.
* In modalità navigazione in Microsoft Excel, è possibile esplorare le celle di sola lettura nei documenti protetti. (#4952)

### Cambiamenti

* L'opzione "leggi revisioni" presente nella finestra "formattazione documento" è ora attiva da  impostazioni predefinite. (#4920)
* Quando ci si sposta per carattere in Microsoft Word e l'opzione annuncia revisioni è attiva, vengono fornite meno informazioni sulle varie modifiche per rendere più agevole la lettura. Per ascoltare ogni singolo dettaglio, servirsi dell'elenco elementi. (#4920)
* Aggiornato liblouis braille translator a 2.6.4. (#5341)
* Un gran numero di simboli, inclusi quelli per la matematica di base, sono stati spostati sul livello "qualcosa" di modo che essi vengano letti da impostazioni predefinite. (#3799)
* Se la sintesi vocale lo supporta, verranno effettuate delle pause in concomitanza di parentesi e del trattino d'unione (–). (#3799)
* Quando si seleziona del testo, il testo viene annunciato prima della parola "Selezionato". (#1707)

### Bug corretti

* Aumento delle prestazioni nella navigazione dell'elenco  messaggi in Outlook 2010/2013. (#5268)
* In un grafico in Microsoft Excel, la navigazione con alcuni tasti come ctrl+pagina su/giù per cambiare foglio, ora funziona correttamente. (#5336)
* Sistemato l'aspetto visivo dei pulsanti nella finestra di avviso che viene visualizzata quando si tenta di passare a una versione precedente di NVDA. (#5325)
* In Windows 8 e versioni successive, NVDA ora si avvia  molto prima, quando configurato per l'avvio dopo l'accesso a Windows. (#308)
 * Se ciò è stato attivato utilizzando una versione precedente di NVDA, sarà necessario disattivarlo e riattivarlo in modo che la modifica abbia effetto. Seguire questa procedura:
  1. Aprire la finestra di dialogo Impostazioni generali.
  1. Deselezionare la casella di controllo Avvia automaticamente NVDA dopo l'accesso a Windows.
  1. Premere il tasto OK.
  1. Aprire nuovamente la finestra di dialogo Impostazioni generali.
  1. Controllare la casella di controllo Avvia automaticamente NVDA dopo l'accesso a Windows.
  1. Premere il tasto OK.
* Miglioramenti delle prestazioni per UI Automation, tra cui File Explorer e Task Viewer. (#5293)
* NVDA ora passa correttamente alla modalità focus quando si preme tab e ci si sposta in un controllo Aria di una griglia di sola lettura, per Mozilla Firefox e altri controlli Gecko. (#5118)
* NVDA ora annuncia correttamente l'assenza di oggetti precedenti quando si esegue un flick sul touch screen.
* Risolto un problema nell'immissione di più parole nel campo filtro nella finestra gesti di Immissione. (#5426)
* NVDA non si blocca più in alcuni casi quando connesso ad un display Braille Brailliant via USB. (#5406)
* Nelle lingue con caratteri congiunti, le descrizioni degli stessi ora funziona correttamente anche con le lettere maiuscole inglesi. (#5375)
* NVDA non si dovrebbe più bloccare all'apertura del menu avvio in Windows10. (#5417)
* In Skype Desktop, vengono annunciate correttamente tutte le notifiche, anche quelle che scompaiono in presenza di altre. (#4841)
* Le notifiche vengono annunciate correttamente anche in Skype 7.12 e successive. (#4841)
* NVDA ora aggancia correttamente il focus quando si esce da un menu contestuale in alcune applicazioni come Jart. (#5302)
* In Windows7 e successivi, vengono annunciati correttamente di nuovo i colori in alcune applicazioni come Wordpad.  (#5352)
* Durante la modifica di una diapositiva in Microsoft Powerpoint, la pressione del tasto invio ora annuncia correttamente alcune tipologie di testo inserito come numeri o elenchi puntati. (#5360)

## 2015.3

Le principali migliorie presenti in questa versione si concentrano principalmente nel supporto iniziale a Windows10, nella possibilità di disattivare la navigazione a lettere singole utile in alcune applicazioni web, in una gestione migliorata di Internet Explorer e per finire nella risoluzione di alcuni problemi durante la scrittura in combinazione con i display braille.

### Novità

* Se richiesto, vengono segnalati ora anche gli errori di ortografia presenti nei campi editazione di Internet Explorer e altri controlli MSHTML. (#4174)
* Supporto per un numero molto più ampio di  simboli matematici unicode presenti in un testo. (#3805)
* I suggerimenti di ricerca che appaiono nella schermata di start in Windows10 ora vengono annunciati automaticamente. (#5049)
* Supporto per i Display Braille EcoBraille 20, EcoBraille 40, EcoBraille 80 e EcoBraille Plus. (#4078)
* Nella modalità navigazione, è possibile attivare o disattivare la navigazione a lettere singole con la combinazione di tasti NVDA+Shift+Spazio. Quando disattiva, i tasti premuti saranno passati alle applicazioni web, il che risulta utile in applicazioni web quali Twitter, Gmail o Facebook. (#3203)
* Nuove tabelle braille: Finlandese 6 punti, Irlandese grado 1, Irlandese grado 2, coreano grado 1 (2006), Coreano grado 2 (2006). (#5137, #5074, #5097)
* Aggiunto il supporto alla tastiera Qwerty della barra braille Papenmeier Braillex Live Plus. (#5181)
* Supporto sperimentale al nuovo Browser Edge di Microsoft, presente in Windows10. (#5212)
* Nuova lingua: Kannada.

### Cambiamenti

* liblouis braille translator aggiornato alla versione  2.6.3. (#5137)
* Quando si tenta di installare una versione precedente di NVDA rispetto a quella attualmente installata, si verrà avvertiti che l'operazione è caldamente sconsigliata e  che NVDA dovrebbe essere completamente disinstallato prima di procedere. (#5037)

### Bug corretti

* Nella modalità navigazione in Internet Explorer e altri controlli MSHTML, lo spostamento con la navigazione veloce con il tasto "f" per andare al campo successivo non presenta più elementi ornamentali. (#4204)
* In Firefox, NVDA non cerca più di creare una descrizione per le schede  ARIA basata su tutto il testo all'interno. (#4638)
* Migliorata la lettura dei contenuti quando si preme tab per spostarsi tra sezioni, articoli o finestre di dialogo in Internet Explorer e altri controlli MSHTML. (#5021, #5025)
* Quando si utilizzano le barre Baum / Humanware / APH  con una tastiera braille, la scrittura non smette di funzionare dopo aver premuto un altro tipo di tasto sul display. (#3541)
* In Windows 10, non vengono più lette informazioni fuori luogo quando si preme ALT + TAB o alt + shift + tab per passare da un'applicazione all'altra. (#5116)
* Non vi sono più errori di scrittura nel testo in Microsoft Word quando si utilizza un display braille. Capitava a volte che le lettere venissero inserite alla rinfusa. (#2953)
* In modalità navigazione usando Internet Explorer o altri controlli mshtml, il contenuto viene letto correttamente anche quando un elemento appare o cambia e il focus viene posizionato su di esso. (#5040)
* In modalità navigazione in Microsoft Word, il display braille e il cursore di controllo si aggiornano correttamente utilizzando la navigazione a lettere singole. (#4968)
* In braille, Non vengono più mostrati spazi inesistenti, prima o dopo gli indicatori di controllo di formattazione. (#5043)
* Quando un'applicazione inizia a rispondere lentamente e si decide di passare ad un'altra applicazione, NVDA risulterà molto più rapido nella maggior parte dei casi con il nuovo programma che ha il focus. (#3831)
* Le notifiche di Windows10 vengono ora riportate correttamente. (#5136)
* In alcune caselle combinate UiAutomation, il valore viene letto correttamente man mano che cambia.
* In modalità navigazione nei browser web, la pressione del tasto tab si comporta correttamente quando si entra in un documento all'interno di un frame. (#5227)
* La schermata di blocco di Windows 10 può ora essere gestita con un touch screen. (#5220)
* In Windows 7 e versioni successive, il testo non viene più scritto alla rinfusa quando si digita in alcune applicazioni come Wordpad e Skype con un display braille. (#4291)
* Nella schermata di blocco di Windows 10, non è più possibile leggere  appunti, accedere alle applicazioni in esecuzione con il cursore, modificare la configurazione di NVDA, ecc (#5269)

### Cambiamenti per sviluppatori, in inglese

* You can now injet raw input from a system keyboard that is not handled natively by Windows (e.g. a QWERTY keyboard on a braille display) using the new keyboardHandler.injectRawKeyboardInput function. (#4576)
* eventHandler.requestEvents has been added to request particular events that are blocked by default; e.g. show events from a specific control or certain events even when in the background. (#3831)
* Rather than a single i18nName attribute, synthDriverHandler.SynthSetting now has separate displayNameWithAccelerator and displayName attributes to avoid reporting of the accelerator in the synth settings ring in some languages.
 * For backwards compatibility, in the constructor, displayName is optional and will be derived from displayNameWithAccelerator if not provided. However, if you intend to have an accelerator for a setting, both should be provided.
 * The i18nName attribute is deprecated and may be removed in a future release.

## 2015.2

Caratteristiche salienti di questa versione includono la capacità di leggere i grafici in Microsoft Excel, nonché il supporto per la lettura e la navigazione interattiva dei contenuti di tipo matematico.

### Novità

* è ora possibile spostarsi avanti e indietro per frasi in Microsoft Word con la combinazione di tasti alt+freccia giù o freccia su. (#3288)
* Nuove tabelle braille relative a molte lingue presenti in India. (#4778)
* In Microsoft Excel, NVDA notifica quando una cella possiede del contenuto che ne supera i bordi. (#3040)
* In Microsoft Excel, si può utilizzare la combinazione di tasti NVDA+f7 per ottenere un elenco dei grafici, dei commenti e delle formule. (#1987)
* Aggiunto il supporto per la lettura dei grafici in Excel. Per utilizzare tale funzione, premere NVDA+f7, selezionare il grafico desiderato, dopodiché usare le frecce per spostarsi tra i punti del grafico stesso. (#1987)
* Aggiunto il supporto a Mathplayer4. Tramite questa applicazione è possibile leggere e esplorare in maniera interattiva la matematica presente sulle pagine web, sui documenti Word o su Powerpoint. Consultare il manuale utente di NVDA per ottenere informazioni su come utilizzare questa funzione. (#4673)
* è ora possibile assegnare dei gesti o dei tasti rapidi per tutte le finestre di dialogo Preferenze di NVDA e anche per tutte le opzioni di formattazione documento, servendosi della finestra gesti e tasti di immissione. (#4898)

### Cambiamenti

* Nella finestra di dialogo Formattazione Documento, sono stati modificati i tasti rapidi per le funzioni leggi elenchi, leggi i link, leggi i numeri di riga e leggi il nome del carattere. (#4650)
* Nella finestra impostazioni Mouse di NVDA, sono stati aggiunti dei tasti rapidi per le funzioni Coordinate audio quando il mouse si sposta, e La luminosità controlla il volume delle coordinate audio. (#4916)
* NVDA ora riconosce un numero molto più cospicuo di colori. (#4984)
* Aggiornato liblouis braille translator alla versione 2.6.2. (#4777)

### Bug corretti

* La descrizione dei caratteri è ora gestita correttamente per i caratteri congiunti in alcune lingue indiane. (#4582)
* Se l'opzione "Considera attendibile la lingua della voce  corrente nel processare caratteri e simboli" risulta attiva, la finestra di dialogo "pronuncia punteggiatura/simboli" ora utilizza correttamente la lingua della voce, e la mostrerà anche sul titolo della finestra. (#4930)
* In Internet Explorer e altri controlli MSHTML, non vengono più annunciati erroneamenti i caratteri digitati nelle caselle combinate modificabili, come  il campo di ricerca di Google sulla home page di Google. (#4976)
* Durante la selezione dei colori nelle applicazioni Microsoft Office, ora viene letto il nome del colore. (#3045)
* La tabella Braille Danese ora funziona di nuovo regolarmente. (#4986)
* I tasti paginaSu e pagina giù funzionano di nuovo per cambiare diapositiva in una presentazione di Powerpoint. (#4850)
* In Skype Desktop 7.2 e versioni successive, sono stati risolti alcuni problemi che si evidenziavano spostandosi da una conversazione, ed inoltre viene di nuovo annunciato quando un contatto sta scrivendo. (#4972)
* Risolti i problemi durante la digitazione di alcuni simboli come le parentesi nel campo filtro della finestra di dialogo gesti e tasti di immissione. (#5060)
* In Internet Explorer e altri controlli MSHTML, la pressione dei tasti g o shift + g per spostarsi tra i grafici ora consente di spostarsi anche tra elementi contrassegnati come immagini a fini di accessibilità (ossia ARIA role img). (#5062)

### Cambiamenti per sviluppatori (in inglese)

* brailleInput.handler.sendChars(mychar) will no longer filter out a character if it is equal to the previous character by ensuring that the key sent is correctly released. (#4139)
* Scripts for changing touch modes will now honor new labeles added to touchHandler.touchModeLabels. (#4699)
* Add-ons can provide their own math presentation implementations. See the mathPres package for details. (#4509)
* Speech commands have been implemented to insert a break between words and to change the pitch, volume and rate. See BreakCommand, PitchCommand, VolumeCommand and RateCommand in the speech module. (#4674)
 * There is also speech.PhonemeCommand to insert specific pronunciation, but the current implementations only support a very limited number of phonemes.

## 2015.1

Caratteristiche salienti di questa versione includono la modalità di navigazione per i documenti in Microsoft Word e Outlook; importanti miglioramenti al supporto per Skype per Desktop; e correzioni significative per Microsoft Internet Explorer.

### Novità

* È ora possibile aggiungere nuovi simboli nella finestra di dialogo pronuncia punteggiatura/simboli. (#4354)
* Nella finestra di dialogo Gesti di immissione, è possibile utilizzare il nuovo parametro "Filtra per" campo per visualizzare solo i gesti che contengono parole specifiche. (#4458)
* NVDA annuncia automaticamente il testo in mintty. (#4588)
* In modalità navigazione Nella finestra di dialogo trova, ora esiste un'opzione che permette di  effettuare ricerche distinguendo tra maiuscole e minuscole. (#4584)
* Se si attiva la modalità navigazione con nvda+spazio in Microsoft Word, è possibile sia utilizzare i tasti di navigazione veloce o premere nvda+f7 per ottenere l'elenco degli elementi. (#2975)
* Migliorata notevolmente la lettura dei messaggi html in Microsoft Outlook 2007 e successivi. Nel caso la modalità navigazione non venga automaticamente attivata, è possibile ovviare al problema premendo nvda+spazio. (#2975)
* In Microsoft Word vengono automaticamente lette le intestazioni colonna di una tabella laddove l'autore le abbia dichiarate per la riga nelle proprietà della tabella Word. (#4510)
 * Tuttavia, per le tabelle in cui le righe sono state unite, questo non funzionerà automaticamente. In questa situazione, è comunque possibile impostare manualmente le intestazioni delle colonne in NVDA con NVDA + shift + c.
* In Skype per Desktop, vengono annunciate le notifiche. (#4741)
* In Skype per Desktop, è ora possibile rivedere la cronologia dei messaggi più recenti utilizzando NVDA+control+1 fino a NVDA+control+0; ad esempio NVDA+control+1 leggerà il messaggio più recente, mentre NVDA+control+0 il decimo messaggio. (#3210)
* In una conversazione su Skype per Desktop, NVDA annuncerà quando il contatto sta scrivendo. (#3506)
* NVDA può essere installato in maniera silenziosa dalla riga di comando senza che poi esso si avvii dopo l'installazione. Per farlo, utilizzare il parametro --install-silent. (#4206)
* Supporto per i modelli di barre braille Papenmeier BRAILLEX Live 20, BRAILLEX Live e BRAILLEX Live Plus. (#4614)

### Cambiamenti

* All'opzione "leggi gli errori di ortografia" presente nella finestra di dialogo Formattazione documento di NVDA ora è stato assegnato un tasto caldo, (alt+r). (#793)
* NVDA ora utilizza la lingua della sintesi vocale per processare caratteri e simboli (inclusi i nomi della punteggiatura e dei simboli), non tenendo conto dello stato dell'opzione cambio automatico della lingua. Per disattivare questa opzione di modo che NVDA utilizzi di nuovo la sua interfaccia della lingua, smarcare la casella di controllo della nuova opzione nelle impostazioni voce, chiamata "Considera attendibile la lingua della voce  corrente nel processare caratteri e simboli".
* è stato rimosso il supporto per il sintetizzatore Newfon. Questa sintesi ora la si può utilizzare tramite un componente aggiuntivo. (#3184)
* Affinché NVDA funzioni con Skype, ènecessario utilizzare una versione di Skype pari o superiore alla 7. (#4218)
* Migliorata la sicurezza nella ricerca e nello scaricamento degli aggiornamenti di NVDA, utilizzando il protocollo https e controllando l'integrità del file. (#4716)
* Aggiornata Espeak alla versione 1.48.04. (#4325)

### Bug corretti

* In Microsoft Excel, le intestazioni di righe e colonne unite vengono trattate correttamente. Ad esempio, se a1 e b1 sono unite, quando ci si sposta in b2 verrà notificato che la sua intestazione di colonna è a1-b1, piuttosto che niente. (#4617)
* Quando si modifica il contenuto di una casella di testo in Microsoft PowerPoint 2003, NVDA annuncerà correttamente il contenuto di ogni riga. In precedenza, per ogni paragrafo, le righe sarebbero sempre risultate spostate di un carattere. (#4619)
* Tutte le finestre di dialogo di NVDA sono ora al centro dello schermo, migliorando in presentazione visiva e usabilità. (#3148)
* In Skype per desktop, quando si entra in un messaggio introduttivo per aggiungere un contatto, lo spostamento lungo il testo funziona correttamente. (#3661)
* Quando si sposta il focus in un elemento di una visualizzazione ad albero in Eclipse Ide, se l'elemento precedentemente evidenziato era una casella di controllo, non verrà più annunciata in maniera errata.  (#4586)
* Nella finestra di dialogo controllo ortografico di Microsoft Word, l'errore successivo verrà segnalato automaticamente quando l'ultimo è stato modificato o ignorato utilizzando i rispettivi tasti di scelta rapida. (#1938)
* Il testo viene nuovamente letto correttamente in ambienti come il terminale di Tera Term Pro e documenti in Balabolka. (#4229)
* Risolto un problema con l'immissione di testo in Internet Explorer per quel che concerne le lingue asiatiche e in particolare il coreano. (#4045)
* Nella finestra di dialogo di immissione gesti, quando si seleziona un layout di tastiera per aggiungere un gesto di tipo tasto, la pressione del tasto Esc ora chiude il menu come previsto invece di chiudere la finestra di dialogo. (#3617)
* Quando si rimuove un componente aggiuntivo, la directory di quel componente viene eliminata correttamente dopo il riavvio di NVDA. In precedenza, era necessario riavviare due volte. (#3461)
* Sono stati risolti i principali problemi quando si usa Skype per Desktop 7. (#4218)
* Quando si invia un messaggio in Skype per desktop, non viene più letto due volte. (#3616)
* In Skype per desktop, NVDA non dovrebbe più leggere occasionalmente una grande quantità di messaggi senza fermarsi mai. (#4644)
* Risolto un problema in cui il comando data / ora di NVDA non rispettava le impostazioni internazionali specificate dall'utente in alcuni casi. (#2987)
* Risolto un problema che in modalità navigazione portava a far visualizzare testo senza senso, ad esempio in Google Gruppi. (#4793)
* NVDA non dovrebbe più bloccarsi dopo pochi secondi, quando il focus viene spostato da una applicazione Windows Store che viene sospesa. (#4572)
* Migliorata la gestione dell'attributo  aria-atomic nelle live region in Firefox. (#4794)
* per i documenti in modalità navigazione all'interno di applicazioni ARIA incorporati in un documento di Internet Explorer o altri controlli MSHTML, il contenuto sarà aggiornato in concomitanza dell'aggiornamento delle live region. (#4798)
* Quando il testo viene modificato o aggiunto nelle live region in Internet Explorer e altri controlli MSHTML in cui l'autore ha specificato che il testo è rilevante, solo il testo modificato o aggiunto è annunciato, e non tutto il testo dell'elemento che lo contiene. (#4800)
* I contenuti indicati dall'attributo aria-labelledby su elementi in Internet Explorer e altri controlli MSHTML sostituiscono correttamente il contenuto originale laddove risulta appropriato farlo. (#4575)
* Durante il controllo ortografico in Microsoft Outlook 2013, vengono regolarmente annunciate le parole errate. (#4848)
* In Internet Explorer e altri controlli MSHTML, non viene più annunciato il contenuto all'interno di elementi nascosti con il tag  visibility:hidden. (#4839, #3776)
* In Internet Explorer e altri controlli MSHTML, l'attributo title nei form, non prende più il sopravvento in maniera appropriata rispetto ad altre associazioni di etichette. (#4491)
* In Internet Explorer e altri controlli MSHTML, NVDA non ignora più la focalizzazione di un elemento grazie all'attributo aria-activedescendant. (#4667)

### Cambiamenti per sviluppatori

* Aggiornato wxPython alla versione 3.0.2.0. (#3763)
* Aggiornato Python alla versione 2.7.9. (#4715)
* NVDA non crasha più al riavvio dopo aver rimosso o  modificato un componente aggiuntivo che importa speechDictHandler nel suo modulo di installTasks. (#4496)

## 2014.4

### Novità

* Nuove lingue: Spagnolo Colombiano, Punjabi
* Risulta ora possibile riavviare NVDA con i componenti aggiuntivi disattivati dalla finestra di dialogo all'uscita. (#4057)
 * NVDA può essere avviato con i componenti aggiuntivi disabilitati con il parametro --disable-addons dalla riga di comando.
* Nei dizionari, è ora possibile  stabilire se un'occorrenza debba essere valutata se si incontra una parola intera; ad esempio non viene considerata nel caso si trovi all'interno di una parola molto lunga. (#1704)

### Cambiamenti

* Se ci si è spostati tramite la navigazione ad oggetti in un oggetto che è situato all'interno di un documento che supporta la modalità esplorazione, ma l'oggetto in cui ci si trovava non vi apparteneva, la modalità di esplorazione viene automaticamente impostata su documento. In precedenza questo accadeva soltanto se il navigatore ad oggetti veniva spostato con il focus. (#4369)
* L'elenco dei display braille e delle sintesi vocali nelle rispettive finestre di dialogo ora è reso in ordine alfabetico, ad eccezione per nessun display braille|nessun sintetizzatore  che ora si trovano alla fine. (#2724)
* liblouis braille translator aggiornato a 2.6.0. (#4434, #3835)
* In modalità navigazione, la pressione dei tasti e o Shift+e per andare al campo editazione successivo|precedente ora funziona anche nelle caselle combo-editazione. Un esempio è il nuovo campo di ricerca di Google. (#4436)
* Il click con il tasto sinistro del mouse nell'icona di NVDA presente sull'area di notifica ora consente di aprire il menu di NVDA, invece di non fare nulla. (#4459)

### Bug Risolti

* Quando si sposta il focus in un documento in modalità navigazione (ad esempio premendo alt+tab per andare in una pagina web già aperta) il cursore di controllo viene ora posizionato sul cursore virtuale, piuttosto che sul controllo evidenziato  (ad esempio un link vicino). (#4369)
* Nelle presentazioni Powerpoint , il cursore di controllo segue correttamente il cursore virtuale. (#4370)
* In Mozilla Firefox e altri browser basati sulla tecnologia Gecko, un nuovo contenuto all'interno di una live region sarà annunciato, anche se questo  appartiene ad un tipo di live region diversa.  (#4169).
* In Internet Explorer e altri controlli MSHTML, l'utente può accedere a tutti i contenuti anche quando un documento è all'interno di un altro documento (nello specifico, frameset all'interno di altri framesets). (#4418)
* NVDA non crasha più se si utilizza un display braille Handy Tech in alcune circostanze. (#3709)
* In Windows Vista, non verrà più mostrato uno strano messaggio "Punto d'entrata non trovato" quando si avvia NVDA dal Desktop. (#4235)
* Sono stati risolti grossi problemi nelle finestre di dialogo delle ultime versioni di Eclipse. (#3872)
* In Outlook 2010, lo spostamento del cursore funziona ora correttamente nei campi per gli appuntamenti e le richieste di meeting. (#4126)
* All'interno di una live region, il contenuto marcato come non live verrà ignorato. (#4405)
* Quando viene annunciato del testo in una barra di stato che contiene un nome, questo viene correttamente separato dalla prima parola del testo della barra di stato. (#4430)
* Nei campi di immissione password con l'opzione leggi le parole digitate attiva, non vengono più annunciati gli asterischi senza motivo. (#4402)
* Nell'elenco messaggi di Microsoft Outlook, gli elementi non sono più visti come campi data. (#4439)
* Quando si seleziona del testo nel controllo codice di Eclipse IDE, non viene più letta l'intera selezione ogni qualvolta viene modificata. (#2314)
* Varie versioni di Eclipse, quali Spring Tool Suite e la versione inclusa nel pacchetto  Android Developer Tools, vengono riconosciute e gestite di conseguenza. (#4360, #4454)
* Il tracciamento Mouse e l'esplorazione a tocco in Internet Explorer e altri controlli MSHTML (incluse molte app di Windows8) risultano molto più accurate su display con molti DPI o quando l'ingrandimento del documento viene cambiata. (#3494)
* Il tracciamento Mouse e l'esplorazione a tocco in Internet Explorer e altri controlli MSHTML leggeranno un maggior numero di etichette di pulsanti. (#4173)
* Quando si utilizza un display braille Papenmeier BRAILLEX con BrxCom, i tasti sul display ora funzionano come previsto. (#4614)

### Cambiamenti per sviluppatori, in inglese

* For executables which host many different apps (e.g. javaw.exe), code can now be provided to load specific app modules for each app instead of loading the same app module for all hosted apps. (#4360)
 * See the code documentation for appModuleHandler.AppModule for details.
 * Support for javaw.exe is implemented.

## 2014.3

### Nuove caratteristiche

* La riproduzione del suono all'avvio e alla chiusura di nvda, ora può essere disabilitata tramite una nuova opzione nelle impostazioni generali. (#834)
* L'aiuto per i componenti aggiuntivi che lo supportano, ora può essere raggiunto dalla gestione componenti aggiuntivi. (#2694)
* supporto per il Calendario in Microsoft Outlook 2007 e superiori (#2943) incluso:
 * Notifica del'ora corrente quando ci si sposta con le frecce,
 * Indicazione se l'ora selezionata è presente in un appuntamento,
 * Notifica dell'appuntamento selezionato quando si preme tab
 * Filtro intelligente per la data in modo da notificarla solo se la selezione della nuova ora o del nuovo appuntamento è in un giorno diverso rispetto all'ultimo.
* Esteso il supporto per la Inbox e altre liste messaggi in Outlook 2010 e superiori (#3834) including:
 * Possibilità di silenziare le intestazioni di colonna(daà oggetto etc) disattivando l'opzione annuncia le intestazioni di riga e colonna nelle impostazioni di formattazione documento,
 * Possibilità di usare icomandi di navigazione tabella (control + frecce)  per muoversi tra le singole colonne.
* Microsoft word: se un'immagine in linea non ha impostato un testo alternativo, al suo posto, NVDA riporterà il titolo se l'autore ne ha fornito uno. (#4193)
* Microsoft Word: Viene riportata l'indentazione di paragrafo col comando (NVDA+f) e in modo automatico quando la nuova impostazione notifica indentazione paragrafo nella formattazione documento è abilitata (#4165).
* Viene letto automaticamente il testo inserito come un nuovo bullet, numero o una tabulazione quando viene premuto invio nei documenti editabili o in un campo di testo. (#4185)
* Microsoft word: Premendo NVDA+alt+c verrà letto il testo del commento se il cursore è posizionato sopra. (#3528)
* Migliorato il supporto per la lettura automatica dell'intestazione di riga e colonna in Microsoft Excel (#3568) incluso:
 * Supporto per range di nomi definiti in Excel per identificare le celle d'intestazione (compatibile con loscreen reader Jaws)
 * I comandi imposta l'intestazione di colonna (NVDA+shift+c) e imposta l'intestazione di riga (NVDA+shift+r) ora salvano le impostazioni nel foglio di lavoro in modo da essere disponibili la prossima volta che il foglio viene aperto, e saranno a disposizione degli screen reader che supportano lo schema di range nomi definiti.
 * Questi comandi possono venir utilizzati più volte in un foglio per impostare diverse intestazioni per regioni differenti.
* Supporto per la lettura automatica dell'intestazione di riga e colonna in Microsoft Word (#3110) incluso:
 * Supporto dei segnalibri di MS Word per identificare le celle d'intestazione (compatibile con lo screen reader Jaws)
 -  I comandi imposta l'intestazione di colonna (NVDA+shift+c) e imposta l'intestazione di riga (NVDA+shift+r) quando ci si trova sulla prima cella d'intestazione in una tabella, permettono di dire a NVDA che le intestazioni vanno lette automaticamente. Le impostazioni sono salvate nel documento in modo da essere disponibili alla prossima apertura e sono disponibili per gli screen reader che supportano lo schema dei segnalibri.
* Microsoft Word: Notifica la distanza dall'angolo sinistro della pagina quando viene premuto il tasto tab. (#1353)
* Microsoft Word: fornito riscontro in voce e in braille per la maggior parte dei comandi rapidi di formattazione disponibili  (grassetto, corsivo, sottolineato, allineamento livello di rientro). (#1353)
* Microsoft Excel: se la cella selezionata contiene commenti, ora possono essere letti prmendo  NVDA+alt+c (#2920)
* Microsoft Excel: prevista una finestra di dialogo specifica di NVDA per editare i commenti nella cella selezionata corrente quando si preme il comando di Excel shift+f2 per accedere alla modalità editazione commento. (#2920)
* Microsoft Excel: Riscontro in voce e in Braille di molti altri comandi rapidi di spostamento e selezione (#4211) incluso:
 * Spostamento di pagina verticale (pagina su e pagina giù)
 * Spostamento di pagina orizzontale (alt+pagina su e alt+pagina giù)
 * Selezione estesa (i tasti precedenti più l'aggiunta del tasto Shift).
 * Selezionare la regione corrente  (control+shift+8)
* Microsoft Excel: l'allineamento verticale e orizzontale delle celle ora può essere riportato con il comando di formattazione del report (NVDA+f). Può anche essere segnalato automaticamente se l'opzione Allineamento report nelle impostazioni di formattazione del documento è abilitata. (#4212)
* Microsoft Excel: ora è possibile riportare lo stile di una cella con il comando di formattazione del report (NVDA+f). Può anche essere segnalato automaticamente se l'opzione Stile report nelle impostazioni di formattazione del documento è abilitata. (#4213)
* Microsoft PowerPoint: quando si spostano le forme all'interno di una diapositiva con i tasti freccia, viene ora segnalata la posizione corrente della forma (#4214), incluso:
 * Viene segnalata la distanza tra la forma e ciascuno dei bordi della diapositiva.
 * Se la sagoma copre o è coperta da un'altra sagoma, allora vengono riportate la distanza sovrapposta e la sagoma sovrapposta.
 * Per segnalare queste informazioni in qualsiasi momento senza spostare una forma, premere il comando segnala posizione (NVDA+cancella).
 * Quando si seleziona una forma, se questa è coperta da un'altra forma, NVDA segnalerà che è oscurata.
* Il comando di ubicazione del report (NVDA+cancella) è più specifico del contesto in alcune situazioni. (#4219)
 * Nei campi di modifica standard e nella modalità navigazione, vengono riportate la posizione del cursore come percentuale nel contenuto e le sue coordinate sullo schermo.
 * Nelle forme nelle presentazioni PowerPoint viene segnalata la posizione della forma rispetto alla diapositiva e alle altre forme.
 * Premendo questo comando due volte si produrrà il comportamento precedente di riportare le informazioni sulla posizione per l'intero controllo.
* Nuova lingua: catalano.

### Cambiamenti

* Aggiornato liblouis braille translator alla versione 2.5.4. (#4103)

### Bug Fixes

* In Google Chrome e Chrome-based browsers, alcune porzioni di testo (come quelle enfatizzate) non vengono più ripetute quando viene letto il testo di un avviso o di una finestra di dialogo. (#4066)
* Nella modalità navigazione nelle applicazioni di Mozilla, premendo invio su un pulsante, etc. non fallisce più la sua attivazione (o che si attivi il controllo sbagliato) in certi casi come i bottoni all'inizio di Facebook. (#4106)
* Non vengono più riportate le informazioni inutili quando si preme tab in iTunes. (#4128)
* In alcune liste in iTunes, come la lista Musica, spostarsi all'elemento successivo tramite il navigatore ad oggetti ora funzionacorrettamente. (#4129)
* Gli elementi HTML considerati intestazioni inquanto marcatori di tipo WAI ARIA ora vengono inclusi nella lista elementi della modalità navigazione e nella navigazione rapida nel documento di internet explorer. (#4140)
* Nelle recenti versioni di Internet Explorer, seguendo i links nella stessa pagina, si viene spostati correttamente nella giusta posizione che viene letta nella modalità navigazione documenti. (#4134)
* Microsoft Outlook 2010 e superiori: miglioramenti nell'accesso a tutte le finestre di dialogo sicure come i nuovi profili o le impostazioni mail. (#4090, #4091, #4095)
* Microsoft Outlook: diminuita l'inutile verbosità dei comandi della barra degli strumenti quando si naviga in alcune finestre di dialogo. (#4096, #3407)
* Microsoft word: Quando si giunge con il tab in una cella vuota di una tabella, non viene più annunciato "uscita da tabella". (#4151)
* Microsoft Word: il primo carattere dopo la fine di una tabella (inclusa una nuova riga vuota) non è più considerato erroneamente parte della tabella. (#4152)
* Microsoft Word 2010 finestra di dialogo del controllo ortografico: viene letta la reale parola errata piuttosto che in modo inappropriato la prima parola in grassetto. (#3431)
* Nel modo navigazione in Internet Explorer e in altri controlli MSHTML, usando tab o le lettere singole di navigazione per spostarsi sui controlli modulo, verrà riletta  l'etichetta in molti casi nei quali non veniva fatto (in particolar modo dove vengono impiegati gli elementi di tipo etichetta html). (#4170)
* Microsoft Word: la notifica dell'esistenza di commenti e del loro posizionamento, ora è più accurata. (#3528)
* migliorata la navigazione di alcune finestre di dialogo in prodotti MS Office come Word, Excel e Outlook non riportando particolari barre degli strumenti contenitore di controlli poco utili per gli utenti. (#4198)
* i riquadri attività come il clipboard manager o recupero File non ricevono più accidentalmente il fuoco quando si apre un'applicazione come Microsoft Word o Excel, che in qualche caso obbligavano l'utente a lasciare e riprendere l'applicazione per poter usare il documento o il foglio di calcolo. (#4199)
* NVDA non fallisce più nell'avvio nei recenti sistemi operativi Windows se la lingua utente del sistema è impostata su Serba (Latin). (#4203)
* Premendo il tasto numlock mentre ci si trova in modalità di aiuto all'immissione ora si attiva/disattiva correttamente il numlock, invece di causare la non sincronizzazione della tastiera e del sistema operativo rispetto allo stato di questo tasto. (#4226)
* In Google Chrome, il titolo del documento viene nuovamente riportato quando si passa da una scheda all'altra. Nella NVDA 2014.2 ciò in alcuni casi non si verificava. (#4222)
* In Google Chrome e nei browser basati su Chrome, l'URL del documento non viene più riportato quando si segnala il documento. (#4223)
* Quando si esegue dire tutto con il sintetizzatore vocale No selezionato (utile per i test automatizzati), dire tutto verrà ora completato invece di fermarsi dopo le prime righe. (#4225)
* Finestra di dialogo Firma di Microsoft Outlook: il campo di modifica della firma è ora accessibile, consentendo il tracciamento completo del cursore e il rilevamento del formato. (#3833)
* Microsoft Word: quando si legge l'ultima riga di una cella di tabella, non viene più letta l'intera cella della tabella. (#3421)
* Microsoft Word: quando si legge la prima o l'ultima riga di un sommario, non viene più letto l'intero sommario. (#3421)
* Quando si pronunciano parole digitate e in alcuni altri casi, le parole non vengono più interrotte erroneamente in corrispondenza di segni come i segni vocalici e i virama nelle lingue indiane. (#4254)
* I campi di testo numerici modificabili in GoldWave ora vengono gestiti correttamente. (#670)
* Microsoft Word: quando ci si sposta per paragrafo con control+freccia giù / control+freccia su, non è più necessario premerli due volte se ci si sposta negli elenchi puntati o numerati. (#3290)

### Cambiamenti per gli sviluppatori

* NVDA ha unito  ora il supporto per la documentazione sugli add-on. Consultare la sezione sulla documentazione sugli add-on della guida per sviluppatori per maggiori dettagli. (#2694)
* Quando si forniscono associazioni di gesti su uno ScriptableObject tramite __gestures, ora è possibile fornire la parola chiave None come script. Ciò scioglie il gesto in qualsiasi classe base. (#4240)
* Ora è possibile modificare il tasto di scelta rapida utilizzato per avviare NVDA per le versioni locali in cui la normale scorciatoia causa problemi. (#2209)
 * Questo viene fatto tramite gettext.
 * Tieni presente che anche il testo dell'opzione Crea collegamento sul desktop nella finestra di dialogo Installa NVDA, nonché il tasto di scelta rapida nella Guida per l'utente, devono essere aggiornati.

## 2014.2

### Novità

* è adesso possibile ascoltare la selezione del testo in alcuni campi editazione personalizzati, dove viene ancora utilizzata la modalità di prelevare informazioni dallo schermo. (#770)
* Nelle applicazioni Java accessibili, ora vengono annunciate le informazioni sulla posizione di pulsanti radio e altri controlli che espongono queste informazioni in gruppo. (#3854)
* Nelle applicazioni Java accessibili, ora vengono lette le scorciatoie da tastiera per i controlli che ne fanno uso. (#3881)
* In modalità navigazione, vengono annunciate le etichette nelle sezioni. Questi elementi sono anche presenti nella finestra che si ottiene premendo NVDA+f7. (#1195)
* In modalità navigazione, le regioni etichettate vengono ora trattate come sezioni. #3741)
* Nei documenti e nelle applicazioni facenti uso di Internet Explorer, vengono ora supportate le live region Aria definite dal W3c, il che permette ai webmaster di marcare quei contenuti che necessitano di essere letti non appena cambiano. (#1846)

### Cambiamenti

* Quando si esce da una finestra di dialogo o da un'applicazione che utilizza la modalità navigazione, NVDA non annuncia più il nome del programma e la dicitura "modalità navigazione". (#4069)

### Bug corretti

* il menu di sistema standard che si ottiene con la combinazione alt+spazio non viene più accidentalmente silenziato nelle applicazioni java. (#3882)
* Durante la copia del testo dalla modalità di controllo, non verranno più ignorate le interruzioni di riga. (#3900)
* Non vengono più annunciati oggetti formati solo da spazi vuoti o bianchi in alcune applicazioni durante il cambiamento del focus. (#3839)
* Sistemato un bug che impediva la gestione corretta della sintesi vocale all'apertura improvvisa di finestre di dialogo di NVDA.
* In modalità navigazione, le etichette di controlli quali link e bottoni vengono ora gestite correttamente laddove l'etichetta è stata sovrascritta dall'autore, con lo scopo di aumentarne l'accessibilità. (#1354)
* In modalità navigazione in Internet Explorer, il testo contenuto in un elemento marcato con l'attributo (ARIA role="presentation"), non verrà più ignorato erroneamente.
* è di nuovo possibile utilizzare il software Unikey per scrivere nella lingua Vietnamita. (#4043)
* In modalità navigazione, gli elementi di menu come pulsanti radio o caselle di controllo vengono riportati come controlli, non come semplice testo cliccabile. (#4092)
* NVDA non passa più erroneamente dalla modalità focus alla modalità navigazione quando viene evidenziato un elemento di menu come un pulsante radio o una casella di controllo. (#4092)
* In microsoft Powerpoint, se è attiva la lettura parola per parola, i caratteri eliminati con il Backspace non vengono più annunciati come parte della parola appena scritta. (#3231)
* Nella finestra di dialogo Opzioni di Microsoft Office 2010, vengono annunciate correttamente le etichette delle caselle combinate. (#4056)
* In modalità navigazione nelle applicazioni Mozilla, l'uso dei comandi rapidi per spostarsi tra bottoni o form ora include anche i pulsanti toggle. (#4098)
* Gli avvisi in Firefox e nelle applicazioni Mozilla non vengono più letti due volte di seguito. (#3481)
* In modalità navigazione, il contenuto delle sezioni e dei contenitori non viene letto più volte quando si naviga all'interno di questi elementi. (#3825)
* NVDA risulta più reattivo quando si cerca di interagire con applicazioni che hanno smesso di rispondere. (#3825)
* Risolto un bug che non permetteva l'inseguimento del cursore in modalità dire tutto, nei controlli non standard disegnati a schermo. (#4125)

## 2014.1

### Novità

* Supporto per Microsoft Powerpoint 2013. Si noti che la visualizzazione protetta non è supportata. (#3578)
* In Microsoft Word ed Excel, NVDA può ora leggere il simbolo selezionato nella scelta dei simboli utilizzando la finestra di dialogo Inserisci simboli. (#3538)
* è ora possibile stabilire se il contenuto nei documenti debba essere identificato come cliccabile, attraverso una nuova opzione nelle impostazioni formattazione documento. Da impostazioni predefinite il valore è attivo, come da comportamento precedente. (#3556)
* Supporto per i display braille collegati via Bluetooth su un computer che esegue il software Bluetooth Widcomm. (#2418)
* Quando si modifica del testo in Powerpoint, vengono segnalati eventuali collegamenti ipertestuali. (#3416)
* Nelle applicazioni aria o finestre di dialogo web, è ora possibile forzare NVDA ad utilizzare la modalità navigazione con NVDA+spazio permettendo l'esplorazione dell'applicazione o della finestra di dialogo come se si trattasse di un documento web. (#2023)
* In Outlook Express / Windows Mail / Windows Live Mail, ora NVDA è in grado di stabilire se un messaggio contiene un allegato o è stato contrassegnato. (#1594)
* Durante l'esplorazione delle tabelle nelle applicazioni Java accessibili, ora vengono annunciate le coordinate di riga e colonna, comprese le loro intestazioni se presenti. (#3756)

### Cambiamenti

* Per i display braille Papenmeier, sono stati rimossi i comandi di spostamento al cursore di controllo/focus. Gli utenti potranno definire i propri tasti preferiti nella finestra gesti e tasti di immissione. (#3652)
* NVDA ora si basa su Microsoft VC runtime versione 11, il che significa che non può più essere eseguito su sistemi operativi precedenti a Windows XP Service Pack 2 o Windows Server 2003 Service Pack 1.
* Se il livello di punteggiatura è impostato su qualcosa, verranno annunciati i caratteri asterisco (*) e più (+) (#3614)
* Aggiornata eSpeak alla versione 1.48.03 che include numerose correzioni linguistiche e sistema diversi crash. (#3842, #3739)

### Bug corretti

* Quando ci si sposta o si selezionano le celle in Microsoft Excel, NVDA non dovrebbe più impropriamente annunciare la vecchia cella piuttosto che la nuova cella quando Microsoft Excel è lento nello spostare la selezione. (#3558)
* NVDA gestisce correttamente l'apertura di un elenco a discesa per una cella in Microsoft Excel tramite il menu contestuale. (#3586)
* In Itunes 11, vengono gestite correttamente le pagine dello store con nuovi contenuti in modalità navigazione quando si segue il link allo store. (#3625)
* In Itunes11, i pulsanti usati per l'anteprima dei brani visualizzano correttamente la loro etichetta in modalità navigazione. (#3638)
* In modalità navigazione in Google Chrome, le etichette delle caselle di controllo e dei pulsanti radio sono ora visualizzate correttamente. (#1562)
* In Instantbird, NVDA non segnala più informazioni inutili ogni volta che si passa a un contatto nell'elenco contatti. (#2667)
* In modalità navigazione in Adobe Reader, viene elaborato correttamente il testo in quei pulsanti nei quali l'etichetta è stata resa invisibile da qualche fumetto d'aiuto o simili. (#3640)
* In modalità navigazione in Adobe Reader, non verranno più annunciati grafici contenente il testo "mc-ref". (#3645)
* NVDA non segnala più tutte le celle in Microsoft Excel come sottolineate nelle informazioni di formattazione. (#3669)
* Migliorata la visualizzazione di documenti unicode in modalità navigazione. (#2963).
* Ora in Putty è possibile immettere correttamente caratteri dell'Asia dell'est. (#3432)
* Mentre si esplora un documento e si termina la modalità dire tutto, NVDA non annuncerà più che si è abbandonato un elemento del documento (ad esempio un campo in una tabella) che la modalità dire tutto non aveva ancora raggiunto. (#3688)
* Quando si utilizzano i comandi rapidi di esplorazione in un documento web con la funzione dire tutto, e con lettura veloce attiva, NVDA annuncia in maniera più accurata un nuovo campo. (#3689)
* I comandi di lettura veloce durante la modalità dire tutto funzionano correttamente anche durante lo spostamento nei contenitori. (#3675)
* Tutti i nomi dei principali gesti che si trovano nella finestra tasti e gesti di immissione sono stati tradotti nelle varie lingue. (#3624)
* NVDA non causa più il crash di alcuni programmi quando il mouse veniva posizionato nei controlli richedit (TRichEdit). I programmi comprendono Jarte 5.1 e BRfácil. (#3693, #3603, #3581)
* In Internet Explorer e altri controlli MSHTML, contenitori come le tabelle contrassegnati come presentazione ARIA non sono annunciati agli utenti. (#3713)
* In Microsoft Word, NVDA non ripete più per svariate volte le informazioni riga/colonna di una cella. (#3702)
* In quelle lingue che utilizzano uno spazio come separatore di cifre per le migliaia come francese e tedesco, i numeri contenenti più blocchi di testo non vengono più letti come un singolo numero. Questo risultava molto problematico con le celle contenenti numeri. (#3698)
* Risolto un problema che non permetteva al braille di aggiornare correttamente la propria posizione al movimento del cursore in Word2013. (#3784)
* Quando ci si posiziona sul primo carattere di un'intestazione in Microsoft Word, il testo che fa capire che si tratta di un'intestazione (ad esempio intestazione di livello 1) non scompare più dai display braille. (#3701)
* Quando un profilo di configurazione viene associato ad un'applicazione e quell'applicazione termina la sua esecuzione, NVDA non fallisce più nel disattivare quel profilo. (#3732)
* Quando vengono inseriti caratteri con il metodo di immissione asiatico nei controlli che fanno parte di NVDA (come la finestra trova in un browser), viene letto correttamente il carattere candidato invece che la parola NVDA. (#3726)
* Vengono ora annunciate correttamente le schede nella finestra di opzioni di Outlook 2013. (#3826)
* Migliorato il supporto alle regioni Aria in Firefox e ad altre applicazioni Mozilla:
 * Supporto per gli aggiornamenti  ad aria-atomic e filtraggio degli aggiornamenti di aria-busy (#2640)
 * Viene annunciato il testo alternativo (ad esempio l'attributo alt o aria-label) se non c'è altro testo utile. (#3329)
 * Se il focus viene spostato e contemporaneamente viene aggiornato un controllo live-region, quest'ultimo sarà annunciato ugualmente. (#3777)
* Alcuni elementi di presentazione di Firefox e altre applicazioni Mozilla Gecko non vengono più impropriamente mostrati in modalità navigazione. (#3781)
* Miglioramento delle prestazioni durante l'esplorazione di un documento di Microsoft Word con il controllo degli errori di ortografia abilitato. (#3785)
* Diverse correzioni al supporto per le applicazioni Java accessibili:
 * Non vi sono più problemi nell'annunciare il controllo iniziale su cui si trova il focus, all'interno di un frame o di una finestra di dialogo che torna in primo piano. (#3753)
 * Non vengono più riportate informazioni inutili riguardo i pulsanti radio, ad esempio  1 di 1. (#3754)
 * Gestione migliorata dei controlli JComboBox, (html non più annunciato), sistemato anche il rilevamento dello stato espanso/non espanso. (#3755)
 * Migliorata la lettura di tutto il testo di una finestra di dialogo, in precedenza poteva accadere che alcuni elementi fossero omessi. (#3757)
 * Vengono annunciate in maniera più corretta le modifiche al nome, alla descrizione o al valore del controllo su cui si trova il focus. (#3770)
* Risolto un problema che causava il crash di NVDA in Windows8 in concomitanza con controlli contenenti grosse porzioni di testo, come il visualizzatore log di NVDA. (#3867)
* Nei sistemi con le impostazioni del display settate ad un numero molto alto di DPI, (ossia quasi tutti i pc più moderni), NVDA non ha più problemi nel portare il mouse nella posizione desiderata. (#3758, #3703)
* Sistemato un fastidioso problema che occasionalmente, provocava l'arresto di NVDA durante la navigazione, inibendone però il riavvio. (#3804)
* Ora è possibile utilizzare un display Braille Papenmeier anche se non è mai stato collegato un display Papenmeier tramite USB. (#3712)
* NVDA non va più in crash quando si seleziona un vecchio modello di barra braille Braillex Papenmeier senza che quest'ultima sia connessa.

### Cambiamenti per sviluppatori in inglese

* AppModules now contain productName and productVersion properties. This info is also now included in Developer Info (NVDA+f1). (#1625)
* In the Python Console, you can now press the tab key to complete the current identifier. (#433)
 * If there are multiple possibilities, you can press tab a second time to choose from a list.

## 2013.3

### Novità

* Nei documenti Microsoft Word vengono ora annunciati i campi dei form (#2295)
* Nvda è ora in grado di annunciare le informazioni di revisione in Microsoft Word quando tieni traccia delle modifiche è attivo. Si noti che affinché tali informazioni siano lette, è necessario abilitare anche l'opzione leggi revisioni (disattivata di default) nella finestra di dialogo impostazioni documento di NVDA (#1670)
* Vengono gestiti correttamente gli elenchi a tendina a partire da Microsoft Excel 2003 fino al 2010, sia nell'apertura che nell'esplorazione (#3382)
* Nelle impostazioni tastiera è stata aggiunta una nuova opzione chiamata 'consenti lettura veloce in modalità dire tutto', che permette l'esplorazione di un documento in modalità navigazione tramite i comandi rapidi di navigazione e movimento in lettura per righe / paragrafi, mentre si rimane in modalità dire tutto. Questa opzione è disattivata di default. (#2766)
* è stata introdotta la voce 'gesti e tasti di immissione' per permettere una personalizzazione facilitata dei tasti rapidi o dei gesti (come la pressione di un tasto sulla tastiera) per i comandi di NVDA. (#1532)
* Ora si possono avere, grazie ai profili, configurazioni diverse a seconda della situazione in cui ci si trova. I profili possono essere attivati manualmente, oppure in concomitanza di un determinato evento (per esempio un'applicazione specifica) (#87, #667, #1913)
* In Microsoft Excel, le celle che contengono collegamenti vengono ora annunciate correttamente come link. (#3072)
* In Microsoft Excel, viene annunciata all'utente l'esistenza di un commento in una cella. (#2921)

### Bug corretti

* Zend studio ora funziona allo stesso modo di Eclipse. (#3420)
* Viene annunciato correttamente il cambiamento di stato di alcune caselle di controllo nella finestra di dialogo regole in Outlook 2010. (#3063)
* NVDA annuncia lo stato 'bloccato' per alcuni controlli presenti in Firefox. (#3372)
* è ora possibile associare script a combinazioni di tasti che contengano anche alt o il tasto Windows.  In precedenza, se ad esempio veniva premuto il tasto alt in uno script, ciò avrebbe causato l'apertura di un menu. (#3472)
* La selezione del testo per i documenti in modalità navigazione (ad esempio con ctrl+shift+fine) non provoca più il cambio layout tastiera nei sistemi dove ve n'era installato più d'uno. (#3472)
* Internet Explorer non provocherà più errori alla chiusura di NVDA. (#3397)
* In alcuni computer molto nuovi, i movimenti fisici ed altri eventi non vengono più considerati come se si trattasse di pressioni di tasti. Talvolta infatti questo errato comportamento portava allo zittimento della sintesi vocale. (#3468)
* NVDA si comporta correttamente in Poedit 1.5.7. Se vi sono utenti che utilizzano versioni meno recenti dovrebbero aggiornare. (#3485)
* NVDA è in grado di leggere documenti protetti in Microsoft Word 2010, senza che quest'ultimo vada in crash. (#1686)
* Se il pacchetto d'installazione di NVDA viene eseguito con un parametro sconosciuto dalla riga di comando, NVDA non andrà più in un loop senza fine. (#3463)
* NVDA non commette più errori nell'annunciare testo alternativo o grafici e oggetti in Microsoft Word se l'attributo alt Text contiene virgolette o caratteri non standard. (#3579)
* è stato corretto il calcolo del numero di elementi negli elenchi orizzontali nella modalità navigazione. (#2151)
* Quando si preme ctrl+a in un foglio di lavoro in Microsoft Excel, viene letta correttamente la selezione aggiornata. (#3043)
* NVDA ora è in grado di leggere correttamente documenti XHTML in Microsoft Internet Explorer e altri controlli MSHTML. (#3542)
* Finestra di dialogo Impostazioni tastiera: Se non viene selezionato alcun tasto che agisca come tasto NVDA, potrebbe risultare impossibile accedere ad alcuni comandi dello screen reader. Pertanto, verrà visualizzato un messaggio d'errore nell'eventualità tutti i tasti siano deselezionati.
* In Microsoft Excel, NVDA ora distingue correttamente tra l'unione di celle e selezione di celle multiple. (#3567)
* Il cursore in modalità navigazione non viene più posizionato in maniera errata all'uscita da una finestra di dialogo o da un'applicazione interna del documento. (#3145)
* Sistemato un problema che non faceva apparire il display braille HumanWare Brailliant BI/B series nell'elenco delle barre disponibili, sebbene esso fosse correttamente connesso.
* NVDA non fallisce più nel passare alla revisione dello schermo quando l'oggetto del navigatore non ha una posizione effettiva sullo schermo. In questo caso il cursore di revisione è ora posizionato nella parte superiore dello schermo. (#3454)
* Risolto un problema che causava il fallimento del driver del display braille di Freedom Scientific quando la porta era impostata su USB in alcune circostanze. (#3509, #3662)
* Risolto un problema per cui in alcune circostanze i tasti sui display braille di Freedom Scientific non venivano rilevati. (#3401, #3662)

### Cambiamenti per sviluppatori(in inglese)

* You can specify the category to be displayed to the user for scripts using the scriptCategory attribute on ScriptableObject classes and the category attribute on script methods. See the documentation for baseObject.ScriptableObject for more details. (#1532)
* config.save is deprecated and may be removed in a future release. Use config.conf.save instead. (#667)
* config.validateConfig is deprecated and may be removed in a future release. Add-ons which need this should provide their own implementation. (#667, #3632)

## 2013.2

### Novità

* Supporto al Framework Chromium, un tipo di controllo browser web utilizzato in svariate applicazioni. (#3108)
* Nuova variante voce eSpeak: Iven3.
* In Skype, i nuovi messaggi di chat vengono annunciati automaticamente durante la conversazione focalizzata. (# 2298)
* Supporto per Tween, compresa la segnalazione dei nomi delle schede e meno verbosità durante la lettura dei tweet.
* È ora possibile disabilitare la visualizzazione di messaggi di NVDA su un display braille impostando il timeout messaggi a 0 nella finestra di dialogo Impostazioni Braille. (# 2482)
* Nel Gestore componenti aggiuntivi, ora c'è un pulsante chiamato Preleva ulteriori componenti aggiuntivi  che aprirà il sito web dedicato da dove sarà possibile navigare e scaricare ulteriori script. (# 3209)
* Nella finestra di dialogo  di benvenuto di NVDA che  appare sempre la prima volta che si esegue lo screen reader, sarà ora possibile specificare se NVDA debba avviarsi automaticamente dopo l'accesso a Windows. (# 2234)
* La modalità riposo viene attivata di default ogni qualvolta si esegue Dolphin Cicero. (#2055)
* Viene ora supportata la versione a 64 bit di Miranda Im. (#3296)
* Vengono annunciati automaticamente i suggerimenti nella schermata di Ricerca in Windows8. (#3322)
* Supporto per la navigazione e la modifica di fogli di calcolo in Microsoft Excel 2013. (#3360)
* Supporto migliorato per i display braille di Freedom Scientific Focus14 Blue e Focus 80 Blue, oltre che per la Focus40 Blue, in modalità Bluetooth. (#3307)
* I suggerimenti di completamento automatico vengono ora riportati in Outlook 2010 . (#2816)
* Nuove tabelle di traduzione Braille: English (UK) Computer Braille , coreano grado2, russo computer braille.
* Nuova lingua: Farsi. (#1427)

### Cambiamenti

* L'azione di scorrimento a destra o a sinistra con un dito quando si opera in modalità oggetti ora permette di spostarsi tra di essi nella modalità in linea, seguendone la gerarchia degli stessi. Utilizzare lo scorrimento con due dita a destra o sinistra per spostarsi avanti e indietro tra gli oggetti nello stesso livello gerarchico.
* La casella di controllo "Annuncia tabelle di layout", situata nelle impostazioni modalità navigazione, è stata migliorata in modo da escludere tali tabelle quando si usano i comandi di navigazione veloce, se la casella di controllo è disattivata. (#3140)
* La navigazione in linea è stata sostituita con tre tipi di modalità: ad oggetti, documento e a schermo.  (#2996)
 * La navigazione ad oggetti permette di esplorare il testo all'interno del navigatore ad oggetti, la navigazione documento consente di esplorare il testo in un documento in modalità navigazione (ad esempio una pagina web), mentre la modalità a schermo permette di controllare il testo presente in un'applicazione.
 * I comandi che in precedenza consentivano di spostarsi o attivare la modalità in linea adesso permettono di passare tra queste tre nuove modalità.
 * Il navigatore ad oggetti segue automaticamente il cursore di controllo in modo che  alla posizione di quel cursore coincida sempre l'oggetto principale in modalità documento o schermo.
 * Una volta che si è passati in modalità a schermo, NVDA rimarrà in tale modalità fino a quando non si cambierà tipo di navigazione.
 * NVDA inoltre potrebbe attivare automaticamente la modalità più appropriata quando ci si trova in navigazione ad oggetti o documento.
* Liblouis Braille aggiornato alla versione 2.5.3. (#3371)

### Bug corretti

* L'attivazione di un oggetto ora fa sì che venga annunciata prima l'azione rispetto all'attivazione stessa, (in sostanza in una visualizzazione ad albero, se si preme nvda+invio per espandere un ramo verrà annunciato espanso, non chiuso). (#2982)
* Migliorata sensibilmente l'interazione con i campi d'immissione in Skype, quali chat o campi di ricerca. (#1601, #3036)
* Nell'elenco delle conversazioni recenti di Skype, viene letto per ciascuna conversazione il numero di eventi, se rilevante. (#1446)
* Migliorati sensibilmente inseguimento del cursore e lettura nei testi RTL, ad esempio modifica di fogli Excel in lingua araba. (#1601)
* I comandi di navigazione veloce per bottoni e campi di form ora sono in grado di individuare collegamenti contrassegnati come pulsanti per motivi di accessibilità in Internet Explorer. (#2750)
* In modalità navigazione, non viene più interpretato il contenuto all'interno di visualizzazioni ad albero. Per interagire con esse, premere invio in modalità focus. (#3023)
* La pressione dei tasti alt-freccia giù o alt-freccia su in una casella combinata non causerà più erroneamente l'attivazione della modalità navigazione, quando ci si trovava in modalità focus. (#2340)
* In Internet Explorer 10, le celle di una tabella non attiveranno più la modalità focus, a meno che l'autore della pagina web non le abbia esplicitamente dichiarate come focalizzabili. (#3248)
* NVDA non si rifiuterà più di avviarsi se l'ora di sistema risulta precedente all'ultimo controllo fatto per la verifica di aggiornamenti. (#3260)
* Se in un display braille viene visualizzata una barra di avanzamento, la barra braille viene aggiornata man mano che la barra di avanzamento cambia i valori. (#3258)
* In modalità navigazione nelle applicazioni Mozilla, le didascalie delle tabelle non vengono più presentate due volte. (#3196)
* Quando in Windows8 viene modificata la lingua di immissione, NVDA parlerà nella lingua corretta, non con la precedente.
* NVDA ora annuncia i cambiamenti della modalità di conversione IME in Windows 8.
* NVDA non annuncia più caratteri incomprensibili sul desktop se viene utilizzato Google in versione giapponese oppure il metodo di immissione Atok.
* In Windows7 e successivi, NVDA non annuncia più erroneamente riconoscimento vocale o immissione a tocco come una modifica della lingua di tastiera.
* NVDA non annuncia più il carattere speciale (0x7F) premendo Ctrl + backspace in alcuni editor, quando l'opzione leggi i caratteri digitati è attiva. (#3315)
* Espeak non emette più cambiamenti di tono, volume, etc, quando NVDA legge caratteri di controllo o xml. (#3334) (regressione di #437)
* Nelle applicazioni Java, le modifiche all'etichetta o al valore del controllo focalizzato ora vengono annunciate automaticamente. (#3119)
* Nei controlli Scintilla, le righe vengono annunciate correttamente quando è attiva la formattazione automatica. (#885)
* Nelle applicazioni Mozilla, il nome delle voci di sola lettura  in un elenco è ora riportato correttamente: ad esempio durante la navigazione tweet in modalità focus su twitter.com. (#3327)
* Le finestre di conferma in Office2013 vengono lette automaticamente.
* Migliorate le prestazioni durante la navigazione nelle tabelle in Microsoft Word. (#3326)
* Sistemato il funzionamento del comando CTRL+alt+frecce nell'esplorazione tabelle in alcune circostanze.
* Se il gestore componenti aggiuntivi risulta già aperto, un tentativo di aprirlo una seconda volta non produce più errori. (#3351)
* NVDA non si blocca più nel caso in cui si utilizzi Office 2010/2013 con il metodo di immissione cinese o giapponese. (#3064)
* Nei display braille, più spazi non vengono più compressi in uno solo. (#1366)
* Eclipse Zend PHP Developer Tools adesso funziona come Eclipse. (#3353)
* In Internet Explorer, non è più necessario premere tab per interagire con un oggetto incorporato (ad esempio un contenuto Flash) dopo aver premuto il tasto Invio su di esso. ( # 3364)
* Durante la modifica di un testo in Powerpoint, l'ultima riga non viene più considerata per errore uguale alla penultima, se la riga finale è vuota. (#3403)
* In microsoft Powerpoint, gli oggetti non sono più annunciati due volte se selezionati. (#3394)
* NVDA non provoca più il crash di Adobe Reader in presenza di documenti mal strutturati, con righe di tabelle al di fuori di esse. (#3399)
* NVDA ora intercetta correttamente ladiapositiva successiva focalizzata quando ne viene eliminata una in visualizzazione anteprima. (#3415)

### Cambiamenti per sviluppatori in inglese

* windowUtils.findDescendantWindow has been added to search for a descendant window (HWND) matching the specified visibility, control ID and/or class name.
* The remote Python console no longer times out after 10 seconds while waiting for input. (#3126)
* Inclusion of the bisect module in binary builds is deprecated and may be removed in a future release. (#3368)
 * Add-ons which depend on bisect (including the urllib2 module) should be updated to include this module.

## 2013.1.1

Questa versione risolve il problema per cui NVDA si bloccava all'avvio se configurato per utilizzare la lingua irlandese, oltre a includere aggiornamenti alle traduzioni e alcune altre correzioni di bug.

### Bug corretti

* quando si utilizza un metodo di immissione coreano o giapponese ed esso è il metodo predefinito, vengono prodotti correttamente i caratteri quando si digita nella propria interfaccia utente di NVDA. (#2909)
* In Internet Explorer e altri controlli MSHTML, i campi contrassegnati come contenenti una voce non valida sono ora gestiti correttamente. (# 3256)
* NVDA non si blocca più all'avvio se è configurato per utilizzare la lingua irlandese.

## 2013.1

Le caratteristiche più importanti di questa versione comprendono un layout tastiera per i portatili più coerente e intuitivo; il supporto di base per Microsoft PowerPoint; la gestione degli attributi longdesc nei browser web e il supporto per l'immissione del Braille computer per i display braille che dispongono una tastiera braille.

### Importante

#### Nuovo layout tastiera laptop

Il layout per tastiere laptop è stato completamente rifatto per renderlo più semplice e intuitivo.
Il nuovo layout utilizza i tasti freccia in combinazione con il tasto NVDA e altri tasti funzione per i comandi di revisione.

Si consiglia di leggere con attenzione i cambiamenti per i comandi seguenti:

| Nome |Tasto|
|---|---|
|Dire tutto |NVDA+a|
|Leggere la riga corrente |NVDA+l|
|Leggere il testo selezionato |NVDA+shift+s|
|Annunciare il contenuto della barra di stato |NVDA+shift+fine|

In aggiunta, sono stati cambiati tutti i comandi inerenti la navigazione ad oggetti, la revisione del testo, il click del mouse e la possibilità di modificare al volo le impostazioni del sintetizzatore.
Si prega di consultare il documento [Comandi rapidi](keyCommands.html) per i nuovi tasti.

### Novità

* Supporto di base alla modifica e alla lettura delle presentazioni in Microsoft Powerpoint. (#501)
* Supporto alla lettura e scrittura dei messaggi in Lotus Notes 8.5. (#543)
* Supporto per il cambio automatico della lingua durante la lettura documenti in Microsoft Word. (#2047)
* In modalità navigazione MSHTML (ad esempio Internet Explorer) e Gecko (ad esempio Firefox), viene annunciata l'esistenza delle descrizioni degli elementi se esistente, tramite l'interpretazione dell'attributo longdesc. è anche possibile aprire la descrizione in una nuova finestra tramite nvda+d. (#809)
* Ora vengono annunciate le notifiche in Internet Explorer 9 e superiori, ad esempio download di file o contenuti bloccati. (#2343)
* Annuncio automatico delle intestazioni riga/colonna nelle tabelle per la modalità navigazione in Internet Explorer e altri controlli MSHTML. (#778)
* Nuove lingue: Aragonese, irlandese
* Nuove tabelle Braille: Danese grado 2, Coreano grado 1. (#2737)
* Supporto per i display Braille connessi tramite Bluetooth su computer che eseguono lo stack Bluetooth prodotto da Toshiba. (#2419)
* Supporto per la selezione della porta per i Display Braille Freedom Scientific (Automatica, Usb o Bluetooth).
* Supporto per i display Braille Braillenote della Humanware quando configurati per funzionare come periferica per screen reader. (#2012)
* Supporto ai vecchi modelli Papenmeier utilizzati tramite porta seriale. (#2679)
* Supporto alla scrittura diretta tramite display braille con tastiera in stile perkins. (#804)
* Nuove impostazioni della tastiera che consentono di selezionare se NVDA debba interrompere il parlato per i caratteri digitati e o il tasto ENTER. (#698)
* Supporto per diversi browser basati su Google Chrome: Rockmelt, BlackHawk, Comodo Dragon e SRWare Iron. (#2236, #2813, #2814, #2815)

### Cambiamenti

* Aggiornato liblouis Braille Translator alla versione 2.5.2. (#2737)
* Il layout tastiera laptop è stato completamente riprogettato in modo da renderlo più intuitivo e coerente. (#804)
* Aggiornata Espeak alla versione 1.47.11. (#2680, #3124, #3132, #3141, #3143, #3172)

### Bug Corretti

* Il tasto rapido per spostarsi di sezione in sezione ora funziona anche con Internet Explorer. (#2781)
* Se NVDA non riesce a caricare un sintetizzatore all'avvio ed è costretto a parlare tramite Espeak, la configurazione viene lasciata inalterata, il che significa che la prossima volta che si riavvierà NVDA, tenterà di caricare ancora il sintetizzatore scelto dall'utente in precedenza, anziché mantenere Espeak come predefinito. (#2589)
* Se NVDA torna a non utilizzare Braille a causa di un guasto del display braille configurato all'avvio di NVDA, il display configurato non viene più automaticamente impostato su non Braille. Ciò significa che al prossimo avvio di NVDA verrà riprovata la visualizzazione originale. traduzione con intelligenza artificiale orribile! (#2264)
* Nelle applicazioni Mozilla in modalità navigazione, vengono ora riportati correttamente gli aggiornamenti delle tabelle. Ad esempio, nelle celle aggiornate, vengono annunciate correttamente le coordinate delle colonne e delle righe. (#2684)
* Nei browser web in modalità navigazione, ora vengono intercettati anche elementi grafici cliccabili non etichettati che non venivano mostrati in precedenza. (#2838)
* Vengono supportate tutte le versioni  del programma SecureCRT. (#2800)
* Per i metodi di immissione asiatici come "Easy dots IME" in Windows Xp,  la stringa di lettura viene annunciata correttamente.
* L'elenco dei suggerimenti nel metodo di immissione cinese semplificato Microsoft Pinyin input method su Windows 7 viene ora letto correttamente  quando si cambia pagina con le frecce destra e sinistra, e quando viene aperto col tasto home..
* Quando viene salvata la pronuncia di un nuovo simbolo, il campo "preserve" non viene più rimosso.
* Quando il controllo aggiornamenti  viene disattivato, NVDA non necessita più di essere riavviato affinché le modifiche abbiano effetto.
* NVDA non ha più problemi nell'avviarsi nel caso in cui un componente aggiuntivo non possa essere rimosso in quanto la directory che lo contiene è in uso da un'altra applicazione. (#2860)
* Le etichette delle schede in Dropbox, ad esempio quelle nella finestra preferenze, possono ora essere raggiunte anche con la navigazione in linea.
* Se la lingua di immissione viene modificata in un valore diverso da quello predefinito, NVDA individua correttamente i tasti per l'aiuto immissione e per i comandi.
* Per le lingue come il tedesco in cui il (più) + è un tasto singolo  sulla tastiera, è ora possibile associare i comandi ad esso usando la parola "plus". (#2898)
* In Internet Explorer e altri controlli MSHTML, i blocchi tra virgolette vengono  ora annunciati correttamente nella posizione appropriata. (#2888)
* Il Display braille HumanWare Brailliant BI / B può ora essere selezionato quando il display è collegato tramite Bluetooth, ma non è mai stato collegato via USB.
* L'operazione di filtraggio degli elementi nell'elenco elementi della modalità navigazione è stata migliorata. (#2951)
* Quando si utilizza un browser Mozilla, può essere usata di nuovo la modalità navigazione in presenza di oggetti flash. (#2546)
* Quando si utilizza una tabella con braille contratto e l'opzione espandi la parola sotto al cursore è attiva, il cursore braille viene ora posizionato correttamente quando collocato dopo una parola laddove un carattere è rappresentato da celle braille multiple (ad esempio segno per maiuscole, lettere, numeri etc.). (#2947)
* La selezione del testo è ora visualizzata correttamente  sul display braille nei campi editazione di applicazioni come Microsoft Word 2003 e Internet Explorer.
* è di nuovo possibile selezionare il testo all'indietro in Microsoft Word quando il Braille è abilitato.
* Durante la revisione o la cancellazione del testo col tasto canc o backspace nei controlli scintilla, NVDA ora annuncia correttamente i caratteri multibyte. (#2855)
* NVDA non si rifiuterà più di installarsi quando il percorso del profilo utente contiene caratteri multibyte. (#2729)
* L'annuncio dei gruppi per i controlli visualizzazione ad elenco di tipo SysListview32) in applicazioni a 64 bit non causa più un errore.
* In modalità navigazione nelle applicazioni Mozilla, il contenuto del testo non è più considerato come modificabile in alcuni rari casi. (#2959)
* In IBM Lotus Symphony e Openoffice, lo spostamento del cursore di sistema provoca anche lo spostamento del cursore di controllo se necessario.
* I contenuti di tipo Adobe Flash sono ora accessibili in Internet Explorer in Windows 8. (#2454)
* Corretto il supporto Bluetooth per il display braille Trio della Papenmeier. (#2995)
* Sistemato un problema che non permetteva l'utilizzo di alcune sintesi vocali Sapi5 come Koba Speech. (#2629)
* Nelle applicazioni che utilizzano Java Access Bridge, ora il display braille viene aggiornato correttamente quando il cursore si sposta nei campi editazione. (#3107)
* In modalità navigazione, migliorato il supporto ai form che utilizzano le sezioni. (#2997)
* Migliorata in Espeak la lettura carattere per carattere. (#3106)
* NVDA ora è in grado di copiare la configurazione utente nella configurazione da usarsi per le schermate di logon, anche quando il percorso del profilo utente contiene caratteri non-ascii. (#3092)
* NVDA non si blocca più quando si utilizza l'immissione di caratteri asiatici in alcune applicazioni .NET. (#3005)
* ora è possibile utilizzare la modalità navigazione per le pagine in Internet Explorer 10 in modalità standard; per esempio. Pagina di accesso [www.gmail.com](http://www.gmail.com). (#3151)

### Cambiamenti per sviluppatori

* I driver dei display braille supportano la selezione manuale della porta. (#426)
 * Questo risulta molto utile per i display braille che supportano il collegamento tramite una porta seriale.
 * L'operazione viene effettuata utilizzando la classe getPossiblePorts sulla classe BrailleDisplayDriver.
* Viene supportata l'immissione tramite tastiera braille. (#808)
 * L'immissione braille è gestita dalla classe brailleInput.BrailleInputGesture o una sottoclasse della stessa.
 * Le sottoclassi braille.BrailleDisplayGesture (come implementate nei driver dei display braille) possono anche ereditare da brailleInput.BrailleInputGesture. Ciò permette la gestione dei comandi dei display braille e dell'immissione braille dalla stessa classe gesture.
* È ora possibile utilizzare comHelper.getActiveObject per ottenere un oggetto COM attivo da un processo normale quando NVDA è in esecuzione con privilegi uiAccess. (#2483)

## 2012.3

Le novità principali in questa versione sono costituite dal supporto all'immissione dei caratteri asiatici; supporto sperimentale ai dispositivi touch screen in Windows 8; l'annuncio dei numeri di pagina e un notevole miglioramento per le tabelle in Adobe Reader; il poter usare comandi di navigazione delle tabelle nelle finestre con visualizzazioni ad elenco; supporto per molti nuovi display braille; e la possibilità di annunciare le intestazioni di righe e colonne in Excel.

### Novità

* NVDA è ora in grado di supportare la modalità di immissione per i caratteri asiatici, usando la tecnologia IME e i servizi di testo resi disponibili nelle applicazioni, comprendenti:
 * Annuncio e navigazione tra l'elenco dei caratteri suggeriti
 * Annuncio e navigazione tra le stringhe di composizione
 * Annuncio delle stringhe di lettura.
* In Adobe Reader vengono ora individuati elementi come sottolineato e barrato. (#2410)
* Quando la funzione "tasti permanenti" in Windows è attiva, il tasto funzione di NVDA si comporterà come gli altri tasti funzione. Questo permette di poter usare il tasto funzione di NVDA senza doverlo tenere premuto mentre si premono altri tasti. (#230)
* è ora supportato l'annuncio automatico delle intestazioni di righe e colonne in Excel. Premere NVDA+shift+c per impostare la riga che contiene le intestazioni colonna e NVDA+shift+r per impostare la colonna che contiene le intestazioni riga. Premere gli stessi comandi due volte in rapida successione per rimuovere tali impostazioni. (#1519)
* Supporto per i display Braille della Hims BrailleSense, Braille Edge e SyncBraille. (#1266, #1267)
* Quando appare una notifica in Windows8, NVDA la annuncerà se l'opzione "leggi i fumetti d'aiuto" risulta attiva. (#2143)
* Supporto sperimentale per il touch screen in Windows8, comprendente:
 * Lettura del testo situato sotto le dita mentre ci si sposta
 * Gesti dedicati per effettuare la navigazione ad oggetti, la revisione del testo ed altri comandi di NVDA
* Supporto per Vip Mud. (#1728)
* In Adobe Reader, se una tabella ha un riassunto, esso viene letto correttamente.
* In Adobe Reader, possono essere annunciate le intestazioni di righe e colonne. (#2193, #2527, #2528)
* Nuove lingue: Amharic, Coreano, Nepalese, sloveno.
* NVDA è in grado di leggere i suggerimenti nell'autocompletamento quando si inserisce un indirizzo in Microsoft Outlook 2007. (#689)
* Nuove varianti di voce Espeak: Gene, Gene2. (#2512)
* In Adobe Reader, ora possono venir annunciati i numeri di pagina. (#2534)
 * In Reader XI, le etichette delle pagine vengono annunciate laddove presenti, in accordo con i cambiamenti dei numeri di pagina nelle diverse sezioni, etc. Nelle versioni precedenti, questo non risulta possibile e vengono annunciate solo le numerazioni di pagina sequenziali..
* è ora possibile ripristinare la configurazione di NVDA ai suoi valori di fabbrica sia premendo NVDA+control+r tre volte velocemente, oppure selezionando ripristina ai valori di fabbrica dal menu di NVDA.(#2086)
* Supporto per i Display Braille Seika Versione 3, 4 e 5 e Seika80 prodotti da Nippon Telesoft. (#2452)
* Il primo e l'ultimo pulsante superiore nel Pac Mate e nei Display Braille Focus di Freedom Scientific  può ora essere usato per scorrere in avanti e indietro. (#2556)
* Vengono implementate molte più funzioni con i tasti dei Display Braille della Freedom Scientific. (#2516)
* Nei programmi che fanno uso di IAccessible2 come le applicazioni Mozilla, le intestazioni delle righe e delle colonne possono essere annunciate al di fuori della modalità navigazione. (#926)
* Supporto iniziale al controllo documenti in Microsoft Word 2013. (#2543)
* Nelle applicazioni che fanno uso di Iaccessible2 come i programmi di Mozilla, può essere annunciato l'allineamento del testo. (#2612)
* Quando si incontra una riga di una tabella, o una visualizzazione ad elenco standard di Windows contenente molte colonne, si possono utilizzare i comandi di navigazione tabelle per esplorare il contenuto delle celle. (#828)
* Nuove tabelle di traduzione Braille: Estone Grado 0, Portoghese Braille Computer 8 punti, Italiano 6 punti. (#2139, #2662)
* Se NVDA è installato nel sistema, l'apertura diretta di un componente aggiuntivo (o da risorse del computer, oppure dal browser web dopo il download) lo installerà in NVDA. (#2306)
* Introdotto il supporto per i nuovi display braille Braillex Papenmeier. (#1265)
* Nelle visualizzazioni ad elenco come quelle presenti in risorse del computer in Windows7 o superiori, Vengono ora annunciate le informazioni sulla posizione (ad esempio 1 di 4). (#2643)

### Cambiamenti

* Nella finestra di dialogo preferenze/cursore di controllo, la voce "Segui il cursore della tastiera" è stata sostituita con "Segui il cursore di sistema", per adeguarsi alla terminologia attuale dello screen reader.
* Se il braille segue il cursore di controllo e il cursore si trova in un oggetto non testuale (ad esempio campo editazione), i tasti di cursor routing ora attiveranno l'oggetto. (#2386)
* L'opzione Salva le impostazioni all'uscita è ora resa predefinita per le nuove configurazioni.
* Durante l'aggiornamento di una versione precedente di NVDA, il tasto di scelta rapida Control+Alt+n non viene più assegnato forzatamente, nel caso l'utente lo avesse associato ad un'altra combinazione. (#2572)
* Nell'elenco componenti aggiuntivi, ora viene visualizzato prima il nome del pacchetto seguito dallo stato. (#2548)
* Se viene installato un componente aggiuntivo già presente, sia che la versione sia la stessa o una diversa, NVDA ora chiederà di rimuovere il vecchio ed installare il nuovo, piuttosto che dare un generico messaggio d'errore. (#2501)
* I comandi di navigazione ad oggetti (ad eccezione del comando annuncia l'oggetto corrente) sono stati resi meno prolissi. è sempre possibile ottenere informazioni aggiuntive utilizzando il comando annuncia l'oggetto corrente.
* Aggiornate le librerie LibLouis alla versione 2.5.1. (#2319, #2480, #2662, #2672)
* la voce "Guida rapida ai comandi da tastiera" è stata cambiata in "Guida rapida ai comandi" in quanto ora al suo interno si possono trovare anche riferimenti ai gesti, oltre che ai comandi da tastiera.
* La lista elementi in modalità navigazione ricorderà l'ultimo tipo di elemento mostrato (ad esempio link, intestazioni o sezioni) ogni qualvolta la finestra appaia nella medesima sessione di NVDA. (#365)
* La maggior parte delle App Metro in Windows 8 (ad esempio Mail, Calendario) non attiverà più la modalità navigazione per l'intera app.
* Aggiornato Handy Tech BrailleDriver COM-Server alla versione 1.4.2.0.

### Bug corretti

* In Windows Vista e versioni successive, NVDA non considera più erroneamente il tasto Windows come premuto, quando si ritorna a Windows dopo averlo bloccato premendo la combinazione windows-l. (#1856)
* In Adobe Reader, le intestazioni delle righe ora sono correttamente viste come celle di tabella; ad esempio, le coordinate ora vengono annunciate e gli elementi possono essere raggiunti tramite i comandi di navigazione standard. (#2444)
* in Adobe reader, le celle di una tabella che occupano più di una colonna o di una riga sono ora trattate correttamente. (#2437, #2438, #2450)
* Il pacchetto di distribuzione di NVDA ora effettua un controllo di integrità prima di essere eseguito. (#2475)
* I file temporanei scaricati verranno eliminati nel caso il download dell'aggiornamento fallisca. (#2477)
* Quando viene copiata la configurazione utente nella configurazione di sistema, (per essere usata nelle finestre di Logon e altre schermate di sicurezza), NVDA non si bloccherà più in Windows XP durante l'operazione. (#2485)
* Vengono presentate in maniera più omogenea le mattonelle nella schermata iniziale di Windows8 sia tramite sintesi vocale che braille. Il nome non viene più ripetuto, lo stato di non selezionato non viene più annunciato per ogni mattonella, e le informazioni live di stato vengono riportate come descrizione della mattonella (ad esempio l'attuale temperatura nella mattonella meteo).
* Le password non vengono più annunciate durante la lettura dei campi password in Microsoft Outlook e altri controlli editazione standard che sono marcati come protetti. (#2021)
* In Adobe Reader, le modifiche ai campi dei form vengono individuate anche in modalità navigazione. (#2529)
* Miglioramenti al supporto del controllo ortografico di Microsoft Word, che comprendono una lettura più accurata della parola che contiene l'errore, e la possibilità di usare tale funzione anche con copie installate di NVDA su sistemi operativi Windows Vista.
* I componenti aggiuntivi che contengono al loro interno file con caratteri non inglesi possono essere installati correttamente nella maggior parte dei casi. (#2505)
* In Adobe Reader, la lingua del documento non viene più persa quando lo si aggiorna o si effettuano operazioni di scorrimento. (#2544)
* Durante l'installazione di un componente aggiuntivo, la finestra di conferma ora visualizza correttamente il nome del componente nella lingua dell'utente, se disponibile. (#2422)
* Nelle applicazioni che fanno uso della tecnologia UI Automation (come i programmi .net o Silverlight), il calcolo dei valori numerici per i controlli come i cursori di avanzamento è stato corretto. (#2417)
* La configurazione per l'annuncio delle barre di avanzamento viene ora rispettata anche per quei controlli di NVDA dove non è possibile determinarne la dimensione, come l'installazione, la creazione di una copia portable, etc. (#2574)
* I comandi di NVDA non possono più essere impartiti tramite barra braille se ci si trova nelle schermate di sicurezza di Windows come la finestra di login. (#2449)
* Nella modalità navigazione, il braille viene aggiornato quando il testo visualizzato cambia. (#2074)
* Quando ci si trova in una finestra di sicurezza, i messaggi provenienti dalle applicazioni che vogliono parlare o mostrare informazioni in Braille tramite NVDA vengono ignorati.
* Nella modalità navigazione, NVDA non tornerà più all'inizio del documento se si va alla fine e si preme ripetutamente la freccia a destra. (#2463)
* Quando si legge la finestra di dialogo di un'applicazione web, non vengono più annunciati contenuti non appartenenti al contesto. (#2390)
* NVDA ora non riporta più erroneamente alcuni campi editazione non esistenti, specialmente in Internet Explorer, quando l'autore della pagina web ha dichiarato un ruolo Aria esplicitamente. (#2435)
* Il tasto Backspace viene intercettato correttamente anche quando l'opzione "leggi le parole digitate" è attivata, nel prompt dei comandi. (#2586)
* Le coordinate delle celle in Microsoft Excel vengono di nuovo visualizzate in Braille.
* In Microsoft Word, NVDA non presenta più problemi nell'esplorazione di un paragrafo avente elenchi puntati o numerati. (#2402)
* Nella modalità navigazione nelle applicazioni Mozilla, gli elementi in alcune caselle ad elenco (nello specifico, caselle ad elenco ARIA), non vengono più interpretati in maniera errata.
* Nelle applicazioni web Mozilla, NVDA nasconde il contenuto che è stato marcato come nascosto per gli screen reader (nello specifico, si tratta dell'attributo aria-hidden). (#2117)
* Nelle applicazioni web Mozilla in modalità navigazione, alcuni controlli che venivano interpretati con un etichetta non corretta o proprio con uno spazio bianco, ora vengono riconosciuti correttamente.
* Nelle applicazioni web Mozilla in modalità navigazione, sono stati eliminati alcuni spazi bianchi che non avevano motivo di esistere.
* Nei browser web in modalità navigazione, alcuni grafici che sono considerati esplicitamente di presentazione (in sostanza quelli che contengono la stringa alt=""), vengono definitivamente ignorati.
* Le quantità negative di valuta (ad esempio -123$) ora vengono annunciate in maniera corretta. (#2625)
* Durante la modalità Dire tutto, NVDA non tornerà più erroneamente alla lingua predefinita, se la riga non termina con un punto. (#2630)
* vengono riconosciute correttamente le informazioni sul carattere in Adobe Reader 10.1 e successivi. (2175)
* In Adobe Reader, se viene fornito del testo alternativo, verrà analizzato soltanto questo. In precedenza, talvolta veniva incluso del testo con caratteri incomprensibili. (#2174)
* Nei browser web, se ci si trova in un documento che contiene un'applicazione, il contenuto di tale applicazione non viene più mostrato in modalità navigazione. Questo per prevenire la possibilità di finire inavvertitamente dentro l'applicazione durante la navigazione. Si può interagire con tale applicazione nello stesso modo in cui si interagisce con gli oggetti. (#990)
* Nelle applicazioni Mozilla, viene calcolato correttamente il valore dei pulsanti spin. (#2653)
* Aggiornato il supporto per Adobe Digital Editions in modo che ora sia in grado di funzionare nella versione 2.0. (#2688)
* La pressione della combinazione di tasti NVDA+FrecciaSu mentre ci si trova in una casella combinata in Internet Explorer e altri documenti MSHTML non causerà più la lettura errata di tutti gli elementi. Verrà letto soltanto l'elemento attivo. (#2337)
* I dizionari sono in grado di salvare correttamente termini che contengano al proprio interno il simbolo cancelletto (#) (#961)
* In modalità navigazione usando Internet Explorer o comunque in documenti Mshtml, vengono visualizzati correttamente contenuti visibili messi all'interno di contenuti nascosti. Nello specifico, elementi con uno stile visibility:visible all'interno di un elemento con stile visibility:hidden). (#2097)
* I link presenti nel centro sicurezza di Windows Xp non vengono più accompagnati da caratteri strani dopo il proprio nome. (#1331)
* Vengono annunciati correttamente i controlli di testo UI Automation (come la casella di ricerca in Windows7) quando si sposta il mouse su di essi.
* Non vengono più annunciati i cambiamenti di layout tastiera durante la lettura continua di un testo. Questo era particolarmente fastidioso per la lingua araba in documenti che contenevano numerosi cambiamenti di linguaggio. (#1676)
* Se un controllo di testo UI Automation (come la casella di ricerca in Windows7) cambia, non viene più ripetuto tutte le volte il contenuto per intero.
* Quando ci si sposta tra i gruppi nella schermata iniziale di Windows8, il nome della prima mattonella non viene più interpretato come nome del gruppo, il che dovrebbe velocizzare la navigazione. (#2658)
* Quando viene aperta la schermata iniziale di Windows8, il focus viene ora posto correttamente sulla prima mattonella. (#2720)
* NVDA non darà più messaggi di errore all'avvio se il percorso nome profilo utente contiene alcuni caratteri multibyte. (#2729)
* In Google Chrome, il testo delle schede viene visualizzato correttamente anche in modalità navigazione.
* Nella modalità navigazione, vengono annunciati correttamente i bottoni dei menu.
* In OpenOffice.org/LibreOffice Calc, ora avviene correttamente la lettura delle celle dei fogli di calcolo. (#2765)
* NVDA funziona di nuovo nell'elenco messaggi di Yahoo Mail in Internet Explorer. (#2780)

### Cambiamenti per sviluppatori

* Il file di log precedente ora viene copiato nel file nvda-old.log subito dopo l'inizializzazione di NVDA. Tenere presente che se NVDA dovesse riavviarsi o crashare, le informazioni di log per quella sessione sono ancora accessibili. (#916)
* Il recuperare le proprietà di un ruolo in chooseNVDAObjectOverlayClasses ora funzionerà correttamente  anche negli oggetti aventi controlli Scintilla o prompt dei comandi. (#2569)
* I menu di NVDA Preferenze, Strumenti e Aiuto ora sono accessibili  come attributi su gui.mainFrame.sysTrayIcon chiamati rispettivamente preferencesMenu, toolsMenu e helpMenu. Questo permette ai componenti aggiuntivi di aggiungere voci a questi menu in maniera più rapida.
* Lo script navigatorObject_doDefaultAction in globalCommands è stato rinominato review_activate.
* Introdotto il supporto per i messaggi di contesto gettext. Questo significa che possono essere definite più traduzioni per un singolo messaggio inglese, che dipenderanno dal contesto. (#1524)
 * Realizzato grazie alla funzione pgettext(context, message).
 * Viene garantito il supporto sia per NVDA che per i componenti aggiuntivi.
 * Devono essere utilizzati xgettext e msgfmt da GNU gettext per la creazione dei file PO e MO. Gli strumenti python non supportano i messaggi di contesto.
 * Per xgettext, passare --keyword=pgettext:1c,2 come argomento da linea di comando per abilitare l'inclusione dei messaggi di contesto.
 * vedere https://www.gnu.org/software/gettext/manual/html_node/Contexts.html#Contexts per maggiori informazioni.
* è ora possibile accedere ai moduli interni a NVDA quando essi sono sovrascritti da moduli di terze parti. Si veda nvdaBuiltin module per dettagli.
* Può essere utilizzato il supporto alla traduzione dei componenti aggiuntivi all'interno del modulo installTasks. (#2715)

## 2012.2.1

Questa versione sistema pareccchi potenziali problemi di sicurezza, in seguito all'aggiornamento a Python 2.7.3.

## 2012.2

Le principali novità in questa versione riguardano la creazione di versioni portable e installer direttamente da un unico pacchetto, una funzione di aggiornamento automatico, una gestione semplificata dei componenti aggiuntivi, l'annuncio dei grafici in Microsoft Word, il supporto per le applicazioni in stile Metro in Windows8 e la risoluzione di importanti bug.

### Novità

* NVDA è in grado di controllare e scaricare nuove versioni e aggiornamenti dello screen reader. (#73)
* Le funzioni di NVDA possono essere aumentate tramite la gestione di plugin personalizzati e driver, grazie al gestore di componenti aggiuntivi (situato alla voce strumenti del menu di NVDA) che permette l'installazione e disinstallazione dei pacchetti aventi come estensione nvda-addon. Si noti che il Gestore di componenti aggiuntivi non è in grado di rilevare componenti installati in precedenza dall'utente. (#213)
* Molte funzionalità comuni di NVDA nelle applicazioni che usano l'interfaccia Metro di Windows8 ora si comportano correttamente, quando viene utilizzata una versione installer di NVDA, compreso l'annuncio dei caratteri digitati, e la modalità navigazione per i documenti web (incluso il supporto per la versione Metro di Internet Explorer 10). Le copie portabili di NVDA non possono accedere alle app in stile Metro. (#1801)
* Nei documenti in modalità navigazione (Internet Explorer, Firefox, etc) è ora possibile saltare all'inizio o alla fine di elenchi, frame o tabelle, con i tasti "Shift+;" e ",". (#123)
* Nuova lingua: Greco.
* In Microsoft Word, vengono ora visualizzati i grafici e il testo alternativo. (#2282, #1541)

### Cambiamenti

* L'annuncio delle coordinate delle celle in Microsoft Excel avviene dopo il contenuto e non prima, e risulta attivo soltanto se le opzioni "leggi le tabelle" e "leggi le coordinate di una cella in una tabella, situate sulla finestra di dialogo formattazione documento, sono attive. (#320)
* NVDA viene ora distribuito in un unico pacchetto. Invece di avere due pacchetti diversi formati da un installer e una portable, ora è a disposizione un file unico che, una volta eseguito, farà avviare una copia temporanea di NVDA, permettendo o l'installazione di NVDA, oppure la generazione di una distribuzione portable. (#1715)
* NVDA viene installato ora nella cartella programmi su tutti i sistemi operativi. L'aggiornamento da una versione precedente causerà lo spostamento dei file in tale cartella.

### Bug Corretti

* Con l'opzione "cambia la lingua automaticamente" attiva, il testo ricavato da grafici o etichette nelle applicazioni Mozilla Gecko (come Firefox) viene ora letto nella lingua appropriata.
* Il comando  dire tutto non si ferma più nel mezzo di un testo nel programma Bibleseeker e nei controlli editazioni di tipo  TRxRichEdit.
* Vengono letti correttamente gli elenchi situati in Windows8 Explorer, scheda permessi della finestra proprietà, e anche quelli nella finestra Windows Update.
* NVDA non rallenta più nei documenti Word in presenza di righe molto lunghe, o di sommari complessi, e in tutte le circostanze in cui necessitano più di due secondi per ottenere informazioni dal documento. (#2191)
* Il rilevamento della fine di una parola ora funziona correttamente anche in presenza di spazi bianchi seguiti da certi simboli di punteggiatura. (#1656)
* In Adobe Reader, quando si utilizza la modalità navigazione, ora è possibile navigare per intestazioni senza un livello utilizzando i tasti di navigazione veloce e l'elenco elementi. (#2181)
* In Winamp, il braille viene aggiornato correttamente quando ci si sposta in un elemento diverso nell'editor playlist. (#1912)
* L'albero nell'elenco elementi (disponibile nei documenti in modalità navigazione) è ora ridimensionato per visualizzare il testo di ciascun elemento. (#2276)
* Nelle applicazioni che fanno uso di Java Access bridge, i campi editazione ora vengono mostrati correttamente in Braille. (#2284)
* Nelle applicazioni che fanno uso di Java Access bridge, i campi editazione non vengono più visualizzati con caratteri strani in alcune circostanze. (#1892)
* Nelle applicazioni che utilizzano Java Access Bridge, giunti alla fine di un campo di testo modificabile, la riga corrente viene ora riportata correttamente. (#1892)
* In modalità navigazione nelle applicazioni che utilizzano Mozilla Gecko 14 e successivi (ad esempio Firefox 14), i tasti di navigazione veloce funzionano nei blocchi tra virgolette e negli oggetti. (#2287)
* In Internet Explorer 9, NVDA non legge più contenuti non desiderati quando il focus si sposta all'interno di un elemento div che risulta evidenziabile o che è marcato con una sezione ARIA.
* L'icona di NVDA nel desktop e i collegamenti nel menu di avvio nei sistemi a 64 bit sono visualizzati ora correttamente. (#354)

### Cambiamenti per sviluppatori

* A causa della sostituzione del precedente NSIS Installer per NVDA con uno integrato in Python, non è più necessario per i traduttori lavorare sul file langstrings.txt per l'installer. Tutte le stringhe vengono ora gestite dai file gettext po.

## 2012.1

Le principali novità di questa versione si concentrano su una lettura del braille molto più fluida; la formattazione dei documenti è indicata anche in braille; accesso a molte più informazioni di formattazione e una migliore gestione di Microsoft Word; inoltre, accesso semplificato e intuitivo all'Itunes Store.

### Novità

* NVDA è in grado di annunciare il numero di spazi e di rientri nella riga attuale, nell'ordine in cui sono stati inseriti. Questo può essere attivato selezionando l'opzione annuncia rientri riga nella finestra di dialogo formattazione documento. (#373)
* NVDA è in grado di rilevare la pressione dei tasti proveniente da tastiere alternative che lavorano in emulazione come tastiere a schermo o programmi di riconoscimento vocale.
* NVDA è in grado di rilevare i colori nelle finestre console, come prompt dei comandi.
* Vengono indicati in braille i simboli di sottolineato, grassetto e corsivo, utilizzando i segni della tabella braille selezionata. (#538)
* Vengono annunciate molte più informazioni nei documenti Microsoft word, che comprendono:
 * Informazioni in linea come note a piè di pagina e note a fine testo, numerazioni, livello intestazioni, l'esistenza di commenti, livello di annidamento delle tabelle, link e colori del testo;
 * Annuncio di quando si raggiungono sezioni del documento come l'elenco dei commenti, delle note a piè di pagina o note a fine testo, e delle intestazioni e piè di pagina.
* In braille, i puntini 7 e 8 indicano la selezione del testo. (#889)
* Vengono riportate in braille informazioni sui controlli contenuti nei documenti, come link, intestazioni e pulsanti. (#202)
* Supporto per  i display Braille hedo ProfiLine e MobilLine USB. (#1863, #1897)
* NVDA ora cerca di evitare di spezzare le parole in braille di default. Questo può venir disattivato nelle impostazioni braille. (#1890, #1946)
* E' ora possibile usufruire in braille della lettura per paragrafi, oltre che per righe, che dovrebbe offrire una consultazione più comoda in grandi porzioni di testo. Tale opzione è selezionabile dalle impostazioni Braille, voce lettura per paragrafi. (#1891)
* In modalità navigazione, è possibile attivare un oggetto direttamente utilizzando una barra braille. Sarà sufficiente fare doppio click con il cursor routing corrispondente, oppure, nel caso il cursore sia già alla posizione desiderata, basterà un click solo. (#1893)
* Introdotto un supporto di base nelle aree web di Itunes, come lo store. Possono essere supportate anche altre applicazioni che utilizzino WebKit 1. (#734)
* Nei libri in Adobe Digital Edition 1.8.1 e versioni successive, le pagine verranno girate automaticamente anche utilizzando l'opzione dire tutto. (#1978)
* Nuove tabelle di traduzione Braille: Portoghese Grado 2, Islandese 8 punti Braille Computer, Tamil Grado 1, Spagnolo 8 punti Braille Computer, Farsi Grado 1. (#2014)
* E' ora possibile configurare dalla finestra Formato documento se i frame debbano essere annunciati o meno, tramite l'opzione Leggi Frame. (#1900)
* Viene attivata automaticamente la modalità riposo per il programma Openbook. (#1209)
* In Poedit, ora i traduttori sono in grado di leggere automaticamente i commenti estratti e i commenti aggiunti nelle traduzioni. I messaggi che risultano non ancora tradotti o che sono incerti sono marcati con un asterisco e viene prodotto un beep quando li si raggiunge. (#1811)
* Supporto per i Display Braille Serie HumanWare Brailliant BI e B (#1990)
* Nuova Lingua: Norvegese Bokmål.

### Cambiamenti

* Il comando che consente di ottenere una descrizione del carattere attuale o di ascoltare lo spelling della parola o della riga ora funzionerà esattamente con la lingua del testo, se l'opzione cambio lingua automatica risulta attiva e sono disponibili le informazioni appropriate per la lingua.
* Aggiornata Espeak alla versione 1.46.02.
* NVDA non visualizzerà nomi più lunghi di 30 caratteri quando essi vengono presi da grafici o link degli URL, in quanto generalmente si tratta di informazioni di poco conto che disturbano la lettura. (#1989)
* Molte informazioni in braille sono state abbreviate. (#1955, #2043)
* Quando il cursore, oppure il cursore di controllo, viene spostato, il Braille lo seguirà correttamente come se avvenisse uno scorrimento manuale. Il risultato è una lettura più fluida quando l'opzione "lettura per paragrafi", o "evita di spezzare le parole", è attiva. (#1996)
* Aggiornamento alla nuova tabella Braille Spagnola Grado1
* Aggiornamento a libblouis braille translator 2.4.1.

### Bug corretti

* In Windows8, il focus non viene più spostato erroneamente al di fuori del campo di ricerca in Windows Explorer, il che non permetteva a NVDA di interagire con esso.
* Notevole aumento delle prestazioni durante la lettura e l'esplorazione di documenti word quando l'opzione annuncio automatico  formattazione è attiva, il che consente la correzione dei documenti in maniera più confortevole. Aumento in generale delle prestazioni in Microsoft Word.
* La modalità navigazione è utilizzata ora anche nei contenuti  flash a tutto schermo.
* Risolto un problema che faceva ascoltare le voci Microsoft Speech Api Versione 5 con audio scadente, nel caso fosse selezionata una periferica audio diversa da sound mapper. (#749)
* NVDA ora funziona nuovamente con i display braille, anche se la sintesi vocale è impostata su Nessun Sintetizzatore. (#1963)
* I comandi per la navigazione ad oggetti non annunceranno più  nessun oggetto genitore/figlio, ma utilizzeranno gli stessi termini della documentazione.
* Quando NVDA viene configurato nell'utilizzare una lingua diversa dall'inglese, il nome del tasto tab viene annunciato nella lingua corretta.
* Nelle applicazioni Mozilla Gecko (ad esempio Firefox), NVDA non attiverà più in maniera intermittente la modalità navigazione quando si esplorano i menu nei documenti. (#2025)
* Nella calcolatrice, la pressione del tasto Backspace ora annuncia il risultato aggiornato, piuttosto che non dire nulla. (#2030)
* Nella modalità navigazione,  il comando "sposta il puntatore del mouse sull'oggetto attuale del navigatore) ora porterà il mouse al centro dell'oggetto sul quale è situato il cursore di controllo, invece che in alto a sinistra, il che rende questa operazione più accurata in alcune circostanze. (#2029)
* In modalità navigazione, se l'opzione Modalita' focus automatica per i cambiamenti del focus è attiva, il portarsi in una barra degli strumenti farà attivare la modalità focus. (#1339)
* Il comando Leggi titolo ora funziona di nuovo correttamente in Adobe Reader.
* Quando l'opzione "modalità del focus automatica per i cambiamenti del focus" è attiva, viene utilizzata correttamente la modalità focus nelle tabelle e naturalmente nelle celle (esempio griglie). (#1763)
* In Itunes, la posizione in alcune visualizzazioni ad elenco è ora riportata correttamente.
* In Adobe Reader,  alcuni link non sono più trattati come campi editazione di sola lettura.
* Le etichette di alcuni campi editazione non vengono più incluse in maniera non corretta quando viene annunciato il testo di una finestra di dialogo. (#1960)
* Viene annunciata nuovamente la descrizione dei raggruppamenti, se l'opzione annuncia descrizione degli oggetti è attiva.
* La finestra di dialogo inerente le proprietà di un'unità disco in risorse del computer  viene gestita in maniera migliore indipendentemente dalla dimensione dei caratteri.
* E' stato sistemato un problema che causava la doppia lettura del testo nelle finestre proprietà. (#218)
* Migliorato l'inseguimento del cursore nei campi di testo editabili che si basano sul testo scritto a schermo. In particolare, si possono notare grossi benefici nella modifica del contenuto delle celle in Microsoft Excel e nella gestione della composizione messaggi in Eudora. (#1658)
* In Firefox11, il comando control+NVDA+spazio ora si comporta in maniera corretta, ad esempio nell'uscire da oggetti Flash.
* NVDA ora si riavvia correttamente, ad esempio quando viene modificata la lingua, e la configurazione viene salvata in una cartella con caratteri non ascii.  (#2079)
* Il Braille ora rispetta correttamente le impostazioni che influenzano la rappresentazione dei tasti caldi  degli oggetti, informazioni sulla loro posizione e descrizione.
* Nelle applicazioni Mozilla, cambiare dalla modalità navigazione alla modalità focus ora funziona correttamente anche con il braille attivo. (#2095)
* Se si utilizza un tasto cursor routing per spostare il cursore all'ultimo carattere di una riga o di un paragrafo, e questo carattere è uno spazio bianco, NVDA eseguirà l'operazione correttamente invece di portare il cursore all'inizio del testo. (#2096)
* NVDA funziona di nuovo correttamente con la sintesi vocale Audiologic. (#2109)
* Vengono elaborati correttamente i documenti in Microsoft Word come multilinea, di modo che lo scorrimento con un display braille sia fluido e senza intoppi.
* In Microsoft Internet Explorer, non vengono più generati errori in caso il focus venga dato su alcuni controlli abbastanza rari. (#2121)
* La modifica della pronuncia di simboli e punteggiatura effettuata da un utente avrà effetto immediato, piuttosto che dopo un riavvio di NVDA o dover impostare l'opzione rilevamento lingue su disattivo.
* Quando si utilizza Espeak, la sintesi vocale non smette più di parlare in alcune circostanze nella finestra salva con nome del visualizzatore log di NVDA. (#2145)

### Cambiamenti per sviluppatori

* E' disponibile una console remota python da usarsi in quelle situazioni dove il debug da remoto risulta utile. Si veda la guida per sviluppatori per maggiori informazioni.
* Il percorso di base del codice di NVDA viene catturato dal traceback nei log, per migliorarne la lettura. (#1880)
* Gli oggetti TextInfo  ora possiedono il metodo activate() per attivare la posizione rappresentata da Textinfo.
 * Questo viene usato dai display braille per attivare la posizione con i cursor routing, ma vi saranno altre chiamate in futuro.
* Gli elementi TreeInterceptors e NVDAObjects che espongono solo una pagina di testo alla volta ora supportano l'azione di girare pagina in modalità dire tutto, grazie all'uso di textInfos.DocumentWithPageTurns. (#1978)
* Sono stati rinominati o spostati diversi controlli o costanti output. (#228)
 * Le costanti speech.REASON_* sono state spostate su controlTypes.
 * In controlTypes, speechRoleLabels e speechStateLabels sono stati rinominati in roleLabels e stateLabels.
* Implementato nelle funzioni di log anche l'output del braille. (#2102)
* Le sottoclassi di Sapi5 Synthdrivers possono sovrascrivere _getVoiceTokens  e estendere init per supportare token di voce personalizzati come  con sapi.spObjectTokenCategory per ottenere token da una locazione di registro personalizzata.

## 2011.3

I punti salienti di questa versione includono il cambio automatico della lingua vocale durante la lettura di documenti con informazioni sulla lingua appropriate; supporto per ambienti Java Runtime a 64 bit; segnalazione della formattazione del testo in modalità navigazione nelle applicazioni Mozilla; migliore gestione degli arresti anomali e dei blocchi delle applicazioni; e correzioni iniziali per Windows 8.

### Novità

* NVDA ora è in grado di modificare la lingua di Espeak al volo, quando vengono letti documenti pdf oppure pagine web, purché essi contengano informazioni appropriate per la lingua. Le opzioni sul cambio automatico della lingua/dialetto possono essere modificate nelle impostazioni voce. (#845)
* Viene supportato Java Access Bridge 2.0.2, che include il supporto per RunTime Java a 64 bit.
* Nelle applicazioni Mozilla Gecko (ad esempio Firefox), vengono annunciati i livelli di intestazione anche nella navigazione ad oggetti.
* Le informazioni di formattazione vengono annunciate anche quando si utilizza la modalità navigazione nelle applicazioni Mozilla Gecko, ad esempio Firefox o Thunderbird. (#394)
* Le applicazioni con controlli Iaccessible2 come quelle di Mozilla  ora sono in grado di rilevare il testo sottolineato o barrato.
* Nella modalità navigazione in Adobe Reader, viene riportata la quantità di righe e colonne in una tabella.
* Aggiunto il supporto alle sintesi vocali Microsoft Speech platform. (#1735)
* Vengono annunciati i numeri di pagina e di riga relativi al cursore in Ibm Lotus Symphony. (#1632)
* E' possibile configurare dalle impostazioni voce in percentuale di quanto debba aumentare l'altezza della voce in concomitanza con lettere maiuscole. Di conseguenza, la vecchia opzione viene sostituita da questo nuovo parametro. (Per disattivare questa caratteristica impostare l'opzione a 0). (#255)
* Il colore del testo e dello sfondo ora sono compresi nell'annuncio delle informazioni di formattazione nelle celle di Microsoft Excel. (#1655)
* Nelle applicazioni dove si utilizza Java Access Bridge, il comando attiva l'oggetto alla posizione del navigatore ora funziona nei controlli appropriati. (#1744)
* Supporto Base per Design Science MathPlayer.
* Nuova lingua: tamil.

### Cambiamenti

* NVDA verrà riavviato nel caso si pianti.
* Alcune informazioni mostrate in braille sono state abbreviate. (#1288)
* Il comando per leggere il contenuto della finestra attiva NVDA+b è stato migliorato in modo da eliminare informazioni superflue ed inoltre risulta molto più agevole da silenziare. (#1499)
* La caratteristica dire tutto nei documenti in modalità navigazione può essere attivata o disattivata tramite un'opzione presente nella finestra impostazioni navigazione. (#414)
* Nel caso il comando per leggere la barra di stato non funzioni, verrà letta l'ultima riga dello schermo dell'applicazione attiva. (#649)
* Durante la lettura di un documento in modalità navigazione, NVDA effettuerà le pause alla fine delle intestazioni o di altri elementi con blocco di testo, piuttosto di leggere un enorme quantità di testo tutta assieme.
* In modalità navigazione, la pressione del tasto invio o spazio in una scheda (tab) ora la attiverà, invece di passare in modalità focus. (#1760)
* Espeak Aggiornata alla versione 1.45.47.

### Bug corretti

* NVDA non visualizzerà più i simboli di puntato o numerico negli elenchi in Internet Explorer e altri controlli MSHTML nel caso l'autore abbia indicato che essi non devono essere mostrati (ad esempio lo stile elenco è impostato su "none"). (#1671)
* Il riavvio di NVDA quando è bloccato (ad esempio premendo control+alt+n) non chiude più la copia precedente senza lanciarne una di nuova.
* La pressione dei tasti backspace o le frecce non provoca più strani comportamenti in alcune circostanze nella finestra prompt dei comandi. (#1612)
* L'elemento selezionato nelle caselle ad elenco WPF (e probabilmente in altre caselle ad elenco esposte utilizzando UI automation) che non permette la modifica del testo viene ora annunciato correttamente.
* In Adobe Reader nella modalità navigazione ora è sempre possibile spostarsi alla riga successiva e precedente nelle tabelle. (#1731)
* In Adobe Reader nella modalità navigazione ora è sempre possibile spostarsi in celle vuote in una tabella.
* Non vengono più visualizzate in braille posizioni  senza riferimenti (ad esempio livello 0 di 0).
* Quando il Braille segue il cursore di controllo, ora è in grado di mostrare il contenuto anche nella navigazione in linea. (#1711)
* Un testo con un controllo di testo non viene più visualizzato due volte in braille, ad esempio muovendosi indietro dall'inizio di un documento in wordpad.
* Nella modalità navigazione in Internet Explorer, la pressione del tasto invio in un pulsante file upload ora mostrerà correttamente la finestra di dialogo di selezione file, invece di attivare la modalità focus. (#1720)
* I cambiamenti di contenuti dinamici come nelle finestre Dos non vengono più riportati se la modalità riposo per quell'applicazione è attiva. (#1662)
* Nella modalità navigazione, il comportamento dei comandi alt+freccia su e alt+freccia giù per comprimere o espandere una casella combinata è stato migliorato. (#1630)
* NVDA riesce ad essere più reattivo e a non bloccarsi in alcune situazioni dove applicazioni esterne non rispondono più (#1408)
* Nei documenti Mozilla Gecko (ad esempio Firefox), in modalità navigazione,  NVDA non interpreterà più male il testo in alcune situazioni specifiche dove un elemento utilizzava lo stile display:table. #(1373)
* NVDA non annuncerà più i controlli di un etichetta quando il focus si sposta all'interno di essi. Inoltre le etichette per alcuni campi nei forum non verranno più annunciate due volte in Firefox (Gecko) e Internet Explorer (MSHTML). (#1650)
* NVDA non commetterà più errori nella lettura di una cella in Microsoft Excel dopo aver incollato qualcosa in essa con control+v. (#1781)
* In Adobe Reader, non vengono più annunciate informazioni senza senso per un documento quando ci si sposta in un controllo che si trova in una pagina diversa in modalità focus. (#1659)
* Nelle applicazioni Mozilla Gecko (ad esempio Firefox) nella modalità navigazione, i pulsanti ciclici o pulsanti di cambio vengono individuati e riportati ora correttamente. (#1757)
* NVDA è ora in grado di leggere correttamente la barra degli indirizzi in Esplora Risorse in Windows 8 Developer Preview.
* NVDA non bloccherà più alcune applicazioni in Windows8 come Winver o Wordpad a causa di traduzioni errate.
* Nelle applicazioni che utilizzano Mozilla Gecko 10 e successivi come Firefox10, in modalità navigazione, il cursore verrà posizionato più correttamente al caricamento di una pagina web avente un'ancora come destinazione. (#360
* In modalità navigazione in applicazioni Mozilla Gecko (esempio Firefox), vengono ora annunciate le etichette per le mappe immagini.
* Quando il tracciamento mouse è attivo, lo spostamento del mouse su certi campi editazione di testo (come nelle impostazioni periferiche di puntamento Synaptics, e Speechlab Speaktext) non causerà più il crash dell'applicazione. (#672)
* NVDA ora funzionerà in maniera nettamente migliore nelle finestre  di dialogo di alcune applicazioni distribuite con Windows Xp, come ad esempio la finestra informazioni in Notepad e la finestra informazioni in Windows. (#1853, #1855)
* Risolti gli errori della funzione "spostarsi parola per parola" nei controlli editazione di Windows. (#1877)
* Lo spostamento al di fuori di un campo editazione di testo servendosi della freccia sinistra, superiore o pagina su, mentre ci si trova in modalità focus, ora attiverà la modalità navigazione, se la funzione modalità focus automatica per i movimenti del cursore è attiva. (#1733)

### Changes for Developers

* NVDA can now instruct speech synthesizers to switch languages for particular sections of speech.
 * To support this, drivers must handle speech.LangChangeCommand in sequences past to SynthDriver.speak().
 * SynthDriver objects should also provide the language argument to VoiceInfo objects (or override the language attribute to retrieve the current language). Otherwise, NVDA's user interface language will be used.

## 2011.2

Le principali novità di questa versione riguardano una gestione avanzata della punteggiatura e dei simboli, con possibilità di avere livelli configurabili, etichette personalizzabili e descrizione dei caratteri; durante la lettura in modalità "dire tutto", non verranno più effettuate pause alla fine di ciascuna riga; migliorato il supporto Aria in Internet Explorer; supporto migliorato per i documenti pdf XFA/LiveCycle in Adobe Reader; accesso al testo presente a video in un maggior numero di applicazioni; aggiunte informazioni sul carattere, sui colori e sulla formattazione del testo presente a schermo.

### Novità

* Ora è possibile ascoltare la descrizione di un dato carattere premendo due volte il tasto che attiva lo script dire carattere nei comandi di revisione. Per l'italiano si tratta dell'alfabeto Nato: Alpha, Bravo, etc. Per lingue pittografiche come il cinese tradizionale, vengono annunciati uno o più esempi tramite delle frasi. Tutto ciò ha effetto anche con i comandi dire parola e dire riga premuti tre volte. (#55)
* Può essere esaminata una maggior quantità di testo con la navigazione in linea per applicazioni tipo Mozilla Thunderbird che scrivono il testo direttamente a schermo.
* E' possibile scegliere tra più livelli nell'annuncio di simboli e punteggiatura. (#332)
* Quando vengono ripetuti più di 4 volte simboli di punteggiatura o simili, viene annunciato il numero dei simboli presenti piuttosto che annunciarli uno ad uno. (#43)
* Nuove tabelle di traduzione Braille: Norvegese 8 punti braille computer, Etiope Grado1, Sloveno Grado1, Serbo Grado1. (#1456)
* La sintesi vocale non effettua più pause innaturali alla fine di ogni riga nella modalità dire tutto. (#149)
* NVDA annuncerà se un elemento  possiede l'attributo "ordinato" nei browser web, rispettando le proprietà Aria-sort. (#1500)
* I simboli Braille Unicode vengono riprodotti correttamente nei Display Braille. (#1505)
* In Internet Explorer ed in altri controlli MShtml quando il focus si sposta all'interno di un gruppo di controlli, NVDA ora dirà il nome di tale gruppo. (#535)
* In Internet Explorer e altri controlli MShtml, le proprietà Aria-LabelledBy e aria-describedBy ora vengono rispettate.
* In Internet Explorer e altri controlli MShtml, è stato migliorato il supporto Aria per elenchi, griglie di celle, indicatori e barre di progresso.
* Gli utenti possono modificare la pronuncia della punteggiatura ed altri simboli, e possono stabilire il livello in cui NVDA dovrà annunciarli. (#271, #1516)
* In Microsoft Excel, ora viene letto il nome del foglio attivo quando ci si sposta tra essi con Control+Pagina su o Control+Pagina giù. (#760)
* Quando in Microsoft Word si esplora una tabella utilizzando il tasto Tab, NVDA leggerà la cella attuale man mano che ci si sposta. (#159)
* Dalle opzioni formattazione documento, è possibile configurare se le coordinate di una cella in una tabella debbano essere annunciate. (#719)
* NVDA ora è in grado di individuare informazioni sul colore e sulla formattazione del testo scritto direttamente a schermo.
* Nell'elenco dei messaggi di Outlook Express/Windows Mail/Windows Live mail, NVDA ora annuncerà se un messaggio non è ancora stato letto, o nel caso si utilizzi la visualizzazione discussioni, se essa è espansa o meno. (868)
* Espeak ora possiede una nuova impostazione chiamata aumento velocità, che triplica la velocità del parlato.
* Supporto per i controlli del calendario situati nella finestra di dialogo  informazioni data/ora, accessibile dall'orologio di Windows7. (#1637)
* Sono state assegnate nuove combinazioni di tasti per il display Braille Lilli prodotto dalla MDV. (#241)
* Nuove lingue: Bulgaro, Albanese.

### Cambiamenti

* Per spostare il cursore di sistema alla posizione del cursore di controllo, bisogna utilizzare il comando sposta il focus alla posizione del navigatore ad oggetti (NVDA+Shift+meno del tastierino numerico per i computer fissi, NVDA+Shift+Backspace per i portatili) due volte in rapida successione. (#837)
* Per ascoltare la rappresentazione decimale o esadecimale di un carattere mentre si usa il cursore di controllo, premere il comando leggi carattere corrente tre volte anziché due, in quanto la doppia pressione ora riporta la descrizione del carattere.
* Aggiornato il motore di sintesi Espeak alla versione 1.45.03. (#1465)
* Le tabelle di layout non vengono più annunciate nelle applicazioni Mozilla Gecko se ci si trova in modalità focus e si sposta il cursore.
* In Internet Explorer e altri controlli MSHTML, la modalità navigazione funziona per documenti all'interno di applicazioni ARIA. (#1452)
* Aggiornato il pacchetto Liblouis Braille alla versione 2.3.0.
* Quando ci si trova in modalità navigazione e si salta ad un controllo  con un tasto rapido di navigazione,   viene annunciata la descrizione di tale controllo se esiste.
* Le barre di progresso ora vengono annunciate in modalità navigazione.
* I nodi contrassegnati con un ruolo di presentazione ARIA in Internet Explorer e altri controlli MSHTML vengono ora filtrati dalla revisione semplice e dall'ascendenza del focus.
* L'interfaccia utente di NVDA e la documentazione non utilizzeranno più la terminologia buffer virtuale, bensì modalità navigazione, in quanto il termine buffer virtuale risultava complicato per molti utenti. (#1509)
* Quando l'utente desidera copiare le proprie impostazioni personali sul profilo di sistema in modo da poter esplorare anche le schermate di login, e questi settaggi contengono plugin personalizzati, viene mostrato un messaggio che avvisa che questa operazione può essere rischiosa per la sicurezza. (#1426)
* Il servizio NVDA non avvia e arresta più NVDA sui desktop di input dell'utente.
* In Windows XP e Windows Vista NVDA non effettua più uso delle UI Automation, nonostante esse possano essere disponibili attraverso gli aggiornamenti. Sebbene l'utilizzo di tale tecnologia può aumentare l'accessibilità di programmi moderni, in Windows Xp e Vista si verificavano troppi rallentamenti e crash durante il loro utilizzo. (#1437)
* Nelle applicazioni che si avvalgono di Mozilla Gecko 2 e successivi (Firefox4 e seguenti per esempio), un documento può venir letto in modalità navigazione anche prima che esso sia caricato del tutto.
* NVDA ora annuncia lo stato del documento quando il focus si sposta su di esso, ad esempio se il focus viene portato su un documento che è in fase di caricamento, NVDA dirà occupato.
* La documentazione di NVDA è stata aggiornata in modo da non utilizzare più alcuni termini come oggetto padre e oggetto figlio, in quanto poco comprensibili per la maggior parte degli utenti.
* Il termine "espanso"  non viene più annunciato per alcuni elementi di menu che hanno al loro interno altri sotto menu.
* Il comando NVDA+f ora annuncia la formattazione alla posizione del cursore di controllo, non più quindi all'altezza di quella del cursore di sistema. Poiche' in ogni caso da impostazioni predefinite il cursore di controllo segue il cursore di sistema, la maggior parte degli utenti non noteranno differenze. In ogni caso, questo fa sì che ora sia possibile esplorare la formattazione del testo con il cursore di controllo, soprattutto quando si utilizza la navigazione in linea.

### Bug corretti

* Quando vengono  chiuse le caselle combinate nei documenti in modalità navigazione e la modalità focus è stata forzata con NVDA+spazio, NVDA non tornerà più in modalità navigazione automaticamente. (#1386)
* Nei documenti Gecko (ad esempio Firefox) o controlli MSHTML (ad esempio Internet Explorer), NVDA ora non spezza più certe parti di testo su più righe, ma le dispone in una riga sola. (#1378)
* Quando il Braille segue il cursore di controllo e il navigatore ad oggetti viene spostato in un documento ove si utilizza la modalità navigazione, sia manualmente sia tramite un mutamento del focus, verrà riprodotta correttamente in braille la modalità navigazione. (#1406, #1407)
* Quando l'annuncio della punteggiatura è disabilitato, alcuni simboli non verranno più erroneamente vocalizzati con certe sintesi vocali. (#332)
* Non vi sono più problemi nel caricamento di  quei sintetizzatori come Audiologic che non supportano le impostazioni della voce. (#1347)
* Il menu Extra di Skype ora viene letto correttamente. (#648)
* Abilitare la casella di controllo  "la luminosità controlla il volume delle coordinate audio) nella finestra di dialogo inerenti le impostazioni del mouse non causa più grossi rallentamenti quando si sposta il mouse in WindowsVista/Windows7 con la modalità Aero attivata. (#1183)
* Quando NVDA è configurato per utilizzare il layout di tastiera Laptop, la combinazione NVDA+Canc funziona come documentato nel riportare le dimensioni dell'oggetto corrente. (#1498)
* NVDA ora rispetta correttamente l'attributo aria-selected in Internet Explorer.
* Quando NVDA va automaticamente dalla modalità navigazione alla modalità focus, ora annuncia informazioni sul contesto del focus. Per esempio, se un elemento di un elenco viene focalizzato, verrà annunciato per prima che si tratta di un elenco. (#1491)
* In Internet Explorer ed altri controlli MSHTML, gli elenchi Aria sono trattati come elenchi, non più come elementi di elenchi.
* Quando viene focalizzato un controllo di testo di sola lettura, NVDA ora annuncerà per l'appunto che il testo su cui ci si trova è di sola lettura. (#1436)
* Nella modalità navigazione, NVDA ora si comporta correttamente in presenza di campi di testo di sola lettura.
* Nei documenti in modalità navigazione, NVDA non passerà più automaticamente alla modalità focus in caso sia impostato l'attributo aria-activedescendant; ad esempio quando appare un elenco di elementi con completamento automatico.
* In Adobe Reader, è ora annunciato il nome dei controlli quando viene spostato il focus o o vengono utilizzati tasti rapidi in modalità navigazione.
* Nei documenti XFA Pdf in Adobe reader, vengono riconosciuti correttamente bottoni, links e grafici.
* Nei documenti XFA Pdf in Adobe reader, tutti gli elementi vengono ora riportati su linee separate. Questo cambiamento è dovuto al fatto che vi erano alcune sezioni di testo o documenti interi che venivano letti senza alcuna interruzione a causa della mancanza di una struttura di base in essi.
* Risolti i problemi quando viene spostato il focus in campi di testo editabili nei documenti XFA PDF in Adobe Reader.
* Nei documenti XFA Pdf in Adobe reader, vengono ora annunciati i cambiamenti dei valori di una casella combinata su cui è il focus.
* Sono ora accessibili a NVDA caselle combinate come quelle presenti in Outlook Express per la selezione del colore. (#1340)
* Nelle lingue che utilizzano uno spazio per separare le cifre in gruppi come le migliaia in Francese e in Tedesco, i numeri presenti nelle varie porzioni di testo non vengono più pronunciati come cifre singole. Questo è risultato particolarmente problematico nelle celle in tabelle che contenevano numeri al proprio interno. (#555)
* Elementi che contengono un ruolo Aria di descrizione in Internet Explorer e altri controlli MSHTML sono ora visti come testo statico anziché editabile.
* Risolti numerosi problemi causati dalla pressione del tasto tab mentre il focus si trovava in un documento in modalità navigazione, (ad esempio la pressione del tab portava inavvertitamente alla barra degli indirizzi in Internet Explorer). (#720, #1367)
* Quando si entra in un elenco durante la lettura del testo, NVDA ora annuncia "elenco con 5 elementi", invece che "elencocon 5 elementi". (#1515)
* Nell'aiuto immissione,  i gesti sono loggati sebbene gli script ad essi relativi bypasserebbero l'aiuto immissione, come i comandi di scorrimento avanti e indietro nei Display Braille.
* Nell'aiuto immissione, quando un tasto funzione viene tenuto premuto nella tastiera, NVDA non annuncerà più quel tasto come se stesse modificando se stesso; ad esempio NVDA+NVDA.
* Nei documenti Adobe Reader, ora funziona la pressione dei tasti C e Shift+c per muoversi tra le caselle combinate.
* Lo stato "selezionato" di una riga selezionabile all'interno di una tabella viene ora annunciato allo stesso modo degli elementi in un elenco o in una visualizzazione ad albero.
* I controlli in Firefox o in altre applicazioni Gecko possono essere attivati in modalità navigazione anche se il loro contenuto è stato spostato fuori schermo. (#801)
* Non è più possibile far apparire una finestra di dialogo di NVDA mentre ne viene visualizzata una seconda, in quanto questo causava grossi rallentamenti. (#1451)
* In Microsoft Excel non si manifesta più alcun ritardo se si tiene premuto un tasto per muoversi rapidamente tra celle vicine o selezionarle.
* Sistemato un fenomeno che provocava il crash del servizio NVDA che rendeva impossibile l'utilizzo dello screen reader nelle finestre di login.
* Sistemato un problema che talvolta si verificava nei display Braille, che causava la scomparsa del testo che invece doveva essere riprodotto. (#1377)
* La finestra di Download in Internet Explorer 9 è ora accessibile a NVDA. (#1280)
* Non è più possibile lanciare accidentalmente multiple istanze di NVDA. (#507)
* In sistemi particolarmente lenti, NVDA non mostrerà più tutte le volte la propria finestra principale quando viene eseguito. (#726)
* NVDA non crasherà più in WindowsXp quando viene eseguita un'applicazione WPF. (#1437)
* I comandi DireTutto e DireTutto usando il cursore di controllo ora funzionano con controlli di testo che utilizzano la tecnologia Ui Automation.  Un esempio può essere rappresentato dall'usare il cursore di controllo nei documenti xps.
* NVDA non considera più alcuni elementi della finestra di dialogo regole in Outlook Express / Windows Live Mail come caselle di controllo. (#576)
* Le caselle combinate non sono più annunciate con un sottomenu.
* NVDA ora è in grado di leggere i campi a, cc, e bcc in Microsoft Outlook. (#421)
* Risolto un problema nella finestra di dialogo delle impostazioni voce di NVDA laddove il valore di un indicatore non veniva correttamente annunciato. (#1411)
* NVDA non commette più errori nell'individuare una nuova cella quando ci si muove in un foglio di lavoro Excel dopo un taglia/incolla. (#1567)
* NVDA non peggiora nel riconoscimento dei colori se ne incontra di vario tipo.
* In Internet Explorer e altri controlli MSHTML, NVDA ora è in grado di leggere porzioni di pagine che contengono elementi iframes marcati con un ruolo Aria di presentazione. (#1569)
* In Internet Explorer e altri controlli MSHTML, risolto un problema piuttosto raro che causava il continuo ciclo in modalità focus tra un documento e un testo contenente più righe. (#1566)
* In Microsoft Word 2010, NVDA ora legge automaticamente le finestre di dialogo di conferma. (#1538)
* In campi di testo contenenti più righe presenti in Internet Explorer e altri controlli MSHTML, la selezione delle righe oltre la prima è riportata correttamente. (#1590)
* Migliorato lo spostamento parola per parola in molti casi, inclusa la modalità navigazione e i controlli editazione nelle finestre. (#1580)
* L'Installer di NVDA non visualizza più caratteri senza senso per le versioni Hong Kong di Windows Vista e Windows7. (#1596)
* NVDA non ha più problemi nel caricare il sintetizzatore Sapi5 se la configurazione contiene impostazioni per quel sintetizzatore ma mancano i parametri della voce. (#1599)
* Nei campi editazione in Internet Explorer e altri controlli MSHTML, NVDA non rallenta e non provoca grossi ritardi nel caso il Braille sia abilitato.
* Nella modalità navigazione in Firefox, NVDA non si rifiuta più di includere contenuto che si trova all'interno di un elemento focalizzabile avente un ruolo ARIA di presentazione.
* In Microsoft Word con il braille attivato, le righe oltre la prima pagina vengono visualizzate correttamente. (#1603)
* In Microsoft Word 2003, il testo delle righe scritte da destra a sinistra può di nuovo essere letto con il Braille attivo. (#627)
* In Microsoft Word, l'opzione direTutto funziona correttamente anche quando il documento non termina con la fine di una frase.
* Quando viene aperto un messaggio di testo semplice in Windows Live Mail 2011, NVDA posizionerà il focus correttamente sul documento, permettendo la lettura del messaggio stesso.
* NVDA non causerà ritardi e non smetterà temporaneamente di parlare nella finestra di dialogo Sposta in / Copia in di Windows Live Mail. (#574)
* In Outlook 2010, NVDA ora segue il focus correttamente nell'elenco dei messaggi. (#1285)
* Corretti alcuni problemi di connessione USB con il Display Braille MDV Lilli. (#241)
* In Internet Explorer e altri controlli MSHTML, in alcuni casi (ad esempio dopo un collegamento) gli spazi non vengono più ignorati nella modalità di navigazione.
* In Internet Explorer e altri controlli MSHTML, alcune interruzioni di riga estranee sono state eliminate nella modalità navigazione. in particolare, gli elementi HTML con uno stile di visualizzazione Nessuno non forzano più un'interruzione di riga. (#1685)
* Se NVDA non è in grado di avviarsi, la mancata riproduzione del suono di arresto critico di Windows non blocca più il messaggio di errore critico nel file di registro.

### Changes for Developers

* Developer documentation can now be generated using SCons. See readme.txt at the root of the source distribution for details, including associated dependencies.
* Locales can now provide descriptions for characters. See the Character Descriptions section of the Developer Guide for details. (#55)
* Locales can now provide information about the pronunciation of specific punctuation and other symbols. See the Symbol Pronunciation section of the Developer Guide for details. (#332)
* You can now build NVDAHelper with several debugging options using the nvdaHelperDebugFlags SCons variable. See readme.txt at the root of the source distribution for details. (#1390)
* Synth drivers are now passed a sequence of text and speech commands to speak, instead of just text and an index.
 * This allows for embedded indexes, parameter changes, etc.
 * Drivers should implement SynthDriver.speak() instead of SynthDriver.speakText() and SynthDriver.speakCharacter().
 * The old methods will be used if SynthDriver.speak() is not implemented, but they are deprecated and will be removed in a future release.
* gui.execute() has been removed. wx.CallAfter() should be used instead.
* gui.scriptUI has been removed.
 * For message dialogs, use wx.CallAfter(gui.messageBox, ...).
 * For all other dialogs, real wx dialogs should be used instead.
 * A new gui.runScriptModalDialog() function simplifies using modal dialogs from scripts.
* Synth drivers can now support boolean settings. See SynthDriverHandler.BooleanSynthSetting.
* SCons now accepts a certTimestampServer variable specifying the URL of a timestamping server to use to timestamp authenticode signatures. (#1644)

## 2011.1.1

Questa versione risolve diversi problemi di sicurezza e altri importanti problemi riscontrati in NVDA 2011.1.

### Bug Corretti

* Il menù Fai una Donazione ora è disabilitato nelle schermate di Login e UAC, in quanto risultava essere un potenziale rischio per la sicurezza. (#1419)
* Risulta ora impossibile effettuare operazioni di copia/incolla all'interno dell'interfaccia di NVDA, quando ci si trova in schermate di sicurezza (UAC, login, etc), in quanto risultava essere un potenziale rischio di sicurezza. (#1421)
* In Firefox 4, il comando Control+NVDA+Spazio ora funziona correttamente, permettendo di abbandonare oggetti flash e tornare al buffer virtuale. (#1429)
* Quando la funzione leggi i tasti di comando è attivata, i caratteri digitati con il tasto Shift non vengono più letti come tasti di comando. (#1422)
* Quando la funzione leggi i tasti di comando è attivata, la pressione della barra spazio con altri tasti speciali ad eccezione dello Shift (control, alt), viene ora annunciata come tasto di comando. (#1424)
* Le funzioni di logging sono completamente disabilitate quando ci si trova in schermate di sicurezza, UAC, logon di Windows, etc, in quanto risultava essere un potenziale rischio per la sicurezza. (#1435)
* Nella modalità di aiuto all'immissione, i gesti vengono ora registrati anche se non sono legati a uno script (in conformità con la guida per l'utente). (#1425)

## 2011.1

Le principali novità di questa versione riguardano l'annuncio automatico del testo in programmi come Mirc, PuTTY, Teraterm e Secure CRT; supporto per plugin globali;  lettura di numeri ed elenchi in Microsoft Word; nuove assegnazioni tasti per i Display Braille, compresi tasti per spostarsi alla riga precedente o successiva; supporto per molti Display Braille Baum, HumanWare e APH; e l'annuncio dei colori in alcuni controlli, compreso il testo in IBM Lotus Symphony.

### Nuove caratteristiche

* I colori possono essere annunciati in alcuni controlli. La lettura automatica può essere configurata  nella finestra di dialogo formattazione documento. Risulta possibile ottenere le stesse informazioni anche manualmente, con il comando NVDA+f.
 * Per ora, questa funzione è supportata nei controlli editazione Iaccessible2 (ad esempio applicazioni Mozilla), controlli RichEdit (come Wordpad), e controlli IBM Lotus Symphony.
* Quando si utilizza il buffer virtuale, ora è possibile selezionare il testo anche per pagine (Shift+Pagina su e Shift+Pagina giù) oppure per paragrafi (Control+Shift+Freccia su e Control+Shift+Freccia giù). (#639)
* NVDA annuncia automaticamente il testo in mIRC, PuTTY, Tera Term e SecureCRT. (#936)
* Gli utenti possono aggiungere o modificare le assegnazioni di tasti per qualsiasi script in NVDA con una mappa utente delle gesture. (#194)
* Supporto ai plugin globali. I Plugin globali possono aggiungere nuove funzionalità in NVDA per tutte le applicazioni. (#281)
* Un leggero segnale acustico viene emesso nel caso si digiti un carattere con il tasto shift, mentre il blocca maiuscole è attivo. Il parametro si configura nelle opzioni tastiera. (#663)
* Vengono annunciate le interruzioni di pagina quando ci si sposta riga per riga in Microsoft Word. (#758)
* Gli elenchi numerati e i simboli negli elenchi vengono letti correttamente in Microsoft Word quando ci si sposta riga per riga. (#208)
* E' disponibile un comando per attivare/disattivare la modalità Riposo, SleepMode: NVDA+Shift+S. La modalità riposo, sleep mode disabilita tutti i comandi di NVDA e l'output tramite voce/braille per l'applicazione corrente. Risulta utile se si ha a che fare con programmi che forniscono direttamente indicazioni vocali. Ripremere la combinazione di tasti per disattivare questa funzione.
* Aggiunte alcune assegnazioni di tastiera per Display Braille. Si veda la sezione Display Braille nella documentazione per tutti i dettagli. (#209)
* Per agevolare il lavoro degli sviluppatori, è possibile ricaricare i plugin globali e i moduli applicazione AppModules senza riavviare NVDA. Per farlo, usare il comando NVDA+Control+f3, oppure scegliere Strumenti, ricarica plugin nel menu di NVDA. (#544)
* NVDA ricorda l'ultima posizione in cui ci si trovava quando si ritorna in una pagina web già visitata, ad esempio quando si preme il bottone backspace o il tasto indietro. Questo fino a quando il Browser oppure NVDA verrà chiuso. (#132)
* I Display Braille HandyTech possono essere utilizzati senza dover installare Handy Tech universal driver. (#854)
* Supporto a molte barre braille Baum, HumanWare e APH. (#937)
* La Barra di Stato in Media Player Classic Home Cinema è ora individuata correttamente.
* Il Display Braille Focus Blue di Freedom Scientific può essere utilizzato anche in modalità BlueTooth. (#1345)

### Cambiamenti

* Non vengono più annunciate di default le informazioni sulla posizione in alcune circostanze quando esse possono risultare poco accurate; ad esempio la maggior parte dei menu, la barra delle applicazioni, la system tray etc. In ogni caso, l'opzione può essere riattivata dalle impostazioni presentazione oggetti.
* Aiuto tastiera è stato rinominato in aiuto immissione dati, per sottolineare che ora i sistemi di input possono essere diversi dalla tastiera.
* L'aiuto immissione dati non legge più la posizione dello script tramite voce e braille perche' risulta utile soltanto agli sviluppatori. In ogni caso l'informazione viene loggata.
* Quando NVDA si accorge di essere bloccato, continuerà ad intercettare la pressione del tasto NVDA, anche se poi i tasti vengono passati al sistema. Questo fa in modo che l'utente non disattivi o attivi il tasto blocca maiuscole inavvertitamente. (#939)
* Se i tasti vengono tenuti premuti dopo aver usato la funzione passa il tasto successivo attraverso, tutti i tasti (inclusi tasti ripetuti) verranno passati al sistema e non a NVDA fino a che l'ultimo tasto sarà stato rilasciato.
* Se un tasto funzione NVDA viene premuto due volte in rapida successione affinche' venga intercettato dal sistema e viene tenuto premuto alla seconda pressione, verranno passati al sistema anche tutti i tasti ripetuti.
* I tasti relativi al volume vengono annunciati nell'aiuto immissione dati. Può risultare utile se l'utente non è sicuro sulla loro posizione.
* Il tasto caldo per la voce cursore di controllo nel menu preferenze è stato modificato da r a c per eliminare il conflitto con le impostazioni braille.

### Bug corretti

* Quando si aggiunge una nuova voce nel dizionario, il titolo della finestra di dialogo è "aggiungi nuova voce" invece che "modifica voce dizionario". ([924)
* Nella finestra di dialogo dizionari per la voce, elementi come espressione regolare o distingui tra maiuscole e minuscole vengono presentati nella lingua dell'utente e non solo in inglese.
* Nel programma AIM, viene annunciata la propria posizione nelle visualizzazioni ad albero.
* Nei cursori d'avanzamento delle impostazioni della voce, freccia su/pagina su/home-inizio aumentano il valore mentre freccia giù/pagina giù/fine-end lo diminuiscono. In precedenza, accadeva l'opposto, il che non era affatto logico. (#221)
* Nei buffer virtuali con layout schermo disattivato, non appaiono più alcune righe vuote inutili.
* Se un tasto funzione NVDA viene premuto due volte in rapida successione ma vi è un ulteriore tasto premuto, il tasto NVDA non viene più intercettato una seconda volta per passarlo al sistema.
* I tasti di punteggiatura vengono annunciati nell'aiuto immissione dati, anche se l'opzione leggi punteggiatura è disattivata. (#977)
* Nella finestra di dialogo impostazioni tastiera, i nomi dei layout vengono presentati nella lingua scelta dall'utente e non solo in inglese. (#558)
* Risolto un problema che causava la presentazione di alcune voci come fossero vuote in documenti Adobe Reader; ad esempio i link dell'indice della guida di Apple Iphone IOS 4.1.
* il Bottone "Utilizza le impostazioni di configurazione salvate nella finestra di logon (richiede privilegi di amministratore)" situato nella finestra di dialogo generale del menu preferenze di NVDA, ora funziona anche se premuto immediatamente dopo che NVDA è stato installato per la prima volta ma prima dell'apparizione di una schermata di login sicuro. In precedenza NVDA annunciava che la copia era avvenuta correttamente, ma in realtà non veniva effettuata. (#1194)
* Non risulta più possibile avere due finestre di dialogo di impostazioni NVDA aperte allo stesso momento. (#603)
* Nei sistemi con UAC attivato, il bottone "Utilizza le impostazioni di configurazione salvate nella finestra di logon (richiede privilegi di amministratore)" non fallisce l'operazione dopo la schermata UAC, nel caso il nome utente contenga uno spazio. (#918)
* In Internet Explorer e altri controlli MSHTML, ora NVDA utilizza l'indirizzo come ultimo tentativo per carpire il nome del link, piuttosto che presentarlo come link vuoto. (#633)
* NVDA non ignora più il focus nei menu in Aol Instant Messenger 7. (#655)
* Viene annunciata l'etichetta corretta negli errori in Microsoft Word originati dal controllo ortografico (ad esempio voci come non nel dizionario, errore grammaticale, errore di punteggiatura, etc). In precedenza venivano annunciati tutti come errori grammaticali. (#883)
* Se si utilizza un Display Braille e si sta scrivendo in Microsoft Word, non dovrebbe più essere prodotto testo pieno di caratteri strani. Inoltre risolto un problema che provocava il blocco di NVDA alla pressione di un cursor routing. (#1212) Comunque, vi è una limitazione, nell'impossibilità di leggere documenti in arabo con Microsoft Word 2003 e precedenti, mentre si usa un display braille. (#627)
* Quando si preme il tasto Canc in un campo editazione, il testo nel display braille ora si aggiorna in maniera corretta. (#947)
* Cambiamenti nei documenti Gecko2 contenenti pagine web dinamiche (esempio firefox4). Ora se vi sono più schede aperte esse vengono riportate correttamente. In precedenza venivano intercettati soltanto i cambiamenti della prima scheda. (Mozilla bug 610985)
* NVDA ora è in grado di annunciare i suggerimenti per gli errori grammaticali e di punteggiatura nelle finestre di dialogo del controllo ortografico in Microsoft Word. (#704)
* In Internet Explorer e altri controlli MSHTML, NVDA non presenta più le ancore di destinazione come link vuoti. Ora, queste ancore vengono nascoste, come dev'essere. (#1326)
* La navigazione ad oggetti all'interno e attorno alle finestre raggruppate ora funziona di nuovo.
* In Firefox e altri controlli Gecko, migliorata la gestione frame multipli quando il documento è in fase di caricamento.
* NVDA ora annuncia correttamente il carattere successivo quando si elimina un carattere con il tasto canc del tastierino numerico. (#286)
* Nella finestra di login in Windows Xp, il nome utente viene nuovamente annunciato quando l'utente selezionato viene modificato.
* Risolti problemi nella lettura del testo nelle finestre del prompt dei comandi quando l'opzione annuncia numeri di riga è attiva.
* La finestra di dialogo elenco elementi per il buffer virtuale è utilizzabile ora anche da persone vedenti. (#1321)
* L'elenco delle voci nel dizionario ora risulta più leggibile da persone vedenti in quanto la finestra è più grande. (#90)
* Risolto un bug nella gestione tasti nei display braille Alva bc640/680.
* Adobe Reader non crasha più dopo aver evidenziato l'opzione documenti senza tag ed essere passati all'opzione successiva. (#1218)
* NVDA seleziona il display braille appropriato quando si ritorna alla configurazione salvata. (#1346)
* La procedura guidata di un nuovo progetto viene ora letta correttamente in  Visual Studio 2008. (#974)
* NVDA non si rifiuta più di lavorare in applicazioni che contengono caratteri non ASCII nel loro nome eseguibile. (#1352)
* Quando si legge riga per riga utilizzando AKelpad e l'opzione formato automatico è attiva, NVDA ora si comporta in maniera corretta.
* Nell'editor di codice in Visual Studio 2005/2008, NVDA non legge più l'intero testo dopo ogni carattere digitato. (#975)
* Risolto un problema che non permetteva una corretta pulizia dei caratteri dei display braille all'uscita da NVDA.
* Il focus iniziale non viene più annunciato una volta che NVDA viene attivato. (#1359)

### Cambiamenti per sviluppatori

* SCons is now used to prepare the source tree and create binary builds, portable archives, installers, etc. See readme.txt at the root of the source distribution for details.
* The key names used by NVDA (including key maps) have been made more friendly/logical; e.g. upArrow instead of extendedUp and numpadPageUp instead of prior. See the vkCodes module for a list.
* All input from the user is now represented by an inputCore.InputGesture instance. (#601)
 * Each source of input subclasses the base InputGesture class.
 * Key presses on the system keyboard are encompassed by the keyboardHandler.KeyboardInputGesture class.
 * Presses of buttons, wheels and other controls on a braille display are encompassed by subclasses of the braille.BrailleDisplayGesture class. These subclasses are provided by each braille display driver.
* Input gestures are bound to ScriptableObjects using the ScriptableObject.bindGesture() method on an instance or an __gestures dict on the class which maps gesture identifiers to script names. See baseObject.ScriptableObject for details.
* App modules no longer have key map files. All input gesture bindings must be done in the app module itself.
* All scripts now take an InputGesture instance instead of a key press.
 * KeyboardInputGestures can be sent on to the OS using the send() method of the gesture.
* To send an arbitrary key press, you must now create a KeyboardInputGesture using KeyboardInputGesture.fromName() and then use its send() method.
* Locales may now provide an input gesture map file to add new bindings or override existing bindings for scripts anywhere in NVDA. (#810)
 * Locale gesture maps should be placed in locale\LANG\gestures.ini, where LANG is the language code.
 * See inputCore.GlobalGestureMap for details of the file format.
* The new LiveText and Terminal NVDAObject behaviors facilitate automatic reporting of new text. See those classes in NVDAObjects.behaviors for details. (#936)
 * The NVDAObjects.window.DisplayModelLiveText overlay class can be used for objects which must retrieve text written to the display.
 * See the mirc and putty app modules for usage examples.
* There is no longer an _default app module. App modules should instead subclass appModuleHandler.AppModule (the base AppModule class).
* Support for global plugins which can globally bind scripts, handle NVDAObject events and choose NVDAObject overlay classes. (#281) See globalPluginHandler.GlobalPlugin for details.
* On SynthDriver objects, the available* attributes for string settings (e.g. availableVoices and availableVariants)  are now OrderedDicts keyed by ID instead of lists.
* synthDriverHandler.VoiceInfo now takes an optional language argument which specifies the language of the voice.
* SynthDriver objects now provide a language attribute which specifies the language of the current voice.
 * The base implementation uses the language specified on the VoiceInfo objects in availableVoices. This is suitable for most synthesisers which support one language per voice.
* Braille display drivers have been enhanced to allow buttons, wheels and other controls to be bound to NVDA scripts:
 * Drivers can provide a global input gesture map to add bindings for scripts anywhere in NVDA.
 * They can also provide their own scripts to perform display specific functions.
 * See braille.BrailleDisplayDriver for details and existing braille display drivers for examples.
* The 'selfVoicing' property on AppModule classes has now been renamed to 'sleepMode'.
* The app module events event_appLoseFocus and event_appGainFocus have now been renamed to event_appModule_loseFocus and event_appModule_gainFocus, respectivly, in order to make the naming convention consistent with app modules and tree interceptors.
* All braille display drivers should now use braille.BrailleDisplayDriver instead of braille.BrailleDisplayDriverWithCursor.
 * The cursor is now managed outside of the driver.
 * Existing drivers need only change their class statement accordingly and rename their _display method to display.

## 2010.2

Le caratteristiche più importanti in questa versione riguardano la facilitazione nell'utilizzare la navigazione ad oggetti; l'uso dei buffer virtuali nei contenuti Adobe Flash; accedere a controlli prima inaccessibili tramite il recuperare informazioni scritte sullo schermo; supporto ai documenti IBM Lotus Symphony; l'annuncio delle intestazioni riga e colonna nelle tabelle in Firefox; e un miglioramento significativo alla documentazione utente.

### Nuove caratteristiche

* La navigazione ad oggetti tramite il cursore di controllo è stata significativamente semplificata. Ora il cursore di controllo è in grado di escludere oggetti che non sono utili all'utente; ad esempio oggetti non disponibili o utilizzati per funzioni di layout.
* In applicazioni che si avvalgono di Java Access Bridge (inclusa OpenOffice.org), viene annunciata la formattazione del carattere. (#358, #463)
* Quando si sposta il Mouse tra le celle in Microsoft Excel, NVDA le annuncerà correttamente.
* In applicazioni che fanno uso di Java Access Bridge, il testo presente in una finestra di dialogo viene annunciato appena compare sullo schermo. (#554)
* Il buffer virtuale può essere usato per esplorare contenuti di tipo Adobe Flash. La navigazione ad oggetti e l'interazione diretta con i controlli è ancora supportata (attivando la modalità focus). (#453)
* I controlli di testo editabili in Eclipse Ide, incluso l'editor di codice, sono ora accessibili. Si noti che si deve utilizzare Eclipse 3.6 o superiore. (#256, #641)
* NVDA è in grado di recuperare molte informazioni scritte direttamente sullo schermo. (#40, #643)
 * Questo risulta utile nella lettura di controlli che non generano le informazioni in maniere più dirette o sfruttando i canali dell'accessibilità.
 * Controlli che vengono resi accessibili attraverso questa caratteristica includono: alcuni elementi di menu che mostrano delle icone (ad esempio la voce apri con, nel menu file in windows XP (#151), campi di testo editabili nelle applicazioni Windows Live (#200), l'elenco errori in Outlook Express (#582), i controlli di testo editabili in Textpad (#605), elenchi in Eudora, molti controlli in Australian E-Tax e la gestione formule in Excel.
* Supporto al Code Editor in Microsoft Visual Studio 2005 e 2008. E' richiesto almeno Visual Studio Standard; non funziona nell'edizione Express. (#457)
* Supporto per documenti IBM Lotus Symphony.
* Supporto embrionale e sperimentale a Google Chrome. Si noti che tale funzione è ben lontana dall'essere considerata completa. Si avrà bisogno di una delle versioni in sviluppo più recenti di Google Chrome.
* Lo stato dei pulsanti a interruttore (caps lock, num lock e scroll lock) viene ora visualizzato anche in Braille. (#620)
* I fumetti d'aiuto vengono mostrati anche in braille quando appaiono. (#652)
* Aggiunto un Driver per la riga Braille Mdv Lilli. (#241)
* Quando viene selezionata un'intera riga con shift+spazio o una colonna con control+spazio in Excel, la selezione viene annunciata. (#759)
* Possono essere annunciate le intestazioni di righe e colonne. L'opzione è configurabile dalla finestra formato documento.
 * Al momento il supporto viene fornito nelle applicazioni Mozilla a partire da Firefox 3.6.11 e successive e Thunderbird 3.1.5 e successive. (#361)
* Introdotti comandi per la navigazione in linea (#58)
 * NVDA + 7 del tastierino numerico: Passa alla navigazione in linea, collocando l'utente alla posizione attuale del navigatore ad oggetti, permettendo di esplorare lo schermo (o il documento se ci si trova all'interno di esso) con i consueti comandi di revisione del testo usati dal cursore di controllo.
 * NVDA+1 del tastierino numerico: Attiva il navigatore ad oggetti a partire dalla posizione corrente nella navigazione in linea, permettendo poi di usare i consueti tasti relativi alla navigazione ad oggetti.
* Le impostazioni di configurazione possono essere copiate tramite un apposito bottone nella finestra generale del menù preferenze in modo da essere usate anche nelle schermate di logon o UAC. (#730)
* Supporto a Mozilla Firefox 4.
* Supporto a Microsoft Internet Explorer 9.

### Cambiamenti

* Alcuni tasti relativi alla navigazione ad oggetti (NVDA+shift+numpad6 e NVDA+shift+numpad4) sono stati rimossi a causa del loro mal funzionamento.
* Nella finestra di dialogo Sintetizzatore, viene mostrato solo il nome reale della sintesi vocale. In precedenza, veniva accompagnato dal nome del driver, il che non serve all'utente finale.
* In presenza di applicazioni incorporate o di buffer virtuali all'interno di altri buffer virtuali (ad esempio il flash), è ora possibile premere NVDA+control+spazio per uscire dall'applicazione incorporata o dal buffer virtuale e tornare al documento che la contiene. In precedenza, NVDA+spazio veniva usato per tale scopo. Ora NVDA+spazio viene utilizzato per cambiare tra modalità esplorazione e modalità focus nel buffer virtuale.
* Se viene focalizzato il visualizzatore sintesi vocale (menu strumenti), il nuovo testo non apparirà fino a quando il focus non sarà spostato altrove. Questo permette una selezione del testo molto agevole (ad esempio per copiarlo).
* Le finestre visualizzatore log e Console Python sono già ingrandite quando vengono attivate.
* Quando si evidenzia un foglio di lavoro in Excel e c'è più di una cella selezionata, l'intervallo di selezione viene annunciato, piuttosto che solo la cella attiva. (#763)
* Il salvataggio della configurazione e alcune opzioni importanti sono disabilitate in presenza di schermate logon o UAC.
* Espeak è aggiornata alla versione 1.44.03.
* Se NVDA è già in esecuzione, la pressione del tasto rapido ctrl+alt+n provocherà il riavvio dello screen reader.
* Rimossa la casella di controllo "annuncia il testo sotto il mouse" e sostituita con "attiva trascinamento mouse", che si adatta meglio allo script (nvda+m).
* Aggiornato il layout laptop che ora contiene tutte le scorciatoie da tastiera e funziona anche su tutte le tastiere non inglesi. (#798, #800)
* Migliorata in modo significativo la documentazione, con l'aggiunta tra l'altro di tutti i comandi tastiera anche per layout laptop e sincronizzazione automatica con la guida rapida che contiene solo i comandi da tastiera. (#455)
* Le tabelle liblouis sono aggiornate alla versione 2.1.1. Da notare un sensibile miglioramento al braille cinese e l'aggiunta di caratteri nuovi alle tabelle. (#484, #499)

### Bug corretti

* In µTorrent, l'elemento evidenziato nell'elenco dei torrent non viene più ripetuto continuamente e non verrà perso il focus dopo l'apertura di un menu.
* In µTorrent, ora vengono annunciati i nomi dei files nella lista torrent.
* Nelle applicazioni Mozilla, il focus viene individuato correttamente quando si finisce in una tabella vuota o in una visualizzazione ad albero.
* Nelle applicazioni Mozilla, la voce "non attivato" viene correttamente riportata nelle caselle di controllo nelle celle delle tabelle. (#571)
* Nelle applicazioni Mozilla, il testo presente nelle sezioni Aria ora viene annunciato. (#630)
* In Internet Explorer e altri controlli MShtml, vengono rispettati i livelli degli attributi nelle sezioni Aria.
* Corretto un crash abbastanza raro in Internet Explorer nella navigazione tra frames e iframes.
* Migliorata la gestione tipi e ruoli Aria in Internet Explorer.
* In Microsoft Word viene letto nuovamente il testo con righe da destra a sinistra, come la scrittura araba. (#267)
* Decisamente abbassati i tempi d'attesa in presenza di grandi quantità di testo nelle finestre Console sui sistemi a 64 bit. (#622)
* Se Skype è già attivo quando viene avviato NVDA, non è necessario riavviare Skype per attivare le opzioni di accessibilità.
* Nelle applicazioni Microsoft Office, NVDA non crasha più alla pressione del tasto NVDA+b o esplorando le barre degli strumenti. (#616)
* Corretta la pronuncia inesatta dei numeri che contengono uno 0 dopo il separatore; esempio: 1,023. (#593)
* Adobe Acrobat Pro e Reader non crashano più in concomitanza della chiusura di un documento o altre operazioni. (#613)
* Viene correttamente annunciata la selezione del tasto alla pressione della combinazione di tasti control+a in alcuni Editor, ad esempio Microsoft Word. (#761)
* Nei controlli Scintilla (ad esempio Notepad++), il testo viene ora selezionato in maniera corretta quando NVDA si sposta con comandi dire tutto. (#746)
* Risulta nuovamente possibile esplorare il testo presente nelle celle di Microsoft Excel con il cursore di controllo.
* NVDA può nuovamente leggere alcune aree di testo problematiche in Internet Explorer 8. (#467)
* Windows Live Messenger 2009 non si chiude più all'improvviso non appena lo si esegue se NVDA è in esecuzione. (#677)
* Nei Browsers web, non è più necessario premere Tab per interagire con gli oggetti incorporati (come i contenuti di tipo flash) dopo aver premuto l'invio sull'oggetto o arrivandoci da un'altra applicazione. (#775)
* Nei controlli Scintilla (ad esempio Notepad++), l'inizio di una riga lunga non viene più troncato in concomitanza dello scorrimento dello schermo. Inoltre, queste righe verranno visualizzate correttamente in Braille quando sono selezionate.
* in LoudTalks, è ora possibile accedere all'elenco contatti.
* L'URL del documento e "MSAAHTML Registered Handler" non vengono più annunciati sporadicamente in Internet Explorer e altri controlli MSHtml. (#811)
* Nelle visualizzazioni ad albero in Eclipse Ide, l'elemento precedentemente evidenziato non viene più annunciato erroneamente quando il focus si sposta su di un altro elemento.
* NVDA ora funziona correttamente in quei sistemi dove la directory di lavoro è stata rimossa dal percorso di ricerca DLL (impostando la chiave di registro CWDIllegalInDllSearch al valore 0xFFFFFFFF). Si noti che questo non dovrebbe essere di interesse per la stragrande maggioranza degli utenti. (#907)
* Quando i comandi di navigazione tabella sono usati al di fuori di una tabella in Microsoft Word, non viene più annunciato "bordo della tabella" dopo "non in una tabella". (#921)
* Quando non ci si può più spostare in una tabella di Microsoft Word con i comandi di navigazione perche' si è raggiunto il bordo della stessa, la frase "bordo della tabella" viene ora annunciata nella lingua dell'utente piuttosto che soltanto in inglese. (#921)
* In Outlook Express, Windows Mail e Windows Live Mail, lo stato delle caselle di controllo nell'elenco regole viene riportato correttamente. (#576)
* La descrizione delle regole può essere letta anche in Windows Live Mail 2010.

## 2010.1

Questa release si è concentrata principalmente nella risoluzione di bug e in una maggiore facilità di approccio agli utenti, in quanto il programma ora è molto più stabile.

### Nuove caratteristiche

* NVDA non si rifiuterà più di avviarsi in sistemi privi di una scheda audio. Naturalmente, è auspicabile utilizzare un display braille oppure il visualizzatore sintesi vocale. (#425)
* Una casella di controllo chiamata annuncia sezioni è stata inserita nella finestra di dialogo formato documento, che permette a NVDA di annunciare le sezioni nel buffer virtuale. Per ragioni di compatibilità con le versioni precedenti, l'opzione è attivata di default.
* Se l'opzione annunciare tasti di comando è attivata, NVDA annuncerà anche i tasti multimediali (play, stop, homepage, etc) presenti in molte tastiere. (#472)
* NVDA ora annuncia la parola che viene cancellata alla pressione della combinazione ctrl+backspace nei controlli che lo prevedono. (#491)
* e'  possibile utilizzare le frecce per scorrere il testo anche nelle finestre di Web Formator. (#452)
* L'elenco contatti nella gestione indirizzi di Microsoft Office Outlook è ora supportata.
* NVDA ora supporta meglio alcuni campi editazione incorporati in documenti in Microsoft Internet Explorer. (#402)
* Un nuovo script (NVDA+Shift+Meno del tastierino numerico) permette di spostare  il cursore di sistema alla posizione del navigatore ad oggetti.
* Nuovo script per bloccare/sbloccare i pulsanti sinistro/destro del mouse. Utile per operazioni di trascinamento. Shift+numlock+diviso per il tasto sinistro, shift+numlock+moltiplicato per il destro.
* Nuove tabelle di traduzione Braille: German 8 punti computer braille, German grade 2, Finlandese 8 punti computer braille, Cinese (Hong Kong, Cantonese), Cinese (Taiwan, Mandarino). (#344, #369, #415, #450)
* Ora è possibile in fase di installazione disabilitare la creazione del tasto caldo per avviare NVDA. (#518)
* NVDA può avvalersi delle Iaccessible2 quando presenti in applicazioni a 64 bit. (#479)
* Migliorato il supporto alle live region nelle applicazioni Mozilla. (#246)
* E' ora presente NVDA Controller Client API, che permette alle applicazioni di interagire con NVDA; ad esempio annunciare del testo, silenziare la sintesi, far apparire messaggi in Braille, etc.
* Vengono ora annunciati messaggi di informazione e di errore nelle finestre di logon in Windows Vista e Windows7. (#507)
* In Adobe Reader, i form interattivi pdf prodotti con Adobe LiveCycle sono ora accessibili. (#475)
* In Miranda Im, NVDA è in grado di annunciare automaticamente i messaggi chat, se la funzione di rilevamento cambiamento contenuto dinamico è attiva. Inoltre, sono stati aggiunti comandi per leggere gli ultimi 3 messaggi (NVDA+control+numeri). (#546)
* Nei contenuti di tipo Adobe Flash sono supportati i campi editazione. (#461)

### Cambiamenti

* Non viene più annunciato il messaggio ridondante di aiuto tastiera in Windows7.
* La funzione Display Synth è stata sostituita con il visualizzatore sintesi. Per attivarla, selezionare visualizzatore sintesi dal menù strumenti. Può venir utilizzato indipendentemente dal tipo di sintesi in uso. (#44)
* I messaggi nei Display Braille verranno automaticamente rimossi non appena l'utente preme un tasto che opera un cambiamento come lo spostamento del focus. In precedenza il messaggio sarebbe rimasto per tutta la durata del tempo per il quale era stato configurato.
* L'impostazione inerente se il display braille deve seguire il focus o il cursore di controllo  (NVDA+control+t) può essere modificata anche dal menù braille presente nel menù preferenze, e viene anche salvata nel file di configurazione.
* Aggiornata la sintesi Espeak alla versione 1.43.
* Aggiornato il pacchetto LibLouis alla versione 1.8.0.
* Nel buffer virtuale, è stato sensibilmente migliorato l'annuncio degli elementi quando ci si sposta o per carattere o a parole. In precedenza, venivano annunciate molte informazioni irrilevanti e il comportamento era molto diverso rispetto a quando ci si spostava riga per riga. (#490)
* Il tasto Control ora interrompe la sintesi come qualsiasi altro tasto, piuttosto che metterla in pausa. Per metterla in pausa e farla ripartire, usare il tasto shift.
* I numeri di riga e colonna di una tabella non vengono più annunciati in concomitanza con cambiamenti del focus, in quanto troppo ridondante e poco utile.

### Bug Corretti

* NVDA non si rifiuta più di avviarsi nel caso in cui il supporto per Ui Automation sembra esistere ma fallisce nell'inizializzazione per qualche motivo. (#483)
* L'intero contenuto della riga di una tabella non viene più annunciato sporadicamente quando viene spostato il focus all'interno di una cella nelle applicazioni Mozilla. (#482)
* NVDA non presenta più lunghi tempi d'attesa nel caso in cui si espandano elementi con visualizzazione ad albero contenenti un gran numero di sotto-elementi.
* Quando vengono elencate le voci Sapi5, NVDA intercetta voci non valide e non le include nella lista. In precedenza, in presenza di una voce difettosa, il driver Sapi5 si rifiutava di avviarsi.
* Il buffer virtuale ora rispetta l'impostazione "annuncia tasto caldo dell'oggetto", situata nella finestra di dialogo presentazione oggetti. (#486)
* Nel Buffer Virtuale, le coordinate riga/colonna non vengono più lette in maniera non corretta per intestazioni di riga e colonna quando l'annuncio delle tabelle è disattivato.
* Nel Buffer Virtuale, le coordinate riga/colonna vengono lette correttamente quando si esce da una tabella e poi si ritorna nella medesima cella, senza esplorare altre celle; ad esempio premendo freccia su e poi freccia giù nella prima cella di una tabella. (#378)
* Le linee vuote in documenti Microsoft Word e nei controlli editazione Microsoft HTML vengono ora visualizzate in maniera appropriata in Braille. In precedenza, NVDA mostrava la frase attuale, non la riga. (#420)
* Risolti molti problemi di sicurezza quando NVDA deve interagire con finestre di Logon e altri controlli UAC. (#515)
* Viene correttamente aggiornata la posizione del cursore di sistema quando si impartisce il comando dire tutto per cui il cursore arriva a fine schermo e deve scorrere, nei campi editazione standard di Windows e nei documenti Microsoft Word. (#418)
* Nel Buffer Virtuale, il testo non è più incluso non correttamente per immagini all'interno di links e controlli cliccabili che sono irrilevanti per gli screen readers. (#423)
* Correzioni al Layout tastiera Laptop. (#517)
* Quando il Braille segue il cursore di controllo e ci si trova in una finestra Dos, tale cursore può ora esplorare correttamente il testo.
* Quando si utilizza TeamTalk3 o TeamTalk4 Classic, la barra di avanzamento Vu Meter nella finestra principale non viene più annunciata ogni volta che si aggiorna. Vengono anche letti correttamente caratteri speciali nella finestra dei messaggi ricevuti.
* Nel Menù Avvio di Windows7, gli elementi non vengono più letti due volte. (#474)
* L'attivazione di links sulla stessa pagina in Mozilla Firefox 3.6 sposta ora il buffer virtuale nel posto esatto.
* Risolto un problema che non permetteva la lettura del testo in alcuni documenti pdf.
* NVDA non interpreta più erroneamente certi numeri scritti col trattino; esempio 500-1000. (#547)
* In Windows Xp, NVDA non provoca più il rallentamento in Internet Explorer quando vengono attivate/disattivate le caselle di controllo. (#477)
* Quando viene usata la sintesi interna ESpeak, l'emissione simultanea di parole e beep non provoca più il rallentamento in alcuni sistemi. Questo accadeva soprattutto nella copia di grosse quantità di dati in Windows Explorer.
* NVDA non annuncia più quando un documento in Firefox diventa occupato (dovuto ad esempio ad un aggiornamento) quando quel documento è in secondo piano. Questo provocava anche l'annuncio sporadico delle barre di stato di alcuni programmi.
* Quando si cambia il tipo di tastiera con control+Shift o Alt+Shift, viene annunciato il nome completo del layout sia in voce che in braille. In precedenza, veniva annunciato solo dalla sintesi vocale e Layout alternativi come Dvorak non venivano riportati.
* Se l'annuncio delle tabelle è disattivato, informazioni sulla tabella non vengono più riportate quando il focus cambia.
* Alcuni controlli standard nelle visualizzazioni ad albero in applicazioni a 64 bit (ad esempio la visualizzazione ad albero in Microsoft HTML Help) sono ora accessibili. (#463)
* Risolti alcuni problemi mentre vengono loggati messaggi contenenti caratteri non ascii.  Questo causava errori casuali su sistemi non inglesi. (#581)
* I contenuti presenti nella finestra informazioni vengono ora presentati nella lingua dell'utente e non solo in inglese. (#586)
* Sono stati risolti i problemi quando si utilizzano le opzioni per cambiare al volo i parametri del sintetizzatore dopo aver cambiato la voce in una che dispone di meno settaggi della precedente.
* In Skype 4.2, i nomi dei contatti non vengono più annunciati due volte mentre si scorre la lista contatti.
* Sistemati alcuni potenziali problemi con la memoria con interfacce Gui e con i buffer virtuali. (#590, #591)
* Risolto un fastidioso bug che provocava il crash quando si utilizzavano alcune voci Sapi4. (#597)

## 2009.1

Le maggiori novità di questa release riguardano la capacità di funzionare anche con le versioni a 64 bit di Windows; migliorato sensibilmente il supporto ai documenti Adobe Reader e Microsoft Internet Explorer; supporto a Windows7; lettura delle finestre di Logon, schermate Control+Alt+Canc e UAC (User Account Control); e l'abilità di interagire con i controlli Adobe Flash e Sun Java nelle pagine web. Inoltre ci sono stati grossissimi miglioramenti per quel che riguarda la stabilità e l'interfaccia utente.

### Nuove Caratteristiche

* Supporto ufficiale alle versioni a 64 bit di Windows! (#309)
* Aggiunto il supporto ai sintetizzatori Newfon. (nota, non commercializzato in Italia, richiede una speciale versione del sintetizzatore e la lingua parlata è russo ed ucraino). (#206)
* Nel buffer virtuale, le impostazioni della modalità focus o della modalità buffer virtuale possono venir riportate tramite suoni, che e' l'impostazione predefinita, oltre che normalmente annunciate a parole. In pratica, vi saranno dei beep all'attivazione/disattivazione della modalità focus. (#244)
* La sintesi vocale non smette più di funzionare quando l'utente modifica il volume con la tastiera, naturalmente per quelle tastiere che prevedono tale funzione, permettendo quindi di continuare ad usare lo screen reader correttamente. (#287)
* totalmente riscritto il supporto per Internet Explorer e Acrobat Reader. Tale funzione è stata inglobata con il supporto per Firefox, cosicche' ora è possibile utilizzare tutte le facilitazioni e i tasti rapidi presenti, nonche' il supporto braille nelle pagine web. Non ci dovrebbero essere più differenze tra Firefox e Internet Explorer in fase di navigazione.
* migliorata la gestione del controllo della selezione Data/ora in Windows Vista.
* Migliorato il supporto al nuovo menù di avvio di Windows Xp, in special modo dalla voce tutti i programmi, i livelli vengono pronunciati correttamente.
* La quantità di testo che viene letta scorrendo con il mouse ora è configurabile dalle impostazioni Mouse: le scelte disponibili sono paragrafo, riga, parola e carattere.
* In Microsoft Word ora vengono notificati gli errori ortografici della parola corrente.
* Supporto per il controllo ortografico di Microsoft Word 2007. Altre versioni di Word possono funzionare ma non è garantito.
* Supporto per Windows Mail, nello specifico, vengono letti correttamente anche i messaggi in testo semplice.
* In Windows Vista, quando appare la finestra di sicurezza di richiesta di autorizzazione dell'utente, oppure quando l'utente preme ctrl+alt+canc, NVDA notifica che non ci si trova più nell'interfaccia classica ed accessibile.
* NVDA è in grado di leggere il testo sotto il Mouse anche nelle finestre Dos.
* Supporto per la tecnologia Ui Automation  presente in Windows7, che renderà la gestione di tale sistema operativo molto più agevole da parte dello screen reader.
* NVDA può essere impostato in modo da venir eseguito automaticamente all'avvio di Windows, subito dopo aver effettuato il login, sempre che ve ne sia bisogno. L'opzione si trova nella schermata di configurazione generale, solo per NVDA Installer.
* NVDA è in grado di leggere le videate inerenti la sicurezza, le finestre di login e quelle generate premendo la combinazione di tasti ctrl+alt+canc, a partire da Windows XP in poi. Anche questa impostazione la si trova in preferenze, impostazioni generali, solo per NVDA Installer. (#97)
* Aggiunto un driver per i display Braille Optelec ALVA BC6 series.
* In una pagina web, è possibile premere i tasti n e shift+n per saltare interi blocchi di link.
* In una pagina web, vengono riportate le "sezioni", in inglese ARIA Landmarks. E' possibile passare da una sezione all'altra con i tasti d o Shift+d. (#192)
* L'elenco dei links che si richiamava con la combinazione di tasti NVDA+f7 è ora diventata una finestra di dialogo con la possibilità da parte dell'utente di filtrare cosa visualizzare tra links, intestazioni e sezioni. Si noti che intestazioni e sezioni vengono presentate in modo gerarchico. (#363)
* Questa nuova finestra di dialogo è in grado di filtrare anche gli elementi man mano che l'utente scrive. Esempio aggiuntivo del traduttore di questo documento: se premiamo NVDA+f7, e ci troviamo con un elenco di 55 links ed iniziamo a scrivere qualcosa, per esempio la lettera l, ci verranno mostrati solo quei links che contengono al loro interno la lettera l. Possiamo scrivere qualunque cosa, anche parole intere, in questo modo andremo direttamente sul link o l'elemento specifico, ad esempio se scrivo "video", e tale elemento esiste sulla pagina, mi verrà visualizzato soltanto il link "video" e premendo invio verrà attivato. Si noti che premendo Backspace verranno resettati i filtri e tutti gli elementi saranno visualizzati nuovamente. (#173)
* La versione portatile di NVDA ora ricerca le configurazioni dell'utente nella cartella user Config situata all'interno della cartella NVDA. In questo modo, come avviene con la versione installer, seppur con percorsi diversi, le configurazioni dell'utente sono indipendenti dalla struttura principale di NVDA.
* Moduli personalizzati per le applicazioni, driver di sintesi vocali e driver per Display Braille possono essere salvati nella cartella userConfig. (#337)
* L'elaborazione di lunghi o complessi documenti riguardanti il buffer virtuale vengono effettuati in background, in modo che l'utente possa interagire con il sistema operativo in altro modo, verrà avvisato non appena il documento sarà stato processato e pronto all'uso.
* Se NVDA si accorge di non funzionare più correttamente, tutti i tasti premuti dall'utente non verranno più intercettati dallo screen reader, in modo da facilitare l'utilizzatore nelle operazioni di recupero del sistema.
* Supporto per le operazioni di trascinamento nei controlli Aria in Mozilla Gecko. (#239)
* Il titolo di un documento e la riga corrente o quella selezionata viene ora annunciato quando il focus viene spostato all'interno del buffer virtuale. (#210)
* Nel Buffer virtuale, è possibile interagire con gli oggetti Adobe Flash o Sun Java premendo invio su di essi. Se l'oggetto è accessibile, premere tab e comportarsi come con qualsiasi altra applicazione. Per ritornare nel buffer virtuale premere NVDA+spazio. (#431)
* Nel Buffer Virtuale, premere O oppure Shift O per spostarsi all'oggetto successivo o precedente.
* NVDA è in grado di funzionare con le applicazioni che richiedono privilegi di amministratore in Windows Vista e successivi. Si noti che questo è valido solo per le versioni installer, non portable. (#397)

### Cambiamenti

* NVDA non pronuncia più "NVDA avviato" quando viene lanciato.
* I suoni di avvio e chiusura dello screen reader vengono eseguiti utilizzando le impostazioni di output scheda audio presenti in NVDA, piuttosto che quelle predefinite di sistema. (#164)
* Migliorata la gestione delle barre di avanzamento. Ora è possibile selezionare come NVDA deve avvertire l'utente sul loro stato, o con segnali acustici, o a parole, o con entrambe le cose.
* Alcuni ruoli generici come pannello, applicazione e frame, non vengono più annunciati se evidenziati a meno che il controllo non abbia un nome.
* Il comando copia dal cursore di controllo (NVDA+f10) copia il testo dal marcatore iniziale fino alla posizione del cursore di controllo, invece di non tenere conto della posizione. Questo permette la copia dell'ultimo carattere di una riga che in precedenza non era possibile. (#430)
* Lo script navigatorObject_where (ctrl+NVDA+numpad5) è stato rimosso in quanto non funzionava su tutte le tastiere.
* Lo script direPosizioneNavigatoreOggetti è stato assegnato alla combinazione di tasti NVDA+Canc del tastierino numerico. Prima non funzionava su tutte le tastiere. Lo script ora annuncia anche altezza e larghezza dell'oggetto.
* Migliorate le prestazioni (specialmente con i netbooks) quando vi sono molti beeps in rapida successione, ad esempio rapidi movimenti del mouse con coordinate audio attivate. (#396)
* Il suono di errore di NVDA non viene più riprodotto nelle versioni candidate e definitive, anche se gli errori vengono comunque loggati.

### Bug corretti

* Quando NVDA viene eseguito da un percorso Dos standard, nome di 8 caratteri seguito da un punto e estensioni di 3 caratteri, ma è installato nel relativo percorso con nome lungo (esempio:  progra~1 punta a programmi), NVDA  sarà in grado di identificare che si sta eseguendo una versione installata e caricherà i settaggi dell'utente.
* la funzione insert+t che permette di leggere il titolo della finestra corrente ora funziona anche se premuta all'interno di un menù.
* non vengono più visualizzate informazioni inutili sulla riga Braille in presenza di elementi non etichettati.
* Non vengono più annunciate informazioni inutili quando si passa da un elemento ad un altro in applicazioni Java o lotus-notes.
* Migliorata la gestione delle ricerche nelle finestre di aiuto delle applicazioni (.hlp, .chm).
* Viene riportato correttamente il numero di pagina nei documenti Word.
* Migliorato il supporto della gestione dei campi editazione in Microsoft Word nelle finestre di dialogo, ad esempio quella inerente la gestione caratteri/font. Utilizzare i tasti cursore per navigare in questi controlli.
* Migliorato il supporto alle finestre del prompt dei comandi, soprattutto in quelle circostanze in cui NVDA non riconosceva alcun carattere.
* In Windows Vista e versioni successive l'Installer di NVDA eseguirà il programma con i privilegi effettivi dell'utente quando la casella di controllo Esegui NVDA è attivata.
* Il tasto Backspace ora non crea più problemi quando NVDA è configurato per pronunciare le parole digitate.
* Non viene più riportata erroneamente la voce menù avvio in alcuni menù di contesto in esplora risorse. (#257)
* NVDA ora interpreta correttamente le etichette Aria in Mozilla Gecko quando non esiste altro contenuto. (#156)
* NVDA non abilita più automaticamente la modalità focus nei campi editazione di testo che aggiornano il proprio valore quando cambia il focus; ad esempio https://tigerdirect.com/. (#220)
* NVDA cercherà di recuperare alcune situazioni nelle quali in precedenza si bloccava per lunghi periodi. Sono necessari circa 10 secondi allo screen reader per riavviarsi.
* Quando la lingua di NVDA è impostata su "User Default", viene usata la lingua scelta dall'utente nelle impostazioni lingua di Windows, piuttosto che altre opzioni. (#353)
* NVDA ora riconosce l'esistenza di controlli in AIM7.
* Il comando passa tasto attraverso non presenta più problemi se un tasto viene tenuto premuto. In precedenza NVDA si rifiutava di accettare comandi quando questo capitava.  (#413)
* La barra delle applicazioni non viene più ignorata quando viene evidenziata, che accade spesso quando si esce da un programma. In precedenza, NVDA si comportava come se il focus non fosse cambiato affatto.
* Quando si legge del testo in applicazioni che fanno uso di Java Access Bridge (incluso OpenOffice.org), NVDA ora funziona correttamente quando l'opzione dire i numeri di riga è abilitata.
* Il comando Copia dal cursore di controllo (NVDA+f10) ora prevede la circostanza in cui venga usato prima del marcatore d'inizio.  In precedenza, questo poteva causare problemi, come il crash in Notepad++.
* Il carattere di controllo (0x1) non provoca più strani comportamenti di Espeak come cambio di volume o tono quando viene incontrato. (#437)
* Il comando dire testo selezionato (NVDA+Shift+freccia su) ora avverte che non esiste alcuna selezione in oggetti che non supportano la selezione del testo.
* Risolto un problema che provocava il blocco di NVDA durante la pressione di alcuni bottoni o links in Miranda IM. (#440)
* La riga o la selezione corrente viene rispettata quando viene fatto lo spelling o viene copiato l'oggetto attuale del navigatore.
* Si è cercato di lavorare su un bug di Windows che provocava la lettura di caratteri senza senso dopo il nome dei link nelle finestre di dialogo in Esplora risorse e Internet Explorer. (#451)
* Risolto un problema con il comando Annuncia data/ora (NVDA+f12). In precedenza, l'annuncio della data veniva troncato in alcuni sistemi. (#471)
* Risolto un problema che provocava inavvertitamente la cancellazione del flag Screen Reader di sistema dopo aver interagito con le schermate di sicurezza di Windows. Questo poteva creare delle difficoltà a quelle applicazioni che controllano il flag Screen Reader di Sistema come Skype, Adobe Reader e Jart. (#462)
* Nelle caselle combinate di  Internet Explorer 6, viene annunciato l'elemento attivo quando cambia. (#342)

## 0.6P3

### Nuove caratteristiche

* Poiche' la gestione Formule in Excel è inacessibile a NVDA, viene fornita una specifica finestra di dialogo con campi editazione modificabili dall'utente.
* Supporto alla formattazione nei controlli di testo Iaccessible2, comprese le applicazioni Mozilla.
* Gli errori grammaticali ora possono essere annunciati dove possibile. Questo è configurabile dalla finestra di dialogo formato documento.
* NVDA può essere configurato ad emettere beep per tutte le barre di progresso o solo per quelle visibili. In alternativa, NVDA può essere configurato ad annunciare il valore delle barre di progresso ogni 10%.
* I links possono essere individuati nei controlli Richedit.
* Ora il mouse può essere spostato alla posizione del carattere del cursore di controllo nella maggior parte dei controlli di testo editabili. In precedenza il mouse poteva essere spostato solo al centro del controllo.
* Nei buffer virtuali, il cursore di controllo ora può esplorare il testo del buffer, piuttosto che soltanto il testo interno del navigatore ad oggetti (che spesso non è utile all'utente). Questo significa che è possibile esplorare la gerarchia del buffer virtuale utilizzando la navigazione ad oggetti e il cursore di controllo si sposterà in quel punto del buffer.
* Prevista la gestione di alcuni stati aggiuntivi dei controlli Java.
* Se il comando dire titolo (NVDA+t) viene premuto due volte, verrà fatto lo spelling del titolo. Se premuto tre volte, verrà copiato negli appunti.
* L'aiuto tastiera ora è in grado di leggere i nomi dei tasti funzione se premuti da soli.
* I nomi dei tasti annunciati dall'aiuto tastiera sono ora traducibili.
* Aggiunto il supporto ai campi di testo riconosciuto in SiRecognizer. (#198)
* Supporto per i Display Braille!
* Aggiunto un comando (NVDA+c) per annunciare il testo contenuto negli appunti. (#193)
* Nei Buffer Virtuali, se NVDA passa automaticamente alla modalità Focus, si può usare il tasto Esc per tornare alla modalità esplorazione. NVDA+spazio può ancora essere utilizzato.
* Nei buffer virtuali, quando il focus cambia o il cursore viene spostato, NVDA può passare automaticamente alla modalità focus o esplorazione a seconda del controllo sul cursore. L'opzione è configurabile dalle impostazioni del buffer virtuale. (#157)
* Riscritto il Driver per i sintetizzatori Sapi4 che prende il posto dei due driver precedenti Microsoft e Serotek, e che dovrebbe risolvere i problemi che si incontravano con quest'ultimi.
* L'applicazione NVDA ora include il Manifest, che significa che non viene più eseguita in modalità compatibilità in Windows Vista.
* Il file di configurazione e i dizionari vengono salvati nella cartella dati applicazione dell'utente se è stato usato l'Installer. Questo è necessario in Windows Vista e permette a più utenti di avere configurazioni diverse di NVDA.
* Aggiunto il supporto per informazioni sulla posizione per i controlli IAccessible2.
* Inserita la possibilità di copiare testo negli appunti utilizzando il cursore di controllo. NVDA+f9 imposta il marcatore iniziale alla posizione attuale del cursore di controllo. NVDA+f10 recupera il testo tra il marker iniziale e la posizione attuale del cursore di controllo e lo copia negli appunti. (#240)
* Aggiunto il supporto ad alcuni campi editazione in Programmi Pinacle Tv.
* Quando viene annunciata una gran quantità di testo selezionato (sopra i 512 caratteri), NVDA ora dice il numero di caratteri selezionati piuttosto che annunciare l'intera selezione. (#249)

### Cambiamenti

* Se il dispositivo d'uscita audio è impostato a quello predefinito di Windows (Microsoft sound mapper), NVDA ora passerà al nuovo dispositivo predefinito per Espeak e i Toni quando il dispositivo predefinito cambia. Ad esempio, NVDA passerà su una scheda audio USB se essa è quella predefinita e viene connessa.
* Migliorate le prestazioni di Espeak con alcuni drivers audio per Windows Vista.
* L'annuncio di links, intestazioni, tabelle, elenchi e blocchi tra virgolette può essere configurato dalla finestra di dialogo formato documento. In precedenza per configurare queste impostazioni per il buffer virtuale, questi parametri erano situati nella finestra buffer virtuale.
* La velocità ora è l'impostazione predefinita quando si cambiano al volo i parametri del sintetizzatore.
* Migliorato il caricamento e lo scaricamento di moduli aggiuntivi (appmodules).
* Il comando dire titolo (NVDA+t) ora annuncia solo il titolo piuttosto che l'intero oggetto. Se l'oggetto in primo piano non ha un nome, viene usato il nome del processo dell'applicazione.
* Invece della dicitura passa attraverso il buffer virtuale attivato/disattivato, NVDA annuncerà modalità focus o modalità esplorazione.
* Le voci ora vengono salvate nel file di configurazione con l'ID invece che con l'indice. (#19)
* Il livello degli elementi nelle visualizzazioni ad albero è ora annunciato per prima se è stato cambiato dall'elemento precedentemente evidenziato per tutte le visualizzazioni ad albero. In precedenza, questo avveniva solo per le finestre di visualizzazioni ad albero native (SysTreeView32).

### Bug risolti

* L'ultimo frammento d'audio non viene più troncato quando si usa NVDA con Espeak in un server desktop remoto.
* Risolto un problema nel salvataggio dizionari per alcune voci.
* Eliminato il ritardo quando ci si sposta per unità diverse dal carattere (parole, righe, etc) fino alla fine del documento nel buffer virtuale nelle applicazioni Mozilla Gecko. (#155)
* Se è abilitata la funzione leggi parole digitate, la parola viene annunciata anche quando viene premuto invio.
* Risolti alcuni problemi con set di caratteri in documenti richedit.
* Il visualizzatore log di NVDA ora utilizza RichEdit piuttosto che soltanto edit per mostrare i log. Questo migliora la lettura parola per parola in NVdA.
* Risolti alcuni problemi relativi agli oggetti incorporati in controlli richedit.
* NVDA ora legge i numeri di pagina in Microsoft Word. (#120)
* Risolto il problema laddove giungendo con il tab in una casella di controllo attivata con il buffer virtuale in Mozilla Gecko, premendo il tasto spazio non veniva notificato che la casella diventava disattivata.
* Le caselle di controllo parzialmente attivabili sono ora annunciate correttamente nelle applicazioni Mozilla.
* Se la selezione del testo si espande o si restringe in entrambe le direzioni, la selezione verrà letta come una sola porzione anziché due.
* Quando si legge con il mouse, il testo nei campi editazione Mozilla Gecko ora dovrebbe venir annunciato.
* Dire tutto non dovrebbe più causare crash con sintesi Sapi5.
* Risolto un problema che faceva in modo che i cambiamenti di selezione del testo non venivano letti nei controlli standard di Windows.
* Sistemato il trascinamento Mouse negli oggetti Java. (#185)
* NVDA non annuncia più elementi nella visualizzazione ad albero Java come espandibili se non hanno sottoelementi.
* Annuncio dell'oggetto con il focus quando una finestra Java appare in primo piano.
* Il Driver della sintesi Espeak non smette più di parlare dopo un errore.
* Risolto un problema che non permetteva il salvataggio dei parametri della voce se modificati al volo e non tramite menù.
* Migliorata la lettura delle parole e dei caratteri digitati.
* Alcuni frammenti di testo che prima non venivano letti (esempio giochi di avventura nelle console di testo) ora vengono correttamente annunciati.
* NVDA ora ignora i cambiamenti del focus nelle finestre in secondo piano.
* Migliorato il rilevamento del focus quando si esce dai menù di contesto.
* NVDA ora annuncia quando viene attivato un menù di contesto nel menù avvio.
* Il menù avvio classico di Windows è annunciato come menù avvio invece che menù applicazione.
* Migliorata la gestione degli avvisi, ad esempio quelli incontrati in Mozilla Firefox. Il testo non verrà più letto molte volte. (#248)
* Il testo di campi editazione evidenziabili e di sola lettura non verrà più incluso quando vengono recuperate informazioni sulle finestre di dialogo. Questo risolve, ad esempio, la lettura automatica delle intere licenze negli installer.
* NVDA non annuncia più la deselezione del testo uscendo da certi campi editazione (esempio: barra degli indirizzi di Internet Explorer, campi indirizzi in Thunderbird3).
* Quando viene aperta un'email solo testo in Outlook Express e Windows Mail, il focus viene correttamente posizionato sul messaggio, che diventa pronto alla lettura. In precedenza l'utente era costretto ad avvalersi del tasto tab per accedere al messaggio.
* Risolti molti problemi con la funzione "leggi i tasti di comando".
* NVDA può leggere testi più lunghi di 65535 caratteri nei controlli editazione standard (ad esempio Notepad).
* Migliorata la lettura delle righe nei controlli editazione MSHTML (campi di immissione testo in Internet Explorer e messaggi modificabili in Microsoft Outlook Express).
* NVDA non si blocca più quando legge il testo in OpenOffice. (#148, #180)

## 0.6p2 (da qui in inglese)

* Improved the default ESpeak voice in NVDA
* Added a laptop keyboard layout. Keyboard layouts can be configured from NVDA's  Keyboard settings dialog. (#60)
* Support for grouping items in SysListView32 controls, mainly found in Windows Vista. (#27)
* Report the checked state of treeview items in SysTreeview32 controls.
* Added shortcut keys for many of NVDA's configuration dialogs
* Support for IAccessible2 enabled applications such as Mozilla Firefox when running NVDA from portable media, with out having to register any special Dll files
* Fix a crash with the virtualBuffers Links List in Gecko applications. (#48)
* NVDA should no longer crash Mozilla Gecko applications such as Firefox and Thunderbird if NVDA is running with higher privilages than the Mozilla Gecko application. E.g. NVDA is  running as Administrator.
* Speech dictionaries (previously User dictionaries) now can be either case sensitive or insensitive, and the patterns can optionally be regular expressions. (#39)
* Whether or not NVDA uses a 'screen layout' mode for virtual buffer documents can now be configured from a settings dialog
* No longer report anchor tags with no href in Gecko documents as links. (#47)
* The NVDA find command now remembers what you last searched for, across all applications. (#53)
* Fix issues where the checked state would not be announced for some checkboxes and radio buttons in virtualBuffers
* VirtualBuffer pass-through mode is now specific to each document, rather than NVDA globally. (#33)
* Fixed some sluggishness with focus changes and incorrect speech interuption which sometimes occured when using NVDA on a system that had been on standby or was rather slow
* Improve support for combo boxes in Mozilla Firefox. Specifically when arrowing around them text isn't repeated, and when jumping out of them, ancestor controls are not announced unnecessarily. Also virtualBuffer commands now work when focused on one  when you are in a virtualBuffer.
* Improve accuracy of finding the statusbar in many applications. (#8)
* Added the NVDA interactive Python console tool, to enable developers to look at and manipulate NVDA's internals as it is running
* sayAll, reportSelection and reportCurrentLine scripts now work properly when in virtualBuffer pass-through mode. (#52)
* The increase rate and decrease rate scripts have been removed. Users should use the synth settings ring scripts (control+nvda+arrows) or the Voice settings dialog
* Improve the range and scale of the progress bar beeps
* Added more quick keys to the new virtualBuffers:  l for list, i for list item, e for edit field, b for button, x for checkbox, r for radio button, g for graphic, q for blockquote, c for combo box, 1 through 6 for respective heading levels, s for separator, m for frame. (#67, #102, #108)
* Canceling the loading of a new document in Mozilla Firefox now allows the user to keep using the old document's virtualBuffer if the old document hadn't yet really been destroyed. (#63)
* Navigating by words in virtualBuffers is now more accurate as  words do not accidentally contain text from more than one field. (#70)
* Improved accuracy of focus tracking and focus updating when navigating in Mozilla Gecko virtualBuffers.
* Added a findPrevious script (shift+NVDA+f3) for use in new virtualBuffers
* Improved sluggishness in Mozilla Gecko dialogs (in Firefox and Thunderbird). (#66)
* Add the ability to view the current log file for NVDA. it can be found in the NVDA menu -> Tools
* Scripts such as say time and date now take the current language in to account; punctuation and ordering of words now reflects the language
* The language combo box in NVDA's General settings dialog now shows full language names for ease of use
* When reviewing text in the current navigator object, the text is always up to date if it changes dynamically. E.g. reviewing the text of a list item in Task Manager. (#15)
* When moving with the mouse, the current paragraph of text under the mouse is now announced, rather than either all the text in that particular object or just the current word. Also audio coordinates, and announcement of object roles is optional, they are turned off by default
* Support for reading text with the mouse in Microsoft Word
* Fixed bug where leaving the menu bar in applications such as Wordpad would cause text selection to not be announced anymore
* In Winamp, the title of the track is no longer announced again and again when switching tracks, or pausing/resuming/stopping playback.
* In Winamp,  Added ability to announce state of the shuffle and repeat controls as they are switched. Works in the main window and in the playlist editor
* Improve the ability to activate particular fields in Mozilla Gecko virtualBuffers. May include clickable graphics, links containing paragraphs, and other weird structures
* Fixed an initial lag when opening NVDA dialogs on some systems. (#65)
* Add specific support for the Total Commander application
* Fix bug in the sapi4serotek driver where the pitch could get locked at a particular value, i.e. stays high after reading a capital letter. (#89)
* Announce clickable text and other fields as clickable in Mozilla Gecko VirtualBuffers. e.g.  a field which has an onclick HTML attribute. (#91)
* When moving around Mozilla Gecko virtualBuffers, scroll the current field in to view -- useful so sighted peers have an idea of where the user is up to in the document. (#57)
* Add basic support for ARIA live region show events in IAccessible2 enabled applications. Useful in the Chatzilla IRC application, new messages will now be read automatically
* Some slight improvements to help use ARIA enabled web applications,  e.g. Google Docs
* Stop adding extra blank lines to text when copying it from a virtualBuffer
* Stop the space key from activating a link in the Links List. Now it can be used like other letters in order to  start typing the name of a particular link you wish to go to
* The moveMouseToNavigator script (NVDA+numpadSlash) now moves the mouse to the centre of the navigator object, rather than the top left
* Added scripts to click the left and right mouse buttons (numpadSlash and numpadStar respectively)
* Improve access to the Windows System Tray. Focus hopefully should no longer seem to keep jumping back to one particular item. Reminder: to get to the System Tray use the Windows command WindowsKey+b. (#10)
* Improve performance and stop announcing extra text when holding down a cursor key in an edit field and it hits the end
* Stop the ability for NVDA to make the user wait while particular messages are spoken. Fixes some crashes/freezes with particular speech synthesizers. (#117)
* Added support for the Audiologic Tts3 speech synthesizer, contribution by Gianluca Casalino. (#105)
* Possibly improve performance when navigating around documents in Microsoft Word
* Improved accuracy when reading text of alerts in Mozilla Gecko applications
* Stop possible crashes when trying to save configuration on non-English versions of Windows. (#114)
* Add an NVDA welcome dialog. This dialog is designed to provide essential information for new users and allows CapsLock to be configured as an NVDA modifier key. This dialog will be displayed when NVDA is started by default until it is disabled.
* Fix basic support for Adobe Reader so it is possible to read documents  in  versions 8 and 9
* Fix some errors that may have occured when holding down keys before NVDA is properly initialized
* If the user has configured NVDA to save configuration on exit, make sure the configuration is properly saved when shutting down or logging out of  Windows.
* Added an NVDA logo sound to the beginning of the installer, contributed by Victer Tsaran
* NVDA, both running in the installer and otherwise, should properly clean up its system tray icon when it exits
* Labels for standard controls in NVDA's dialogs (such as Ok and cancel buttons) should now show in the language NVDA is set to, rather than just staying in English.
* NVDA's icon should now be  used for  the NVDA shortcuts in the start menu and on the Desktop, rather than a default application icon.
* Read cells in MS Excel when moving with tab and shift+tab. (#146)
* Fix some double speaking in particular lists in Skype.
* Improved caret tracking in IAccessible2 and Java applications; e.g. in Open Office and Lotus Symphony, NVDA properly waits for the caret to move in documents rather than accidentally reading the wrong word or line at the end of some paragraphs. (#119)
* Support for AkelEdit controls found in Akelpad 4.0
* NVDA no longer locks up in Lotus Synphony when moving from the document to the menu bar.
* NVDA no longer freezes in the Windows XP Add/Remove programs applet when launching an uninstaller. (#30)
* NVDA no longer freezes when opening Spybot Search and Destroy

## 0.6p1

### Access to web content with new in-process virtualBuffers (so far for Mozilla Gecko applications including Firefox3 and Thunderbird3)

* Load times have been improved almost by a factor of thirty (you no longer have to wait at all for most web pages to load in to the buffer)
* Added a links list (NVDA+f7)
* Improved the find dialog (control+nvda+f) so that it performs a case-insencitive search, plus fixed a few focus issues with that dialog box.
* It is now possible to select and copy text in the new virtualBuffers
* By default the new virtualBuffers represent the document in a screen layout (links and controls are not on separate lines unless they really are visually). You can toggle this feature with NVDA+v.
* It is possible to move by paragraph with control+upArrow and control+downArrow.
* Improved support for dynamic content
* Improved over all accuracy of reading lines and fields when arrowing up and down.

### Internationalization

* It is now possible to type accented characters that rely on a "dead character", while NVDA is running.
* NVDA now announces when the keyboard layout is changed (when pressing alt+shift).
* The announce date and time feature now takes the system's current regional and language options in to account.
* added czech translation (by Tomas Valusek with help from Jaromir Vit)
* added vietnamese translation by Dang Hoai Phuc
* Added Africaans (af_ZA) translation, by Willem van der Walt.
* Added russian translation by Dmitry Kaslin
* Added polish translation by DOROTA CZAJKA and friends.
* Added Japanese translation by Katsutoshi Tsuji.
* added Thai translation by Amorn Kiattikhunrat
* added croatian translation by Mario Percinic and Hrvoje Katic
* Added galician translation by Juan C. buno
* added ukrainian translation by Aleksey Sadovoy

### Speech

* NVDA now comes packaged with eSpeak 1.33 which contains many improvements, among those are improved languages, named variants, ability to speak faster.
* The voice settings dialog now allows you to change the variant of a synthesizer if it supports one. Variant is usually a slight variation on the current voice. (eSpeak supports variants).
* Added the ability to change the inflection of a voice in the voice settings dialog if the current synthesizer supports this. (eSpeak supports inflection).
* Added the ability to turn off speaking of object position information(e.g. 1 of 4). This option can be found in the Object presentation settings dialog.
* NVDA can now beep when speaking a capital letter. This can be turned on and off with a check box in the voice settings dialog. Also added a raise pitch for capitals check box to configure whether NVDA should actually do its normal pitch raise for capitals. So now you can have either raise pitch, say cap, or beep, for capitals.
* Added the ability to pause speech in NVDA (like found in Voice Over for the Mac). When NVDA is speaking something, you can press the control or shift keys to silence speech just like normal, but if you then tap the shift key again (as long as you havn't pressed any other keys) speech will continue from exactly where it left off.
* Added a virtual synthDriver which outputs text to a window instead of speaking via a speech synthesiser. This should be more pleasant for sighted developers who are not used to speech synthesis but want to know what is spoken by NVDA. There are probably still some bugs, so feedback is most definitely welcome.
* NVDA no longer by default speaks punctuation, you can enable speaking of punctuation with NVDA+p.
* eSpeak by default now speaks quite a bit slower, which should make it easier for people who are using eSpeak for the first time, when installing or starting to use NVDA.
* Added user dictionaries to NVDA. These allow you to make NVDA speak certain text differently. There are three dictionaries: default, voice, and temporary. Entries you add to the default dictionary will happen all the time in NVDA. Voice dictionaries are specific to the current synthesizer and voice you currently have set. And temporary dictionary is  for those times you quickly want to set a rule while you are doing a particular task, but you don't want it to be perminant (it will disappear if you close NVDA). For now the rules are regular expressions, not just normal text.
* Synthesizers can now use any audio output device on your system, by setting the output device combo box in the Synthesizer dialog before selecting the synthesizer you want.

### Performance

* NVDA no longer takes up a huge amount of system memory , when editing messages in mshtml edit controls
* Improved performance when reviewing text inside many controls that do not actually have a real cursor. e.g. MSN Messenger history window, treeview items, listview items etc.
* Improved performance in rich edit documents.
* NVDA should no longer slowly creep up in system memory size for no reason
* Fixed bugs when  trying to focus on a dos console window more than three or so times. NVDA did have a tendency to completely crash.

### Key commands

* NVDA+shift+numpad6 and NVDA+shift+numpad4 allow you to navigate to the next or previous object in flow respectively. This means that you can navigate in an application by only using these two keys with out having to worry about going up by parent, or down to first child as you move around the object hyerarchy. For instance in a web browser such as firefox, you could navigate the document by object, by just using these two keys. If next in flow or previous in flow takes you up and out of an object, or down in to an object, ordered beeps indicate the direction.
* You can now configure voice settings with out opening the voice settings dialog, by using the Synth Settings Ring. The synth settings ring is a group of voice settings you can toggle through by pressing control+NVDA+right and control+NVDA+left. To change a setting use control+NVDA+up and control+NVDA+down.
* Added a command to report the current selection in edit fields (NVDA+shift+upArrow).
* Quite a few NVDA commands that speak text (such as report current line etc) now can spell the text if pressed twice quickly.
* the capslock, numpad insert and extended insert can all be used as the NVDA modifier key. Also if one of these keys is used, pressing the key twice with out pressing any other keys will send the key through to the operating system, just like you'd pressed the key with out NVDA running. To make one of these keys be the NVDA modifier key, check its checkbox in the Keyboard settings dialog (used to be called the keyboard echo dialog).

### Application support

* Improved support for Firefox3 and Thunderbird3 documents. Load times have been improved by almost a factor of thirty, a screen layout is used by default (press nvda+v to toggle between this and no screen layout), a links list (nvda+f7 has been added), the find dialog (control+nvda+f) is now case-insensitive, much better support for dynamic content, selecting and copying text is now possible.
* In the MSN Messenger and Windows Live Messenger history windows, it is now possible to select and copy text.
* Improved support for the audacity application
* Added support for a few edit/text controls in Skype
* Improved support for Miranda instant messenger application
* Fixed some focus issues when opening html and plain text messages in Outlook Express.
* Outlook express newsgroup message fields are now labeled correctly
* NVDA can now read the addresses in the Outlook Express message fields (to/from/cc etc)
* NVDA should be now more accurate at announcing the next message in out look express when deleting a message from the message list.

### APIs and toolkits

* Improved object navigation for MSAA objects. If a window has a system menu, title bar, or scroll bars, you can now navigate to them.
* Added support for the IAccessible2 accessibility API. A part from the ability to announce more control types, this also allows NVDA to access the cursor in applications such as Firefox 3 and Thunderbird 3, allowing you to navigate, select or edit text.
* Added support for Scintilla edit controls (such controls can be found in Notepad++ or Tortoise SVN).
* Added support for Java applications (via the Java Access Bridge). This can provide basic support for Open Office (if Java is enabled), and any other stand-alone Java application. Note that java applets with in a web browser may not work yet.

### Mouse

* Improved support for reading what is under the mouse pointer as it moves. It is now much faster, and it also now has the ability in some controls such as standard edit fields, Java and IAccessible2 controls, to read the current word, not just the current object. This may be of some used to vision impared people who just want to read a specific bit of text with the mouse.
* Added a new config option, found in the mouse settings dialog. Play audio when mouse moves, when checked, plays a 40 ms beep each time the mouse moves, with its pitch (between 220 and 1760 hz) representing the y axis, and left/right volume, representing the x axis. This enables a blind person to get a rough idea of where the mouse is on the screen as its being moved. This feature also depends on reportObjectUnderMouse also being turned on. So this means that if you quickly need to disable both beeps and announcing of objects, then just press NVDA+m. The beeps are also louder or softer depending on how bright the screen is at that point.

### Object presentation and interaction

* Improved support for most common treeview controls. NVDA now tells you how many items are in the branch when you expand it. It also announces the level when moving in and out of branches. And, it announces the current item number and number of items, according to the current branch, not the entire treeview.
* Improved what is announced when focus changes as you move around applications or the operating system. Now instead of just hearing the control you land on, you hear information about any controls this control is positioned inside of. For instance if you tab and land on a button inside a groupbox, the groupbox will also get announced.
* NVDA now tries to speak the message inside many dialog boxes as they appear. This is accurate most of the time, though there are still many dialogs that arn't as good as they could be.
* Added a report object descriptions checkbox to the object presentation settings dialog. Power users may wish to sometimes uncheck this to stop NVDA announcing a lot of extra descriptions on particular controls,  such as in Java applications.
* NVDA automatically announces selected text in edit controls when focus moves to them. If there isn't any selected text, then it just announces the current line like usual.
* NVDA is a lot more careful now when it plays beeps to indicate progress bar changes in applications. It no longer goes crazy in Eclipse applications such as Lotus Notes/Symphony, and Accessibility Probe.

### User Interface

* Removed the NVDA interface window, and replaced it with a simple NVDA popup menu.
* NVDA's user interface settings dialog is now called General Settings. It also contains an extra setting: a combo box to set the log level, for what messages should go to NVDA's log file. Note that NVDA's log file is now called nvda.log not debug.log.
* Removed the report object group names checkBox from the object presentation settings dialog, reporting of group names now is handled differently.

## 0.5

* NVDA now has a built-in synthesizer called eSpeak, developed by Jonathan Duddington.It is very responsive and lite-weight, and has support for many different languages. Sapi synthesizers can still be used, but eSpeak will be used by default.
 * eSpeak does not depend on any special software to be installed, so it can be used with NVDA on any computer, on a USB thumb drive, or anywhere.
 * For more info on eSpeak, or to find other versions, go to http://espeak.sourceforge.net/.
* Fix bug where the wrong character was being announced when pressing delete in Internet Explorer / Outlook Express editable panes.
* Added support for more edit fields in Skype.
* VirtualBuffers only get loaded when focus is on the window that needs to be loaded. This fixes some problems when the preview pane is turned on in Outlook Express.
* Added commandline arguments to NVDA:
 * -m, --minimal: do not play startup/exit sounds and do not show the interface on startup if set to do so.
 * -q, --quit: quit any other already running instance of NVDA and then exit
 * -s, --stderr-file fileName: specify where NVDA should place uncaught errors and exceptions
 * -d, --debug-file fileName: specify where NVDA should place debug messages
 * -c, --config-file: specify an alternative configuration file
 * -h, -help: show a help message listing commandline arguments
* Fixed bug where punctuation symbols would not be translated to the appropriate language, when using a language other than english, and when speak typed characters was turned on.
* Added Slovak language files thanks to Peter Vagner
* Added a Virtual Buffer settings dialog and a Document Formatting settings dialog, from Peter Vagner.
* Added French translation thanks to Michel Such
* Added a script to toggle beeping of progress bars on and off (insert+u). Contributed by Peter Vagner.
* Made more messages in NVDA be translatable for other languages. This includes script descriptions when in keyboard help.
* Added a find dialog to the virtualBuffers (internet Explorer and Firefox). Pressing control+f when on a page brings up a dialog in which you can type some text to find. Pressing enter will then search for this text and place the virtualBuffer cursor on this line. Pressing f3 will also search for the next occurance of the text.
* When speak typed characters is turned on, more characters should be now spoken. Technically, now ascii characters from 32 to 255 can now be spoken.
* Renamed some control types for better readability. Editable text is now edit, outline is now tree view and push button is now button.
* When arrowing around list items in a list, or tree view items in a tree view, the control type (list item, tree view item) is no longer spoken, to speed up navigation.
* Has Popup (to indicate that a menu has a submenu) is now spoken as submenu.
* Where some language use control and alt (or altGR) to enter a special character, NVDA now will speak these characters when speak typed characters is on.
* Fixed some problems with reviewing static text controls.
* Added Translation for Traditional Chinese, thanks to Coscell Kao.
* Re-structured an important part of the NVDA code, which should now fix many issues with NVDA's user interface (including settings dialogs).
* Added Sapi4 support to NVDA. Currently there are two sapi4 drivers, one based on code contributed by Serotek Corporation, and one using the ActiveVoice.ActiveVoice com Interface. Both these drivers have issues, see which one works best for you.
* Now when trying to run a new copy of NVDA while an older copy is still running will cause the new copy to just exit. This fixes a major problem where running multiple copies of NVDA makes your system very unusable.
* Renamed the title of the NVDA user interface from NVDA Interface to NVDA.
* Fixed a bug in Outlook Express where pressing backspace at the start of an editable message would cause an error.
* Added patch from Rui Batista that adds a script to report the current battery status on laptops (insert+shift+b).
* Added a synth driver called Silence. This is a synth driver that does not speak anything, allowing NVDA to stay completely silent at all times. Eventually this could be used along with Braille support, when we have it.
* Added capitalPitchChange setting for synthesizers thanks to J.J. Meddaugh
* Added patch from J.J. Meddaugh that makes the toggle report objects under mouse script more like the other toggle scripts (saying on/off rather than changing the whole statement).
* Added spanish translation (es) contributed by Juan C. buo.
* Added Hungarian language file from Tamas Gczy.
* Added Portuguese language file from Rui Batista.
* Changing the voice in the voice settings dialog now sets the rate, pitch and volume sliders to the new values according to the synthesizer, rather than forcing the synthesizer to be set to the old values. This fixes issues where a synth like eloquence or viavoice seems to speek at a much faster rate than all other synths.
* Fixed a bug where either speech would stop, or NVDA would entirely crash, when in a Dos console window.
* If support for a particular language exists, NVDA now automatically can show its interface and speak its messages in the language Windows is set to. A particular language can still be chosen manualy from the user interface settings dialog as well.
* Added script 'toggleReportDynamicContentChanges' (insert+5). This toggles whether new text, or other dynamic changes should be automatically announced. So far this only works in Dos Console Windows.
* Added script 'toggleCaretMovesReviewCursor' (insert+6). This toggles whether the review cursor should be automatically repositioned when the system caret moves. This is useful in Dos console windows when trying to read information as the screen is updating.
* Added script 'toggleFocusMovesNavigatorObject' (insert+7). This toggles whether the navigator object is repositioned on the object with focus as it changes.
* Added some documentation translated in to various languages. So far there is French, Spannish and Finish.
* Removed some developer documentation from the binary distribution of NVDA, it is only now in the source version.
* Fixed a possible bug in Windows Live Messanger and MSN Messenger where arrowing up and down the contact list would cause errors.
* New messages are now automatically spoken when in a conversation using Windows Live Messenger. (only works for English versions so far)
* The history window in a Windows Live Messenger conversation can now be read by using the arrow keys. (Only works for English versions so far)
* Added script 'passNextKeyThrough' (insert+f2). Press this key, and then the next key pressed will be passed straight through to Windows. This is useful if you have to press a certain key in an application but NVDA uses that key for something else.
* NVDA no longer freezes up for more than a minute when opening very large documents in MS Word.
* Fixed a bug where moving out of a table in MS Word, and then moving back in, caused the current row/column numbers not to be spoken if moving back in to exactly the same cell.
* When starting NVDA with a synthesizer that doesn't exist, or is not working, the sapi5 synth will try and be loaded in stead, or if sapi5 isn't working, then speech will be set to silence.
* Increasing and decreasing rate scripts can no longer take the rate above 100 or below 0.
* If there is an error with a language when choosing it in the User Interface Settings dialog, a message box will alert the user to the fact.
* NVDA now asks if it should save configuration and restart if the user has just changed the language in the User Interface Settings Dialog. NVDA must be restarted for the language change to fully take effect.
* If a synthesizer can not be loaded, when choosing it from the synthesizer dialog, a message box alerts the user to the fact.
* When loading a synthesizer for the first time, NVDA lets the synthesizer choose the most suitable voice, rate and pitch parameters, rather than forcing it to defaults it thinks are ok. This fixes a problem where Eloquence and Viavoice sapi4 synths start speaking way too fast for the first time.
