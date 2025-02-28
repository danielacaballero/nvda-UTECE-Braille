# NVDA NVDA_VERSION brugervejledning

[TOC]

<!-- KC:title: NVDA NVDA_VERSION Kommandooversigt -->



## Introduktion {#Introduction}

Velkommen til NVDA!

NonVisual Desktop Access (NVDA) er en gratis og open source skærmlæser for Microsoft Windows.
Skærmlæseren gør brug af syntetisk tale og punkt. Programmet giver blinde og svagtseende brugere adgang til computere med Windows for en pris, der ikke er højere end den, en seende bruger betaler.
NVDA er udviklet af [NV Access](https://www.nvaccess.org/), med bidrag fra fællesskabet.

### Generelle funktioner {#GeneralFeatures}

NVDA giver blinde og svagsynede mulighed for at få adgang til og interagere med Windows-operativsystemet og mange tredjeparts-programmer.

En kort videodemonstration, ["What is NVDA?"](https://www.youtube.com/watch?v=tCFyyqy9mqo) er tilgængelig på NV Access YouTube-kanalen. Denne video er på engelsk.

Af væsentlige funktioner kan nævnes:

* Understøttelse af populære applikationer som web-browsere, email-programmer, internet-chat- programmer og office suites
* Indbygget talesyntese der understøtter over 80 sprog
* Rapportering af tekstformatering hvor det er muligt, såsom skrifttype og størrelse, typografi og stavefejl
* Læser automatisk teksten under musen op og kan angive musens position akustisk
* Understøttelse af mange punktdisplays, herunder mulighed for at tilkoble mange af disse automatisk og indtastning af punkt på punktdisplays med et punkttastatur
* Kan køre fra et USB-drev eller andet bærbart medie uden installation
* Talende installation der er let at bruge
* Oversat til 54 sprog
* Understøttelse af moderne Windows operativsystemer herunder 32 og 64 bit varianter
* Kan køre på Windows logon skærmen og [andre beskyttede skærme](#SecureScreens)
* Oplæsning af kontroller og tekst, når der benyttes touch-bevægelser
* Understøttelse af fælles tilgængelighedsgrænseflader såsom Microsoft Active Accessibility, Java Access Bridge, IAccessible2 and UI Automation
* Understøtter Windows kommandoprompt og konsolapplikationer
* Mulighed for at fremhæve det aktuelle systemfokus på skærmen

### Systemkrav {#SystemRequirements}

#### Minimum Systemkrav {#MinimumSystemRequirements}

* Operativsystemer: alle 32-bit og 64-bit udgaver af Windows 8.1, Windows 10, Windows 11, og alle Server Operativsystemer fra og med Windows Server 2012 R2.
  * både AMD64 og ARM64 varianter af Windows understøttes.
  * Note that 32-bit operating systems are no longer under active support.
  * Bemærk, at Windows 8.1 og Windows Server versioner ældre end 2022 ikke længere er under aktiv support.
* at least 500 MB of storage space.

#### Recommended System Requirements {#RecommendedSystemRequirements}

* Operating Systems: 64-bit editions of Windows 10, Windows 11, and Windows Server 2022.
  * both AMD64 and ARM64 variants of Windows are supported.
* at least 500 MB of storage space.
* at least 4 GB of RAM.

### Internationalisering {#Internationalization}

Det er vigtigt, at folk overalt i verden, uanset hvilket sprog de taler, får lige adgang til teknologi.
Udover Engelsk er NVDA blevet oversat til 54 sprog herunder: Afrikaans, albansk, amharisk, arabisk, aragonisk, brasiliansk portugisisk, bulgarsk, burmesisk, catalansk, colombiansk spansk, kroatisk, tjekkisk, dansk, hollandsk, farsi, finsk, fransk, galicisk, græsk, georgisk, tysk (Tyskland og Schweiz), hebraisk, hindi, ungarsk, islandsk, irsk, italiensk, japansk, kannada, koreansk, kirgisisk, litauisk, makedonsk, nepalesisk, norsk, polsk, portugisisk, punjabi, rumænsk, russisk, serbisk, slovakisk, slovensk, spansk, svensk, tamilsk, thai, traditionelt og forenklet kinesisk, tyrkisk, ukrainsk og vietnamesisk.

### Understøttelse af talesynteser {#SpeechSynthesizerSupport}

Udover at programmets meddelelser og brugerflade findes på flere sprog, kan NVDA også sætte brugeren i stand til at læse tekster på alle sprog, så længe de har en talesyntese, der kan tale det pågældende sprog.

NVDA leveres med [eSpeak NG](https://github.com/espeak-ng/espeak-ng), en gratis, open-source, flersproget talesyntese.

Oplysninger om andre talesynteser som NVDA understøtter kan findes i afsnittet [Understøttede Talesynteser](#SupportedSpeechSynths).

### Understøttelse af punktskrift {#BrailleSupport}

Brugere, som har et punktdisplay, kan med NVDA få tekst ud på punktskrift.
NVDA benytter de open source punkttabeller fra [LibLouis](https://liblouis.io/) til at vise tekst på punktskrift.
Indtastning på uforkortet og uforkortet punkt er også understøttet ved hjælp af et punkttastatur.
Desuden kan NVDA tilkoble sig mange af disse displays automatisk som standard.
Se venligst afsnittet [Understøttede punktdisplays](#SupportedBrailleDisplays) for oplysninger om understøttede punktdisplays.

NVDA understøtter punkttabeller for mange sprog, herunder forkortet, fuldskrift og computer braille.

### Licens og Ophavsret {#LicenseAndCopyright}

NVDA er ophavsret NVDA_COPYRIGHT_YEARS NVDA bidragydere.

NVDA er omfattet under GNU General Public License (version 2) med to undtagelser.
Undtagelserne beskrives i licensdokumentet under paragrafferne "Non-GPL Components in Plugins and Drivers" og "Microsoft Distributable Code".
NVDA inkluderer og benytter også komponenter, der omfattes af forskellige gratis og open source licenser, der gør komponenterne tilgængelige.
Du kan frit dele eller ændre denne software så længe du distribuerer licensen sammen med softwaren og stiller hele kildekoden til rådighed for alle, der ønsker det.
Dette gælder både originale og modificerede kopier af softwaren, plus software der anvender kode taget fra denne software.

For yderligere oplysninger, kan du [læse den fulde licens](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html).
For oplysninger om, hvilke undtagelser gør sig gældende, læs licensvilkårene under "Licens" under NVDA-menu>Hjælp.

## NVDA-hurtigstartguide {#NVDAQuickStartGuide}

Denne hurtigstartguide indeholder tre hovedafsnit: download, opsætning og kørsel af NVDA.
Disse efterfølges af information om, hvordan man justere indstillinger, bruger tilføjelser, deltager i fællesskabet og får hjælp.
Oplysningerne i denne vejledning er en sammenfatning af andre dele af NVDAs brugervejledning.
Se venligst den fulde brugervejledning for mere detaljeret information om hvert emne.

### Download NVDA {#GettingAndSettingUpNVDA}

NVDA er helt gratis for alle at bruge.
Der er ingen licensnøgle at bekymre sig om eller dyrt abonnement at betale.
NVDA opdateres i gennemsnit fire gange om året.
Den seneste version af NVDA er altid tilgængelig fra siden "Download" på [NV Access-webstedet](NVDA_URL).

NVDA fungerer med alle nyere versioner af Microsoft Windows.
Se [Systemkrav](#SystemRequirements) for alle detaljer.

#### Trin til download af NVDA {#StepsForDownloadingNVDA}

Disse trin forudsætter en vis fortrolighed med at navigere på en webside.

* Åbn din webbrowser (Tryk på `Windows`-tasten, skriv ordet "internet" uden anførselstegn, og tryk på `enter`.
* Indlæs NV Access-downloadsiden (Tryk på `alt+d`, skriv følgende adresse og tryk `enter`):
https://www.nvaccess.org/download
* Aktivér "download"-knappen
* Browseren beder muligvis ikke om en handling efter download, og starter derefter download af filen
* Afhængigt af browseren kører filen muligvis automatisk, efter den er downloadet
* Hvis filen skal startes manuelt, skal du trykke på `alt+n` for at flytte til meddelelsesområdet og derefter på `alt+k` for at køre filen (eller trinene til din browser)

### Opsætning af NVDA {#SettingUpNVDA}

Når du kører den fil du lige har hentet, starter du en midlertidig kopi af NVDA.
Du bliver så spurgt om du ønsker at installere NVDA, oprette en flytbar kopi af NVDA, eller fortsætte med at benytte den midlertidige kopi.

NVDA behøver ikke en internetforbindelse for at køre eller installere, når programmet er hentet.
En internetforbindelse gør det dog muligt at hente opdateringer til programmet.

#### Trin til at køre den hentede fil {#StepsForRunningTheDownloadLauncher}

Opsætningsfilen hedder "nvda_2022.1.exe" eller lignende.
Årstal og version ændres mellem opdateringer for at afspejle den aktuelle version.

1. Kør den downloadede fil.
Musik afspilles, mens en midlertidig kopi af NVDA indlæses.
Når den er indlæst, taler NVDA gennem resten af processen.
1. NVDA-installationsprogrammet viser licensaftalen.
Tryk på `pil ned` for at læse licensaftalen, hvis du ønsker dette.
1. Tryk på `tab` for at flytte til check boxen "Enig", og tryk derefter på `mellemrumstasten` for at markere det.
1. Tryk på `tab` for at gå gennem mulighederne, og tryk derefter på `enter` på den ønskede indstilling.

Mulighederne er:

* "Installér NVDA på denne computer": Dette er den vigtigste mulighed, de fleste brugere ønsker for nem brug af NVDA.
* "Opret flytbar kopi": Dette tillader NVDA at blive opsat i enhver mappe uden at installere.
Dette er nyttigt på computere uden administratorrettigheder, eller på en USB-pen.
Hvis du har valgt denne mulighed, går NVDA gennem trinene for at oprette en flytbar kopi.
Det vigtigste, NVDA har brug for at vide, er mappen til  den flytbar kopi. NVDA vil blive kopieret til denne placering.
* "Fortsæt med at køre": Dette holder den midlertidige kopi af NVDA kørende.
Dette er eksempelvis nyttigt, hvis du ønsker at teste funktionalitet af en nyere version af NVDA, før du installere opdateringen.
Når det er valgt, lukkes installationsvinduet, og den midlertidige kopi af NVDA fortsætter med at køre, indtil den afsluttes, eller pc'en lukkes ned.
Bemærk, at ændringer af indstillinger ikke gemmes.
* "Annuller": Dette lukker NVDA uden at udføre nogen handling.

Hvis du har planer om altid at benytte NVDA på denne computer, skal du vælge at installere NVDA.
Installation af NVDA giver mulighed for yderligere funktionalitet, såsom automatisk start efter logon, evnen til at læse skærmen ved Windows Logon og [Beskyttet Skrivebord](#SecureScreens).
Dette kan ikke gøres med flytbare og midlertidige kopier.
For flere oplysninger om begrænsninger, når du kører en midlertidig eller flytbar kopi af NVDA, læs afsnittet [Begrænsninger for flytbare og midlertidige kopier af NVDA](#PortableAndTemporaryCopyRestrictions).

Installation af NVDA lader dig også oprette genveje i startmenuen og på skrivebordet. Skrivebordsgenvejen vil få genvejen `Alt+Ctrl+N` tilknyttet for at starte NVDA.

#### Sådan installeres NVDA fra installationsprogrammet {#StepsForInstallingNVDAFromTheLauncher}

Disse trin fører dig igennem de mest anvendte installationsindstillinger.
For flere detaljer om de tilgængelige indstillinger læs afsnittet [Installationsindstillinger](#InstallingNVDA).

1. Fra startprogrammet skal du sikre dig, at check box for at acceptere licensen er markeret.
1. `Tab` til, og aktiver knappen "Installer NVDA på denne computer".
1. Dernæst er der muligheder for at bruge NVDA under Windows-logon og for at oprette en skrivebordsgenvej.
Disse er markeret som standard.
Hvis det ønskes, tryk på `tab` og `mellemrumstasten` for at ændre nogen af disse muligheder, eller lad dem være som standard.
1. Tryk på `enter` for at fortsætte.
1. En Windows "Brugerkontokontrol (UAC)"-dialogboks vises og spørger "Vil du tillade denne app at foretage ændringer på din pc?".
1. Tryk på `alt+y` for at acceptere UAC-prompten.
1. En statuslinje vil gradvist bevæge sig på skærmen, efterhånden som NVDA installerer.
Under denne proces afgiver NVDA et nogle bip, der bliver højere efterhånden som installationen skrider frem.
Denne proces er ofte hurtig og bliver muligvis ikke bemærket.
1. Der vises en dialogboks, der bekræfter, at installationen af NVDA er lykkedes.
En meddelelse kommer frem på skærmen der fortæller dig, at du kan trykke på "OK" for at starte den installerede kopi.
Tryk på `enter` for at starte den installerede kopi.
1. Dialogboksen "Velkommen til NVDA" vises, og NVDA læser en velkomstmeddelelse.
Fokus er på boksen "Tastaturlayout".
Som standard bruger "Desktop" tastaturlayout det numeriske tastatur til nogle funktioner.
Hvis det ønskes, skal du trykke på `pil ned` for at vælge "Laptop" tastaturlayout for at tilknytte numeriske tastaturfunktioner til andre taster, såfremt du ikke har et numerisk tastatur.
1. Tryk på `tab` for at gå til "Brug `caps Lock` som en NVDA-tast".
`Insert` er indstillet som NVDA-tast som standard.
Tryk på `mellemrumstasten` for at vælge `caps Lock` som en alternativ NVDA-tast.
Bemærk, at tastaturlayoutet er indstillet uafhængigt af NVDA-tasten.
NVDA-tasten og tastaturlayoutet kan ændres senere fra tastaturindstillingerne.
1. Brug `tab` og `mellemrumstasten` for at justere de andre muligheder på denne skærm.
Disse bestemmer om NVDA starter automatisk.
1. Tryk på `enter` for at lukke dialogboksen. NVDA vil fortsætte med at køre.

### Kørsel af NVDA {#RunningNVDA}

Den fulde NVDA-brugervejledning har alle NVDA-kommandoer, opdelt i forskellige sektioner, så du nemt kan navigere rundt blandt de forskellige afsnit.
Tabellerne med kommandoer er også tilgængelige i "Kommandooversigt" fra NVDAs hjælpemenu.
I NVDA-træningsmodulet "Basic Training for NVDA" har hver kommando en mere dybdegående beskrivelse med trinvise aktiviteter (findes kun på engelsk).
"Basic Training for NVDA" er tilgængelig fra [NV Access Shop](http://www.nvaccess.org/shop).

Her er nogle grundlæggende kommandoer, som bruges ofte.
Alle kommandoer er konfigurerbare, så disse er standardtastetryk for disse funktioner.

#### NVDA-tasten {#NVDAModifierKey}

Som standard er NVDA-tasten enten `numpad0`, (med `numLock` slået fra), eller `insert-tasten` nær `delete`, `home` og `end`-taster.
NVDA-tasten kan også indstilles til `capsLock`-tasten.

#### Tastaturhjælp {#InputHelp}

For at lære placeringen af tasterne på tastaturet, tryk på `NVDA+1` for at slå tastaturhjælp til.
Når du er i tastaturhjælpen, vil et hvilket som helst tastetryk (såsom at trykke på en tast eller udføre en berøring på en touchskærm) oplyse handlingen og beskrive, hvad den gør (hvis der er en handling tilknyttet).
De faktiske kommandoer vil ikke udføres, når tastaturhjælpen er slået til. Tryk på NVDA+1 igen for at slå funktionen fra.

#### Start og stop NVDA {#StartingAndStoppingNVDA}

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Start NVDA |`ctrl+alt+n` |`control+alt+n` |Starter eller genstarter NVDA|
|Afslut NVDA |`NVDA+q`, og `enter` |`NVDA+q`, og `enter` |Afslutter NVDA|
|Sæt tale på pause eller genoptag oplæsning |`shift` |`shift` |Sætter talen på pause med det samme. Hvis du trykker på tasten igen, vil talen fortsætte|
|Stop tale |`ctrl` |`ctrl` |Stopper talen med det samme|

#### Læsning af tekst {#ReadingText}

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Sig alt |`NVDA+pil ned` |`NVDA+a` |Læser fra din aktuelle position|
|Læs aktuelle linje |`NVDA+pil op` |`NVDA+l` |Læser den aktuelle linje. Ved to tryk staves linjen. Ved et tredje tryk staves linjen ved brug af såkaldte tegnbeskrivelser (Alpha, Bravo, Charley, osv)|
|Læs markeret tekst |`NVDA+shift+pil op` |`NVDA+shift+s` |Læser den valgte tekst. Ved to tryk staves teksten. Ved et tredje tryk staves teksten ved brug af såkaldte tegnbeskrivelser (Alpha, Bravo, Charley, osv)|
|Læs teksten i udklipsholderen |`NVDA+c` |`NVDA+c` |Læser teksten i udklipsholderen. Ved to tryk staves teksten. Ved et tredje tryk staves teksten ved brug af såkaldte tegnbeskrivelser (Alpha, Bravo, Charley, osv)|

#### Oplys placering og andre informationer {#ReportingLocation}

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Læs vinduets titel |`NVDA+t` |`NVDA+t` |Tryk én gang for at læse titlen på det aktuelle vindue. To tryk staver titlen. Et tredje tryk kopiere informationen til udklipsholderen|
|Oplys fokus |`NVDA+tab` |`NVDA+tab` |Oplyser det aktuelle kontrolelement, der har fokus. To tryk staver informationen. Ved et tredje tryk staves informationen ved brug af såkaldte tegnbeskrivelser (Alpha, Bravo, Charley, osv)|
|Læs vindue |`NVDA+b` |`NVDA+b` |Læser hele vinduet (brugbart i dialoger)|
|Læs statuslinjen |`NVDA+end` |`NVDA+shift+end` |Læser statuslinjen, såfremt NVDA kan finde den. To tryk staver informationen. Ved et tredje tryk kopieres informationen til udklipsholderen|
|Læs tid |`NVDA+f12` |`NVDA+f12` |Ved ét tryk oplyses tiden. Hvis du trykker to gange, vil du få datoen oplyst. Tid og dato oplyses i henhold til formatet, der er angivet i indstillingerne for tid og dato i Windows.|
|Oplys tekstformattering |`NVDA+f` |`NVDA+f` |Denne kommando oplyser formatteringsoplysninger for den aktuelle tekst. Ved to tryk vises disse informationer i et vindue|
|Oplys adresse for link |`NVDA+k` |`NVDA+k` |Oplyser webadressen for linket ved markøren eller fokuspositionen. Hvis der trykkes to gange, vises linket i et vindue for lettere gennemgang.|

#### Vælg, hvilke informationer NVDA skal læse {#ToggleWhichInformationNVDAReads}

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Sig indtastede tegn |`NVDA+2` |`NVDA+2` |Når dette er slået til, vil NVDA oplyse alle tegn, når du skriver på tastaturet.|
|Sig indtastede ord |`NVDA+3` |`NVDA+3` |Når dette er slået til, vil NVDA oplyse alle ord, når du skriver på tastaturet.|
|Oplys funktionstaster |`NVDA+4` |`NVDA+4` |Når denne funktion er slået til, vil NVDA oplyse enhver tast du trykker, såfremt det ikke er et tegn. Dette kan f.eks. være Ctrl-tasten sammen med et bogstav.|
|Følg musen |`NVDA+m` |`NVDA+m` |Når denne funktion er aktiveret, vil NVDA annoncere teksten under musemarkøren, når du flytter den rundt på skærmen. Dette giver dig mulighed for at finde ting på skærmen ved fysisk at flytte musen, i stedet for at finde dem ved brug af objektnavigation.|

#### Ringen af talesynteseindstillinger {#TheSynthSettingsRing}

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Flyt til næste indstilling |`NVDA+ctrl+højre pil` |`NVDA+shift+ctrl+højre pil` |Flytter til næste mulige indstilling efter den indstilling du er på i øjeblikket. Bemærk, at dette vil bevæge dig rundt i ring mellem de tilgængelige indstillinger, når du er på den sidste indstilling|
|Flyt til forrige indstilling |`NVDA+ctrl+venstre pil` |`NVDA+shift+ctrl+venstre pil` |Flytter til næste mulige indstilling før den, du er på i øjeblikket. Bemærk, at dette vil bevæge dig rundt i ring mellem de tilgængelige indstillinger, når du er på den sidste indstilling|
|Forøg den aktuelle indstilling |`NVDA+ctrl+pil op` |`NVDA+shift+ctrl+pil op` |øger den aktuelle taleindstilling, du er på. F.eks. øger hastigheden, vælger den næste stemme, øger lydstyrken|
|Forøg den aktuelle indstilling med en større værdi |`NVDA+Ctrl+sideOp` |`NVDA+shift+Ctrl+sideOp` |Forøger den indstilling, du er på i øjeblikket, med en større værdi. Hvis du befinder dig på stemmeindstillingen, vil den springe 20 stemmer fremad, og ved brug af indstillinger som toneleje og hastighed, vil der springes fremad med 20%|
|Formindsk den aktuelle indstilling |`NVDA+ctrl+pil ned` |`NVDA+shift+ctrl+pil ned` |Formindsker den aktuelle taleindstilling, du er på. F.eks. formindsker talehastigheden, vælger den forrige stemme, formindsker lydstyrken|
|Formindsk den aktuelle indstilling med en større værdi |`NVDA+Ctrl+sideNed` |`NVDA+shift+Ctrl+sideNed` |Forøger den indstilling, du er på i øjeblikket, med en større værdi. Hvis du befinder dig på stemmeindstillingen, vil den springe 20 stemmer fremad, og ved brug af indstillinger som toneleje og hastighed, vil der springes fremad med 20%|

Det er også muligt hurtigt at springe til den første og sidste mulighed for den aktuelle indstilling, hvis du tildeler en kommando til dette via dialogen [Håndter kommandoer](#InputGestures) under talekategorien.
Dette betyder, at der eksempelvis springes til 0 eller 100%, hvis du står på hastighedsindstillingen.
Hvis du står på stemme i ringen af synteseindstillinger, vil dette springe til første og sidste stemme.

#### Navigér på internettet {#WebNavigation}

Den samlede liste over tastaturkommandoer for bogstavnavigation kan du læse ved at gå til afsnittet [Gennemsynstilstand](#BrowseMode) i brugervejledningen.

| Kommando |Tastetryk |Beskrivelse|
|---|---|---|
|Overskrift |`h` |Flyt til næste overskrift|
|Overskriftsniveau 1, 2 eller 3 |`1`, `2`, `3` |Flytter til det tilsvarende overskriftsniveau|
|Formularfelt |`f` |(Flytter til det næste editfelt, den næste knap, osv)|
|Link |`k` |Flyt til næste link|
|Landmærke |`d` |Flyt til næste landmærke|
|Liste |`l` |Flyt til næste liste|
|Tabel |`t` |Flyt til næste tabel|
|Flyt bagud |`shift+bogstav` |Tryk `shift` og et af bogstaverne ovenfor, for at flytte til det forrige element af den pågældende type|
|Elementlisten |`NVDA+f7` |Viser en liste over de forskellige elementer på siden, som links og overskrifter|

### Indstillinger {#Preferences}

De fleste NVDA-funktioner kan aktiveres eller ændres via NVDA-indstillingerne.
Indstillinger og andre muligheder er tilgængelige via NVDAs menu.
For at åbne NVDAs menu, tryk på `NVDA+n`.
For at åbne NVDAs generelle indstillingsdialog fra hvor som helst, tryk på `NVDA+Ctrl+g`.
Mange indstillingspaneler har tastetryk til at åbne dem fra hvor som helst, som eksempelvis `NVDA+Ctrl+s` for talesyntese, eller `NVDA+ctrl+v` for andre stemmeindstillinger.

### Tilføjelser {#Addons}
Tilføjelser er programmer, der giver ny eller ændret funktionalitet til NVDA.
Tilføjelser udvikles af NVDA-fællesskabet eller eksterne virksomheder og er ikke tilknyttet NV Access.
Som med enhver software er det vigtigt at have tillid til udvikleren af en tilføjelse, før du bruger den.
Se venligst [Installation af tilføjelser](#AddonStoreInstalling) for måder at bekræfte tilføjelser på, inden installation.

Når Tilføjelsescentret åbnes for første gang, viser NVDA en advarsel om tilføjelser.
Tilføjelser er ikke godkendt af NV Access og kan have ubegrænset funktionalitet og adgang til information.
Tryk på `mellemrumstasten`, hvis du har læst advarslen og ikke behøver at se den næste gang.
Tryk på `tab` for at nå knappen "OK", og tryk derefter på `enter` for at acceptere advarslen og fortsætte til Tilføjelsescentret.
Afsnittet "[Tilføjelser og Tilføjelsescentret](#AddonsManager)" i brugervejledningen indeholder oplysninger om alle funktioner i Tilføjelsescentret.

Tilføjelsescentret er tilgængeligt fra Værktøjsmenuen.
Tryk på `NVDA+n` for at åbne NVDA-menuen, derefter `t` for værktøjer, og derefter `t` for Tilføjelsescenter.
Når Tilføjelsescentret åbnes, viser det "Tilgængelige tilføjelser", hvis ingen tilføjelser er installeret.
Når tilføjelser er installeret, åbner Tilføjelsescentret til fanen "Installerede tilføjelser".

#### Tilgængelige tilføjelser {#AvailableAddons}
Når vinduet først åbnes, kan tilføjelser tage et par sekunder at indlæse.
NVDA vil læse navnet på den første tilføjelse, når listen over tilføjelser er færdig med at indlæse.
Tilgængelige tilføjelser er opført alfabetisk i en liste bestående af flere kolonner.
For at gennemse listen og finde ud af mere om en specifik tilføjelse:

1. Brug piletasterne eller tryk på det første bogstav i navnet på en tilføjelse for at navigere rundt i listen.
1. Tryk `tab` én gang for at flytte til beskrivelsen af den aktuelt valgte tilføjelse.
1. Brug [læsetasterne](#ReadingText) eller piletasterne for at læse hele beskrivelsen.
1. Tryk `tab` til "Handlinger"-knappen, som kan bruges til at installere tilføjelsen, blandt andre handlinger.
1. Tryk `tab` til "Andre detaljer", som viser detaljer såsom udgiver, version og hjemmeside.
1. For at vende tilbage til listen over tilgængelige tilføjelser, tryk `alt+t`, eller `shift+tab`, indtil du kommer tilbage til listen.

#### Søgning efter tilføjelser {#SearchingForAddons}
Udover at gennemse alle tilgængelige tilføjelser, er det muligt at filtrere de viste tilføjelser.
For at søge, tryk `alt+s` for at springe til søgefeltet og indtast teksten for at søge.
Når du skriver i feltet, kan du søge efter informationer som tilføjelses-ID, visningsnavn, udgiver, forfatter eller beskrivelse.
Listen ændrer sig, mens du indtaster din søgning.
Når du er færdig, tryk `tab` for at gå til den filtrerede liste over tilføjelser og gennemse resultaterne.

#### Installation af tilføjelser {#InstallingAddons}

For at installere en tilføjelse:

1. Med fokus på en tilføjelse, du ønsker at installere, tryk `enter`.
1. Handlingsmenuen åbnes med en liste over handlinger. Den første handling er "Installér".
1. For at installere tilføjelsen, tryk `i` eller `pil ned` til "installér" og tryk `enter`.
1. Fokus vender tilbage til tilføjelsen i listen, og NVDA vil læse detaljerne om tilføjelsen.
1. "Status"-informationen rapporteret af NVDA ændres fra "Tilgængelig" til "Henter".
1. Når tilføjelsen er færdig med at hente, ændres status til "Hentet. Afventer installation".
1. Gentag med eventuelle andre tilføjelser, du ønsker at installere samtidigt.
1. Når du er færdig, tryk `tab`, indtil fokus er på knappen "Luk", og tryk derefter `enter`.
1. De hentede tilføjelser starter installationsprocessen, når Tilføjelsescentret lukkes.
Under installationsprocessen kan dialogbokse fremkomme, som du skal reagere på.
1. Når tilføjelserne er installeret, vises en dialog, der informerer om, at der er foretaget ændringer, og du skal genstarte NVDA for at fuldføre installationen.
1. Tryk `enter` for at genstarte NVDA.

#### Håndtering af installerede tilføjelser {#ManagingInstalledAddons}
Tryk `control+tab` for at bevæge dig mellem fanerne i Tilføjelsescentret.
Fanerne inkluderer: "Installerede tilføjelser", "Opdaterbare tilføjelser", "Tilgængelige tilføjelser" og "Installerede inkompatible tilføjelser".
Hver af fanerne er opstillet på samme måde, som en liste over tilføjelser, et panel med flere detaljer om den valgte tilføjelse og muligheden for at udføre handlinger for tilføjelsen.
Handlingsmenuen for installerede tilføjelser inkluderer "Deaktiver" og "Fjern" i stedet for "Installér".
Deaktivering af en tilføjelse forhindrer NVDA i at indlæse den, men lader den være installeret.
For at genaktivere en deaktiveret tilføjelse, aktiver "Aktiver" fra handlingsmenuen.
Efter aktivering, deaktivering eller fjernelse af tilføjelser vil du blive bedt om at genstarte NVDA, når Tilføjelsescentret lukkes.
Disse ændringer træder kun i kraft, når NVDA genstartes.
Bemærk, at i denne dialog fungerer `escape` på samme måde som Luk-knappen.

#### Opdatering af tilføjelser {#UpdatingAddons}
Når der er en opdatering til en tilføjelse, du har installeret, vil den blive vist i fanen "Opdaterbare tilføjelser".
Tryk `control+tab` for at komme til denne fane fra hvor som helst i Tilføjelsescentret.
Status for tilføjelsen vil være angivet som "Opdatering tilgængelig".
Tabellen viser den aktuelt installerede version og den tilgængelige version.
Tryk `enter` på tilføjelsen for at åbne handlingsmenuen og vælg "Opdatër".

Som standard, vil du få besked om opdateringer for tilføjelser, når NVDA starter.
For at lære mere om, hvordan denne indstilling konfigureres, læs ["Opdateringsmeddelelser"](#AutomaticAddonUpdates).

### NVDAs internationale fællesskab {#Community}

NVDA har et stærkt brugerfællesskab.
Der er en [e-mail-liste på engelsk](https://nvda.groups.io/g/nvda) og en side fuld af [lokale sproggrupper](https://github.com/nvaccess/nvda-community/wiki/Connect) .
NV Access, udviklerne af NVDA, er aktive på [Twitter](https://twitter.com/nvaccess) og [Facebook](https://www.facebook.com/NVAccess).
NV Access har også en regelmæssig [In-Process blog](https://www.nvaccess.org/category/in-process/).

Der er også et [NVDA Certified Expert](https://certification.nvaccess.org/)-program.
Dette er en online eksamen, du kan gennemføre for at demonstrere dine færdigheder i NVDA.
[NVDA Certified Experts](https://certification.nvaccess.org/) kan angive deres kontaktpersoner og relevante forretningsoplysninger.

### Få hjælp {#GettingHelp}

For at få hjælp til, hvordan du bruger NVDA, tryk `NVDA+n` får at åbne menuen og bagefter `H` for hjælp.
Fra denne menu kan du nemt få adgang til brugervejledningen, en kommandooversigt, nyheder i NVDA og mere.
De første tre muligheder åbner i din webbrowser.
Der er også mere omfattende træningsmateriale tilgængeligt i [NV Access Shop](https://www.nvaccess.org/shop).

Vi anbefaler at starte med modulet "Basic Training for NVDA".
Dette modul omfatter koncepter helt fra, hvordan man kommer i gang med NVDA til at surfe på nettet og bruge objektnavigation.
Den er tilgængelig i:

* [Elektronisk tekst](https://www.nvaccess.org/product/basic-training-for-nvda-ebook/), som inkluderer formaterne Word DOCX, webside HTML, eBook ePub og Kindle KFX.
* [Lyd i mp3, oplæst af et menneske](https://www.nvaccess.org/product/basic-training-for-nvda-downloadable-audio/)
* [Punktskrift på papir i UEB Braille](https://www.nvaccess.org/product/basic-training-for-nvda-braille-hard-copy/) med levering inkluderet overalt i verden.

Andre moduler og den nedsatte [NVDA Productivity Bundle](https://www.nvaccess.org/product/nvda-productivity-bundle/), er tilgængelige i [NV Access Shop https://www.nvaccess.org/shop/ ].

NV Access sælger også [telefonsupport](https://www.nvaccess.org/product/nvda-telephone-support/), enten pr. time eller som en del af [NVDA Productivity Bundle NVDA Productivity Bundle](https://www.nvaccess.org/product/nvda-productivity-bundle/).
Telefonsupport omfatter lokale numre i Australien og USA.

[e-mail-brugergrupperne](https://github.com/nvaccess/nvda-community/wiki/Connect) er en stor inspiration til hjælp fra fællesskabet, ligesom [certificerede NVDA-eksperter](https://certification.nvaccess.org/).

Du kan anmode om nye funktioner eller oprette en fejlrapport via [GitHub](https://github.com/nvaccess/nvda/blob/master/projectDocs/issues/readme.md).
[Retningslinjerne for at bidrage](https://github.com/nvaccess/nvda/blob/master/.github/CONTRIBUTING.md) indeholder nyttige oplysninger, såfremt du ønsker at bidrage til udviklingen.

## Flere installationsindstillinger {#MoreSetupOptions}
### Installation af NVDA {#InstallingNVDA}

Hvis du installerer NVDA direkte fra den hentede fil, skal du trykke på knappen Installer NVDA.
Hvis du allerede har lukket denne dialog, eller hvis du ønsker at installere fra en flytbar kopi, skal du vælge menupunktet Installer NVDA under Værktøjer i NVDA-menuen.

Installationsdialogen der vises vil bede dig bekræfte, at du ønsker at installere NVDA, og dialogen vil også fortælle dig om en tidligere installation vil blive opdateret.
Når du trykker på knappen Fortsæt, installeres NVDA.
Der er desuden nogle få indstillinger i denne dialog der vil blive forklaret nedenunder.
Når installationen er færdig vil du få en besked om, at installationen er lykkedes.
Når du trykker OK på dette tidspunkt, vil din nyinstallerede kopi af NVDA starte op.

#### Advarsel om inkompatible tilføjelser {#InstallWithIncompatibleAddons}

Hvis du allerede har tilføjelser installeret, vil en dialog muligvis fremkomme der advarer om inkompatible tilføjelser.
Før du kan fortsætte, vil det være nødvendigt at vælge check boxen der bekræfter, at inkompatible tilføjelser deaktiveres.
I denne dialog vil du også finde en knap der lader dig gennemgå de inkompatible tilføjelser.
Læs venligst afsnittet om [dialogen omfattende inkompatible tilføjelser](#incompatibleAddonsManager) for yderligere hjælp med denne knap.
Efter installationen, kan du genaktivere tilføjelser, der er inkompatible på eget ansvar fra [Tilføjelsescenteret](#AddonsManager).

#### Brug af NVDA på logon-skærmen {#StartAtWindowsLogon}

Med denne indstilling bestemmer du, om du vil starte NVDA på Windows logon-skærmen, før du har indtastet din adgangskode.
Dette omfatter også kontrol af brugerkonti og [ andre sikre skærme](#SecureScreens).
Denne indstilling er aktiveret for nye installationer.

#### Opret Genvej på Skrivebordet (ctrl+alt+n) {#CreateDesktopShortcut}

Denne indstilling, hvis valgt, vil oprette en genvej til NVDA på skrivebordet.
Hvis du vælger, at oprette denne genvej på dit skrivebord, vil genvejen også blive tilknyttet genvejstasten `Ctrl+Alt+n`. Denne genvejstast gør det muligt at starte NVDA når som helst når du trykker genvejstasten.

#### Kopier flytbar konfiguration til nuværende brugerkonto {#CopyPortableConfigurationToCurrentUserAccount}

Denne indstilling lader dig vælge, om du vil kopiere brugerkonfigurationen fra den kørende kopi af NVDA til konfigurationen for den bruger, som er logget på. Indstillingen gælder brugerens installerede kopi.
Dette vil ikke kopiere konfigurationen for andre brugere på dette system, og vil heller ikke kopiere til systemkonfigurationen til brug af Windows sikkert logon og [andre sikre skærme](#SecureScreens).
Denne indstilling er kun tilgængelig når du installerer fra den flytbare kopi, og ikke den hentede fil.

### Opret en flytbar kopi {#CreatingAPortableCopy}

Hvis du ønsker, at oprette en flytbar kopi af NVDA direkte fra den hentede fil, skal du bare trykke på knappen Opret Flytbar Kopi.
Hvis du allerede har lukket denne dialog, eller hvis du kører en installeret kopi af NVDA, skal du vælge menupunktet Opret Flytbar Kopi under Værktøjer i NVDA-menuen.

Dialogen der vises lader dig vælge hvor du vil oprette den flytbare kopi.
Det kan være en mappe på din harddisk, et USB-drev eller andet bærbart medie.
Som standard, vil en ny mappe blive oprettet for den flytbare kopi.
Du kan også vælge at benytte en eksisterende mappe. Vær dog opmærksom på, at dette vil overskrive alle filer i mappen.
Hvis mappen allerede eksisterer og har en kopi af NVDA, vil denne kopi i stedet blive opdateret.

Der er også mulighed for at kopiere den aktuelle brugerkonfiguration fra den bruger, som er logget ind.
Dette inkluderer også tilføjelser.
Denne indstilling er kun tilgængelig når du opretter en flytbar kopi fra en installeret kopi, og ikke hvis du opretter en flytbar kopi fra den hentede fil.

Trykker du Fortsæt vil den flytbare kopi blive oprettet.
Når installationen er færdig vil du få en besked om, at installationen er fuldført.
Tryk Ok for at lukke denne dialog.

### Begrænsninger for flytbare og midlertidige kopier af NVDA {#PortableAndTemporaryCopyRestrictions}

Hvis du ønsker, at tage NVDA med dig på et USB-drev eller andre skrivbare medier, skal du vælge at oprette en flytbar kopi.
Med den installerede kopi af NVDA kan du også oprette en flytbar kopi når som helst.
Den flytbare kopi kan desuden også installere sig selv på en computer på et senere tidspunkt.
Ønsker du dog at kopiere NVDA til et skrivebeskyttet medie såsom en CD, skal du blot kopiere den hentede fil.
Kørsel af den flytbare version fra skrivebeskyttede medier er på nuværende tidspunkt ikke understøttet.

[NVDA-installationsfilen](#StepsForRunningTheDownloadLauncher) kan fungere som en midlertidig kopi af NVDA:
Midlertidige kopier tillader ikke, at du gemmer NVDA-indstillinger.
[Tilføjelsescenteret](#AddonsManager) er også deaktiveret.

Flytbar eller midlertidig kopier af NVDA har følgende begrænsninger:

* Manglende evne til at start ved eller after logon
* manglende evne til at interagere med programmer der kører med administratorrettigheder, med mindre NVDA ligeledes kører med administratorrettigheder (anbefales ikke).
* Manglende evne til at læse Kontrol af Brugerkonti (UAC) skærme når du forsøger at starte et program med administratorrettigheder.
* Understøtter ikke input for berøringsfølsomme skærme.
* NVDA er ikke i stand til at benytte funktioner såsom gennemsynstilstand, samt evnen til at udtale indtastede tegn i Windows Store apps.
* Lyddæmpning er ikke understøttet.

## Kom i gang med at bruge NVDA {#GettingStartedWithNVDA}
### Start NVDA {#LaunchingNVDA}

Hvis du har installeret NVDA med installationsprogrammet, kan du blot starte NVDA ved enten at trykke Ctrl+Alt+n eller vælge NVDA fra NVDA-menuen under Programmer i menuen Start.
Derudover kan du skrive NVDA i dialogboksen Kør og trykke på Enter.
Hvis NVDA allerede kører, vil programmet blive genstartet.
Du kan også skrive nogle [kommandolinjeparametre](#CommandLineOptions), som du kan bruge til følgende: Genstarte NVDA (-r), afslut (-q) deaktivere tilføjelsesprogrammer fra (--disable-addons) osv.

For installerede kopier, vil konfigurationen af NVDA blive gemt i mappen roaming application data for den aktuelle bruger som standard (f.eks. "`C:\Users\<user>\AppData\Roaming`").
Det er muligt at ændre dette således NVDA indlæser konfigurationen fra den lokale application data mappe i stedet.
Læs afsnittet [systemspecifikke parametre](#SystemWideParameters) for flere detaljer.

Hvis du vil starte den flytbare version, skal du åbne den mappe hvori du udpakkede NVDA, og trykke enter eller dobbeltklikke på nvda.exe.
Hvis NVDA allerede kørte, vil den aktuelle version af NVDA stoppes og den flytbare version køres i stedet.

Mens NVDA starter, vil du først høre en stigende række toner, som fortæller, at NVDA er ved at blive indlæst.
Afhængigt af hvor hurtigt din computer er, eller hvis du kører NVDA fra en USB-nøgle eller andet langsommere medie, kan det tage lidt tid at starte.
Hvis det tager ekstra lang tid, bør NVDA sige "Indlæser NVDA. Vent venligst ... "

Hvis du ikke hører noget af dette, eller du hører Windows lyden der indikere en fejl eller en faldende række af toner, så betyder det, at NVDA har en fejl, og du bliver nødt til eventuelt at rapportere en fejl til udviklerne.
Venligst tjek på NVDA hjemmesiden for hvordan du gør dette.

#### Dialogen Velkommen {#WelcomeDialog}

Når NVDA starter for første gang, vil du blive mødt af en dialogboks som giver dig nogle grundlæggende oplysninger om NVDA/tasten og NVDA-menuen.
(Se de følgende afsnit om disse emner).
Dialogboksen indeholder også en combo box og tre check boxe.
Combo boxen lader dig vælge tastaturlayout.
Med den første check box kan du bestemme, om NVDA skal bruge capslock som en NVDA/tast.
Den anden bestemmer, om NVDA skal starte automatisk, efter du har logget på Windows. Denne indstilling er kun tilgængelig i installerede kopier af NVDA.
Den tredje lader dig styre, om denne Velkomstdialog boks skal vises hver gang NVDA starter.

#### Dialog om brugsstatistik {#UsageStatsDialog}

Når du starter NVDA for første gang, vil der vises en dialogboks, der spørger, om du vil acceptere at sende data til NV Access, mens du bruger NVDA, for at hjælpe med at forbedre NVDA.
Du kan læse yderligere information om, hvilke data indsamles i NVDAs generelle indstillinger under [Tillad, at NV Access indsamler brugsdata](#GeneralSettingsGatherUsageStats).
Bemærk: Når du trykker "Ja" eller "Nej", vil denne dialog ikke fremkomme igen med mindre du geninstallerer NVDA.
Du kan aktivere eller deaktivere denne indstilling i NVDAs generelle indstillinger ved at ændre indstillingen [Tillad at NVDA-projektet indsamler brugsdata om NVDA](#GeneralSettingsGatherUsageStats).

### Om NVDA tastaturkommandoer {#AboutNVDAKeyboardCommands}
#### NVDA-tasten {#TheNVDAModifierKey}

De fleste NVDA-specifikke tastaturkommandoer består normalt af at trykke på en særlig tast kaldet NVDA-tasten, samtidig med en eller flere andre taster.
Bemærkelsesværdige undtagelser herfra er tekstlæsekommandoerne i desktop-tastaturlayoutet, som kun består af tasterne i det numeriske tastatur alene, men der er også andre undtagelser.

NVDA kan konfigureres således, at enten `Insert`, den `numeriske Insert`, eller `Caps Lock-tasten` kan bruges som `NVDA`-tast.
Som standard er både `Insert` og `Numerisk Insert` tasterne indstillet som NVDA-tast.

Hvis du ønsker at få en af NVDA-tasterne til at brue dens oprindelige funktion (for eksempel, hvis du ønsker at slå Caps Lock til og fra, når du har valgt Caps Lock som en NVDA-tast) kan du trykke på tasten to gange i hurtig rækkefølge.

#### Tastaturlayouts {#KeyboardLayouts}

NVDA har i øjeblikket to sæt tastaturkommandoer eller tastaturlayouts: Desktop-layoutet og laptop-layoutet.
Som standard er NVDA sat til at bruge Desktop-layout, men du kan skifte til det bærbare/laptop layout ved brug af indstillingskategorien Tastatur i [dialogen Indstillinger](#NVDASettings), under Opsætning i NVDA-menuen.

Desktop-layout bruger i høj grad det numeriske tastatur (med Num Lock slået fra).
Selvom de fleste bærbare computere ikke har et fysisk numerisk tastatur, kan nogle bærbare computere efterligne et ved at holde Fn-tasten nede og trykke på bogstaver og tal på højre side af tastaturet (7 8 9 u i o j k l osv)..
Hvis din bærbare computer ikke kan gøre brug af dette, eller ikke tillader dig at slå Num Lock fra, kan du skifte til det bærbare layout i stedet.

### NVDA Berøringsbevægelser {#NVDATouchGestures}

Hvis du kører NVDA på en enhed med touchskærm, kan du kontrollere NVDA direkte ved hjælp af den berøringsfølsomme skærm.
Når NVDA er i gang, vil alle bevægelser registreret af skærmen blive indfanget af NVDA, medmindre berøringsinteraktion er deaktiveret.
Dette betyder, at handlinger der kan udføres normalt uden NVDA ikke vil virke.
<!-- KC:beginInclude -->
For at slå understøttelse for berøring til eller fra, tryk NVDA+Ctrl+alt+T.
<!-- KC:endInclude -->
Du kan også skifte denne indstilling ved at gå til [Berøringsinteraktion](#TouchSupportEnable) i NVDAs indstillingspanel.

#### Udforsk skærmen {#ExploringTheScreen}

Den mest grundlæggende handling du kan udføre er at få annonceret et element eller noget tekst på skærmen uanset hvor det befinder sig.
For at gøre dette, skal du placere en finger et sted på skærmen.
Du kan også beholde din finger på skærmen, og derefter bevæge den rundt på skærmen for at få oplæst tekst og elementer, som du bevæger dig hen over.

#### Berøringsbevægelser {#TouchGestures}

Når NVDA-kommandoer er beskrevet senere i denne brugermanual, kan de indeholde information om hvordan man benytter touchskærmen til at udføre den tilsvarende kommando.
Følgende information beskriver hvordan du kan udføre diverse berøringsbevægelser.

##### Tryk {#Taps}

Tryk på skærmen hurtigt med en eller flere fingre.

Et enkelt tryk med en finger er bare kendt som et tryk.
Et enkelt tryk med to fingre på samme tid er et enkelt tryk med to fingre, osv.

Hvis det samme tryk er udført hurtigt efter hinanden, vil NVDA behandle handlingen som en multi-tryk bevægelse.
Et tryk to gange med en finger er et dobbelt tryk
Tre tryk er et trippel-tryk, osv.
Disse bevægelser genkender selvfølgelig også hvor mange fingre var benyttet da bevægelsen var udført, så det er muligt at have flere kombinationer der udføre bestemte handlinger som et trippel tryk med to fingre, et tryk med fire fingre, osv.

##### Svirp {#Flicks}

Svirp din finger hurtigt over skærmen.

Der er fire mulige svirpebevægelser du kan benytte, afhængige af retningen: Svirp til venstre, svirp til højre, svirp op og svirp ned.

Ligesom tryk kan du benytte flere fingre for at udføre de forskellige bevægelser.
Derfor er bevægelser som svirp op med to fingre og svirp til venstre med fire fingre mulige bevægelser.

#### Berøringstilstande {#TouchModes}

Eftersom der er mange flere NVDA-kommandoer tilgængelige end der er mulige bevægelser, har NVDA implementeret forskellige tilstande der gør det muligt for dig, at benytte dig af forskellige undergrupper af kommandoer.
De to tilstande er teksttilstand og objekttilstand.
Visse NVDA-kommandoer fra listen i dette dokument kan have en touch-funktion anført i parentes efter berøringsbevægelsen.
For eksempel, svirp op (teksttilstand) betyder at kommandoen vil blive udført hvis du svirper op, men kun hvis teksttilstand er aktiv.
Hvis kommandoen ikke har en tilstand knyttet til den, virker den uafhængigt af hvilken tilstand NVDA befinder sig i.

<!-- KC:beginInclude -->
For at skifte berøringstilstand, udfør et tryk med tre fingre.
<!-- KC:endInclude -->

#### Berøringstastatur {#TouchKeyboard}

Berøringstastaturet benyttes til at indtaste tekst og udføre kommandoer ved brug af en touchskærm.
Når fokus befinder sig på et editfelt, kan du dobbelttrykke ikonet for berøringstastaturet i bunden af skærmen for at vise tastaturet.
For tablets som Microsoft Surface Pro vil tastaturet altid være tilgængeligt, når disse tablets ikke er forbundet til en dock.
For at afvise berøringstastaturet, kan du dobbelttrykke ikonet for berøringstastaturet igen eller bevæge dig væk fra editfeltet.

Når berøringstastaturet vises på skærmen, kan du flytte en finger henover tasterne på tastaturet. Tastaturet befinder sig typisk i bunden af skærmen. Bevæg dig dernæst mellem tasterne med en finger.
Når du finder den ønskede tast, skal du dobbelttrykke med en finger eller løfte din finger, afhængigt af dine indstillinger i [indstillingskategorien  Berøringsinteraktion](#TouchInteraction).

### Tastaturhjælp {#InputHelpMode}

Mange vigtige kommandoer er nævnt i resten af denne brugervejledning, men en nem måde at udforske alle de forskellige tastekommandoer er ved at starte tastaturhjælpen.

For at slå tastaturhjælp til, skal du trykke på NVDA+1.
For at slå tastaturhjælp fra igen, tryk på NVDA+1.
Når tastaturhjælp er slået til, vil enhver udført kommando, såsom et tastetryk eller en udført berøringsbevægelse annoncere, hvilken handling den er knyttet til.
Selve kommandoerne vil ikke blive udført, mens tastaturhjælp er slåët til.

### NVDA-menuen {#TheNVDAMenu}

I NVDA-menuen kan du styre NVDA indstillingerne, få adgang til hjælp, gemme/gendanne din konfiguration, Ændre taleordbøger, få adgang til yderligere værktøjer og afslutte NVDA.

For at komme til NVDA-menuen fra et hvilket som helst sted i Windows, mens NVDA kører, kan du gøre følgende:

* Tryk på tasterne `NVDA+n` på tastaturet.
* Udfør et 2-fingers dobbelttryk på touchskærmen.
* Få adgang til systembakken ved at trykke på `Windows+b`, `pil ned` til NVDA-ikonet og trykke på `enter`.
* Alternativt kan du få adgang til systembakken ved at trykke på `Windows+b`, `pil ned` til NVDA-ikonet og åbne genvejsmenuen ved at trykke på `applications`-tasten, som er placeret ved siden af højre kontroltast på de fleste tastaturer.
På et tastatur uden en `applications`-tast skal du i stedet trykke på `shift+f10`.
* Højreklik på NVDA-ikonet i Windows-systembakken.

Når menuen vises, kan du bruge piletasterne til at navigere i menuen og `enter` for at aktivere.

### Grundlæggende NVDA-kommandoer {#BasicNVDACommands}

<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Touchbevægelse |Beskrivelse|
|---|---|---|---|---|
|Starter eller genstarter NVDA |Control+alt+n |Control+alt+n |ingen |Starter eller genstarter NVDA. Dette er en Windows-kommando tildelt til ikonet på skrivebordet under installationen, hvis den pågældende indstilling er markeret. Denne genvej kan ikke ændres via dialogen til håndtering af kommandoer.|
|Stop tale |Kontrol |Kontrol |enkelt tryk med to fingre |stopper talen med det samme|
|Pause Tale |Shift |Shift |Ingen |Sætter talen på pause. Når du trykker igen, fortsætter talen, hvor den slap (hvis pause er understøttet af den aktuelle talesyntese)|
|NVDA-menu |NVDA+n |NVDA+n |Dobbelttryk med to fingre |Fremkalder NVDA-menuen, så du får adgang til indstillinger, værktøjer og hjælp osv.|
|Skift Tastaturhjælp tilstand |NVDA+1 |NVDA+1 |Ingen |Hvis du trykker på en tast i denne tilstand vil tasten blive oplæst, sammen med den eventuelle NVDA kommando der er tilknyttet tasten|
|Afslut NVDA |NVDA+q |NVDA+q |Ingen |Afslutter NVDA|
|Slip næste tast igennem |NVDA+f2 |NVDA+f2 |Ingen |Fortæller NVDA at den næste tast slippes lige igennem til den aktive applikation, selv om det normalt er en NVDA kommando|
|Slå dvaletilstand til og fra |NVDA+Shift+s |NVDA+Shift+z |Ingen |Dvaletilstand deaktivere alle NVDA-kommandoer og tale/punkt output i det aktive program. Dette er mest brugbart når du benytter et program der gør brug af egne skærmlæsefunktioner. Tryk kommandoen en gang til for at deaktivere dvaletilstand.|

<!-- KC:endInclude -->

### Rapportering af Systemoplysninger {#ReportingSystemInformation}

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Sig dato/tid |NVDA+f12 |Tryk en gang for klokkeslæt, to gange for dato|
|Sig batteristatus |NVDA+Shift+b |Rapporterer batteristatus fx. om AC strømforsyning er tilsluttet eller om batteriet aflader.|
|Sig tekst i udklipsholderen |NVDA+c |Rapporterer tekst i udklipsholderen hvis der er nogen.|

<!-- KC:endInclude -->

### Taletilstande {#SpeechModes}

Taletilstande i NVDA bestemmer, hvordan indhold på skærmen, notifikationer og tale som følge af en kommando udtales.
Standardindstillingen er "tale", som aktiveres under almindelig brug af en skærmlæser.
Der er situationer eller specifikke programmer, hvor alternative taletilstande kan være fordelagtige.

De fire tilgængelige taletilstande er:

* Tale (Standard): Reagerer normalt på skærmændringer og notifikationer, samt andre situationer, der kræver tale. Dette inkludere også, når fokus flyttes, eller brug af kommandoer.
* Efter behov: Tal kun ved brug af specifikke kommandoer til oplæsning af tekst eller information (f.eks. kommandoen til at få vinduets titel oplæst). NVDA vil ikke sige noget, hvis du eksempelvis flytter fokus eller markøren.
* Fra: Ingen taleoutput, men reagerer stadig på kommandoer uden lyd, i modsætning til dvaletilstand.
* Bip: Erstatter tale med korte bip.

Biptilstand er nyttig ved kontinuerlig aktivitet, hvor detaljerne er mindre vigtige end selve aktiviteten. Dette kan eksempelvis være, når output ruller forbi i et terminalvindue, hvor det ikke nødvendigvis er relevant at noget står på skærmen, så længe noget aktivitet faktisk forekommer.

Tilstanden "Efter behov" er god, når du kun sporadisk behøver oplysninger om skærmaktiviteter.
Dette kan være ved lydoptagelse, brug af skærmforstørrelse, møder eller opkald.

En kommando lader dig skifte mellem taletilstande:
<!-- KC:beginInclude -->

| Navn |Tast |beskrivelse|
|---|---|---|
|Skift taletilstand |`NVDA+s` |Skifter mellem taletilstande.|

<!-- KC:endInclude -->

For at begrænse valgene af taletilstande, læs afsnittet [tilgængelige taletilstande ved brug af kommandoen til at skifte mellem disse](#SpeechModesDisabling).

## Navigering med NVDA {#NavigatingWithNVDA}

Med NVDA kan du udforske og navigerer i systemet på flere forskellige måder, både med normal brug og med gennemlæsning af skærmen.

### Objekter {#Objects}

Hvert program og selve operativsystemet består af mange objekter.
Et objekt er et enkelt emne såsom et stykke tekst, en knap, check box, skyder, liste eller redigerbart tekstfelt (editfelt).

### Navigering med systemfokus {#SystemFocus}

Systemfokus, også bare kendt som fokus, er [det objekt](#Objects) der modtager de tastetryk, du laver på tastaturet.
For eksempel, hvis du skriver i et redigerbart tekstfelt har tekstfeltet fokus.

Den mest almindelige måde at navigere rundt med NVDA i Windows er simpelthen ved at bevæge sig rundt med de almindelige Windows-tastatur kommandoer, såsom at trykke på Tab og Skift+TAB for at flytte frem og tilbage mellem kontrolelementerne, trykke ALT for at komme til menulinjen og derefter bruge pilene til at navigere i menuer, og bruge ALT + TAB for at flytte mellem kørende programmer.
Mens du gør dette, vil NVDA give dig oplysninger om det objekt, som har fokus såsom dets navn, type, værdi, tilstand, beskrivelse, tastaturgenvej og oplysninger om placering.
Når [Visuel Fremhævning](#VisionFocusHighlight) er aktiveret, vil systemmarkørens aktuelle fokus blive fremhævet på skærmen.

Der er nogle nyttige kommandoer, når du flytter fokus rundt i systemet:
<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Sig det aktuelle fokus |NVDA+Tab |NVDA+Tab |annoncerer det aktuelle objekt eller kontrol, der er i fokus. Tryk to gange for at få oplysningerne stavet|
|Sig titel |NVDA+t |NVDA+t |Rapporterer titlen på det aktive vindue. Tryk to gange for at få oplysningerne stavet. Tryk tre gange for at kopiere til udklipsholderen.|
|Læs det aktive vindue |NVDA+b |NVDA+b |Læser alle kontrolelementerne i det aktive vindue (nyttigt i dialogbokse)|
|Læs statuslinje |NVDA+End |NVDA+Shift+End |Annoncerer statuslinjen, hvis NVDA kan finde den. Tryk to gange for at få stavet informationen. Et tredje tryk vil kopiere informationen til udklipsholderen.|
|Oplys genvej Key |`shift+numpad2` |`NVDA+Ctrl+shift+.` |Oplyser genvejstasten for det objekt, der er i fokus|

<!-- KC:endInclude -->

### Navigering med systemmarkøren {#SystemCaret}

Når et [objekt](#Objects) der tillader navigation og/eller redigering af tekst har [fokus](#SystemFocus), kan du bevæge dig gennem teksten med systemmarkøren.

Når fokus er på et objekt der har en systemmarkør kan du bruge piletasterne, side op, side ned, hjem, end, osv. til at flytte igennem teksten
Du kan også ændre teksten hvis kontrollen understøtter redigering.
NVDA vil fortælle, hvad der sker, mens du bevæger dig imellem tegn, ord og linie, og vil også annoncere valgt og fravalgt tekst.

Følgende NVDA-kommandoer kan bruges i forbindelse med systemmarkøren:
<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Sig alt |NVDA+Pil-ned |NVDA+a |Starter læsningen fra markørens nuværende position og flytter markøren med ned i teksten|
|Læs aktuelle linje |NVDA+Pil-op |NVDA+l |Læser den linje, hvor markøren for øjeblikket befinder sig. Tryk to gange for at få linjen stavet. Tryk tre gange for at stave linjen ved brug af tegnbeskrivelser.|
|Læs den valgte tekst |NVDA+Shift+Pil-op |NVDA+Shift+s |Læser den tekst, som er blevet markeret|
|Rapportér tekstformatering |NVDA+f |NVDA+f |Oplyser formateringsinformation for systemmarkørens aktuelle position i et dokument. Ved et dobbelttryk vil denne information blive vist i gennemsynstilstand|
|Oplys linkets destination |`NVDA+k` |`NVDA+k` |Oplyser webadressen for linket ved systemmarkøren eller ved fokus. Hvis der trykkes to gange, vises linket i et vindue for lettere gennemgang|
|Oplys systemmarkørens position |NVDA+NumpadDelete |NVDA+Delete |Giver information om placeringen af teksten eller objektet ved systemmarkøren. Fx. procentdel af dokumentet, afstand fra kanten af siden eller den præcise position på skærmen. To tryk kan give flere detaljer.|
|Næste sætning |Alt+Pil-ned |Alt+Pil-ned |Flytter markøren til den næste sætning og læser den (kun understøttet i Microsoft Word og Outlook).|
|Forrige sætning |Alt+Pil-op |Alt+Pil-op |Flytter markøren til den forrige sætning og læser den (kun understøttet i Microsoft Word og Outlook).|

Når du er i en tabel, kan følgende kommandoer også bruges:

| Navn |Tast |Beskrivelse|
|---|---|---|
|Flyt til forrige kolonne |Ctrl+Shift+Venstre-pil |Flytter markøren til den forrige kolonne (i samme række)|
|Flyt til næste kolonne |Ctrl+Alt+Højre-pil |Flytter markøren til den næste kolonne (i samme række)|
|Flyt til forrige række |Ctrl+Alt+Pil-op |Flytter markøren til den forrige række (i den samme kolonne)|
|Flyt til næste række |Ctrl+Alt+Pil-ned |Flytter markøren til næste række (i den samme kolonne)|
|Flyt til første kolonne |ctrl+alt+hjem |Flytter markøren til den første kolonne (i den samme række)|
|Flyt til sidste kolonne |ctrl+alt+end |Flytter markøren til den sidste kolonne (i den samme række)|
|Flyt til første række |Ctrl+alt+side op |Flytter markøren til den første række (i den samme kolonne)|
|Flyt til sidste række |ctrl+alt+side ned |Flytter markøren til den sidste række (i den samme kolonne)|
|Sig alt i kolonne |`NVDA+Ctrl+alt+Pil ned` |Læser kolonnen lodret fra den aktuelle celle nedad til den sidste celle i kolonnen.|
|Sig alt i række |`NVDA+Ctrl+alt+Højre pil` |Læser rækken vandret fra den aktuelle celle mod højre til den sidste celle i rækken.|
|Læs hel kolonne |`NVDA+Ctrl+alt+pil op` |Læser den aktuelle kolonne lodret fra top til bund uden at flytte systemmarkøren.|
|Læs hel række |`NVDA+Ctrl+alt+venstre pil` |Læser den aktuelle række vandret fra venstre mod højre uden at flytte systemmarkøren.|

<!-- KC:endInclude -->

### Objektbaseret navigering {#ObjectNavigation}

For det meste vil du arbejde med kommandoer der ændrer [fokus](#SystemFocus) og [systemmarkøren](#SystemCaret).
Nogle gange kan det imidlertid værre, at du hellere vil udforske den aktuelle applikation eller operativsystemet uden at flytte fokus eller systemmarkøren.
Du kan også have nytte af at arbejde med [objekter](#Objects) der nomalt ikke kan benyttes af tastaturet.
I disse situationer kan du bruge objektbaseret navigation.

Objektbaseret navigation lader dig bevæge dig mellem og skaffe information om de individuelle [objekter](#Objects).
Når du flytter til et objekt, vil NVDA rapportere det på samme måde, som det sker med systemfokus.
Du kan også benytte den såkaldte [skærmlæsetilstand](#ScreenReview) til at læse al tekst, præcis som den vises på skærmen.

I stedet for at skulle flytte frem og tilbage mellem hvert enkelt objekt i systemet, er objekterne grupperet i et hierarki.
Dette betyder, at nogle objekter kan indeholde andre objekter, og at du skal åbne objekterne for at få adgang til objekter inde i dem.
Fx.: En liste indeholder listeemner. Så du må gå ind i listen for at komme til dens listeemner.
Hvis du har fundet et emne i listen, kan du komme til andre emner i listen ved at gå til forrige eller næste objekt.
Du kan komme tilbage til selve listen ved at gå til det overordnede objekt for listeemnet.
Derefter kan du bevæge dig forbi listen, hvis du ønsker, at udforske andre objekter.
På samme måde er der kontroller (fx. knapper) inde i en værktøjslinje. Så du skal gå ind i værktøjslinjen for at komme til kontrollerne i værktøjslinjen.

Hvis du stadig ønsker at navigere mellem hvert enkelt objekt i systemet, kan du bruge kommandoer til at skifte mellem forrige og næste objekt i en flad visning.
For eksempel, hvis du skifter til det næste objekt i denne visning og det aktuelle objekt indeholder underobjekter, vil NVDA automatisk skifte til det første underobjekt.
Men hvis det aktuelle objekt ikke har nogle underobjekter, vil NVDA navigere til det næste objekt på samme hierarkiske niveau.
Hvis der ikke findes et sådant objekt, søger NVDA videre op i hierarkiet, indtil der ikke er flere objekter at skifte til.
Samme princip gælder, når man navigerer bagud i hierarkiet.

Det objekt, du er i gang med at gennemse, kaldes for navigatorobjektet.
Når du navigerer til et objekt, kan du gennemse det ved at benytte [ kommandoerne til gennemsyn af tekst](#ReviewingText) når du befinder dig i [objektlæsetilstand](#ObjectReview).
Når [Visuel Fremhæving](#VisionFocusHighlight) er aktiveret, vil det aktuelle navigatorobjekt blive fremhævet på skærmen.
Som standard, flytter navigator objektet sammen med System fokus, men denne adfærd kan slås til  og fra.

Bemærk: Du kan konfigurere, hvordan punkt skal følge objektnavigation under [Punkt følger](#BrailleTether).

For at navigere imellem objekter, skal du benytte følgende kommandoer:

<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Touchbevægelse |Beskrivelse|
|---|---|---|---|---|
|Sig aktuelle objekt |NVDA+Numpad5 |NVDA+Shift+o |Ingen |Annoncerer det aktuelle navigatorobjekt. Tryk to gange for at få stavet oplysningerne, og tryk tre gange for at kopiere objektets navn og værdi til udklipsholderen.|
|Flyt til det overordnede objekt |NVDA+Numpad8 |NVDA+Shift+Pil-op |Svirp op (objekttilstand) |Navigerer til det overordnede objekt i forhold til det aktuelle navigatorobjekt|
|Gå til forrige objekt |NVDA+Numpad4 |NVDA+Shift+Venstre-pil |ingen |Flytter til objektet før det aktuelle navigatorobjekt|
|Gå til forrige objekt i flad visning |NVDA+numpad9 |NVDA+shift+ø |Svirp til venstre (objekttilstand) |Flytter til det forrige objekt i en flad visning af objektnavigationshierarkiet|
|Gå til næste objekt |NVDA+Numpad6 |NVDA+Shift+Højre-pil |Svirp til højre (objekttilstand) |Flytter til objektet efter det aktuelle navigatorobjekt|
|Gå til næste objekt i flad visning |NVDA+numpad3 |NVDA+shift+' |Svirp til højre (objekttilstand) |Flytter til det næste objekt i en flad visning af objektnavigationshierarkiet|
|Gå til første underordnede objekt |NVDA+Numpad2 |NVDA+Shift+Pil-ned |Svirp ned (objekttilstand) |Flytter til det første objekt, som er indeholdt i det aktuelle navigatorobjekt.|
|Gå til objektet i fokus |NVDA+Numpad-Minus |NVDA+Backmellemrum |Ingen |Flytter til det objekt, som er i fokus. Placerer også læsemarkøren ved systemmarkøren, hvis den er synlig.|
|Aktivér aktuelle navigatorobjekt |NVDA+Numpad-Enter |NVDA+Enter |Dobbelttryk |Aktiverer det nuværende navigatorobjekt (svarende til at klikke med musen eller trykke på mellemrums tasten, når det er i fokus)|
|Flyt systemfokus eller systemmarkør til den aktuelle læseposition |NVDA+Shift+Numpad-Minus |NVDA+Shift+Backmellemrum |Ingen |Tryk en gang for at flytte systemfokus til det nuværende navigatorobjekt. Tryk to gange for at flytte systemmarkøren til læsemarkøren.|
|Oplys læsemarkørens position |NVDA+Skift+NumpadDelete |NVDA+Skift+Delete |Ingen |Giver information om placeringen af teksten eller objektet ved læsemarkøren. Fx. procentdel af dokumentet, afstand fra kanten af siden eller den præcise position på skærmen. To tryk kan give flere detaljer.|
|Flyt læsemarkøren til statuslinjen |ingen |ingen |ingen |Oplyser, hvad der står på statuslinjen, hvis NVDA kan finde den. Dette flytter også læsemarkøren til statuslinjens placering.|

<!-- KC:endInclude -->

Bemærk: For at det numeriske tastatur skal fungere korrekt, skal Num Lock-tasten være slået fra.

### Gennemsyn af tekst {#ReviewingText}

NVDA giver dig mulighed for at læse indholdet af [skærmen](#ScreenReview), det aktuelle [dokument](#DocumentReview) eller det aktuelle [objekt](#ObjectReview) ved enten at flytte imellem tegn, ord eller linjer.
Dette er mest nyttigt i Windows kommando konsol vinduer og andre steder, hvor der er en begrænset eller ikke-eksisterende [systemmarkør](#SystemCaret).
For eksempel kan du bruge denne markør til at gennemse en lang besked i en dialog.

Når man bevæger sig rundt med den ubegrænsede markør flytter systemets markør ikke med, så du kan gennemse teksten på skærmen uden at tabe det sted af syne, hvor du er ved at redigere.
Men når du flytter rundt med systemets markør, følger den ubegrænsede markør som standard med.
Dette kan slås til og fra.

Bemærk: Hvordan punkt skal følge læsemarkøren kan konfigureres via indstillingen [Punkt følger](#BrailleTether).

Følgende tastekommandoer er tilgængelige for gennemsyn af tekst:
<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Touchbevægelse |Beskrivelse|
|---|---|---|---|---|
|Gå til øverste linje i læsetilstand |Shift+Numpad-7 |NVDA+Ctrl+Home |Ingen |Flytter læsemarkøren til den øverste linje af teksten|
|Gå til forrige linje i læsetilstand |Numpad-7 |NVDA+Pil-op |Svirp op (teksttilstand) |Flytter læsemarkøren til forrige linje i teksten|
|Læs aktuelle linje i læsetilstand |Numpad8 |NVDA+Shift+. |Ingen |Læser den linje, hvor læsemarkøren er placeret. Tryk to gange for at få linjen stavet. Tryk tre gange for at få linjen stavet fonetisk.|
|Gå til næste linje i læsetilstand |Numpad9 |NVDA+Pil-ned |Svirp ned (teksttilstand) |Flytter læsemarkøren til næste linje i teksten|
|Gå til nederste linje i læsetilstand |Shift+Numpad9 |NVDA+Ctrl+End |Ingen |Flytter læsemarkøren til nederste linje i teksten|
|Flyt til forrige ord i læsetilstand |Numpad4 |NVDA+Ctrl+Venstre-pil |Svirp til venstre med to fingre |Flytter læsemarkøren til forrige ord i teksten|
|Læs aktuelle ord i læsetilstand |Numpad5 |NVDA+Ctrl+. |Ingen |Læser det ord i teksten, hvor læsemarkøren er placeret. Tryk to gange for at stave ordet. Tryk tre gange for at stave ordet fonetisk.|
|Gå til næste ord i læsetilstand |Numpad6 |NVDA+Ctrl+Højre-pil |Svirp til højre med to fingre |Flytter læsemarkøren til næste ord i teksten|
|Gå til starten af linje i læsetilstand |Shift+Numpad1 |NVDA+Home |Ingen |Flytter læsemarkøren til starten af den aktuelle linje i teksten|
|Flyt til forrige tegn i læsetilstand |Numpad1 |NVDA+Venstre-pil |Svirp til venstre (teksttilstand)| Flytter læsemarkøren til forrige tegn på den aktuelle linje i teksten|
|Læs aktuelle tegn i læsetilstand |Numpad2 |NVDA+. |Ingen |Læser det aktuelle tegn på den linje i teksten, hvor læsemarkøren er placeret. To tryk giver en beskrivelse eller et eksempel på tegnet. Tryk tre gange for at få den numeriske værdi af tegnet (decimal og hexadecimal).|
|Gå til næste tegn i læsetilstand |Numpad3 |NVDA+Højre-pil |Svirp til højre (teksttilstand) |Flytter læsemarkøren til næste tegn på den aktuelle linje i teksten|
|Gå til slutningen af linje i læsetilstand |Shift+Numpad3 |NVDA+End |Ingen |Flytter læsemarkøren til slutningen af den aktuelle linje i teksten|
|Gå til forrige side i læsetilstand |`NVDA+Side op` |`NVDA+shift+Side op` |ingen |Flytter læsemarkøren til den forrige side med tekst, hvis denne funktion understøttes af det aktuelle program|
|Flyt til næste side i læsetilstand |`NVDA+Side ned` |`NVDA+shift+Side ned` |ingen |Flytter læsemarkøren til den næste side med tekst, hvis denne funktion understøttes af det aktuelle program|
|Sig alt i læsetilstand |Numpad-plus |NVDA+Shift+a |Svirp ned med tre fingre (teksttilstand) |Læser fra læsemarkørens aktuelle position og flytter den under læsningen|
|Vælg og derefter kopier fra læsemarkør |NVDA+f9 |NVDA+f9 |Ingen |Begynder vælge og kopiere processen fra læsemarkørens aktuelle position. Den faktiske handling finder ikke sted, før du fortæller NVDA, hvor udvælgelsen af teksten afsluttes.|
|Vælg og kopier til læsemarkør |NVDA+f10 |NVDA+f10 |Ingen |Ved et tryk, vil tekst blive valgt fra den tidligere startmarkør, som er blevet sat, til og med læsemarkørens aktuelle position. Hvis systemmarkøren kan nå den aktuelle tekst, vil systemmarkøren flytte dertil. Når du trykker på denne tast to gange, bliver teksten kopieret til Windows udklipsholderen.|
|Flyt til starten af markeringen  for kopiering for læsemarkør |NVDA+shift+f9 |NVDA+shift+f9 |none |Flytter læsemarkøren til placeringen for den tidligere indstillede startmarkering til kopiering|
|Sig tekstformatering |NVDA+f |NVDA+f |Ingen |Annoncerer formateringen af teksten ved læsemarkørens position. Trykkes dette to gange vil informationen blive vist i gennemsynstilstand|
|Rapportér aktuelle symbolerstatning |Ingen |Ingen |Ingen |Oplyser symbolet for læsemarkørens aktuelle position. Ved to tryk vises symbolet og tekste der bruges til at udtale symbolet i gennemsynstilstand.|

<!-- KC:endInclude -->

Bemærk: For at det numeriske tastatur skal fungere korrekt, skal Numlock-tasten være slået fra.

En god måde at huske kommandoerne til tekstlæsning i desktop-layout på er at sammenligne dem med en tabel eller et skema med tre gange tre felter. Fra toppen til bunden er det linje, ord og tegn. Fra venstre mod højre er det forrige, aktuelle og næste.
Layoutet kan illustreres på følgende måde:

| . {.hideHeaderRow} |. |.|
|---|---|---|
|Forrige linje |Aktuelle linje |Næste linje|
|Forrige ord |Aktuelle ord |Næste ord|
|Forrige tegn |Aktuelle tegn |Næste tegn|

### Læsetilstande {#ReviewModes}

med NVDAs [kommandoer til tekstlæsning](#ReviewingText) kan du læse indhold i det aktuelle navigatorobjekt, det aktuelle dokument eller skærmen, afhængigt af hvilken læsetilstand der benyttes.

Du skifter mellem læsetilstandene med følgende kommandoer:
<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Touchbevægelse |Beskrivelse|
|---|---|---|---|---|
|skift til næste læsetilstand |NVDA+Numpad7 |NVDA+sideOp |svirp op med to fingre |skifter til den næste tilgængelige læsetilstand.|
|skift til forrige læsetilstand |NVDA+Numpad1 |NVDA+sideNed |Svirp ned med to fingre |skifter til den forrige tilgængelige læsetilstand.|

<!-- KC:endInclude -->

#### ObjektLæsetilstand {#ObjectReview}

Når du benytter objektlæsetilstand, er du kun i stand til at læse indholdet af det aktuelle [navigatorobjekt](#ObjectNavigation).
I forhold til objekter som redigeringsfelter (edit-felter)eller andre grundlæggende elementer, ville dette typisk være tekstindholdet.
For andre objekter kan det muligvis være navnet eller dets værdi.

#### Dokumentlæsetilstand {#DocumentReview}

Når [navigatorobjektet](#ObjectNavigation) befinder sig i et dokument, hvori gennemsynstilstanden benyttes (fx. en webside) eller andre komplekse dokumenter, der indeholder mange objekter (fx. Lotus Symphony dokumenter) er det muligt at skifte til dokumentlæsetilstand.
Med dokumentlæsetilstand kan du gennemse hele dokumentet.

Når du skifter fra objektlæsetilstand til dokumentlæsetilstand, placeres markøren i dokumentet ved positionen for det aktuelle navigatorobjekt.
Når du flytter rundt i dokumentet med læsekommandoer, bliver navigatorobjektet automatisk opdateret, så det svarer til objektet ved den aktuelle markørposition.

Bemærk, at NVDA automatisk vil skifte til dokument læsetilstand fra objekt læsetilstand når der bevæges rundt i dokumenter der kræver gennemsynstilstand.

#### Skærm Læsetilstand {#ScreenReview}

Med skærmtilstand kan du gennemse teksten, sådan som den optræder visuelt på skærmen i det aktuelle program.
Dette kan sammenlignes med "screen review" eller "mouse cursor" i andre skærmlæseprogrammer.

Når du skifter til Skærmlæsetilstand placeres læsemarkøren på skærmpositionen for det aktuelle [navigatorobjekt](#ObjectNavigation).
Når du flytter rundt på skærmen med læsekommandoer, bliver navigatorobjektet automatisk opdateret, så det svarer til objektet ved den aktuelle markørposition.

Bemærk, at NVDA muligvis ikke kan se hele eller dele af teksten i nogle af applikationer på grund af nyere teknologier brugt til at tegne skærmen. Disse teknologier er umulige at understøtte på nuværende tidspunkt.

### Navigering ved brug af musen {#NavigatingWithTheMouse}

Når du bevæger musen, rapporterer NVDA som standard tekst, der er direkte under musemarkøren, mens den bevæger sig hen over teksten.
Der hvor det kan lade sig gøre, vil NVDA læse det omkringstående tekstafsnit, selv om der i nogle felter kun er tale om den aktuelle linje.

NVDA kan desuden konfigureres til også at annoncere typen af det [objekt](#Objects) musen bevæger sig over, (f.eks listboks, trykknap osv.)..
Dette kan være nyttigt for helt blinde brugere hvor teksten nogle gange ikke er nok.

NVDA gør det muligt for brugerne at finde ud af, hvor musen er placeret på skærmen, ved at afspille musens position som biptoner.
Jo højere oppe musen befinder sig på skærmen, jo højere tonehøjde har lydsignalerne.
Jo mere til venstre eller højre musen er på skærmen, jo mere til venstre eller højre vil lyden synes at komme fra (under forudsætning at du har stereohøjttalere) eller hovedtelefoner.

Disse ekstra musefunktioner er ikke slået til som standard i NVDA
Hvis du ønsker at drage fordel af dem, kan de konfigureres fra [Indstillingskategorien Mus,](#MouseSettings) som findes i dialogen [Indstillinger](#NVDASettings) i NVDA-menuen.

Selv om du bør bruge en fysisk mus eller et pegefelt til at navigere med musen, har NVDA et par vigtige kommandoer relateret til brugen af mus:

<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Touchbevægelse |Beskrivelse|
|---|---|---|---|---|
|Venstre museklik |Numpad-skråstreg |NVDA+[ |Ingen |Klikker en enkelt gang med venstre museknap. Det almindelige dobbeltklik kan udføres ved at trykke på denne tastekombination to gange hurtigt efter hinanden.|
|Lås venstre museknap |Shift+Numpad-divideret-med |NVDA+ctrl+[ |Ingen |Låser venstre museknap i nedtrykket tilstand. Tryk igen for at slippe den. Hvis du vil trække med musen, så tryk på denne tast for at låse museknappen, og flyt så musen, enten fysisk eller med en af de andre musekommandoer.|
|Højre museklik |Numpad-stjerne |NVDA+] |Tryk og hold |Klikker en enkelt gang med højre museknap.|
|Lås højre museknap |Shift+Numpad-stjerne |NVDA+ctrl+] |Ingen |Låser højre museknap i nedtrykket tilstand. Tryk igen for at slippe den. Hvis du vil trække med musen, så tryk på denne tast for at låse museknappen, og flyt så musen, enten fysisk eller med en af de andre musekommandoer.|
|Rul opad ved musens position |ingen |ingen |ingen |Ruller musen opad ved musens aktuelle position|
|Rul nedad ved musens position |ingen |ingen |ingen |Ruller musen nedad ved musens aktuelle position|
|Rul til venstre ved musens position |ingen |ingen |ingen |Ruller musen til Venstre ved musens aktuelle position|
|Rul nedad ved musens position |ingen |ingen |ingen |Ruller musen nedad ved musens aktuelle position|
|Flyt musen til det aktuelle navigatorobjekt |NVDA+Numpad-skråstreg |NVDA+Shift+m |Ingen |Flytter musen til positionen for det aktuelle navigatorobjekt og læsemarkøren|
|Flyt til objektet ved musen |NVDA+Numpad-stjerne |NVDA+Shift+n |Ingen |Flytter navigatorobjektet til objektet ved musens aktuelle position|

<!-- KC:endInclude -->

## Gennemsynstilstand {#BrowseMode}

Komplekse dokumenter, der ikke kan redigeres, fx. web-sider, bliver præsenteret med NVDA i gennemsynstilstand.
Dette omfatter dokumenter i følgende applikationer:

* Mozilla Firefox
* Microsoft Internet Explorer
* Mozilla Thunderbird
* HTML-meddelelser i Microsoft Outlook
* Google Chrome
* Microsoft Edge
* Adobe Reader
* Foxit Reader
* Understøttede bøger i Amazon Kindle for PC

Gennemsynstilstand kan også valgfrit benyttes i Microsoft Word-dokumenter.

Når du benytter gennemsynstilstand, bliver indholdet af dokumentet præsenteret i en flad visning, som du kan navigere rundt i ved hjælp af piletasterne, præcist som hvis det var et normalt dokument.
Alle NVDAs kommandoer der benytter [systemmarkøren](#SystemCaret) fungerer i denne tilstand; fx. læs alt, rapportér tekstformatering, kommandoer til navigering af tabeller, osv.
Når [Visuel Fremhævning](#VisionFocusHighlight) er aktiveret, vil markøren i gennemsynstilstand blive fremhævet på skærmen.
Oplysninger såsom, om teksten er et link, en overskrift osv bliver annonceret sammen med teksten mens du bevæger dig rundt.

Nogle gange får du brug for at interagere direkte med kontrollerne i disse dokumenter.
For eksempel har du behov for dette, når du arbejder med redigerbare tekstfelter og lister, så du kan indtaste bogstaver, samt bruge piletasterne til at finde rundt i listen.
Du gør dette ved at skifte til fokustilstand hvor næsten alle taster bliver sluppet igennem til det program eller det felt, du står i.
Når du er i gennemsynstilstand, vil NVDA som udgangspunkt automatisk skifte til fokustilstand, hvis du tabber til eller klikker på en kontrol, der kræver det.
Tilsvarende, når du tab'er til eller klikker på et felt, hvor der ikke kræves fokustilstand, skifter NVDA automatisk tilbage til gennemsynstilstand.
Du kan også trykke på Enter eller Mellemrum for at skifte til fokustilstand i de felter, som kræver det.
Tryk på Escape for at skifte tilbage til gennemsynstilstand.
Derudover kan du også manuelt tvinge NVDA i fokustilstand, hvorefter tilstanden vil forblive i kraft indtil du selv slår den fra.

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Skift mellem gennemsyns- og fokustilstand |NVDA+Mellemrum |Skifter mellem gennemsynstilstand og fokustilstand|
|Forlad fokustilstand |Escape |Skifter tilbage til gennemsynstilstand, hvis NVDA havde skiftet automatisk til fokustilstand|
|Opdater dokument i gennemsynstilstand |NVDA+f5 |Genindlæser det aktuelle dokument. (Kan være nyttigt, hvis noget af indholdet synes at mangle. Ikke tilgængelig i Microsoft Word og Outlook.)|
|Søg |NVDA+Ctrl+f |Viser en dialog, hvor du kan indtaste den tekst, du vil søge efter i det aktuelle dokument. Læs [søg efter tekst](#SearchingForText) for mere information.|
|Find næste |NVDA+f3 |Finder næste forekomst i dokumentet af den tekst, du tidligere har søgt efter|
|Find forrige |NVDA+Shift+F3 |Finder forrige forekomst i dokumentet af den tekst, du tidligere har søgt efter|

<!-- KC:endInclude -->

### Bogstavnavigering {#SingleLetterNavigation}

For hurtigere at kunne navigere når du er i gennemsynstilstand, giver NVDA også mulighed for ved hjælp af et enkelt bogstav at springe til bestemte områder i dokumentet.
Bemærk, at ikke alle disse kommandoer understøttes i alle dokumenttyper.

<!-- KC:beginInclude -->
Hvis du trykker en af de følgende taster ned alene, hopper du til den næste forekomst af det pågældende element. Hvis du trykker tasten ned sammen med Skift, hopper du til det forrige element.

* h: overskrift
* l: liste
* i: punkt i liste
* t: tabel
* k: link
* n: tekst, som ikke er et link
* f: formularfelt
* u: ubesøgt link
* v: besøgt link
* e: editfelt
* b: Knap
* x: Check box
* c: combo box
* r: radioknap
* q: blokcitat
* s: separator
* m: ramme
* g: grafik
* d: landmærke
* o: indlejret objekt (lyd- og videoafspiller, apllikation, dialog, osv.)
* 1-6: overskrifter på niveauer fra 1 til 6.
* a: Annotation (kommentar, revision o.s.v.)
* `p`: Tekstafsnit
* w: Stavefejl

For at flytte til begyndelsen eller slutningen af overordnede elementer, fx. lister eller tabeller:

| Navn |Tast |Beskrivelse|
|---|---|---|
|Flyt til starten af overordnede element |Shift+Komma |Flytter til starten af det overordnede element, liste tabel osv., hvor systemmarkøren er placeret.|
|Flyt forbi slutningen af det overordnede element |Komma |Flytter forbi slutningen af det overordnede element, liste tabel osv., hvor systemmarkøren er placeret.|

<!-- KC:endInclude -->

Nogle web-applikationer, som f.eks. Gmail, Twitter og Facebook, bruger bogstaver som genvejstaster.
Hvis du gerne vil kunne bruge disse genvejstaster og stadig være i stand til at bruge markørtasterne til at læse i gennemsynstilstand, kan du midlertidigt slå NVDAs bogstavnavigering fra.
<!-- KC:beginInclude -->
Du kan slå bogstavnavigering til og fra i det aktuelle dokument ved at trykke på NVDA+Shift+Mellemrum.
<!-- KC:endInclude -->

#### Navigationskommando til tekstafsnit {#TextNavigationCommand}

Du kan hoppe til det næste eller forrige tekstafsnit ved at trykke `p` eller `shift+p`.
Tekstafsnit defineres som en gruppe tekst, der synes at være skrevet i fuldstændige sætninger.
Dette kan være nyttigt for at finde begyndelsen på læsbart indhold på forskellige websteder, såsom:

* Nyhedshjemmesider
* Fora
* Blogindlæg

Disse kommandoer kan også være nyttige til at springe visse former for rod over, såsom:

* Annoncer
* Menuer
* Overskrifter

Bemærk dog, at selvom NVDA gør sit bedste for at identificere tekstafsnit, er algoritmen ikke perfekt og kan til tider lave fejl.
Desuden er denne kommando ikke den samme som kommandoer til navigation mellem afsnit `controll+pil op og ned`.
Navigation mellem tekstafsnit springer kun mellem tekstafsnit, mens kommandoer til navigation mellem afsnit tager markøren til det forrige/næste afsnit uanset om de indeholder tekst eller ej.

#### Andre navigationskommandoer {#OtherNavigationCommands}

Udover kommandoerne til bogstavnavigering nævnt ovenfor, har NVDA desuden også yderligere kommandoer, der ikke er tildelt et tastetryk.
Før du kan bruge disse kommandoer, skal du tildele et tastetryk til dem ved brug af [dialogen "Håndter kommandoer"](#InputGestures).
Her er en liste over tilgængelige kommandoer:

* Artikel
* Figur
* Gruppering
* Fane
* Menupunkt
* Skifteknap
* Behandlingslinje
* Matematikformel
* Lodret justeret afsnit
* Tekst med den samme typografi
* Tekst med en anden typografi

Bemærk, at to kommandoer eksisterer for hver enkelt element. Du skal derfor huske at tildele et tastetryk til kommandoerne, der flytter til forrige og næste element.
Hvis du eksempelvis vil bruge `y` / `shift+y` til hurtigt at flytte til næste og forrige fane, skal du gøre følgende:

1. Åbne dialogen til håndtering af kommandoer, når du er i gennemsynstilstand.
1. Find "Flytter til næste fane" under "Gennemsynstilstand".
1. Tildel bogstavet `y` som tastetryk.
1. Find "flytter til forrige fane".
1. Tildel bogstavet `shift+y` som tastetryk.

### Elementlisten {#ElementsList}

Elementlisten giver adgang til en liste med  forskellige typer elementer i dokumentet, alt efter hvilket program du bruger.
F.eks., i web-browsere kan kan elementlisten vise links, overskrifter, knapper og landmærker.
Med radioknapper kan du skifte mellem de forskellige typer elementer.
Ved hjælp af Et editfelt kan du filtrere listen, så du kan søge efter et bestemt element på siden.
Når du har valgt et element, kan du bruge knapperne i dialogen til at flytte til, eller aktivere det pågældende element.
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Elementliste i gennemsynstilstand |NVDA+f7 |Giver Element listen som indeholder forskellige elementer i det nuværende dokument|

<!-- KC:endInclude -->

### Søg efter tekst {#SearchingForText}

Denne dialog lader dig søge efter tekst i det aktuelle dokument.
I feltet "Skriv teksten, du ønsker at finde" kan du indtaste den tekst, du vil søge efter.
Boksen "Forskel på store og små bogstaver" bestemmer omsøgningen skal tage forbehold for store og små bogstaver.
F.eks. hvis boksen er valt, kan du finde "NV Access" men ikke "nv access".
Brug følgende kommandoer for at udføre en søgning:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Find tekst |NVDA+control+f |Åbner søgedialogen|
|Find næste |NVDA+f3 |Søger efter den næste forekomst af den aktuelle søgning|
|Find forrige |NVDA+shift+f3 |Søger efter den forrige forekomst af den aktuelle søgning|

<!-- KC:endInclude -->

### Indlejrede objekter {#ImbeddedObjects}

Sider kan ved hjælp af teknologier som Oracle Java og HTML5 omfatte meget dynamisk indhold, såsom applikationer og dialoger.
Når man støder på disse objekter i i et dokument, vil NVDA henholdsvist annoncere "Indlejret objekt", "applikation" og "dialog".
Du kan hurtigt flytte til dem ved brug af O og shift+O bogstavnavigationstasterne til indlejrede objekter.
Du kan trykke Enter på disse objekter for at aktivere dem.
Hvis objektet er tilgængeligt, kan du derefter tabbe rundt indenfor det og interagere med det som ethvert andet program
du kan med et tastetryk vende tilbage til den oprindelige side, der indeholder det indlejrede objekt:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Gå til det overordnede dokument i gennemsynstilstand |NVDA+Ctrl+Mellemrum |Flytter fokus ud af det aktuelle indlejrede objekt og ind i dokumentet, som indeholder objektet|

<!-- KC:endInclude -->

### Oprindelig markeringstilstand {#NativeSelectionMode}

Når du vælger tekst ved brug af `shift+piletasterne`, vil teksten kun blive valgt i NVDAs præsentation af webindholdet, og ikke i selve browseren.
Dette betyder, at markeringen af tekst ikke er synlig på skærmen, når du bruger `control+c`. Det er udelukkende tekst, der kopieres. Derfor bevares formatering af tabeller, eller om noget er et link ikke i det indhold, som du har kopieret.
NVDA har en indstilling, der kan aktiveres, der vil bevare denne formatering. Dette hedder "Oprindelig markeringstilstand". Dette virker indtil videre kun i Mozilla Firefox.

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Slå oprindelig markeringstilstand til og fra |`NVDA+shift+f10` |Slår oprindelig markeringstilstand til og fra|

<!-- KC:endInclude -->

Når denne indstilling er aktiveret, vil det oprindelige indhold blive kopieret med `control+c`, herunder formateringen af den valgte tekst.
Dette betyder, at indsættelse af din markering vil bevare formateringen (f.eks. hvis noget er et link eller en tabel) i f.eks. Microsoft Word.
Bemærk dog, at i denne tilstand, vil særlige tilgængelighedsegenskaber for webindhold, eller andet, som NVDA genererer, ikke kopieres.
Bemærk også, at programmet vil forsøge at markere det samme indhold som i gennemsynstilstand, men dette kan nogle gange forekomme unøjagtigt.
Funktionaliteten er dog nyttig i situationer, hvor du skal kopiere hele tabeller.

## Læsning af matematisk materiale {#ReadingMath}

NVDA er i stand til både at læse og navigere i forskelligt matematikindhold på internettet og andre programmer, og gengive indholdet på punkt eller via tale.
Før du kan læse og benytte matematisk indhold med NVDA, skal du først installere en komponent, der kan bearbejde indholdet.
Der er adskillige tilføjelser tilgængelige, der kan arbejde sammen med matematisk indhold, herunder [MathCAT NVDA add-on](https://nsoiffer.github.io/MathCAT/) og [Access8Math](https://github.com/tsengwoody/Access8Math). Disse kan hentes i tilføjelsescenteret.
Læs venligst afsnittet om [Tilføjelsescenteret](#AddonsManager) for at finde ud af, hvordan du installerer tilføjelser.
NVDA kan også benytte den gamle [MathPlayer](https://info.wiris.com/mathplayer-info) software fra Wiris. Bemærk dog, at softwaren ikke længere vedligeholdes.

### Understøttet matematikindhold {#SupportedMathContent}

NVDA understøtter følgende typer af matematisk indhold:

* MathML i Mozilla Firefox, Microsoft Internet Explorer og Google Chrome.
* Microsoft Word 365 moderne matematikligninger via UI automation:
NVDA er i stand til at læse og interagere med matematikligninger i Microsoft Word 365/2016 build 14326 og nyere.
Bemærk, at du først skal konvertere dine MathType ligninger til Office ligninger.
Dette gøres ved at vælge ligningen, og derefter vælge "Equation options>Convert to Office Math" fra kontekstmenuen. Dette skal gøres for hver ligning.
Sørg for, at du har den seneste udgave af Mathtype, før du gør dette.
Microsoft Word lader dig nu også  navigere lineært mellem symbolerne i selve ligningen, og understøtter desuden indtastning af matematik i forskellige formater, herunder LateX.
For yderligere oplysninger, læs [Ligninger i lineært format ved hjælp af UnicodeMath og LaTeX i Word](https://support.microsoft.com/da-dk/office/linear-format-equations-using-unicodemath-and-latex-in-word-2e00618d-b1fd-49d8-8cb4-8d17f25754f8)
* Microsoft Powerpoint og ældre versioner af Microsoft Word:
NVDA kan læse og navigere i MathType-ligninger i Microsoft Powerpoint og Microsoft word.
MathType skal være installeret, for at dette kan virke.
Prøveversionen er tilstrækkelig.
Programmet kan hentes fra [MathPlayer information page](https://info.wiris.com/mathplayer-info).
* Adobe Reader.
Bemærk, at dette endnu ikke er en officiel standard, så der er i øjeblikket ingen offentligt tilgængelige programmer, som kan producere dette indhold.
* Kindle Reader for PC:
NVDA kan læse og navigere i matematisk indhold i Kindle for PC, hvis bøgerne benytter tilgængelige matematikløsninger.

Når du læser et dokument, vil NVDA udtale understøttet matematisk indhold der, hvor det forekommer.
Hvis du bruger et punktdisplay, vil det også blive vist på punkt.

### Interaktiv navigering {#InteractiveNavigation}

Hvis du primært bruger tale, vil du sandsynligvis i de fleste tilfælde ønske at undersøge det matematiske udtryk i mindre bidder i stedet for at høre hele udtrykket på en gang.

Hvis du befinder dig i gennemsynstilstand, kan du gøre dette ved at flytte markøren til det matematiske indhold og trykke Enter.

Hvis du ikke er i gennemsynstilstand:

1. Flyt læsemarkøren til det matematiske indhold.
Som udgangspunkt følger læsemarkøren systemmarkøren, så som regel kan du bare bruge systemmarkøren til at gå til det ønskede indhold.
1. Aktivér så følgende kommando:

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Interager med matematikindhold |NVDA+Alt+m |Starter interaktion med matematikindhold|

<!-- KC:endInclude -->

På dette tidspunkt vil NVDA gå ind i matematiktilstand, hvor du eksempelvis kan bruge piletasterne, til at udforske udtrykket.
For eksempel kan du flytte gennem udtrykket med Venstre- og Højre-pil og zoome ind på en del af udtrykket, f.eks. en brøk, med Pil-ned.

Når du vil tilbage til dokumentet, skal du blot trykke på Escape-tasten.

For flere informationer om, hvordan du læser og navigere i matematisk indhold, skal du læse afsnittet for den pågældende tilføjelse, som du har installeret.

* [MathCAT documentation](https://nsoiffer.github.io/MathCAT/users.html)
* [Access8Math documentation](https://github.com/tsengwoody/Access8Math)
* [MathPlayer documentation](https://docs.wiris.com/mathplayer/en/mathplayer-user-manual.html)

Nogle gange kan matematisk indhold blive præsenteret som en knap eller en anden type element, hvilket evt. viser en dialog eller yderligere informationer om formeln, når denne aktiveres.
For at aktivere knappen eller elementet, der indeholder formlen, tryk Ctrl+enter.

### Installation af MathPlayer {#InstallingMathPlayer}

Selvom det generelt anbefales, at du benytter én af de nyere tilføjelser til at læse matematisk indhold i NVDA, kan der stadig være situationer, hvor MathPlayer er et mere passende valg.
F.eks. kan det være, at MathPlayer understøtter matematik på punktskrift for et sprog, som én af de nyere tilføjelser ikke understøtter endnu.
MathPlayer er gratis tilgængelig fra Wiris-websiden.
[Download MathPlayer](https://downloads.wiris.com/mathplayer/MathPlayerSetup.exe).
Efdter installationen af MathPlayer, skal du genstarte NVDA.
Bemærk, at informationerne på siden antyder, at dette kun er for ældre browsere, som Internet Explorer 8.
Dette er kun, hvis det matematiske indhold skal læses med øjnene, men kan ignoreres for dem, der skal læse indholdet med NVDA.

## Punktskrift {#Braille}

Hvis du ejer et punktdisplay, kan NVDA vise information på punkt.
Hvis dit punktdisplay har et punkttastatur, kan du også indtaste forkortet og uforkortet punkt.
En visuel gengivelse af punktskrift kan også vises på skærmen ved at benytte [punktskriftsviseren](#BrailleViewer). Denne funktion kan bruges alene eller sammenkoblet med et fysisk punktdisplay.

Se venligst afsnittet [Understøttede Punktdisplays](#SupportedBrailleDisplays) for oplysninger om understøttede punktdisplays.
Dette afsnit indeholder også yderligere oplysninger om NVDAs automatiske tilkobling af punktdisplays.
Du kan konfigurere punkt ved hjælp af [indstillingskategorien Punkt](#BrailleSettings) fra dialogen med [NVDAs indstillinger](#NVDASettings).

### Punktforkortelser for felttyper, felttilstande og landmærker {#BrailleAbbreviations}

For at få plads til så meget som muligt på et punktdisplay bruger NVDA følgende forkortelser til at indikere type og tilstand for felter såvel som landmærker.

| Forkortelse |felttype|
|---|---|
|app |applikation|
|art |artikel|
|bkt |blokcitat|
|knp |knap|
|drknp |drop down knap|
|dreknp |drejeknap|
|splknp |splitknap|
|seknp |skifteknap|
|bldt |billedtekst|
|cbo |combo box|
|chk |check box|
|dlg |dialog|
|dok |dokument|
|edt |redigerbart tekstfelt (editfelt)|
|adgedt |adgangskode edit|
|indl |indlejret objekt|
|snote |slutnote|
|fig |figure|
|fnote |fodnote|
|gra |grafik|
|grp |gruppering|
|hN |Overskrift niveau N, fx. h1, h2|
|hlp |hjælpeballon|
|lmk |landmærke|
|lnk |link|
|blnk |besøgt link|
|lst |list|
|mnu |menu|
|mnuln |menulinje|
|mnuknp |menuknap|
|mnupnkt |menupunkt|
|pnl |panel|
|bhln |behandlingslinje|
|opbhln |optaget behandlingslinje|
|rknp |radioknap|
|rulln |rullelinje|
|sekt |sektion|
|stln |statuslinje|
|fanktl |fanekontrolelement|
|tb |tabel|
|kN |Nummer på tabelkolonne fs. k1, k2|
|rN |Nummer på tabelrække, fx. r1, r2|
|term |terminal|
|vkln |værktøjslinje|
|vktip |værktøjstip|
|tv |trævisning|
|tvknp |trævisningsknap|
|tvemne |emne i trævisning|
|nv N |Et emne i en trævisning har niveau N|
|vnd |vindue|
|⠤⠤⠤⠤⠤ |separator|
|mrkt |markeret indhold|

Desuden er følgende indikatorer for tilstande defineret:

| Forkortelse |tilstand for felt|
|---|---|
|... |vises, når et objekt understøtter autofuldførelse|
|⢎⣿⡱ |vises, når et objekt (f.eks. en skifteknap) er trykket|
|⢎⣀⡱ |vises, når et objekt (f.eks. en skifteknap) ikke er trykket|
|⣏⣿⣹ |bliver vist, når et objekt, fx. en check box, er markeret|
|⣏⣸⣹ |bliver vist, når et objekt, fx. en check box, er delvist markeret|
|⣏⣀⣹ |bliver vist, når et objekt, f.eks. en check box, er markeret|
|- |Bliver vist, når et objekt, fx. en trævisning, kan foldes sammen|
|+ |Bliver vist, når et objekt, fx. en trævisning, kan foldes ud|
|*** |vises, når et beskyttet dokument eller en beskyttet kontrol fremkommer|
|klk |Bliver vist, når et objekt kan klikkes på|
|kmnt |vises, når der er en kommentar til et stykke tekst eller en celle i et regneark|
|frml |vises, når der er en formular på en celle i et regneark|
|ugyldig |vises, når en ugyldigt indtastning er opstået|
|lbesk |vises, når et objekt ( typisk en grafik) har en lang beskrivelse|
|mln |vises, når et tekstfelt tillader at indtaste flere linjer, såsom kommentarfelter på hjemmesider|
|pkr |vises, når et påkrævet formularfelt forekommer|
|sb |Bliver vist, når et objekt, fx. et editfelt, er skrivebeskyttet|
|vlg |Bliver vist, når et objekt er valgt|
|ivlg |Bliver vist, når et objekt er valgt|
|sorteret st |vises, når et objekt har stigende sortering|
|sorteret fa |vises, når et objekt har faldende sortering|
|umnu |Bliver vist, når et objekt har en pop-up-funktion, som regel en undermenu|

Til sidst defineres følgende forkortelser for landmærker:

| Forkortelse |Landmærke|
|---|---|
|bnnr |banner|
|iind |information om indhold|
|kmpl |komplementært|
|form |formular|
|hind |hovedindhold|
|navi |navigation|
|sæg |søg|
|omr |område|

### Indtastning med punkt {#BrailleInput}

NVDA understøtter indtastning ved brug af uforkortet og forkortet punktskrift ved hjælp af et punkttastatur.
Du kan vælge den ønskede indtastningstabel ved brug af indstillingen [Indtastningstabel](#BrailleSettingsInputTable) i indstillingskategorien punkt i [NVDAs indstillingsdialog](#NVDASettings).

Når uforkortet punktskrift benyttes, vil tekst indsættes så snart det skrives.
Når forkortet punkt benyttes, vil tekst indsættes når der trykkes på mellemrum eller enter efter et ord.
Bemærk, at oversættelsen kun reflektere det aktuelle ord du er ved at indtaste, men kan ikke bearbejde eksisterende tekst.
Hvis du f.eks. bruger en indtastningstabel der starter indtastning af numre ved brug af et taltegn, skal du indtaste et taltegn igen, hvis du har trykket backspace for at flytte til slutningen af et nummer, og såfrem du ønsker at indtaste yderligere numre.

<!-- KC:beginInclude -->
Et tryk på punkt 7 sletter sidst indtastede punktcelle eller tegn.
Punkt 8 oversætter alt indtastet punkt og trykker på enter-tasten.
Ved at trykke på punkt 7 og 8 sammen oversættes den indtastede punktskrift, men tilføjer ikke et mellemrum eller et tryk på enter-tasten.
<!-- KC:endInclude -->

#### Indtastning af tastaturgenveje {#BrailleKeyboardShortcuts}

NVDA understøtter indtastning af tastaturgenveje og emulering af forskellige tastaturkombinationer ved brug af dit punktdisplay.
Denne emulering findes i to varianter. Du kan enten tildele en tastekombination på dit punktdisplay til et tastaturtryk, eller benytte de virtuelle funktionstaster.

Almindeligt brugte taster, såsom piletasterne eller alt-tasten for at komme til menuen, kan blive direkte tildelt en tast på punktdisplayet.
Driveren for hvert punktdisplay har nogle af disse taster tildelt som standard.
Du kan ændre disse tastekombinationer eller tildele nye via [dialogen "Håndter Kommandoer"](#InputGestures).

Selvom dette er brugbart for ofte benyttede taster såsom tab, så anbefales det ikke, at du tildeler unikke tastetryk til hver genvej.
For at lade dig benytte tastekombinationer, hvor  taster holdes nede, har NVDA kommandoer, der lader dig holde tasterne Control, alt, skift, windows og NVDA-tasten nede, således at du kan benytte dem til at udføre en kommando fra punktdisplayet.
For at benytte denne funktion skal du først indtaste kommandoerne for den ønskede funktionstast. Du kan bruge mere end én på samme tid.
Derefter skal du indtaste bogstavet, der skal benyttes sammen med tasten.
Vil du eksempelvis trykke Control+F, skal du første indtaste kommandoen der holder Control-tasten nede på dit punktdisplay og derefter bogstavet f.
Det samme er tilfældet med f.eks. kommandoen Alt+skift+t. Her kan du indtaste tastekombinationerne, der holder henholdsvis alt og skift nede i en vilkårlig rækkefølge, eller benytte kommandoen, der holder disse taster nede samtidigt, og derefter indtaste et t.

Hvis du ved et uheld kommer til at holde en tast nede ved brug af dit punktdisplay, skal du blot indtaste kommandoen igen.

Når du skriver med forkortet punktskrift, vil brug af funktionstasterne fortsætte med at udføre punktoversættelse, når du indtaster punkterne 7 og 8.
Desuden, så vil funktionstasten du har indtastet via dit punktdisplay ikke tage højde for punktskrift, som du har indtastet tidligere.
Dette betyder at du f.eks. først skal holde alt-tasten nede og bagefter indtaste tallet 2, hvis du vil holde alt+2 nede og vil indtaste et taltegn, hvis du bruger en punkttabel, der bruger denne kombination.

## Syn {#Vision}

Trods NVDA primært er udviklet for at blinde og svagtseende kan bruge en computer med punkt og tale, så har NVDA nogle faciliteter der gør det muligt at ændre måden hvorpå indhold vises visuelt.
Disse kaldes i NVDA for synshjælpemidler.

NVDA tilbyder nogle indbyggede visuelle forbedringer, der beskrives nedenfor.
yderligere visuelle forbedringer kan leveres ved hjælp af [tilføjelsespakker](#AddonsManager).

Disse indstillinger kan ændres ved brug af [indstillingskategorien "Syn"](#VisionSettings) i [NVDAs indstillingspanel](#NVDASettings).

### Visuel Fremhævning {#VisionFocusHighlight}

Denne indstilling kan hjælpe dig med at finde [systemfokus](#SystemFocus), [navigatorobjektet](#ObjectNavigation) og [markøren i gennemsynstilstand](#BrowseMode).
Disse positioner er fremhævet ved hjælp af et farvet rektangulært omrids.

* Solid blå fremhæver positionen for navigatorobjekt og systemfokus ( f.eks. fordi [navigatorobjektet følger systemfokus](#ReviewCursorFollowFocus)).
* Blå med en streg igennem fremhæver systemfokus.
* Solid pink fremhæver navigatorobjektet.
* Solid gul fremhæver markøren for gennemsynstilstand (hvor der ikke befinder sig en fysisk markør som i web-browsere).

Når "Visuel Fremhævning" er aktiveret i [indstillingskategorien Syn](#VisionSettings) i [NVDAs indstillinger](#NVDASettings), kan du [bestemme om du vil fremhæve systemfokus, navigatorobjektet eller markøren brugt i gennemsynstilstand](#VisionSettingsFocusHighlight).

### Skærmtæppe {#VisionScreenCurtain}

Som en blind eller svagtseende bruger er det ofte ikke muligt eller nødvendigt at se indholdet på skærmen.
Derudover kan det være svært at sikre, at der ikke er nogen, der kigger dig over skulderen.
I denne situation indeholder NVDA en funktion kaldet "Skærmtæppe", der kan aktiveres for at gøre skærmen sort.

Du kan aktivere funktionen ved at gå til [indstillingskategorien "Syn"](#VisionSettings) i [NVDAs indstillinger](#NVDASettings).

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Skifter indstillingen for skærmtæppet |`NVDA+control+escape` |Hvis dette er aktiveret, er skærmen sort, og indhold vises ikke på skærmen. Hvis der trykkes én gang, vil denne funktion kun forblive aktiv, indtil du genstarter NVDA. Trykker du to gange, forbliver funktionen aktiv, indtil du slår den fra med ét tryk igen.|

<!-- KC:endInclude -->

Vær opmærksom på at du ikke kan udføre nogle handlinger, der tager udgangspunkt i noget visuelt på skærmen såsom at tage et skærmbillede eller benytte [Windows 10 tekstgenkendelse](#Win10Ocr), hvis denne funktion er aktiveret.

Pga. ændringer i Windows Magnification API, var det nødvendigt at opdatere skærmtæppefunktionen for at understøtte de nyeste versioner af Windows.
Benyt NVDA 2021.2 til at aktivere skærmtæppet med Windows 10 21H2 (10.0.19044) eller nyere.
Af sikkerhedsmæssige årsager kan det være en god idé at få bekræftet af en seende person, hvorvidt skærmtæppefunktionen er aktiv og gør skærmen fuldstændigt sort, når denne benyttes med nyere versioner af Windows.

Bemærk: Såfremt Windows forstørrelse er aktiv og inverterede farver er slået til, kan skærmtæppet ikke benyttes.

## Indholdsgenkendelse {#ContentRecognition}

Når forfattere ikke giver tilstrækkelig information til en skærmlæserbruger til at bestemme indholdet af noget, kan forskellige værktøjer bruges til at forsøge at genkende indholdet på et billede.
NVDA understøtter den optiske tegngenkendelse (OCR) -funktionalitet indbygget i Windows 10 og nyere til at genkende tekst fra billeder.
Yderligere indholdsgenkendelse kan leveres i tilføjelser til NVDA.

Når du bruger en kommando til genkendelse af indhold, genkender NVDA indhold fra det aktuelle [navigatorobjekt](#ObjectNavigation).
Som standard følger navigatorobjektet systemfokus eller markøren i gennemsynstilstand, så du kan som regel bare flytte fokusmarkøren eller markøren der benyttes i gennemsynstilstand, hvor du ønsker den.
Hvis du for eksempel flytter markøren der benyttes i gennemsynstilstand til en grafik, vil tekstgenkendelse udføres på grafikken som standard.
Du kan også benytte objektnavigation til for eksempel at genkende indholdet af et helt programvindue.

Når tekstgenkendelsen er udført, vil resultatet blive præsenteret i et dokument, der ligner gennemsynstilstand, så du kan læse oplysningerne med markørtaster osv.
Et tryk på Enter eller mellemrum vil aktivere (normalt klikke) teksten ved markøren, hvis det er muligt.
Et tryk på escape afviser genkendelsesresultatet.

### Windows Tekstgenkendelse {#Win10Ocr}

Windows 10 og nyere indeholder tekstgenkendelsesfunktionalitet til mange sprog.
NVDA kan bruge denne funktionalitet til at genkende tekst fra billeder eller utilgængelige applikationer.

Du kan indstille det sprog, der skal bruges til tekstgenkendelse ved brug af indstillingskategorien [Windows Tekstgenkendelse](#Win10OcrSettings) i [NVDAs indstillinger](#NVDASettings).
Yderligere sprog kan installeres ved at åbne startmenuen, vælge Indstillinger, vælge Tid og sprog, Område og sprog og derefter vælge Tilføj et sprog.

Når du ønsker at overvåge indhold, der regelmæssigt opdateres eller ændres løbende, for eksempel når du ser en video med undertekster, har du mulighed for at aktivere automatisk opdatering af det genkendte indhold.
Dette kan også gøres i [Windows Tekstgenkendelse-kategorien](#Win10OcrSettings) i [NVDA Indstillinger](#NVDASettings) dialogboksen.

Bemærk at Windows tekstgenkendelsen kan forekomme delvist eller fuldkommen inkompatibel med [synshjælpemidler i NVDA](#Vision) eller andre eksterne visuelle hjælpemidler. Disse skal deaktiveres, før du fortsætter.

<!-- KC:beginInclude -->
For at genkende teksten af det aktuelle navigatorobjekt ved hjælp af Windows Tekstgenkendelse, skal du trykke på NVDA + r.
<!-- KC:endInclude -->

## Programspecifikke NVDA-kommandoer {#ApplicationSpecificFeatures}

NVDA har sine egne ekstra kommandoer for nogle programmer. Dette er for at gøre nogle opgaver lettere, eller for at give adgang til funktionalitet som ellers ikke er tilgængelig for brugere af skærmlæsere.

### Microsoft Word {#MicrosoftWord}
#### Automatisk læsning af kolonne- og rækkeoverskrifter {#WordAutomaticColumnAndRowHeaderReading}

NVDA kan læse de passende overskrifter på rækker og kolonner automatisk, mens du bevæger dig rundt i tabeller i Microsoft Word.
Dette kræver, at indstillingen "Overskrifter" er indstillet til "Rækker og kolonner" i NVDAs dokumentformateringsindstillinger, fundet i indstillingskategorien dokumentformatering under [NVDAs indstillingsdialog](#NVDASettings).

Hvis du bruger [UIA for at få adgang til Word-dokumenter](#MSWordUIA), hvilket er standardadfærd i nylige versioner af Word og Windows, vil celerne i den første række automatisk blive indstillet som kolonneoverskriften. Det samme er tilfældet for den første kolonneoverskrift, der automatisk vil blive indstillet som rækkeoverskriften.

Bruger du derimod ikke [UIA til at få adgang til Word-dokumenter](#MSWordUIA), skal du selv indstille kolonne- og rækkeoverskrifterne.
Når du er placeret i den første celle i den række eller kolonne, som indeholder overskrifterne, kan du bruge følgende kommandoer:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Indstil kolonneoverskrifter |NVDA+Shift+c |Tryk en gang for at fortælle NVDA, at dette er den første overskriftscelle i rækken med kolonneoverskrifter, som skal læses automatisk, når du bevæger dig mellem kolonner i rækkerne nedenunder. Tryk to gange for at nulstille denne indstilling.|
|Indstil rækkeoverskrifter |NVDA+Shift+r |Tryk en gang for at fortælle NVDA, at dette er den første overskriftscelle i kolonnen med rækkeoverskrifter, som skal læses automatisk, når du bevæger dig mellem rækker til højre for denne kolonne. Tryk to gange for at nulstille denne indstilling.|

<!-- KC:endInclude -->
Disse indstillinger bliver gemt i dokumentet som bogmærker, der er kompatible med andre skærmlæsere såsom JAWS.
Dette betyder, at brugere af andre skærmlæsere, som senere åbner dette dokument, automatisk vil have fået indstillet overskrifterne på rækker og kolonner rigtigt.

#### Gennemsynstilstand i Microsoft Word {#BrowseModeInMicrosoftWord}

Ligesom på internettet kan gennemsynstilstand bruges i Microsoft word til at give adgang til funktioner som bogstavnavigation og elementlisten.
<!-- KC:beginInclude -->
For at slå gennemsynstilstand til eller fra i Microsoft Word skal du trykke NVDA+mellemrum.
<!-- KC:endInclude -->
For mere information om gennemsynstilstand og hurtignavigation se afsnittet om [Gennemsynstilstand](#BrowseMode).

##### Elementlisten {#WordElementsList}

<!-- KC:beginInclude -->
Mens du står i gennemsynstilstand i Microsoft Word, kan du komme til elementlisten ved at trykke NVDA+f7.
<!-- KC:endInclude -->
Elementlisten kan vise overskrifter, links og annotationer, som omfatter kommentarer og sporing af ændringer, såvel som fejl (på nuværende tidspunkt begrænset til stavefejl).

#### Annoncering af kommentarer {#WordReportingComments}

<!-- KC:beginInclude -->
To report any comments at the current caret position, press `NVDA+alt+c`.
Pressing twice shows the information in a browsable message.
<!-- KC:endInclude -->
Alle kommentarer i dokumentet vil, sammen med andre sporede ændringer, desuden blive vist i NVDAs elementliste, når du vælger annotationer som type.

### Microsoft Excel {#MicrosoftExcel}
#### Automatisk læsning af kolonne- og rækkeoverskrifter {#ExcelAutomaticColumnAndRowHeaderReading}

NVDA kan læse de rigtige overskrifter på rækker og kolonner automatisk, mens du bevæger dig rundt i Excel-regneark.
Dette kræver for det første, at "Oplæs kolonne- og rækkeoverskrifter" er slået til i NVDAs dokumentformateringsindstillinger, fundet i [NVDAs indstillingsdialog](#NVDASettings).
For det andet skal NVDA have at vide, hvilken række eller kolonne der indeholder overskrifterne.
Når du er placeret i den første celle i den række eller kolonne, som indeholder overskrifterne, kan du bruge følgende kommandoer:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Indstil kolonneoverskrifter |NVDA+Shift+c |Tryk en gang for at fortælle NVDA, at dette er den første overskriftscelle i rækken med kolonneoverskrifter, som skal læses automatisk, når du bevæger dig mellem kolonner i rækkerne nedenunder. Tryk to gange for at nulstille denne indstilling.|
|Indstil rækkeoverskrifter |NVDA+Shift+r |Tryk en gang for at fortælle NVDA, at dette er den første overskriftscelle i kolonnen med rækkeoverskrifter, som skal læses automatisk, når du bevæger dig mellem rækker til højre for denne kolonne. Tryk to gange for at nulstille denne indstilling.|

<!-- KC:endInclude -->
Disse indstillinger bliver gemt i projektmappen som definerede navneområder, og de er kompatible med andre skærmlæsere såsom JAWS.
Det betyder, at brugere af andre skærmlæsere, som senere åbner denne projektmappe, automatisk vil få overskrifter på kolonner og rækker indstillet.

#### Elementlisten {#ExcelElementsList}

Ligesom på internettet har NVDA en elementliste til Microsoft Excel, hvor du kan få vist og få adgang til flere forskellige typer af oplysninger.
<!-- KC:beginInclude -->
For at komme til elementlisten i Excel skal du trykke NVDA+f7.
<!-- KC:endInclude -->
De forskellige typer af oplysninger, du kan se i elementlisten, er følgende:

* Diagrammer: Viser alle diagrammer i det aktive regneark.
Hvis du vælger et diagram og trykker på Enter eller knappen "Flyt til", får du diagrammet i fokus, så du kan bevæge dig rundt i det og læse det med piletasterne.
* Kommentarer: Viser en liste over alle celler i REGNEARKET, som indeholder kommentarer.
For hver celle for du vist adressen og den tilhørende kommentar.
Hvis du trykker på Enter eller "Flyt til"-knappen på en kommentar i listen, går du direkte til cellen.
* Formler: Viser en liste med alle celler i REGNEARKET, som indeholder en formel.
For hver celle bliver vist celleadressen og formlen.
Hvis du trykker på Enter eller "Flyt til"-knappen på en formel i listen, kommer du direkte til cellen.
* Ark: Viser en liste over alle ark i projektmappen.
Du kan omdøbe et ark ved at trykke F2 på arket.
Tryk på Enter eller "Flyt til"-knappen på et ark for at skifte til arket.
* Formularfelter: Dette viser en liste over formularfelter i det aktuelle regneark.
Alternativ tekst vil blive vist for hvert formularfelt, samt celleadresserne formularfeltet omfatter.
Ved at vælge et formularfelt og derefter trykke på "Flyt til" knappen eller enter, vil fokus flyttes til formularfeltet i gennemsynstilstand.

#### Annoncering af noter {#ExcelReportingComments}

<!-- KC:beginInclude -->
To report any notes for the currently focused cell, press `NVDA+alt+c`.
Pressing twice shows the information in a browsable message.
I Microsoft 2016, 365 og nyere er "Kommentarer" omdøbt til "Noter".
<!-- KC:endInclude -->
Du kan også få vist alle noter i projektarket i elementlisten ved at trykke NVDA+F7.

NVDA kan også vise en bestemt dialog, der tillader dig at tilføje eller redigere en bestemt note.
NVDA overtager det oprindelige MS Excel-noteredigeringsområde på grund af tilgængelighedsbegrænsninger, men tastaturkommandoen for visning af dialogen er arvet fra MS Excel og fungerer derfor også uden at NVDA kører.
<!-- KC:beginInclude -->
For at tilføje eller redigere en note, tryk Shift+F2 på en celle med fokus.
<!-- KC:endInclude -->

Denne tastaturkommando vises ikke og kan ikke redigeres via dialogen for kommandoer.

Bemærk: Det er også muligt at åbne lignende redigeringsmuligheder for noter i et ark via kontekstmenuen.
Dette åbner dog de utilgængelige noteredigeringsværktøjer og ikke den specifik til NVDA.

En ny dialog for kommentarer er blevet tilføjet i Microsoft Office 2016, 365 og nyere.
Denne dialog er tilgængelig og indeholder flere funktioner, der lader dig besvare kommentarer osv.
Den kan også tilgås fra kontekstmenuen af en bestemt celle.
Kommentarerne tilføjet via denne dialog har intet at gøre med "Noter".

#### Læsning af beskyttede celler {#ExcelReadingProtectedCells}

Hvis en projektmappe er blevet skrivebeskyttet, kan det være, det ikke er muligt at flytte fokus til de celler, der er låst for redigering.
<!-- KC:beginInclude -->
For at kunne navigere til låste celler skal du skifte til gennemsynstilstand ved at trykke NVDA+Mellemrum og så bruge de almindelige kommandoer i Excel, f.eks. piletasterne, til at bevæge dig rundt i alle cellerne i regnearket.
<!-- KC:endInclude -->

#### Formularfelter {#ExcelFormFields}

Excel regneark kan indeholde formularfelter.
Du kan få adgang til disse ved brug af elementlisten eller F og Shift+F bogstavnavigation for formularfelter.
Når du flytter til et formularfelt i gennemsynstilstand, kan du benytte enter eller mellemrum til at aktivere eller skifte til fokustilstand, så du kan interagere med feltet, afhængigt af kontrollen.
For yderligere informationer om gennemsynstilstand samt bogstavnavigation, se [Gennemsynstilstand](#BrowseMode).

### Microsoft PowerPoint {#MicrosoftPowerPoint}

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Slå oplæsning af talenoter til/fra |Ctrl+Shift+s |Når du kører et dias-show, vil denne kommando skifte mellem talenoterne til diasset og diassets indhold. Dette påvirker kun, hvad NVDA læser op, ikke hvad der bliver vist på skærmen.|

<!-- KC:endInclude -->

### foobar2000 {#Foobar2000}

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Rapportér resterende tid |Ctrl+Shift+r |Rapporterer den resterende tid af det igangværende spor, hvis tilgængelig.|
|Rapportér forløbne tid |Ctrl+shift+e |Rapporterer den forløbne tid for det igangværende spor, hvis tilgængelig.|
|Rapportér længden af det aktuelle spor |Ctrl+shift+t |Rapporterer længden for det igangværende spor, hvis tilgængelig.|

<!-- KC:endInclude -->

Bemærk: Ovenstående genveje virker kun, når statuslinjen i Foobar er formateret som standard.

### Miranda IM {#MirandaIM}

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Læs seneste beskeder |NVDA+Ctrl+1-4 |Læser en af de seneste beskeder afhængig af nummeret. Fx.: 2 læser den næstseneste besked.|

<!-- KC:endInclude -->

### Poedit {#Poedit}

NVDA offers enhanced support for Poedit 3.5 or newer.

<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Læs oversætternoter |`Ctrl+Shift+a` |Læser oversætternoter. Hvis der trykkes to gange, vises noterne i gennemsynstilstand|
|Læs kommentarvindue |`Ctrl+Shift+c` |Læser en kommentar i kommentarvinduet. Hvis der trykkes to gange, vises teksten i gennemsynstilstand|
|Læs gammel kildetekst |`control+shift+o` |Oplæser den gamle kildetekst, hvis den findes. Hvis der trykkes to gange, vises teksten i gennemsynstilstand|
|Oplæs oversættelsesadvarsel |`control+shift+w` |Oplæser oversættelsesadvarsel, hvis den findes. Hvis der trykkes to gange, vises advarslen i gennemsynstilstand|

<!-- KC:endInclude -->

### Kindle for PC {#Kindle}

NVDA understøtter navigering og læsning i Amazon Kindle for PC.
Denne funktionalitet er kun tilgængelig i Kindle bøger,hvor der står "Screen Reader: Supported." Du kan undersøge dette på detaljesiden for bogen.

Gennemsynstilstand benyttes til at læse bøger.
Dette slås til automatisk, eller når du fokusere på bogens område.
Siderne vendes automatisk efter behov, eller når kommandoen "Sig Alt" benyttes.
<!-- KC:beginInclude -->
Du kan manuelt gå til den næste side med tasten side ned, og gå til forrige side ved hjælp af tasten side op.
<!-- KC:endInclude -->

Bogstavnavigation er understøttet for links og grafik, men kun indenfor den aktuelle side.
Navigering ved hjælp af links vil også inkludere fodnoter.

NVDA understøtter læsning af matematisk indhold i Kindle-bøger der benytter Accessible Math.
Se venligst afsnittet [Læsning af matematisk materiale](#ReadingMath) for yderligere oplysninger.

#### Valg af tekst {#KindleTextSelection}

Kindle lader dig udføre diverse funktioner på udvalgt tekst, såsom at slå ord op i en ordbog, tilføje noter og fremhævelser, kopiere tekst til udklipsholderen og søge på nettet.
For at gøre dette, skal du først vælge tekst som du normalt ville gøre det i gennemsynstilstand f.eks. ved at bruge shift og piletasterne.
<!-- KC:beginInclude -->
Når du har valgt tekst, skal du trykke på applikationstasten eller Shift+F10 for at vise de tilgængelige muligheder og arbejde med den udvalgte tekst.
<!-- KC:endInclude -->
Hvis du gør dette uden at vælge tekst, vil tilgængelige muligheder vises for det aktuelle ord under markøren.

#### Brugernoter {#KindleUserNotes}

Du kan tilføje en note angående et ord eller en tekstpassage.
For at gøre dette, skal du først vælge den ønskede tekst og bruge menuen som beskrevet ovenfor.
Derefter, vælg "Add Note".

Når der læses i gennemsynstilstand, vil NVDA henvise til disse noter som kommentarer.

For at vise, redigere eller slette en note:

1. Flyt markøren til teksten, der indeholder noten.
1. Vis menuen til behandlingen af udvalgt tekst, som beskrevet ovenfor.
1. Vælg "Edit Note".

### Azardi {#Azardi}

<!-- KC:beginInclude -->
Når du befinder dig i tabelvisningen for tilføjede bøger:

| Navn |Tast |Beskrivelse|
|---|---|---|
|Enter |enter |Åbner den valgte bog.|
|Kontekstmenu |applikationer |Åbner kontekstmenuen for den valgte bog.|

<!-- KC:endInclude -->

### Windows-konsollen {#WinConsole}

NVDA har understøttelse for Windows-kommandokonsollen brugt af Kommandoprompt, PowerShell, og Windows Subsystem for Linux.
Kommandokonsollens vindue har en forudbestemt størrelse, der typisk er meget mindre end den beholder, der indeholder den tekst, der kommer frem på skærmen.
Efterhånden som nyere linjer af tekst skrives, vil teksten rulle opad og forrige linjer af tekst vil ikke forblive synlige.
Tekst, der ikke er synlig, kan ikke læses ved brug af NVDAs læsekommandoer, hvis du bruger en Windows version ældre end Windows 11 22H2.
Derfor er det nødvendigt at bruge kommandoer til at rulle konsolvinduet.
I Windows-konsollen og terminaler er det nu muligt at læse alt tekst uden at rulle konsolvinduet.
<!-- KC:beginInclude -->
Følgende indbyggede kommandoer til manipulering af konsolvinduet kan være nyttige, når du skal [læse teksten](#ReviewingText) med NVDA i ældre versioner af Windows-konsollen:

| Navn |Tast |Beskrivelse|
|---|---|---|
|Rul op |control+Pil op |Ruller konsolvinduet opad, så tidligere tekst kan læses.|
|Rul ned |control+Pil ned |Ruller konsolvinduet nedad, så nyere tekst kan læses.|
|Rul til begyndelsen |control+hjem |Ruller konsolvinduet til begyndelsen af teksten.|
|Rul til den sidste tekst |control+end |Ruller konsolvinduet til den sidst modtagede tekst.|

<!-- KC:endInclude -->

## Opsætning af NVDA {#ConfiguringNVDA}

De fleste indstillinger i NVDA kan nås fra dialogbokse, som åbnes via undermenuerne Opsætning>Indstillinger i NVDA-menuen.
Mange af disse indstillinger kan findes ved brug af kategorierne i [NVDAs indstillingsdialog](#NVDASettings).
I alle NVDAs indstillingsdialoger skal du trykke på knappen OK for at godkende de ændringer, du har foretaget.
Tryk på Annuller-knappen eller Escape-tasten for at annullere dine ændringer.
For bestemte dialoger kan du trykke på knappen "Anvend" for at anvende dine ændringer med det samme.
I de fleste NVDA-dialoger, kan du nemt finde hjælp for den pågældende indstilling.
<!-- KC:beginInclude -->
Når du befinder dig i en dialog, vil et tryk på `f1` åbne brugervejledningen til det relevante kapitel, der omfatter den aktuelle indstilling eller dialog.
<!-- KC:endInclude -->
Nogle indstillinger kan ligeledes ændres ved hjælp af genvejstaster, der anføres i de enkelte afsnit nedenfor, hvor det er relevant.

### NVDA-indstillinger {#NVDASettings}

<!-- KC:settingsSection: || Navn | Desktop tast | Laptop tast | Beskrivelse | -->
NVDAs indstillingsdialog tilbyder en bred vifte af indstillinger, der kan ændres efter behov.
For at gøre det lettere at finde de indstillinger, du ønsker at ændre, viser dialogen en liste over konfigurationskategorier, som du kan vælge imellem.
Når du vælger en kategori, vises alle de tilhørende indstillinger i dialogen.
Du kan navigere mellem kategorier ved at bruge `tab` eller `shift+tab` for at komme til kategorilisten, og derefter bruge op- og nedpilene til at bevæge dig rundt i listen.
Du kan også skifte til næste kategori fra hvilket som helst sted i dialogen ved at trykke på `ctrl+tab`, eller gå tilbage til forrige kategori ved at trykke på `shift+ctrl+tab`.

Når du har foretaget ændringer i én eller flere indstillinger, kan du anvende ændringerne ved at klikke på "Anvend"-knappen. I så fald forbliver dialogen åben, så du kan ændre flere indstillinger eller vælge en anden kategori.
Hvis du vil gemme dine indstillinger og lukke dialogen, skal du bruge knappen "OK".

Nogle indstillingskategorier har en tildelt tastaturkommando.
Hvis kommandoen udføres, vil indstillingsdialogen åbnes og vise den pågældende indstillingskategori.
Det er ikke alle kategorier, der kan tilgås vha. tastaturkommandoer.
Hvis du gerne vil have let adgang til indstillingskategorier, som ikke har tilknyttet en genvejstast, kan du bruge [dialogen til håndtering af kommandoer](#InputGestures) til at tilføje en bestemt bevægelse eller et tastetryk til dialogen.

De tilgængelige indstillingskategorier i NVDAs indstillingsdialog vil blive beskrevet nedenfor.

#### Generelt {#GeneralSettings}

<!-- KC:setting -->

##### Åbn generelle indstillinger {#OpenGeneralSettings}

Tast: `NVDA+control+g`

Denne kategori indstiller NVDAs generelle adfærd, herunder sproget der skal anvendes og om NVDA automatisk skal søge efter opdateringer.
Denne kategori indeholder følgende indstillingsmuligheder:

##### Sprog {#GeneralSettingsLanguage}

Det er en combo box, hvor sproget på NVDAs brugerflade og meddelelser kan indstilles.
Der er mange sprog. Som standard sættes sproget imidlertid til Windows standardsprog.
Denne valgmulighed giver NVDA besked på at benytte det sprog, som Windows aktuelt er sat til at bruge.

Bemærk, at NVDA skal genstartes efter ændring af sproget.
Når dialogen til at bekræfte ændring til et andet sprog vises, skal du tage stilling til om du vil genstarte nu eller senere. Vælger du at genstarte senere, skal konfigurationen gemmes manuelt eller ved brug af den tilsvarende indstilling, der gemmer din konfiguration ved afslutning af NVDA.

##### Gem konfiguration ved afslutning {#GeneralSettingsSaveConfig}

Denne indstilling er en check box, der får NVDA til automatisk at gemme den aktuelle konfiguration ved afslutning, når den er slået til.

##### Vis muligheder ved afslutning af NVDA {#GeneralSettingsShowExitOptions}

Denne indstillingsmulighed er en check box, der giver mulighed for at vælge, hvorvidt en dialog skal fremkomme ved afslutning af NVDA med spørgsmålet om hvilken handling, du vil foretage dig.
Når den er slået til, fremkommer en dialog, når du forsøger at afslutte NVDA, hvor du skal tage stilling til, hvorvidt du ønsker at afslutte, genstarte, genstarte med tilføjelsesprogrammer deaktiverede eller installere ventende opdateringer (hvis relevant).
Når den er slået fra, bliver NVDA afsluttet med det samme.

##### Afspil lyd ved start og afslutning af NVDA {#GeneralSettingsPlaySounds}

Dette er en check box, der, når den er slået til, får NVDA til at afspille en lyd ved opstart og afslutning af programmet.

##### Logningsniveau {#GeneralSettingsLogLevel}

Dette er en combo box, hvor du kan bestemme, hvor meget NVDA skal logge under afvikling.
Generelt bør det ikke være nødvendigt for brugeren at ændre denne indstilling, idet der ikke logges for meget.
Det kan imidlertid være en nyttig funktion, hvis du ønsker at give tilbagemelding i forbindelse med fejlfinding til en fejlrapport.

De tilgængelige logningsmuligheder er:

* Deaktiveret: Udover en kort besked ved opstart, vil NVDA ikke benytte logning under kørsel-
* Info: NVDA vil logge grundlæggende informationer under opstart og andre nyttige informationer for udviklere.
* Fejlfinding og advarsler: Advarsler der ikke forårsages af alvorlige fejl vil logges.
* Input/output: Denne indstilling logger både input og output fra punktdisplays, tastaturenheder samt tale.
Hvis du bekymre dig om dit privatliv, benyt ikke denne valgmulighed.
* Fejlfinding: Udover diverse informationer, input/output, og beskeder om advarsler, vil yderligere fejlbeskeder logges ved brug af denne indstilling.
Hvis du ligeledes bekymre dig om dit privatliv, skal du ikke aktivere denne indstilling, da alt vil blive logget.

##### Start NVDA automatisk, når jeg har logget på Windows {#GeneralSettingsStartAfterLogOn}

Hvis denne funktion er slået til, vil NVDA starte, så snart du er logget på Windows.
Denne funktion er kun tilgængelig i en installeret kopi af NVDA.

##### Brug NVDA på Windows Logon-skærmen (kræver administratorrettigheder) {#GeneralSettingsStartOnLogOnScreen}

Hvis du skal angive brugernavn og adgangskode for at logge på Windows, kan denne funktion slås til, og NVDA startes automatisk op på logon-skærmen når Windows starter.
Denne funktion er kun tilgængelig i en installeret kopi af NVDA.

##### Benyt de aktuelt gemte indstillinger på logon-skærmen og andre beskyttede skærmbilleder (kræver administratorrettigheder) {#GeneralSettingsCopySettings}

Aktivering af denne knap kopierer dine aktuelt gemte brugerindstillinger i NVDA til NVDAs systemkonfigurationsmappe, så NVDA vil bruge dem, når du befinder dig på logon, brugerkontokontrol (UAC) og [andre beskyttede skærmbilleder](#SecureScreens).
For at være sikker på at alle dine indstillinger bliver kopieret, skal du først gemme dine indstillinger med Ctrl+NVDA+c eller gem konfiguration in NVDA-menuen.
Denne funktion er kun tilgængelig i en installeret kopi af NVDA.

##### Søg automatisk efter opdateringer af NVDA {#GeneralSettingsCheckForUpdates}

Hvis denne indstilling er aktiveret, vil NVDA automatisk søge efter opdateringer og informere dig, når en opdatering er tilgængelig.
Du kan også manuelt søge efter opdateringer ved at vælge Søg efter opdateringer under Hjælp i NVDA-menuen.
Når der manuelt eller automatisk søges efter opdateringer, vil det være nødvendigt at sende nogle informationer til opdateringsserveren for at sikre, at du modtager den rette opdatering til dit system.
Følgende informationer bliver altid sendt:

* Aktuelle version af NvDA
* Version af dit operativsystem
* Om dit system er 64- eller 32 bit.

##### Tillad, at NV Access indsamler brugsdata om NVDA {#GeneralSettingsGatherUsageStats}

Hvis dette er aktiveret, bruger NV Access oplysningerne indsendt under søgning af opdateringer til at spore antallet af NVDA-brugere, herunder bestemte demografiske forhold som operativsystem og oprindelsesland.
Bemærk, at selvom din IP-adresse vil blive brugt til at beregne dit land under opdateringskontrollen, bliver IP-adressen aldrig gemt.
Bortset fra de obligatoriske oplysninger, der kræves for at kontrollere efter opdateringer, er følgende yderligere oplysninger også sendt i øjeblikket:

* Et unikt ID-nummer for brugeren af NVDA. Dette ændres hver måned.
* NVDAs aktuelle sprog
* Om denne kopi af NVDA er flytbar eller installeret
* Navn på den aktuelle talesyntese i brug (herunder navnet på tilføjelsesprogrammet, som driveren tilhører)
* Navn på det aktuelle punktdisplay i brug (herunder navnet på tilføjelsen, som driveren tilhører)
* Den aktuelle oversættelsestabel (hvis punkt er i brug)

Disse informationer hjælper i høj grad NV Access med at prioritere fremtidig udvikling af NVDA.

##### Meddel om ventende opdateringer, når NVDA startes {#GeneralSettingsNotifyPendingUpdates}

Hvis denne indstilling er slået til, vil NVDA lade dig installere ventende opdateringer, når NVDA starter, hvis en opdatering venter på installation.
Du kan også manuelt installere de ventende opdateringer fra dialogen "Afslut NVDA", eller ved at søge efter opdateringer fra menupunktet "Hjælp" i NVDA-menuen.

#### Taleindstillinger {#SpeechSettings}

<!-- KC:setting -->

##### Åbn taleindstillinger {#OpenSpeechSettings}

Tast: `NVDA+control+v`

Indstillingskategorien  Tale, som findes i dialogen Indstillinger, rumer valgmuligheder til ændring af talesyntese, samt hvordan talen lyder.
Du kan finde en alternativ, hurtigere måde til styring af taleparametre fra et hvilket som helst sted i afsnittet [Ringen af talesynteseindstillinger](#SynthSettingsRing).

Talekategorien indeholder følgende valgmuligheder:

##### Skift talesyntese {#SpeechSettingsChange}

Den første mulighed er knappen "Skift...". Denne knap åbner dialogboksen [Vælg talesyntese](#SelectSynthesizer), der lader dig vælge den aktuelle talesyntese og output-enhed.
Denne dialog åbnes oveni dialogen med NVDAs indstillinger.
Ved at gemme eller kassere dine ændringer, vil du få fokus i NVDAs indstillingsdialog.

##### Stemme {#SpeechSettingsVoice}

Denne valgmulighed er en combo box med en liste over alle stemmerne tilhørende den aktuelt valgte talesyntese.
Med piletasterne kan du lytte til de enkelte stemmemuligheder.
Venstre-pil og Pil-op fører dig opad i listen, mens Højre-pil og Pil-ned flytter nedad i listen.

##### Variant {#SpeechSettingsVariant}

Hvis du bruger talesyntesen ESpeak NG, som følger med NVDA, indeholder denne combo box en liste hvorfra du kan vælge den variant, som talesyntesen skal tale med.
eSpeak NGs Varianter minder om forskellige stemmer, idet de får ESpeak NG-stemmen til at tale på lidt forskellige måder.
Nogle varianter lyder som en mand, nogle som en kvinde, andre lyder endda som en frø.
Du kan også ændre denne indstilling, hvis du bruger en talesyntese fra en tredjepart og den understøtter dette.

##### Hastighed {#SpeechSettingsRate}

Med denne indstilling kan du ændre hastigheden for den aktuelle stemme.
Det er en skyderkontrol, der går fra 0 til 100, (med 0 som det langsommeste, 100 som det hurtigste).

##### Højere hastighed {#SpeechSettingsRateBoost}

Denne indstilling vil markant forøge talehastigheden, hvis denne funktion understøttes af din aktuelle talesyntese.

##### Toneleje {#SpeechSettingsPitch}

Med denne indstilling kan du ændre tonelejet for den aktuelle stemme.
Det er en skyderkontrol, der går fra 0 til 100, (med 0 som det laveste toneleje og 100 som den højeste).

##### lydstyrke {#SpeechSettingsVolume}

Det er en skyderkontrol, der går fra 0 til 100, (med 0 som den laveste lydstyrke og 100 som den højeste).

##### Udsving {#SpeechSettingsInflection}

Denne indstilling er en skyder, som giver mulighed for at bestemme, hvor stort udsving (stigning og fald i tonehøjde) den pågældende talesyntese skal bruge under oplæsning. (Den eneste talesyntese, der p.t. understøtter denne funktion, er eSpeak NG).

##### Automatisk skift af sprog {#SpeechSettingsLanguageSwitching}

Med denne check box kan du vælge, om NVDA skal skifte sprog for talesyntesen automatisk, hvis den tekst, der bliver læst op, rummer information om sproget.
Denne indstilling er slået til som standard.

##### Automatisk skift af dialekt {#SpeechSettingsDialectSwitching}

Med denne check box kan du vælge, om NVDA også skal skifte dialekt automatisk i stedet for bare at skifte sprog.
Hvis du fx. læser med den amerikanske stemme, men et dokument er specificeret til at være på britisk engelsk, vil talesyntesen skifte dialekt, hvis denne indstilling er slået til.
Denne indstilling er slået fra som standard.

<!-- KC:setting -->

##### Niveau for sætningstegn og symboler {#SpeechSettingsSymbolLevel}

Tast: NVDA+p

Her kan du vælge, hvor mange sætningstegn og andre symboler, der skal udtales som ord.
Hvis du f.eks. sætter niveauet til "alt", vil alle symboler blive udtalt.
Denne indstilling gælder for alle talesynteser og ikke kun den, der er aktiv i øjeblikket.

##### Brug stemmens aktuelle sprog til behandling af specialtegn og symboler {#SpeechSettingsTrust}

Med den indstilling, som er slået til som standard, kan du vælge om du vil benytte sproget for den aktuelle stemme til udtale af tegn og symboler.
Hvis du opdager, at NVDA læser tegn og symboler på et forkert sprog med en bestemt talesyntese eller stemme, kan du slå denne indstilling fra for at tvinge NVDA til at benytte sin globale sprogindstilling.

##### Unicode-normalisering {#SpeechUnicodeNormalization}
| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Deaktiveret), Aktiveret, Deaktiveret|
|Standard |Deaktiveret|

Når denne indstilling er aktiveret, udføres unicode-normalisering på den tekst, der siges af NVDA.
Dette er gavnligt, når der siges tegn, der kan repræsenteres i flere former.
NVDA bruger NFKC (Normalization Form Compatibility Composition) algoritmen, som giver følgende fordele blandt andre:

1. De fede og kursiverede versioner af tegn, der er en del af unicode-standarden og almindeligt anvendes på sociale medier, normaliseres til deres mest almindelige kompatible ækvivalent.
For eksempel kan det latinske bogstav "h" også præsenteres som "𝐡" (fed), "ℎ" (kursiv) osv., men vil altid blive talt som "h", når normalisering er aktiveret.
Dette aspekt af normalisering hjælper også med at læse ligninger i Microsoft Word ligningseditor.

1. Normalisering til sammensatte tegn.
For eksempel kan tegnet "ü" (u med trema), et almindeligt tegn i sprog som tysk og tyrkisk, repræsenteres i to former:
  1. Et enkeltstående unicode-tegn (ü)
  1. En dekomponering i to tegn (ü), nemlig det normale latinske bogstav u og en trema-modifikator
  Unicode-normalisering sikrer, at kun én form vil blive brugt i hele taleoutputtet, hvilket er den ene tegn-variant.

1. Dekomponering af nogle ligaturer, herunder "ĳ" (ligatur ij) til deres to bogstav-form ("ij").

1. Stabil rækkefølge af modifikatorer i sammensatte tegn, for eksempel på oldhebraisk.

For at aktivere eller deaktivere unicode-normalisering fra ethvert sted, bedes du tildele en brugerdefineret kommando ved hjælp af [Dialogen Håndter Kommandoer](#InputGestures).

##### Rapportér "Normaliseret" ved navigation efter tegn {#SpeechReportNormalizedForCharacterNavigation}

Dette er en check box, der, når den er markeret, får NVDA til at oplyse, at et tegn er normaliseret, når det udtales som et enkelt tegn, f.eks. under stavning.
Når denne indstilling er aktiveret, vil stavning af tegnet 'ĳ' for eksempel få det udtalt som 'i j normaliseret'.

Bemærk, at denne indstilling kun er tilgængelig, når "[Unicode normalisering](#SpeechUnicodeNormalization)" er aktiveret.

##### Benyt Unicode Consortium data (herunder emoji) under behandling af tegn og symboler {#SpeechSettingsCLDR}

Når denne check box er valgt, vil NVDA benytte yderligere udtaleordbøger til udtale af symboler og tegn.
Disse ordbøger indeholder symboler (særligt emoji) der er angivet af [Unicode Consortium](https://www.unicode.org/consortium/) som en del af deres [Common Locale Data Repository](http://cldr.unicode.org/).
Hvis du ønsker, at NVDA skal udtale beskrivelser af emoji ved brug af denne data, skal indstillingen være slået til.
Hvis du derimod bruger en talesyntese, der har denne funktionalitet indbygget, vil det evt. være nødvendigt at slå denne funktion fra.

Bemærk: Manuelt tilføjede og redigerede tegnbeskrivelser gemmes som en del af din brugerkonfiguration.
Dette betyder, at dine tilpassede udtaler for emoji vil blive udtalt, uanset om denne indstilling er slået til eller ej.
Du kan tilføje, redigere og fjerne symbolbeskrivelser i NVDAs [ dialog Udtale af Sætningstegn og Symboler](#SymbolPronunciation).

For at ændre denne indstilling fra hvor som helst, kan du tildele en kommando i [dialogen Håndter Komandoer](#InputGestures).

##### Ændring af tonehøjde ved store bogstaver {#SpeechSettingsCapPitchChange}

I dette editfelt kan du indtaste et tal for, hvor meget tonehøjden skal ændre sig, når NVDA udtaler et stort bogstav.
Denne værdi er en procentsats. En negativ værdi vil gøre tonehøjden lavere, og en positiv værdi vil gøre den højere.
Hvis du ikke ønsker nogen ændring af tonehøjden, skal du indtaste 0.
Normalt vil NVDA hæve tonelejet, hver gang du får store bogstaver oplæst, men nogle talesynteser understøtter ikke denne funktion.
Hvis dette ikke understøttes af din aktuelle talesyntese, bør du overveje at bruge indstillingen ["Sig stort før store bogstaver"](#SpeechSettingsSayCapBefore) og/eller [Bip ved store bogstaver](#SpeechSettingsBeepForCaps).

##### Sig "Stort" før store bogstaver {#SpeechSettingsSayCapBefore}

Denne indstilling er en check box. Når den er markeret, oplæser NVDA ordet "stort" før hvert stort bogstav, når markøren flyttes hen over bogstavet med piletasterne, eller under skrivning.

##### Bip ved stort bogstav {#SpeechSettingsBeepForCaps}

Hvis denne check box er markeret, bipper NVDA hver gang der forekommer et stort bogstav.

##### Brug stavefunktion hvis understøttet {#SpeechSettingsUseSpelling}

Nogle ord består af kun et bogstav, men udtalen kan være anderledes, afhængigt af om ordet er udtalt som et individuelt bogstav (som når du staver) eller som et helt ord.
For eksempel, på engelsk er "a" både et bogstav og et ord, og det skal udtales forskelligt alt efter sammenhængen.
Denne indstilling giver talesyntesen mulighed for at skelne mellem disse to tilfæld.
De fleste synteser understøtter denne funktion.

Denne indstilling bør generelt være slået til.
Nogle Microsoft Speech API synteser anvender dog ikke denne funktion korrekt og opfører sig mærkeligt når indstillingen er slået til.
Talesynteser fra Code Factory implementerer heller ikke dette korrekt. Dette gælder både for NVDA-tilføjelsen og SAPI-syntesen. Dette vil også forårsage unødvendig stavning af tekst i f.eks. menuer og dialoger.
Hvis du har problemer med udtalen af diverse bogstaver kan du prøve at deaktivere denne indstilling.

##### Forsinkede beskrivelser af tegn ved markørbevægelser {#delayedCharacterDescriptions}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Aktiveret, deaktiveret|
|Standard |Deaktiveret|

Når denne indstilling er aktiveret, vil NVDA sige tegnbeskrivelsen, når du flytter markøren tegn for tegn.

For eksempel, mens du gennemgår en linje med tegn, når bogstavet "b" læses, vil NVDA sige "Bravo" efter ét sekund.
Dette kan være nyttigt, hvis det er svært at skelne mellem udtale af symboler, eller for hørehæmmede brugere.

Tegnets beskrivelse vil ikke blive oplæst, hvis andet tekst udtales, eller hvis du trykker på `Ctrl-tasten`.

##### Taletilstande {#SpeechModesDisabling}

Denne liste af muligheder lader dig bestemme, hvilke [taletilstande](#SpeechModes), der er tilgængelige, når du bruger kommandoen `NVDA+s` til at skifte mellem dem.
Tilstande, der ikke er markerede, vil ikke fremkomme.
Som standard er alle tilstande inkluderede.

Har du f.eks. ikke brug for at benytte "bip" og "fra", skal du fjerne markeringen ved dem og lade "tale" og "efter behhov" være markerede.
Bemærk, at du skal vælge mindst to tilstande.

#### Vælg talesyntese {#SelectSynthesizer}

<!-- KC:setting -->

##### Åbn dialogen for valg af talesyntese {#OpenSelectSynthesizer}

Tast: `NVDA+control+s`

Talesyntesedialogen, som findes ved at trykke på knappen "Skift..." i indstillingskategorien "Tale", lader dig vælge hvilken talesyntese NVDA skal bruge.
Så snart du har valgt en talesyntese med piletasterne, kan du trykke Ok og NVDA vil benytte den valgte talesyntese.
Hvis NVDA ikke kan anvende den talesyntese du har valgt, vil NVDA give dig en fejlmeddelelse, og fortsætte med at bruge den tidligere anvendte talesyntese.

##### Talesyntese {#SelectSynthesizerSynthesizer}

Her har du mulighed for at bestemme, hvilken talesyntese NVDA skal benytte til taleoutput.

For en liste over de talesynteser, som NVDA understøtter, se venligst afsnittet [Understøttede Talesynteser](#SupportedSpeechSynths).

Der er en særlig indstilling, som altid vil være at finde i denne liste, nemlig "Ingen tale". Den gør det muligt at benytte NVDA uden nogen som helst form for taleoutput.
Dette kan være nyttigt for dem, der ønsker at bruge NVDA udelukkende med punktskrift eller for seende udviklere, der kun ønsker at bruge Talevisning.

#### Ringen af talesynteseindstillinger {#SynthSettingsRing}

Hvis du ønsker hurtigt at ændre taleindstillingerne uden først at skulle åbne dialogboksen med stemmeindstillinger, findes der en række NVDA-kommandoer, der giver mulighed for at flytte mellem de mest almindelige indstillinger for talesyntesen fra et hvilket som helst sted, hvis blot NVDA kører:
<!-- KC:beginInclude -->

| Navn |Desktop tast |Laptop tast |Beskrivelse|
|---|---|---|---|
|Flyt til næste talesynteseindstilling |NVDA+Ctrl+Højre-pil |NVDA+Shift+Ctrl+Højre-pil |Flytter til den næste tilgængelige talesynteseindstilling efter den aktuelle og folder rundt til den første indstilling, når du er nået til den sidste|
|Flyt til forrige talesynteseindstilling |NVDA+Ctrl+Venstre-pil |NVDA+Shift+Ctrl+Venstre-pil |Flytter til den forrige tilgængelige talesynteseindstilling før den aktuelle og folder rundt til den sidste indstilling, når du er nået til den første|
|Forøg den aktuelle taleindstilling |NVDA+Ctrl+Pil-op |NVDA+Shift+Ctrl+Pil-op |Forøger den synteseindstilling, du i øjeblikket er ved at ændre, fx. forøger hastigheden, vælger den næste stemme, forøger lydstyrken|
|Forøg den aktuelle indstilling med en større værdi |`NVDA+Ctrl+sideOp` |`NVDA+shift+Ctrl+sideOp` |Forøger den indstilling, du er på i øjeblikket, med en større værdi. Hvis du befinder dig på stemmeindstillingen, vil den springe 20 stemmer fremad, og ved brug af indstillinger som toneleje og hastighed, vil der springes fremad med 20%|
|Formindsk den aktuelle taleindstilling |NVDA+Ctrl+Pil-ned |NVDA+Shift+Ctrl+Pil-ned |Formindsker den synteseindstilling, som du i øjeblikket er ved at ændre fx formindsker hastigheden, vælger den forrige stemme, formindsker lydstyrken|
|Formindsk den aktuelle indstilling med en større værdi |`NVDA+Ctrl+sideNed` |`NVDA+shift+Ctrl+sideNed` |Forøger den indstilling, du er på i øjeblikket, med en større værdi. Hvis du befinder dig på stemmeindstillingen, vil den springe 20 stemmer fremad, og ved brug af indstillinger som toneleje og hastighed, vil der springes fremad med 20%|

<!-- KC:endInclude -->

#### Punktindstillinger {#BrailleSettings}

Indstillingskategorien "Punkt" i NVDAs indstillingsdialog lader dig vælge, hvordan NVDA skal håndtere forskellige aspekter af punktskrift.
Denne kategori indeholder følgende indstillinger:

##### Skift punktdisplay {#BrailleSettingsChange}

Den første mulighed er knappen "Skift...". Denne knap åbner dialogboksen [Vælg punktdisplay](#SelectBrailleDisplay), der lader dig vælge det aktuelle punktdisplay.
Denne dialog åbnes oven på dialogen med NVDAs indstillinger.
Ved at gemme eller kassere dine ændringer, vil du få fokus i NVDAs indstillingsdialog.

##### Oversættelsestabel {#BrailleSettingsOutputTable}

Den næste indstilling, du kommer til i denne kategori, er combo boxen oversættelsestabel.
I denne combo box finder du punkttabeller for en lang række sprog, punktstandarder og forkortelsesniveauer.
Den valgte tabel vil blive brugt til at oversætte punkt til visning på dit punktdisplay.
Med piletasterne kan du flytte fra den ene punkttabel til den næste på listen.

##### Indtastningstabel {#BrailleSettingsInputTable}

Komplementært til den foregående indstilling er Den næste indstilling combo boxen indtastningstabel.
Den valgte tabel vil blive benyttet til at oversatte det, du indtaster på dit Perkins punkttastatur, til tekst.
Med piletasterne kan du flytte fra den ene punkttabel til den næste på listen.

Bemærk, at denne indstilling kun kan bruges, hvis dit punktdisplay har et Perkins punkttastatur og funktionen er understøttet af driveren til displayet.
Hvis indtastning ikke er understøttet af et punktdisplay med tilhørende tastatur, vil dette være noteret i kapitlet [Understøttede Punktdisplays](#SupportedBrailleDisplays).

<!-- KC:setting -->

##### Punkttilstand {#BrailleMode}

Key: `NVDA+alt+t`

Denne indstilling lader dig skifte mellem to tilstande for punktskrift.

To punkttilstande er i øjeblikket tilgængelige, "følg markører" og "vis taleoutput".

Når indstillingen "følg markører" er valgt, vil dit display følge systemfokus/systemmarkøren, eller navigatorobjektet/læsemarkøren, afhængigt af hvad punktmarkøren er indstillet til at følge.

Hvis indstillingen er indstillet til "Vis taleoutput", vil punktdisplayet vise, hvad NVDA siger. Er taleindstillingen ikke indstillet til "tale", vil denne indstilling vise på punkt, hvad NVDA ville have sagt.

##### Udvid ordet ved markøren til computer-Braille {#BrailleSettingsExpandToComputerBraille}

Med denne indstilling kan du få ordet under markøren vist i uforkortet computer-braille.

##### Vis markør {#BrailleSettingsShowCursor}

Denne indstilling lader dig slå punktmarkøren til og fra.
Denne indstilling anvendes til brug af system- og læsemarkøren, men ikke valgmarkøren.

##### Blinkende markør {#BrailleSettingsBlinkCursor}

Denne indstilling gør punktmarkøren i stand til at blinke.
Hvis dette er slået fra, vil markøren konstant forblive i "op" positionen.
Valgmarkøren er ikke påvirket af denne indstilling, men vil altid forblive punkt 7 og 8 uden disse punkter blinker.

##### Blinkhastighed for markør (MS) {#BrailleSettingsBlinkRate}

Denne indstilling er et felt til indtastning af en talværdi. Her har du mulighed for at indtaste markørens blinkhastighed i millisekunder.

##### Markørform til fokus {#BrailleSettingsCursorShapeForFocus}

Denne indstilling lader dig vælge formen (punktmønstret) til brugen af punktmarkøren, når punktmarkøren følger fokus.
Udvælgelsesindikatoren påvirkes ikke af denne indstilling,  men vil altid forblive punkt 7 og 8 uden disse punkter blinker.

##### Markørform til læsning {#BrailleSettingsCursorShapeForReview}

Denne indstilling lader dig vælge formen (punktmønstret) til brugen af punktmarkøren, når punktmarkøren følger læsemarkøren.
Udvælgelsesindikatoren påvirkes ikke af denne indstilling,  men vil altid forblive punkt 7 og 8 uden disse punkter blinker.

##### Vis beskeder {#BrailleSettingsShowMessages}

Denne indstilling lader dig vælge, hvordan NVDA skal vise beskeder på punkt og om disse skal forsvinde automatisk.

Hvis du vil ændre denne indstilling fra hvor som helst, kan duk tildele et tastetryk til denne indstilling fra [dialogen Håndter kommandoer](#InputGestures).

##### Besked vises i (sek) {#BrailleSettingsMessageTimeout}

Denne indstilling er et felt til indtastning af en talværdi, som styrer, hvor længe NVDA-meddelelser vises på punktdisplayet.
Ved et tryk på en markørknap på punktdisplayet, vil beskeden forsvinde. Beskeden vil blive vist igen, såfremt der trykkes en tilsvarende tast.
Denne indstilling vises kun, hvis "Vis beskeder" er indstillet til "Brug timeout".

<!-- KC:setting -->

##### Punkt følger {#BrailleTether}

Tast: NVDA+Ctrl+t

Med denne indstilling kan du vælge, om punktdisplayet skal følge systemfokus/systemmarkøren, om det skal følge navigatorobjektet /læsemarkøren eller begge dele.
Med "automatisk" valgt, vil NVDA som standard følge systemmarkøren og læsemarkøren.
Med denne indstilling vil NVDA midlertidigt følge læsemarkøren ved ændringer, men stopper ved ændring af systemfokus.
For kun at følge systemfokus og systemmarkøren, skift til "Fokus".
Her vil punkt ikke følge navigatorobjektet eller læsemarkøren.
Ønsker du at punkt skal følge læsemarkøren, vælg "Læsemarkør".
Med denne indstilling ignorerer punkt systemfokus og systemmarkøren.

##### Flyt systemmarkør, når læsemarkøren flyttes med markørknapperne {#BrailleSettingsReviewRoutingMovesSystemCaret}

Denne indstilling afgør, om systemmarkøren også skal flyttes med markørknapperne.
Denne indstilling er sat til Aldrig som standard, hvilket betyder, at markørknapperne aldrig vil flytte systemmarkøren, når du flytter gennemsynsmarkøren.

Når denne indstilling er sat til Altid, og [ punkt følger](#BrailleTether) er indstillet til automatisk eller læsemarkøren, vil et tryk på en markørknap også flytte systemmarkøren eller systemfokus, når det understøttes.
Når den aktuelle læsetilstand er [Skærmtilstand](#ScreenReview), er der ingen systemmarkør.
I dette tilfælde forsøger NVDA at fokusere på objektet under den tekst, du flytter til.
Det samme gælder for [objekttilstand](#ObjectReview).

Du kan også indstille denne mulighed til kun at flytte systemmarkøren, når den følger automatisk.
I så fald vil et tryk på en markørknap kun flytte systemets systemmarkør eller fokus, når NVDA automatisk følger læsemarkøren, mens der ikke vil ske nogen bevægelse, når den manuelt er forbundet til læsemarkøren.

Denne mulighed vises kun, hvis "[punkt følger](#BrailleTether)" er sat til "Automatisk" eller "Til læsemarkør".

For at ændre denne indstilling fra hvor som helst, kan du tildele et tastetryk fra [dialogen "Håndter kommandoer..."](#InputGestures)

| . {.hideHeaderRow} |.|
|---|---|
|Options |Default (Never), Never, Only when tethered automatically, Always|
|Default |Never|

##### Læs i afsnit {#BrailleSettingsReadByParagraph}

Hvis du slår denne indstilling til, vil du få vist punkt et afsnit ad gangen i stedet for en linje ad gangen.
Desuden vil kommandoer til forrige og næste linje flytte et afsnit ad gangen.
Det betyder, at du ikke behøver at rulle med displayet for enden af hver linje, selv ikke hvis der er plads til mere tekst på displayet.
Det kan give mulighed for en mere flydende læseoplevelse, når der er tale om store mængder tekst.
Som standard er dette slået fra.

##### Paragraph start marker {#BrailleParagraphStartMarkers}

If "Read by paragraph" is checked, the selected start marker will be displayed to indicate the start of a paragraph.
This can be especially helpful in applications used to read large pieces of text, like structured documents or books.
In such documents, knowing where paragraphs start may be useful to understand the structure of the content, or to set bookmarks or annotations based on paragraph position.

The options include using two spaces as a subtle paragraph break, and the paragraph symbol, pilcrow (¶), as a more obvious one.

| . {.hideHeaderRow} |.|
|---|---|
|Options |No paragraph start marker, Double space (  ), Pilcrow (¶)|
|Default |No paragraph start marker|

##### fokuskontekstpræsentation {#BrailleSettingsFocusContextPresentation}

Denne indstilling giver dig mulighed for at vælge, hvilke kontekstoplysninger NVDA vil vise på punktdisplayet, når et objekt får fokus.
Kontekstoplysninger refererer til hierarkiet af objekter, der indeholder fokus.
For eksempel, når du fokuserer et listeobjekt, er dette liste element en del af en liste.
Denne liste kan være indeholdt i en dialog mv.
Se venligst afsnittet om [objektnavigation](#ObjectNavigation) for at få flere oplysninger om det hierarki, der gælder for objekter i NVDA.

Når den er indstillet til at udfylde displayet for kontekstændringer, forsøger NVDA at vise så meget kontekstinformation som muligt på punktdisplayet, men kun for de dele af konteksten, der er ændret.
For eksemplet ovenfor betyder dette, at når du skifter fokus til listen, vil NVDA vise listeemnet på punktdisplayet.
Desuden vil NVDA forsøge at vise, at listeemnet er en del af en liste, hvis der er tilstrækkelig plads tilbage på punktdisplayet.
Hvis du så begynder at flytte gennem listen med dine piletaster, antages det at du er klar over, at du stadig er på listen.
Derfor vil de resterende listeemner, du fokuserer på, kun vise det fokuserede listeemne på displayet.
For at du kan læse konteksten igen (dvs. at du er på en liste, og at listen er en del af en dialog), skal du rulle dit punktdisplay tilbage.

Når denne indstilling er indstillet til altid at fylde displayet, vil NVDA forsøge at vise så meget kontekstinformation som muligt på punktdisplayet, uanset om du tidligere har set de samme kontekstoplysninger.
Dette har den fordel, at NVDA vil vise så meget information som muligt på skærmen.
Ulempen er imidlertid, at der altid er en forskel i den position, hvor fokus befinder sig på punktdisplayet.
Dette kan gøre det vanskeligt at skimme en lang liste med emner, for eksempel, da du bliver nødt til løbende at flytte din finger for at finde starten på emnet.
Dette var standardadfærden for NVDA 2017.2 og tidligere.

Når du indstiller fokuskontekstpræsentationsfunktionen til kun at vise kontekstoplysningerne, når du ruller tilbage, viser NVDA som standard aldrig kontekstoplysninger på dit punktdisplay.
Således vil NVDA i eksemplet ovenfor vise, at du har fokus på et listeemne.
For at du skal kunne læse konteksten (dvs. at du er på en liste, og at listen er en del af en dialog), skal du rulle dit punktdisplay tilbage.

Hvis du vil skifte fokuskontekstpræsentation fra hvor som helst, skal du tildele en brugerdefineret bevægelse eller et tastetryk ved hjælp af [dialogboksen Håndter Kommandoer](#InputGestures).

##### Vis valgmarkør {#BrailleSettingsShowSelection}

Denne indstilling bestemmer, om valgmarkøren (punkter 7 og 8) skal vises på punktdisplayet.
Indstillingen er som standard aktiveret, så valgmarkøren vises.
Valgmarkøren kan være distraherende under læsning.
Hvis du deaktiverer denne indstilling, kan læsbarheden forbedres.

For at ændre denne indstilling fra et hvilket som helst sted, skal du tildele et brugerdefineret tastetryk ved hjælp af [dialogen Håndter kommandoer](#InputGestures).

| . {.hideHeaderRow} |.|
|---|---|
|Options |Default (Enabled), Enabled, Disabled|
|Default |Enabled|

##### Formatting display {#BrailleFormattingDisplay}

This setting determines how NVDA will display text formatting in braille.
This option only has an effect if NVDA is set to [display font attributes in braille](#DocumentFormattingFontAttributes).

| . {.hideHeaderRow} |.|
|---|---|
| Options | Default (Liblouis), Liblouis, Tags |
| Default | Liblouis |

| Option | Behaviour |
|---|---|
| Liblouis | Use native Braille formatting. Note that this option will only indicate bold, italic and underlined text, and only if the selected braille table supports indicating these attributes. |
| [Tags](#BrailleFormattingDisplayTags) | Use tags that describe how and where text formatting changes. |

###### Tags {#BrailleFormattingDisplayTags}

When "Formatting display" is set to "Tags", a formatting tag is displayed in braille when a change in formatting is detected.
These tags start with ⣋ and end with ⣙.
A formatting tag will contain one or more symbols which describe the text formatting.
The following symbols are defined:

| Symbol | Meaning |
|---|---|
| ⠃ ("b") | Start bold |
| ⡃ ("b" with dot 7) | End bold |
| ⠊ ("i") | Start italic |
| ⡊ ("i" with dot 7) | End italic |
| ⠥ ("u") | Start underline |
| ⡥ ("u" with dot 7) | End underline |
| ⠎ ("s")| Start strikethrough |
| ⡎ ("s" with dot 7) | End strikethrough |

##### Speak character when routing cursor in text {#BrailleSpeakOnRouting}

If this is enabled, NVDA will automatically speak the character at the cursor when routing to it with braille cursor routing keys.

To toggle this option from anywhere, please assign a custom gesture using the [Input Gestures dialog](#InputGestures).

##### Avoid splitting words when possible {#BrailleSettingsWordWrap}

If this is enabled, a word which is too large to fit at the end of the braille display will not be split.
Instead, there will be some blank space at the end of the display.
When you scroll the display, you will be able to read the entire word.
This is sometimes called "word wrap".
Note that if the word is too large to fit on the display even by itself, the word must still be split.

If this is disabled, as much of the word as possible will be displayed, but the rest will be cut off.
When you scroll the display, you will then be able to read the rest of the word.

Enabling this may allow for more fluent reading, but generally requires you to scroll the display more.

##### Unicode normalization {#BrailleUnicodeNormalization}

When this option is enabled, unicode normalization is performed on the text that is brailled on the braille display.
This is beneficial when coming across characters in braille that are unknown in a particular braille table and which have a compatible alternative, like the bold and italic characters commonly used on social media.
Other benefits of unicode normalization are explained in greater detail in the [section for the equivalent speech setting](#SpeechUnicodeNormalization).

To toggle Unicode normalization from anywhere, please assign a custom gesture using the [Input Gestures dialog](#InputGestures).

| . {.hideHeaderRow} |.|
|---|---|
|Options |Default (Disabled), Enabled, Disabled|
|Default |Disabled|

##### Interrupt speech while scrolling {#BrailleSettingsInterruptSpeech}

This setting determines if speech should be interrupted when the Braille display is scrolled backwards/forwards.
Previous/next line commands always interrupt speech.

On-going speech might be a distraction while reading Braille.
For this reason the option is enabled by default, interrupting speech when scrolling braille.

Disabling this option allows speech to be heard while simultaneously reading Braille.

| . {.hideHeaderRow} |.|
|---|---|
|Options |Default (Enabled), Enabled, Disabled|
|Default |Enabled|

#### Vælg punktdisplay {#SelectBrailleDisplay}

<!-- KC:setting -->

##### Åbn dialog til valg af punktdisplay {#OpenSelectBrailleDisplay}

Tast: `NVDA+control+a`

Denne dialog, der tilgås vha. knappen "Skift..." i NVDAs indstillingsdialog under kategorien "Punkt", lader dig vælge hvilket punktdisplay NVDA skal benytte.
Når du har valgt dit punktdisplay, kan du trykke på knappen "OK", hvorefter NVDA vil benytte det valgte display.
Hvis der er en fejl under indlæsning af driveren til det aktuelle display, vil NVDA meddele dette med en besked, og fortsætte med at bruge det tidligere benyttede display, hvis aktuelt.

##### Punktdisplay[SelectBrailleDisplayDisplay] {#SelectBrailleDisplayDisplay}

Denne kombobox viser dig forskellige muligheder  alt efter, hvilke punktdisplay-drivere der er tilgængelige på dit system.
Brug piletasterne til at flytte imellem de forskellige valgmuligheder.

Den automatiske indstilling gør det muligt for NVDA at søge og automatisk tilkoble understøttede punktdisplays i baggrunden.
Når denne funktion er slået til, vil NVDA forbinde automatisk med punktdisplayet, hvis det benyttes med Bluetooth eller USB.

"Ingen punkt" betyder, at du i øjeblikket ikke bruger noget punktdisplay.

Læs venligst afsnittet [Understøttede punktdisplays](#SupportedBrailleDisplays) for yderligere oplysninger om understøttede punktdisplays, samt hvilke af disse understøtter automatisk tilkobling.

##### Displays, der skal detekteres automatisk {#SelectBrailleDisplayAutoDetect}

Hvis "Punktdisplay" er indstillet til "automatisk", vil valgene af disse bokse bestemme, hvilke displays der automatisk bliver tilkoblet.
Dette lader dig udelade drivere, som du ikke regelmæssigt benytter.
Hvis du eksempelvis kun bruger displays, der kræver at Baum-driveren er aktiv, kan du med fordel udelade alle andre drivere.

Som standard er alle drivere, der understøtter automatisk detektion aktiveret.
Enhver driver, der tilføjes senere i enten en NVDA-opdatering eller via en tilføjelse, vil også blive aktiveret som standard.

Du kan læse, hvilke displays understøtter denne funktionalitet ved at læse afsnittet [Understøtede punktdisplays](#SupportedBrailleDisplays).

##### Port {#SelectBrailleDisplayPort}

Hvis denne indstilling er tilgængelig, giver den dig mulighed for at vælge, hvilken port eller forbindelsestype du vil benytte for at kommunikere med det punktdisplay, du har valgt.
Det er en kombobox der indeholder de mulige indstillinger for dit display.

Som standard søger NVDA automatisk efter den påkrævede port til dit punktdisplay ved brug af automatisk tilkobling, hvilket betyder, at NVDA automatisk vil etablere forbindelse med din enhed ved at scanne computeren for alle tilgængelige USB og Bluetooth enheder koblet til dit system.
For nogle punktdisplays er det dog muligt at vælge direkte, hvilken port du vil bruge.
Almindelige indstillinger er "Automatisk" (hvilket gør at NVDA anvender standardproceduren til valg af porte), "USB", "Bluetooth" og ældre seriel porte til kommunikation hvis dit display understøtter denne forbindelsestype.

Denne indstilling er ikke tilgængelig, hvis dit display kun understøtter automatisk tilkobling.

Læs dokumentationen for dit punktdisplay i afsnittet [Understøttede punktdisplays](#SupportedBrailleDisplays) for at læse om de mulige tilkoblingsmuligheder og tilgængelige porte.

Bemærk: Hvis du forbinder to punktdisplays, der bruger den samme driver til din maskine på samme tid (f.eks. to Seika displays),
vil det ikke i øjeblikket være muligt at fortælle NVDA, hvilket display, der skal benyttes.
Derfor anbefales det, at du kun forbinder ét display af en bestemt type og af et bestemt mærke til din maskine ad gangen.

#### Lyd {#AudioSettings}

<!-- KC:setting -->

##### Åbn lydindstillinger {#OpenAudioSettings}

Tast: `NVDA+control+u`

Denne kategori i NVDAs indstillinger lader dig ændre nogle indstillinger i forhold til lydoutput.

##### Output-enhed {#SelectSynthesizerOutputDevice}

Denne valgmulighed bruges til at bestemme, hvilket lydkort den aktuelt valgte talesyntese skal tale igennem.

<!-- KC:setting -->

##### Lyddæmpningstilstand {#SelectSynthesizerDuckingMode}

Tast: `NVDA+shift+D`

Med denne  indstilling kan du vælge, om NVDA skal sænke lydstyrken af andre applikationer, når NVDA taler, eller om NVDA konstant skal sænke lydstyrken imens NVDA kører.

* Ingen lyddæmpning: NVDA vil aldrig dæmpe lydstyrken af andre lydkilder.
* Dæmp, når der udsendes tale og lyde: NVDA vil kun dæmpe lyden, hvis NVDA afspiller lyde eller taler. Dette virker muligvis ikke for alle talesynteser.
* Altid dæmp: NVDA vil sænke lyden fra alle andre lydkilder, så længe NVDA kører.

Denne indstilling er kun tilgængelig, hvis NVDA er installeret.
Det er ikke muligt at understøtte lyddæmpning for midlertidige og flytbare kopier af NVDA.

##### Lydstyrken af NVDA-lyde følger stemmelydstyrken {#SoundVolumeFollowsVoice}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Deaktiveret, Aktiveret|
|Standard |Deaktiveret|

Når denne indstilling er aktiveret, vil lydstyrken af NVDA-lyde og bip-lyde følge stemmens lydstyrke for den stemme, du bruger.
Hvis du sænker stemmelydstyrken, vil lydstyrken af lydeffekter også blive sænket.
På samme måde vil lydstyrken af lydeffekter blive øget, hvis du øger  for stemmen.lydstyrken
Denne indstilling er ikke tilgængelig, hvis du slår [WASAPI fra som lydoutput](#WASAPI) i NVDAs avancerede indstillinger.

##### Lydstyrke for NVDA-lyde {#SoundVolume}

Denne skyder lader dig indstille lydstyrken for NVDAs lyde og bip.
Denne indstilling træder kun i kraft, hvis "Brug WASAPI for lydoutput" er aktiveret og "Lydstyrken af NVDA-lyde følger stemmelydstyrken" er deaktiveret.
Denne indstilling er ikke tilgængelig, hvis du slår [WASAPI fra som lydoutput](#WASAPI) i NVDAs avancerede indstillinger.

##### Lydopdeling {#SelectSoundSplitMode}

Lydopdelingsfunktionen giver brugere mulighed for at udnytte deres stereo-udgangsenheder, såsom hovedtelefoner og højttalere.
Lydopdeling gør det muligt at have NVDA-tale i den ene kanal (f.eks. venstre) og have alle andre programmer afspille deres lyde i den anden kanal (f.eks. højre).
Som standard er lydopdeling deaktiveret.
En kommando lader dig skifte mellem de forskellige lydopdelingstilstande:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Skift Lydopdelingstilstand |`NVDA+alt+s` |Skifter mellem lydopdelingstilstandene.|

<!-- KC:endInclude -->

Som standard vil denne kommando skifte mellem følgende tilstande:

* Deaktiveret lydopdeling: både NVDA og andre applikationer udsender lyde til både venstre og højre kanaler.
* NVDA i vebstre og programmer i højre: NVDA vil tale i venstre kanal, mens andre programmer vil afspille lyde i højre kanal.
* NVDA i venstre og alle andre programmer i begge kanaler: NVDA vil tale i venstre kanal, og alle andre programmer vil afspille lyde i begge kanaler.

Der er flere avancerede lydopdelingstilstande tilgængelige i NVDA-indstillingerne.
Blandt disse tilstande, vil indstillingen "NVDA og programmer i begge kanaler" tvinge lyden til at blive afspillet i begge kanaler.
Denne indstilling kan virke anderledes end hvis du blot Deaktiverer lydopdeling, såfremt anden lydbehandling påvirker kanalernes lydstyrke.

Bemærk venligst, at lydopdeling ikke fungerer som en mixer.
For eksempel, hvis et program afspiller et stereo-lydspor, mens lydopdelingen er sat til "NVDA i venstre og programmer i højre", vil du kun høre højre kanal af lydsporet, mens venstre kanal af lydsporet vil være slået fra.

Denne indstilling er ikke tilgængelig, hvis du har startet NVDA med [WASAPI deaktiveret for lydudgang](#WASAPI) i avancerede indstillinger.

Bemærk venligst, at hvis NVDA går ned, vil den ikke være i stand til at genoprette programmernes lydstyrke, og disse kan stadig udsende lyd i én kanal efter NVDA-nedbrud.
For at afhjælpe dette, genstart NVDA og vælg "NVDA og programmer i begge kanaler".

##### Tilpasning af lydopdeling {#CustomizeSoundSplitModes}

Denne liste lader dig vælge, hvilke lydopdelingstilstande der er inkluderet, når der skiftes mellem dem ved hjælp af `NVDA+alt+s`.
Tilstande, som ikke er afkrydset, fremkommer ikke.
Som standard er kun tre tilstande inkluderet.

* Lydopdeling deaktiveret: både NVDA og programmer afspiller lyde i både venstre og højre kanaler.
* NVDA i venstre og alle andre programmer i højre kanal.
* NVDA i venstre og alle andre programmer i begge kanaler.

Bemærk, at det er nødvendigt at afkrydse mindst én tilstand.
Denne mulighed er ikke tilgængelig, hvis du har startet NVDA med [WASAPI deaktiveret for lydudgang](#WASAPI) i avancerede indstillinger.

##### Tid lydenheden skal holdes i gang, når tale er stoppet {#AudioAwakeTime}

Denne combo box bestemmer, hvor længe NVDA holder lydenheden aktiv, efter at talen er stoppet.
Dette giver NVDA mulighed for at undgå visse talefejl som udeladte dele af ord.
Dette kan ske på grund af lydenheder (især Bluetooth- og trådløse enheder) der går i dvaletilstand.
Dette kan også være nyttigt i andre tilfælde, såsom når NVDA kører inden i en virtuel maskine (f.eks. Citrix Virtual Desktop), eller på visse bærbare computere.

Lavere værdier vil gøre, at lyd oftere bliver afbrudt, da enheden kan gå i dvaletilstand for tidligt, hvilket får begyndelsen af den efterfølgende tale til at blive afkortet.
At indstille værdien for høj kan forårsage, at batteriet på lydudgangsenheden aflades hurtigere, da den forbliver aktiv længere, mens der ikke sendes lyd.

Du kan indstille tiden til 0 for at deaktivere denne funktion.

#### Syn {#VisionSettings}

Indstillingskategorien "Syn" lader dig aktivere, deaktivere samt konfigurere diverse [synshjælpemidler](#Vision).

Bemærk, at disse muligheder kan udvides ved brug af [tilføjelsespakker](#AddonsManager).
Denne kategori indeholder som udgangspunkt følgende:

##### Visuel fremhævning {#VisionSettingsFocusHighlight}

Indstillingerne her bestemmer adfærden for NVDAs [evne til at fremhæve fokuspositionen](#VisionFocusHighlight).

* Aktivér fremhævelse: Slår fremhævelse af fokus til eller fra.
* Fremhæv systemfokus: Bestemmer om [systemfokus](#SystemFocus) skal fremhæves.
* Fremhæv navigatorobjekt: Bestemmer om [navigatorobjektet](#ObjectNavigation) skal fremhæves.
* Fremhæv markør i gennemsynstilstand: Bestemmer om [den virtuelle markør i gennemsynstilstand](#BrowseMode) skal fremhæves.

Bemærk, hvis du aktiverer eller deaktiverer fremhævelse ved brug af boksen, vil de andre indstillinger også ændres.
Markerer du denne check box, hvis funktionen er deaktiveret, vil de tre andre forholdsvist vælges.
Hvis du kun vil fremhæve systemfokus, men derimod ikke ønsker at fremhæve navigatorobjektet eller markøren i gennemsynstilstand, vil tilstanden for denne indstilling være delvist markeret.

##### Skærmtæppe {#VisionSettingsScreenCurtain}

Du kan aktivere [skærmtæppet](#VisionScreenCurtain) ved at markere "Gøre skærmen sort (aktiveres øjeblikkeligt)".
En varsel om at skærmen vil blive sort vises.
Før du fortsætter (ved at vælge "Ja"), skal du sikre dig at du kan styre computeren uden en skærm ved brug af tale eller punkt.
Vælg "Nej", hvis du ikke længere vil anvende skærmtæppet.
Hvis du er sikker, kan du aktivere funktionen ved at vælge "Ja"..
Hvis du ikke vil se denne advarsel, hver gang du aktivererer funktionen, kan du ændre dette i dialogen.
Du kan altid få advarslen til at komme frem igen, hvis du markerer "Vis altid en advarsel, når Skærmtæppe indlæses".

Som standard vil en lyd blive afspillet, når NVDA starter og NVDA aktiverer skærmtæppet automatisk.
Du kan ændre denne adfærd ved at fjerne markeringen fra den pågældende boks i indstillingerne.

##### Indstillinger for synshjælpemidler fra tredjeparter {#VisionSettingsThirdPartyVisualAids}

Yderligere synshjælpemidler kan tilføjes via [tilføjelsespakker til NVDA](#AddonsManager).
Når disse tilføjelser indeholder indstillinger, vil de vises i denne indstillingskategori i særskilte grupper.
For understøttede indstillinger, skal du læse dokumentationen for det aktuelle synshjælpemiddel.

#### Tastatur {#KeyboardSettings}

<!-- KC:setting -->

##### Åbn tastaturindstillinger {#OpenKeyboardSettings}

Tast: `NVDA+control+k`

Denne indstillingskategori bestemmer hvordan NVDA skal opføre sig, når du benytter et tastatur.
Denne indstillingskategori indeholder følgende indstillingsmuligheder:

##### Tastaturlayout {#KeyboardSettingsLayout}

Denne combo box giver mulighed for at vælge, hvilken type tastaturlayout NVDA skal benytte. De 2 muligheder, der i øjeblikket er inkluderet i NVDA er Desktop og Laptop.

##### Vælg NVDA-funktionstaster {#KeyboardSettingsModifiers}

Check boxe i denne liste lader dig vælge, hvilke taster du ønsker at benytte som din [NVDA-tast](#TheNVDAModifierKey). Her kan du vælge følgende taster:

* CAPSLock-tasten
* Insert-tasten på det numeriske tastatur
* Den udvidede insert-tast (findes sædvanligvis over piletasterne ved hjem og end-tasterne).

Hvis der ikke er valgt nogen tast som NVDA-tast, kan det være umuligt at nå visse NVDA-funktioner. Du skal vælge mindst én af disse taster.

<!-- KC:setting -->

##### Sig indtastede tegn {#KeyboardSettingsSpeakTypedCharacters}

Tast: NVDA+2

Når denne funktion er slået til, oplæser NVDA alle de tegn, du skriver på tastaturet.

<!-- KC:setting -->

##### Sig indtastet ord {#KeyboardSettingsSpeakTypedWords}

Tast: NVDA+3

Når denne funktion er slået til, oplæser NVDA hvert ord, du skriver på tastaturet.

##### Afbryd tale ved indtastning {#KeyboardSettingsSpeechInteruptForCharacters}

Hvis denne indstilling er slået til, vil talen blive afbrudt, hver gang du indtaster et tegn. Dette er slået til som standard.

##### Afbryd talen ved tryk på Enter {#KeyboardSettingsSpeechInteruptForEnter}

Hvis denne indstilling er slået til, vil talen blive afbrudt, når du trykker på Enter. Dette er slået til som standard.

##### Tillad skimlæsning ved Sig Alt {#KeyboardSettingsSkimReading}

Hvis denne indstilling er slået til, vil en del navigationskommandoer ikke stoppe talen under "Sig alt". Det gælder fx. Hurtignavigationstaster i gennemsynstilstand eller navigering i linjer og afsnit. I stedet vil NVDA hoppe til den nye position og fortsætte med at læse.

##### Bip hvis der skrives med små bogstaver når Caps Lock er slået til {#KeyboardSettingsBeepLowercase}

Når denne indstilling er slået til, vil du høre et advarende bip, hvis et bogstav bliver indtastet med skift-tasten nede, mens Caps Lock er slået til.
Generelt er det utilsigtet, hvis man skriver bogstaver med shift-tasten nede, mens Caps Lock er slået til. Sædvanligvis skyldes det, at man ikke er klar over, at Capslock er slået til.
Derfor kan det være meget rart at blive advaret om det.

<!-- KC:setting -->

##### Sig funktionstaster {#KeyboardSettingsSpeakCommandKeys}

Tast: NVDA+4

Når denne funktion er slået til, oplæser NVDA alle taster på tastaturet, der ikke er bogstaver, når du trykker på dem. Dette omfatter ligeledes tastekombinationer som Ctrl plus et bogstav.

##### Afspil lyd for stavefejl ved skrivning {#KeyboardSettingsAlertForSpellingErrors}

Når denne indstilling er aktiveret vil der blive afspillet en lyd, hvis du begår en stavefejl imens du skriver.
Denne indstilling er kun tilgængelig hvis "Annoncér stavefejl" indstillingen er slået til i NVDAs [Dokumentformateringsindstillinger](#DocumentFormattingSettings) i NVDAs indstillinger.

##### Håndter tastetryk fra andre programmer {#KeyboardSettingsHandleKeys}

Med denne indstilling kan du vælge, om NVDA skal behandle tastetryk, der bliver genereret af andre programmer som fx. skærmtastaturer eller talegenkendelsesprogrammer.
Denne indstilling er slået til som standard, men nogle brugere vil måske foretrække at slå den fra, fx. hvis man skriver vietnamesisk med UniKey. I dette tilfælde kan det forårsage indtastning af forkerte bogstaver.

##### Multiple key press timeout {#MultiPressTimeout}

Some NVDA keyboard gestures perform different actions based upon how many times the same key is pressed in rapid succession.
An example of this is the "Report current character of navigator object" command.
This command reports the character if pressed once, a phonetic description of the character if pressed twice, and the numeric value of the character if pressed three times.
This option configures the timeout after which an additional press of the same key will start a new gesture, rather than being taken as a subsequent press of the first one.
For the example command, a too short timeout will cause two presses to report the current character twice, rather than the phonetic description.
The default timeout is 500 ms, i.e. half a second.
Increasing this timeout may be especially useful for people using sticky keys, or who have a physical disability.

#### Mus {#MouseSettings}

<!-- KC:setting -->

##### Åbn museindstillinger {#OpenMouseSettings}

Tast: `NVDA+control+m`

Denne indstillingskategori kontrollerer indstillinger der lader NVDA spore musen, afspille lyde i forhold til musens koordinater, samt andre muserelaterede indstillinger.
Denne indstillingskategori indeholder følgende indstillingsmuligheder:

##### Oplæs ændringer i musemarkørens form {#MouseSettingsShape}

Når denne check box er markeret, vil NVDA fortælle formen på musemarkøren, hver gang den ændrer sig.
I Windows ændrer musemarkøren form for at videregive visse typer af information som fx. når noget kan redigeres,, når noget er ved at blive indlæst osv. .

<!-- KC:setting -->

##### Følg musen {#MouseSettingsTracking}

Tast: NVDA+m

Når denne funktion er slået til, oplæser NVDA den tekst, der i øjeblikket befinder sig under musemarkøren i takt med, at musemarkøren flyttes rundt på skærmen. Det giver mulighed for at finde ting på skærmen ved fysisk at bevæge musen, i stedet for at lede efter dem ved hjælp af objektnavigation.

##### Opløsning for tekstenhed {#MouseSettingsTextUnit}

Hvis NVDA er indstillet til at oplæse teksten under musen, når du flytter med den, giver denne indstilling mulighed for at bestemme præcist, hvor meget tekst der skal læses op.
Indstillingsmulighederne er tegn, ord, linje og afsnit.

For at ændre opløsning for tekstenhed fra hvor som helst, kan du tildele en kommando via [dialogen Håndter Kommandoer](#InputGestures).

##### Oplys object, når musen flyttes ind i det {#MouseSettingsRole}

Hvis denne check box er markeret, oplæser NVDA objektet, når musen bevæger sig ind i objektet.
Dette omfatter typen af objekt, samt om det eksempelvis er markeret eller ej, cellekoordinater i tabeller, osv.
Bemærk, at nogle af detaljerne, der oplyses om det pågældende objekt, kan afhænge af andre indstillinger. Informationsniveauet påvirkes typisk af indstillingerne i [objektpræsentation](#ObjectPresentationSettings) eller [dokumentformatering](#DocumentFormattingSettings).

##### Afspil lydkoordinater under flytning af mus {#MouseSettingsAudio}

Hvis denne check box er slået til, bipper NVDA under flytning af musen. På den måde kan du følge med i, hvor musen netop nu befinder sig på skærmen.
Jo højere oppe musen befinder sig på skærmen, desto højere bliver tonehøjden af lydsignalet.
Jo længere mod venstre eller højre musen befinder sig på skærmen, desto længere mod venstre eller højre vil lyden blive afspillet (forudsat at du har stereohøjttalere eller hovedtelefoner).

##### Lysstyrke kontrollerer lydstyrke for lydkoordinater {#MouseSettingsBrightness}

Hvis check boxen "Afspil lydkoordinater under flytning af mus" er slået til, bevirker markering af denne check box, at lydstyrken på biptonen ved lydkoordinaterne bestemmes af, hvor lyst skærmbilledet under musen er.
Denne indstilling er slået fra som standard.

##### Ignorér museinput fra andre applikationer {#MouseSettingsHandleMouseControl}

Denne indstilling lader brugeren ignorere musehandlinger (f.eks. musebevægelse og museklik) udført af andre programmer som TeamViewer og andet software til fjernstyring.
Denne indstilling er slået fra som standard.
Hvis du vælger denne indstilling og du har slået "følg musen" til, vil NVDA ikke annoncere hvad der befinder sig under musen, når musen flyttes af andre applikationer.

#### Berøringsinteraktion {#TouchInteraction}

Denne indstillingskategori vil kun være tilgængelig på computere, der har mulighed for touch-funktionalitet. Disse indstillinger lader dig konfigurere, hvordan NVDA håndtere berøring af touchskærme.
Denne kategori indeholder følgende indstillinger:

##### Aktivér berøringsinteraktion {#TouchSupportEnable}

Denne indstilling aktiverer NVDAs understøttelse for touchskærme.
Hvis indstillingen er slået til, kan du bruge fingrene til at navigere på en enhed med en touchskærm.
Hvis indstillingen er slået fra, vil almindelige bevægelser på touchskærmen fungere som om NVDA var slået fra.
Denne indstilling kan også slås til og fra ved brug af NVDA+Control+T.

##### Berøringsindtastning {#TouchTypingMode}

Denne check box lader dig vælge den metode du ønsker at bruge, når du benytter berøringstastaturet.
Hvis denne check box er valgt, kan du indtaste bogstaver blot ved at løfte din finger fra den pågældende tast på tastaturet.
Hvis denne indstilling ikke er valgt, skal du dobbelttrykke med en finger på hvert bogstav, du vil skrive.

#### Læsemarkør {#ReviewCursorSettings}

Denne kategori benyttes til at konfigurere adfærden for læsemarkøren.
Denne indstillingskategori indeholder følgende indstillingsmuligheder:

<!-- KC:setting -->

##### Følg systemfokus {#ReviewCursorFollowFocus}

Tast: NVDA+7

Når denne funktion er slået til, bliver læsemarkøren altid placeret i samme objekt som det aktuelle systemfokus, når det ændrer sig.

<!-- KC:setting -->

##### Følg systemmarkør {#ReviewCursorFollowCaret}

Tast: NVDA+6

Når denne funktion er slået til, flyttes læsemarkøren automatisk til systemmarkørens position, hver gang den flytter sig.

##### Følg musemarkør {#ReviewCursorFollowMouse}

Når denne funktion er slået til, følger læsemarkøren musen, når musen flytter sig.

##### Simpel læsetilstand {#ReviewCursorSimple}

Når denne funktion er slået til, vil NVDA filtrere de objekter, du kan navigere til. NVDA vil udelukke de objekter, som i almindelighed ikke er af interesse, f.eks. usynlige objekter eller objekter, som kun bruges til layoutformål.

For at kunne slå simpel læsetilstand til og fra hvor som helst, tildel et tastetryk til kommandoen ved brug af [dialogen Håndter Kommandoer](#InputGestures).

#### Objektpræsentation {#ObjectPresentationSettings}

<!-- KC:setting -->

##### Åbn indstillinger for objektpræsentation {#OpenObjectPresentationSettings}

Tast: `NVDA+control+o`

Denne indstillingskategori benyttes til at bestemme hvor meget information NVDA skal rapportere om kontrolelementer, såsom beskrivelse og positionsinformation osv.
Disse indstillinger bliver som udgangspunkt ikke anvendt, når du er i gennemsynstilstand.
Indstillingerne gælder som udgangspunkt kun for rapportering af fokus, eller når du bruger objektnavigation, men dog ikke, når du læser tekstindhold (f.eks. gennemsynstilstand).

##### Oplys værktøjstips {#ObjectPresentationReportToolTips}

Dette er en check box der, når den er markeret, bevirker, at NVDA oplyser værktøjstips, når de kommer til syne.
En del vinduer og kontroller viser en lille meddelelse (eller et værktøjstip), når musemarkøren flyttes hen over dem, eller i visse tilfælde når fokus flyttes til dem.

##### Oplys meddelelser {#ObjectPresentationReportNotifications}

Når denne check box er markeret, oplyser NVDA meddelelser og hjælpeballonerne, når de fremkommer.

* Hjælpeballoner ligner værktøjstips med den forskel, at de som regel er større og er tilknyttet systemhændelser såsom at et netværkskabel er fjernet eller muligvis for at henlede opmærksomheden på Windows sikkerhedsproblemer.
* Toast-meddelelser og bliver vist i handlingscenteret i systembakken, og informerer dig om diverse hændelser (f.eks. hvis en opdatering til Windows er blevet downloadet, en ny e-mail ankommet, osv).

##### Oplys objektets genvejstaster {#ObjectPresentationShortcutKeys}

Når denne check box er markeret, medtager NVDA den genvejstast, der hører til et objekt eller en kontrol, under rapporteringen af det givne element.
Som eksempel kan nævnes filmenuen på en menulinje, der kan have genvejstasten alt+f.

##### Oplys information om objektets placering {#ObjectPresentationPositionInfo}

Denne indstilling giver dig mulighed for at vælge, om du ønsker at få et objekts position (dvs. 1 af 4) oplyst, når du flytter til objektet med enten fokusnavigation eller objektnavigation.

##### Gæt objektets positionsinformation når utilgængelig {#ObjectPresentationGuessPositionInfo}

Hvis denne indstilling er valgt, gør den NVDA i stand til at gætte placeringen af et objekt, hvis denne information ellers er utilgængelig for en bestemt kontrol.

Når denne indstilling er slåe ttil, vil NVDA rapportere positionsinformation for flere kontroller såsom menuer og værktøjslinjer, men denne information kan dog være en smule upræcis.

##### Oplys objektbeskrivelser {#ObjectPresentationReportDescriptions}

Slå denne check box fra, hvis du ikke ønsker at få en beskrivelse af objektet oplyst sammen med selve objektet (f.eks. søgeforslag eller automatisk oplæsning af dialoger, når de fremkommer, osv).

<!-- KC:setting -->

##### Output for behandlingslinjer {#ObjectPresentationProgressBarOutput}

Tast: NVDA+u

Denne indstilling bestemmer, hvordan NVDA annoncerer opdateringer af behandlingslinjer.

Der er følgende muligheder:

* Fra: Ændringer i behandlingslinjer annonceres ikke.
* Tale: NVDA oplæser behandlingslinjen i procent. Hver gang behandlingslinjen ændrer sig, oplæser NVDA den nye værdi.
* Bip: Denne mulighed får NVDA til at bippe hver gang behandlingslinjen ændrer sig. Jo højere biptonen er, desto nærmere er behandlingslinjen på at være fuldført.
* Bip og tal: Indstillingen får NVDA til både at tale og bippe, når en behandlingslinje ændrer sig.

##### Oplys behandlingslinjer i baggrunden {#ObjectPresentationReportBackgroundProgressBars}

Dette er en indstilling, der, når den er slået til, får NVDA til at rapportere en behandlingslinje, selvom den ikke fysisk er i forgrunden.
Hvis du minimerer et vindue eller skifter til et andet vindue end det, der indeholder behandlingslinjen, bliver NVDA ved med at overvåge den, hvilket gør det muligt for dig at lave andre ting samtidig med, at NVDA overvåger behandlingslinjen.

<!-- KC:setting -->

##### Oplys ændringer i dynamisk indhold {#ObjectPresentationReportDynamicContent}

Tast: NVDA+5

Skifter indstillingen for rapportering af nyt indhold, især objekter som terminalvinduer og historikfelter i chatprogrammer.

##### Afspil en lyd når auto-forslag vises {#ObjectPresentationSuggestionSounds}

Slår annonceringen af auto-forslag når de vises til og fra. Hvis denne indstilling er slået til, vil NVDA afspille en lyd for at indikere dette.
Auto-forslag er en liste af tekstforslag der er baseret på indtastning i bestemte tekstfelter og dokumenter.
Søgefeltet i startmenuen i Windows Vista og nyere vil for eksempel vise en liste af forslag baseret på hvad du skrev.
I nogle editfelter, såsom søgefelter i forskellige Windows 10 apps, er det muligt for NVDA at give dig besked, når automatiske tekstforslag vises når du skriver.
Listen med auto-forslag lukkes, når du bevæger dig væk fra editfeltet, og i nogle tilfælde vil NVDA være i stand til at meddele, når dette sker.

#### Inputkomposition {#InputCompositionSettings}

Denne indstillingskategori lader dig styre, hvordan NVDA rapporterer input af asiatiske tegn, såsom med IME eller indtastningstmetoder med TextService.
Bemærk, at indtastningsmetoder kan variere meget med hensyn til tilgængelige funktioner, samt hvordan de formidler information. Det vil højst sandsynligt være nødvendigt at konfigurere disse indstillinger for hver indtastningsmetode, så du kan opnå den mest effektive oplevelse, når du skriver.

##### Oplys automatisk alle tilgængelige kandidater {#InputCompositionReportAllCandidates}

Denne indstilling, der er slået til som standard, giver dig mulighed for automatisk at få alle synlige kandidater rapporteret, når de vises, eller når listen ændres.
Denne indstilling er nyttig for piktografiske indtastningsmetoder, såsom Nykenesisk ChangJie eller Boshiami, eftersom du automatisk kan høre deres symboler og numre og derefter vælge med det samme.
For fonetiske indtastningsmetoder såsom Kinesisk Nyfonetisk, kan det dog være mere hensigtsmæssigt at slå denne indstilling fra, da alle symboler vil lyde ens. Du vil blive nød til at bruge piletasterne og navigere listeelementerne enkeltvis for, at få flere oplysninger fra tegnets beskrivelse.

##### Annoncér valgte kandidat {#InputCompositionAnnounceSelectedCandidate}

Denne indstilling lader dig vælge, om NVDA automatisk skal annoncere den valgte kandidat, når en liste af kandidater vises eller du ændrer valget. Indstillingen er slået till som standard.
Dette er nødvendigt når du bruger indtastningsmetoder hvor den valgte kandidat kan ændres ved brug af piletasterne (såsom Kinesisk Nyfoneetisk), men for andre indtastningsmetoder kan det være mere effektivt at skrive med denne indstilling slået fra.
Bemærk, at læsemarkøren stadig vil blive placeret på den valgte kandidat, hvis denne indstilling er slået fra. Dette giver dig mulighed for at oplæse den valgte kandidat ved hjælp af objekt navigation eller læsemarkøren.

##### Medtag altid kort tegnbeskrivelse ved oplysning af kandidater {#InputCompositionCandidateIncludesShortCharacterDescription}

Denne indstilling lader dig vælge, om NVDA automatisk skal oplæse en kort beskrivelse for hvert tegn i en kandidat, hvis en kandidat er valgt eller når en list vises. Indstillingen er slået til som standard.
Bemærk, at for lokaliteter som kinesisk, er annonceringen af ekstra tegnbeskrivelser for den valgte kandidat ikke påvirket af denne indstilling.
Denne indstilling kan være nyttig for koreansk og japansk indtastningsmetoder.

##### Oplys ændringer i oplæsningsstrengen {#InputCompositionReadingStringChanges}

Nogle indtastningsmetoder, såsom Kinesisk Nyfonetisk og Nyt ChangJie har en oplæsningsstreng (nogle gange kendt som en forsætningsstreng).
Med denne indstilling kan du vælge, om NVDA skal annoncere nye tegn indtastet i denne oplæsningsstreng.
Denne indstilling er slået til som standard.
Bemærk, at nogle ældre indtastningsmetoder såsom kinesisk ChangJie må ikke bruge oplæsningsstrengen til at holde kompositionstegn, men i stedet direkte bruge kompositionsstrengen. Se venligst den næste indstilling til konfiguration af rapportering af kompositionsstrengen direkte. Se næste indstilling for mulighed for at få annonceret kompositionsstrengen.

##### Oplys ændringer i kompositionsstrengen {#InputCompositionCompositionStringChanges}

Efter at oplæsning eller prekompositionsdata er blevet kombineret til et gyldigt billedskrifttegn, placere de fleste indtastningsmetoder dette symbol i en kompositionsstreng sammen med andre kombinerede symboler for midlertidig opbevaring, indtil disse symboler til sidst bliver indssat i dokumentet.
Denne indstilling bestemmer om NVDA automatisk skal annoncere nye symboler efterhånden som de kommer til syne i kompositionsstrengen.
Denne indstilling er slået til som standard.

#### Gennemsynstilstand {#BrowseModeSettings}

<!-- KC:setting -->

##### Åbn indstillinger for gennemsynstilstand {#OpenBrowseModeSettings}

Tast: `NVDA+control+b`

Denne kategori lader dig bestemme, hvordan NVDA skal håndtere navigation og læsning af komplekse dokumenter såsom en webside.
Indstillingskategorien indeholder følgende indstillinger:

##### Maximum antal tegn på én linje {#BrowseModeSettingsMaxLength}

Denne indstilling bestemmer længden på en linje i gennemsynstilstand (antal tegn).

##### Antal linjer pr. side {#BrowseModeSettingsPageLines}

Med dette felt kan du indstille, hvor mange linjer du springer ad gangen, når du trykker på Page-up og Page-down.

<!-- KC:setting -->

##### Brug skærmlayout {#BrowseModeSettingsScreenLayout}

Tast: NVDA+v

Med denne indstilling kan du vælge, om NVDA i gennemsynstilstand skal placere klikbart indhold som links, knapper og felter på hver sin linje, eller om de skal bevares som en del af den løbende tekst, sådan som det bliver vist på skærmen.
Bemærk, at denne indstilling ikke vil påvirke adfærden i Office-programmer herunder Word og Outlook. Disse vil altid benytte skærmlayout.
Hvis denne indstilling er slået til, vil hele sidens opbygning blive vist ligesom på skærmen.
Eksempelvis vil en visuel linje med flere links blive vist som en del af den samlede linje både i talestrømmen og på punktskrift.
Hvis indstillingen deaktiveres, vil ethvert element på siden blive vist på sin egen linje.
Dette kan gøre det nemmere for nogle brugere at navigere på websider.

##### Aktivér gennemsynstilstand ved sideindlæsning {#BrowseModeSettingsEnableOnPageLoad}

Denne check box lader dig vælge, om gennemsynstilstand skal aktiveres automatisk, når en side indlæses.
Når denne indstilling er deaktiveret, kan gennemsynstilstand stadig aktiveres i dokumenter eller på sider hvor tilstanden er understøttet.
Læs [afsnittet Gennemsynstilstand](#BrowseMode) for en liste over understøttede applikationer.
Bemærk, at denne indstilling ikke omfatter tilfæld, hvor gennemsynstilstand er valgfrit (f.eks. Microsoft Word).
Denne indstilling er slået til som standard.

##### Automatisk sig alt efter indlæsning af side {#BrowseModeSettingsAutoSayAll}

Med denne indstilling kan du slå automatisk læsning til og fra af sider, når de er blevet indlæst i gennemsynstilstand.
Denne indstilling er slået til som standard.

##### Inkluder layouttabeller {#BrowseModeSettingsIncludeLayoutTables}

Denne indstilling bestemmer, hvordan NVDA håndterer tabeller, som kun er lavet af hensyn til det visuelle layout.
Når den er slået til, vil NVDA håndtere disse tabeller som normale tabeller og indikere dem afhængigt af [Dokumentformateringsindstillinger](#DocumentFormattingSettings) og finde dem med hurtignavigeringskommandoer.
Når indstillingern er slået fra, vil layouttabeller ikke blive indikeret og ikke blive fundet med hurtignavigering.
Tabellernes indhold vil imidlertid stadig blive læst op som normal tekst.
Denne indstilling er slået fra som standard.

For at skifte denne indstilling fra hvor som helst, kan du tildele en tastaturkommando ved brug af [dialogen Håndter Kommandoer](#InputGestures)

##### Konfigurer annoncering af felter som links og overskrifter {#BrowseModeLinksAndHeadings}

Se venligst  [indstillingskategorien Dokumentformatering](#DocumentFormattingSettings) i [NVDAs indstillingsdialog](#NVDASettings) for at konfigurere rapportéring for felter så som links, overskrifter og tabeller.

##### Automatisk fokustilstand ved ændring af fokus {#BrowseModeSettingsAutoPassThroughOnFocusChange}

Denne funktion gør det muligt automatisk at fremkalde fokustilstand, når fokus ændrer sig.
Hvis du f.eks. befinder dig på en webside, trykker tab og lander i et formularfelt, skifter NVDA automatisk til fokustilstand, hvis denne indstilling er slået til.

##### Automatisk fokustilstand ved flytning af systemmarkør {#BrowseModeSettingsAutoPassThroughOnCaretMove}

Når denne indstilling er valgt, er det muligt at få NVDA til at skifte til og fra fokustilstand under flytning med piletasterne.
Hvis du fx flytter ned over en webside med pil-ned og NVDA støder på et editfelt, skifter NVDA automatisk til fokustilstand.
Når du med piletasterne bevæger dig ud af editfeltet, skifter NVDA automatisk tilbage til gennemsynstilstand.

##### Lydindikering af fokus- og gennemsynstilstand {#BrowseModeSettingsPassThroughAudioIndication}

Hvis denne indstilling er slået til, afspiller NVDA en særlig lyd i stedet for at oplæse ændringen.

##### Forhindre alle ikke-NVDA-kommandoer i at nå til dokumentet {#BrowseModeSettingsTrapNonCommandGestures}

med denne indstilling, som er slået til som udgangspunkt, kan du vælge om kommandobevægelser, f.eks. tastetryk, som ikke udgør en NVDA-kommando, og som ikke anses for at være en generel kommando, skal forhindres i at komme videre til det dokument, du har fokus på.
Hvis denne indstilling er slået til, og du f.eks. trykker på bogstavet j, vil tastetrykket blive forhindret i at komme videre til dokumentet, selv om det ikke er en kommando til hurtignavigation, og det heller ikke er sandsynligt, at det er en kommando i selve programmet.
I dette tilfæld vil NVDA få Windows til at afspille en standardlyde, hver gang en kommando forhindres i at nå dokumentet.

<!-- KC:setting -->

##### Placer automatisk systemfokus på fokuserbare elementer {#BrowseModeSettingsAutoFocusFocusableElements}

Tast: NVDA+8

Denne indstilling bestemmer om systemfokus automatisk skal flyttes til fokuserbare elementer der kan overtage systemfokus (formfelter, links, osv), når du navigerer indhold med gennemsynstilstand. Denne indstilling er deaktiveret som standard.
Ved at deaktivere denne indstilling vil elementer der er valgt med markøren i gennemsynstilstand ikke automatisk få fokus.
Dette kan resultere i hurtigere navigation på nettet og forekomme mere responsivt.
Fokus vil stadig blive opdateret, hvis du trykker på en knap, markere en check box, osv.
Aktivering af denne indstilling kan forbedre oplevelsen på nogle sider, men med risiko for ustabilitet og dårlig ydeevne.

#### Dokumentformatering {#DocumentFormattingSettings}

<!-- KC:setting -->

##### Åbn indstillinger for dokumentformatering {#OpenDocumentFormattingSettings}

Tast: `NVDA+control+d`

De fleste check boxe i denne indstillingskategori bruges til at angive, hvilke typer formatering, du ønsker oplæst automatisk, når du flytter markøren rundt inden i dokumenter.
Hvis du fx markerer check boxen "oplæs skrifttypenavn", hører du navnet på skrifttypen, hver gang du med piletasterne bevæger dig hen over tekst med en anden skrifttype.

Indstillingerne for dokumentformatering er organiseret i grupper.
Du kan tilpasse annoncering af:

* Skrifttype
  * Navn på skrifttype
  * Størrelse på skrifttype
  * Font attributes [(Off, Speech, Braille, Speech and braille)](#DocumentFormattingFontAttributes)
  * hævet og sænket skrift
  * fremhævelse
  * Fremhævet (markeret) tekst
  * Typografi
  * Farve
* Dokumentinformation
  * Kommentarer
  * Bogmærker
  * Redaktørændringer
  * Stavefejl
* Sider og linjeafstand
  * Sidetal
  * Linjenumre
  * Rapportering af linjeindrykning [(fra, tale, toner eller både tale og toner)](#DocumentFormattingSettingsLineIndentation)
  * Ignorer blanke linjer ved rapportering af linjeindrykning
  * Indrykning af afsnit (f.eks. hængende indrykning, indrykning af første linje)
  * Linjeafstand (enkelt, dobbel, osv.)
  * Justering
* Tabelinformation
  * Tabeller
  * Række- og kolonneoverskræfter (fra, rækker, kolonner, rækker og kolonner)
  * Cellekoordinater
  * Cellekanter (fra, typografier, både farver og typografier)
* Elementer
  * Overskrifter
  * Links
  * Grafik
  * Lister
  * Bloksitater
  * Grupper
  * Landmærker
  * Artikler
  * Rammer
  * Figurer og billedtekster
  * Klikbart

For at slå disse indstillinger til eller fra, uanset hvor du befinder dig, kan du knytte en bevægelse eller et tastetryk til indstillingen med [dialogen Håndter kommandoer](#InputGestures).

##### Font attributes {#DocumentFormattingFontAttributes}

This option allows you to select how certain font attributes, such as bold, italics, underline and strikethrough are reported.
The font attributes combo box has four options:

* Off: NVDA will not report these font attributes.
* Speech: NVDA will announce when these font attributes change.
* Braille: NVDA will display these attributes in braille.
Exactly how they are displayed can be configured in [NVDA's braille settings](#BrailleFormattingDisplay).
* Speech and braille: NVDA will report font attributes using both of the above methods.

##### Rapportér ændringer i formatering efter markøren {#DocumentFormattingDetectFormatAfterCursor}

Hvis denne indstilling er slået til, betyder det at NVDA forsøger at spore alle ændringer i formateringen på en linje, når den rapportérers, selvom dette måtte sænke NVDAs hastighed.

NVDA vil som standard spore ændringer i formateringen på markørens eller den ubegrænsede markørs position og af og til også på resten af linjen, med mindre hastigheden derved reduceres.

Slå denne funktion til ved korrekturlæsning af dokumenter i programmer som Wordpad, hvor formatering har betydning.

##### Rapportering af linjeindrykning {#DocumentFormattingSettingsLineIndentation}

Denne indstilling lader dig konfigurere hvordan linjeindrykning rapporteres.
Denne combo box har fire muligheder.

* Fra: NVDA ignorere rapportering af linjeindrykning.
* Tale: Hvis denne mulighed er valgt og indrykningen ændres, vil NVDA rapportere noget lignende "12 mellemrum" eller "4 tab."
* Toner: Hvis denne mulighed er valgt og indrykningen ændres, vil toner rapportere mængden af linjeindrykning.
Tonens toneleje vil forøges ved hvert mellemrum, og for tab vil tonen forøges fire mellemrum.
* Både Tale og Toner: Denne mulighed vil læse indrykningen ved brug af begge metoder.

Hvis du vælger boksen "Ignorer &blanke linjer ved rapportering af linjeindrykning", vil blanke linjer ikke blive oplyst for blanke linjer.
Dette kan være nyttigt, hvis du læser et dokument, hvor blanke linjer bruges til at adskille indrykkede blokke af tekst (f.eks. i kildekode til programmering).

#### Document Navigation {#DocumentNavigation}

Denne kategori lader dig justere forskellige indstillinger der anvendes, når du navigere rundt i dokumenter.

##### Navigering af afsnit {#ParagraphStyle}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Håndteret af det aktuelle program), Håndteret af det aktuelle program, Enkelt linjeskift, Flere linjeskift|
|Standard |Håndteret af det aktuelle program|

Disse indstillinger lader dig bestemme, hvordan du vil navigere gennem afsnit, når du bruger `Ctrl+pil op` og `ctrl+ pil ned`.
De tilgængelige indstillinger er følgende:

* Håndteret af det aktuelle program: NVDA vil lade programmet i brug bestemme, hvordan der navigeres mellem afsnit. NVDA vil læse det nye afsnit, når du navigere.
Denne indstilling fungere bedst, når selve programmet understøtter navigering mellem afsnit. Dette er standardindstillingen.
* Enkelt linjeskift: Med denne indstilling vil NVDA forsøge at gætte, hvornår et nyt afsnit begynder i en tekst. Dette gøres udelukkende ved brug af blanke linjer, der indsættes i en tekst ved brug af enter-tasten.
Denne indstilling fungerer bedst, når du læser et dokument i et program, der ikke selv understøtter navigering mellem afsnit, og hvor begyndelsen af et nyt afsnit indikeres ved tryk på `enter`.
* Flere linjeskift: NVDA vil selv forsøge at genkende, når der er afsnit i en tekst. Dette gøres ved hjælp af mindst én blank linje (to tryk på `enter-tasten`).
Denne indstilling fungerer bedst, når du arbejder med dokumenter, der anvender blokafsnit.
Bemærk, at du ikke kan benytte denne indstilling i Microsoft Word eller Outlook, hvis UIA ikke er aktiveret i NVDA-indstillingerne>Avanceret.

Du kan skifte mellem disse indstillinger fra hvor som helst, hvis du tilknytter en kommando til funktionen via [dialogen Håndter kommandoer](#InputGestures).

#### Indstillinger for Tilføjelsescenter {#AddonStoreSettings}

Denne kategori giver dig mulighed for at justere adfærden for Tilføjelsescenteret.

##### Opdateringsmeddelelser {#AutomaticAddonUpdates}

Når denne indstilling er indstillet til "Underret", vil Tilføjelsescenteret underrette dig efter NVDA opstart, hvis der er tilgængelige opdateringer til tilføjelser.
Denne kontrol udføres hver 24. time.
Underretninger vil kun forekomme for tilføjelser med tilgængelige opdateringer inden for samme kanal.
For eksempel vil du for installerede beta-tilføjelser kun blive underrettet om opdateringer inden for beta-kanalen.

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Underret (Standard), Deaktiveret |
|Standard |Underret |

|Indstilling |Adfærd |
|---|---|
|Underret |Underret, når der er tilgængelige opdateringer til tilføjelser inden for samme kanal |
|Deaktiveret |Kontrollér ikke automatisk for opdateringer til tilføjelser |

#### Windows Tekstgenkendelse {#Win10OcrSettings}

Indstillingerne i denne kategori lader dig konfigurere [Windows Tekstgenkendelse](#Win10Ocr).
Denne kategori indeholder følgende indstillinger:

##### Sprog til tekstgenkendelse {#Win10OcrSettingsRecognitionLanguage}

Denne combo box lader dig vælge det ønskede sprog til brugen af tekstgenkendelse.
For at skifte mellem tilgængelige sprog fra hvor som helst, tilknyt et tastetryk eller en bevægelse fra [dialogen Håndter Kommandoer](#InputGestures).

##### Opdater regelmæssigt genkendt indhold {#Win10OcrSettingsAutoRefresh}

Når denne indstilling er aktiveret, vil NVDA regelmæssigt opdatere indholdet, når du bruger tekstgenkendelse.
Dette kan være meget brugbart, når du vil holde øje med tekst, der løbende ændres. Dette kan være, at du ser en video med undertekster.
Teksten opdateres hvert halvanden sekund.
Denne indstilling er som standard slået fra.

#### Avancerede Indstillinger {#AdvancedSettings}

Advarsel! Indstillingerne i denne kategori gælder for avancerede brugere. Hvis du ændrer disse, kan NVDA fungere uhensigtsmæssigt.
Du skal kun ændre disse, hvis du ved hvad du laver eller er specifikt instrueret af NVDA-udviklere.

##### Ændring af avancerede indstillinger {#AdvancedSettingsMakingChanges}

for at foretage ændringer af avancerede indstillinger, skal du bekræfte ved at markere boksen at du forstår risikoen ved at ændre disse indstillinger.

##### Gendan standardindstillingerne {#AdvancedSettingsRestoringDefaults}

Knappen gendanner standardværdierne for disse indstillinger. Dette gælder også, selv hvis boksen ikke er markeret.
Når du har lavet dine ændringer vil du måske gerne vende tilbage til standardindstillingerne på et senere tidspunkt.
Dette kan også være tilfældet, hvis du er usikker og ikke ved om indstillingerne er blevet ændret.

##### Tillad indlæsning af tilpasset kode fra mappen Developer Scratchpad {#AdvancedSettingsEnableScratchpad}

Når du udvikler kode for en NVDA-tilføjelse, så er det nyttigt at have muligheden for at afprøve din kode, når du skriver den.
Denne indstilling, hvis slået til, lader dig indlæse tilpasset appModules, globalPlugins, brailleDisplayDrivers, synthDrivers og synsoptimeringsdriver fra en særlig mappe ved navn "Developer Scrachpad" i konfigurationsmappen for din bruger af NVDA.
Ved opstart af NVDA indlæses disse moduler som deres tilsvarende tilføjelser. AppModules og GlobalPlugins indlæses dog kun, når der genindlæses tilføjelsesprogrammer ved hjælp af kommandoen [Genindlæs plugins](#ReloadPlugins).
Denne indstilling er slået fra. Dette vil sikre, at ingen kode kan køres uden brugerens samtykke.
Hvis du ønsker at distribuere kode til andre, skal du gøre dette som en tilføjelsespakke.

##### Åbn mappen Developer Scratchpad {#AdvancedSettingsOpenScratchpadDir}

Denne knap åbner mappen vor du kan placere din kode under udvikling.
Denne knap vil kun være tilgængelig, hvis NVDA tillader indlæsning af tilpasset kode.

##### Registrer hændelser fra UI Automation samt egenskabsændringer {#AdvancedSettingsSelectiveUIAEventRegistration}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Automatisk, selektivt, globalt|
|Standard |Automatisk|

Denne indstilling ændre, hvordan NVDA registrere og behandler hændelser fra UI Automation Accessibility API.
Denne indstilling har tre muligheder:

* Automatisk: "Selektiv"  Windows 11 Sun Valley 2 (version 22H2) og nyere, "global" benyttes i alle andre tilfælde.
* Selektivt: NVDA vil begrænse registreringen af hændelser til systemfokus i de fleste tilfælde.
Hvis du oplever, at NVDA forekommer langsom, kan du slå denne indstilling til for at se om ydeevnen forbedres.
Der kan dog forekomme problemer med at spore det aktuelle fokus ved brug af bestemte kontrolelementer, når du kører en ældre version af Windows (f.eks. joblisten og emoji-panelet).
* Globalt: NVDA registrerer mange UIA-hændelser, der behandles og kasseres i selve NVDA.
Sporing af fokus kan være mere pålideligt i de fleste tilfælde, men dette har en meget negativ indflydelse på ydelsen, særligt i programmer som Microsoft Visual Studio.

##### Benyt UI Automation til at få adgang til kontrolelementer for Microsoft Word-dokumenter {#MSWordUIA}

Dette bestemmer om NVDA skal benytte UI Automation Accessibility API til at få adgang til Microsoft Word-dokumenter i stedet for den gamle Microsoft Word objektmodel.
Dette omfatter dokumenter åbnet i Microsoft Word og meddelelser i Microsoft Outlook.
Indstillingen indeholder følgende muligheder:

* Standard (Hvor det er passende)
* Kun hvis det er nødvendigt: Bruges i tilfælde, hvor Microsoft Word objektmodellen ikke kan benyttes
* Hvor det er passende: Microsoft Word version 16.0.15000 eller nyere, eller når Microsoft Word objektmodellen ikke er tilgængelig
* Altid: Denne mulighed vil benytte UI Automation i Microsoft Word i ethvert tilfælde, selv når understøttelsen for UI Automation ikke er fuldstændig.

##### Benyt UI Automation til at få adgang til kontrolelementer for Microsoft Excel-regneark, når det er tilgængeligt {#UseUiaForExcel}

Når denne indstilling er aktiveret, vil NVDA forsøge at bruge Microsoft UI Automation tilgængeligheds API for at hente information fra Microsoft Excel-regnearkskontroller.
Dette er en eksperimentel funktion, og nogle funktioner i Microsoft Excel er muligvis ikke tilgængelige i denne tilstand.
Nogle af disse utilgængelige funktioner er elementlisten, der viser fformler og kommentarer, samt gennemsynstilstand, der tillader dig at hoppe til formularfelter i et regneark.
Dog kan denne mulighed for grundlæggende regnearksnavigation/redigering give en betydelig ydelsesforbedring.
Vi anbefaler stadig ikke, at flertallet af brugere aktiverer dette som standard, selvom vi byder brugere af Microsoft Excel build 16.0.13522.10000 eller højere velkommen til at teste denne funktion og give feedback.
Microsoft Excels UI-automatiseringsimplementering ændres konstant, og versioner af Microsoft Office ældre end 16.0.13522.10000 eksponerer muligvis ikke nok information til, at denne mulighed er af nogen nytte.

##### Brug forbedret hændelsesbehandling {#UIAEnhancedEventProcessing}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Aktiveret), Deaktiveret, Aktiveret|
|Standard |Aktiveret|

Når dette er aktiveret, burde NVDA blive ved med at reagere, selv når der modtages mange hændelser fra UI Automation, som f.eks. i terminalvinduer.
Når du ændre denne indstilling, skal du genstarte NVDA.

##### Understøttelse af Windows-konsol {#AdvancedSettingsConsoleUIA}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Automatisk, UIA, når dette er tilgængeligt, Forældet|
|Standard |Automatisk|

Denne indstilling bestemmer, hvordan NVDA interagerer med Windows-konsollen, der bruges af kommandoprompt, PowerShell og Windows Subsystem for Linux.
Dette påvirker ikke den moderne Windows Terminal.
I Windows 10 version 1709 [tilføjede Microsoft understøttelse af sin UI Automation API til konsollen https://devblogs.microsoft.com/commandline/whats-new-in-windows-console-in-windows-10-fall-creators-](update/), hvilket betyder en markant forbedret ydeevne og stabilitet med skærmlæsere, der understøtter dette.
I situationer, hvor UI Automation er utilgængelig eller kendt for at resultere i en dårligere brugeroplevelse, er NVDAs forældede konsolsupport tilgængelig som en reservemetode.
Boksen har tre muligheder:

* Automatisk: Bruger UI Automation i versionen af Windows-konsollen, der følger med Windows 11 version 22H2 og nyere.
Denne indstilling anbefales og indstilles som standard.
* UIA, når dette er tilgængeligt: Bruger UI Automation  i konsoller, hvis det er tilgængeligt, selv for versioner med ufuldstændige eller fejlagtige implementeringer.
Selvom denne begrænsede funktionalitet kan være nyttig (og endda tilstrækkelig til dit brug), er brugen af denne mulighed helt på egen risiko, og der vil ikke blive ydet support til den.
* Forældet: UI Automation i Windows-konsollen vil være fuldstændig deaktiveret.
Den gamle reservemetode  vil altid blive brugt selv i situationer, hvor UI Automation ville give en betydeligt bedre brugeroplevelse.
Derfor anbefales det ikke at vælge denne mulighed, medmindre du ved, hvad du laver.

##### Brug UIA med Microsoft Edge og andre Chromium-baserede browsere, hvis muligt {#ChromiumUIA}

Denne indstillinger lader dig vælge, hvorvidt UIA bliver benyttet, når du bruger en Chromium-baseret browser som Microsoft Edge.
Understøttelse af UIA for disse browsere er i begyndelse af udviklingsfasen, og vil derfor muligvis ikke give samme form for tilgængelighed som IA2.
Du kan vælge følgende indstillinger:

* Standard (kun når dette er nødvendigt): Dette er standardindstillingen. Dette vil muligvis ændres eftersom teknologien udvikler sig.
* Kun når dette er nødvendigt: Hvis NVDA ikke kan forbinde til browserprocessen for at bruge IA2 vil UIA automatisk benyttes, hvis UIA er tilgængeligt.
* Ja: Hvis browseren gør UIA tilgængeligt, vil NVDA bruge dette.
* Nej: Brug ikke UIA, selv hvis NVDA ikke kan forbinde sig selv med processen. Dette kan være nyttigt, hvis udviklere er i færd med at problemløse IA2 og vil sikre sig, at NVDA ikke benytter UIA.

##### Annotationer {#Annotations}

Denne gruppe af indstillinger bruges til at aktivere eksperimentel understøttelse af ARIA-annotationer.
Nogle af disse funktioner er ufuldstændige.

<!-- KC:beginInclude -->
For at få et sammendrag af eventuelle annoteringsdetaljer ved systemmarkøren, tryk NVDA+d.
<!-- KC:endInclude -->

Følgende indstillinger er tilgængelige:

* Oplys "har detaljer" for strukturerede annoteringer: Denne indstilling giver besked, hvis et objekt har yderligere detaljer i gennemsynstilstand.
* Oplys altid aria-beskrivelse:
  Når kilden af `accDescription` er aria-description, vil beskrivelsen blive oplyst.
  Dette er brugbart for annotationer på internettet.
  Bemærk:
  * Der er mange kilder for `accDescription`, hvor flere har blandede eller upålidelig semantik.
    Historisk set, så har hjælpeteknologier ikke været i stand til at kende forskel på diverse kilder for `accDescription`. Typisk blev dette ignoreret, navnligt pga. af de upålidelige kilder.
  * Denne funktion er under meget tidlig udvikling, hvilket betyder, at funktionaliten ikke er bredt tilgængelig i alle browsere.
  * Denne funktionalitet forventes at virke med Chromium 92.0.4479.0+

##### Oplys live-områder {#BrailleLiveRegions}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Aktiveret) Deaktiveret, aktiveret|
|Standard |Aktiveret|

Denne indstilling bestemmer om NVDA skal vise opdateringer af dynamisk webindhold på punkt.
Denne indstilling svarer til adfærden i NVDA 2023.1 og tidligere, hvor disse opdateringer kun blev oplyst via tale.

##### Udtal adgangskoder i alle forbedrede konsoller {#AdvancedSettingsWinConsoleSpeakPasswords}

Denne funktion bestemmer om tegn udtales ved brug af indstillingen [sig indtastede tegn](#KeyboardSettingsSpeakTypedCharacters) eller [sig indtastede ord](#KeyboardSettingsSpeakTypedWords). Dette kan evt. være nyttigt i situationer hvor skærmen ikke opdateres (som ved indtastning af adgangskoder i konsolvinduer), i nogle terminalprogrammer som Windows-konsollen med understøttelse for UIA aktiveret og Mintty.
På grund af sikkerhedsårsager bør denne indstilling forblive deaktiveret.
Du kan dog ønske at aktivere indstillingen, hvis du oplever problemer med udtale af indtastede ord og tegn eller arbejder i et sikkert miljø.

##### Benyt forbedret understøttelse af indtastede tegn i forældede Windows-konsoller, når denne er tilgængelig {#AdvancedSettingsKeyboardSupportInLegacy}

Denne indstilling aktivere en alternative metode til at opdage indtastede tegn i forældede Windows-konsoller.
Selvom denne indstilling kan forbedre ydeevnen og forhindre at noget konsolindhold staves, kan denne indstilling forekomme inkompatibel med nogle terminalprogrammer.
Denne funktion kan aktiveres i Windows 10 version 1607 og nyere versioner af Windows 10, hvor UI Automation ikke er tilgængelig.
Advarsel: Med denne indstilling aktiveret vil indtastede tegn, der ikke vises på skærmen såsom adgangskoder ikke blive undertrykket.
I usikre miljøer, kan du midlertidigt deaktivere [sig indtastede tegn](#KeyboardSettingsSpeakTypedCharacters) og [sig indtastede ord](#KeyboardSettingsSpeakTypedWords) under indtastning af adgangskoder.

##### Diff-algoritme {#DiffAlgo}

Denne indstilling styrer, hvordan NVDA skal bestemme teksten, der skal udtales i terminaler.
Der er følgende indstillinger:

* Automatisk: Denne mulighed gør at NVDA vil foretrække Diff Match Patch i de fleste tilfælde. I problematiske programmer vil NVDA falde tilbage på Difflib, såsom ældre versioner af Windows-konsolprogrammer og Mintty.
* Diff Match Patch: Denne mulighed får NVDA til at beregne ændringer i terminaltekst efter tegn, selv hvis dette ikke forekommer hensigtsmæssigt.
Dette kan forbedre ydelsen, når der skrives store mængder tekst til konsollen, og muliggøre mere nøjagtig rapportering af ændringer foretaget midt på linierne.
Indstillingen kan dog i nogle tilfælde forårsage, at læsning af ny tekst i programmet vil blive oplæst på en uhensigtsmæssig måde. Læsningen af den nye tekst kan forekomme inkonsekvent eller som om at talen hakker.
* Difflib: Denne indstilling får NVDA til at beregne ændringer til terminalens tekst pr. linje.
Dette er identiskt med NVDAs adfærd i NVDA 2020.4 og tidligere.
Indstillingen kan forbedre læsning af ny tekst i nogle tilfælde.
Dette vil dog gøre, at teksten foran systemmarkøren vil blive læst, når du indsætter eller sletter tekst midt på en linje i terminaler.

##### Sig ny tekst i Windows-terminaler via {#WtStrategy}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Diffing), UIA-meddelelser|
|Standard |Diffing|

Denne indstilling bestemmer, hvordan NVDA skal opfatte teksten i et terminalvindue som "ny" (og henholdsvis, hvad der skal læses op, når indstillingen "Dynamisk indhold" er slået til) i Windows Terminal og WPF Windows Terminal brugt i Visual Studio 2022.
Det påvirker ikke adfærden i Windows-konsollen (`conhost.exe`).
Der er tre muligheder:

* Standard: Denne indstilling er i øjeblikket det samme som "diffing", men dette formodes at blive ændret, når udviklingen af UIA-meddelelser er skredet længere frem.
* Diffing: Denne indstilling benytter den valgte diff-algoritme til at kalkulere ændringerne, hver gang terminalen gengiver den nye tekst.
Dette er identisk med NVDAs adfærd i 2022.4 og ældre.
* UIA-meddelelser: Denne mulighed gør, at Windows-terminalen bestemmer, hvilken tekst der anses som "ny".
Dette skulle markant forbedre ydeevnen og stabiliteten af Windows Terminal, men denne funktion er endnu ikke færdig.
Især indskrevne tegn, der ikke vises på skærmen (såsom adgangskoder) rapporteres, når denne indstilling er valgt.
Dette kan dog medføre, at lange output af tekst på over 1.000 tegn muligvis ikke oplæses nøjagtigt.

##### Forsøg at annullere tale for udløbne fokushændelser {#CancelExpiredFocusSpeech}

Denne indstilling gør det muligt for NVDA at forsøge på at annullere tale for udløbne fokushændelser
Som et eksempel kan hurtig navigation gennem GMail i Chrome forårsage, at NVDA oplæser forældede  informationer.
Denne indstilling er automatisk aktiveret som standard i NVDA 2021.1.

##### Interval for markøren (i MS) {#AdvancedSettingsCaretMoveTimeout}

Denne indstilling lader dig konfigurere hvor mange millisekunder NVDA skal vente på systemmarkøren (indsættelsesmarkøren) i redigerbare tekstfelter.
Hvis du opdager, at NVDA har problemer med at følge systemmarkøren (f.eks. hvis NVDA konsekvent er et tegn bagud eller gentager linjer), kan du forøge denne værdi.

##### Oplys gennemsigtige farveværdier {#ReportTransparentColors}

Denne indstilling lader NVDA oplyse, når farver er gennemsigtige. Dette er brugbart, hvis man er ved at udvikle en tilføjelse eller et app-modul, der har til hensigt at forbedre brugeroplevelsen for tredjepartsprogrammer.
Nogle GDI-applikationer vil fremhæve tekst med en baggrundsfarve. NVDA (via display model) vil forsøge at oplyse farven.
I nogle tilfælde kan det være, at tekstens baggrund er fuldstændig gennemsigtig, hvor selve teksten befinder sig i lag på et andet gui-element.
Med flere historisk populære GUI API'er kan teksten gengives med en gennemsigtig baggrund, men visuelt er baggrundsfarven nøjagtig.

##### Brug WASAPI til lydoutput {#WASAPI}

| . {.hideHeaderRow} |.|
|---|---|
|Muligheder |Standard (Aktiveret) Deaktiveret, Aktiveret|
|Standard |Aktiveret|

Denne indstilling muliggør lydoutput via Windows Audio Session API (WASAPI).
WASAPI er en mere moderne lydteknologi, der kan forbedre reaktionsevne, ydeevne og stabilitet for NVDA-lydoutput, herunder både tale og lydeffekter.
Efter ændring af denne indstilling skal du genstarte NVDA, for at ændringen træder i kraft.
Hvis du deaktiverer WASAPI, vil følgende indstillinger blive deaktiveret:

* [ Lydstyrke af NVDA-lyde følger stemmelydstyrken](#SoundVolumeFollowsVoice)
* [Lydstyrke for NVDA-lyde](#SoundVolume)

##### Aktiverede logningskategorier {#AdvancedSettingsDebugLoggingCategories}

Check boxene i denne liste lader dig vælge, hvilke logningskategorier der skal benyttes under skrivning af NVDAs logfil.
Logning af disse hændelser kan resultere i lavere ydeevne og store logfiler.
Slå kun dette til, hvis du er blevet bedt om det af en NVDA-udvikler (f.eks. for at finde ud af, hvorfor et punktdisplay ikke fungere som forventet).

##### Afspil en lyd, når fejl opstår {#PlayErrorSound}

Denne indstilling lader dig vælge om NVDA skal afspille en lyd, når fejl logføres.
Ved at vælge "Kun i testversioner af NVDA", vil NVDA kun afspille lyden, hvis din version er en testversion (alpha, beta eller NVDA køres fra kildekoden). Denne indstilling er standard.
Ved at vælge "Ja" vil en lyd afspilles, uanset din version af NVDA.

##### Regulært udtryk, der bruges, når kommandoerne til at springe mellem tekstafsnit benyttes i gennemsynstilstand {#TextParagraphRegexEdit}

Dette tekstfelt lader brugere bestemme, hvilket regulære udtryk, der skal anvendes, når der søges efter tekstafsnit i gennemsynstilstand ved brug af de tilsvarende kommandoer.
[Kommandoen til at navigere mellem tekstafsnit](#TextNavigationCommand) vil benytte dette udtryk.

### Yderligere indstillinger {#MiscSettings}

Udover [NVDAs indstillingsdialog](#NVDASettings), indeholder menuen "Opsætning" under NVDA-menuen yderligere indstillinger, der beskrives nedenfor.

#### Udtaleordbøger {#SpeechDictionaries}

Menuen Udtaleordbøger, som findes i menuen Opsætning, indeholder dialogbokse, der giver mulighed for at styre,  hvordan NVDA udtaler bestemte ord eller tekstbidder.
Der er i øjeblikket 3 typer af udtaleordbøger.
Disse er:

* Standard: Reglerne i denne ordbog gælder for al tale i NVDA.
* Stemme: Regler i denne ordbog gælder for den talesyntesestemme, der i øjeblikket er i brug.
* Midlertidig: Regler i denne ordbog gælder for al tale i NVDA, dog kun for den aktuelle session. Disse regler er midlertidige og forsvinder, næste gang NVDA genstartes.

Du kan tilknytte kommandoer med [dialogen Håndter Kommandoer](#InputGestures), hvis du gerne vil have let adgang til at kunne åbne disse ordbøger fra hvor som helst.

Alle ordbogsdialogerne indeholder en liste med regler, som bruges under behandling af talen.
Dialogboksen indeholder også knapperne Tilføj, Redigér, Fjern og Fjern alle.

For at tilføje en ny regel til ordbogen skal du  vælge knappen Tilføj, udfylde felterne i den dialogboks, der fremkommer, og derefter trykke Ok.
Den nye regel vises derefter i regellisten.
Men for at være helt sikker på, at din regel virkelig bliver gemt, skal du trykke Ok for at lukke ordbogsdialogen helt, når du er færdig med at tilføje/redigere regler.

Med reglerne i NVDAs udtaleordbøger kan du lave tegnene i en tekststreng om til nogle andre.
Et enkelt eksempel kunne være, at du ville have, at NVDA sagde ordet frø hver gang der stod fugl.
Den nemmeste måde at gøre det på, er at skrive ordet fugl i dialogboksen Tilføj regel i feltet Mønster, og derefter at skrive ordet frø i feltet Erstatning.
Du kan også lave en beskrivelse af reglen i feltet Kommentar (som fx: ændrer fugl til frø).

NVDAs udtaleordbøger er imidlertid langt mere righoldige på muligheder end blot at kunne erstatte tekst.
Dialogen "Tilføj regel" indeholder også en check box til at bestemme, om du ønsker reglen skal være følsom for store og små bogstaver (altså om NVDA skal gøre forskel på, om bogstaverne er store eller små.
NVDA gør som standard ikke forskel på store og små bogstaver).

Endelig er der et sæt radioknapper, som du kan bruge til at fortælle NVDA, hvorvidt dit søgemønster skal gælde overalt, om det kun skal bruges som et helt ord, eller om det skal behandles som et regulært udtryk (regular expression).
Hvis du sætter mønsteret til kun at gælde for hele ord, betyder det, at mønsteret kun vil blive erstattet, hvis mønstret ikke forekommer som en del af et længere ord.
Dette er eksempelvis tilfældet, hvis de tegn, der kommer før eller efter, ikke er et bogstav, alfanumerisk tegn eller et understregningstegn eller hvis der ingen tegn er tilstede som en del af mønstret.
Hvis du med eksemplet fra før vil erstatte ordet "fugl" med "frø", og det kun skulle gælde som et helt ord, ville det ikke komme til at gælde ord som "fugle" eller "sommerfugl".

Et regulært udtryk er en række af specielle symboler, som sætter dig i stand til at søge på mere end et tegn ad gangen, at søge udelukkende på tal eller udelukkende på bogstaver for blot at nævne nogle få eksempler.
Regulære udtryk bliver ikke beskrevet nærmere i denne brugervejledning.
For en introduktion til regulære udtryk, læs [Python's Regular Expression Guide](https://docs.python.org/3.11/howto/regex.html).

#### Udtale af sætningstegn og symboler {#SymbolPronunciation}

Denne dialog giver dig mulighed for at bestemme, hvordan sætningstegn og andre symboler skal udtales, samt på hvilket niveau de skal udtales.

Det sprog, som du redigerer udtale af symboler for, bliver vist i dialogens titellinje.
Bemærk, at denne dialog følger indstillingen "Brug stemmens sprog til behandling af symboler og tegn", som kan findes i [indstillingskategorien Stemme](#SpeechSettings) i [NVDAs indstillingsdialog](#NVDASettings); D.v.s., den bruger den aktuelle stemmes sprog og ikke NVDAs globale sprog, når denne indstilling er slået til.

For at ændre et symbol, skal du først vælge det i listen med symboler.
Du kan filtrere listen ved at indtaste symbolet eller en del af symbolets erstatning i det tilsvarende felt.

* I feltet erstatning, kan du skrive den tekst du vil have læst i stedet for det oprindelige symbol.
* I feltet niveau, kan du justere det laveste symbolniveau dette symbol skal udtales ved (ingen, nogle, flere eller alle).
Du kan også indstille niveauet til "tegn". I dette tilfælde bliver symbolet ikke oplæst uanset symbolniveau, medmindre følgende er aktuelt:
  * Når du navigerer tegn for tegn
  * Når NVDA staver tekst, hvor symbolet fremkommer
* Med feltet "Send selve symbolet til talesyntese" kan du specificere, hvornår symbolet selv, i modsætning til erstatningsteksten, skal sendes til talesyntesen.
Dette kan være nyttigt, hvis tegnet får talesyntesen til at holde en pause eller ændre på tonehøjden.
F.eks., et komma kan få talesyntesen til at holde en pause.
Der er tre muligheder:
  * Aldrig: Send aldrig selve symbolet til talesyntesen.
  * Altid: Send altid selve symbolet til talesyntesen.
  * Kun under symbolets niveau: Send kun det aktuelle symbol, hvis det indstillede symbolniveau er lavere end symbolets niveau.
  Du kan f.eks. bruge dette til at få erstatningsteksten for et symbol udtalt uden pause ved højtesymbolniveauer og stadig få indikeret symbolet ved hjælp af en pause på lavere niveauer.

Du kan tilføje nye symboler ved at trykke på Tilføj-knappen.
I den dialog, som fremkommer, skal du indtaste symbolet og trykke på Enter.
Du kan så  ændre felterne for det nye symbol, præcist som med andre symboler.

Du kan fjerne et symbol, som du tidligere har tilføjet, ved at trykke på Fjern-knappen.

Når du er færdig, skal du trykke på OK-knappen for at gemme dine ændringer, eller Annuller-knappen for at kassere dem.

I tilfælde af komplekse symboler skal feltet Erstatning muligvis omfatte nogle gruppereferencer for den matchede tekst. F.eks. et mønster, der skal matche til en hel dato, vil det være nødvendigt at inkludere \1, \2, og \3 i feltet, hvorefter erstatningen ville blive ændret til den tilsvarende del af den pågældende dato.
Normale omvendte skråstreger (\) skal derfor skrives to gange, f.eks. "a\\b" skal indtastes for at få "a\b" erstattet.

#### Håndter Kommandoer {#InputGestures}

I denne dialog kan du tilpasse kommandoer for de forskellige NVDA-funktioner (taster på tastaturet, knapper på et punktdisplay osv.)

Du får kun vist de kommandoer, som er tilgængelige på det tidspunkt, hvor du åbner dialogen.
Hvis du fx. vil tilpasse kommandoer til gennemsynstilstand, skal du åbne dialogen, mens NVDA er i gennemsynstilstand.

Trævisningen i denne dialog viser alle de tilgængelige NVDA-kommandoer grupperet efter kategori.
Du kan filtrere dem ved at indtaste et eller flere ord fra kommandoens navn i editfeltet "Filtrer efter" i en hvilken som helst rækkefølge.
Hvis en kommando er tilknyttet en bevægelse eller tastaturkommando, bliver den vist neden under kommandoen.

For at tilføje en bevægelse eller et tastetryk til en kommando skal du vælge kommandoen og så trykke på Tilføj-knappen.
Derefter skal du udføre den tilsvarende handling, du vil knytte til kommandoen, fx. trykke på en tast på tastaturet eller en knap på punktdisplayet.
Ofte kan en bevægelse eller et tastetryk fortolkes på mere end én måde.
I det tilfælde kommer der en menu til syne, hvor du kan vælge den mulighed, du vil have.
Hvis du fx. trykker på en tast på tastaturet, kan det være, at tastetrykket skal være specifikt for enten Desktop-layout eller laptop-layout eller gælde for alle tastatur-layouts.

Hvis du vil fjerne et tastetryk eller bevægelse fra en kommando, så vælg den pågældende kommando og tryk på Fjern-knappen.

Kategorien "Emulerede tastaturtryk" indeholder kommandoer, der lader dig emulere almindelige tastaturtryk.
Disse kommandoer kan benyttes til at kontrollere systemets tastatur direkte fra dit punktdisplay.
For at tilføje en af disse taster, kan du vælge ovennævnte kategori og vælge "Tilføj".
Herefter skal du trykke den tast, som du ønsker at emulere.
Den emulerede tast vil herefter vises i kategorien "Emulerede tastaturtryk" og du kan tildele en kommando som beskrevet ovenfor.

Bemærk:

* Emulerede tastaturtryk skal have en kommando tildelt, før du kan gemme dine indstillinger.
* En kommando der benytter en funktionstast kan ikke tildeles et emuleret tastaturtryk uden funktionstast.
F.eks. hvis man indstiller det emulerede tastaturtryk `A` til kommandoen `Control+M`, ville dette forårsage atprogrammet kun modtager `Control+A`.

Når du er færdig med dine ændringer, så tryk OK for at gemme dem eller Annuller for at kassere dem.

### Gemme og genindlæse  konfigurationen {#SavingAndReloading}

Som standard gemmer NVDA dine indstillinger automatisk.
Du skal dog være opmærksm på, at denne indstilling kan ændres under de generelle indstillinger i menuen Indstillinger.
Ved at aktivere "Gem konfiguration" i NVDAs hovedmenu, kan du altid gemme dine indstillinger manuelt.

Hvis du laver fejl i dine indstillinger og ønsker at vende tilbage til de gemte indstillinger, vælger du "Vend tilbage til gemt konfiguration" i NVDAs hovedmenu.
Du kan også nulstille dine indstillinger til de oprindelige fabriksindstillinger ved at vælge dette menupunkt under NVDA-menuen.

Følgende NVDA-genvejstaster kan være nyttige:
<!-- KC:beginInclude -->

| Navn |Desktop-tast |Laptop-tast |Beskrivelse|
|---|---|---|---|
|Gem konfiguration |NVDA+Ctrl+c |NVDA+Ctrl+c |Gemmer dine aktuelle indstillinger, så de ikke går tabt, når du afslutter NVDA|
|Vend tilbage til konfiguration |NVDA+Ctrl+r |NVDA+Ctrl+r |Gendanner de indstillinger, som NVDA havde, da du senest gemte NVDAs konfiguration|

<!-- KC:endInclude -->

### Indstillingsprofiler {#ConfigurationProfiles}

Nogle gange kan det være praktisk at have NVDA indstillet forskelligt i forskellige situationer.
Det kan fx. være, at du vil have annoncering af indrykning slået til, mens du skriver og annoncering af skrifttype slået til, mens du læser korrektur.
Med NVDA kan du gøre dette ved hjælp af indstillingsprofiler.

En indstillingsprofil indeholder kun de ændringer, som du laver, mens du tilpasser profilen.
De fleste indstillinger kan ændres i en indstillingsprofil, undtagen dem, som findes i indstillingskategorien "Generelt" i [NVDAs indstillingsdialog](#NVDASettings). Disse indstillinger gælder for hele NVDA.

indstillingsprofiler kan aktiveres manuelt fra en dialog eller via tildelte kommandoer.
De kan også aktiveres automatisk ved hjælp af en såkaldt udløser såsom at skifte til et bestemt program.

#### Grundlæggende styring {#ProfilesBasicManagement}

Du kan styre indstillingsprofiler ved at vælge menupunktet indstillingsprofiler i NVDA-menuen.
Du kan også gøre dette ved hjælp af en tastaturkommando:
<!-- KC:beginInclude -->

* NVDA+Ctrl+p: Vis dialogen indstillingsprofiler

<!-- KC:endInclude -->

Det første felt i denne dialog er en liste, hvor du kan vælge en af profilerne.
Når du åbner dialogen, er den profil, som du i øjeblikket redigerer, i fokus.
Der bliver også vist yderligere oplysninger om andre profiler. Du kan se, om de bliver aktiveret manuelt eller via en udløser, og om de er ved at blive ændret.

Hvis du vil omdøbe eller slette en profil, skal du trykke på henholdsvis Omdøb- eller Sletknappen.

Tryk på Luk-knappen for at lukke dialogen.

#### Opret en profil {#ProfilesCreating}

Hvis du vil oprette en profil, så tryk på Ny-knappen.

I Ny-dialogen kan du indtaste et navn på profilen.
Du kan også vælge, hvordan profilen skal bruges.
Hvis du kun vil bruge profilen manuelt, skal du vælge "manuel aktivering", hvilket iøvrigt er standard.
Ellers kan du vælge en udløser, som skal aktivere profilen automatisk.
For nemheds skyld, hvis du ikke har givet profilen et navn, vil den automatisk blive tildelt et passende navn, når du vælger en udløser.
Se [nedenfor](#ConfigProfileTriggers) for flere oplysninger.

Når du trykker OK, bliver profilen oprettet, og dialogen indstillingsprofiler bliver lukket, så du kan tilpasse profilen.

#### Manuel aktivering {#ConfigProfileManual}

Du kan aktivere en profil manuelt ved at vælge profilen og trykke på knappen "manuel aktivering".
Når profilen er aktiveret, kan andre profiler stadigvæk blive aktiveret automatisk på grund af en udløser, men indstillinger i den profil, du har aktiveret manuelt, vil overtrumfe de andre.
For eksempel, hvis en profil er tilknyttet det aktuelle program, og annoncering af links er slået til i den profil, men slået fra i den manuelt aktiverede profil, vil links ikke blive annonceret.
Hvis du imidlertid har ændret stemmen i den automatiske profil, men ikke i den manuelle profil, vil stemmen i den automatiske profil blive brugt.
De indstillinger, du ændrer, vil blive gemt i den manuelle profil.
Hvis du vil deaktivere en profil, som du har aktiveret manuelt, så vælg profilen i dialogen indstillingsprofiler, og tryk på knappen "Manuel deaktivering".

#### Udløsere {#ConfigProfileTriggers}

Ved at trykke på knappen Udløsere i dialogen indstillingsprofiler kan du komme til at redigere de profiler, som skal aktiveres ved hjælp af forskellige udløsere.

Listen viser de udløsere, som du kan bruge, nemlig:

* aktuelle program: Bliver udløst, når du skifter til det aktuelle program.
* Sig alt: Bliver udløst når du udfører "Sig alt"-kommandoen.

For at vælge hvilken profil der skal aktiveres automatisk af en udløser skal du først vælge en udløser og derefter vælge en profil fra profillisten.
Du kan vælge (standardkonfiguration), hvis du ikke vil bruge nogen speciel profil.

Tryk på Luk-knappen for at komme tilbage til dialogen indstillingsprofiler.

#### Rediger en profil {#ConfigProfileEditing}

Hvis du har aktiveret en profil manuelt, vil alle de ændringer, du foretager, blive gemt i denne profil.
Ellers vil de indstillinger, du ændrer, blive gemt i den profil, der sidst er blevet aktiveret af en udløser.
For eksempel, hvis du har knyttet en profil til Notesblok-programmet, og du skifter til Notesblok, vil alle de indstillinger, du ændrer, blive gemt i denne profil.
Endelig, hvis der ikke er aktiveret nogen speciel profil, hverken manuelt eller via en udløser, vil de indstillinger, du ændrer, blive gemt i standardkonfigurationen.

Hvis du vil ændre i den profil, som er tilknyttet "Sig alt"-kommandoen, skal du [manuelt aktivere ](#ConfigProfileManual) profilen.

#### Slå udløsere fra midlertidigt {#ConfigProfileDisablingTriggers}

En gang imellem kan det være nyttigt at kunne slå alle udløsere fra.
Det kan fx. være, hvis du vil redigere en manuelt aktiveret profil eller standardkonfigurationen uden at blive forstyrret af automatiske profiler.
Du kan gøre dette ved at markere check boxen "Slå alle udløsere fra midlertidigt" i dialogen indstillingsprofiler.

For at slå udløsere fra hvor som helst, tildel et tastetryk ved at benytte [dialogen kommandoer](#InputGestures).

#### Aktivering af profiler ved brug af tastaturkommandoer {#ConfigProfileGestures}

For hver indstillingsprofil du opretter, kan du herefter tildele en tastaturkommando til at aktivere den fra hvor som helst.
Som standard har ingen indstillingsprofil tildelte kommandoer.
Du kan tildele tastaturkommandoer ved at bruge [dialogen Kommandoer](#InputGestures).
Hver profil har et emne under kategorien "Indstillingsprofiler".
Hvis du omdøber en profil, vil kommandoen stadig forblive tilgængelig.
Hvis du sletter en profil, vil tildelte kommandoer ligeledes fjernes.

### Placering af indstillingsprofiler {#LocationOfConfigurationFiles}

Flytbare versioner af NVDA opbevarer alle indstillinger og tilføjelsesprogrammer i en mappe med navnet userConfig, som findes i NVDA-mappen.

Installerede versioner af NVDA opbevarer alle indstillinger og tilføjelsesprogrammer i en bestemt NVDA-mappe, som findes i din Windows brugerprofil.
Det betyder, at alle brugere på systemet kan have hver sine NVDA-indstillinger.
Du kan åbne din egen konfigurationsmappe fra hvor som helst ved at tildele en kommando til den ved brug af dialogen [Kommandoer](#InputGestures).
Hvis du har NVDA installeret, kan du finde mappen med dine NVDA-indstillinger ved at gå til Start-menuen og derefter Programmer -> NVDA -> Udforsk mappen med bruger-indstillinger.

De indstillinger, som NVDA bruger ved kørsel på logon-skærmen eller skærmbilledet i forbindelse med brugerkonto-kontrol findes i mappen systemConfig i NVDAs installationsmappe.
Det er normalt ikke nødvendigt at ændre disse indstillinger.
Hvis du vil ændre indstillingerne, som NVDA benytter på logon-skærmen eller skærmbilledet i forbindelse med brugerkonto-kontrol, skal du sætte NVDAs indstillinger, som du ønsker dem, mens du er logget ind på dit Windows-system. Aktivér derefter knappen til kopiering af dine indstillinger til logon-skærmen, der kan findes i den generelle indstillingskategori i [NVDAs indstillinger](#NVDASettings).

## Tilføjelser og Tilføjelsescenter {#AddonsManager}

Tilføjelser er softwarepakker, der giver ny eller ændret funktionalitet til NVDA.
De udvikles af NVDA-fællesskabet og eksterne organisationer som kommercielle udbydere.
Tilføjelser kan udføre følgende opgaver:

* Tilføje eller forbedre understøttelse af visse applikationer.
* Give understøttelse for yderligere punktdisplays eller talesynteser.
* Tilføje eller ændre funktioner i NVDA.

NVDAs Tilføjelsescenter giver dig mulighed for at gennemse og administrere tilføjelsespakker.
Alle tilføjelser, der er tilgængelige i tilføjelsescenteret, kan hentes gratis.
Dog kan nogle af dem kræve, at brugere betaler for en licens eller ekstra software, før de kan bruges.
Kommercielle talesynteser er et eksempel på denne type tilføjelse.
Hvis du installerer en tilføjelse med betalingskomponenter og fortryder, kan tilføjelsen nemt fjernes.

Tilføjelsescenteret åbnes fra undermenuen "Værktøjer" i NVDA-menuen.
For at åbne tilføjelsescenteret fra ethvert sted kan du tildele en brugerdefineret kommando ved hjælp af [dialogen Håndter kommandoer](#InputGestures).

### Gennemse tilføjelser {#AddonStoreBrowsing}

Når tilføjelsescenteret åbnes, vises en liste over tilføjelser.
Hvis du ikke har installeret en tilføjelse før, viser centeret  en liste over tilgængelige tilføjelser til installation.
Hvis du har installeret tilføjelser, vises listen over aktuelt installeret tilføjelser.

Ved at vælge en tilføjelse og navigere til den med piletasterne op og ned, vises detaljerne for tilføjelsen.
Tilføjelser har tilknyttede handlinger, som du kan få adgang til via en [handlingsmenu](#AddonStoreActions), såsom installation, hjælp, deaktivering og fjernelse.
Tilgængelige handlinger ændres baseret på, om tilføjelsen er installeret eller ej, og om den er aktiveret eller deaktiveret.

#### Visninger af tilføjelseslisten {#AddonStoreFilterStatus}

Der er forskellige visninger for installerede, opdaterbare, tilgængelige og inkompatible tilføjelser.
For at ændre visningen af tilføjelser skal du skifte den aktive fane i tilføjelseslisten ved at bruge `ctrl+tab`.
Du kan også navigere til listen over visninger med `tab` og bevæge dig gennem dem ved hjælp af  `venstrePil` og `højrePil`.

#### Filtrering af aktiverede eller deaktiverede tilføjelser {#AddonStoreFilterEnabled}

Normalt er en installeret tilføjelse "aktiveret", hvilket betyder, at den kører og er tilgængelig i NVDA.
Dog kan nogle af dine installeret tilføjelser være sat i "deaktiveret" tilstand.
Dette betyder, at de ikke vil blive brugt, og deres funktioner vil ikke være tilgængelige under den aktuelle NVDA-session.
Du kan have deaktiveret en tilføjelse, fordi den konflikter med en anden tilføjelse eller med en bestemt applikation.
NVDA kan også deaktivere visse tilføjelser, hvis de  anses for at være inkompatible under en opgradering af NVDA, men du vil blive advaret, hvis dette er tilfældet.
Tilføjelser kan også deaktiveres, hvis du ikke har brug for dem i en længere periode, men ikke ønsker at afinstallere dem, fordi du forventer at ville bruge dem igen i fremtiden.

Listerne over installerede og inkompatible tilføjelser kan filtreres efter deres aktiverede eller deaktiverede tilstand.
Standardindstillingen viser både aktiverede og deaktiverede tilføjelser.

#### Inkluder inkompatible tilføjelser {#AddonStoreFilterIncompatible}

Tilgængelige og opdaterbare tilføjelser kan filtreres for at inkludere [inkompatible tilføjelser](#incompatibleAddonsManager), der kan installeres.

#### Filtrér tilføjelser efter kanal {#AddonStoreFilterChannel}

Tilføjelser kan distribueres gennem op til fire kanaler:

* Stabil: Udvikleren har frigivet dette som en testet tilføjelse med en frigivet version af NVDA.
* Beta: Denne tilføjelse kan have brug for yderligere testning, men er frigivet til brugerfeedback.
Anbefales til folk, der gerne vil leve lidt på kanten.
* Dev: Denne kanal anbefales til brug af tilføjelsesudviklere til at teste uoffentliggjorte API-ændringer.
NVDA-alpha-testere kan være nødt til at bruge en "Dev"-version af deres tilføjelser.
* Ekstern: Tilføjelser installeret fra eksterne kilder, uden for tilføjelsescenteret.

For at vise tilføjelser kun for specifikke kanaler skal du ændre filtervalget for "Kanal".

#### Søg efter tilføjelser {#AddonStoreFilterSearch}

For at søge efter tilføjelser skal du bruge tekstfeltet "Søg".
Du kan nå det ved at trykke på `shift+tab` fra listen over tilføjelser.
Indtast ét eller to nøgleord, der beskriver den type tilføjelse, du leder efter, og naviger derefter tilbage til listen over tilføjelser ved at trykke på `tab`.
Tilføjelserne vil blive vist, hvis søgeteksten kan findes i ID, displaynavnet, udgiveren, forfatter eller beskrivelsen.

### Tilføjelseshandlinger {#AddonStoreActions}

Tilføjelser har tilknyttede handlinger, såsom Installér, Hjælp, Deaktivér eller Fjern.
Du kan få adgang til handlingsmenuen i listen over tilføjelser ved at trykke på `applications`-tasten, `enter`, højreklikke eller dobbeltklikke på tilføjelsen.
Denne menu kan også tilgås via knappen "Handlinger" tilgængelig i detaljerne for den valgte tilføjelse.

#### Installation af tilføjelser {#AddonStoreInstalling}

Bare fordi en tilføjelse er tilgængelig i NVDAs Tilføjelsescenter, betyder det ikke, at den er blevet godkendt eller kontrolleret af NV Access eller andre.
Det er meget vigtigt kun at installere tilføjelser fra kilder, du stoler på.
Funktionaliteten af tilføjelser er ubegrænset inden i NVDA.
Dette kan omfatte adgang til dine personlige data eller endda hele systemet.

Du kan installere og opdatere tilføjelser ved at [gennemse tilgængelige tilføjelser](#AddonStoreBrowsing).
Vælg en tilføjelse fra fanen "Tilgængelige tilføjelser" eller "Opdaterbare tilføjelser".
Brug derefter handlingerne "Opdater", "Installér" eller "Erstat" for at starte installationen.

Du kan også installere flere tilføjelser på én gang.
Dette kan du gøre ved at vælge flere tilføjelser, og derefter aktivere kontekstmenuen med mellemrum og vælge "Installér tilføjelser" fra fanen med tilgængelige tilføjelser.

For at installere en tilføjelse, du har fået uden for Tilføjelsescenteret, skal du trykke på knappen "Installer fra ekstern kilde".
Dette giver dig mulighed for at søge efter en tilføjelsespakke (`.nvda-addon`-fil) et sted på din computer eller på et netværk.
Når du åbner tilføjelsespakken, begynder installationsprocessen.

Hvis NVDA er installeret og kører på dit system, kan du også åbne en tilføjelsesfil direkte fra Windows Stifinder for at begynde installationsprocessen.

Når en tilføjelse installeres fra en ekstern kilde, vil NVDA bede dig om at bekræfte installationen.
Når tilføjelsen er installeret, skal NVDA genstartes for, at tilføjelsen kan starte, selvom du kan udskyde genstarten af NVDA, hvis du har andre tilføjelser at installere eller opdatere.

Som standard, vil du få besked om opdateringer for tilføjelser, når NVDA starter.
For at lære mere om, hvordan denne indstilling konfigureres, læs ["Opdateringsmeddelelser"](#AutomaticAddonUpdates).

#### Fjernelse af tilføjelser {#AddonStoreRemoving}

For at fjerne en tilføjelse skal du vælge tilføjelsen fra listen og bruge fjernelseshandlingen.
NVDA beder dig om at bekræfte fjernelsen.
Som ved installation skal NVDA genstartes for, at tilføjelsen bliver fuldstændigt fjernet.
Indtil da vises statussen "Afventer fjernelse" for tilføjelsen i listen.
Som ved instalation, kan du også fjerne flere tilføjelser på én gang.

#### Aktivering og deaktivering af tilføjelser {#AddonStoreDisablingEnabling}

For at deaktivere en tilføjelse skal du bruge "deaktiver"-handlingen.
For at aktivere en tidligere deaktiveret tilføjelse skal du bruge "aktivér"-handlingen.
Du kan deaktivere en tilføjelse, hvis tilføjelsesstatus indikerer, at den er "aktiveret", eller aktivere den, hvis tilføjelsen er "deaktiveret".
For hver brug af aktiverings-/deaktiveringshandlingen ændres tilføjelsesstatus for at angive, hvad der vil ske, når NVDA genstartes.
Hvis tilføjelsen tidligere var "deaktiveret", vises statussen som "aktiveret efter genstart".
Hvis tilføjelsen tidligere var "aktiveret", vises statussen som "deaktiveret efter genstart".
Ligesom ved installation eller fjernelse af tilføjelser skal du genstarte NVDA for, at ændringerne træder i kraft.
Du kan også aktivere eller deaktivere flere tilføjelser på én gang ved at aktivere kontekstmenuen for tilføjelserne med mellemrum, når du står i listen over tilgængelige tilføjelser og du har valgt mere end én.

#### Lav og læs anmeldelser for en tilføjelse {#AddonStoreReviews}

Før du installerer en tilføjelse, kan du læse anmeldelser, som andre har skrevet.
Det kan også være en stor hjælp, hvis du giver feedback her om tilføjelser, som du har brugt.
For at læse anmeldelser, skal du vælge en tilføjelse fra fanen for opdaterbare eller tilgængelige tilføjelser og vælge "Anmeldelser".
Dette fører til en diskussion på GitHub, hvor du kan læse og skrive anmeldelser for tilføjelsen. Denne åbnes i din webbrowser.
Husk, at dette ikke betyder, at det ikke er en god idé at kommunikere direkte med en udvikler af en tilføjelse, som du benytter.
Anmeldelsernes formål er blot at gøre det nemmere for andre brugere at beslutte, hvor vidt en tilføjelse kan være nyttig for dem.

### Inkompatible tilføjelser {#incompatibleAddonsManager}

Nogle ældre tilføjelser er måske ikke længere kompatible med den version af NVDA du har.
Hvis du bruger en ældre version af NVDA, kan nogle nyere tilføjelser også være inkompatible.
Hvis du forsøger at installere en inkompatibel tilføjelse, vises en fejlmeddelelse, der forklarer, hvorfor tilføjelsen anses for inkompatibel.

For ældre tilføjelser kan du omgå inkompatibiliteten på egen risiko.
Inkompatible tilføjelser fungerer måske ikke med din version af NVDA og kan forårsage ustabil eller uventet adfærd, herunder nedbrud.
Du kan omgå kompatibiliteten ved aktivering eller installation af en tilføjelse.
Hvis den inkompatible tilføjelse senere forårsager problemer, kan du deaktivere eller fjerne den.

Hvis du har problemer med at køre NVDA, og du for nylig har opdateret eller installeret en tilføjelse, især hvis det er en inkompatibel tilføjelse, kan du prøve at køre NVDA midlertidigt med alle tilføjelser deaktiveret.
For at genstarte NVDA med alle tilføjelser deaktiveret, vælg den passende mulighed, når du afslutter NVDA.
Alternativt kan du bruge [kommandolinjeoptionen](#CommandLineOptions) `--disable-addons`.

Du kan gennemse tilgængelige inkompatible tilføjelser ved hjælp af [fanerne for tilgængelige og opdateringsmulige tilføjelser](#AddonStoreFilterStatus).
Du kan gennemse installeret inkompatible tilføjelser ved hjælp af [fanen for inkompatible tilføjelser](#AddonStoreFilterStatus).

## Ekstra værktøjer {#ExtraTools}
### Logviser {#LogViewer}

Logvisning, der findes under Værktøjer i NVDA-menuen, giver mulighed for at gennemse al output, der indtil nu og fra NVDA blev startet er blevet gemt i loggen.

Udover muligheden for at gennemse indholdet, er det også muligt at gemme en kopi af logfilen eller genopfriske viseren, så det seneste output fra logvisningen blev startet er det, der vises.
Disse funktioner kan findes under viserens Log-menu.

Logfilen, der vises, når du åbner logviseren er gemt på destinationen `%temp%\nvda.log`.
En ny logfil oprettes, hver gang NVDA startes.
Den gamle logfil, der blev oprettet da NVDA blev startet tidligere, bliver flyttet til `%temp%\nvda-old.log`.

Du kan også kopiere et stykke af logfilen til udklipsholderen uden at åbne logviseren.
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Åbn logviser |`NVDA+f1` |Åbner logviseren og viser udviklerinformationer om det aktuelle navigatorobjekt.|
|Kopier et stykke af logfilen til udklipsholderen |`NVDA+control+shift+f1` |Når du trykker denne kommando for første gang, vil dette indstille, hvornår logfilens indholde skal kopieres. Hvis du trykker igen, vil dette indhold fra og til det tidspunkt, hvor du trykker igen blive kopieret til udklipsholderen.|

<!-- KC:endInclude -->

### Talevisning {#SpeechViewer}

Af hensyn til seende software-udviklere og personer, der ønsker at demonstrere NVDA for seende indeholder NVDA et svævende vindue, der giver mulighed for at se al den tekst, som NVDA i øjeblikket læser op.

Talevisning slås til ved at markere menupunktet  "Talevisning" under Værktøjer" i NVDA-menuen.
Fjern markeringen fra punktet for at slå det fra.

Vinduet til talevisning viser en check box med navnet "Vis talevisning ved opstart".
Hvis denne er valgt, vil talevisning automatisk åbnes når NVDA startes.
Dette vindue vil altid forsøge at åbne med samme dimensioner og samme placering, som de var, da vinduet blev lukket.

Så længe talevisning er slået til, opdateres den konstant med den tekst, der netop nu læses op.
Hvis du holder musen over viseren, eller hvis den får fokus, stoppes opdateringen dog midlertidigt, så det er muligt at markere eller kopiere det aktuelle indhold.

Hvis du gerne vil kunne slå talevisning til og fra, uanset hvor du befinder dig på computeren, kan du tilknytte en bestemt bevægelse eller et tastetryk med [dialogen "Håndter kommandoer"](#InputGestures).

### Punktskriftsviser {#BrailleViewer}

Af hensyn til seende software-udviklere og personer, der ønsker at demonstrere NVDA for seende indeholder NVDA et flydende vindue, der giver mulighed for at se al den tekst, som NVDA i øjeblikket læser op gengivet som punktskrift visuelt på skærmen.
Denne funktion kan bruges samtidigt med et fysisk punktdisplay, hvor mængden af punktceller på skærmen vil tilpasse sig det aktuelt tilkoblede display.
Når funktionen er aktiveret, vil vinduet konstant blive opdateret med den punktskrift, som NVDA gengiver.

Punktskriftsviseren slås til ved at markere menupunktet  "Punktskriftsviser" under Værktøjer" i NVDA-menuen.
Fjern markeringen fra punktet for at slå det fra.

Fysiske punktdisplays har typisk knapper til at panorere displayet frem og tilbage. For at tildele kommandoer til disse funktioner, når punktskriftsviseren benyttes, skal du tildele dem via [kommandoer](#InputGestures) for kommandoerne "Ruller punktdisplay tilbage" og "Ruller punktdisplay fremad".

Vinduet til punktskriftsviseren viser en check box med navnet "Vis punktskriftsviser ved opstart".
Hvis denne er valgt, vil viseren automatisk åbnes når NVDA startes.
Dette vindue vil altid forsøge at åbne med samme dimensioner og samme placering, som de var, da vinduet blev lukket.

Dette vindue indeholder desuden en check box kaldet "Hold musen over for at flytte til den pågældende celle".
Hvis denne indstilling er valgt, vil dette simulere markørknapper og fungere, som havde du trykket på en knap over en punktcelle.
Denne funktion benyttes ofte, når du skal flytte markøren eller udføre en handling på en kontrol.
Dette kan eksempelvis være nyttigt, når du skal bekræfte om NVDA er i stand til at flytte til en bestemt celle.
For at forhindre at NVDA utilsigtet flytter til celler, vil kommandoen være forsinket.
Musen skal holdes over cellen, indtil cellen bliver grøn.
Cellen starter som en lysegul farve, overgår til orange og bliver pludselig grøn.

For at aktivere og deaktivere punktviseren fra hvor som helst, kan du tildele en kommando til funktionen   i [dialogen "Håndter Kommandoer"](#InputGestures).

### Python-konsol {#PythonConsole}

Python-konsollen, der er at finde i menuen "Værktøjer" i NVDA-menuen fungerer som et udviklingsværktøj. Dette værktøj kan benyttes til generel fejlfinding, undersøgelse af interne komponenter i NVDA eller tilgængeligheden af en applikation.
For yderligere information, læs [NVDA Developer Guide](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html).

### Tilføjelsescenteret {#AddonStoreMenuItem}

Dette åbner [Tilføjelsescenteret](#AddonsManager).
For flere informationer, læse afnisttet [Tilføjelser og tilføjelsescenteret](#AddonsManager).

### Opret flytbar kopi {#CreatePortableCopy}

Dette vil åbne en dialog, således du kan oprette en flytbar kopi fra den installerede version af NVDA.

Følg vejledningen [Opret en flytbar kopi](#CreatingAPortableCopy) for yderligere oplysninger.

### Kør værktøj til løsning af almindelige problemer... {#RunCOMRegistrationFixingTool}

Installation og afinstallation af programmer på computeren kan i nogle tilfælde resultere i at nogle COM DLL filer bliver afregistrerede.
Eftersom COM-interfaces som IAccessible afhænger af korrekte registrering af COM DLL, vil problemer nogle gange opstå, hvis nogle filregistreringer mangler.

Dette kan eksempelvis forekomme, hvis du har installeret og derefter afinstalleret Adobe Reader, Math Player og andre programmer.

De manglende filregistreringer kan forårsage problemer med diverse browsere, skrivebordsprogrammer, joblinjen og andre brugergrænseflader.

Følgende problemer kan løses ved at køre dette værktøj:

* NVDA rapporterer "Ukendt", når der navigeres i browsere som Firefox, Thunderbird osv.
* NVDA er ikke i stand til at skifte korrekt mellem fokus- og gennemsynstilstand.
* NVDA forekommer meget langsom, når du navigere i gennemsynstilstand.
* Evt. andre problemer.

### Genindlæs plugins {#ReloadPlugins}

Denne indstilling vil genindlæse alle app-moduler og globale plugins uden at genstarte NVDA. Dette kan være nyttigt for udviklere.
App-moduler bestemmer, hvordan NVDA fungerer med det pågældende program.
Globale plugins bestemmer, hvordan NVDA fungerer med alle programmer.

Følgende NVDA-kommandoer kan være nyttige:
<!-- KC:beginInclude -->

| Navn |Tast |Beskrivelse|
|---|---|---|
|Genindlæs plugins |`NVDA+Control+f3` |Genindlæser NVDAs globale plugins og app-moduler.|
|Få app-modul og  den tilhørende eksekverbare fil oplyst| `NVDA+Control+f1` |Få navnet på det aktuelle app-modul, hvis muligt, samt navnet på den eksekverbare fil for det program, der i øjeblikket har tastaturfokus.|

<!-- KC:endInclude -->

## Understøttede talesynteser {#SupportedSpeechSynths}

Dette afsnit indeholder informationer om de talesynteser, som NVDA understøtter.
For en endnu mere omfattende list over gratis og kommercielt tilgængelige synteser, som du kan bruge med NVDA, besøg venligst [siden om yderligere stemmer der kan bruges med NVDA](https://github.com/nvaccess/nvda/wiki/ExtraVoices).

### eSpeak NG {#eSpeakNG}

Talesyntesen [eSpeak NG](https://github.com/espeak-ng/espeak-ng) er bygget direkte ind i NVDA og kræver ingen installation af særskilte drivere eller komponenter for at fungere.
I Windows 8.1, vil NVDA benytte eSpeak NG som standard ([Windows OneCore](#OneCore) benyttes i Windows 10 og nyere).
Eftersom denne talesyntese er bygget ind i NVDA, er den et godt valg til de situationer, hvor NVDA skal afvikles fra en USB-pen eller fra en cd på flere forskellige systemer.

Hver af de stemmer, som følger med eSpeak NG, taler forskellige sprog.
Der findes mere end 43 forskellige sprog i eSpeak NG.

Der findes også mange forskellige varianter, der kan vælges for at ændre, hvordan den enkelte stemme lyder.

### Microsoft Speech API version 4 (SAPI 4) {#SAPI4}

SAPI 4 er en ældre standard fra Microsoft for software-talesynteser.
NVDA understøtter denne talesyntese for brugere, som allerede har SAPI 4 synteser installeret.
Microsoft understøtter derimod ikke længere talesyntesen og nødvendige komponenter er ikke længere tilgængelige fra Microsoft.

Når denne talesyntese vælges i NVDA, indeholder listen (som nås med [indstillingskategorien "Tale"](#SpeechSettings) i [NVDAs indstillinger](#NVDASettings) eller via [ringen af talesynteseindstillinger](#SynthSettingsRing)) en oversigt over de tilgængelige stemmer fra samtlige SAPI 4 talesynteser, der er installeret på dit system.

### Microsoft Speech API version 5 (SAPI 5) {#SAPI5}

SAPI 5 er en standard fra Microsoft for software-talesynteser.
En lang række af de talesynteser, der overholder denne standard, kan enten købes eller hentes gratis fra forskellige firmaer og netsteder. Din computer har sandsynligvis allerede én SAPI 5 talesyntese præinstalleret.
Når denne talesyntese vælges i NVDA, indeholder listen (som nås med [indstillingskategorien "Tale"](#SpeechSettings) i [NVDAs indstillinger](#NVDASettings) eller via [ringen af talesynteseindstillinger](#SynthSettingsRing)) en oversigt over de tilgængelige stemmer fra samtlige SAPI 5 talesynteser, der er installeret på dit system.

### Microsoft Speech Platform {#MicrosoftSpeechPlatform}

Microsoft Speech Platform giver stemmer til mange sprog. Disse stemmer bliver normalt brugt i udvikling af serverbaserede applikationer.
Stemmerne kan dog også bruges af NVDA.

For a tbruge disse stemmer, er det nødvendigt at installere to komponenter:

* [Microsoft Speech Platform - Runtime (Version 11), x86](https://www.microsoft.com/download/en/details.aspx?id=27225)
* [Microsoft Speech Platform - Runtime Languages (Version 11)](https://www.microsoft.com/download/en/details.aspx?id=27224)
  * Denne side indeholder mange filer for både talegenkendelse og tekst til tale.
 Vælg filerne der indeholder det ønskede sprog/stemmer.
 For eksempel er filen MSSpeech_TTS_en-US_ZiraPro.msI en stemme til amerikansk engelsk.

### Windows OneCore Stemmer {#OneCore}

Windows 10 og nyere indeholder nu stemmer kendt som "OneCore" eller" Mobile."
Der er stemmer tilgængelige på mange sprog, og disse stemmer er hurtigere til at reagere end de tilgængelige Microsoft-stemmer der benytter Microsoft Speech API version 5.
NVDA vil benytte Windows OneCore som standardtalesyntese i windows 10 og nyere ([eSpeak NG](#eSpeakNG) benyttes i andre versioner af Windows).

For at tilføje nye Windows OneCore-stemmer, skal du gå til "Tid og sprog" under Windows-indstillinger (Windows+I), og vælge "Tale".
Vælg "Tilføj stemmer" og søg efter det ønskede sprog.
Mange sprog har flere varianter.
Storbritannien og Australien er to af de engelsk varianter.
For fransk er der Canada, Frankrig og Schweiz.
Søg for det sprog du ønsker, og find en variant i listen over resultater.
Tryk på "Tilføj" for hvert sprog, du ønsker at tilføje.
Genstart NVDA, når du er færdig.

Læs [understøttede sprog og stemmer](https://support.microsoft.com/da-dk/windows/appendix-a-supported-languages-and-voices-4486e345-7730-53da-fcfe-55cc64300f01) for en liste over tilgængelige stemmer.

## Understøttede punktdisplays {#SupportedBrailleDisplays}

Dette afsnit indeholder oplysninger om de punktdisplays, som NVDA understøtter.

### Displays der understøtter automatisk tilkobling i baggrunden {#AutomaticDetection}

NVDA har mulighed for automatisk at tilkoble mange punktdisplays i baggrunden, enten via USB eller Bluetooth.
Denne adfærd opnås ved at vælge "Automatisk" i NVDAs [dialog med punktindstillinger](#BrailleSettings).
Denne indstilling er valgt som standard.

Følgende displays understøtter denne funktionalitet:

* Handy Tech displays
* Baum/Humanware/APH/Orbit braille displays
* HumanWare Brailliant BI/B series
* HumanWare BrailleNote
* SuperBraille
* Optelec ALVA 6 series
* HIMS Braille Sense/Braille EDGE/Smart Beetle/Sync Braille Series
* Eurobraille Esys/Esytime/Iris displays
* Nattiq nBraille displays
* Seika Notetaker: MiniSeika (16, 24 celler), V6, og V6Pro (40 celler)
* Tivomatic Caiku Albatross 46/80 displays
* Ethvert punktdisplay, der understøtter HID Braille-protokollen.

### Freedom Scientific Focus/PAC Mate Series {#FreedomScientificFocus}

Der er understøttelse af alle Focus og PAC Mate displays fra [Freedom Scientific](https://www.freedomscientific.com/), når de kobles til med USB eller Bluetooth.
Punktdisplay-driverne fra Freedom Scientific skal vær installeret på dit system.
Hvis du ikke allerede har dem, kan du hente dem fra [siden om punktdisplayets driver https://www2.freedomscientific.com/downloads/focus-40-blue/focus-40-blue-downloads.asp).
Selvom siden kun henviser til displayet Focus 40 Blue,understøtter driveren alle Freedom Scientific Focus og PAC Mate displays.

Som standard kan NVDA automatisk finde og forbinde til disse displays via USB og Bluetooth.
Når du konfigurerer disse displays kan du dog selv vælge, hvilken forbindelsestype du ønsker at benytte.
Dette kan være nyttigt hvis du ønsker at bruge dit Focus display via Bluetooth, men fortsætte med at oplade dit punktdisplay ved brug af USB fra computeren.
NVDAs automatiske genkendelse af punktdisplays vil også genkende disse display via USB eller Bluetooth.

Tastekombinationerne til dette punktdisplay med NVDA er følgende.
Se venligst dokumentationen til dit punktdisplay for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |top markørsammenføringstast1(første celle på display)|
|Rul display fremad |top markørsammenføringstast20/40/80 (sidste celle på display)|
|Rul punktdisplay tilbage |venstre panoreringsknap|
|Rul punktdisplay fremad |højre panoreringsknap|
|Slå punkt følger til/fra |venstre vælgeknap+højre vælgeknap|
|Skift handling for venstre lynhjul |Tryk venstre lynhjul|
|Flyt tilbage ved brug af venstre lynhjul |Venstre lynhjul op|
|Flyt fremad ved brug af venstre lynhjul |Venstre lynhjul|
|Skift handling for højre lynhjul |tryk på højre lynhjul|
|Flyt tilbage ved brug af højre lynhjul |højre lynhjul op|
|Flyt fremad ved brug af højre lynhjul |højre lynhjul ned|
|Flyt til punktcelle |markørsammenføringsknap|
|skift+tab tast |punktMellemrum+punkt1+punkt2|
|tab tast |punktMellemrum+punkt4+punkt5|
|Pil-op |punktMellemrum+punkt1|
|Pil-ned |punktMellemrum+punkt4|
|Ctrl+Venstre-pil |punktMellemrum+punkt2|
|Ctrl+Højre-pil |punktMellemrum+punkt5|
|Venstre-pil |punktMellemrum+punkt3|
|Højre-pil |punktMellemrum+punkt6|
|Hjem tast |punktMellemrum+punkt1+punkt3|
|end tast |punktMellemrum+punkt4+punkt6|
|Ctrl+hjem tast |punktMellemrum+punkt1+punkt2+punkt3|
|Ctrl+end tast |punktMellemrum+punkt4+punkt5+punkt6|
|alt tast |punktMellemrum+punkt1+punkt3+punkt4|
|alt+tab tast |punktMellemrum+punkt2+punkt3+punkt4+punkt5|
|alt+shift+tab taster |punktMellemrum+punkt1+punkt2+punkt5+punkt6|
|windows+tab taster |punktMellemrum+punkt2+punkt3+punkt4|
|escape tast |punktMellemrum+punkt1+punkt5|
|windows tast |punktMellemrum+punkt2+punkt4+punkt5+punkt6|
|mellemrum tast |punktMellemrum|
|Hold Ctrl-tasten nede |punktMellemrum+punkt3+punkt8|
|Hold alt-tasten nede |punktMellemrum+punkt6+punkt8|
|Hold Windows-tasten nede |punktMellemrum+punkt4+punkt8|
|Hold NVDA-tasten nede |punktMellemrum+punkt5+punkt8|
|Hold shift-tasten nede |punktMellemrum+punkt7+punkt8|
|Hold Ctrl+skift nede |punktMellemrum+punkt3+punkt7+punkt8|
|Hold alt og skift nede |punktMellemrum+punkt6+punkt7+punkt8|
|Hold Alt og Windows nede |punktMellemrum+punkt4+punkt7+punkt8|
|Hold NVDA og skift nede |punktMellemrum+punkt5+punkt7+punkt8|
|Hold Ctrl og alt nede |punktMellemrum+punkt3+punkt6+punkt8|
|Hold Ctrl, alt og skift nede |punktMellemrum+punkt3+punkt6+punkt7+punkt8|
|windows+d tast (minimer alle programmer) |punktMellemrum+punkt1+punkt2+punkt3+punkt4+punkt5+punkt6|
|Annoncér aktuelle linje |punktMellemrum+punkt1+punkt4|
|NVDA-menu |punktMellemrum+punkt1+punkt3+punkt4+punkt5|

For nyere Focus modeller der har vippebjælker (focus 40, focus 80 og focus blue):

| Navn |Tast|
|---|---|
|Flyt punktdisplay til forrige linje |venstre Vippe Bjælke Op, højre vippe bjælke op|
|Flyt punktdisplay til næste linje |venstre vippe bjælke ned, højre vippe bjælke ned|

Kun for Focus 80:

| Navn |Tast|
|---|---|
|Rul display tilbage |højre vippe bjælke op, venstre vippe bjælke op|
|Rul punktdisplay fremad |venstre vippe bjælke ned, højre vippe bjælke ned|

<!-- KC:endInclude -->

### Optelec ALVA 6 serien/protokolomformer {#OptelecALVA}

Der er understøttelse af både ALVA BC640 og BC680 punktdisplays fra [Optelec](https://www.optelec.com/), når der forbindes via USB eller Bluetooth.
Desuden kan du forbinde et ældre punktdisplay fra Optelec, som Braille Voyager, ved brug af en protokolomformer, der leveres af Optelek.
Der kræves ingen særskilte drivere installeret for at bruge disse displays.
Sæt blot displayet til computeren og indstil NVDA til at bruge det.

Bemærk: NVDA er måske ikke i stand til at benytte et ALVA BC6 Bluetooth-punktdisplay, når det pares ved hjælp af Alva Bluetooth-værktøjet.
Når du har benyttet dette værktøj, og NVDA ikke kan finde dit display, anbefales det at du parer dit display ved hjælp af Bluetooth-indstillingerne, der findes i Windows.

Bemærk: Selv om disse punktdisplays har et tastatur, håndtere de selv oversættelsen fra punkt til tekst.
Derfor er NVDAs punkt input indstilling ikke relevant.
For ALVA-punkdisplays med den nyeste firmware, vil det være muligt at slå simuleringen af dette HID-tastatur fra ved hjælp af en tastaturkommando.

Dette er tastekombinationerne til dette display til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |t1, etouch1|
|Flyt punktdisplay to forrige linje |t2|
|Flyt til aktuelle fokus |t3|
|Flyt punktdisplay til næste linje |t4|
|Rul punktdisplay fremad |t5, etouch3|
|Flyt til punktcelle |markørsammenføringsknapper|
|Rapportér tekstformatering under den aktuelle punktcelle |sekundære markørsammenføringsknapper|
|Slå HID-tastatursimulation til og fra |t1+spEnter|
|Flyt til øverste linje i læsning |t1+t2|
|Flyt til nederste linje i læsning |t4+t5|
|Skift indstilling for, hvad punkt følger |t1+t3|
|Rapporter titel |etouch2|
|Rapporter statuslinje |etouch4|
|shift+tab tast |sp1|
|alt tast |sp2, alt|
|escape tast |sp3|
|tab tast |sp4|
|Pil-op |spOp|
|Pil-ned |spNed|
|Venstre-pil |spVenstre|
|Højre-pil |spHøjre|
|enter tast |spEnter, enter|
|Rapporter dato/tid |sp2+sp3|
|NVDA-menu |sp1+sp3|
|windows+d tast (Minimer alle programmer) |sp1+sp4|
|windows+b key (gå til systembakke) |sp3+sp4|
|windows tast |sp1+sp2, Windows|
|alt+tab tast |sp2+sp4|
|CTRL+hjem |t3+spUp|
|CTRL+end |t3+spDown|
|hjem tast |t3+spLeft|
|end tast |t3+spRight|
|control key |control|

<!-- KC:endInclude -->

### Handy Tech Displays {#HandyTech}

NVDA understøtter de fleste displays fra [Handy Tech](https://www.handytech.de/) når displayet er forbundet via USB, serielport eller Bluetooth.
Ældre punktdisplays kræver, at du installerer USB-driveren fra handy Tech på computeren.

Følgende displays er ikke understøttet direkte af NVDA, men kan bruges med [Handy Techs universale driver](https://handytech.de/en/service/downloads-and-manuals/handy-tech-software/braille-display-drivers) og NVDA-tilføjelsespakken:

* Braillino
* Bookworm
* Modular displays med firmware version 1.13 eller ældre. Bemærk venligst at firmware på disse displays kan opdateres.

Dette er tastekombinationerne til Handytech displays med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre, op, b3|
|Rul punktdisplay fremad |højre, ned, b6|
|Flyt punktdisplay to forrige linje |b4|
|Flyt punktdisplay til næste linje |b5|
|Flyt til punktcelle |markørsammenføringsknapper|
|shift+tab Tast |esc, venstre triple action-tast op+ned|
|alt Tast |b2+b4+b5|
|escape Tast |b4+b6|
|tab Tast |enter, højre triple actiontast op+ned|
|enter Tast |esc+enter, left+højre triple actiontast op+ned, joystickAction|
|Pil-op |joystickOp|
|Pil-ned |joystickNed|
|venstre pil |joystickVenstre|
|højre pil |joystickHøjre|
|NVDA-menu |b2+b4+b5+b6|
|Skift indstilling for, hvad punkt følger |b2|
|Ændre indstilling for punktmarkøren |b1|
|Ændre indstilling for fokuskontekstpræsentation |b7|
|Skift indstilling for punktindtastning |mellemrum+b1+b3+b4 (mellemrum+capital B)|

<!-- KC:endInclude -->

### MDV Lilli {#MDVLilli}

Punkttdisplayet Lilli fra [MDV](https://www.mdvbologna.it/) er understøttet.
Installation af særskilte drivere er ikke nødvendig for at kunne bruge dette display.
Tilslut blot displayet og indstil NVDA til at bruge det.

Dette display understøtter ikke NVDAs automatiske tilkobling af punktdisplays.

Dette er tastekombinationerne til dette display til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay baglæns |LF|
|Rul punktdisplay fremad |RG|
|Flyt punktdisplay to forrige linje |op|
|Flyt punktdisplay til næste linje |Ned|
|Flyt til punktcelle |Flyt|
|shift+tab Tast |SLF|
|tab Tast |SRG|
|alt+tab Tast |SDN|
|alt+shift+tab Tast |SUP|

<!-- KC:endInclude -->

### Baum/Humanware/APH/Orbit Punktdisplays {#Baum}

Adskillige [Baum](https://www.baum.de/cms/en/), [HumanWare](https://www.humanware.com/), [APH](https://www.aph.org/) og [Orbit](https://www.orbitresearch.com/) displays er understøttet hvis de kobles til via USB, Bluetooth eller serielport.
Det omfatter:

* Baum: SuperVario, PocketVario, VarioUltra, Pronto!, SuperVario2, Vario 340
* HumanWare: Brailliant, BrailleConnect, Brailliant2
* APH: Refreshabraille
* Orbit: Orbit Reader 20

Nogle andre displays, som er  fremstillet af Baum, virker måske også, men dette er ikke testet.

Hvis du kobler til displayes med USB som ikke bruger HID, skal du først installere driveren fra leverandøren.
VarioUltra og Pronto! bruger HID.
Refreshabraille og Orbit Reader 20 kan bruge HID hvis konfigueret korrekt.

USB serieltilstand af Orbit Reader 20 er på nuværende tidspunkt kun understøttet i Windows 10 og nyere.
USB HID skal som udgangspunkt bruges i stedet.

Dette er tastekombinationerne til dette display til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |`d2`|
|Rul punktdisplay fremad |`d5`|
|Flyt punktdisplay to forrige linje |`d1`|
|Flyt punktdisplay til næste linje |`d3`|
|Flyt til punktcelle |`markørsammenføringsknapper`|
|`shift+tab` |`mellemrum+punkt1+punkt3`|
|`tab` |`mellemrum+punkt4+punkt6`|
|`alt` |`mellemrum+punkt1+punkt3+punkt4` (`mellemrum+m`)|
|`escape` |`mellemrum+punkt1+punkt5` (`mellemrum+e`)|
|`windows` |`mellemrum+punkt3+punkt4`|
|`alt+tab` |`mellemrum+punkt2+punkt3+punkt4+punkt5` (`mellemrum+t`)|
|NVDA-menu |`mellemrum+punkt1+punkt3+punkt4+punkt5` (`mellemrum+n`)|
|`windows+d` (minimer alle applikationer) |`mellemrum+punkt1+punkt4+punkt5` (`mellemrum+d`)|
|Sig alt |`mellemrum+punkt1+punkt2+punkt3+punkt4+punkt5+punkt6`|

For displays der har et joystick:

| Navn |Tast|
|---|---|
|Pil-op |op|
|Pil-ned |ned|
|Venstre-pil |venstre|
|Højre-pil |højre|
|enter Tast |select|

<!-- KC:endInclude -->

### hedo ProfiLine USB {#HedoProfiLine}

Hedo ProfiLine USB fra [hedo Reha-Technik](https://www.hedo.de/) er understøttet.
Du skal først installere driveren fra leverandøren, før du kan benytte dette punktdisplay.

Dette display understøtter ikke NVDAs automatiske tilkobling af punktdisplays.

Dette er tastekombinationerne til dette display til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |K1|
|Rul punktdisplay fremad |K3|
|Flyt punktdisplay to forrige linje |B2|
|Flyt punktdisplay til næste linje |B5|
|Flyt til punktcelle |markørsammenføringsknapper|
|Slå "Punkt følger" til/fra |K2|
|Sig alt |B6|

<!-- KC:endInclude -->

### hedo MobilLine USB {#HedoMobilLine}

Hedo MobilLine USB fra [hedo Reha-Technik](https://www.hedo.de/) er understøttet.
Du skal først installere driveren fra leverandøren, før du kan benytte dette punktdisplay.

Dette display understøtter ikke NVDAs automatiske tilkobling af punktdisplays.

Dette er tastekombinationerne til dette display til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |K1|
|Rul punktdisplay fremad |K3|
|Flyt punktdisplay to forrige linje |B2|
|Flyt punktdisplay til næste linje |B5|
|Flyt til punktcelle |markørsammenføringsknapper|
|Slå "Punkt følger" til/fra |K2|
|Sig alt |B6|

<!-- KC:endInclude -->

### HumanWare Brailliant BI/B Series/BrailleNote Touch {#HumanWareBrailliant}

Brailliant BI og B serierne af punktdisplays fra [HumanWare](https://www.humanware.com/), herunder BI 14, BI 32, BI 20X, BI 40, BI 40X og B 80 er understøttede når du kobler til via USB eller Bluetooth.
Hvis du ønsker at koble displayet til ved brug af USB med protokollen sat til HumanWare, skal du først installere driveren fra leverandøren.
USB drivere kræves ikke, hvis protokollen er sat til OpenBraille.

Følgende yderligere enheder understøttes også, men kræver ingen driver for at fungere:

* APH Mantis Q40
* APH Chameleon 20
* Humanware BrailleOne
* NLS eReader
  * Bemærk, at Zoomax ikke er Understøtet uden tredjepartsdrivere

Dette er tastekombinationerne til Brailliant BI/B og BrailleNote Touch displays til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.

#### Tastekombinationer til alle modeller {#HumanWareBrailliantKeyAssignmentForAllModels}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay to forrige linje |op|
|Flyt punktdisplay til næste linje |ned|
|Flyt til punktcelle |markørsammenføringsknapper|
|Slå "Punkt følger" til/fra |op+ned|
|Pil-op |mellemrum+punkt1|
|Pil-ned |mellemrum+punkt4|
|Venstre-pil |mellemrum+punkt3|
|højre-pil |mellemrum+punkt6|
|shift+tab Tast |mellemrum+punkt1+punkt3|
|tab Tast |mellemrum+punkt4+punkt6|
|alt Tast |mellemrum+punkt1+punkt3+punkt4 (mellemrum+m)|
|escape Tast |mellemrum+punkt1+punkt5 (mellemrum+e)|
|enter Tast |punkt8|
|windows-tast |mellemrum+punkt3+punkt4|
|alt+tab Tast |mellemrum+punkt2+punkt3+punkt4+punkt5 (mellemrum+t)|
|NVDA-menu |mellemrum+punkt1+punkt3+punkt4+punkt5 (space+n)|
|Tasterne Windows+D (minimer alle programmer) |mellemrum+punkt1+punkt4+punkt5 (mellemrum+D)|
|Sig alt |mellemrum+punkt1+punkt2+punkt3+punkt4+punkt5+punkt6|

<!-- KC:endInclude -->

#### Tastekombinationer for Brailliant BI 32, BI 40 og B 80 {#HumanWareBrailliantKeyAssignmentForBI32BI40AndB80}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|NVDA-menu |c1+c3+c4+c5 (command n)|
|Tasterne Windows+D (minimer alle programmer) |c1+c4+c5 (command d)|
|Sig alt |c1+c2+c3+c4+c5+c6|

<!-- KC:endInclude -->

#### Tastekombinationer for Brailliant BI 14 {#HumanWareBrailliantKeyAssignmentForBI14}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Pil op |joystick op|
|Pil ned |joystick ned|
|Venstre piletast |joystick venstre|
|Højre piletast |joystick højre|
|enter-tast |joystick action|

<!-- KC:endInclude -->

### HIMS Braille Sense/Braille EDGE/Smart Beetle+ Sync Braille Series {#Hims}

NVDA understøtter Braille Sense, Braille EDGE, Smart Beetle og Sync punktdisplays fra [Hims](https://www.hims-inc.com/) hvis disse displays kobles til med USB eller Bluetooth.
Hvis du ønsker at koble displayet til ved brug af USB, skal du først installere [driveren fra HIMS](http://www.himsintl.com/upload/HIMS_USB_Driver_v25.zip) på dit system.

Tastekombinationerne til disse displays med NVDA er følgende.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Flyt til punktcelle |markørsammenføringsknapper|
|Rul punktdisplay tilbage |venstre side rul op, højre side rul op, venstre side rul|
|Rul punktdisplay fremad |venstre side rul ned, højre side rul ned, højre side rul|
|Flyt punktdisplay til forrige linje |højre side rul op+venstre side rul op|
|Flyt punktdisplay til næste linje |venstre side rul ned+højre side rul ned|
|Flyt til forrige linje med læsemarkør |højre side pil op|
|Flyt til næste linje med læsemarkør |højre side pil ned|
|Flyt til forrige tegn med læsemarkør |højre side venstre pil|
|Flyt til næste tegn med læsemarkør |højre side højre pil|
|Flyt til aktuelle fokus |venstre side rul op+venstre side rul ned, højre side rul op+højre side rul ned, venstre side rul+højre side rul|
|CTRL-tast |smartbeetle:f1, brailleedge:f3|
|windows-tast |f7, smartbeetle:f2|
|alt+tast |punkt1+punkt3+punkt4+mellemrum, f2, smartbeetle:f3, brailleedge:f4|
|skift-tast |f5|
|insert-tast |punkt2+punkt4+mellemrum, f6|
|tasten applikationer |punkt1+punkt2+punkt3+punkt4+mellemrum, f8|
|capsLock-tast |punkt1+punkt3+punkt6+mellemrum|
|tab-tast |punkt4+punkt5+mellemrum, f3, brailleedge:f2|
|tasterne skift+alt+tab |f2+f3+f1|
|tasterne alt+tab |f2+f3|
|tasterne skift+tab |punkt1+punkt2+mellemrum|
|end-tast |punkt4+punkt6+mellemrum|
|tasterne ctrl+end |punkt4+punkt5+punkt6+mellemrum|
|hjem-tast |punkt1+punkt3+mellemrum, smartbeetle:f4|
|tasterne ctrl+hjem |punkt1+punkt2+punkt3+mellemrum|
|tasterne alt+f4 |punkt1+punkt3+punkt5+punkt6+mellemrum|
|venstre piletast |punkt3+mellemrum, venstre side pil venstre|
|tasterne ctrl+skift+venstre pil |punkt2+punkt8+mellemrum+f1|
|tasterne ctrl+venstre pil |punkt2+mellemrum|
|skift+alt+pil venstre |punkt2+punkt7+f1|
|`alt+pil venstre` |`punkt2+punkt7`|
|højre piletast |punkt6+mellemrum, venstre side pil højre|
|ctrl+skift+pil højre |punkt5+punkt8+mellemrum+f1|
|ctrl+pil højre |punkt5+mellemrum|
|skift+alt+pil højre |punkt5+punkt7+f1|
|`alt+højre pil` |`punkt5+punkt7`|
|tasten side op |punkt1+punkt2+punkt6+mellemrum|
|tasterne ctrl+side op |punkt1+punkt2+punkt6+punkt8+mellemrum|
|pil op |punkt1+mellemrum, venstre side pil op|
|ctrl+skift+pil op |punkt2+punkt3+punkt8+mellemrum+f1|
|ctrl+pil op |punkt2+punkt3+mellemrum|
|skift+alt+pil op |punkt2+punkt3+punkt7+f1|
|`alt+pil op` |`punkt2+punkt3+punkt7`|
|skift+pil op |venstre side rul ned+mellemrum|
|tasten side ned |punkt3+punkt4+punkt5+mellemrum|
|tasterne ctrl+side ned |punkt3+punkt4+punkt5+punkt8+mellemrum|
|pil ned |punkt4+mellemrum, venstre side pil ned|
|ctrl+skift+pil ned |punkt5+punkt6+punkt8+mellemrum+f1|
|ctrl+pil ned |punkt5+punkt6+mellemrum|
|skift+alt+pil ned |punkt5+punkt6+punkt7+f1|
|`alt+pil ned` |`punkt5+punkt6+punkt7`|
|skift+pil ned |mellemrum+højre side rul ned|
|esc+tast |punkt1+punkt5+mellemrum, f4, brailleedge:f1|
|tasten slet |punkt1+punkt3+punkt5+mellemrum, punkt1+punkt4+punkt5+mellemrum|
|f1-tast |punkt1+punkt2+punkt5+mellemrum|
|f3-tast |punkt1+punkt4+punkt8+mellemrum|
|f4-tast |punkt7+f3|
|tasterne windows+b |punkt1+punkt2+f1|
|tasterne windows+d |punkt1+punkt4+punkt5+f1|
|tasterne ctrl+insert |smartbeetle:f1+rightSideScroll|
|tasterne alt+insert |smartbeetle:f3+rightSideScroll|

<!-- KC:endInclude -->

### Seika Braille Displays {#Seika}

Følgende Seika punktdisplays fra Nippon Telesoft understøttes af NVDA. Disse displays er opdelt i to grupper med forskellig funktionalitet:

* [Seika Version 3, 4 og 5 (40 celler), Seika80 (80 celler)](#SeikaBrailleDisplays)
* [MiniSeika (16, 24 celler), V6, og V6Pro (40 celler)](#SeikaNotetaker)

Du kan finde yderligere information om disse displays på [siden Demo and Driver Download](https://en.seika-braille.com/down/index.html).

#### Seika Version 3, 4, og 5 (40 cells), Seika80 (80 cells) {#SeikaBrailleDisplays}

* Disse displays understøtter ikke NVDAs automatiske tilkobling af punktdisplays.
* Vælg "Seika punktdisplays" for at konfigurere manuelt.
* Enhedsdriveren skal være installeret, før du benytter Seika v3/4/5/80.
Driveren er at finde på [producentens hjemmeside](https://en.seika-braille.com/down/index.html).

Dette er tastekombinationerne til Seika displays til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay to forrige linje |b3|
|Flyt punktdisplay to næste linje |b4|
|Slå "Punkt følger" til/fra |b5|
|Sig alt |b6|
|tab |b1|
|skift+tab |b2|
|alt+tab |b1+b2|
|NVDA-menu |venstre+højre|
|Flyt til punktcelle |markørknapper|

<!-- KC:endInclude -->

#### MiniSeika (16, 24 celler), V6, og V6Pro (40 celler) {#SeikaNotetaker}

* NVDAs automatiske tilkobling af punktdisplays understøttes via både USB og Bluetooth, når du bruger disse enheder.
* Vælg "Seika Notetaker" eller "Automatisk" to configure.
* Ekstra drivere er ikke nødvendige, når du bruger et af disse displays.

Dette er tastekombinationerne til Seika Notetaker displays til brug med NVDA.
Se venligst dokumentationen til dit display for at finde ud af, hvor du kan finde knapperne.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Sig alt |mellemrum+Backspace|
|NVDA-Menu |Venstre+højre|
|Flyt punktdisplay to forrige linje |LJ op|
|Flyt punktdisplay til næste linje |LJ ned|
|Slå "Punkt følger" til/fra |LJ center|
|Tab |LJ højre|
|Skift+tab |LJ left|
|Pil op |RJ op|
|Pil ned |RJ ned|
|Venstre pil |RJ venstre|
|Højre pil |RJ højre|
|Flyt til punktcelle |markørknap|
|Skift+pil op |mellemrum+RJ op, Backspace+RJ op|
|Skift+pil ned |mellemrum+RJ ned, Backspace+RJ ned|
|Skift+venstre pil |mellemrum+RJ venstre, backspace+RJ venstre|
|Skift+højre pil |mellemrum+RJ højre, backspace+RJ højre|
|Enter-tast |RJ center, punkt8|
|Escape-tast |mellemrum+RJ center|
|windows-tast |mellemrum+RJ center|
|Mellemrumstast |mellemrum, backspace|
|backspace-tast |punkt7|
|Tasten side op |mellemrum+LJ højre|
|Tasten side ned |mellemrum+LJ venstre|
|Tasten hjem |mellemrum+LJ op|
|Tasten end |mellemrum+LJ ned|
|Ctrl+hjem |backspace+LJ op|
|Ctrl+end |backspace+LJ ned|

<!-- KC:endInclude -->

### Papenmeier BRAILLEX Nyere modeller {#Papenmeier}

Følgende punktdisplays er understøttede:

* BRAILLEX EL 40c, EL 80c, EL 20c, EL 60c (USB)
* BRAILLEX EL 40s, EL 80s, EL 2d80s, EL 70s, EL 66s (USB)
* BRAILLEX Trio (USB og bluetooth)
* BRAILLEX Live 20, BRAILLEX Live og BRAILLEX Live Plus (USB and bluetooth)

Disse displays understøtter ikke NVDAs automatiske tilkobling af punktdisplays.
Der er en indstilling i punktdisplayets USB-driver, der kan forhindre indlæsning af displayet.
Prøv venligst følgende:

1. Sørg for, at du har installeret [den seneste driver](https://www.papenmeier-rehatechnik.de/en/service/downloadcenter/software/articles/software-braille-devices.html).
1. Åbn enhedshåndtering i Windows.
1. Gå ned til "USB-controllere" eller "USB-enheder".
1. Vælg "Papenmeier Braillex USB Device".
1. Åbn "Egenskaber" og gå til fanen "Avanceret".
Nogle gange vises denne fane ikke.
Hvis dette er tilfældet, skal du frakoble displayet fra computeren, afslutte NVDA, vente et øjeblik og koble displayet til igen.
Gentag dette fire til fem gange, hvis nødvendigt.
Hvis fanen stadig ikke vises, genstart computeren.
1. Deaktivér indstillingen "Load VCP".

De fleste enheder har en Easy Access bjælke (EAB) der giver mulighed for intuitive og hurtige handlinger.
EAB kan bevæge sig i fire retninger, hvor der generelt er to tilhørende stillinger.
C-serien og Live-serien er de eneste undtagelser til denne regel.

C-serien samt nogle andre displays har to rækker med markørsammenføringsknapper, hvor den øveste række bruges til at rapportere formateringsinformation.
Hvis du holder en af de øverste  markørsammenføringsknapper og trykker på EAB på C-serien, vil enheden emulere handlingen for den anden stilling.
Displays i Live-serien har kun en enkelt række sammenføringsknapper, og bjælken kan kun bevæges et enkelt trin i hver retning.
Du kan emulere det andet trin ved at trykke på en af sammenføringstasterne og skubbe bjælken i den tilsvarende retning.
Hvis du trykker og holder på piletasterne op, ned, højre og venstre (eller EAB) vil den tilsvarende handling gentages.

De følgende taster er generelt tilgængelige på disse punktdisplays:

| Navn |Tast|
|---|---|
|l1 |Venstre frontTast|
|l2 |Venstre bagtast|
|r1 |Højre frontTast|
|r2 |Højre batTast|
|op |1 trin op|
|op2 |To trin op|
|Venstre |1 trin til venstre|
|venstre2 |2 trin til venstre|
|Højre |1 Trin til højre|
|Højre2 |2 trin til højre|
|ned |1 trin ned|
|Ned2 |2 trin ned|

Papenmeier kommandoer til NVDA er som følger:
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay to forrige linje |op|
|Flyt punktdisplay til næste linje |ned|
|Flyt til punktcelle |markørsammenføringsknapper|
|Sig aktuelt tegn i læsetilstand |l1|
|Aktiver det aktuelle navigatorobjekt |l2|
|slå Braille-tøjring til/fra |r2|
|Rapportér titel |l1+up|
|Rapportër statuslinje |l2+ned|
|Flyt til overordnet objekt |op2|
|Flyt til første underordnet objekt |ned2|
|Flyt til forrige objekt |venstre2|
|Flyt til næste objekt |højre2|
|Rapportér tekstformatering under den aktuelle punktcelle |øverste markørsammenføringsknapper|

<!-- KC:endInclude -->

Trio modellen har yderligere fire knapper. Disse er placeret foran punkttastaturet.
Knapperne er fra venstre mod højre.

* Venstre thumb key (LT)
* mellemrum
* mellemrum
* højre thumb key (RT)

På nuværende tidspunkt er højre thumb key ikke taget i brug.
De midterste taster bliver begge brugt som mellemrumstaster.

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|escape tast |mellemrum med punkt 7|
|Pil-op |mellemrum med punkt 2|
|Venstre-pil |mellemrum med punkt 1|
|Højre-pil |mellemrum med punkt 4|
|Pil-ned |mellemrum med punkt 5|
|kontrol tast |lt+punkt2|
|alt tast |lt+punkt3|
|Ctrl+escape tast |mellemrum med punkt 1 2 3 4 5 6|
|tab tast |mellemrum med punkt 3 7|

<!-- KC:endInclude -->

### Papenmeier Braille BRAILLEX Ældre Modeller {#PapenmeierOld}

Følgende punktdisplays er understøttede:

* BRAILLEX EL 80, EL 2D-80, EL 40 P
* BRAILLEX Tiny, 2D Screen

Bemærk, at disse punktdisplays kun kan opkobles med en serielport.
På grund af dette understøtter disse displays ikke NVDAs automatiske tilkobling af punktdisplays.
Det er nødvendigt at vælge porten, du har koblet dit punktdisplay til, når du har valgt driveren. Dette kan indstilles i dialogen [Vælg punktdisplay](#SelectBrailleDisplay).

Nogle enheder har en Easy Access bjælke (EAB) der giver mulighed for intuitive og hurtige handlinger.
EAB kan bevæge sig i fire retninger, hvor der generelt er to tilhørende stillinger.
Hvis du trykker og holder på piletasterne op, ned, højre og venstre (eller EAB) vil den tilsvarende handling gentages.
Ældre enheder har ikke en AEB; front taster er brugt i stedet.

Følgende taster er generelt tilgængelige på disse punktdisplays:

| Navn |Tast|
|---|---|
|l1 |Venstre front tast|
|l2 |Venstre tast bagved|
|r1 |Højre front tast|
|r2 |Højre tast bagved|
|op |1 trin op|
|op2 |2 trin op|
|venstre |1 trin venstre|
|venstre2 |2 trin venstre|
|højre |1 trin til højre|
|højre2 |2 trin til højre|
|ned |1 trin ned|
|ned2 |2 trin ned|

Papenmeier kommandoer til NVDA er som følgende:

<!-- KC:beginInclude -->
Enheder med EAB:

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay to forrige linje |op|
|Flyt punktdisplay til næste linje |ned|
|Flyt til punktcelle |markørsammenføringsknapper|
|Sig aktuelt tegn i læsetilstand |l1|
|Aktiver det aktuelle navigatorobjekt |l2|
|Rapportér titel |l1+up|
|Rapportër statuslinje |l2+ned|
|Flyt til overordnet objekt |op2|
|Flyt til første underordnet objekt |ned2|
|Flyt til næste objekt |højre2|
|Flyt til forrige objekt |venstre2|
|Rapportér tekstformatering under den aktuelle punktcelle |øverste markørsammenføringsknapper|

BRAILLEX Tiny:

| Navn |Tast|
|---|---|
|Sig aktuelt tegn i læsetilstand |l1|
|Aktiver det aktuelle navigatorobjekt |l2|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay to forrige linje |op|
|Flyt punktdisplay til næste linje |ned|
|Slå "Punkt følger" til/fra |r2|
|Flyt til overordnet objekt |R1+op|
|Flyt til første underordnet objekt |R1+ned|
|Flyt til forrige objekt |R1+venstre|
|Flyt til næste objekt |R1+højre|
|Rapportér tekstformatering under den aktuelle punktcelle |øverste markørsammenføringsknapper|
|Rapportér titel |l1+op|
|Rapportér statuslinje |l2+ned|

BRAILLEX 2D Screen:

| Navn |Tast|
|---|---|
|Rapportér det aktuelle tegn i læsetilstand |l1|
|Aktivér det aktuelle navigatorobjekt |l2|
|Slå "Punkt følger" til/fra |r2|
|Rapportér tekstformatering under den aktuelle punktcelle |øverste markørsammenføringsknapper|
|Flyt punktdisplay to forrige linje |op|
|Rul punktdisplay tilbage |venstre|
|Rul punktdisplay fremad |højre|
|Flyt punktdisplay til næste linje |ned|
|Flyt til næste objekt |Venstre2|
|Flyt til overordnet objekt |Op2|
|Flyt til første underordnet objekt |Ned2|
|Flyt til forrige objekt |Højre2|

<!-- KC:endInclude -->

### HumanWare BrailleNote {#HumanWareBrailleNote}

NVDA understøtter BrailleNote notatapparaterne fra [Humanware](https://www.humanware.com) når de bruges som en displayterminal for en skærmlæser.
Følgende modeller er understøttede:

* BrailleNote Classic ( kun serielforbindelse)
* BrailleNote PK (seriel og bluetooth forbindelser)
* BrailleNote MPower (seriel og bluetooth forbindelser)
* BrailleNote Apex (USB og Bluetooth forbindelser)

For BrailleNote Touch, læs venligst afsnittet [Brailliant BI Series / BrailleNote Touch](#HumanWareBrailliant) for yderligere information.

Udover BrailleNote PK, så er både tastaturer understøttet, herunder både punktindtastning (BT) og QWERTY (QT).
For BrailleNote QT er tastaturemulation ikke understøttet.
Du kan også indtaste punkt via QWERTY-tastaturet.
Læs venligst afsnittet om Braille Terminal i BrailleNote-manualen for yderligere detaljer.

Hvis din enhed understøtter mere end en forbindelsestype, skal du indstille porten til punktterminal under indstillinger for Punkt Terminal.
Læs venligst Braillenote manualen for detaljer.
Det kan også være nødvendigt at indstille porten i [dialogen Vælg punktdisplay](#SelectBrailleDisplay).
hvis du kobler til via USB eller Bluetooth, kan du sætte indstillingen til "Automatisk", "USB" eller "Bleutooth", afhængigt af de tilgængelig valgmuligheder.
Hvis du forbinder enheden gennem en ældre seriel port eller en USB til seriel adapter, eller hvis ingen af de forrige indstillinger er tilgængelige, skal du vælge hvilken port du ønsker at bruge fra listen.

Før du forbinder din BrailleNote Apex ved brug af dens USB-client grænseflade, skal du installere de nødvendige drivere fra HumanWare.

På BrailleNote Apex BT kan du benytte rullehjulet, der er at finde mellem punkt 1 og punkt 4, til at udføre diverse NVDA-kommandoer.
Hjulet består af fire etningspunkter, en klikknap i midten, og et hjul der kan bevæge sig med og imod uret.

Dette er tastekombinationerne til BrailleNote til brug med NVDA.
Se venligst dokumentationen til din BrailleNote for at finde ud af, hvor du kan finde knapperne.

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |back|
|Rul punktdisplay fremad |advance|
|Flyt punktdisplay til forrige linje |previous|
|Flyt punktdisplay til næste linje |next|
|Flyt til punktcelle |markørsammenføringsknapper|
|NvDA-menu |mellemrum+punkt1+punkt3+punkt4+punkt5 (mellemrum+n)|
|Slå "Punkt følger" til/fra |previous+next|
|Pil-op |mellemrum+punkt1|
|Pil-ned key |mellemrum+punkt4|
|Venstre-pil |mellemrum+punkt3|
|Højre-pil |mellemrum+punkt6|
|Side op |mellemrum+punkt1+punkt3|
|side ned |mellemrum+punkt4+punkt6|
|Hjem tast |mellemrum+punkt1+punkt2|
|End tast |mellemrum+punkt4+punkt5|
|Ctrl+hjem |mellemrum+punkt1+punkt2+punkt3|
|Ctrl+end |mellemrum+punkt4+punkt5+punkt6|
|Mellemrumstast |mellemrum|
|Enter tast |mellemrum+punkt8|
|Backmellemrum tast |mellemrum+punkt7|
|Tab tast |mellemrum+punkt2+punkt3+punkt4+punkt5 (mellemrum+t)|
|Shift+tab taster |mellemrum+punkt1+punkt2+punkt5+punkt6|
|Windows tast |mellemrum+punkt2+punkt4+punkt5+punkt6 (mellemrum+w)|
|Alt tast |mellemrum+punkt1+punkt3+punkt4 (mellemrum+m)|
|Tastaturhjælp til/fra |mellemrum+punkt2+punkt3+punkt6 (mellemrum+lavt+h)|

Følgende er tastekombinationer tildelt BrailleNote BT, når punkttilstand ikke er slået til.

| Navn |Tast|
|---|---|
|NvDA-menu |read+n|
|Pil op |pilOp|
|Pil ned |pilNed|
|Venstre pil |venstrePil|
|Højre pil |højrePil|
|Side op |funktion+pilOp|
|Side ned |funktion+pilNed|
|Hjem |funktion+venstrePil|
|End |funktion+højre pil|
|Control+hjem taster |read+t|
|Control+end taster |read+b|
|Enter-tast |enter|
|Backspace-tast |backspace|
|Tab-tast |tab|
|Skift+tab-taster |skift+tab|
|Windows-tast |read+w|
|Alt-tast |read+m|
|Slå tastaturhjælp til og fra |read+1|

Følgende er kommandoer tildelt rullehjulet:

| Navn |Tast|
|---|---|
|Pil op |pilOp|
|Pil ned |pilNed|
|Venstre pil |venstrePil|
|Højre pil |højrePil|
|Enter-tast |center-knap|
|Tab-tast |rul hjul mod uret|
|Skift+tab-taster |rul hjul imod uret|

<!-- KC:endInclude -->

### EcoBraille {#EcoBraille}

NVDA understøtter EcoBraille displays fra [ONCE](https://www.once.es/).
Følgende modeller er understøttet:

* EcoBraille 20
* EcoBraille 40
* EcoBraille 80
* EcoBraille Plus

I NVDA kan du indstille, hvilken seriel port punktdisplayet er forbundet til, i dialogen [Vælg punktdisplay](#SelectBrailleDisplay).
Disse displays understøtter ikke NVDAs automatiske tilkobling af punktdisplays.

Tastaturkommandoerne til Eco punktdisplays er som følger:
Se venligst [dokumentationen til EcoBraille](ftp://ftp.once.es/pub/utt/bibliotecnia/Lineas_Braille/ECO/) for en beskrivelse af, hvor disse taster er placeret.

<!-- KC:beginInclude -->

| Navn |Tastetryk|
|---|---|
|Rul punktdisplay tilbage |T2|
|Rul punktdisplay frem |T4|
|Flyt punktdisplay til forrige linje |T1|
|Flyt punktdisplay til næste linje |T5|
|Flyt markør til punktcelle |Markørflyttetast|
|Aktiver det aktuelle navigator-objekt |T3|
|Skift til næste gennemsynstilstand |F1|
|Flyt til overordnede objekt |F2|
|Skift til forrige gennemsynstilstand |F3|
|Flyt til forrige objekt |F4|
|Læs det aktuelle objekt |F5|
|flyt til næste objekt |F6|
|Flyt til objektet i fokus |F7|
|Flyt til første underordnede objekt |F8|
|Flyt systemfokus eller markør til den aktuelle position for gennemsyn |F9|
|Sig position for gennemsynsmarkør |F0|
|slå tøjring af Braille til/fra |a|

<!-- KC:endInclude -->

### SuperBraille {#SuperBraille}

Punktdisplayet SuperBraille, der for det meste findes i Taiwan, kan forbindes til en computer ved hjælp af USB eller Seriel.
Eftersom displayet ikke har fysiske rulleknapper eller knapper til indtastning af punkt, er det nødvendigt at skrive på et standard computertastatur.
På grund af dette, og for at bevare kompatibiliteten mellem andre skærmlæsere i Taiwan, findes der to taster til at rulle på displayet:
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |numpadMinus|
|Rul punktdisplay fremad |numpadPlus|

<!-- KC:endInclude -->

### Eurobraille displays {#Eurobraille}

b.book, b.note, Esys, Esytime og Iris displays fra Eurobraille understøttes af NVDA.
Disse enheder har et braille tastatur med 10 taster.
Læs venligst dokumentationen for det pågældende display for en beskrivelse af disse taster.
Af de to taster placeret som et mellemrum, svarer den venstre tast til backspace tasten og den højre tast til mellemrumstasten.

Forbundet via USB, har disse enheder et uafhængigt usb tastatur.
Det er muligt at aktivere/deaktivere dette tastatur med en tastaturkommando.
Funktionaliteten beskrevet nedenfor kan benyttes, når HID Braille ikke er aktiv.

#### Funktioner for punkttastatur {#EurobrailleBraille}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Slet den sidst indtastede braille celle eller karakter |`backspace`|
|Oversæt enhver braille indtastning og tryk på enter tasten |`backspace+mellemrum`|
|Skift `NVDA` tast |`punkt3+punkt5+mellemrum`|
|`insert` tast |`punkt1+punkt3+punkt5+mellemrum`, `punkt3+punkt4+punkt5+mellemrum`|
|`delete` tast |`punkt3+punkt6+mellemrum`|
|`home` tast |`punkt1+punkt2+punkt3+mellemrum`|
|`end` tast |`punkt4+punkt5+punkt6+mellemrum`|
|`leftArrow` tast |`punkt2+mellemrum`|
|`rightArrow` tast |`punkt5+mellemrum`|
|`upArrow` tast |`punkt1+mellemrum`|
|`downArrow` tast |`punkt6+mellemrum`|
|`pageUp` tast |`punkt1+punkt3+mellemrum`|
|`pageDown` tast |`punkt4+punkt6+mellemrum`|
|`numpad1` tast |`punkt1+punkt6+backspace`|
|`numpad2` tast |`punkt1+punkt2+punkt6+backspace`|
|`numpad3` tast |`punkt1+punkt4+punkt6+backspace`|
|`numpad4` tast |`punkt1+punkt4+punkt5+punkt6+backspace`|
|`numpad5` tast |`punkt1+punkt5+punkt6+backspace`|
|`numpad6` tast |`punkt1+punkt2+punkt4+punkt6+backspace`|
|`numpad7` tast |`punkt1+punkt2+punkt4+punkt5+punkt6+backspace`|
|`numpad8` tast |`punkt1+punkt2+punkt5+punkt6+backspace`|
|`numpad9` tast |`punkt2+punkt4+punkt6+backspace`|
|`numpadInsert` tast |`punkt3+punkt4+punkt5+punkt6+backspace`|
|`numpadDecimal` tast |`punkt2+backspace`|
|`numpadDivide` tast |`punkt3+punkt4+backspace`|
|`numpadMultiply` tast |`punkt3+punkt5+backspace`|
|`numpadMinus` tast |`punkt3+punkt6+backspace`|
|`numpadPlus` tast |`punkt2+punkt3+punkt5+backspace`|
|`numpadEnter` tast |`punkt3+punkt4+punkt5+backspace`|
|`escape` tast |`punkt1+punkt2+punkt4+punkt5+mellemrum`, `l2`|
|`tab` tast |`punkt2+punkt5+punkt6+mellemrum`, `l3`|
|`shift+tab` taster |`punkt2+punkt3+punkt5+mellemrum`|
|`printScreen` tast |`punkt1+punkt3+punkt4+punkt6+mellemrum`|
|`pause` tast |`punkt1+punkt4+mellemrum`|
|`applications` tast |`punkt5+punkt6+backspace`|
|`f1` tast |`punkt1+backspace`|
|`f2` tast |`punkt1+punkt2+backspace`|
|`f3` tast |`punkt1+punkt4+backspace`|
|`f4` tast |`punkt1+punkt4+punkt5+backspace`|
|`f5` tast |`punkt1+punkt5+backspace`|
|`f6` tast |`punkt1+punkt2+punkt4+backspace`|
|`f7` tast |`punkt1+punkt2+punkt4+punkt5+backspace`|
|`f8` tast |`punkt1+punkt2+punkt5+backspace`|
|`f9` tast |`punkt2+punkt4+backspace`|
|`f10` tast |`punkt2+punkt4+punkt5+backspace`|
|`f11` tast |`punkt1+punkt3+backspace`|
|`f12` tast |`punkt1+punkt2+punkt3+backspace`|
|`windows` tast |`punkt1+punkt2+punkt4+punkt5+punkt6+mellemrum`|
|Skift `windows` tast |`punkt1+punkt2+punkt3+punkt4+backspace`, `punkt2+punkt4+punkt5+punkt6+mellemrum`|
|`capsLock` tast |`punkt7+backspace`, `punkt8+backspace`|
|`numLock` tast |`punkt3+backspace`, `punkt6+backspace`|
|`shift` tast |`punkt7+mellemrum`|
|Skift `shift` tast |`punkt1+punkt7+mellemrum`, `punkt4+punkt7+mellemrum`|
|`control` tast |`punkt7+punkt8+mellemrum`|
|Skift `control` tast |`punkt1+punkt7+punkt8+mellemrum`, `punkt4+punkt7+punkt8+mellemrum`|
|`alt` tast |`punkt8+mellemrum`|
|Skift `alt` tast |`punkt1+punkt8+mellemrum`, `punkt4+punkt8+mellemrum`|
|Aktiver/deaktiver HID-punkttastatur |`switch1Left+joystick1Down`, `switch1Right+joystick1Down`|

<!-- KC:endInclude -->

#### b.book tast kommandoer {#Eurobraillebbook}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul braille display tilbage |`backward`|
|Rul braille display fremad |`forward`|
|Flyt til aktuel fokus |`backward+forward`|
|Rute til braille celle |`routing`|
|`leftArrow` tast |`joystick2Left`|
|`rightArrow` tast |`joystick2Right`|
|`upArrow` tast |`joystick2Up`|
|`downArrow` tast |`joystick2Down`|
|`enter` tast |`joystick2Center`|
|`escape` tast |`c1`|
|`tab` tast |`c2`|
|Skift `shift` tast |`c3`|
|Skift `control` tast |`c4`|
|Skift `alt` tast |`c5`|
|Skift `NVDA` tast |`c6`|
|`control+Home` tast |`c1+c2+c3`|
|`control+End` tast |`c4+c5+c6`|

<!-- KC:endInclude -->

#### b.note tast kommandoer {#Eurobraillebnote}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul braille display tilbage |`leftKeypadLeft`|
|Rul braille display fremad |`leftKeypadRight`|
|Rute til braille celle |`routing`|
|Rapporter tekstformatering under braille celle |`doubleRouting`|
|Flyt til næste linje i gennemgang |`leftKeypadDown`|
|Skift til forrige gennemgangsmodus |`leftKeypadLeft+leftKeypadUp`|
|Skift til næste gennemgangsmodus |`leftKeypadRight+leftKeypadDown`|
|`leftArrow` tast |`rightKeypadLeft`|
|`rightArrow` tast |`rightKeypadRight`|
|`upArrow` tast |`rightKeypadUp`|
|`downArrow` tast |`rightKeypadDown`|
|`control+home` tast |`rightKeypadLeft+rightKeypadUp`|
|`control+end` tast |`rightKeypadLeft+rightKeypadUp`|

<!-- KC:endInclude -->

#### Esys tast kommandoer {#Eurobrailleesys}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul braille display tilbage |`switch1Left`|
|Rul braille display fremad |`switch1Right`|
|Flyt til aktuel fokus |`switch1Center`|
|Rute til braille celle |`routing`|
|Rapporter tekstformatering under braille celle |`doubleRouting`|
|Flyt til forrige linje i gennemgang |`joystick1Up`|
|Flyt til næste linje i gennemgang |`joystick1Down`|
|Flyt til forrige karakter i gennemgang |`joystick1Left`|
|Flyt til næste karakter i gennemgang |`joystick1Right`|
|`leftArrow` tast |`joystick2Left`|
|`rightArrow` tast |`joystick2Right`|
|`upArrow` tast |`joystick2Up`|
|`downArrow` tast |`joystick2Down`|
|`enter` tast |`joystick2Center`|

<!-- KC:endInclude -->

#### Esytime tast kommandoer {#EurobrailleEsytime}

<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul braille display tilbage |`l1`|
|Rul braille display fremad |`l8`|
|Flyt til aktuel fokus |`l1+l8`|
|Rute til braille celle |`routing`|
|Rapporter tekstformatering under braille celle |`doubleRouting`|
|Flyt til forrige linje i gennemgang |`joystick1Up`|
|Flyt til næste linje i gennemgang |`joystick1Down`|
|Flyt til forrige karakter i gennemgang |`joystick1Left`|
|Flyt til næste karakter i gennemgang |`joystick1Right`|
|`leftArrow` tast |`joystick2Left`|
|`rightArrow` tast |`joystick2Right`|
|`upArrow` tast |`joystick2Up`|
|`downArrow` tast |`joystick2Down`|
|`enter` tast |`joystick2Center`|
|`escape` tast |`l2`|
|`tab` tast |`l3`|
|Skift `shift` tast |`l4`|
|Skift `control` tast |`l5`|
|Skift `alt` tast |`l6`|
|Skift `NVDA` tast |`l7`|
|`control+home` tast |`l1+l2+l3`, `l2+l3+l4`|
|`control+end` tast |`l6+l7+l8`, `l5+l6+l7`|
|Aktiver/deaktiver HID-punkttastatur |`l1+joystick1Down`, `l8+joystick1Down`|

<!-- KC:endInclude -->

### Nattiq nBraille Displays {#NattiqTechnologies}

NVDA understøtter punktdisplays fra [Nattiq Technologies](https://www.nattiq.com/) når de forbindes via USB.
Windows 10 og nyere vil automatisk forbinde til punktdisplayet. Hvis du bruger ældre versioner af Windows (f.eks. Windows 7) skal du installere driveren.
Disse kan hentes fra producentens hjemmeside.

Følgende er tastekombinationerne til  Nattiq Technologies displays ved brug af NVDA.
Læs venligst dokumentationen for det pågældende display der beskriver, hvor disse taster findes.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |op|
|Rul punktdisplay fremad |ned|
|Flyt punktdisplay til forrige linje |venstre|
|Flyt punktdisplay til næste linje |højre|
|Flyt til punktcelle |Markørknapper|

<!-- KC:endInclude -->

### BRLTTY {#BRLTTY}

[BRLTTY](https://www.brltty.app/) er et særskilt program, der understøtter yderligere en lang række punktdisplays.
For at kunne bruge det, skal du installere programmet [BRLTTY for Windows](https://www.brltty.app/download.html).
Det anbefales, at du henter og installerer den seneste installationspakke, som fx. kan have navnet brltty-win-4.2-2.exe.
Under konfigurationen af displayet og den port, der skal bruges, skal du følge instruktionerne nøje, især hvis du benytter et USB-display og allerede har installeret producentens drivere.

BRLTTY håndterer selv indtastning på punkt, hvis det tilkoblede punktdisplay har et punkttastatur.
NVDAs indstilling for oversættelsestabel er derfor ikke relevant.

BRLTTY har ikke noget med NVDAs automatiske tilkobling af punktdisplays at gøre.

Dette er tastekombinationerne til BRLTTY til brug med NVDA.
Se venligst [BRLTTY dokumentationen for tastekombinationer](https://brltty.app/doc/KeyBindings/) for yderliger information om, hvordan BRLTTY kommandoer er indstillet til kontroller på diverse punktdisplays.
<!-- KC:beginInclude -->

| Navn |BRLTTY command|
|---|---|
|Rul punktdisplay tilbage |`fwinlt` (gå et vindue til venstre)|
|Rul punktdisplay fremad |`fwinrt` (gå et vindue til højre)|
|Flyt punktdisplay til forrige linje |`lnup` (gå en linje op)|
|Flyt punktdisplay til næste linje |`lndn` (gå en linje ned)|
|Flyt til punktcelle |`route` (bring markør til tegn)|
|Aktivér/deaktivér tastaturhjælp |`learn` (Slår tastaturhjælp til og fra)|
|Åbn NVDA-menu |`prefmenu` (Åbn/forlad opsætningsmenu)|
|Gendan konfiguration |`prefload` (Gendan opsætning fra disk)|
|Gem konfiguration |`prefsave` (Gem opsætning til disk)|
|Oplys tid |`time` (Vis aktuelle tid og dato)|
|Sig linje, hvor læsemarkøren befinder sig |`say_line` (sig aktuelle linje)|
|Sig alt ved brug af læsemarkøren |`say_below` (læs fra aktuelle linjen til bunden af skærmen)|

<!-- KC:endInclude -->

### Tivomatic Caiku Albatross 46/80 {#Albatross}

Caiku Albatross-enhederne, som fremstilles af Tivomatic og er tilgængelige i Finland, kan tilsluttes enten via USB eller seriel.
Det er ikke nødvendigt at installere en særlig enhedsdriver, før du kan bruge disse displays.
Du skal blot koble displayet til din enhed og herefter konfigurere NVDA til at bruge punktdisplayet.

Bemærk: Baud rate 19200 anbefales på det kraftigste.
Skift om nødvendigt indstillingsværdien for Baud-hastighed til 19200 fra punktdisplayets menu.
Selvom driveren understøtter 9600 baud rate, har den ingen måde at kontrollere, hvilken baud rate displayet bruger.
Fordi 19200 er displayets standard baudhastighed, vil driveren automatisk benytte denne hastighed.
Hvis baud-hastighederne ikke er de samme, kan driveren opføre sig uhensigtsmæssigt.

Følgende er tastekombinationerne til disse displays ved brug af NVDA.
Læs venligst dokumentationen for det pågældende display der beskriver, hvor disse taster findes.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Flyt til øverste linje med læsemarkøren |`home1`, `home2`|
|Flyt til nederste linje med læsemarkøren |`end1`, `end2`|
|Flytter navigatorobjektet til det aktuelle fokus |`eCursor1`, `eCursor2`|
|Flyt til aktuelle fokus |`cursor1`, `cursor2`|
|Flytter musemarkøren til det aktuelle navigatorobjekt |`home1+home2`|
|Flytter musemarkøren til det aktuelle navigatorobjekt og læser det op |`end1+end2`|
|Flytter fokus til det aktuelle navigatorobjekt |`eCursor1+eCursor2`|
|Skifter indstillingen for "punkt følger" |`cursor1+cursor2`|
|Flyt punktdisplay til forrige linje |`up1`, `up2`, `up3`|
|Flyt punktdisplay til næste linje |`down1`, `down2`, `down3`|
|Panorer punktdisplay tilbage |`left`, `lWheelLeft`, `rWheelLeft`|
|Panorer punktdisplay fremad |`right`, `lWheelRight`, `rWheelRight`|
|Flyt til punktcelle |`markørknapper`|
|Oplys tekstformattering under den aktuelle punktcelle |`sekundære markørknapper`|
|Skift måden kontekstoplysninger vises på punkt |`attribute1+attribute3`|
|Skift mellem de forskellige taleindstillinger |`attribute2+attribute4`|
|Skift til forrige læsetilstand (f.eks. objekt, dokument eller skærm) |`f1`|
|Skift til næste læsetilstand |`f2`|
|Flyt navigatorojektet til det objekt, der indeholder det |`f3`|
|Flytter navigatorobjektet til det første objekt inde i det |`f4`|
|Flytter navigatorobjektet til det forrige objekt |`f5`|
|Flytter navigatorobjektet til det næste objekt |`f6`|
|Oplyser det aktuelle navigatorobjekt |`f7`|
|Oplyser oplysninger om placeringen af teksten eller objektet ved læsemarkøren |`f8`|
|Viser indstillinger for punkt |`f1+home1`, `f9+home2`|
|Læser statuslinjen og flytter navigatorobjektet til den |`f1+end1`, `f9+end2`|
|Skift mellem punktmønstre for punktmarkørens form |`f1+eCursor1`, `f9+eCursor2`|
|Slå punktmarkøren til og fra |`f1+cursor1`, `f9+cursor2`|
|Skift indstilling for "Vis beskeder" |`f1+f2`, `f9+f10`|
|Skift indstillingen for valgmarkøren |`f1+f5`, `f9+f14`|
|Skift indstillingen for "Punkt flytter systemmarkør, når læsemarkøren flyttes med markørknapperne" |`f1+f3`, `f9+f11`|
|Udfør standardhandlingen for det aktuelle navigatorobjekt |`f7+f8`|
|Få dato/tid oplyst |`f9`|
|Få batteriet oplyst |`f10`|
|Få titlen oplyst |`f11`|
|Oplys statuslinje |`f12`|
|Oplys den aktuele linje under markøren |`f13`|
|Sig alt |`f14`|
|Oplys det aktuelle tegn under læsemarkøren |`f15`|
|Oplys den aktuelle linje for det navigatorobjekt, hvor læsemarkøren befinder sig |`f16`|
|Oplys det aktuelle ord for det navigatorobjekt, hvor læsemarkøren befinder sig |`f15+f16`|
|Flytter læsemarkøren til den forrige linje i det aktuelle navigatorobjekt og læser det op |`lWheelUp`, `rWheelUp`|
|Flytter læsemarkøren til den næste linje i det aktuelle navigatorobjekt og læser det op |`lWheelDown`, `rWheelDown`|
|Tasterne `Windows+d` (minimér alle programmer) |`attribute1`|
|Tasterne `Windows+e` (Denne PC) |`attribute2`|
|Tasterne `Windows+b` (flyt fokus til systembakken) |`attribute3`|
|Tasterne `Windows+i` (Windows-indstillinger) |`attribute4`|

<!-- KC:endInclude -->

### Standard HID Braille displays {#HIDBraille}

Dette er en eksperimentel driver for den nye HID Braille standard, som firmaerne Microsoft, Google, Apple samt flere virksomheder bag hjælpeteknologier herunder NV Access nåede til enighed om i 2018.
Håbet er, at denne standard vil blive vedtaget og benyttet af fremtidige fabrikanter af punktdisplays, hvilket vil fjerne behovet for særskilte drivere.

NVDAs automatiske tilkobling vil også automatisk genkende punktdisplays, der bruger denne standard.

Følgende er tastekombinationerne ved brug af displays, der bruger denne standard.
<!-- KC:beginInclude -->

| Navn |Tast|
|---|---|
|Rul punktdisplay tilbage |panorer til venstre eller vippeknap op|
|Rul punktdisplay fremad |panorer til højre eller vippeknap ned|
|Flyt til punktcelle |markørflytteknap|
|Skift indstillingen Punkt følger |op+ned|
|Pil op |joystick op , dpad op eller mellemrum+punkt1|
|Pil ned |joystick ned , dpad ned eller mellemrum+punkt4|
|Venstre pil |mellemrum+punkt3, joystick venstre eller dpad venstre|
|Højre pil |mellemrum+punkt6, joystick højre eller dpad højre|
|shift+tab |mellemrum+punkt1+punkt3|
|tab |mellemrum+punkt4+punkt6|
|alt |mellemrum+punkt1+punkt3+punkt4 (mellemrum+m)|
|escape |mellemrum+punkt1+punkt5 (mellemrum+e)|
|Enter |punkt8, tryk på midten af joystick eller dpad|
|windows |mellemrum+punkt3+punkt4|
|alt+tab |mellemrum+punkt2+punkt3+punkt4+punkt5 (mellemrum+t)|
|NVDA-menu |mellemrum+punkt1+punkt3+punkt4+punkt5 (mellemrum+n)|
|Windows+d (minimer alle programmer og gå til skrivebordet) |mellemrum+punkt1+punkt4+punkt5 (mellemrum+d)|
|Sig alt |Mellemrum+punkt1+punkt2+punkt3+punkt4+punkt5+punkt6|

<!-- KC:endInclude -->

## Avancerede emner {#AdvancedTopics}
### Sikker tilstand {#SecureMode}

Systemadministratorer kan ønske at indstille NVDA, så man forhindrer uautoriseret adgang til systemet.
NVDA giver mulighed for at installere brugerdefinerede tilføjelsesprogrammer, som kan køre enhver form for kode. Dette gælder også, når NVDA har administratorrettigheder.
Desuden giver NVDA brugerne mulighed for at køre enhver kode via NVDA's Python-konsol.
Når NVDA er i sikker tilstand, kan brugere ikke ændre deres indstillinger i NVDA, og uautoriseret adgang til systemet begrænses yderligere.

NVDA kører automatisk i sikker tilstand, når du bruger [beskyttede skærme](#SecureScreens), medmindre `serviceDebug` [systemspecifikke parameter](#SystemWideParameters) er aktiveret.
Hvis du vil tvinge NVDA til altid at køre i sikker tilstand, skal du benytte [systemparametret](#SystemWideParameters) `forceSecureMode`.
NVDA kan startes i sikker tilstand ved brug af `-s` [kommandolinjeparameter](#CommandLineOptions).

Sikker tilstand deaktiverer:

* Muligheden for at gemme konfiguration og andre indstillinger til disken
* Muligheden for at gemme filen til håndtering af kommandoer til disken
* [Konfigurationsprofiler](#ConfigurationProfiles) funktioner som at oprette, slette og omdøbe profiler, osv.
* Indlæsning af andre mapper til konfigurationer ved brug af [t`-c` kommandolinjeparameter](#CommandLineOptions)
* Opdatering af NVDA og oprettelse af flytbare kopier
* [Tilføjelsescenteret](#AddonsManager)
* [Python-konsollen](#PythonConsole)
* [Logviseren](#LogViewer) og logføring
* [Punktskriftsviseren](#BrailleViewer) og [Taleviseren](#SpeechViewer)
* Åbning af eksterne filer fra NVDAs menu, såsom brugervejledningen og filen, hvor bidragydere er anførte

Installerede versioner af NVDA lagrer deres opsætning, herunder tilføjelsesprogrammer, i `%APPDATA%\nvda`.
For at sikre, at NVDA-brugere ikke direkte kan ændre på opsætningen eller tilføjelserne, bør adgangen til denne mappe begrænses.

Sikker tilstand er ineffektiv for bærbare kopier af NVDA.
Denne begrænsning gælder også for den midlertidige kopi af NVDA, der kører, når installationsprogrammet startes.
I sikre miljøer udgør en brugers mulighed for at køre en flytbar eksekverbar fil den samme sikkerhedsrisiko uanset sikker tilstand.
Det forventes, at systemadministratorer begrænser uautoriseret software fra at køre på deres systemer, herunder flytbare kopier af NVDA.

Mange NVDA-brugere tilpasser deres NVDA-profil for at få den til at passe til deres specifikke behov.
Dette kan indebære at installere og indstille specielle tilføjelsesprogrammer, som bør gennemgås uafhængigt af selve NVDA.
I sikker tilstand bliver ændringer i NVDA's opsætning låst. Det er derfor vigtigt at sikre, at NVDA er sat op korrekt, inden man aktiverer sikker tilstanden.

### Sikre skærme {#SecureScreens}

NVDA kører i [sikker tilstand](#SecureMode), når du bruger sikre skærme, medmindre `serviceDebug` [systemspecifikke parameter](#SystemWideParameters) er aktiveret.

Når NVDA afvikles i et sikkert miljø, vil NVDA benytte systemprofilen til at anvende indstillinger.
NVDAs indstillinger kan kopieres for brug på [sikre skærme](#GeneralSettingsCopySettings).

Sikre skærme inkluderer:

* Windows logon-skærmen
* Kontrol af brugerkonti (aktiv, når du udfører bestemte handlinger som administrator)
  * Dette er også tilfældet, når du installerer programmer

### indstillinger på kommandolinjen {#CommandLineOptions}

Du kan angive en eller flere indstillinger på kommandolinjen, når du starter NVDA.
Du kan angive så mange indstillinger, som du har brug for.
Disse indstillinger kan angives, når du starter NVDA fra en genvej (under egenskaber for genvej), fra Kør-dialogen (Startmenu -> Kør eller Windows+r) eller eller fra Windows kommandoprompt.
kommandolinjeparametre skal adskilles fra navnet på NVDAs eksekverbare fil og fra andre kommandolinjeparametre af mellemrum.
En nyttig kommandolinjeparameter er for eksempel `--disable-addons`, som får NVDA til at afbryde alle tilføjelsesprogrammer
Med den kan du finde ud af, om et givet problem skyldes et tilføjelsesprogram eller klare et alvorligt problem, som er forårsaget af et tilføjelsesprogram.

Som et eksempel kan du afslutte den aktuelle kopi af NVDA ved at skrive følgende i Kør-dialogen:

    nvda -q

Nogle af kommandolinjeparametrene har både en kort og en lang version, mens andre kun har en lang version.
Dem  som har en kort version, kan kombineres på denne måde:

| . {.hideHeaderRow} |.|
|---|---|
|`nvda -mc CONFIGPATH` |Dette vil starte NVDA uden at afspille opstartslyden eller udtale en besked, og med den angivne konfiguration|
|`nvda -mc CONFIGPATH --disable-addons` |Det samme som ovenfor, men deaktivere også tilføjelser|

Med nogle af kommandolinjeparametrene kan du angive yderlige parametre, fx. hvor detaljeret loggen skal være, eller stien til mappen med brugerprofiler.
Disse yderligere parametre skal skrives efter indstillingen og adskilles fra indstillingen af et mellemrum i den korte version og af et lighedstegn (`=`) i den lange version, fx.

| . {.hideHeaderRow} |.|
|---|---|
|`nvda -l 10` |Starter NVDA med logningsniveau sat til fejlfinding|
|`nvda --log-file=c:\nvda.log` |Får NVDA til at skrive sin log til `c:\nvda.log`|
|`nvda --log-level=20 -f c:\nvda.log` |Får NVDA til at starte med logniveau sat til "info" og gemme sin log i filen `c:\nvda.log`|

De mulige kommandolinjeparametre til NVDA er følgende:

| Kort |Lang |Beskrivelse|
|---|---|---|
|`-h` |`--help` |Vis hjælp til kommandolinje og afslut|
|`-q` |`--quit` |Afslut den nuværende kopi af NVDA|
|`-k` |`--check-running` |Fortæl via exitkoden, om NVDA kører (0 hvis NVDA kører, 1 hvis den ikke gør)|
|`-f LOGFILENAME` |`--log-file=loggens filnavn` |Filen hvor NVDAs log skal gemmes. Logføring er altid deaktiveret, hvis sikker tilstand er aktiv.|
|`-l LOGLEVEL` |`--log-level=LOGNINGSNIVEAU` |Det laveste niveau af meddelelser, som skal logges (fejlfinding 10, input/output 12, fejlfinding og advarsler 15, info 20, deaktiveret 100). Logføring er altid deaktiveret, hvis sikker tilstand er aktiv.|
|`-c CONFIGPATH` |`--config-path=KONFIGURATIONSSTI` |Stien, hvor alle indstillinger i NVDA skal gemmes. Standardværdien vil blive brugt, hvis sikker tilstand er aktiv.|
|None |`--lang=SPROG` |Brug et specifikt sprog uanset NVDAs konfiguration. Skriv "Windows" for standardsprog, "en" for engelsk, osv.|
|`-m` |`--minimal` |Ingen lyde, ingen brugergrænseflade, ingen opstartsmeddelelser osv.|
|`-s` |`--secure` |Starter NVDA i [sikker tilstand](#SecureMode)|
|Ingen |`--disable-addons` |ingen tilføjelsesprogrammer|
|Ingen |`--debug-logging` |Aktivér logningsniveau til brug ved fejlfinding for kun denne opstart. Denne indstilling vil overstyre alle logningsniveau (`--loglevel`, `-l`) parametre.|
|Ingen |`--no-logging` |Deaktivér logning fuldstændigt under brugen af NVDA. Denne indstilling kan blive tilsidesat hvis (`--loglevel`, `-l`) angives fra kommandolinjen eller såfremt logning for fejlfinding er slået til.|
|Ingen |`--no-sr-flag` |Forhindre ændring af det globale skærmlæserflag|
|Ingen |`--install` |Installerer NVDA og starter den nyinstallerede kopi|
|Ingen |`--install-silent` |Tavs installation af NVDA (Starter ikke den nyinstallerede kopi)|
|Ingen |`--enable-start-on-logon=True|False` |Under installation vil dette aktivere [opstart ved logon-skærmen](#StartAtWindowsLogon)|
|Ingen |`--copy-portable-config` |Kopierer den flytbare konfiguration til den angivne sti under installation (`--config-path`, `-c`) til den aktuelle brugerkonto|
|Ingen |`--create-portable` |Opretter en flytbar kopi af NVDA (starter den nyoprettede kopi). Kræver `--portable-path` angives|
|Ingen |`--create-portable-silent` |Opretter en flytbar kopi af NVDA (starter ikke den nyoprettede kopi). Kræver `--portable-path` angives|
|Ingen |`--portable-path=sti` |Stien, hvor den flytbare kopi oprettes|

### Systemspecifikke parametre {#SystemWideParameters}

NVDA tillader, at nogle værdier ændres i systemregistreringsdatabasen. Disse ændringer påvirker NVDAs adfærd på et systemspecifikt niveau.
Disse værdier er gemt i registreringsdatabasen under en af følgende nøgler:

* 32-bit system: `HKEY_LOCAL_MACHINE\SOFTWARE\nvda`
* 64-bit system: `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\nvda`

Følgende værdier kan indstilles under denne registreringsdatabasenøgle:

| Navn |Type |Mulige værdier |Beskrivelse|
|---|---|---|---|
|`configInLocalAppData` |DWORD |0 (standard) for at deaktivere, 1 for at aktivere |Hvis dette er aktiveret, vil NVDAs konfiguration gemmes i local application data i stedet for mappen roaming application data|
|`serviceDebug` |DWORD |0 (standard) for at deaktivere, 1 for at aktivere |vis dette er aktiveret, deaktiveres [sikker tilstand](#SecureMode) på [sikre skærme](#SecureScreens). På grund af flere sikkerhedsbrud, kan denne indstilling ikke anbefales|
|`forceSecureMode` |DWORD |0 (standard) for at deaktivere, 1 for at aktivere |Hvis dette er aktiveret, tvinger NVDA til at køre i [sikker tilstand](#SecureMode).|

## Yderligere information {#FurtherInformation}

Hvis du har brug for yderligere information eller hjælp til brugen af NVDA, besøg venligst [NVDAs websted](NVDA_URL).
Her kan du finde yderligere dokumentation, samt teknisk support og ressourcer.
Denne side indeholder også information vedrørende udviklingen af NVDA.
