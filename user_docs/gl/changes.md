# Que hai de Novo no NVDA

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

A tenda de complementos agora notificarache se calquera actualización de complemento está dispoñible ao comezar o NVDA.

Agora hai opcións para aplicar normalización Unicode á saída de voz e de braille.
Esto pode seren útil ao ler caracteres que sexan descoñecidos para un sintetizador de voz en particular ou unha táboa braille que teña unha alternativa compatible, coma os caracteres en negriña e en cursiva usados normalmente en redes sociais.
Tamén permite a lectura de ecuacións no editor de ecuacións de Microsoft Word.

Agora admítense as pantallas braille Help Tech Activator Pro.

Engadíronse ordes sen asignar para desprazar a roda do rato verticalmente e horizontalmente.

Hai varios arranxos de fallos, particularmente para o panel emoji de Windows 11 e para o histórico do portapapeis.
Para navegadores web, hai arranxos para o anunciado de mensaxes de erro, figuras, pes de foto, etiquetas de táboa e  elementos de menú con caixas de verificación e botóns de opción.

Liblouis actualizouse,  engadindo novas táboas braille para Serbio cirílico, Yiddish, varias linguas antigas, Turco e o alfabeto fonético internacional.
eSpeak actualizouse, engadindo soporte para a lingua Karakalpak.
Unicode CLDR tamén se actualizou.

### Novas Características

* Novas teclas de ordes:
  * Engadidas ordes sen asignar para o desprazamento vertical e horizontal da roda do rato, para mellorar a navegación en páxinas web e en aplicacións con contido dinámico, como Dism++. (#16462, @Cary-Rowen)
* Engadido soporte para normalización Unicode para a saída de voz e braille. (#11570, #16466 @LeonarddeR).
  * Esto pode seren útil ao ler caracteres que son descoñecidos para un sintetizador de voz en particular ou táboa braille e que teña unha alternativa compatible, como os caracteres en negriña e cursiva usados comúnmente en redes sociais.
  * Tamén permiten a lectura de ecuacións no editor de ecuacións de Microsoft Word. (#4631)
  * Podes abilitar esta funcionalidade para voz e braille nas súas respectivas categorías de opcións no diálogo de opcións do NVDA.
* Por defecto, despois de arrancar o NVDA, notificaráseche se calquera actualización de complemento está dispoñible. (#15035)
  * Esto pode desactivarse na categoría "Tenda de Complementos" das opcións.
  * O NVDA comproba diariamente as actualizacións de complementos.
  * Só se comprobarán as actualizacións dentro da mesma canle (ex.: os complementos beta instalados só se notificarán para as actualizacións na canle beta).
* Engadido soporte para as pantallas Help Tech Activator Pro. (#16668)

### Cambios

* Actualizacións de compoñentes:
  * eSpeak NG actualizouse a 1.52-dev commit `54ee11a79`. (#16495)
    * Engadida nova lingua Karakalpak.
  * Actualizado Unicode CLDR á versión 45.0. (#16507, @OzancanKaratas)
  * Actualizado fast_diff_match_patch (usado para detectar cambios en terminales e outro contido dinámico) á versión 2.1.0. (#16508, @codeofdusk)
  * Actualizado o transcriptor braille LibLouis a [3.30.0](https://github.com/liblouis/liblouis/releases/tag/v3.30.0). (#16652, @codeofdusk)
    * Novas táboas braille:
      * Serbio cirílico.
      * Yiddish.
      * Varias linguas antigas: hebreo bíblico, acadio, sirio, Ugarítico e texto cuneiforme transliteralizado.
      * Turco grao 2. (#16735)
      * Alfabeto Fonético Internacional. (#16773)
  * Actualizado NSIS a 3.10 (#16674, @dpy013)
  * Actualizado markdown a 3.6 (#16725, @dpy013)
  * Actualizado nh3 a 0.2.17 (#16725, @dpy013)
* A táboa de entrada de reserva agora é igual á táboa de saída de reserva, que é braille inglés unificado Código grao 1. (#9863, @JulienCochuyt, @LeonarddeR)
* O NVDA agora anunciará figuras sen fillos accesibles, pero con unha etiqueta ou descripción. (#14514)
* Ao se ler por liñas en modo exploración, "pe de foto" xa non se anuncia en cada liña de unha figura grande ou de pe de táboa. (#14874)
* Na consola Python, a última orde non executada xa non se perderá ao te mover polo histórico de entradas. (#16653, @CyrilleB79)
* Agora enbvíase un ID anónimo único coma parte da recopilación opcional de estadísticas de uso. (#16266)
* Por defecto, crearase un novo cartafol ao facer unha copia portable.
Unha mensaxe de advertencia avisarache se tentas escrebir nun directorio non valdeiro. (#16684)

### Arranxo de Erros

* Arranxos para Windows 11:
  * O NVDA xa non semellará atascarse ao pechar o histórico do portapapeis e o panel de emoji. (#16346, #16347, @josephsl)
  * O NVDA anunciará os candidatos visibles de novo ao abrir a interfaz IME. (#14023, @josephsl)
  * O NVDA xa non anunciará "histórico do portapapeis" dúas veces ao navegar polos elementos de menú do panel de emoji. (#16532, @josephsl)
  * O NVDA xa non cortará a fala e o braille ao revisar kaomojis e símbolos no panel de emoji. (#16533, @josephsl)
* Arranxos para o navegador web:
  * As mensaxes de erro referenciadas con `aria-errormessage` agora anúncianse en Google Chrome e en Mozilla Firefox. (#8318)
  * Se está presente, o NVDA agora usará `aria-labelledby` para proporcionar nomes acesibles para táboas en Mozilla Firefox. (#5183)
  * O NVDA anunciará correctamente elementos de menú con botóns de opción e caixas de verificación ao entrar por primeira vez en submenús en Google Chrome e en Mozilla Firefox. (#14550)
  * A funcionalidade de procura en modo exploración en NVDA agora é máis precisa cando a páxina contén emojis. (#16317, @LeonarddeR)
  * En Mozilla Firefox, o NVDA agora anuncia correctamente o carácter, palabra e liña actuais cando o cursor estea no punto de inserción ao remate dunha liña. (#3156, @jcsteh)
  * Xa non causa que Google Chrome se conxele ao pechar un documento ou ao saír de Chrome. (#16893)
* O NVDA anunciará correctamente o autocompletado de suxerencias en Eclipse e outros entornos baseados nel en Windows 11. (#16416, @thgcode)
* Mellorada a fiabilidade da lectura automática de texto, especialmente  en aplicacións de terminal. (#15850, #16027, @Danstiv)
* É posible unha vez máis reiniciar a configuración aos valores predeterminados de fábrica de xeito fiable. (#16755, @Emil-18)
* O NVDA anunciará correctamente os cambios de seleción ao editar unha celda de texto en Microsoft Excel. (#15843)
* En aplicacións que usen Java Access Bridge, o NVDA agora lerá correctamente a derradeira liña en branco dun texto a cambio de repetir a liña anterior. (#9376, @dmitrii-drobotov)
* En LibreOffice Writer (versión 24.8 e máis modernas), ao se conmutar o formateado de texto (negriña, cursiva, subliñado, subíndice/superíndice, alineamento) utilizando os atallos de teclado correspondentes, o NVDA anuncia o novo atributo de formato (ex.: "negriña activada", "negriña desactivada"). (#4248, @michaelweghorn)
* Ao navegar coas frechas en caixas de texto en aplicacións que usen UI Automation, o NVDA xa non anuncia ás veces o carácter, palábra, etc. erróneas (#16711, @jcsteh)
* Ao pegar na calculadora de Windows 10/11, o NVDA agora anuncia correctamente o número enteiro pegado. (#16573, @TristanBurchett)
* A fala xa non queda en silenzo despois de desconectarse e voltar a conectarse a unha sesión do Escritorio Remoto. (#16722, @jcsteh)
* Engadido soporte para ordes de revisión de texto para o nome dun obxecto en Visual Studio Code. (#16248, @Cary-Rowen)
* Reproducir sons de NVDA xa non falla nun dispositivo de audio mono. (#16770, @jcsteh)
* O NVDA anunciará os enderezos cando te movas coas frechas polos campos PARA/CC/BCC en outlook.com  e Outlook moderno. (#16856)
* O NVDA agora manexa os fallos de instalación de complementos con máis elegancia. (#16704)

### Cambios para Desenvolvedores

* O NVDA agora utiliza Ruff en lugar de flake8 para linting. (#14817)
* Arranxado o sistema de compilación para NVDA para que funcione correctamente cando se use Visual Studio 2022 versión 17.10 e superiores. (#16480, @LeonarddeR)
* Agora úsase unha fonte de ancho fixo no Visualizador de Rexistro e na Consola Python de NVDA para que o cursor permaneza na mesma columna durante a navegación vertical.
É especialmente útil para ler os marcadores de localización de erros nos tracebacks. (#16321, @CyrilleB79)
* Engadiuse o soporte para as táboas braille persoalizadas. (#3304, #16208, @JulienCochuyt, @LeonarddeR)
  * As táboas poden proporcionarse no cartafol `brailleTables` nun paquete de complemento.
  * Os metadatos da táboa poden engadirse a unha seción opcional `brailleTables` no manifesto do complemento ou nun ficheiro `.ini` co mesmo formato atopado no subdirectorio brailleTables do directorio scratchpad.
  * Por favor consulta a [seción braille translation tables na guía do desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#BrailleTables) para máis detalles.
* Cando se pon en cola un evento `gainFocus` cun obxecto que ten unha propiedade `focusRedirect` válida, o obxecto apuntado pola propiedade `focusRedirect` é agora mantido por `eventHandler.lastQueuedFocusObject`, a cambio do obxecto posto en cola orixinalmente. (#15843)
* O NVDA rexistrará a súa arquitectura executable (x86) ao se  iniciar. (#16432, @josephsl)
* `wx.CallAfter`, que está envolto en  `monkeyPatches/wxMonkeyPatches.py`, agora inclúe a indicación apropriada `functools.wraps`. (#16520, @XLTechie)
* Hai un novo módulo para programar tarefas `utils.schedule`, usando o módulo pip `schedule`. (#16636)
  * Podes usar `scheduleThread.scheduleDailyJobAtStartUp` para programar automáticamente un traballo que ocorra despois de que o NVDA arranque, e cada 24 hhoras despois deso.
  Os traballos prográmanse cun retraso para evitar conflictos.
  * `scheduleThread.scheduleDailyJob` e `scheduleJob` pódense usar para programar traballos en tempos persoalizados, onde un `JobClashError` activarase cando se coñeza un conflicto na programación dun traballo.
* Agora é posible crear app modules para aplicacións aloxando controis WebView2 (msedgewebview2.exe). (#16705, @josephsl)

## 2024.2

Hai unha característica nova chamada separación de son.
Esto permite separar os sons do NVDA nunha canle (ex: a esquerda) mentres os sons de todas as demáis aplicacións colócanse na outra canle (ex.: a dereita).

Hai novas ordes para modificar as opcións do anel do sintetizador, permitindo aos usuarios saltar cara a primeira ou cara a última opción, e aumentar ou diminuir a opción actual en pasos máis longos.
Tamén hai novas ordes de navegación rápida, permitindo aos usuarios vincular xestos para saltar rápidamente entre: parágrafo, parágrafo aliñado verticalmente, mesmo estilo de texto, diferente estilo de texto, elemento de menú, botón conmutable, barra de progreso, figura e fórmula matemática.

Hai moitas características braille novas e arranxos de erros.
Engadiuse un novo modo braille chamado "amosar saída de fala".
Cando estea activo, a pantalla braille amosa exactamente o que o NVDA vaia a falar.
Tamén se engadíu o soporte para as pantallas BrailleEdgeS2 e BrailleEdgeS3.
LibLouis actualizouse, engadindo as novas táboas braille detalladas (con letras maiúsculas indicadas) para bieloruso e ucraniano, unha táboa lao e unha táboa en español para ler texto en grego.

eSpeak actualizouse, engadindo a nova lingua Tigrinya.

Hai moitos outros arranxos menores de fallos para aplicacións como Thunderbird, Adobe Reader, navegadores web, Nudi e Geekbench.

### Novas Características

* Novas teclas de ordes:
  * Nova orde de navegación rápida `p` para saltar ao seguinte e anterior parágrafo de texto en modo exploración. (#15998, @mltony)
  * Novas ordes de navegación rápida non asignadas, que poden usarse para saltar ao seguinte e anterior:
    * figura (#10826)
    * parágrafo aliñado verticalmente (#15999, @mltony)
    * elemento de menú (#16001, @mltony)
    * botón conmutable (#16001, @mltony)
    * barra de progreso (#16001, @mltony)
    * fórmula matemática (#16001, @mltony)
    * mesmo estilo de texto (#16000, @mltony)
    * diferente estilo de texto (#16000, @mltony)
  * Engadidas ordes para saltar cara a á primeira, última, adiante e atrás polas opcións do anel do sintetizador. (#13768, #16095, @rmcpantoja)
    * Estabrecer a opción primeira e última no anel do sintetizador non ten xesto asignado. (#13768)
    * Diminuir e aumentar a opción actual do anel de opcións do sintetizador en pasos longos (#13768):
      * Escritorio: `NVDA+control+rePáx` e `NVDA+control+avPáx`.
      * Portátil: `NVDA+control+shift+rePáx` e `NVDA+control+shift+avPáx`.
  * Engadido un novo xesto de entrada non asignado para conmutar o anunciado de figuras e pes de foto. (#10826, #14349)
* Braille:
  * Engadido o soporte para as pantallas braille BrailleEdgeS2 e BrailleEdgeS3. (#16033, #16279, @EdKweon)
  * Engadiuse un novo modo braille chamado "amosar saída de fala". (#15898, @Emil-18)
    * Cando se activa, a pantalla braille amosa exactamente o que o NVDA vai falar.
    * Pode conmutarse premendo `NVDA+alt+t`, ou dende o diálogo Opcións de Braille.
* Separación de son: (#12985, @mltony)
  * Permite separar sons do NVDA nunha canle (ex.: esquerda) mentres os sons das demáis aplicacións se colocan na outra canle (ex.: dereita).
  * Conmutado con `NVDA+alt+s`.
* Agora admítese o anunciado de cabeceiras de fila e de columna en elementos HTML contenteditable. (#14113)
* Engadida unha opción para deshabilitar o anunciado de figuras e pes de foto nas opcións de formateado de documentos. (#10826, #14349)
* En Windows 11, o NVDA anunciará alertas dende a escritura de voz e accións suxeridas incluindo a suxerencia superior ao copiar datos como números de teléfono ao portapapeis (Windows 11 2022 Update e posterior). (#16009, @josephsl)
* O NVDA manterá o dispositivo de audio activo despois de que se deteña a fala para evitar que  se corte o comezo da seguinte fala con algúns dispositivos de audio como auriculares bluetooth. (#14386, @jcsteh, @mltony)
* Agora sopórtase HP Secure Browser. (#16377)

### Cambios

* Tenda de Complementos:
  * A versión mínima e a última comprobada de NVDA para un complemento agora amósanse na área "outros detalles". (#15776, @Nael-Sayegh)
  * A acción reseñas da comunidade estará dispoñible en todas as pestanas da tenda. (#16179, @nvdaes)
* Actualización de compoñentes:
  * Actualizado o transcriptor braille LibLouis a [3.29.0](https://github.com/liblouis/liblouis/releases/tag/v3.29.0). (#16259, @codeofdusk)
    * Novas táboas detalladas braille (con letras maiúsculas indicadas) para bieloruso e ucraniano.
    * Nova táboa braille española para ler textos en grego.
    * Nova táboa para Lao grao 1.
  * eSpeak NG actualizouse a 1.52-dev commit `cb62d93fd7`. (#15913)
    * Engadida nova lingua Tigrinya.
* Cambiáronse varios xestos para dispositivos BrailleSense para evitar conflictos con caracteres da táboa braille francesa. (#15306)
  * `alt+frecha esquerda` agora asígnase a `punto2+punto7+espazo`
  * `alt+frecha dereita` agora asígnase a `punto5+punto7+espazo`
  * `alt+frecha arriba` agora asígnase a `punto2+punto3+punto7+espazo`
  * `alt+frecha abaixo` agora asígnase a `punto5+punto6+punto7+espazo`
* Os puntos de recheo usados habitualmente nos índices xa non se indican nos niveis de puntuación baixa. (#15845, @CyrilleB79)

### Arranxo de Erros

* Arranxos para Windows 11:
  * o NVDA voltará a anunciar as suxerencias de entrada de teclado por hardware. (#16283, @josephsl)
  * Na Versión 24H2 (actualización de 2024 e Windows Server 2025), a interacción co rato e tactil pode usarse en axustes rápidos. (#16348, @josephsl)
* Tenda de Complementos:
  * Ao se premer `ctrl+tab`, o foco móvese apropriadamente cara o título da pestana actual. (#14986, @ABuffEr)
  * Se os ficheiros de caché non son correctos, o NVDA xa non se reiniciará. (#16362, @nvdaes)
* Arranxos para navegadores web baseados en Chromium cando se usan con UIA:
  * Arranxados erros que provocan que o NVDA se colgue. (#16393, #16394)
  * A tecla retroceso agora funciona correctamente en campos de inicio de sesión en Gmail. (#16395)
* O retroceso agora funciona correctamente ao usar Nudi 6.1 coa opción de NVDA "Manexar teclas de outras aplicacións" habilitada. (#15822, @jcsteh)
* Arranxado un erro onde as cordinadas de audio se reproducían mentres a aplicación estaba en modo durminte cando "Reproducir cordinadas de audio ao mover o rato" estea activada. (#8059, @hwf1324)
* En Adobe Reader, o NVDA xa non ignora o texto alternativo nas fórmulas en PDFs. (#12715)
* Arranxado un erro que causa que o NVDA falle ao ler a cinta e as opcións dentro de Geekbench. (#16251, @mzanm)
* Arranxado un caso pouco frecuente no que ao se gardar a configuración podía fallar o gardado de todos os perfís. (#16343, @CyrilleB79)
* En Firefox e navegadores baseados en Chromium, o NVDA entrará correctamente en modo foco ao premer intro cando se posicione dentro dunha listaxe de presentación (ul / ol) dentro de contido editable. (#16325)
* O cambio de estado de columna notifícase agora corectamente ao selecionar as columnas que se amosarán na listaxe de mensaxes de Thunderbird. (#16323)
* O conmutador de liña de ordes `-h`/`--help` funciona apropriadamente de novo. (#16522, @XLTechie)
* O soporte de NVDA para o software de tradución Poedit versión 3.4 ou superior funciona corectamente ao traducir linguas con 1 ou máis de 2 formas plurais (ex.: Chinés, Polaco). (#16318)

### Cambios para desenvolvedores

Por favor consulta [a guía do desenvolvedor ](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre obsolescencias da API do NVDA e o proceso de eliminación.

* Aa instanciación de obxectos `winVersion.WinVersion` con versións de Windows descoñecidas por enriba de 10.0.22000 como 10.0.25398 devolve "Windows 11 unknown" en lugar de "Windows 10 unknown" para o nome de versión. (#15992, @josephsl)
* Facilítase o proceso de compilación de AppVeyor para as bifurcacións de NVDA, engadindo variables configurables en appveyor.yml para deshabilitar ou modificar partes específicas dos scripts de compilación de NV Access. (#16216, @XLTechie)
* Engadido un documento how-to, explicando o proceso de compilación das bifurcacións do NVDA en AppVeyor. (#16293, @XLTechie)

## 2024.1

Engaiduse un novo modo de voz "baixo demanda".
Cando a voz estea baixo demanda, o NVDA non fala automáticamente (ex. ao mover o cursor) pero aínda fala ao daren ordes cuxo obxetivo sexa explícitamente anunciar algo (ex. anunciar o título da xanela).
Na categoría Voz das opcións do NVDA, agora é posible excluir modos de voz non desexados dende a orde percorrer modos de voz (`NVDA+s`).

Un novo modo de seleción nativa (conmutado con `NVDA+shift+f10`) agora está dispoñible no modo exploración de NVDA para Mozilla Firefox.
Cando se active, selecionar texto en modo exploración tamén manipulará a propria seleción nativa en Firefox.
Copiar o texto con `control+c` pasará directamente a Firefox, copiando así o contido enriquecido, a cambio da representación en texsto cha do NVDA.

A Tenda de Complementos agora admite acións masivas (ex. instalar, habilitar complementos) selecionando varios complementos
Hai unha nova ación para abrir unha páxina de reseñas para o complemento selecionado.

As opcións dispositivo de saída audio e  modo de atenuación borráronse do diálogo "Selecionar Sintetizador".
Agora poden atoparse no panel de opcións de audio o que se pode abrir con `NVDA+control+u`.

Actualizáronse eSpeak-NG, o transcriptor braille Liblouis e o Unicode CLDR.
Están dispoñibles novas táboas braille Thai, Filipino e Romanés.

Hai moitos outros fallos arranxados, particularmente para a Tenda de Complementos, para o braille, para Libre Office, para Microsoft Office e para o audio.

### Notas importantes

* Esta versión rompe a compatibilidade cos complementos existentes.
* Xa non se soportan Windows 7 e Windows 8.
Windows 8.1 é a versión mínima soportada.

### Novas Características

* Tenda de Complementos:
  * A Tenda de Complementos agora admite acións masivas (ex. instalar, habilitar complementos) selecionando varios complementos. (#15350, #15623, @CyrilleB79)
  * Engadiuse unha nova ación para abrir unha páxina web dedicada para ver ou proporcionar comentarios acerca do complemento selecionado. (#15576, @nvdaes)
* Engadido o soporte para pantallas braille Bluetooth Low Energy HID. (#15470)
* Un novo modo de seleción nativa (conmutado con `NVDA+shift+f10`) agora está dispoñible no modo exploración de NVDA para Mozilla Firefox.
Cando se active, selecionar texto en modo exploración tamén manipulará a propria seleción nativa en Firefox.
Copiar o texto con `control+c` pasará directamente a Firefox, copiando así o contido enriquecido, a cambio da representación en texsto cha de NVDA.
Ten en conta sen embargo que coma o Firefox está a manexar a copia real, o NVDA non anunciará unha mensaxe "copiar ao portapapeis" neste modo. (#15830)
* Ao se copiar texto en Microsoft Word co modo exploración de NVDA activado, agora inclúese tamén o formato.
Un efecto secundario desto é que o NVDA xa non anunciará unha mensaxe "copiar ao portapapeis" ao premer `control+c` no modo exploración en Microsoft Word e en Outlook, xa que a aplicación é a que agora manexa o copiado, non NVDA. (#16129)
* Engadiuse un novo modo de voz "baixo demanda".
Cando a voz estea baixo demanda, o NVDA non fala automáticamente (ex. ao se mover o cursor) pero aínda fala ao se dar ordes cuxo obxetivo sexa explícitamente anunciar algo (ex. anunciar o título da xanela). (#481, @CyrilleB79)
* Na categoría Voz das opcións de NVDA, agora é posible excluir modos de voz non desexados dende a orde percorrer modos de voz (`NVDA+s`). (#15806, @lukaszgo1)
  * Se usas actualmente o complemento NoBeepsSpeechMode prantéxate desinstalalo e deshabilitar os modos "pitidos" e "baixo demanda" nas opcións.

### Cambios

* O NVDA xa non soporta Windows 7 e Windows 8.
Windows 8.1 é a versión mínima soportada. (#15544)
* Actualización de componentes:
  * Actualizado o transcriptor braille LibLouis a [3.28.0](https://github.com/liblouis/liblouis/releases/tag/v3.28.0). (#15435, #15876, @codeofdusk)
    * Engadidas novas táboas braille para Thai, Romanés e Filipino.
  * eSpeak NG foi actualizado a 1.52-dev commit `530bf0abf`. (#15036)
  * CLDR emoji y symbol annotations foron actualizados á versión 44.0. (#15712, @OzancanKaratas)
  * Actualizado Java Access Bridge a 17.0.9+8Zulu (17.46.19). (#15744)
* Teclas de ordes:
  * As seguintes ordes agora admiten dúas e tres pulsacións para deletrear a información anunciada e para deletrear con descripción de caracteres: anunciar selección, anunciar texto do portapapeis e anunciar obxecto enfocado. (#15449, @CyrilleB79)
  * A orde para conmutar a Cortina de Pantalla agora ten un xesto predeterminado: `NVDA+control+escape`. (#10560, @CyrilleB79)
  * Ao premer catro veces, a orde de anunciar seleción agora amosa a seleción nunha mensaxe explorable. (#15858, @Emil-18)
* Microsoft Office:
  * Ao se solicitar información de formato en celdas de Excel, marxes e fondo só se anunciará se hai ese formato. (#15560, @CyrilleB79)
  * O NVDA non anunciará de novo grupos non etiquetados coma en menús en versións recentes de Microsoft Office 365. (#15638)
* As opcións dispositivo de saída audio e  modo de atenuación borráronse do diálogo "Selecionar Sintetizador".
Agora poden atoparse no panel de opcións de audio o que se pode abrir con `NVDA+control+u`. (#15512, @codeofdusk)
* A opción "Anunciar rol cando o rato entre no obxecto" na categoría opcións de Rato do NVDA renomeouse a "Anunciar obxecto cando o rato entre nel".
Esta opción agora anuncia información importante adicional acerca dun obxecto cando o rato entre nel, como os estados  (marcado/premedo) ou cordinadas de celda nunha táboa. (#15420, @LeonarddeR)
* Engadíronse novos elementos ao menú Axuda para a páxina "Obter Axuda" e para a tenda de NV Access. (#14631)
* O soporte do NVDA para [Poedit](https://poedit.net) foi revisado para Poedit versión 3 e superiores.
Recoméndase moito aos usuarios de Poedit 1 que actualicen a Poedit 3 se queren contar coa accesibilidade mellorada en Poedit, coma os atallos para ler as notas e os comentarios para o traductor. (#15313, #7303, @LeonarddeR)
* O visualizador Braille e o visualizador de voz agora desactiváronse en modo seguro. (#15680)
* Durante a navegación de obxectos, os obxectos deshabilitados (non dispoñibles) xa non se ignorarán. (#15477, @CyrilleB79)
* Engadido un índice ao documento de ordes chave. (#16106)

### Arranxo de Fallos

* Tenda de Complementos:
  * Cando se cambie o estado dun complemento mentres teña o foco, ex. un cambio de "descargando" a "descargado", o elemento actualizado agora anúnciase correctamente. (#15859, @LeonarddeR)
  * Ao instalar complementos, os avisos de instalación xa non se solapan co diálogo de reinicio. (#15613, @lukaszgo1)
  * Ao reinstalar un complemento incompatible, xa non se desactiva forzosamente. (#15584, @lukaszgo1)
  * Os complementos deshabilitados e incompatibles agora pódense actualizar. (#15568, #15029)
  * O NVDA agora recupérase e amosa un erro en caso de que un complemento non se descargue correctamente. (#15796)
  * O NVDA xa non falla ao se reiniciar intermitentemente despois de abrir e pechar a Tenda de Complementos. (#16019, @lukaszgo1)
* Audio:
  * O NVDA xa non se conxela brevemente cando se reproducen varios sons en sucesión rápida. (#15311, #15757, @jcsteh)
  * Se o dispositivo de saída de audio está configurado a algo distinto do predeterminado e ese dispositivo voltara a estar dispoñible despois de non estalo, o NVDA agora cambiará novamente ao dispositivo configurado a cambio de seguir usando o predeterminado. (#15759, @jcsteh)
  * O NVDA agora reanuda el audio se a configuración do dispositivo cambia ou outra aplicación libera o control exclusivo do dispositivo. (#15758, #15775, @jcsteh)
* Braille:
  * As pantallas braille con varias liñas xa non bloquearán o controlador BRLTTY e trataranse coma unha pantalla contínua. (#15386)
  * Detéctanse máis obxectos que conteñen texto útil e o contido do texto amósase en braille. (#15605)
  * A entrada de braille contraído volta a funcionar correctamente. (#15773, @aaclause)
  * O braille agora actualízase ao mover el navegador de obxectos entre celdas de táboa táboa en máis situacións. (#15755, @Emil-18)
  * Agora amósase en braille o resultado das ordes anunciar foco actual, navegador de obxectos actual e seleción actual. (#15844, @Emil-18)
  * O controlador braille da Albatross xa non manexa un microcontrolador Esp32 coma unha pantalla Albatross. (#15671)
* LibreOffice:
  * As palabras borradas usando o atallo de teclado `control+retroceso` agora tamén se anuncian apropriadamente cando as palabras borradas van seguidas de espazos en branco(coma espazos e tabuladores). (#15436, @michaelweghorn)
  * O anuncio da barra de estado usando o atallo de teclado `NVDA+fin` agora tamén funciona para diálogos en LibreOffice versión 24.2 e posteriores. (#15591, @michaelweghorn)
  * Agora admítense todos os atributos de texto esperados nas versións de LibreOffice 24.2 e superiores.
  Esto fai que o anunciado de erros de ortografía funcione ao anunciar unha liña en Writer. (#15648, @michaelweghorn)
  * O anunciado de niveis de encabezado agora tamén funciona para LibreOffice versións 24.2 e posteriores. (#15881, @michaelweghorn)
* Microsoft Office:
  * En Excel con UIA deshabilitado, o braille actualízase e fálase a celda activa cando se prema `control+y`, `control+z` ou `alt+retroceso`. (#15547)
  * En Word con UIA deshabilitado o braille actualízase cando se prema `control+v`, `control+x`, `control+y`, `control+z`, `alt+retroceso`, `retroceso` ou `control+retroceso`.
  Tamén se actualiza con UIA habilitado cando se teclea texto e o braille siga aos cursores de revisión e do sistema. (#3276)
  * En Word, agora anunciarase correctamente a celda onde se aterrice cando se utilicen as ordes nativas de Word para a navegación de táboa `alt+inicio`, `alt+fin`, `alt+rePág` e `alt+avPág`. (#15805, @CyrilleB79)
* Mellorouse o anunciado dos atallos de teclado dos obxectos. (#10807, #15816, @CyrilleB79)
* O sintetizador de voz SAPI4 agora soporta correctamente  os cambios de volume, velocidade e ton integrados na voz. (#15271, @LeonarddeR)
* Agora anúnciase correctamente o estado multiliña en aplicacións que utilizan Access Bridge. (#14609)
* O NVDA anunciará contido de diálogo para máis diálogos en Windows 10 y 11. (#15729, @josephsl)
* O NVDA xa non fallará ao ler unha páxina recén cargada en Microsoft Edge ao usar  UI Automation. (#15736)
* Cando se usa ler utodo ou ordes que deletreen testo, as pausas entre frases ou caracteres xa non disminúen gradualmente co tempo. (#15739, @jcsteh)
* O NVDA xa non se conxela ás veces cando se fala unha grande cantidade de texto. (#15752, @jcsteh)
* Ao acesar a Microsoft Edge utilizando UI Automation, o NVDA pode activar máis controis en modo exploración. (#14612)
* O NVDA xa non fallará ao arrancar cando o ficheiro de configuración estea corrompido, senon que restaurará a configuración á predeterminada coma o facía no pasado. (#15690, @CyrilleB79)
* Arranxado o soporte para os controis System List view (`SysListView32`) en aplicacións Windows Forms. (#15283, @LeonarddeR)
* Xa non é posible sobrescribir o historial da consola Python do NVDA. (#15792, @CyrilleB79)
* O NVDA debería continuar respondendo cando se inunda con moitos eventos UI Automation, ex. cando se imprimen grandes anacos de texto nunha terminal ou cando se escoitan mensaxes de voz en WhatsApp messenger. (#14888, #15169)
  * Este novo comportamento pódese deshabilitar utilizando a nova opción "Utilizar proceso mellorado de eventos" nas opcións avanzadas de NVDA.
* O NVDA é capaz de novo de seguir o foco en aplicacións que se executen dentro de Windows Defender Application Guard (WDAG). (#15164)
* O texto falado xa non se actualiza cando o rato se move no Visualizador de Voz. (#15952, @hwf1324)
* O NVDA voltará a cambiar ao modo exploración ao pechar caixas combinadas con `escape` ou `alt+Frecha arriba` en Firefox ou Chrome. (#15653)
* Moverse arriba e abaixo coas frechas en caixas combinadas en iTunes xa non cambiará inapropriadamente a modo exploración. (#15653)

### Cambios para Desenvolvedores

Por favor consulta [a guía do desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre o proceso de obsolescencia e eliminación da API de NVDA.

* Nota: esta é unha versión que rompe a compatibilidade coa API de complementos.
Os complementos necesitarán voltar a comprobarse e ter os seus manifestos actualizados.
* Compilar NVDA ahora require de Visual Studio 2022.
Por favor consulta os [NVDA docs](https://github.com/nvaccess/nvda/blob/release-2024.1/projectDocs/dev/createDevEnvironment.md) para unha listaxe específica de compoñentes de Visual Studio. (#14313)
* Engadidos os seguintes puntos de extensión:
  * `treeInterceptorHandler.post_browseModeStateChange`. (#14969, @nvdaes)
  * `speech.speechCanceled`. (#15700, @LeonarddeR)
  * `_onErrorSoundRequested` (debería recuperarse chamando `logHandler.getOnErrorSoundRequested()`) (#15691, @CyrilleB79)
* Agora é posible utilizar formas plurais nas traducións de complementos. (#15661, @beqabeqa473)
* Incluido python3.dll na distribución de binarios para usar por complementos con librerías externas utilizando a [stable ABI](https://docs.python.org/3.11/c-api/stable.html). (#15674, @mzanm)
* A crase base `BrailleDisplayDriver` agora ten as propriedades `numRows` e `numCols` para proporcionar información sobre pantallas braille de varias liñas.
A configuración de `numCells` aínda está admitida para pantallas braille de unha soa liña e `numCells` devolverá o número total de celdas para pantallas braille de varias liñas. (#15386)
* Actualizado BrlAPI para BRLTTY á versión 0.8.5 e o seu correspondente módulo python á compilación compatible Python 3.11. (#15652, @LeonarddeR)
* Engadida a función `speech.speakSsml`, que che permite escrebir secuencias de voz de NVDA utilizando [SSML](https://www.w3.org/TR/speech-synthesis11/). (#15699, @LeonarddeR)
  * As seguintes etiquetas admítense actualmente e tradúcense ás ordes de voz  apropriadas de NVDA:
    * `Prosody` (`pitch`, `rate` e `volume`). só multiplicación (ex. `200%` se soporta.
    * `say-as` co atributo `interpret` configurado a `characters`
    * `voice` co `xml:lang` configurado a unha linguaxe XML
    * `break` co atributo `time` configurado a un valor en milésimas de segundo, ex. `200ms`
    * `mark` co atributo `name` configurado a un nome de marca, ex. `mark1`, require proporcionar unha callback
  * Exemplo: `speech.speakSsml('<speak><prosody pitch="200%">hello</prosody><break time="500ms" /><prosody rate="50%">John</prosody></speak>')`
  * As funcións de análise sintáctico de SSML están respaldadas pola crase `SsmlParser` no módulo `speechXml`.
* Cambios para a librería NVDA Controller Client:
  * Os nomes de ficheiro da libraría xa non conteñen un sufixo denotando a arquitectura, é dicir, `nvdaControllerClient32/64.dll` agora chámase `nvdaControllerClient.dll`. (#15718, #15717, @LeonarddeR)
  * Engadido un exemplo para demostrar o uso de nvdaControllerClient.dll dende Rust. (#15771, @LeonarddeR)
  * Engadidas as seguintes funcións ao controller client: (#15734, #11028, #5638, @LeonarddeR)
    * `nvdaController_getProcessId`: para obter o id de proceso (PID) da instancia actual que está utilizando o NVDA controller client.
    * `nvdaController_speakSsml`: para instruir ao NVDA que fale de acordo co SSML dado. Esta función tamén soporta:
      * Proporcionar o nivel de símbolos.
      * Proporcionar a prioridade da voz a seren falada.
      * Falar síncronamente (bloqueando) e asíncronamente (devolución instantánea).
    * `nvdaController_setOnSsmlMarkReachedCallback`: Para rexistrar unha chamada de tipo `onSsmlMarkReachedFuncType` eso chámase en modo síncrono para cada `<mark />` tag atopado na secuencia SSML proporcionada a `nvdaController_speakSsml`.
  * Nota: as funcións novas no controller client só soportan NVDA 2024.1 e posteriores.
* Actualizadas dependencias `include`:
  * detours a `4b8c659f549b0ab21cf649377c7a84eb708f5e68`. (#15695)
  * ia2 a `3d8c7f0b833453f761ded6b12d8be431507bfe0b`. (#15695)
  * sonic a `8694c596378c24e340c09ff2cd47c065494233f1`. (#15695)
  * w3c-aria-practices a `9a5e55ccbeb0f1bf92b6127c9865da8426d1c864`. (#15695)
  * wil a `5e9be7b2d2fe3834a7107f430f7d4c0631f69833`. (#15695)
* Información do dispositivo por `hwPortUtils.listUsbDevices` agora contén o bus que anuncia a descripción do dispositivo USB (key `busReportedDeviceDescription`). (#15764, @LeonarddeR)
* Para dispositivos USB serie, `bdDetect.getConnectedUsbDevicesForDriver` e `bdDetect.getDriversForConnectedUsbDevices` agora produce coincidencias de dispositivo que conteñen un diccionario `deviceInfo` enriquecido con datos sobre o dispositivo USB, como `busReportedDeviceDescription`. (#15764, @LeonarddeR)
* Cando o ficheiro de configuración `nvda.ini` está corrompido, gárdase unha copia de seguridade antes de reiniciarse. (#15779, @CyrilleB79)
* Cando se define un script co decorador de script, o argumento booleano `speakOnDemand` pode especificarse para controlar se un script debería falar mentres se estea no modo de voz "baixo demanda". (#481, @CyrilleB79)
  * Os Scripts que proporcionan información (ex. dicir título de xanela, anunciar hora/data) deberían falar no modo de voz "baixo demanda".
  * Os Scripts que realicen unha ación (ex. mover o cursor, cambiar un parámetro) non deberían falarse no modo "baixo demanda".
* Arranxado un fallo onde ao eliminar ficheiros git-tracked durante `scons -c` resultaba en falta de interfaces UIA COM ao recompilar. (#7070, #10833, @hwf1324)
* Arranxado un fallo onde algúns cambios de código non se detectaban ao compilar `dist`, o que impedía que se activara unha nova compilación.
Agora `dist` sempre recompila. (#13372, @hwf1324)
* Un `gui.nvdaControls.MessageDialog` cun tipo predeterminado de estándar, xa non lanza unha excepción de conversión none porque non se asignara ningún son. (#16223, @XLTechie)

#### Cambios que Rompen a API

Estos son os cambios que rompen a API.
Por favor abre un GitHub issue si o teu complemento ten un problema coa actualización á nova API.

* NVDA agora compílase con Python 3.11. (#12064)
* Actualizadas as dependencias pip:
  * configobj a 5.1.0dev commit `e2ba4457c4651fa54f8d59d8dcdd3da950e956b8`. (#15544)
  * Comtypes a 1.2.0. (#15513, @codeofdusk)
  * Flake8 a 4.0.1. (#15636, @lukaszgo1)
  * py2exe a 0.13.0.1dev commit `4e7b2b2c60face592e67cb1bc935172a20fa371d`. (#15544)
  * robotframework a 6.1.1. (#15544)
  * SCons a 4.5.2. (#15529, @LeonarddeR)
  * sphinx a 7.2.6. (#15544)
  * wxPython a 4.2.2a commit `0205c7c1b9022a5de3e3543f9304cfe53a32b488`. (#12551, #16257)
* Dependencias pip eliminadas:
  * typing_extensions, estas soportaríase nativamente en Python 3.11 (#15544)
  * nota, a cambio úsase unittest-xml-reporting para xerar informes XML. (#15544)
* `IAccessibleHandler.SecureDesktopNVDAObject` eliminouse.
A cambio, cando o NVDA está en execución no perfil de usuario, rastrea a existencia do escritorio seguro co punto de extensión: `winAPI.secureDesktop.post_secureDesktopStateChange`. (#14488)
* `braille.BrailleHandler.handlePendingCaretUpdate` eliminouse sen remprazo público. (#15163, @LeonarddeR)
* `bdDetect.addUsbDevices e bdDetect.addBluetoothDevices` borráronse.
Os controladores de pantallas braille deberían implementar o método da crase `registerAutomaticDetection` a cambio.
Ese método recibe un obxecto `DriverRegistrar` no que os métodos `addUsbDevices` e `addBluetoothDevices` poden usarse. (#15200, @LeonarddeR)
* A implementación predeterminada do método de  comprobación en `BrailleDisplayDriver` agora require que os atributos `threadSafe` e `supportsAutomaticDetection` estean configurados a `True`. (#15200, @LeonarddeR)
* Pasar funciones lambda a `hwIo.ioThread.IoThread.queueAsApc` xa non é posible, xa que as funcións deberían ser débilmente referenciables. (#14627, @LeonarddeR)
* `IoThread.autoDeleteApcReference` foi eliminada. (#14924, @LeonarddeR)
* Para admitir cambios de tons para maiúsculas, os sintetizadores deben declarar agora explícitamente a súa compatibilidade con `PitchCommand` no atributo `supportedCommands` no controlador. (#15433, @LeonarddeR)
* `speechDictHandler.speechDictVars` eliminouse. Utiliza `NVDAState.WritePaths.speechDictsDir` a cambio de `speechDictHandler.speechDictVars.speechDictsPath`. (#15614, @lukaszgo1)
* `languageHandler.makeNpgettext` e `languageHandler.makePgettext` elimináronse.
`npgettext` e `pgettext` agora sopórtanse nativamente. (#15546)
* O app module para [Poedit](https://poedit.net) foi cambiado significativamente. A función `fetchObject` function eliminouse. (#15313, #7303, @LeonarddeR)
* Os seguintes tipos e constantes redundantes borráronse de `hwPortUtils`: (#15764, @LeonarddeR)
  * `PCWSTR`
  * `HWND` (remprazado por `ctypes.wintypes.HWND`)
  * `ULONG_PTR`
  * `ULONGLONG`
  * `NULL`
  * `GUID` (remprazado por `comtypes.GUID`)
* `gui.addonGui.AddonsDialog` eliminouse. (#15834)
* `touchHandler.TouchInputGesture.multiFingerActionLabel` eliminouse sen remprazo. (#15864, @CyrilleB79)
* `NVDAObjects.IAccessible.winword.WordDocument.script_reportCurrentHeaders` eliminouse sen remprazo. (#15904, @CyrilleB79)
* Os seguintes app modules elimináronse.
O código que importe dun deles debería importar dos seus substitutos. (#15618, @lukaszgo1)

| Nome do módulo eliminado |Módulo de remprazo|
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

#### Obsolescencias

* Utilizar `watchdog.getFormattedStacksForAllThreads` está obsoleto - por favor utiliza `logHandler.getFormattedStacksForAllThreads` a cambio. (#15616, @lukaszgo1)
* `easeOfAccess.canConfigTerminateOnDesktopSwitch` quedou obsoleto, xa que quedou obsoleto ao se rematar o soporte de Windows 7. (#15644, @LeonarddeR)
* `winVersion.isFullScreenMagnificationAvailable` quedou obsoleto - utiliza `visionEnhancementProviders.screenCurtain.ScreenCurtainProvider.canStart` a cambio. (#15664, @josephsl)
* As seguintes constantes de versión de Windows quedaron obsoletas do módulo winVersion (#15647, @josephsl):
  * `winVersion.WIN7`
  * `winVersion.WIN7_SP1`
  * `winVersion.WIN8`
* As constantes `bdDetect.KEY_*` quedaron obsoletas.
Utiliza `bdDetect.DeviceType.*` a cambio. (#15772, @LeonarddeR).
* As constantes `bdDetect.DETECT_USB` e `bdDetect.DETECT_BLUETOOTH` quedaron obsoletas sen remprazo público. (#15772, @LeonarddeR).
* Utilizar `gui.ExecAndPump` está obsoleto - por favor usa `systemUtils.ExecAndPump` a cambio. (#15852, @lukaszgo1)

## 2023.3.4

Este é un parche para arranxar un fallo de seguridade e un fallo do instalador.
Por favor comunica responsablemente os problemas de seguridade seguindo as [políticas de seguridade do NVDA](https://github.com/nvaccess/nvda/blob/master/security.md).

### Arranxos de segruridade

* Evita cargar a configuración persoalizada mentres se forza o modo seguro .
([GHSA-727q-h8j2-6p45](https://github.com/nvaccess/nvda/security/advisories/GHSA-727q-h8j2-6p45))

### Arranxo de Fallos

* Arranxado un fallo que provocaba que o proceso de NVDA fallase ao non saír correctamente.
* Arránxase un erro onde Ao se executar o instalador, provocaba que a instalación entrase nun estado irrecuperable. (#16122, #16123)

## 2023.3.3

Trátase dun parche para solucionar un problema de seguridade.
Por favor revela responsablemente os problemas de seguridade seguindo as [políticas de seguridade](https://github.com/nvaccess/nvda/blob/master/security.md) do NVDA.

### Arranxos de seguridade

* Evita un posible ataque XSS reflectido a partir de contido crafteado para provocar a execución de código arbitrario.
([GHSA-xg6w-23rw-39r8](https://github.com/nvaccess/nvda/security/advisories/GHSA-xg6w-23rw-39r8))

## 2023.3.2

Trátase dun parche para solucionar un problema de seguridade.
O parche de seguridade en 2023.3.1 non se resolveu correctamente.
Por favor revela responsablemente os problemas de seguridade seguindo as [políticas de seguridade](https://github.com/nvaccess/nvda/blob/master/security.md) do NVDA.

### Arranxos de Seguridade

* O parche de seguridade en 2023.3.1 non se resolveu correctamente.
Evita o posible acceso ao sistema e a execución de código arbitrario con privilexios do sistema para usuarios non autenticados..
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3.1

Trátase dun parche para solucionar un problema de seguridade.
Por favor revela responsablemente os problemas de seguridade seguindo as [políticas de seguridade](https://github.com/nvaccess/nvda/blob/master/security.md) do NVDA.

### Arranxos de Seguridade

* Evita o posible acceso ao sistema e a execución de código arbitrario con privilexios do sistema para usuarios non autenticados.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3

Esta versión inclúe melloras no rendemento, a resposta e a estabilidade da saída de audio.
Engadíronse opcións para controlar o volume dos sons e pitidos do NVDA, ou para telos seguindo ao volume da voz que esteas a usar.

O NVDA agora pode refrescar periódicamente os resultados do OCR, falando o texto novo según apareza.
Esto pode configurarse na categoría de OCR de Windows do diálogo opcións de NVDA.

Realizáronse varios arranxos no braille, mellorando a detección de dispositivos, e no movemento do cursor.
Agora é posible excluir controladores non desexados da detección automática para mellorar o rendemento da autodetección.
Tamén hai novas ordes para BRLTTY.

Tamén se arranxaron erros na tenda de complementos, en Microsoft Office, nos menús de contexto de Microsoft Edge, e na calculadora de Windows.

### Novas Características

* Mellorada a xestión do son:
  * Un novo panel de opcións de Audio:
    * Este pode abrirse con `NVDA+control+u`. (#15497)
    * Unha opción para facer que o volume dos sons e pitidos do NVDA siga á configuración do volúme da voz que esteas a usar. (#1409)
    * Unha opción para configurar por separado o volume dos sons do NVDA. (#1409, #15038)
    * As opcións para cambiar o dispositivo de audio e conmutar a atenuación de audio movéronse ao novo diálogo Opcións de audio do diálogo Selecionar Sintetizador.
    Estas opcións borraranse do diálogo "selecionar Sintetizador" en 2024.1. (#15486, #8711)
  * O NVDA agora sacará o audio a través da Windows Audio Session API (WASAPI), o que pode mellorar a resposta, o rendemento e a estabilidade da fala e dos sons do NVDA. (#14697)
  * Nota: WASAPI é incompatible con algúns complementos.
  Hai actualizacións compatibles dispoñibles para estos complementos, por favor actualízaos antes de actualizar o NVDA.
  As versións incompatibles destos complementos desactivaranse ao se actualizar o NVDA:
    * Tony's Enhancements versión 1.15 ou anteriores. (#15402)
    * NVDA global commands extension 12.0.8 ou anteriores. (#15443)
* O NVDA agora pode actualizar continuamente o resultado ao realizar o recoñecemento óptico de caracteres (OCR), falando o texto novo según apareza. (#2797)
  * Para habilitar esta funcionalidade, activa a opción "Refrescar periódicamente ol contido recoñecido" na categoría OCR de Windows do diálogo de opcións do NVDA.
  * Unha vez habilitado, podes conmutar a fala de texto novo activando anunciar cambios de contido dinámico (premendo `NVDA+5`).
* Ao usar a deteción automática de pantallas braille, agora é posible excluir os controladores da detección do diálogo de seleción de pantalla braille. (#15196)
* Unha nova opción nas opcións de Formateado de Documentos, "Ignorar liñas en branco para o anunciado de sangría de liña". (#13394)
* Engadiuse un xesto sin asignar para navegar por grupos de pestanas en modo exploración. (#15046)

### Cambios

* Braille:
  * Cando o texto nunha terminal cambia sen actualizar o cursor do sistema, o texto nunha pantalla braille agora actualizarase correctamente ao situarse sobre unha liña que cambiara.
  Esto inclúe situacións onde o braille estea seguindo á revisión. (#15115)
  * Máis combinacións de teclas para BRLTTY están asignadas agora a ordes do NVDA (#6483):
    * `learn`: conmuta a axuda de entrada do NVDA
    * `prefmenu`: abre o menú do NVDA
    * `prefload` e `prefsave`: carga e garda a configuración do NVDA
    * `time`: amosa a hora
    * `say_line`: fala a liña actual onde estea colocado o cursor de revisión
    * `say_below`: le todo usando o cursor de revisión
  * O controlador BRLTTY só está dispoñible cando estea en execución unha instancia BRLTTY con BrlAPI habilitado. (#15335)
  * Borrouse a configuración avanzada para habilitar a compatibilidade con HID braille en favor dunha nova opción.
  Agora podes desactivar a auto detección de controladores específicos para pantallas braille no diálogo de seleción de pantalla braille. (#15196)
* Tenda de complementos: os complementos instalados agora enumeraranse na pestana Complementos Dispoñibles, se aínda están dispoñibles na tenda. (#15374)
* Algúns atallos de teclado actualizáronse no menú NVDA. (#15364)

### Arranxo de Erros

* Microsoft Office:
  * Arranxo dun fallo en Microsoft Word cando as opcións de formateado de documentos "anunciar cabeceiras" e "anunciar comentarios e notas" non estaban activadas. (#15019)
  * En Word e Excel, a aliñación de texto anunciarase correctamente en máis situacións. (#15206, #15220)
  * Arranxo do anunciado de algúns atallos de formato de celda en Excel. (#15527)
* Microsoft Edge:
  * O NVDA xa non voltará á última posición do modo exploración ao se abrir o menú de contexto en Microsoft Edge. (#15309)
  * O NVDA volta a ser capaz de ler menús de contexto de descargas en Microsoft Edge. (#14916)
* Braille:
  * O cursor braille e os indicadores de seleción agora sempre se actualizan correctamente despois de amosar ou agochar os indicadores respectivos cun xesto. (#15115)
  * Arranxado un fallo onde as pantallas braille Albatross tentan inicializarse aíndaque outro dispositivo braille fora conectado. (#15226)
* Tenda de Complementos:
  * Arranxado un erro onde ao desmarcar "incluir complementos incompatibles" provocaría que os complementos incompatibles seguiran aparecendo na tenda. (#15411)
  * Os complementos bloqueados debido a razóns de compatibilidade agora deberían filtrarse correctamente ao conmutar o filtro por estado habilitado e deshabilitado. (#15416)
  * Arranxado un erro que evita que se actualicen ou substitúan complementos incompatibles instalados e habilitados mediante a ferramenta de instalación externa. (#15417)
  * Arranxado un fallo onde NVDA non falaría ate que se reiniciase despois da instalación de un complemento. (#14525)
  * Arranxado un fallo onde os complementos non poden instalarse se fallou ou se se cancelou unha descarga anterior. (#15469)
  * Arranxados problemas co manexo de complementos imcompatibles ao se actualizar o NVDA. (#15414, #15412, #15437)
* O NVDA volta a anunciar os resultados de cálculo na calculadora de Windows 32bit nas versións Server, LTSC e LTSB de Windows. (#15284)
* O NVDA xa non ignora os cambios do foco cando unha xanela anidada (xanela filla) obtén o foco. (#15432)
* Arranxouse unha posible causa de bloqueo durante o arranque do NVDA. (#15517)

### Cambios para Desenvolvedores

Por favor consulta [a guía do desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre o proceso de obsolescencia e eliminación da API do NVDA.

* `braille.handler.handleUpdate` e `braille.handler.handleReviewMove` foron cambiadas para non actualizar instantáneamente.
Antes deste cambio, cando se chamaba a calquera destos métodos con moita frecuencia, esto consumiría moitos recursos.
Estos métodos agora poñen en cola unha actualización ao remate de cada ciclo do núcleo a cambio.
Tamén deberían seren seguros para os fíos, facendo posible chamalos dende fíos en segundo plano. (#15163)
* Engadiuse o soporte oficial para rexistrar controladores persoalizados de pantallas braille no proceso de deteción automática de pantallas braille.
Consulta a documentación da clase `braille.BrailleDisplayDriver` para máis detalles.
En particular, o atributo `supportsAutomaticDetection` debe ter o valor `True` e debe implementarse o método `registerAutomaticDetection` `classmethod`.  (#15196)

#### Obsolescencias

* `braille.BrailleHandler.handlePendingCaretUpdate` está obsoleto e non ten substituto público.
Borrarase en 2024.1. (#15163)
* Importar as constantes `xlCenter`, `xlJustify`, `xlLeft`, `xlRight`, `xlDistributed`, `xlBottom`, `xlTop` dende `NVDAObjects.window.excel` está obsoleto.
Usa as enumeracións `XlHAlign` ou `XlVAlign` a cambio. (#15205)
* A asignación `NVDAObjects.window.excel.alignmentLabels` está obsoleta.
Usa os métodos `displayString` das enumeracións `XlHAlign` ou `XlVAlign` a cambio. (#15205)
* `bdDetect.addUsbDevices` e `bdDetect.addBluetoothDevices` están obsoletas.
Os controladores de pantallas Braille deberían implementar o método de clase `registerAutomaticDetection` a cambio.
Ese método recibe un obxecto `DriverRegistrar` en cuxos métodos `addUsbDevices` e`addBluetoothDevices` poden usarse. (#15200)
* A implementación predeterminada do método de comprobación en `BrailleDisplayDriver` usa `bdDetect.driverHasPossibleDevices` para os dispositivos que están marcados como fío seguro.
A partir de NVDA 2024.1, para que o método base use `bdDetect.driverHasPossibleDevices`, o atributo `supportsAutomaticDetection` tamén debe ter o valor `True`. (#15200)

## 2023.2

Esta versión introduce a Tenda de Complementos para remprazar o Administrador de Complementos.
Na Tenda de Complementos podes explorar, buscar, instalar e actualizar complementos da comunidade.
Tamén podes anular manualmente problemas de incompatibilidade con complementos desactualizados baixo a túa propria responsabilidade.

Hai novas características, ordes e soporte para pantallas braille.
Tamén hai novos xestos de entrada para o OCR e para a navegación cha de obxectos.
Mellorouse a navegación e o anunciado do formato en Microsoft Office.

Hai moitos máis fallos arranxados, particularmente para o braille, Microsoft Office, navegadores web e Windows 11.

Actualizáronse eSpeak-NG, o transcriptor braille Liblouis e Unicode CLDR.

### Novas Características

* Engadiuse a Tenda de Complementos ao NVDA. (#13985)
  * Explorar, procurar, instalar e actualizar complementos da comunidade.
  * Anular manualmente os problemas de compatibilidade con complementos obsoletos.
  * O Xestor de Complementos eliminouse e remprazouse pola tenda de Complementos.
  * Para máis información le por favor a Guía do usuario actualizada.
* Novos xestos de entrada:
  * Un xesto non asignado para percorrer as linguas dispoñibles para o OCR de Windows. (#13036)
  * Un xesto non asignado para percorrer os modos de amosado de mensaxes braille. (#14864)
  * Un Xesto non asignado para conmutar o amosado do indicador de seleción en braille. (#14948)
  * Engadíronse asignacións para xestos de teclado predeterminados para desprazarse aos obxectos seguintes ou anteriores nunha vista cha  da xerarquía de obxectos. (#15053)
    * Escritorio: `NVDA+9 teclado numérico` e `NVDA+3 teclado numérico` para desprazarse aos obxectos anterior e seguinte respectivamente.
    * Portátil: `shift+NVDA+[` e `shift+NVDA+]` para desprazarse aos obxectos anterior e seguinte respectivamente.
* Novas características Braille:
  * Engadiuse o soporte para o activador Help Tech de pantallas Braille. (#14917)
  * Unha opción nova para conmutar  o amosado do indicador de seleción (puntos 7 e 8). (#14948)
  * Unha opción nova para mover o cursor do sistema ou o foco opcionalmente cando se cambie a posición do cursor de revisión cos sensores Braille. (#14885, #3166)
  * Ao se premer o `2 teclado numérico` tres veces para anunciar o valor numérico do carácter na posición do cursor de revisión, a información agora tamén se proporciona en Braille. (#14826)
  * Engadiuse o soporte para o atributo ARIA 1.3 `aria-brailleroledescription` , permitindo aos autores web anular o tipo dun elemento amosado na pantalla Braille. (#14748)
  * Controlador de Baum Braille: engadíronse varios xestos cor Braille para realizar ordes comúns de teclado como `windows+d` e `alt+tab`.
  Por favor consulta a Guía do Usuario do NVDA para unha listaxe compreta. (#14714)
* Engadiuse a pronunciación de símbolos Unicode:
  * símbolos braille como `⠐⠣⠃⠗⠇⠐⠜`. (#14548)
  * O símbolo da tecla Opción do Mac `⌥`. (#14682)
* Engadíronse xestos para pantallas braille Tivomatic Caiku Albatross. (#14844, #15002)
  * amosar o diálogo de opcións braille
  * acesar á barra de estado
  * percorrer as formas do cursor braille
  * percorrer os modos de amosado de mensaxes braille
  * activar e desactivar o cursor braille
  * conmutar o amosado do estado do indicador de seleción braille
  * percorrer os modos "braille move o cursor do sistema ao enrutar o cursor de revisión". (#15122)
* Características de Microsoft Office:
  * Cando o texto subliñado estea habilitado no formateado de documentos, agora anúncianse as cores de resaltado en Microsoft Word. (#7396, #12101, #5866)
  * Cando as cores estean habilitadas en formateado de documentos, as cores de fondo agora anúncianse en Microsoft Word. (#5866)
  * Ao usar atallos de teclado de Excel para conmutar formato como negriña, cursiva, subliñado e tachado nunha celda, agora anúnciase o resultado. (#14923)
* Mellora experimental da xestión do son:
  * O NVDA agora pode sacar o audio a través da Windows Audio Session API (WASAPI), a que pode mellorar a resposta, o rendemento e a estabilidade da voz e dos sons do NVDA. (#14697)
  * O uso de WASAPI pode habilitarse nas opcións Avanzadas.
  Adicionalmente, se WASAPI está habilitado, tamén poden configurarse as seguintes opcións avanzadas.
    * Unha opción para ter o volume dos sons e pitidos do NVDA seguindo á opción de volume da voz que esteas a usar. (#1409)
    * Unha opción para configurar por separado o volume dos sons do NVDA. (#1409, #15038)
  * Hai un fallo coñecido cun conxelamento intermitente cando WASAPI está habilitado. (#15150)
* En Mozilla Firefox e en Google Chrome, o NVDA agora anuncia cando un control abre un diálogo, unha grella, unha listaxe ou unha árbore se o autor especificou este uso de `aria-haspopup`. (#14709)
* Agora é posible usar variables do sistema (como `%temp%` ou `%homepath%`) na especificación da ruta mentres se crean copias portables do NVDA. (#14680)
* Na actualización Windows 10 May 2019 e posteriores, o NVDA pode anunciar os nomes dos escritorios virtuais ao abrilos, cambialos e pechalos. (#5641)
* Engadiuse un parámetro en todo o sistema para permitir aos usuarios e aos administradores do sistema forzar ao NVDA a arrancar en modo seguro. (#10018)

### Cambios

* Actualizacións de compoñentes:
  * eSpeak NG actualizouse a 1.52-dev commit `ed9a7bcf`. (#15036)
  * Actualizado o transcriptor braille LibLouis a [3.26.0](https://github.com/liblouis/liblouis/releases/tag/v3.26.0). (#14970)
  * CLDR actualizouse á versión 43.0. (#14918)
* Cambios para LibreOffice:
  * Ao anunciar a posición do cursor de revisión, a posición actual do cursor agora anúnciase relativa á páxina actual en LibreOffice Writer para versións de LibreOffice >= 7.6, de modo semellante ao que se fai para Microsoft Word. (#11696)
  * O anunciado da barra de estado  (ex.: disparada por `NVDA+fin`) funciona para LibreOffice. (#11698)
  * Ao desprazarse a unha celda diferente en LibreOffice Calc, o NVDA xa non anuncia incorrectamente as coordenadas da celda enfocada anteriormente cando o anunciado de coordenadas de celda estea deshabilitado nas opcións do NVDA. (#15098)
* Cambios braille:
  * Ao usar unha pantalla braille a través do controlador Standard HID braille, o dpad pode usarse para emular as frechas e o intro.
  Tamén `espacio+punto1` e `espacio+punto4` agora asígnanse a frechas arriba e abaixo respectivamente. (#14713)
  * As actualizacións para o contido web dinámico (rexións ARIA live) agora amósanse en braille.
  Esto pode deshabilitarse no panel das opcións Avanzadas. (#7756)
* Os símbolos guión e raia sempre se enviarán ao sintetizador. (#13830)
* A distancia anunciada en Microsoft Word agora respetará a unidade definida nas opcións avanzadas de Word, incluso cando se use UIA para acesar a documentos de Word. (#14542)
* O NVDA responde máis rápido ao mover o cursor en controis de edición. (#14708)
* O script para anunciar o destiño dunha ligazón agora anuncia dende a posición do cursor do sistema oo do foco en cambio dende o navegador de obxectos. (#14659)
* A creación da copia portable xa non require que se introduza unha letra de unidade como parte da ruta absoluta. (#14681)
* Se Windows se configura para amosar segundos no reloxo da bandexa do sistema, usar `NVDA+f12` para anunciar a hora agora fai caso a esa configuración. (#14742)
* O NVDA agora anunciará grupos sen etiquetar que teñan unha información de posición útil, coma nos menús en versións recentes de Microsoft Office 365. (#14878)

### Correción de Erros

* Braille:
  * Varias correcións de estabilidade de entrada/saída para pantallas braille, resultando en menos erros cotidiáns e conxelamentos do NVDA. (#14627)
  * O NVDA xa non cambia innecesariamente a sen braille moitas veces durante a autodetección, resultando nun rexistro máis limpo e menos consumo xeral. (#14524)
  * O NVDA agora voltará ao USB se un dispositivo HID Bluetooth (como a HumanWare Brailliant ou a APH Mantis) se detecta automáticamente e unha conexión USB queda dispoñible.
  Esto só funciona para portos serie Bluetooth antes. (#14524)
  * Cando a pantalla sen braille estea conectada e o visualizador braille estea pechado premendo `alt+f4` ou facento clic no botón pechar, o tamano da pantalla do subsistema braille reiniciarase de novo a sen celdas. (#15214)
* Navegadores Web:
  * O NVDA xa non provoca ocasionalmente que Mozilla Firefox se conxele ou deixe de respostar. (#14647)
  * En Mozilla Firefox e Google Chrome, os caracteres escrebidos xa non se anuncian nalgunhas caixas de texto cando falar caracteres ao se escreber estea desactivado. (#14666)
  * Agora podes usar modo exploración en controis integrados de Chromium onde non era posible anteriormente. (#13493, #8553)
  * En Mozilla Firefox, mover o rato sobre o texto despois dun ligazón agora anuncia o texto de xeito fiable. (#9235)
  * O destino dos ligazóns gráficos agora anúnciase corectamente en Chrome e en Edge. (#14779)
  * Ao tentar anunciar a URL para un ligazón sen un atributo href o NVDA xa non queda en silenzo.
  A cambio o NVDA anuncia que o ligazón non ten destino. (#14723)
  * En modo exploración, o NVDA xa non ignora incorrectamente o movemento do foco a un control pai ou fillo por exemplo moverse dende un control elemento de listaxe ao seu pai. (#14611)
    * Ten en conta, sen embargo, que esta correción só se aplica cando a opción "Poñer automáticamente o foco en elementos enfocables" nas opcións de Modo exploración estea desactivada (o que é o predeterminado).
* Arranxos para Windows 11:
  * O NVDA pode voltar a anunciar o contido da barra de estado do Notepad. (#14573)
  * Ao cambiar entre pestanas anunciarase o nome da nova pestana e a posición para Notepad e para o Explorador de Arquivos. (#14587, #14388)
  * O NVDA voltará a anunciar os elementos candidatos ao se introducir texto en linguas coma o Chinés e o Xaponés. (#14509)
  * De novo é posible abrir os elementos Colaboradores e Licenza no menú axuda do NVDA. (#14725)
* Arranxos para Microsoft Office:
  * Ao se desprazar rápidamente polas celdas en Excel, agora é menos probable que o NVDA anuncie a celda ou seleción incorrectas. (#14983, #12200, #12108)
  * Ao aterrizar nunha celda de Excel dende fora dunha folla de cálculo, o braille e o resaltador do foco xa non se actualizan innecesariamente ao obxecto que tiña o foco anteriormente. (#15136)
  * O NVDA xa non falla ao anunciar campos de contrasinal enfocables en Microsoft Excel e en Outlook. (#14839)
* Para símbolos que non teñan unha descripción de símbolo na lingua actual, usarase o nivel de símbolo en inglés. (#14558, #14417)
* Agora é posible usar o carácter barra inversa no campo remprazar dunha entrada de diccionario, cando o tipo non se axusta como unha expresión regular. (#14556)
* Na calculadora de Windows 10 e 11, unha copia portable do NVDA xa non fará nada nin reproducirá tons de erro ao se introducir expresións na calculadora estándar no modo de superposición compacto. (#14679)
* O NVDA volta a recuperarse de moitas máis situacións, como aplicacións que deixan de respostar, que antes provocaban que se conxelara por completo. (#14759)
* Ao forzar a compatibilidade con UIA con determinadas terminales e consolas, aránxase un erro que provocaba a conxelación e o lixo no ficheiro de rexistro. (#14689)
* O NVDA xa non refusará gardar a configuración despois de que se reinicie unha configuración. (#13187)
* Ao se executar unha versión temporal  dende un lanzador, o NVDA non enganará ao usuario facéndolle crer que pode gardar a configuración. (#14914)
* O NVDA agora responde xeralmente un pouco máis rápido ás ordes e aos cambios do foco. (#14928)
* A visualización das opcións do OCR non fallará nalgúns sistemas nunca máis. (#15017)
* Arránxase un fallo relacionado con gardar e cargar a configuración do NVDA, incluindo cambiar sintetizadores. (#14760)
* Arránxase un fallo que facía que o xesto táctil de revisión de texto "flic arriba" movese páxinas en lugar de mover á liña anterior. (#15127)

### Cambios para Desenvolvedores

Por favor, consulta [a Guía do Desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para obter información sobre o proceso de obsolescencia e de eliminación da API de NVDA.

* Engadíronse convencións suxeridas á especificación do manifesto do complemento.
Son opcionais para a compatibilidade co NVDA, pero recoméndanse ou esíxense para o envío á tenda de complementos.
  * Usar `lowerCamelCase` para o campo de nome.
  * Usar o formato `<major>.<minor>.<patch>` para o campo versión (requerido para o almacén de datos do complemento).
  * Usar `https://` como esquema para o campo url (requerido para o almacén de datos do complemento).
* Engadiuse un novo tipo de punto de extensión chamado `Chain`, que pode usarse para iterar sobre iterables devoltos por manexadores rexistrados. (#14531)
* Engadiuse o punto de extensión `bdDetect.scanForDevices`.
Os manexadores pódense rexistrar para producir `BrailleDisplayDriver/DeviceMatch` pares que non encaixan en categorías existentes, como USB ou Bluetooth. (#14531)
* Endadiuse o punto de extensión: `synthDriverHandler.synthChanged`. (#14618)
* O anel de opcións do sintetizador agora almacena en caché os valores de opcións dispoñibles a primeira vez que se necesitan, en lugar de facelo ao cargar o sintetizador. (#14704)
* Agora pódese chamar ao método de exportación dun mapa de xestos para exportalo a un dicionario.
Este dicionario pode importarse noutro xesto pasándoo ao constructor de `GlobalGestureMap` ou ao método update nun mapa existente. (#14582)
* `hwIo.base.IoBase` e os seus derivados agora teñen un novo parámetro constructor para tomar un `hwIo.ioThread.IoThread`.
Se non se proporciona, úsase o fío predeterminado. (#14627)
* `hwIo.ioThread.IoThread` agora ten  un método `setWaitableTimer` para establecer un temporizador de espera usando unha función python.
Do mesmo xeito, o novo método `getCompletionRoutine` permíteche converter un método python nunha rutina de finalización de xeito seguro. (#14627)
* `offsets.OffsetsTextInfo._get_boundingRects` agora debería voltar sempre `List[locationHelper.rectLTWH]` como se esperaba para unha subclase de `textInfos.TextInfo`. (#12424)
* `highlight-color` agora é un atributo de campo de formato. (#14610)
* O NVDA debería de determinar con maior precisión se unha mensaxe rexistrada provén do núcleo de NVDA. (#14812)
* O NVDA xa non rexistrará advertencias ou erros inexactos sobre appModules obsoletos. (#14806)
* Todos os puntos de extensión do NVDA agora descrébense brevemente nun capítulo novo específico da guía do desenvolvedor. (#14648)
* `scons checkpot` xa non comprobará máis o subcartafol `userConfig`. (#14820)
* As cadeas traducibles agora poden definirse cunha forma singular e unha plural usando `ngettext` e `npgettext`. (#12445)

#### Obsolescencias

* Pasar funcións lambda a `hwIo.ioThread.IoThread.queueAsApc` está obsoleto.
A cambio, as funcións deberían seren débilmente referenciables. (#14627)
* Importar `LPOVERLAPPED_COMPLETION_ROUTINE` dende `hwIo.base` está obsoleto.
A cambio importa dende `hwIo.ioThread`. (#14627)
* `IoThread.autoDeleteApcReference` está obsoleto.
Introduciuse no NVDA 2023.1 e nunca se pretendeu  que formase parte da API pública.
Ata a súa eliminación, compórtase coma un no-op, é dicir, un xestor de contexto que non produce nada. (#14924)
* `gui.MainFrame.onAddonsManagerCommand` está obsoleto, usa `gui.MainFrame.onAddonStoreCommand` a cambio. (#13985)
* `speechDictHandler.speechDictVars.speechDictsPath` está obsoleta, usa `NVDAState.WritePaths.speechDictsDir` en a cambio. (#15021)
* Importar `voiceDictsPath` e `voiceDictsBackupPath` dende `speechDictHandler.dictFormatUpgrade` está obsoleto.
A cambio usa `WritePaths.voiceDictsDir` e `WritePaths.voiceDictsBackupDir` from `NVDAState`. (#15048)
* `config.CONFIG_IN_LOCAL_APPDATA_SUBKEY` está obsoleto.
A cambio usa `config.RegistryKey.CONFIG_IN_LOCAL_APPDATA_SUBKEY`. (#15049)

## 2023.1

Engadiuse unha nova orde "Estilo de Parágrafo" na "navegación de Documento".
Esto pode usarse con editores de texto que non admitan a navegación por parágrafos nativamente, coma o Bloc de Notas e Notepad++.

Hai unha nova orde global para anunciar o destiño dunha ligazón, mapeada a `NVDA+k`.

O soporte para o contido web anotado (coma os comentarios e as notas ao pe) foi mellorado.
Preme `NVDA+d` para percorrer os resumos cando se anuncien as anotacións (por exemplo, "ten comentario, ten nota ao pe").

Agora admítense as pantallas braille Tivomatic Caiku Albatross 46/80.

Mellorouse o soporte para versións ARM64 e AMD64 de Windows.

Hai moitos arranxos de erros, en particular arranxos de Windows 11.

Actualizáronse eSpeak, LibLouis, Sonic rate boost e Unicode CLDR.
Hai novas táboas braille para xeorxiano, Swahili (Kenya) e Chichewa (Malawi).

Nota:

* Esta versión rompe a compatibilidade cos complementos existentes.

### Novas Características

* Microsoft Excel a través de UI Automation: anunciado automático de cabeceiras de fila e columna en táboas. (#14228)
  * Nota: esto refírese a táboas formateadas a través do botón "Táboa" no panel Insertar da Cinta.
  "Primeira Columna" e "Cabeceira de Fila" en "Opcións de Estilo de Táboa" correspóndense con cabeceiras de columna e fila respectivamente.
  * Esto non se refire ás cabeceiras específicas do lector de pantalla a través de rangos denominados, o que actualmente non se admite a través de UI Automation.
* Engadiuse un script non asignado para conmutar as descripcións retrasadas de caracteres. (#14267)
* Engadiuse unha opción experimental para aproveitar o soporte de notificacións UIA na Terminal de Windows para anunciar o texto novo ou cambiado na terminal, o que mellora a estabilidade e a capacidade de resposta. (#13781)
  * Consulta a Guía do Usuario para coñecer as limitacións de esta opción experimental.
* En Windows 11 ARM64, o modo exploración agora está dispoñible en aplicacións AMD64 coma Firefox, Google Chrome e 1Password. (#14397)
* Engadiuse unha nova opción, "Estilo de Parágrafo" en "Navegación de Documento".
Esto engade o soporte para salto dunha soa liña (normal) e salto de múltiples liñas (bloque) á navegación de parágrafos.
Esto pode usarse con editores de texto que non admitan a navegación por parágrafos nativamente, coma Notepad e Notepad++. (#13797)
* Agora anúnciase a presencia de varias anotacións.
`nvda+d` agora percorre o sumario de cada anotación anunciando o obxectivo para os orixes con varios obxectivos de anotacións.
Por exemplo, cando o texto ten un comentario e unha nota ao pe asociada con ela. (#14507, #14480)
* Engadiuse o soporte para as pantallas braille Tivomatic Caiku Albatross 46/80. (#13045)
* Nova orde global: anunciar destiño da ligazón (`NVDA+k`).
Preméndoa unha vez falará e amosará en braille o destiño da ligazón que estea no navegador de obxectos.
Preméndoa dúas veces amosaráa nunha xanela para unha revisión máis detallada. (#14583)
* Unha nova orde global non mapeada (Categoría Ferramentas): anuncia o destiño da ligazón nunha xanela.
O mesmo que premer `NVDA+k` dúas veces, pero pode ser máis útil para usuarios de braille. (#14583)

### Cambios

* Actualizouse o transcriptor braille LibLouis a [3.24.0](https://github.com/liblouis/liblouis/releases/tag/v3.24.0). (#14436)
  * Actualizaciones grandes ao braille úngaro, UEB e Chinés bopomofo.
  * Soporte para o braille danés estándar 2022.
  * Nobas táboas braille para braille xeorxiano literario, Swahili (Kenya) e Chichewa (Malawi).
* Actualizouse Sonic rate boost library a commit `1d70513`. (#14180)
* CLDR actualizouse á versión 42.0. (#14273)
* eSpeak NG actualizouse a 1.52-dev commit `f520fecb`. (#14281, #14675)
  * Arranxado o anunciado de números longos. (#14241)
* As aplicacións Java con controis que usen o estado selecionable agora anunciarán cando un elemento non estea selecionado a cambio de cando o elemento estea selecionado. (#14336)

### Arranxo de Erros

* Arranxos de Windows 11:
  * O NVDA anunciará os elementos resaltados da procura ao abrir o menú Inicio. (#13841)
  * En ARM, as aplicacións x64 xa non se identifican como aplicacións ARM64. (#14403)
  * Pódese acesar aos elementos de menú do historial do portapapeis coma "elemento anccorado". (#14508)
  * En Windows 11 22H2 e máis modernos, é posible de novo usar o rato e a interactuación táctil para interactuar con áreas como a xanela de desbordamento da bandexa do sistema e o diálogo "Abrir Ccon". (#14538, #14539)
* Anúncianse as suxerencias ao escreber unha @mención nos comentarios en Microsoft Excel. (#13764)
* Na barra de ubicacións de Google Chrome, os controis de suxerencias (cambiar a pestana, borrar suxerencia etc) agora anúncianse cando se selecionen. (#13522)
* Ao pedir información de formato, as cores agora anúncianse explícitamente en Wordpad ou no Visualizador de Rexistro, a cambio de só "cor predeterminada". (#13959)
* En Firefox, agora funciona a activación do botón "Amosar Opcións" nas páxinas de incidencias de GitHub de xeito fiable. (#14269)
* Os controis do selector de data na caixa de diálogo Búsqueda Avanzada de Outlook 2016 / 365 agora anuncian a súa etiqueta e valor. (#12726)
* Os controis de conmutación ARIA agora anúncianse realmente coma conmutadores en Firefox, Chrome e Edge, a cambio de coma caixas de verificación. (#11310)
* O NVDA anunciará automáticamente o estado de ordenación nunha cabeceira de columna de táboa HTML cando se cambie premendo un botón interior. (#10890)
* O nome dun punto de referencia ou dunha rexión sempre se fala automáticamente ao saltar ao interior dende o exterior usando a navegación rápida ou o foco no modo exploración. (#13307)
* Cando se habilita pitar ou anunciar 'maiús' para letras maiúsculas con descripcións retrasadas de caracteres, o NVDA xa non pita nin anuncia 'maius' dúas veces. (#14239)
* Os controis en táboa en aplicacións Java agora anunciaranse con máis precisión no NVDA. (#14347)
* Algunhas opcións xa non serán inesperadamente diferentes cando se usen con varios perfís. (#14170)
  * Abordáronse as seguintes opcións:
    * Sangría de liña en opcións de Formateado de Documento
    * Bordes de celda en opcións de formateo de documento
    * Amosar mensaxes en opcións de braille
    * Seguemento de Braille en opcións de braille
  * Nalgúns casos pouco comúns, estas opcións usadas en perfís poden modificarse inesperadamente ao instalar esta versión de NVDA.
  * Por favor, comproba estas opcións nos teus perfís despois de actualizar o NVDA a esta versión.
* Os Emojis agora deberían anunciarse en máis linguas. (#14433)
* A presenza dunha anotación xa non falta en braille para algúns elementos. (#13815)
* Arranxado un problema onde os cambios de configuración non se gardaban correctamente ao cambiar entre unha opción "Predeterminada" e o valor da opción "predeterminada". (#14133)
* Ao se configurar o NVDA sempre haberá ao menos unha tecla que se defina coma tecla NVDA. (#14527)
* Ao acesar ao menú NVDA a través da área de notificacións, o NVDA agora non suxerirá unha actualización pendente cando non haxa xa ningunha dispoñible. (#14523)
* O tempo restante, transcorrido e total agora anúnciase correctamente para ficheiros de audio de máis dun día en foobar2000. (#14127)
* En navegadores web coma Chrome e Firefox, as alertas coma descargas de ficheiros amósanse en braille ademáis de seren faladas. (#14562)
* Arranxado un erro ao navegar á primeira e última columna nunha táboa en Firefox (#14554)
* Cando o NVDA se lance co parámetro `--lang=Windows`, é posible de novo abrir o diálogo Opcións Xerais de NVDA. (#14407)
* O NVDA xa non falla na lectura continua en Kindle para PC despois de pasar a páxina. (#14390)

### Cambios para Desenvolvedores

Nota: esta é unha versión que rompe a compatibilidade coa API do complemento.
Os complementos terán que voltar a probarse e actualizar o seu manifesto.
Por favor consulta [a guía do desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre as obsolescencias na API de NVDA e procesos borrados.

* As probas de sistema agora deberían pasar ao se executar localmente en sistemas non en inglés. (#13362)
* En Windows 11 en ARM, as aplicacións x64 xa non se identifican como aplicacións ARM64. (#14403)
* Xa non é necesario usar `SearchField` e `SuggestionListItem` `UIA` `NVDAObjects` en novos escenarios UI Automation, onde se anuncian automáticamente as suxerencias de procura, e onde a escritura expúxose a través de UI Automation co patrón `controllerFor`.
Esta funcionalidad agora está dispoñible xenéricamente a través de `behaviours.EditableText` e a base `NVDAObject` respectivamente.
* A categoría UIA debug logging cando está habilitada agora produce un rexistro significativamente maior para os eventos, manexadores e utilidades UIA. (#14256)
* Actualizados os estándares de compilación de NVDAHelper. (#13072)
  * Agora usa os estándares C++20, eran C++17.
  * Agora usa a bandeira do compilador `/permissive-` que deshabilita comportamentos permisivos, e estabrece as opcións do compilador `/Zc` para unha conformidade estricta.
* Algúns obxectos de plugin (por exemplo: controladores e complementos) agora teñen unha descripción máis informativa na consola python de NVDA. (#14463)
* O NVDA agora pode compilarse compretamente con Visual Studio 2022, xa non se require das ferramentas de compilación de Visual Studio 2019.
* Rexistro máis detallado dos bloqueos do NVDA para axudar á depuración. (#14309)
* Substituíuse a clase singleton `braille._BgThread` por `hwIo.ioThread.IoThread`. (#14130)
  * Unha única instancia `hwIo.bgThread` (no núcleo do NVDA) desta clase proporciona entrada/saída en segundo plano para fíos seguros de controladores de pantalla braille.
  * Esta nova clase non é un singleton por deseño, recoméndase aos autores de complementos que usen a súa propria instancia cando realicen entrada/saída hardware.
* A arquitectura do procesador do computador pode consultarse a partir do atributo `winVersion.WinVersion.processorArchitecture.` (#14439)
* Engadíronse novos puntos de extensión. (#14503)
  * `inputCore.decide_executeGesture`
  * `tones.decide_beep`
  * `nvwave.decide_playWaveFile`
  * `braille.pre_writeCells`
  * `braille.filter_displaySize`
  * `braille.decide_enabled`
  * `braille.displayChanged`
  * `braille.displaySizeChanged`
* É posible axustar useConfig a  False nas opcións soportadas para un controlador de sintetizador. (#14601)

#### Cambios de Ruptura da API

Son cambios de última hora na API.
Por favor abre una incidencia en GitHub se o teu complemento ten un problema coa actualización á nova API.

* Alterouse a especificación de configuración, borráronse ou modificáronse chaves. (#14233).
  * Na seción `[documentFormatting]`:
    * `reportLineIndentation` almacena un valor enteiro (de 0 a 3) a cambio dun booleano
    * `reportLineIndentationWithTones` borrouse.
    * `reportBorderStyle` e `reportBorderColor` borráronse e remprazáronse por `reportCellBorders`.
  * Na seción `[braille]`:
    * `noMessageTimeout` borrouse, remplazado por un valor para `showMessages`.
    * `messageTimeout` non pode tomar o valor 0 nunca máis, remprazouse por un valor para `showMessages`.
    * `autoTether` borrouse; `tetherTo` agora pode tomar o valor "auto" a cambio.
  * En la sección `[keyboard]` (#14528):
    * `useCapsLockAsNVDAModifierKey`, `useNumpadInsertAsNVDAModifierKey`, `useExtendedInsertAsNVDAModifierKey` se han eliminado.
    Se remplazaron por `NVDAModifierKeys`.
* A clase `NVDAHelper.RemoteLoader64` foi borrada sen remprazo. (#14449)
* As seguintes funcións en `winAPI.sessionTracking` borráronse sen remprazo. (#14416, #14490)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`
* Xa non é posible habilitar ou deshabilitar o manexador braille coa opción `braille.handler.enabled`.
Para deshabilitar o manexador braille por programa, rexistra un manexador a `braille.handler.decide_enabled`. (#14503)
* Xa non é posible actualizar o tamaño da pantalla do manexador configurando `braille.handler.displaySize`.
Para actualizar o tamaño da pantalla por programa, rexistra un manexador a `braille.handler.filter_displaySize`.
Consulta `brailleViewer` para ver un exemplo de cómo facelo. (#14503)
* Houbo cambios no uso de `addonHandler.Addon.loadModule`. (#14481)
  * `loadModule` agora espera o punto coma un separador, en lugar da barra inversa.
  Por exemplo "lib.example" a cambio de "lib\example".
  * `loadModule` agora lanza unha excepción cando un módulo non se poda cargar  ou teña erros, en lugar de devolver silenciosamente `None` sen dar información sobre a causa.
* Os seguintes símbolos borráronse de `appModules.foobar2000` sen un remplazo directo. (#14570)
  * `statusBarTimes`
  * `parseIntervalToTimestamp`
  * `getOutputFormat`
  * `getParsingFormat`
* Os seguintes xa non son singletons - o seu método get foi borrado.
O uso de `Example.get()` agora é `Example()`. (#14248)
  * `UIAHandler.customAnnotations.CustomAnnotationTypesCommon`
  * `UIAHandler.customProps.CustomPropertiesCommon`
  * `NVDAObjects.UIA.excel.ExcelCustomProperties`
  * `NVDAObjects.UIA.excel.ExcelCustomAnnotationTypes`

#### Obsolescencias

* `NVDAObjects.UIA.winConsoleUIA.WinTerminalUIA` está obsoleto e desaconséllase o seu uso. (#14047)
* `config.addConfigDirsToPythonPackagePath` moveuse.
Usa `addonHandler.packaging.addDirsToPythonPackagePath` a cambio. (#14350)
* `braille.BrailleHandler.TETHER_*` está obsoleto.
Usa `configFlags.TetherTo.*.value` a cambio. (#14233)
* `utils.security.postSessionLockStateChanged` está obsoleta.
Usa `utils.security.post_sessionLockStateChanged` a cambio. (#14486)
* `NVDAObject.hasDetails`, `NVDAObject.detailsSummary`, `NVDAObject.detailsRole` están obsoletos.
Usa `NVDAObject.annotations` a cambio. (#14507)
* `keyboardHandler.SUPPORTED_NVDA_MODIFIER_KEYS` está obsoleta sen ningún remplazo directo.
Considera usar a clase `config.configFlags.NVDAKey` a cambio. (#14528)
* `gui.MainFrame.evaluateUpdatePendingUpdateMenuItemCommand` quedou obsoleto.
Usa `gui.MainFrame.SysTrayIcon.evaluateUpdatePendingUpdateMenuItemCommand` a cambio. (#14523)

## 2022.4

Esta versión inclúe varias teclas de ordes novas, incluíndo ordes para ler toda a táboa.
Engadiuse unha seción "Guía de Inicio Rápido" á Guía do Usuario.
Tamén hai varios arranxos de erros.

Actualizáronse eSpeak e LibLouis.
Hai novas táboas braille para Chinés, sueco, Luganda e Kinyarwanda.

### Novas Características

* Engadiuse unha seción "Guía de Inicio rápido" á Guía do Usuario. (#13934)
* Introduciuse unha nova orde para procurar o atallo de teclado do foco actual. (#13960)
  * Escritorio: `shift+2 do teclado numérico`.
  * Portátil: `NVDA+ctrl+shift+.`.
* Introducíronse novas ordes para mover o cursor de revisión por páxinas onde se admita pola aplicación. (#14021)
  * Mover á páxina anterior:
    * Escritorio: `NVDA+rePáx`.
    * Portátil: `NVDA+shift+rePáx`.
  * Mover á páxina seguinte:
    * Escritorio: `NVDA+avPáx`.
    * Portátil: `NVDA+shift+avPáx`.
* Engadíronse as seguintes ordes de táboa. (#14070)
  * Falar todo na columna: `NVDA+control+alt+frechaAbaixo`
  * Falar todo na fila: `NVDA+control+alt+frechaDereita`
  * Ler toda a columna:  `NVDA+control+alt+frechaArriba`
  * Ler toda a fila: `NVDA+control+alt+FrechaEsquerda`
* Microsoft Excel a través de UI Automation: NVDA agora anuncia cando se saia dunha táboa dentro dunha folla de cálculo. (#14165)
* Anunciar cabeceiras de táboa agora pode se configurar separadamente por filas e columnas. (#14075)

### Cambios

* eSpeak NG actualizouse a 1.52-dev commit `735ecdb8`. (#14060, #14079, #14118, #14203)
  * Arranxado o anunciado de caracteres latinos ao usar Mandarín. (#12952, #13572, #14197)
* Actualizouse o transcriptor braille LibLouis a [3.23.0](https://github.com/liblouis/liblouis/releases/tag/v3.23.0). (#14112)
  * Engadíronse táboas braille:
    * Braille común chinés (caracteres de chinés simplificado)
    * Braille literario Kinyarwanda
    * Braille literario Luganda
    * Braille sueco sen contracción
    * Braille sueco parcialmente contraído
    * Braille sueco contraído
    * Chinés (China, Mandarín) Sistema braille actual (sen tons) (#14138)
* O NVDA agora inclúe a arquitectura do sistema operativo coma parte do seguemento de estadísticas de usuario. (#14019)

### Arranxo de Erros

* Ao actualizar o NVDA usando o Windows Package Manager CLI (aka winget), unha versión liberada do NVDA xa non se trata sempre coma unha versión máis moderna que calquera versión alfa que estea instalada. (#12469)
* O NVDA agora anunciará correctamente caixas de grupo en aplicacións Java. (#13962)
* O cursor do sistema segue apropriadamente o texto falado durante "falar todo" en aplicacións coma Bookworm, WordPad, ou o visualizador do rexistro do NVDA. (#13420, #9179)
* En programas que usen UI Automation, as caixas de verificación parcialmente marcadas anunciaranse correctamente. (#13975)
* Mellorado o rendemento e a estabilidade en Microsoft Visual Studio, Windows Terminal e outras aplicacións baseadas en UI Automation. (#11077, #11209)
  * Estos arranxos aplícanse a Windows 11 Sun Valley 2 (versión 22H2) e posteriores.
  * O rexistro selectivo para eventos UI Automation e cambios de propiedade agora habilítase por omisión.
* O anunciado de texto, a saída Braille e a supresión de contrasinais agora funcionan coma se esperaba no control integrado da Terminal de Windows en Visual Studio 2022. (#14194)
* O NVDA agora é conscente dos DPI cando se usen varios monitores.
Hai varios arranxos para usar unha configuración de DPI superior a 100% ou varios monitores.
Aínda poden seguir existindo problemas con versións de Windows máis vellas que Windows 10 1809.
Para que funcionen estos arranxos, as aplicacións coas que interactúe o NVDA tamén teñen que seren conscentes de DPI.
Ten en conta que aínda hai fallos coñecidos con Chrome e Edge. (#13254)
  * Os marcos de resaltado visual agora deberían se colocar correctamente na maioría das aplicacións. (#13370, #3875, #12070)
  * A interacción coa pantalla táctil agora debería ser precisa para a maioría das aplicacións. (#7083)
  * O seguemento do rato agora debería funcionar para a maioría das aplicacións. (#6722)
* Os cambios do estado da orientación (apaisado ou vertical) agora ignóranse correctamente cando non hai cambio (ex. cambios do monitor). (#14035)
* O NVDA anunciará elementos arrastrables na pantalla en lugares coma na reorganización dos mosaicos do menú Inicio en Windows 10 e nos escritorios virtuais en Windows 11. (#12271, #14081)
* Nas opcións avanzadas, a opción "reproducir un son para rexistro de erros" agora restáurase correctamente a este valor predeterminado ao premer o botón "Restaurar predeterminados". (#14149)
* O NVDA agora pode selecionar texto usando o atallo de teclado `NVDA+f10` en aplicacións Java. (#14163)
* O NVDA xa non se atascará nun menú ao subir e baixar coas frechas por un fío de conversacións en Microsoft Teams. (#14355)-

### Cambios para Desenvolvedores

Por favor consulta [a guía do desenvolvedor](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para obter información sobre a obsolescencia da API do NVDA e o proceso de eliminación.

* Creouse a [listaxe de correo de Anuncios da API de NVDA](https://groups.google.com/a/nvaccess.org/g/nvda-api/about). (#13999)
* O NVDA xa non procesa eventos `textChange` para a maioría das aplicacións UI Automation debido ao impacto do seu extremo rendemento negativo. (#11002, #14067)

#### Obsolescencias

* `core.post_windowMessageReceipt` está obsoleto, usa `winAPI.messageWindow.pre_handleWindowMessage` a cambio.
* `winKernel.SYSTEM_POWER_STATUS` está obsoleto e desaconséllase o seu uso, esto moveuse a `winAPI._powerTracking.SystemPowerStatus`.
* As constantes `winUser.SM_*` están obsoletas, usa `winAPI.winUser.constants.SystemMetrics` a cambio.

## 2022.3.3

Esta é unha versión menor para arranxar problemas con 2022.3.2, 2022.3.1 e 2022.3.
Esto tamén aborda un problema de seguridade.

### Arranxos de Seguridade

* Evita un posible aceso ao sistema (por exemplo: na consola Python de NVDA) para usuarios non autenticados.
([GHSA-fpwc-2gxx-j9v7](https://github.com/nvaccess/nvda/security/advisories/GHSA-fpwc-2gxx-j9v7))

### Arranxo de Erros

* Arranxado un erro no que se o NVDA conxélase cando se bloquea, o NVDA permitirá accesar aos usuarios do escritorio mentres se estea na pantalla de bloqueo de Windows. (#14416)
* Arranxado un erro no que se o NVDA conxélase cando se bloquea, o NVDA non se comportará correctamente, coma se o dispositivo seguira aínda bloqueado. (#14416)
* Arranxados problemas de accesibilidade co proceso de Windows "olvidei o meu PIN" e coa experiencia de actualizar ou instalar Windows. (#14368)
* Arranxado un erro ao intentar instalar o NVDA nalgúns ambentes de Windows, por exemplo en Windows Server. (#14379)

### Cambios para Desenvolvedores

#### Obsolescencias

* `utils.security.isObjectAboveLockScreen(obj)` está obsoleto, a cambio usa `obj.isBelowLockScreen`. (#14416)
* As seguintes funcións en `winAPI.sessionTracking` están obsoletas para a súa eliminación en 2023.1. (#14416)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`

## 2022.3.2

Esta é unha versión menor para arranxar regresións con 2022.3.1 e para abordar un problema de seguridade.

### Arranxos de Seguridade

* Evita o posible aceso a nivel de sistema para usuarios non autentificados.
([GHSA-3jj9-295f-h69w](https://github.com/nvaccess/nvda/security/advisories/GHSA-3jj9-295f-h69w))

### Arranxo de Erros

* Arránxase unha regresión de 2022.3.1 onde certas funcionalidades deshabilitábanse en pantallas seguras. (#14286)
* Arránxase unha regresión de 2022.3.1 onde certas funcionalidades desabilitábanse despois de autentificarse se o NVDA se iniciaba na pantalla de bloqueo. (#14301)

## 2022.3.1

Esta é unha versión menor para arranxar varios problemas de seguridade.
Por favor comunica responsablemente os problemas de seguridade a <info@nvaccess.org>.

### Arranxos de Seguridade

* Arranxouse o exploit polo que era posible elevar ao usuario os privilexios de sistema
([GHSA-q7c2-pgqm-vvw5](https://github.com/nvaccess/nvda/security/advisories/GHSA-q7c2-pgqm-vvw5))
* Arranxouse un problema de seguridade que permitía o aceso á consola de python na pantalla de bloqueo a través dunha condición race para o arranque do NVDA.
([GHSA-72mj-mqhj-qh4w](https://github.com/nvaccess/nvda/security/advisories/GHSA-72mj-mqhj-qh4w))
* Arranxouse un problema polo que o texto do visualizador de voz se gardaba en caché ao bloquear Windows.
([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

### Arranxo de Erros

* Evítase que un usuario non autentificado actualice as opcións para os visualizadores de voz e Braille na pantalla de bloqueo. ([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

## 2022.3

A comunidade de desenvolvedores do NVDA contribuíu en grande medida a esta versión.
Esto inclúe o retraso das descripcións dos caracteres e a mellora do soporte da Consola de Windows.

Esta versión tamén inclúe varios arranxos de fallos.
En particular, as versións actualizadas de Adobe Acrobat/Reader xa non se bloquean ao ler un documento PDF.

eSpeak actualizouse, o que introduce tres linguas novas: Bielorruso, Luxemburgués e Totontepec Mixe.

### Novas Características

* Na Consola de Windows úsase Host polo Símbolo do Sistema, por PowerShell e polo subsistema de Windows para Linux en Windows 11 versión 22H2 (Sun Valley 2) e posterior:
  * Rendemento e estabilidade moi mellorados. (#10964)
  * Ao premer `control+f` para procurar texto, a posición do cursor de revisión actualízase para seguer ao término atopado. (#11172)
  * O anunciado do texto escrebido que non apareza na pantalla (como as contrasinais) deshabilítanse predeterminadamente.
Pode voltar a habilitarse no panel Avanzado dos axustes do NVDA. (#11554)
  * O texto que se desprazara fora da pantalla pódese revisar sen desprazar a xanela da consola. (#12669)
  * Está dispoñible máis información detallada de formato de texto. ([microsoft/terminal PR 10336](https://github.com/microsoft/terminal/pull/10336))
* Engadiuse unha nova opción de Fala para ler as descripcións de caracteres tras un retraso. (#13509)
* Engadiuse unha nova opción de Braille para determinar se o desprazamento cara adiante ou cara atrás da pantalla debería interrumpir a fala. (#2124)

### Cambios

* eSpeak NG actualizouse a 1.52-dev commit `9de65fcb`. (#13295)
  * Linguas engadidas:
    * Bielorruso
    * Luxemburgués
    * Totontepec Mixe
* Ao se usar UI Automation para acesar a controis de folla de cálculo de Microsoft Excel, o NVDA agora pode anunciar cando unha celda está fusionada. (#12843)
* A cambio de anunciar "ten detalles" inclúese o propósito dos detalles cando sexa posible, por exemplo "ten comentarios". (#13649)
* O tamano de instalación do NVDA agora amósase na seción Programas e Características de Windows. (#13909)

### Arranxo de Erros

* O Adobe Acrobat / Reader de 64 bits xa non se bloqueará ao ler un documento PDF. (#12920)
  * Ten en conta que é necesaria tamén a versión máis actualizada do Adobe Acrobat / Reader para evitar o bloqueo.
* As medidas de tamano de fonte agora son traducibles no NVDA. (#13573)
* Ignóranse os eventos de Java Access Bridge nos que non se poda atopar un manexador de xanela para as aplicacións Java.
Esto mellorará o rendemento para algunhas aplicacións Java incluíndo IntelliJ IDEA. (#13039)
* O anunciado de celdas selecionadas para LibreOffice Calc é máis eficaz e xa non da lugar á conxelación de Calc cando se selecionen moitas celdas. (#13232)
* Cando se execute nun usuario diferente, Microsoft Edge xa non é inaccesible. (#13032)
* Cando o aumento brusco de velocidade estea desactivado, a velocidade do eSpeak non descende máis entre velocidades do 99% e 100%. (#13876)
* Arranxouse un erro que permitía que se abriran 2 diálogos de xestos de Entrada. (#13854)

### Cambios para Desenvolvedores

* Actualizado Comtypes á versión 1.1.11. (#12953)
* En compilacións da Consola de Windows (`conhost.exe`) cun nivel 2 da API de NVDA (`FORMATTED`) ou máis grandes, como aqueles incluídos co Windows 11 versión 22H2 (Sun Valley 2), UI Automation agora úsase por defecto. (#10964)
  * Esto pódese anular cambiando a opción "Soporte da Consola de Windows" no panel Avanzado da configuración do NVDA.
  * Para atopar o teu nivel de API de NVDA para a Consola de Windows, configura "Soporte de Consola de Windows" a "UIA cando estea dispoñible", entón verifica que o rexistro estea aberto con NVDA+F1 dende unha instancia de Consola de Windows en execución.
* O Búfer virtual de Chromium agora cárgase incluso cando o obxecto documento teña o MSAA `STATE_SYSTEM_BUSY` exposto a través de IA2. (#13306)
* Creouse un tipo específico de configuración `featureFlag` para utilizar con características experimentais en NVDA. Consulta `devDocs/featureFlag.md` para máis información. (#13859)

#### Obsolescencias

Non se propoñen obsolescencias en 2022.3.

## 2022.2.4

Este é un parche liberado para arranxar un fallo de seguridade.

### Corrección de Erros

* Arranxouse un fallo polo que era posible abrir a consola python do NVDA a través do visualizador do rexistro na pantalla de bloqueo.
([GHSA-585m-rpvv-93qg](https://github.com/nvaccess/nvda/security/advisories/GHSA-585m-rpvv-93qg))

## 2022.2.3

Este é un parche liberado para arranxar unha rotura acidental da API introducida en 2022.2.1.

### Arranxo de Fallos

* Arranxado un fallo onde o NVDA non anunciaba "Escritorio Seguro" ao entrar nun escritorio seguro.
Esto provocaba que o NVDA remote non recoñecese os escritorios seguros. (#14094)

## 2022.2.2

Este é un parche liberado para arranxar un fallo introducido en 2022.2.1 cos xestos de entrada.

### Arranxo de Fallos

* Arranxado un fallo onde os xestos de entrada non sempre funcionaban. (#14065)

## 2022.2.1

Esta é unha versión menor para arranxar un problema de seguridade.
Por favor, comunica responsablemente os fallos de seguridade a <info@nvaccess.org>.

### Arranxos de Seguridade

* Arranxouse un fallo polo que era posible executar unha consola python dende a pantalla de bloqueo. (GHSA-rmq3-vvhq-gp32)
* Arranxouse o fallo polo que era posible escapar da pantalla de bloqueo usando a navegación de obxectos. (GHSA-rmq3-vvhq-gp32)

### Cambios para Desenvolvedores

#### Obsolescencias

Estas obsolescencias non se programaron actualmente para a súa eliminación.
Os alias obsoletos permanecerán ata novo aviso.
Por favor, proba a nova API e proporciona retroalimentación.
Para autores de complementos, por favor abride unha incidencia en GitHub se estos cambios impiden que a API satisfaga as vosas necesidades.

* `appModules.lockapp.LockAppObject` debería reemplazarse con `NVDAObjects.lockscreen.LockScreenObject`. (GHSA-rmq3-vvhq-gp32)
* `appModules.lockapp.AppModule.SAFE_SCRIPTS` debería reemplazarse con `utils.security.getSafeScripts()`. (GHSA-rmq3-vvhq-gp32)

## 2022.2

Esta versión inclúe moitos arranxos de fallos.
En particular, hai grandes melloras para aplicacións baseadas en Java, para pantallas braille e para características de Windows.

Introducíronse novas ordes de navegación de táboas.
Actualizouse Unicode CLDR.
Actualizouse LibLouis, o que inclúe unha táboa braille alemana nova.

### Novas Características

* Soporte para interactuar con Microsoft Loop Components en productos de Microsoft Office. (#13617)
* Engadíronse novas ordes de navegación por táboas. (#957)
 * `control+alt+inicio/fin` para saltar á primeira/última columna.
 * `control+alt+repáx/avpáx` para saltar á primeira/última fila.
* Engadiuse un script sen asignar para moverse circularmente entre cambio de modos de lingua e de dialecto. (#10253)

### Cambios

* NSIS actualizouse á versión 3.08. (#9134)
* CLDR actualizouse á versión 41.0. (#13582)
* Actualizado o transcriptor braille libLouis a [3.22.0](https://github.com/liblouis/liblouis/releases/tag/v3.22.0). (#13775)
  * Nova táboa braille: alemán grao 2 (detallada)
* Engadiuse un novo rol para controis "indicador ocupado". (#10644)
* O NVDA agora anuncia cando non se poda realizar unha acción. (#13500)
  * Esto inclúe cando:
    * Se use a versión do NVDA da Tenda de Windows.
    * Nun contexto seguro.
    * Esperando pola resposta dun diálogo modal.

### Arranxo de Fallos

* Arranxos para aplicacións baseadas en Java:
  * O NVDA agora anunciará o estado de só lectura. (#13692)
  * O NVDA agora anunciará os estados deshabilitado/habilitado correctamente. (#10993)
  * O NVDA agora anunciará os atallos de teclas de función. (#13643)
  * O NVDA agora pode pitar ou falar en barras de progreso. (#13594)
  * O NVDA xa non eliminará incorrectamente texto dos widgets cando se presenten ao usuario. (#13102)
  * O NVDA agora anunciará o estado dos botóns conmutables. (#9728)
  * O NVDA agora identificará a xanela nunha aplicación Java con varias xanelas. (#9184)
  * O NVDA agora anunciará información da posición para controis de pestaña. (#13744)
* Arranxos de braille:
  * Arranxada a saída braille ao navegar por certo texto en conrois de edición enriquecidos de Mozilla, coma redactar unha mensaxe en Thunderbird. (#12542)
  * Cando se segue ao braille automáticamente e o rato móvese co seguemento do rato habilitado,
   as ordes de revisión de texto agora actualizan a pantalla braille co contido falado. (#11519)
  * Agora é posible desprazar a pantalla braille polo contido ao usar as ordes de revisión de texto. (#8682)
* O instalador de NVDA agora pode executarse dende directorios con caracteres especiais. (#13270)
* En Firefox, o NVDA xa non falla ao anunciar elementos en páxinas web onde os atributos aria-rowindex, aria-colindex, aria-rowcount ou aria-colcount sexan inválidos. (#13405)
* O cursor xa non cambia de fila ou de columna ao se usar a navegación de táboas para navegar polas celdas fusionadas. (#7278)
* Ao ler PDFs non interactivos en Adobe Reader, o tipo e estado dos campos de formulario (como caixas de verificación e botóns de opción) agora anúncianse. (#13285)
* "Reiniciar a configuración aos valores predeterminados de fábrica" agora é acesible no menú de NVDA durante o modo seguro. (#13547)
* Calquera tecla de rato bloqueada desbloquearase cando se saia do NVDA, anteriormente o botón do rato seguía bloqueado. (#13410)
* Visual Studio agora anuncia os números de liña. (#13604)
  * Ten en conta que para que funcione o anunciado de números de liña, debe estar habilitado o amosado de números de liña en Visual Studio e en NVDA.
* Visual Studio agora anuncia correctamente a sangría de liñas. (#13574)
* O NVDA anunciará de novo unha vez os detalles dos resultados da procura do menú Inicio en versións recentes de Windows 10 e 11. (#13544)
* Na versión 10.1908 e superior da calculadora en Windows 10 e 11,
O NVDA anunciará resultados cando se pulsen máis ordes, coma ordes do modo científico. (#13386)
* En Windows 11 é posible de novo navegar e interactuar con elementos da interface de usuario
coma Barra de tarefas e visualizador de Tarefas usando interación de rato e tactil. (#13508)
* O NVDA anunciará o contido da barra de estado en Notepad en Windows 11. (#13386)
* O resaltado do navegador de obxectos agora aparece inmediatamente trala activación da característica. (#13641)
* Arránxase a lectura dos elementos da vista de listaxe duna soa columna. (#13659, #13735)
* Arránxase o cambio automático de lingua de eSpeak para inglés e francés voltando a seren inglés británico e francés (Francia). (#13727)
* Arránxase o cambio automático de lingua de OneCore cando se tenta cambiar a unha lingua xa instalada. (#13732)

### Cambios para Desenvolvedores

* Agora admítese compilar as dependencias do NVDA con Visual Studio 2022 (17.0).
aínda se usa Visual Studio 2019 para compilacións de desenvolvemento e de lanzamento. (#13033)
* Cando se recupera a conta dos fillos selecionados a través de accSelection,
o caso se un ID de fillo negativo ou se devolve un IDispatch por `IAccessible::get_accSelection` agora manéxase apropriadamente. (#13276)
* Novas funcións convintes `registerExecutableWithAppModule` e `unregisterExecutable` engadíronse ao módulo `appModuleHandler`.
Poden usarse para usar un so App Module con varios executables. (#13366)

#### Obsolescencias

Estos son os cambios de ruptura de API propostos.
A parte obsoleta da API continuará estando dispoñible ate a versión especificada.
Se non se especifica unha versión, o plan para a eliminación non foi determinado.
Nota, a folla de ruta para a eliminación é 'o maior dos esforzos' e pode estar suxeito a cambios.
Por favor proba a nova API e proporciona retroalimentación.
Para autores de complementos, por favor abre un comentario de GitHub se estos cambios alonxan a API das túas necesidades.

* Foi posto coma obsoleto `appModuleHandler.NVDAProcessID` - usa `globalVars.appPid` a cambio. (#13646)
* `gui.quit` foi posto como obsoleto, usa `wx.CallAfter(mainFrame.onExitCommand, None)` a cambio. (#13498)
  -
* Algúns alias appModules márcanse coma obsoletos e borraranse en 2023.1.
O código que se importe dende un deles, debería importarse dende o módulo reemplazado a cambio.  (#13366)

| Nome do módulo eliminado |Módulo de reemprazo|
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

## 2022.1 =

Esta versión inclúe grandes melloras para o soporte UIA con MS Office.
Para Microsoft Office 16.0.15000 e superiores en Windows 11, o NVDA usará UI Automation para aceder a documentos de Microsoft Word por defecto.
Esto proporciona unha mellora de rendemento significativa sobre o vello modelo de aceso de obxectos.

Hai melloras para os controladores de pantalla braille incluindo Seika Notetaker, Papenmeier e HID Braille.
Tamén hai varios arranxos de erros para Windows 11, para aplicacións como a Calculadora, a Consola, a Terminal, Mail e o Panel de Emoji.

Actualizáronse eSpeak-NG e LibLouis, engadíronse novas táboas Xaponesa, Alemana e Catalana.

Nota:

 * Esta versión rompe a compatibilidade cos complementos existentes.

### Novas Características

* Soporte para o anunciado de notas en MS Excel co UI Automation habilitado en Windows 11. (#12861)
* En compilacións recentes de Microsoft Word a través de UI Automation en Windows 11, a existencia de marcas, borradores de comentarios e comentarios resoltos agora anúncianse en voz e braille. (#12861)
* O novo parámetro de liña de ordes `--lang` sempre sobrescrebe a lingua configurada de NVDA. (#10044)
* O NVDA agora advirte sobre os parámetros de liña de ordes que son descoñecidos e que non se usan por ningún compremento. (#12795)
* En Microsoft Word acesado a través de UI Automation, o NVDA agora fará uso de mathPlayer para ler e navegar as ecuacións matemáticas de Office. (#12946)
  * Para que esto funcione, debes estar executando Microsoft Word 365/2016 compilación 14326 ou posterior.
  * As ecuacións MathType tamén deben converterse manualmente a Office Math selecionando cada unha e escollendo Opcións de Ecuación -> Converter a Office Math no menú de contexto.
* Actualizuse o anunciado de "ten detalles" e a orde asociada para resumir a relación de detalles para que funcionen en modo foco. (#13106)
* A Seika Notetaker agora pode autodetectarse ao conectala a través do USB e do Bluetooth. (#13191, #13142)
  * Esto afecta aos seguintes dispositivos: MiniSeika (16, 24 celdas), V6 e V6Pro (40 celdas)
  * A seleción manual do porto bluetooth COM tamén se admite agora.
* Engadida unha orde para conmutar o Visualizador de braille; non hai un xesto predeterminado asociado. (#13258)
* Engadidas ordes para conmutar varios modificadores simultáneamente cunha pantalla braille (#13152)
* O diálogo diccionarios da fala agora implementa un botón "Borrar todo" para axudar a borrar  un diccionario enteiro. (#11802)
* Engadido o soporte para a Calculadora de Windows 11. (#13212)
* En Microsoft Word con UI Automation habilitado en Windows 11,  os números de liña e de seción agora poden anunciarse.  (#13283, #13515)
* Para Microsoft Office 16.0.15000 e superiores en Windows 11, o NVDA utilizará UI Automation para aceder a documentos de Microsoft Word por defecto, proporcionando unha significativa mellora de rendemento sobre o aceso ao vello modelo de obxectos. (#13437)
 * Esto inclúe documentos no proprio Microsoft Word e tamén no lector e redactor de mensaxes en Microsoft Outlook.

### Cambios

* Espeak-ng actualizouse a 1.51-dev commit `7e5457f91e10`. (#12950)
* Actualizado o transcriptor braille liblouis a [3.21.0](https://github.com/liblouis/liblouis/releases/tag/v3.21.0). (#13141, #13438)
  * Engadida nova táboa braille: braille literario Xaponés (Kantenji)
  * Engadida nova táboa alemana braille computerizado de 6 puntos.
  * Engadida nova táboa braille catalana grado 1. (#13408)
* O NVDA anunciará a seleción e a fusión de celdas en LibreOffice Calc 7.3 e posterior. (#9310, #6897)
* Actualizado o Unicode Common Locale Data Repository (CLDR) a 40.0. (#12999)
* `NVDA+Suprimir do teclado numérico` anuncia a localización do cursor ou do obxecto enfocado por defecto. (#13060)
* `NVDA+Shift+Suprimir do teclado numérico` anuncia a localización do cursor de revisión. (#13060)
* Engadidos bindings predeterminados para conmutar as teclas modificadoras ás pantallas braille de Freedom Scientific (#13152)
* Xa non se anuncia  "Baseline" a través da orde anunciar formato de texto (`NVDA+F`). (#11815)
* Activar descripción lnga xa non ten un xesto predeterminado asignado. (#13380)
* Anunciar resumo de detalles agora ten un xesto predeterminado, `NVDA+d`. (#13380)
* o NVDA necesita se reiniciar despois de instalar MathPlayer. (#13486)

### Arranxo de Fallos

* O panel do xestor do portapapeis xa non debería secuestrar incorrectamente o foco ao abrir algúns programas de Office. (#12736)
* Nun sistema onde o usuario escollera cambiar o botón primario do rato da esquerda á dereita, o NVDA xa non despregará accidentalmente un menú de contexto en lugar de activar un elemento, en aplicacións como navegadores web. (#12642)
* Ao mover o cursor de revisión máis aló do fin dos controis de texto, como en Microsoft Word con UI Automation, "inferior" anúncianse correctamente en máis situacións. (#12808)
* O NVDA pode anunciar o nome da aplicación e a versión para os binarios colocados en system32 cando se executen nunha versión de 64 bits de Windows. (#12943)
* Mellorouse a consistencia da lectura da saída dos programas de terminal. (#12974)
  * Ten en conta que en algunhas situacións, ao insertar ou borrar caracteres no medio dunha liña, os caracteres despois do cursor poden seren lidos de novo.
* MS word con UIA: a navegación rápida por cabeceiras en modo exploración xa non se queda atascada na cabeceira final dun documento, nin esta cabeceira amósase dúas veces na listaxe de elementos do NVDA. (#9540)
* En Windows 8 e posterior, a barra de estado do Explorador de Arquivos agora pódese recuperar usando o xesto estándar NVDA+fin (escritorio) / NVDA+shift+fin (portátil). (#12845)
* As mensaxes entrantes no chat de Skype for Business anúncianse de novo. (#9295)
* O NVDA pode voltar a atenuar o audio ao se usar o sintetizador SAPI5 en Windows 11. (#12913)
* Na Calculadora de Windows 10, o NVDA anunciará as etiquetas da listaxe de elementos do historial e da memoria. (#11858)
* Os xestos coma o desprazamento e enrutamento voltan a funcionar cos dispositivos HID Braille. (#13228)
* Windows 11 Mail: despois de cambiar o foco entre aplicacións, mentres se lía un correo electrónico longo, o NVDA quedábase atascado nunha liña do correo. (#13050)
* HID braille: os xestos cor (por exemplo: `espazo+punto4`) pódense realizar con éxito dende a pantalla braille. (#13326)
* Arranxado un fallo polo que se podían abrir varios diálogos de opcións ao mesmo tempo. (#12818)
* Arranxado un problema polo que algunhas pantallas braille Focus Blue deixaban de funcionar despois de que se espertase o computador tras a suspensión. (#9830)
* Xa non se anuncia 'Baseline' cando a opción 'anunciar superíndice e subíndice' estea activa. (#11078)
* En Windows 11, o NVDA xa non impedirá a navegación no panel de emoji ao se selecionar emojis. (#13104)
* Evítase un erro que causaba un dobre anunciado ao se usar a consola de Windows e a Terminal. (#13261)
* Arranxados varios casos nos que os elementos da listaxe non se podían anunciar en aplicacións de 64 bits, como REAPER. (#8175)
* No xestor de descargas de Microsoft Edge, o NVDA agora cambiará automáticamente a modo Foco unha vez o elemento de listaxe coa descarga máis recente obteña o foco. (#13221)
* O NVDA xa non provoca que as versións de 64 bits de Notepad++ 8.3 e superiores se colguen. (#13311)
* Adobe Reader xa non se colga ao arrancar se o modo protexido de Adobe Reader está habilitado. (#11568)
* Arranxado un fallo onde ao selecionar o controlador da pantalla braille Papenmeier provocaba que o NVDA se colgase. (#13348)
* En Microsoft word con UIA: o número de páxina e outros formatos xa non se anuncian inapropriadamente ao se mover dende unha celda de táboa en branco a unha celda con contido, ou dende o final do documento a un contido existente. (#13458, #13459)
* O NVDA xa non falla ao anunciar o título de páxina e ao comezar a lectura automática cando se cargue unha páxina en Google chrome 100. (#13571)
* O NVDA xa non se bloquea ao se reiniciar a configuración de NVDA aos valores predeterminados de fábrica mentras falar teclas de ordes estea activado. (#13634)

### Cambios para Desenvolvedores

* Nota: esta é unha versión que rompe a compatibilidade coa API dos comprementos. os comprementos terán que voltar a probarse e actualizar o seu manifesto.
* Aíndaque o NVDA segue a requerir o Visual Studio 2019, as compilacións xa non deberían fallar se se instala unha versión máis recente de Visual Studio (por exemplo, 2022) xunto con 2019. (#13033, #13387)
* Actualizado SCons á versión 4.3.0. (#13033)
* Actualizado py2exe á versión 0.11.0.1.0 (#13510)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` borrouse. Usa `apiLevel` a cambio. (#12955, #12660)
* `TVItemStruct` borrouse de `sysTreeView32`. (#12935)
* `MessageItem` borrouse dol appModule Outlook. (#12935)
* As constantes `audioDucking.AUDIODUCKINGMODE_*` agora son unha `DisplayStringIntEnum`. (#12926)
  * o seu uso debería substituirse con `AudioDuckingMode.*`
  * O uso de `audioDucking.audioDuckingModes` debería remprazarse con `AudioDuckingMode.*.displayString`
* O uso das constantes `audioDucking.ANRUS_ducking_*` debería remprazarse con `ANRUSDucking.*`. (#12926)
* Cambios en `synthDrivers.sapi5` (#12927):
  * o uso de `SPAS_*` debería remprazarse con `SPAudioState.*`
  * o uso de `constants.SVSF*` debería remprazarse con `SpeechVoiceSpeakFlags.*`
    * Nota: `SVSFlagsAsync` debería remprazarse con `SpeechVoiceSpeakFlags.Async` non con `SpeechVoiceSpeakFlags.lagsAsync`
  * o uso de `constants.SVE*` debería remprazarse con `SpeechVoiceEvents.*`
* o appModule `soffice` borrou as seguintes crasses e funcións `JAB_OOTableCell`, `JAB_OOTable`, `gridCoordStringToNumbers`. (#12849)
* `core.CallCancelled` agora é `exceptions.CallCancelled`. (#12940)
* Todas as constantes que comecen con RPC de `core` e de `logHandler` movéronse a `RPCConstants.RPC` enum. (#12940)
* Recoméndase que as funcións `mouseHandler.doPrimaryClick` e `mouseHandler.doSecondaryClick` deberían usarse para facer clic co rato que realicen unha ación lóxica como activar (primario) ou secundario (amosar menú de contexto),
en lugar de usar `executeMouseEvent` e especificar os botóns esquerdo e dereito do rato específicamente.
Esto asegura que o código respetará a configuración do usuario de Windows para intercambiar o botón primario do rato. (#12642)
* `config.getSystemConfigPath` borrouse - non hai remprazo. (#12943)
* `shlobj.SHGetFolderPath` borrouse - por favor usa `shlobj.SHGetKnownFolderPath` a cambio. (#12943)
* Borráronse as constantes `shlobj`. creouse unha nova enumeración, `shlobj.FolderId` para usar con `SHGetKnownFolderPath`. (#12943)
* `diffHandler.get_dmp_algo` e `diffHandler.get_difflib_algo` remprazáronse con `diffHandler.prefer_dmp` e `diffHandler.prefer_difflib` respectivamente. (#12974)
* `languageHandler.curLang` borrouse - para obter a lingua actual do NVDA usa `languageHandler.getLanguage()`. (#13082)
* Pode implementarse un novo método `getStatusBarText` nun appModule para persoalizar o modo no que o NVDA obtén o texto da barra de estado. (#12845)
* `globalVars.appArgsExtra` eliminouse. (#13087)
  * Se o teu compremento necesita procesar argumentos adicionais de liña de ordes consulta a documentación de `addonHandler.isCLIParamKnown` e a guía de desenvolvedores para máis detalles.
* O módulo UIA handler e outros módulos UIA soportados agora son parte dun paquete UIAHandler. (#10916)
  * `UIAUtils` agora é `UIAHandler.utils`
  * `UIABrowseMode` agora é `UIAHandler.browseMode`
  * `_UIAConstants` agora é `UIAHandler.constants`
  * `_UIACustomProps` agora é `UIAHandler.customProps`
  * `_UIACustomAnnotations` agora é `UIAHandler.customAnnotations`
* As constantes `IAccessibleHandler` `IA2_RELATION_*` remprazáronse coa `IAccessibleHandler.RelationType` enum. (#13096)
  * Borrado `IA2_RELATION_FLOWS_FROM`
  * Borrado `IA2_RELATION_FLOWS_TO`
  * Borrado `IA2_RELATION_CONTAINING_DOCUMENT`
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` e `LOCALE_SLANGDISPLAYNAME` borráronse de `languageHandler` - usa membros de `languageHandler.LOCALE` a cambio. (#12753)
* Cambiamos de Minhook a Microsoft Detours como librería de enganche para o NVDA. O enganche con esta librería úsase principalmente para axudar ao modelo de visualización. (#12964)
* `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` borrouse. (#13211)
* SCons agora compílase con varias tarefas concurrrentes, igual ao número de procesadores lóxicos do sistema.
Esto pode reducir dramáticamente os tempos de compilación en sistemas multinúcleo. (#13226)
* As constantes `characterProcessing.SYMLVL_*` borráronse - por favor usa `characterProcessing.SymbolLevel.*` a cambio. (#13248)
* As funcións `loadState` e `saveState` borráronse de addonHandler - por favor usa `addonHandler.state.load` e `addonHandler.state.save` a cambio. (#13245)
* Moveuse a capa de interacción UWP/OneCore de NVDAHelper [de C++/CX a C++/Winrt](https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/move-to-winrt-from-cx). (#10662)
* Agora é obrigatorio usar a subcrase `DictionaryDialog`. (#13268)
* `config.RUN_REGKEY`, `config.NVDA_REGKEY` están obsoletas, por favor usa `config.RegistryKey.RUN`, `config.RegistryKey.NVDA` a cambio. Borraranse en 2023. (#13242)
* `easeOfAccess.ROOT_KEY`, `easeOfAccess.APP_KEY_PATH` están obsoletas, por favor usa `easeOfAccess.RegistryKey.ROOT`, `easeOfAccess.RegistryKey.APP` a cambio. Borraranse en 2023. (#13242)
* `easeOfAccess.APP_KEY_NAME` quedou obsoleta, borrarase en 2023. (#13242)
* `DictionaryDialog` e `DictionaryEntryDialog` novéronse dende `gui.settingsDialogs` a `gui.speechDict`. (#13294)
* As relacións IAccessible2 agora amósanse en información para desenvolvedores para obxectos IAccessible2. (#13315)
* `languageHandler.windowsPrimaryLCIDsToLocaleNames` borrouse, a cambio usa `languageHandler.windowsLCIDToLocaleName` or `winKernel.LCIDToLocaleName`. (#13342)
* A propiedade `UIAAutomationId` para obxectos UIA debería preferirse a `cachedAutomationId`. (#13125, #11447)
  * `cachedAutomationId` pode usarse se se obtén directamente do elemento.
* `NVDAObjects.window.scintilla.CharacterRangeStruct` moveuse a `NVDAObjects.window.scintilla.Scintilla.CharacterRangeStruct`. (#13364)
* O boolean `gui.isInMessageBox` borrouse, por favor usa a función `gui.message.isModalMessageBoxActive` a cambio. (#12984, #13376)
* `controlTypes` separouse en varios submodules. (#12510, #13588)
  * `ROLE_*` e `STATE_*` remprrazáronse por `Role.*` e `State.*`.
  * Aíndaque todavía están dispoñibles, as seguintes deben considerarse obsoletas:
    * `ROLE_*` e `STATE_*`, usa `Role.*` e `State.*` a cambio.
    * `roleLabels`, `stateLabels` e `negativeStateLabels`, usos coma `roleLabels[ROLE_*]` deberíanse de remprazar polas súas equivalencias `Role.*.displayString` ou `State.*.negativeDisplayString`.
    * `processPositiveStates` e `processNegativeStates` deberían usar `processAndLabelStates` a cambio.
* As constantes de celda de Excel (`NVSTATE_*`) agora son valores no enum `NvCellState`, refrectidas na enum `NvCellState` en `NVDAObjects/window/excel.py` e mapeadas en `controlTypes.State` a través de _nvCellStatesToStates. (#13465)
* O menbro da estructura `EXCEL_CELLINFO` `state` agora é `nvCellStates`.
* `mathPres.ensureInit` borrouse, MathPlayer agora reinicialízase cando o NVDA arranca. (#13486)

## 2021.3.5

Esta é unha versión menor para arranxar un problema de seguridade.
Por favor, comunica responsablemente os fallos de seguridade a <info@nvaccess.org>.

### Arranxos de Seguridade

* Arranxouse o aviso de seguridade `GHSA-xc5m-v23f-pgr7`.
  * O diálogo pronunciación de símbolos agora deshabilítase en modo seguro.

## 2021.3.4

Esta é unha versión menor para arranxar varios problemas de seguridade descobertos.
Por favor, comunica responsablemente os fallos de seguridade a <info@nvaccess.org>.

### Arranxos de Seguridade

* Arranxouse o aviso de seguridade `GHSA-354r-wr4v-cx28`. (#13488)
  * Quítase a capacidade de arrancar o NVDA co rexistro de depuración habilitado cando o NVDA se executa en modo seguro.
  * Quítase a capacidade de actualizar o NVDA cando o NVDA se execute en modo seguro.
* Arranxouse o aviso de seguridade `GHSA-wg65-7r23-h6p9`. (#13489)
  * Quítase a capacidade de abrir o diálogo Xestos de Entrada en modo seguro.
  * Quítase a capacidade de abrir os diálogos de diccionario predeterminado, diccionario temporal e diccionario por voces en modo seguro.
* Arranxouse o aviso de seguridade `GHSA-mvc8-5rv9-w3hx`. (#13487)
  * A utilidade wx GUI inspection agora está desactivada en modo seguro.

## 2021.3.3

Esta versión é idéntica á 2021.3.2.
Existía un erro no NVDA 2021.3.2 no que se identificaba incorrectamente como 2021.3.1.
Nesta versión identifícase correctamente como 2021.3.3.

## 2021.3.2

Esta é unha versión menor para arranxar varios problemas de seguridade atopados.
Por favor, comunica responsablemente os fallos de seguridade a <info@nvaccess.org>.

### Arranxo de Erros

* Aranxo de seguridade: evítase a navegación de obxectos fora da pantalla de bloqueo en Windows 10 e Windows 11. (#13328)
* Arranxo de seguridade: a caixa de diálogo do Administrador de complementos está agora desactivada nas pantallas seguras. (#13059)
* Arranxo de seguridade: a axuda de contexto de NVDA xa non está dispoñible en pantallas seguras. (#13353)

## 2021.3.1

Esta é unha versión menor para arranxar varios problemas en 2021.3.

### Cambios

* O novo protocolo HID Braille xa non é o preferido cando se poda usar outro controlador de pantalla braille. (#13153)
* O novo protocolo HID Braille pode deshabilitarse a través dunha configuración no panel de opcións avanzadas. (#13180)

### Arranxo de Erros

* De novo acúrtanse as rexións en braille. #13158
* Arranxada a autodeteción inestable das pantallas braille Humanware Brailliant e APH Mantis Q40 cando se usa o Bluetooth. (#13153)

## 2021.3

Esta versión introduce o soporte para a nova especificación Braille HID.
Esta especificación tenta estandarizar o soporte de pantallas braille sen a necesidade de controladores individuais.
Hai actualizacións para eSpeak-NG e LibLouis, incluindo táboas novas para ruso e Tshivenda.
Os sons de erro poden habilitarse en compilacións estables de NVDA a través dunha opción nova nas opcións avanzadas.
Falar todo en Word agora despraza a vista para manter visible a posición actual.
Hai moitas melloras ao se usar Office con UIA.
Un dos arranxos de UIA é que Outlook agora ignora máis tipos de táboas de deseño nas mensaxes.

Notas importantes:

Debido a unha actualización do noso certificado de seguridade, un pequeno número de usuarios obtén un erro cando o NVDA 2021.2 procura actualizacións.
O NVDA agora pide a Windows que actualice os certificados de seguridade, o que evitará este erro no futuro.
Os usuarios afectados terán que descargar esta actualización manualmente.

### Novas Características

* Engádese un xesto de entrada para conmutar opcións para anunciar o estilo de bordes da celda. (#10408)
* Soporte para a nova especificación HID Braille que pretende estandarizar o soporte para pantallas Braille. (#12523)
  * Os dispositivos que admitan esta especificación autodetectaranse polo NVDA.
  * Para máis detalles técnicos sobre a implementación de NVDA desta especificación, consulta https://github.com/nvaccess/nvda/blob/master/devDocs/hidBrailleTechnicalNotes.md
* Engadido o soporte para o dispositivo braille VisioBraille Vario 4. (#12607)
* Pódense habilitar as notificacións de erro (opcións avanzadas) cando se use calquera versión do NVDA. (#12672)
* En Windows 10 e posterior, o NVDA anunciará o reconto de suxerencias ao introducir termos de busca en aplicacións como a configuración e a Tenda de Microsoft. (#7330, #12758, #12790)
* A navegación por táboas é agora compatible cos controis de grella creados mediante o cmdlet Out-GridView en PowerShell. (#12928)

### Cambios

* Espeak-ng actualizouse a 1.51-dev commit `74068b91bcd578bd7030a7a6cde2085114b79b44`. (#12665)
* o NVDA usará por defecto eSpeak se non hai voces OneCore instaladas que admitan a lingua preferida en NVDA. (#10451)
* Se as voces OneCore non falan con consistencia vóltase a usar a eSpeak coma sintetizador. (#11544)
* Ao ler a barra de estado con `NVDA+fin`, o cursor de revisión xa non se move á súa localización.
Se necesitas esta funcionalidade por favor asigna un xesto ao script apropriado na categoría Navegador de obxectos no diálogo xestos de Entrada. (#8600)
* Ao abrir unha caixa de diálogo de opcións que xa estea aberta, o NVDA pon o foco na caixa de diálogo existente en lugar de xerar un erro. (#5383)
* Actualizado o transcriptor braille liblouis a [3.19.0](https://github.com/liblouis/liblouis/releases/tag/v3.19.0). (#12810)
  * Novas tablas braille: Ruso grao 1, Tshivenda grao 1, Tshivenda grao 2
* En lugar de "contenido marcado" ou "mar", anunciarase "resaltado" ou "rstd" para a voz e o braille respectivamente. (#12892)
* O NVDA xa non tentará saír cando os diálogos estean a esperar unha acción requerida (ex.: Confirmar/Cancelar). (#12984)

### Arranxo de Fallos

* O seguemento das teclas modificadoras (coma Control, ou Insertar) é máis robusto cando watchdog se estea recuperando. (#12609)
* Volta a seren posible comprobar as actualizacións do NVDA en certos sistemas; por exemplo, instalacións limpas de Windows. (#12729)
* O NVDA anuncia correctamente as celdas da táboa en branco en Microsoft Word cando se usa UI automation. (#11043)
* Nas celdas da grella de datos ARIA na web, a tecla Escape agora pasará á grella e xa non desactivará o modo foco incondicionalmente. (#12413)
* Ao ler unha celda de cabeceira dunha táboa en Chrome, arránxase que o nome da columna se anuncie dúas veces. (#10840)
* O NVDA xa non informa dun valor numérico para os deslizadores UIA que teñan definida unha representación textual do seu valor. (Agora prefírese UIA ValuePattern a RangeValuePattern). (#12724)
* O NVDA xa non trata o valor dos deslizadores de UIA coma se fora sempre porcentual.
* A notificación da ubicación dunha celda en Microsoft Excel cando se acesa a través de UI Automation volta a funcionar correctamente en Windows 11. (#12782)
* O NVDA xa non estabrece configuracións rexionais de Python non válidas. (#12753)
* Se se desinstala un compremento deshabilitado e se volta a instalar, vóltase a habilitar. (#12792)
* Arranxáronse os erros relacionados coa actualización e borrado de comprementos cando o cartafol de comprementos se renomeara ou teña arquivos abertos. (#12792, #12629)
* Cando se usa UI automation para acesar aos controis das follas de cálculo de Microsoft Excel, o NVDA xa non anuncia de xeito redundante cando se seleciona unha soa celda. (#12530)
* Lese automáticamente máis texto de diálogo en LibreOffice Writer, coma nos diálogos de confirmación. (#11687)
* A lectura e navegación co modo exploración en Microsoft Word a través de UI automation agora garante que o documento sempre se desprace para que a posición actual do modo exploración sexa visible, e que a posición do cursor no modo foco reflicta correctamente a posición do modo exploración. (#9611)
* Cando se realiza a función "Falar todo" en Microsoft Word mediante UI automation, o documento desprázase automáticamente e a posición do cursor actualízase correctamente. (#9611)
* Cando se len correos electrónicos en Outlook e o NVDA está acesando aá mensaxe con UI automation, certas táboas están agora marcadas coma táboas de deseño, o que significa que xa non serán anunciadas por defecto. (#11430)
* Arranxouse un erro pouco frecuente ao cambiar os dispositivos de audio. (#12620)
* A entrada con táboas braille literarias debería comportarse de xeito máis fiable cando se trata de campos de edición. (#12667)
* Ao navegar polo calendario da bandexa do sistema de Windows, o NVDA anuncia agora o día da semán na súa totalidade. (#12757)
* Cando se usa un método de entrada en chino como Taiwán - Microsoft Quick en Microsoft Word, o desprazamento da pantalla braille cara adiante e cara atrás xa non salta incorrectamente á posición orixinal do cursor. (#12855)
* Ao acesar a documentos de Microsoft Word a través de UIA, a navegación por frases (alt+flecha abajo / alt+flecha arriba) volta a seren posible. (#9254)
* Ao acesar a MS Word con UIA, agora anúnciase a sangría dos parágrafos. (#12899)
* Ao aceder a MS Word con UIA, agora anúnciase a orde de seguemento de cambios e algunhas outras ordes localizadas en Word. (#12904)
* Arranxados os duplicados en braille e voz cando a 'descripción' coincida co 'contido' ou co 'nome'. (#12888)
* En MS Word con UIA activado, hai unha reprodución máis precisa dos sons de erros ortográficos mentres se escribe. (#12161)
* En Windows 11, o NVDA xa non anunciará "panel" ao premer Alt+Tab para cambiar de programa. (#12648)
* O novo panel lateral de seguemento de Comentarios Modernos agora é compatible co MS Word cando non se acceda ao documento a través de UIA. Preme alt+f12 para moverte entre o panel lateral de seguemento e o documento. (#12982)

### Cambios para Desenvolvedores

* Compilar NVDA agora require Visual Studio 2019 16.10.4 ou posterior.
Para que coincida co entorno de compilación de producción, actualiza Visual Studio para que estea sincronizado coa [versión actual que AppVeyor está usando](https://www.appveyor.com/docs/windows-images-software/#visual-studio-2019). (#12728)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` foi marcado coma obsoleto para eliminar en 2022.1. (#12660)
  * No seu lugar usa `apiLevel` (consulta os comentarios  en `_UIAConstants.WinConsoleAPILevel` para máis detalles).
* A transparencia da cor de fondo do texto procedente das aplicacións GDI (a través do modelo de visualización), está agora exposta para os complementos ou appModules. (#12658)
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` e `LOCALE_SLANGDISPLAYNAME` movéronse ao enum de `LOCALE` en languageHandler.
Aínda están dispoñibles a nivel de módulo, pero están obsoletos e eliminaranse en NVDA 2022.1. (#12753)
* O uso das funcións `addonHandler.loadState` e `addonHandler.saveState` debe sustituirse polas súas equivalentes `addonHandler.state.save` e `addonHandler.state.load` antes de 2022.1. (#12792)
* A saída braille agora pódese comprobar en probas do sistema. (#12917)

## 2021.2

Esta versión introduce o soporte preliminar para Windows 11.
Aínda que Windows 11 non se lanzou, esta versión provouse en versións preliminares de Windows 11.
Inclúese un arranxo importante para a Cortina de Pantalla (consulta Notas importantes).
A ferramenta COM Registration Fixing agora pode resolver máis problemas cando se executa o NVDA.
Hai actualizacións para o sintetizador eSpeak e para o transcriptor braille LibLouis.
Tamén hai varios arranxos de fallos e melloras, en particular para o soporte de braille e para as terminais de Windows, para a calculadora, o panel de emoji e para o historial do portapapeis.

### Notas importantes

Debido a un cambio na API Windows Magnification, a Cortina de Pantalla tivo que seren actualizada para admitir as versións máis novas de Windows.
Usa o NVDA 2021.2 para activar a Cortina de Pantalla con Windows 10 21H2 (10.0.19044) ou posteriores.
Esto inclúe Windows 10 Insiders e Windows 11.
Por razóns de seguridade, ao usar unha versión nova de Windows, obtén unha confirmación visual de que a Cortina de Pantalla faga que esta estea totalmente negra.

### Novas características

* Soporte experimental para anotacións ARIA:
  * engade unha orde para ler un resumo de detalles dun obxecto con aria-details. (#12364)
  * engade unha opción en preferencias avanzadas para anunciar se un obxecto ten detalles en modo Exploración. (#12439)
* En Windows 10 Versión 1909 e posteriores (incluindo Windows 11), o NVDA anunciará o reconto de suxerencias ao se realizar buscas no Explorador de Arquivos. (#10341, #12628)
* En Microsoft Word, o NVDA agora anuncia o resultado dos atallos de sangría e sangría francesa cando se executen. (#6269)

### Cambios

* Espeak-ng actualizouse a 1.51-dev commit `ab11439b18238b7a08b965d1d5a6ef31cbb05cbb`. (#12449, #12202, #12280, #12568)
* Se se activa artigo nas preferencias de usuario para formateado de documentos, o NVDA anuncia "artigo" despois do contido. (#11103)
* Actualizado o transcriptor braille liblouis a [3.18.0](https://github.com/liblouis/liblouis/releases/tag/v3.18.0). (#12526)
  * Novas táboas braille: Búlgaro grao 1, Birmano grao 1, Birmano grao 2, Kazaxo grao 1, Xemer grao 1, Kurdo do norte grao 0, Sepedi grao 1, Sepedi grao 2, Sesotho grao 1, Sesotho grao 2, Setswana grao 1, Setswana grao 2, Tártaro grao 1, Vietnamés grao 0, Vietnamés grao 2, Vietnamés do sul grao 1, Xhosa grao 1, Xhosa grao 2, Yakut grao 1, Zulú grao 1, Zulú grao 2
* O OCR de Windows 10 pasou a chamarse OCR de Windows. (#12690)

### Corrección de Erros

* Na Calculadora de Windows 10, o NVDA anunciará as expresións da calculadora sobre a pantalla braille. (#12268)
* Nos programas de terminal en Windows 10 versión 1607 e posterior, ao se insertar ou se eliminar caracteres no medio dunha liña, xa non se len os caracteres á dereita do cursor. (#3200)
  * Agora Diff Match Patch actívase por defecto. (#12485)
* A entrada braille funciona correctamente coas seguintes táboas contraídas: Árabe grao 2, Español grao 2, Urdu grao 2, Chino (China, Mandarín) grao 2. (#12541)
* A ferramenta COM Registration Fixing agora resolve máis problemas, especialmente en Windows de 64 bit. (#12560)
* Melloras ao manexo de botóns para o dispositivo braille Seika Notetaker de Nippon Telesoft. (#12598)
* Melloras para anunciar o panel de emoji de Windows e o historial do portapapeis. (#11485)
* Actualizáronse as descripcións dos caracteres do alfabeto Bengalí. (#12502)
* O NVDA sae de xeito seguro cando se inicie un novo proceso. (#12605)
* Voltar a selecionar o controlador da pantalla braille Handy Tech dende o diálogo Selecionar Pantalla Braille xa non provoca erros. (#12618)
* A versión de Windows 10.0.22000 ou posterior recoñécese como Windows 11, non coma Windows 10. (#12626)
* Arranxouse e probouse a compatibilidade da cortina de pantalla para versións de Windows hasta a 10.0.22000. (#12684)
* Se non se amosan resultados ao filtrar os xestos de entrada, o diálogo de configuración de xestos de entrada segue funcionando coma se esperaba. (#12673)
* Arranxouse un fallo onde o primeiro elemento de menú dun submenú non se anuncia nalgúns contextos. (#12624)

### Cambios para Desenvolvedores

* A constante `characterProcessing.SYMLVL_*` debería substituirse usando a súa equivalente `SymbolLevel.*` antes de 2022.1. (#11856, #12636)
* `controlTypes` dibidiuse en varios submódulos, os símbolos marcados como obsoletos deben reemprazarse antes de 2022.1. (#12510)
  * As constantes `ROLE_*` e `STATE_*` deberían reemprazarse polas súas equivalentes `Role.*` e `State.*`.
  * As constantes `roleLabels`, `stateLabels` e `negativeStateLabels` quedaron obsoletas, os usos como `roleLabels[ROLE_*]` deberían reemprazarse polas súas equivalentes `Role.*.displayString` ou `State.*.negativeDisplayString`.
  * As etiquetas `processPositiveStates` e `processNegativeStates` quedaron obsoletas para a súa eliminación.
* En Windows 10 Versión 1511 e posterior (incluindo compilaciones Insider Preview), o nome actual da versión da característica de actualización de Windows obtense do Rexistro de Windows. (#12509)
* Obsoleto: `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` eliminarase en 2022.1, non hai un reemprazo directo. (#12544)

## 2021.1

Esta versión inclúe soporte experimental opcional para UIA en Excel e navegadores Chromium.
Hai correcións para varias linguas e para aceso ás ligas en braille.
Hai actualizacións para Unicode CLDR, para símbolos matemáticos e para LibLouis.
Así coma moitas outras correcións e melloras incluindo Office, Visual Studio e varias linguas.

Nota:

 * Esta versión rompe a compatibilidade cos complementos existentes.
 * Esta versión tamén deixa de seren compatible co Adobe Flash.

### Novas Características

* Soporte preliminar para UIA con navegadores baseados en Chromium (como Edge). (#12025)
* Soporte experimental opcional para Microsoft Excel a través de UI Automation. Só se recomenda para Microsoft Excel compilación 16.0.13522.10000 ou superior. (#12210)
* Navegación máis sinxela da saída na Consola Python do NVDA. (#9784)
  * alt+arriba/abaixo salta ao resultado anterior/seguinte (engade shift para selecionar).
  * control+l borra o panel de saída.
* O NVDA agora anuncia as categorías asignadas a unha cita en Microsoft Outlook se a hai. (#11598)
* Soporte para a pantalla braille do Anotador Electrónico Seika de Nippon Telesoft. (#11514)

### Cambios

* En modo Exploración, os controis agora poden activarse cos sensores de seguemento braille sobre o seu descriptor (Ex.: "lig" para unha liga). esto é especialmente útil para activar, por exemplo, caixas de verificación sen etiquetas. (#7447)
* O NVDA agora evita que o usuario faga o OCR de Windows 10 se a cortina de pantalla está habilitada. (#11911)
* Actualizado o repositorio Unicode Common Locale Data (CLDR) a 39.0. (#11943), #12314)
* Engadidos máis signos matemáticos ao diccionario de símbolos. (#11467)
* A guía do usuario, o ficheiro de cambios e a listaxe de teclas de ordes agora teñen un aspecto remozado. (#12027)
* Agora anúnciase "non soportado" cando se tente cambiar o deseño de pantalla en aplicacións que non o admitan como Microsoft Word. (#7297)
* A opción 'Tentar cancelar a voz para eventos de foco caducados' no panel de opcións avanzadas agora está activada por defecto. (#10885)
  * Este comportamento pódese desactivar configurando esta opción como "Non".
  * As aplicacións web (Ex.: Gmail) xa non falan información obsoleta cando se mova o foco rápidamente.
* Actualizado o transcriptor braille liblouis a [3.17.0](https://github.com/liblouis/liblouis/releases/tag/v3.17.0). (#12137)
  * Novas táboas braille: braille literario bielorruso, braille computerizado bielorruso, Urdu grao 1, Urdu grao 2.
* O soporte para contido Adobe Flash eliminouse do NVDA debido a que Adobe  desaconsella activamente o uso de Flash. (#11131)
* O NVDA sairá incluso con xanelas aínda abertas, o proceso de saída agora pecha todas as xanelas e diálogos do NVDA. (#1740)
* O Visualizador de Voz agora pode pecharse con `alt+F4` e ten un botón pechar estándar para unha interación máis sinxela cos usuarios de dispositivos sinaladores. (#12330)
* O Visualizador Braille agora ten un botón pechar estándar para unha interación máis sinxela con usuarios de dispositivos sinaladores. (#12328)
* Na caixa de diálogo listaxe de elementos, eliminouse a tecla rápida do botón "Activar" en algunhas localizacións para evitar a colisión coa etiqueta do botón de opción do tipo de elemento. Cando estea dispoñible, o botón segue a ser o predeterminado do diálogo e, como tal, pode seguer sendo chamado simplemente premendo intro dende a propria listaxe de elementos. (#6167)

### Arranxo de Fallos

* A listaxe de mensaxes en Outlook 2010 volta a ser lexible. (#12241)
* En programas de terminal en Windows 10 versión 1607 e posteriores, ao se insertar ou eliminar caracteres en medio dunha liña, xa non se len os caracteres á dereita do cursor. (#3200)
  * Esta correción experimental debe habilitarse manualmente no panel de opcións avanzadas do NVDA cambiando o algoritmo diff a Diff Match Patch.
* En MS Outlook, xa non debería producirse un anunciado de distancia inapropriada cando se faga shift+tabulador dende o corpo da mensaxe ao campo de asunto. (#10254)
* Na consola de Python, agora admítese a inserción dun tabulador para a sangría ao comenzo dunha liña de entrada non valdeira e a realización dun tabulador en medio dunha liña de entrada. (#11532)
* A información de formato e outras mensaxes navegables xa non presentan liñas en branco inesperadas cando o deseño de pantalla estea desactivado. (#12004)
* Agora é posible ler comentarios en MS Word co UIA activado. (#9285)
* Mellorouse o rendemento ao interactuar con Visual Studio. (#12171)
* Arranxáronse erros gráficos como a falla de elementos cando se utiliza NVDA con un deseño de dereita a esquerda.  (#8859)
* Respétase a direción da disposición da GUI baseada na lingua do NVDA, non na configuración rexional do sistema. (#638)
  * Problema coñecido para linguas de dereita a esquerda: O borde dereito dos grupos recórtase coas etiquetas e controis. (#12181)
* A configuración rexional de Python establécese para que coincida coa lingua selecionada nas preferencias de forma consistente, e ocorrerá cando se use a lingua por defecto. (#12214)
* TextInfo.getTextInChunks xa non se conxela cando se chame a controis de edición enriquecida como o visor de rexistro do NVDA. (#11613)
* Volta a ser posible usar o NVDA en linguas que conteñan guions baixos no nome da configuración rexional, como de_CH, en Windows 10 1803 e 1809. (#12250)
* En WordPad, a configuración do anunciado de superíndice e subíndice funciona coma se esperaba. (#12262)
* O NVDA xa non falla ao anunciar o contido recén enfocado nunha páxina web se o antigo foco desaparece e é reemplazado polo novo foco na mesma posición. (#12147)
* O tachado, o superíndice e o subíndice das celdas enteiras de Excel agora anúncianse se a opción correspondente está activada. (#12264)
* Arranxouse a copia da configuración durante a instalación dende unha copia portátil cando o directorio de configuración de destiño por defecto está valdeiro. (#12071, #12205)
* Arranxado o anunciado incorrecto dalgunhas letras con acentos ou diacríticos cando a opción 'Dicir maiús antes de maiúsculas' está marcada. (#11948)
* Arranxouse o fallo de cambio de ton no sintetizador de voz SAPI4. (#12311)
* O instalador do NVDA agora tamén respeta o parámetro de liña de ordes `--minimal` e non reproduce o son de inicio, seguindo o mesmo comportamento documentado que un executable do NVDA instalado ou con copia portátil. (#12289)
* En MS Word ou Outlook, a tecla rápida de navegación da táboa agora pode saltar á táboa de deseño se a opción "Incluir tablas de deseño" está activada na configuración do modo de navegación. (#11899)
* NVDA xa non anunciará "↑↑↑" para emojis en linguas en particular. (#11963)
* Espeak agora admite de novo o Cantonés e o Mandarín. (#10418)
* No novo Microsoft Edge baseado en Chromium os campos de texto como a barra de enderezos agora anúncianse cando estean valdeiros. (#12474)
* Arranxado o controlador braille de Seika. (#10787)

### Cambios para Desenvolvedores

* Nota: esta é unha versión que rompe a compatibilidade coa API dos complementos. Os complementos terán que voltar a se probar e actualizar o seu manifesto.
* O sistema de compilación do NVDA agora obtén todas as dependencias de Python con pip e almacénaas nun entorno virtual de Python. Todo esto faise de forma transparente.
  * Para compilar o NVDA, débese seguir utilizando SCons da forma habitual. Por exemplo, executando scons.bat na raíz do repositorio. Executar `py -m SCons` xa non se admite, e `scons.py` tamén foi eliminado.
  * Para executar o NVDA dende o código fonte, en lugar de executar `source/nvda.pyw` directamente, o desenvolvedor debe agora utilizar `runnvda.bat` na raíz do repositorio. Se tentas executar `source/nvda.pyw`, unha caixa de mensaxe avisarache de que esto xa non se admite.
  * Para realizar probas unitarias, executa `rununittests.bat [<extra unittest discover options>]>]`.
  * Para realizar probas do sistema: executa `runsystemtests.bat extra robot options>]`
  * Para realizar linting, executa `runlint.bat <base branch>`.
  * Por favor, consulta o ficheiro readme.md para máis detalles.
* Tamén se actualizaron as seguintes dependencias de Python:
  * comtypes actualizado a 1.1.8.
  * pySerial actualizado a 3.5.
  * wxPython actualizado a 4.1.1.
  * Py2exe actualizado a 0.10.1.0.
* Eliminouse `LiveText._getTextLines`. (#11639)
  * No seu lugar, sobreescribe `_getText` que devolve unha cadea de todo o texto do obxecto.
* Os obxectos `LiveText` agora poden calcular as diferencias por carácter. (#11639)
  * Para alterar o comportamento das diferencias para algún obxecto, sobreescribe a propiedade `diffAlgo` (consulta o docstring para máis detalles).
* Ao definir un script co decorador de script, pódese especificar o argumento booleano 'allowInSleepMode' para controlar se un script está dispoñible en modo de suspensión ou non. (#11979)
* Elimináronse as seguintes funcións do módulo de configuración. (#11935)
  * canStartOnSecureScreens - usa config.isInstalledCopy no seu lugar.
  * hasUiAccess e execElevated - úsaas dende o módulo systemUtils.
  * getConfigDirs - usa globalVars.appArgs.configPath no seu lugar.
* As constantes Module level REASON_* elimináronse de controlTypes - usa no seu lugar controlTypes.OutputReason. (#11969)
* Eliminouse REASON_QUICKNAV de browseMode - usa controlTypes.OutputReason.QUICKNAV no seu lugar. (#11969)
* A propiedade `NVDAObject` (y derivados) `isCurrent` ahora devolve estrictamente a crase Enum `controlTypes.IsCurrent`. (#11782)
  * A propiedade `isCurrent` xa non é Opcional, e polo tanto non devolverá Ningún.
    * Cando un obxecto non é actual, devólvese `controlTypes.IsCurrent.NO`.
* O mapeado `controlTypes.isCurrentLabels` eliminouse. (#11782)
  * A cambio us a propiedade `displayString` en un valor enum `controlTypes.IsCurrent`.
    * Por exemplo: `controlTypes.IsCurrent.YES.displayString`
* Eliminouse `winKernel.GetTimeFormat` - débese usar `winKernel.GetTimeFormatEx`.
* Eliminouse `winKernel.GetDateFormat` - úsase `winKernel.GetDateFormatEx` no seu lugar. (#12139)
* Eliminouse `gui.DriverSettingsMixin` - usa `gui.AutoSettingsMixin`. (#12144)
* Eliminouse `speech.getSpeechForSpelling` - usa `speech.getSpellingSpeech`. (#12145)
* Os comandos non se poden importar directamente dende speech como `import speech; speech.ExampleCommand()` ou `import speech.manager; speech.manager.ExampleCommand()` - usa `from speech.commands import ExampleCommand` no seu lugar. (#12126)
* `speakTextInfo` xa non enviará a voz a través de `speakWithoutPauses` se o motivo é `SAYALL`, xa que `SayAllHandler` faino agora manualmente. (#12150)
* O módulo `synthDriverHandler` xa non se importa por defecto en `globalCommands` e `gui.settingsDialogs` - usa `from synthDriverHandler import synthFunctionExample` no seu lugar. (#12172)
* Eliminouse `ROLE_EQUATION` de controlTypes - usa `ROLE_MATH` no seu lugar. (#12164)
* Elimináronse as crases `autoSettingsUtils.driverSetting` de `driverHandler` - úsaas dende `autoSettingsUtils.driverSetting`. (#12168)
* Elimináronse las crases `autoSettingsUtils.utils` de `driverHandler` - por favor, úsaas dende `autoSettingsUtils.utils`. (#12168)
* Eliminouse o soporte dos `TextInfo` que non herdan de `contentRecog.BaseContentRecogTextInfo`. (#12157)
* Eliminouse `speech.speakWithoutPauses` - por favor, usa `speech.speechWithoutPauses.SpeechWithoutPauses(speakFunc=speech.speak).speakWithoutPauses` no seu lugar. (#12195, #12251)
* Eliminouse `speech.re_last_pause` - por favor, usa `speech.speechWithoutPauses.SpeechWithoutPauses.re_last_pause` no seu lugar. (#12195, #12251)
* Os diálogos `WelcomeDialog`, `LauncherDialog` e `AskAllowUsageStatsDialog` trasladáronse a `gui.startupDialogs`. (#12105)
* Moviuse `getDocFilePath` de `gui` ao módulo `documentationUtils`. (#12105)
* O módulo gui.accPropServer, así como as crases AccPropertyOverride e ListCtrlAccPropServer do módulo gui.nvdaControls elimináronse en pro do soporte nativo de WX para anular as propiedades de accesibilidade. Ao se mellorar a accesibilidade dos controis WX, implementa wx.Accessible no seu lugar. (#12215)
* Os ficheiros en `source/comInterfaces/` son agora máis fácilmente consumibles polas ferramentas de desenvolvemento, coma os IDE. (#12201)
* Engadíronse métodos e tipos convenientes ao módulo winVersion para obter e comparar versións de Windows. (#11909)
  * Eliminouse a función isWin10 que se atopaba no módulo winVersion.
  * A crase winVersion.WinVersion é un tipo comparable e ordeable que encapsula a información da versión de Windows.
  * Engadiuse a función winVersion.getWinVer para obter unha winVersion.WinVersion que represente o sistema operativo que se está executando actualmente.
  * Engadíronse constantes de conveniencia para as versións conocidas de Windows, véase winVersion.WIN* constants.
* IAccessibleHandler xa non importa de forma estelar todo o de as interfaces IAccessible e IA2 COM - por favor, úsaas directamente. (#12232)
* Os obxectos TextInfo teñen agora propiedades de inicio y fin que poden compararse matemáticamente con operadores como < <= == != >= >. (#11613)
  * Por exemplo, ti1.start <= ti2.end
  * Agora prefírese este uso en lugar de ti1.compareEndPoints(ti2, "startToEnd") <= 0
* As propiedades de inicio e fin de TextInfo tamén poden establecerse entre sí. (#11613)
  * Por exemplo, ti1.start = ti2.end
  * Prefírese este uso en lugar de ti1.SetEndPoint(ti2, "startToEnd")
* Elimínanse `wx.CENTRE_ON_SCREEN` e `wx.CENTER_ON_SCREEN`, no seu lugar se usa `self.CentreOnScreen()`. (#12309)
* Eliminouse `easeOfAccess.isSupported`, NVDA só admite versións de Windows nas que se evalúa como `True`. (#12222)
* Moviuse `sayAllHandler` a `speech.sayAll`. (#12251)
  * `speech.sayAll.SayAllHandler` expón as funcións `stop`, `isRunning`, `readObjects`, `readText`, `lastSayAllMode`.
  * O comando `SayAllHandler.stop` tamén reinicia a instancia `SayAllHandler` `SpeechWithoutPauses`.
  * Substituiuse `CURSOR_REVIEW` e `CURSOR_CARET` por `CURSOR.REVIEW` e `CURSOR.CARET`.
* Moviuse `speech.SpeechWithoutPauses` a `speech.speechWithoutPauses.SpeechWithoutPauses`. (#12251)
* Cambiouse o nome de `speech.curWordChars` a `speech._curWordChars`. (#12395)
* Elimináronse de `speech` e pódese acesar a eles a través de `speech.getState()`. Agora son valores de só lectura. (#12395)
  * speechMode
  * speechMode_beeps_ms
  * beenCanceled
  * isPaused
* para actualizar `speech.speechMode` usa `speech.setSpeechMode`. (#12395)
* Moviuse o seguinte a `speech.SpeechMode`. (#12395)
  * `speech.speechMode_off` convírtese en `speech.SpeechMode.off`.
  * `speech.speechMode_beeps` pasa a ser `speech.SpeechMode.beeps`
  * `speechMode_talk` pasa a ser `speech.Speech.SpeechMode.talk`.
* `IAccessibleHandler.IAccessibleObjectIdentifierType` é agora `IAccessibleHandler.types.IAccessibleObjectIdentifierType`. (#12367)
* Cambiaron `NVDAObjects.UIA.WinConsoleUIA` (#12094)
  * `NVDAObjects.UIA.winConsoleUIA.is21H1Plus` renomeado a `NVDAObjects.UIA.winConsoleUIA.isImprovedTextRangeAvailable`.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfo` renomeado ao nome da crase de inicio en maiúsculas.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfoPre21H1` renomeado a `NVDAObjects.UIA.winConsoleUIA.ConsoleUIATextInfoWorkaroundEndInclusive`
    * A implementación funciona en ambos sendo incluidos os puntos finais (en rangos de texto) antes de [microsoft/terminal PR 4018](https://github.com/microsoft/terminal/pull/4018)
    * Solucións para `expand`, `collapse`, `compareEndPoints`, `setEndPoint`, etc

## 2020.4

Esta versión inclúe métodos novos de entrada de chinés, unha actualización de Liblouis e a Listaxe de Elementos (NVDA+f7) agora funciona en modo foco.
A axuda sensible ao contexto agora está dispoñible ao se premer F1 en diálogos de NVDA.
Melloras para as regras de pronunciación de símbolos, diccionarios da fala, mensaxes braille e lectura superficial.
Correción de erros e melloras para Mail, Outlook, Teams, Visual Studio, Azure Data Studio, Foobar2000.
Na web, hai melloras para Google Docs e moito mellor soporte para ARIA.
Máis moitas outras importantes correcións de erros e melloras.

### Novas Características

* Ao se premer F1 dentro dos diálogos do NVDA agora abrirase o ficheiro de axuda para a seción máis relevante. (#7757)
* Soporte para autocompletado de suxerencias (IntelliSense) en Microsoft SQL Server Management Studio máis Visual Studio 2017 e superior. (#7504)
* Pronunciación de símbolos: soporte para agrupacións nunha definición de símbolos comprexa e soporte de referencias de grupo nunha regra de substitución que fainos máis sinxelos e máis poderosos. (#11107)
* Agora notifícase aos usuarios cando tenten crear entradas de dicionarios da fala con sustitucións inválidas de expresións regulares. (#11407)
  * Específicamente agora detéctanse erros de agrupación.
* Engaiduse o soporte para os novos métodos de entrada para chinés tradicional rápido e para Pinyin en Windows 10. (#11562)
* As cabeceiras de pestana agora considéranse campos de formulario coa tecla de navegación rápida f. (#10432)
* Engadida unha orde para conmutar o anunciado de texto marcado (resaltado); Non hai ningún xesto asociado por omisión. (#11807)
* Engadido o parámetro de liña de comandos --copy-portable-config que che permite copiar automáticamente a configuración proporcionada á conta de usuario cando se instala o NVDA en silencio. (#9676)
* Agora admítese o enrutamento Braille co Visualizador Braille para usuarios de rato, desprazándose para enrutar a unha celda braille. (#11804)
* O NVDA agora detectará automáticamente os dispositivos Humanware Brailliant BI 40X e 20X a través do USB e do Bluetooth. (#11819)

### Cambios

* Actualizado o transcriptor braille liblouis á versión 3.16.1
 * Abórdánse múltiples colgues
 * Engádese a táboa Braille grao 1 de Baskir
 * Engádese unha táboa braille de ordenador copto de 8 puntos
 * Engádense táboas de braille literario ruso e braille literario ruso (detallado).
 * Engádese a táboa braille para Afrikaans grao 2
 * Bórrase a táboa braille rusa de grao 1.
* Cando se le con ler todo no modo exploración, as ordes buscar seguinte e anterior non deteñen a lectura se a opción permitir lectura superficial está activada; ler todo reanuda a partir de despois do término seguinte ou anterior atopado. (#11563)
* Para as pantallas braille HIMS remapeouse F3 a Espazo + puntos 148. (#11710)
* Melloras para o UX das opcións "Tempo de espera da mensaxe braille" e "Amosar mensaxes indefinidamente". (#11602)
* En navegadores web e outras aplicacións que soporten o modo exploración, o diálogo Listaxe de Elementos (NVDA+F7) agora pode chamarse ao estar en modo foco. (#10453)
* As actualizacións de rexións ARIA live agora suprímense cando se desactive o anunciado de cambios de contido dinámico. (#9077)
* O NVDA agora anunciará "Copiado ao portapapeis" antes do texto copiado. (#6757)
* Mellorouse a presentación da táboa de vistas gráficas no xestor de discos. (#10048)
* As etiquetas dos controis agora están desactivadas (en gris) cando o control está desactivado. (#11809)
* Actualizada a anotación emoji de CLDR á versión 38. (#11817)
* A funcionalidade incorporada "Resaltado do Foco" renomeouse a "Resaltado Visual". (#11700)

### Corrección de Erros

* o NVDA volta a funcionar correctamente cos campos de edición ao se usar a aplicación Fast Log Entry. (#8996)
* Anúnciase o tempo transcorrido en Foobar2000 se non se dispón dun tempo total (por exemplo, cando se reproduce unha transmisión en directo). (#11337)
* O NVDA agora respeta o atributo aria-roledescription en elementos en contido editable en páxinas web. (#11607)
* Xa non se anuncia 'listaxe' en cada línea de unha listaxe en Google Docs ou outro contido editable en Google Chrome. (#7562)
* Cando se navega coas frechas por caracteres ou palabras dende un elemento de listaxe a outro en contido editable na web, agora anúnciase a entrada no novo elemento de listaxe. (#11569)
* O NVDA agora le a liña correcta cando o cursor se coloca no remate dunha liga no fin dun elemento de listaxe en Google Docs ou outro contido editable na web. (#11606)
* En Windows 7, ao abrir ou pechar o menú Inicio dende o escritorio agora ponse o foco correctamente. (#10567)
* Cando se activa "Tentar cancelar eventos do foco esperados", o título da pestaña agora anúnciase de novo ao cambiar pestañas en Firefox. (#11397)
* O NVDA xa non falla ao anunciar un elemento de listaxe despois de escrebir un carácter nunha listaxe cando se fala coas voces Ivona SAPI5 . (#11651)
* É posible de novo usar o modo exploración ao ler correos electrónicos en Windows 10 Mail 16005.13110 e posteriores. (#11439)
* Cando se usen as voces Ivona SAPI5 dende harposoftware.com, o NVDA agora é capaz de gardar a configuración, cambiar de sintetizador e xa non se quedará en silenzo despois de reiniciar. (#11650)
* Agora é posible introducir o número 6 en braille computerizado dende un teclado braille en pantallas HIMS. (#11710)
* Melloras importantes no rendemento en Azure Data Studio. (#11533, #11715)
* Con "Tentar Cancelar a voz para eventos de foco expirados" activado o título do diálogo buscar do NVDA anúnciase de novo. (#11632)
* O NVDA xa non debería conxelarse cando se desperta o computador e o foco aterriza nun documento de Microsoft Edge. (#11576)
* Xa non é necesario premer tab ou mover o foco despois de pechar un menú de contexto en MS Edge para que o modo Exploración volte a ser funcional de novo. (#11202)
* O NVDA xa non falla ao ler elementos en vistas de listaxe dentro dunha aplicación de 64 bits tal como Tortoise SVN. (#8175)
* Os ARIA treegrids agora expóñense como táboas normais en modo Exploración tanto en Firefox coma en Chrome. (#9715)
* Agora pódese iniciar unha procura inversa con 'buscar anterior' a través de NVDA+shift+F3 (#11770)
* Un script de NVDA xa non se considera repetido se ocorre unha pulsación de tecla non relacionada entre as dúas execucións do script. (#11388)
* Pode suprimirse de novo o anunciado das etiquetas strong e emphasis en Internet Explorer desactivando Anunciar Énfasis nas opcións de Formato de Documentos do NVDA. (#11808)
* Xa non debería producirse un conxelado de varios segundos experimentado por unha pequena cantidade de usuarios ao pasar entre as celdas de Excel. (#11818)
* Nas compilacións de Microsoft Teams con números de versión como 1.3.00.28xxx, o NVDA xa non falla ao ler mensaxes en chats ou en canles de Teams debido a un menú incorrectamente enfocado. (#11821)
* O texto marcado coma erro ortográfico e gramatical ao mesmo tempo en Google Chrome anunciarase apropriadamente coma erro ortográfico e gramatical polo NVDA. (#11787)
* Ao usar Outlook (localización ao francés), o atallo para "Respostar a todos" (control+shift+R) funciona de novo. (#11196)
* No Visual Studio, os consellos da ferramenta IntelliSense que proporcionan detalles adicionais sobre o elemento IntelliSense selecionado actualmente só se anuncian unha vez. (#11611)
* Na calculadora de Windows 10, o NVDA non anunciará o progreso dos cálculos se se desactiva falar caracteres ao se escreber. (#9428)
* O NVDA xa non se bloquea cando se use o inglés grao 2 de Estados unidos e expándese a braille computerizado cando estea sobre el cursor ao amosar certo contido coma unha URL en braille. (#11754)
* É posible de novo anunciar información de formato para a celda de Excel enfocada usando NVDA+F. (#11914)
* A entrada QWERTY en pantallas braille Papenmeier que o admitan funciona de novo e xa non causa que o NVDA se conxele aleatoriamente. (#11944)
* En navegadores basados en Chromium, resolvéronse varios casos onde a navegación de táboas non funcionaba e o NVDA non anunciaba o número de filas e columnas da táboa. (#12359)

### Cambios para Desenvolvedores

* As probas de sistema agora poden enviar teclas usando spy.emulateKeyPress, que toma un identificador de tecla que se axusta aos proprios nomes de tecla do NVDA e por defecto tamén a bloquea hasta que se execute a acción. (#11581)
* O NVDA xa non require que o directorio actual sexa o directorio da aplicación NVDA para funcionar. (#6491)
* A opción aria live politeness para live regions agora pode atoparse en obxectos do NVDA que usen a propiedade liveRegionPoliteness. (#11596)
* Agora é posible definir xestos separados para documentos de Outlook e Word. (#11196)

## 2020.3

Esta versión inclúe varias grandes melloras para a estabilidade e o rendemento, especialmente nas aplicacións de Microsoft Office. Hai novas opcións para conmutar o soporte das pantallas táctiles e do anunciado de gráficos.
A existencia de contido marcado (resaltado) pode anunciarse nos navegadores, e hai novas táboas braille alemanas.

### Novas Características

* Agora podes conbmutar o anunciado de gráficos dende as opcións de Formateado de Documentos do NVDA.  Ten en conta que deshabilitando esta opción aínda lerá o texto alternativo dos gráficos. (#4837)
* Agora podes conmutar o soporte de pantallas táctiles do NVDA. Engadiuse unha opción ao panel de interacción táctil das opcións do NVDA. O xesto predeterminado é NVDA+control+alt+t. (#9682)
* Engadidas novas táboas braille para o Alemán. (#11268)
* O NVDA agora detecta controis de texto de só lectura de UIA. (#10494)
* A existentcia de contido marcado (resaltado) infórmase tanto en voz coma en braille en todos os navegadores web. (#11436)
 * Esto pode activarse e desactivarse cunha nova opción de Formateado de Documento do NVDA para Resaltado.
* Poden engadirse novas teclas ao sistema de teclado emulado dende o diálogo Xextos de Entrada do NVDA. (#6060)
  * Para facelo, pulsa o botón Engadir despois de que seleciones a categoría Teclas de sistema de teclado emulado.
* Agora admítese Handy Tech Active Braille con joystick. (#11655)
* A opción "Modo foco automático para movementos do cursor" agora é compatible con deshabilitar "Poñer automáticamente o foco en elementos enfocables". (#11663)

### Cambios

* O script anunciar formato (NVDA+f) agora cambiouse para anunciar o formato no cursor do sistema en lugar de na posición do cursor de revisión.  Para anunciar o formato na posición do Cursor de Revisión agora usa NVDA+shift+f. (#9505)
* NVDA xa non pon automáticamente o foco do sistema nos elementos enfocables por defecto en modo Exploración, mellorando o rendemento e a estabilidade. (#11190)
* Actualizado CLDR dende a versión 36.1 á versión 37. (#11303)
* Actualizado o eSpeak-NG a 1.51-dev, commit 1fb68ffffea4
* Agora podes usar a navegación de táboas en caixas de listaxe con elementos de listaxe marcables cando unha listaxe en particular teña varias columnas. (#8857)
* No Administrador de complementos, cando se che pregunte para confirmar o borrado dun complemento, agora  "Non", é a predeterminada. (#10015)
* En Microsoft Excel, o diálogo de listaxe de elementos agora presenta fórmulas na súa forma localizada. (#9144)
* O NVDA agora anuncia a terminoloxía correcta para notas en MS Excel. (#11311)
* Ao se usar a orde "mover cursor de revisión ao foco" en modo Exploración, o cursor de revisión agora ponse na posición do cursor virtual. (#9622)
* A información anunciada no modo exploración, como a información de formato con NVDA+F, amósase agora nunha xanela lixeiramente máis grande centrada na pantalla. (#9910)

### Arranxo de Erros

* O NVDA agora fala sempre ao navegar por palabras e aterriza en calquera símbolo seguido por un espazo en branco, calquera que sexan as opcións de verbosidade. (#5133)
* En aplicacións que usen QT 5.11 ou máis novas, as descripcións dos obxectos anúncianse de novo. (#8604)
* Ao borrar unha palabra con control+suprimir, o NVDA xa non permanece en silenzo. (#3298, #11029)
  * Agora anúnciase a palabra á dereita da eliminada.
* No panel Opcións Xerais, a listaxe de linguas agora ordéase correctamente. (#10348)
* No diálogo Xestos de Entrada, mellorouse significativamente o rendemento mentres se filtra. (#10307)(
* Agora podes enviar caracteres Unicode máis aló de U+FFFF dende unha pantalla braille. (#10796)
* O NVDA anunciará diálogo Aberto Con contido en Windows 10 May 2020 Update. (#11335)
* Unha opción nova experimental en Opcións Avanzadas (Habilitar o rexistro selectivo para eventos e cambios de propiedade de UI Automation) pode proporcionar maiores melloras de rendemento en Microsoft Visual Studio e outras aplicacións baseadas en UIAutomation se se habilita. (#11077, #11209)
* Para elementos de listaxe marcables, o estado selecionado xa non se anuncia redundantemente, e se é aplicable, anúnciase o estado deseleccionado no seu lugar. (#8554)
* En Windows 10 May 2020 Update, O NVDA agora amosa o Mapeador de Son de Microsoft ao revisar os dispositivos de saída dende o diálogo Sintetizador. (#11349)
* En Internet Explorer, os números agora anúncianse correctamente para listaxes ordeadas se a listaxe non comeza con 1. (#8438)
* En Google chrome, o NVDA agora anunciará non marcado para todos os controis marcables (non só caixas de verificación) que actualmente non estean marcados. (#11377)
* Unha vez máis é posible de novo navegar por varios controis cando a lingua de NVDA estea posta en Aragonés. (#11384)
* O NVDA xa non debería conxelarse ás veces en Microsoft Word ao mover rápidamente as frechas arriba e abaixo ou ao escreber caracteres co Braille habilitado. (#11431, #11425, #11414)
* O NVDA xa non engade un espazo non existente no arrastre ao copiar o navegador de obxectos actual ao portapapeis. (#11438)
* O NVDA xa non activa o perfil Ler todo se non hai nada que ler. (#10899, #9947)
* O NVDA xa non é incapaz de ler a listaxe de características en el administrador Internet Information Services (IIS). (#11468)
* O NVDA agora mantén o dispositivo de audio aberto mellorando o rendemento nalgunhas tarxetas de son (#5172, #10721)
* O NVDA xa non se conxelará nin se apagará cando manteñas premido control+shift+flecha abaixo en Microsoft Word. (#9463)
* O estado expandido/contraído dos directorios na árbore de navegación de drive.google.com agora sempre se anuncia polo NVDA. (#11520)
* O NVDA detectará automáticamente a pantalla braille NLS eReader Humanware a través do Bluetooth, xa que o seu nome Bluethooth é agora "NLS eReader Humanware". (#11561)
* Grandes melloras no rendemento de Visual Studio Code. (#11533)

### Cambios para Desenvolvedores

* O GUI Helper's BoxSizerHelper.addDialogDismissButtons soporta unha nova palabra cchave de argumento "separated", para engadir un separador horizontal estándar aos diálogos (que non sexan mensaxes e diálogos de entrada sinxelos). (#6468)
* Engadíronse propiedades adicionais aos app modules, incluindo a ruta para o executable (appPath), é unha app de almacenamento de Windows (isWindowsStoreApp), e arquitectura de máquina para a app (appArchitecture). (#7894)
* Agora é posible crear app modules para apps hospedadas dentro de wwahost.exe en Windows 8 e posteriores. (#4569)
* Agora pódese delimitar un fragmento do rexistro e logo copialo ao portapapeis usando NVDA+control+shift+F1. (#9280)
* Os obxectos específicos de NVDA que se atopan polo recolector de basura cíclica de Python agora rexístranse cando se borran polo recolector para axudar na eliminación dos ciclos de referencia de NVDA. (#11499)
 * A maioría das crases de NVDA rastréanse incluindo NVDAObjects, appModules, GlobalPlugins, SynthDrivers e TreeInterceptors.
 * Unha crase que se necesita rastrear debe herdar de garbageHandler.TrackedObject.
* O rexistro de depuración significativo para os eventos de MSAA agora pode habilitarse na configuración avanzada de NVDA. (#11521)
* Os eventos de MSAA para o obxecto enfocado actualmente xa non se filtran xunto con outros eventos se se excede a conta de eventos para un fío determinado. (#11520)

## 2020.2

O subliñable desta versión inclúe o soporte dunha nova pantalla braille de Nattiq, un soporte mellor para a interfaz gráfica de usuario do antivirus ESET e a Terminal de Windows, melloras de rendemento de 1Password e co sintetizador Windows OneCore. Ademáiss de moitas outras importantes melloras e correccións de fallos.

### Novas Características

* Admisión de novas pantallas braille:
  * Nattiq nBraille (#10778)
* Engadido un script para abrir o directorio de configuración do NVDA (sen xesto predeterminado). (#2214)
* Mellor soporte para a interface gráfica de usuario do antivirus ESET. (#10894)
* Engadido o soporte para a Terminal de Windows. (#10305)
* Engadida unha orde para anunciar o perfil de configuración activo (non hai xesto predeterminado). (#9325)
* Engadida unha orde para conmutar o anunciado de subíndices e superíndices (non hai xesto predeterminado). (#10985)
* As aplicacións web (Ex. Gmail) xa non falan información incorrecta cando se mova o foco rápidamente. (#10885)
  * Esta solución experimental debe activarse manualmente a través da opción 'tentar cancelar a voz para eventos de enfoque caducados'  no panel de opcións avanzadas.
* Engadíronse máis símbolos ao diccionario de símbolos predeterminado. (#11105)

### Cambios

* Actualizado o transcriptor braille liblouis de 3.12 a [3.14.0](https://github.com/liblouis/liblouis/releases/tag/v3.14.0) (from 3.12.0). (#10832, #11221)
* O anunciado de superíndices e subíndices agora contrólase por separado ao anunciado de atributos de fonte. (#10919)
* Debido a cambios feitos en VS Code, o NVDA xa non desactiva o modo Exploración en Code por defecto. (#10888)
* O NVDA xa non anuncia as mensaxes "superior" e "inferior" ao se mover o cursor de revisión directamente á primeira ou última liña do actual navegador de obxectos cos scripts mover cursor de revisión arriba ou abaixo respectivamente. (#9551)
* O NVDA xa non anuncia as mensaxes "esquerda" e "dereita" ao se mover o cursor de revisión directamente ao primeiro ou último carácter do actual navegador de obxectos cos scripts mover cursor de revisión á esquerda ou á dereita respectivamente. (#9551)

### Corección de Erros

* O NVDA agora arranca correctamente cando o ficheiro de rexistro non se poda crear. (#6330)
* En versións recentes de Microsoft Word 365, o NVDA xa non anunciará "borrar palabra atrás" cando se prema Control+Retroceso mentres se edita un documento. (#10851)
* En Winamp, o NVDA anunciará de novo o estado de conmutación de aleatorio ou de repetir. (#10945)
* O NVDA xa non é extremadamente lento ao te mover dentro da listaxe de elementos en 1Password. (#10508)
* O sintetizador de voz Windows OneCore xa non ten retraso entre as frases. (#10721)
* O NVDA xa non se conxela cando abres o menú  de contexto para 1Password na área de notificacións do sistema. (#11017)
* En Office 2013 e anteriores:
  * As cintas anúncianse cando o foco se mova cara elas por primeira vez. (#4207)
  * Os elementos do menú de contexto anúncianse de novo apropriadamente. (#9252)
  * As secións das cintas anúncianse consistentemente ao navegar con Control+frechas. (#7067)
* En modo Exploración en Mozilla Firefox e Google Chrome, o texto xa non aparece incorectamente nunha liña separada cando o contido web usa no CSS display: inline-flex. (#11075)
* En modo Exploración co foco automático do sistema configurado a elementos enfocables desactivado, agora é posible activar elementos que non sexan enfocables.
* En modo Exploración co foco automático do sistema configurado a elementos enfocables desactivado, agora é posible activar elementos alcanzables premendo a tecla tab. (#8528)
* En modo Exploración co foco automático do sistema configurado a elementos enfocables desactivado, activar certos elementos xa non fai clic nun lugar incorrecto. (#9886)
* Os sons de erro do NVDA xa non se escoitan cando se aceda a controis de texto de DevExpress. (#10918)
* Os consellos das iconass na bandexa do sistema xa non se anuncian ao navegar co teclado se o seu texto é igual ao seu nome, para evitar un anunciado duplicado. (#6656)
* En modo Exploración co foco automático do sistema configurado a elementos enfocables desactivado, cambiar a modo Foco con NVDA+espazo agora enfoca o elemento baixo o cursor. (#11206)
* De novo é posible procurar actualizacións do NVDA en certos sistemas; ex.: instalacións limpas de Windows. (#11253)
* O foco non se move nunha aplicación Java cando a seleción se cambie nunha árbore, táboa ou listaxe non enfocable. (#5989)

### Cambios para Desenroladores

* execElevated y hasUiAccess movéronse do módulo  config ao módulo systemUtils. O uso a través do módulo config é obsoleta. (#10493)
* Actualizado configobj a 5.1.0dev commit f9a265c4. (#10939)
* Agora é posible a comprobación automatizada do NVDA con Chrome e un exemplo HTML. (#10553)
* IAccessibleHandler convertééuse nun paquete, OrderedWinEventLimiter extraíuse a un módulo e engadíronse probas de unidade (#10934)
* Actualizado BrlApi á versión 0.8 (BRLTTY 6.1). (#11065)
* A recuperación da barra de estado agora pode seren persoalizada por un AppModule. (#2125, #4640)
* O NVDA xa non escoita ao IAccessible EVENT_OBJECT_REORDER. (#11076)
* Un ScriptableObject rompido (coma un GlobalPlugin que perda unha chamada á súa crase base ' método init ) xa non rompe o manexo dos scripts do NVDA. (#5446)

## 2020.1

O subliñable desta versión inclúe o soporte de varias novas pantallas braille de HumanWare e de APH, máis moitos outros arranxos importantes  de fallos como a capacidade de ler de novo matemáticas en Microsoft Word usando MathPlayer e MathType.

### Novas Características

* O elemento actualmente selecionado en caixas de listaxe preséntase de novo en modo exploración en Chrome, semellante a o NVDA 2019.1. (#10713)
* Agora podes realizar clics co botón dereito do rato en dispositivos táctiles facendo un tap cun dedo e manténdoo. (#3886)
* Soporte para pantallas braille novas: APH Chameleon 20, APH Mantis Q40, HumanWare BrailleOne, BrailleNote Touch v2, e NLS eReader. (#10830)

### Cambios

* o NVDA evitará que o sistema se bloquee ou se suspenda cando estea a ler todo. (#10643)
* Soporte para iframes fora de proceso en Mozilla Firefox. (#10707)
* Actualizado o transcriptor braille liblouis á versión 3.12. (#10161)

### Arranxo de Fallos

* Arranxado o non anunciado do símbolo menos Unicode (U+2212) (#10633)
* Ao se instalar complementos dende o administrador de complementos os nomes dos ficheiros e cartafols na xanela de exploración xa non se anuncian dúas veces. (#10620, #2395)
* En Firefox, ao se cargar Mastodon coa interface de web avanzada activada, agora todas as cronoloxías procésanse correctamente en modo exploración. (#10776)
* En modo exploración, o NVDA agora anuncia "non marcado" para caixas de verificación non marcadas onde non o facía en ocasións anteriormente. (#10781)
* Os controis ARIA switch xa non anuncian información confusa como "non premedo marcado" ou "premedo marcado". (#9187)
* As voces SAPI4 xa non deberían rexeitar falar certo texto. (#10792)
* O NVDA pode ler e interactuar de novo con ecuacións matemáticas en Microsoft Word. (#10803)
* O NVDA anunciará de novo o texto que se deselecione en modo exploración se se preme unha frecha mentres o texto se seleciona. (#10731).
* O NVDA xa non sae se hai un erro inicializando o eSpeak. (#10607)
* Os erros causados polo unicode en traduccións para atallos xa non deteñen o instalador, mitigados pola volta ao texto en inglés. (#5166, #6326)
* O feito de saír  das listaxes e táboas en Ler todo coa lectura superficial activada xa non anuncia continuamente a saída da listaxe ou táboa. (#10706)
* Arranxado o seguemento do rato para algúns elementos MSHTML en Internet Explorer. (#10736)

### Cambios para Desenvolvedores

* Agora compílase a documentación para o desenvolvedor usando sphinx. (#9840)
* Dividíronse en dous varias funcións da fala. (#10593)
  A versión speakX permanece, pero agora depende dunha función getXSpeech a que devolve unha secuencia de fala.
  * speakObjectProperties agora baséase en getObjectPropertiesSpeech
  * speakObject agora baséase en getObjectSpeech
  * speakTextInfo agora baséase en getTextInfoSpeech
  * speakWithoutPauses convertiuse nunha clase, e refactorizouse, pero non debería romper a retrocompatibilidade.
  * getSpeechForSpelling está obsoleta (aíndaque todavía dispoñible) usa getSpellingSpeech no seu lugar.
  Cambios privados que non deberían afectar aos desenvolvedores de complementos:
  * _speakPlaceholderIfEmpty agora é _getPlaceholderSpeechIfTextEmpty
  * _speakTextInfo_addMath agora é _extendSpeechSequence_addMathForTextInfo
* Speech 'reason' convertiuse a un Enum, Consulta a clase controlTypes.OutputReason. (#10703)
  * As constantes Module level 'REASON_*' están obsoletas.
* As dependencias de compilación do NVDA agora requiren Visual Studio 2019 (16.2 ou máis recente). (#10169)
* Actualizado SCons á versión 3.1.1. (#10169)
* Novamente permíteselle a behaviors._FakeTableCell non teren unha localización definida (#10864)

## 2019.3

O NVDA 2019.3 é unha versión moi importante que contén moitos cambios baixo o capó, incluíndo a actualización de Python 2 a Python 3, e unha importante reescritura do sistema da fala do NVDA.
Aíndaque estos cambios rompan a compatibilidade cos antigos complemenhtos do NVDA, a actualización a Python 3 é necesaria por motivos de seguridade, e os cambios na fala permiten algunhas innovacións interesantes nun futuro cercano.
 Outros aspectos destacados nesta versión inclúen o soporte para 64 bits para Java VMs, as funcionalidades Cortina de Pantalla e Resaltado do Foco, admisión de máis pantallas braille e un novo visor braille, e moitos outros arranxos de erros.

### Novas Características

* A precisión da orde mover o rato ao navegador de obxectos melloruose en campos de texto en aplicacións Java. (#10157)
* Engadido o soporte para as seguintes pantallas braille Handy Tech (#8955):
 * Basic Braille Plus 40
 * Basic Braille Plus 32
 * Connect Braille
* Todos os xestos definidos polo usuario poden agora borrarse mediante un novo botón "Restablecer os valores predeterminados de fábrica" na caixa de diálogo Xestos de entrada. (#10293)
* O anunciado de fonte en Microsoft Word agora inclúe se o texto se marca como agochado. (#8713)
* Engadida unha orde para mover o cursor de revisión á posición anteriormente axustada como marca de comezo de seleción ou copia: NVDA+shift+F9. (#1969)
* En Internet Explorer, Microsoft Edge e versións recentes de Firefox e Chrome, as rexións agora anúncianse en modo foco e no navegador de obxectos. (#10101)
* En Internet Explorer, Google Chrome e Mozilla Firefox, agora podes navegar por artigos e grupos usando os scripts de navegación rápida. Estos scripts non están vinculados por omisión e poden asignarse no diálogo Xestos de Entrada cando o diálogo se abra dende un documento en modo exploración. (#9227)
 * Agora anúncianse as figuras. Considéranse obxectos e, polo tanto, navegables coa tecla de navegación rápida o.
* En Internet Explorer, Google Chrome e Mozilla Firefox, agora anúncianse os elementos artigo co navegador de obxecto, e opcionalmente, en modo Exploración se se activou nas opcións de Formateado de Documentos. (#10424)
* Engadiuse unha Cortina de Pantalla que, ao se activar, fai que toda a pantalla se torne negra en Windows 8 e posteriores. (#7857)
 * Engadiuse un script para activar a cortina de pantalla (ate o seguinte reinicio cunha soa pulsación, ou sempre mentres o NVDA estea en execución con dúas pulsacións), non se asigna ningún xesto predeterminado.
 * Pode activarse e configurarse a través da categoría 'visión' no diálogo opcións do NVDA.
* Engadida a funcionalidade Resaltado de pantalla ao NVDA. (#971, #9064)
 * O resaltado do foco, do navegador de obxectos e da posición do cursor do modo Exploración poden activarse e configurarse a través da categoría 'visión' no diálogo Opcións do NVDA.
 * Nota: esta característica é incompatible co complemento focus highlight, sen embargo, o complemento aínda pode usarse mentres o resaltador incorporado estea desactivado.
* Engadida a ferramenta Visualizador de Braille, que permite ver a saída braille a través dunha xanela sobre a pantalla. (#7788)

### Cambios

* A Guía do Usuario agora describe cómo usar o NVDA na consola de Windows. (#9957)
* A execución do nvda.exe agora está predeterminada para reemplazar unha copia xa en execución do NVDA. O parámetro de liña de ordes -r|--replace aínda se acepta, pero ignórase. (#8320)
* En Windows 8 e posterior, o NVDA agora anunciará a información de nome do producto e da versión para aplicacións nativas como as aplicacións descargadas da Tenda de Microsoft usando información proporcionada pola aplicación. (#4259, #10108)
* Ao activar e desactivar os cambios de seguemento co teclado de Microsoft Word, o NVDA anunciará o estado da configuración. (#942)
* O número de versión do NVDA agora rexístrase como a primeira mensaxe no rexistro. Esto ocurre incluso se se desactivou o rexistro dende a Interfaz Gráfica de Usuario. (#9803)
* O diálogo de opcións xa non permite cambiar o nivel do rexistro configurado se se substituíu dende a liña de ordes. (#10209)
* En Microsoft Word, o NVDA agora anuncia o estado de visualización dos caracteres non imprimibles ao premer o atallo conmutable Ctrl+Shift+8. (#10241)
* Actualizado o transcriptor braille Liblouis a commit 58d67e63. (#10094)
* Cando o anunciado de caracteres CLDR (incluindo emojis) está activado, anúncianse nos niveis de toda a puntoación. (#8826)
* Os paquetes python de terceiros incluídos no NVDA como comtypes, agora rexistran as súas advertencias e erros no rexistro do NVDA. (#10393)
* Actualizado Unicode Common Locale Data Repository emoji annotations á versión 36.0. (#10426)
* Ao enfocar un grupo no modo Exploración, agora tamén se le a descripción. (#10095)
* Agora inclúese o Java Access Bridge co NVDA para permitir o acceso a aplicacións Java, incluso para máquinas Java de 64 bits. (#7724)
* Se o Java Access Bridge non está habilitado para o usuario, o NVDA actívao actomáticamente ao arrancar. (#7952)
* Actualizado eSpeak-NG á 1.51-dev, commit ca65812ac6019926f2fbd7f12c92d7edd3701e0c. (#10581)

### Arranxo de fallos

* Os Emoji e outros caracteres unicode de 32 bits agora ocupan menos espazo nas pantallas braille cando se amosan como valores hexadecimais. (#6695)
* En Windows 10, o NVDA anunciará os consellos das aplicacións universais se o NVDA se configurou para anunciar consellos no diálogo Presentación de Obxectos. (#8118)
* En Windows 10 versión 1607 e posterior, agora anúnciase o texto escrebido en Mintty. (#1348)
* En Windows 10 versión 1607 e posterior, a saída na consola de Windows que apareza preto do cursor xa non se deletrea. (#513)
* Os controis no diálogo compresor de Audacity agora anúncianse ao se navegar por el. (#10103)
* O NVDA xa non trata os espazos coma palabras en revisión de obxectos en editores baseados en Scintilla como Notepad++. (#8295)
* O NVDA evitará que o sistema entre no modo durminte ao se desprazar polo texto con xestos da pantalla braille. (#9175)
* En Windows 10, o braille agora seguerá ao editar contido de celdas en Microsoft Excel e noutros controis de texto UIA onde se quedaba atrás. (#9749)
* O NVDA voltará a anunciar as suxerencias na barra de dirección de Microsoft Edge. (#7554)
* O NVDA xa non se silencia cando se enfoque un control de cabeceira de pestana HTML en Internet Explorer. (#8898)
* En Microsoft Edge baseado en EdgeHTML, o NVDA xa non reproducirá o son de suxerencia de buxca ao maximizar a xanela. (#9110, #10002)
* As caixas combinadas de ARIA 1.1 agora admítense en Mozilla Firefox e en Google Chrome. (#9616)
* O NVDA xa non anunciará o contido das columnas visualmente agochado para os elementos de listaxe en controis SysListView32. (#8268)
* O diálogo Opcións xa non amosa "info" coma o nivel de rexistro actual cando se estea en modo seguro. (#10209)
* No menú Inicio de Windows 10 Anniversary Update e posterior, o NVDA anunciará detalles dos resultados da busca. (#10232)
* En modo Exploración, se ao mover o cursor ou ao usar a navegación rápida prodúcese un cambio no documento, o NVDA xa non fala contido incorrecto nalgúns casos. (#8831, #10343)
* Arranxáronse algúns nomes de viñetas en Microsoft Word. (#10399)
* En Windows 10 May 2019 Update e posteriores, o NVDA anunciará outra vez o primeiro emoji ou elemento do portapapeis selecionado cando se abra o panel de emojis e o historial do portapapeis respectivamente. (#9204)
* En Poedit, unha vez máis é posible ver algunhas traducións para as linguas de dereita a esquerda. (#9931)
* Na aplicación de configuración de Windows 10 April 2018 Update e posteriores, o NVDA xa non anunciará a información das barras de progreso dos medidores de volume que se atopan na páxina sistema/Son. (#10284)
* As expresións regulares inválidas nos diccionarios da fala xa non interrumpen compretamente a voz no NVDA. (#10334)
* Cando se len elementos con viñetas en Microsoft Word co UIA activado, a viñeta do seguinte elemento da listaxe xa non se anuncia de xeito inapropiado. (#9613)
* Resolvéronse algúns problemas raros de transcripción braille e erros con liblouis. (#9982)
* As aplicacións Java comezadas antes do NVDA agora son accesibles sen a necesidade de comezar a aplicación Java. (#10296)
* En Mozilla Firefox, cando o elemento enfocado se marca como actual (aria-current), este cambio xa non se fala varias veces. (#8960)
* O NVDA agora tratará certos caracteres de composición unicode como e-acute como un so carácter ao se mover polo texto. (#10550)
* Agora admítese Spring Tool Suite Versión 4. (#10001)
* Non se pronuncia o nome por duplicado cuando aria-labelledby relation target é un elemento interior. (#10552)
* En Windows 10 version 1607 e posterior, os caracteres escrebidos dende teclados Braille fálanse en máis situacións. (#10569)
* Ao se cambiar o dispositivo de saída de audio, os tons reproducidos polo NVDA agora reproduciranse polo dispositivo recentemente selecionado. (#2167)
* En Mozilla Firefox, mover o foco en modo Exploración é máis rápido. Esto fai que mover o cursor en modo Exploración sexa máis áxil en moitos casos. (#10584)

### Cambios para Desenvolvedores

* Actualizado Python a 3.7. (#7105)
* Actualizado pySerial á versión 3.4. (#8815)
* Actualizado wxPython a 4.0.3 para soportar Python 3.5+ (#9630)
* Actualizado six á versión 1.12.0 (#9630)
* Actualizado py2exe á versión 0.9.3.2 (en desenvolvemento, commit b372a8e from albertosottile/py2exe#13). (#9856)
* Actualizado UIAutomationCore.dll módulo comtypes á versión 10.0.18362. (#9829)
* O compretado con tab na consola de Python só suxire atributos que comecen cun guión baixo se o guión baixo se escrebe primeiro. (#9918)
* A ferramenta Flake8 integrouse con SCons para reflectir os requisitos do código para Pull Requests. (#5918)
* Como o NVDA xa non depende de pyWin32, módulos como win32api e win32con xa non están dispoñibles para os complementos. (#9639)
 * As chamadas a win32api poden reemprazarse con chamadas directas a funcións win32 dll a través de ctypes.
 * As constantes win32con deberían definirse nos teus ficheiros.
* O argumento "async" en nvwave.playWaveFile renomeouse a "asynchronous". (#8607)
* Os métodos speakText e speakCharacter en obxectos synthDriver xa non se admiten.
 * Esta funcionalidade manéxase con SynthDriver.speak.
* As clases SynthSetting en synthDriverHandler boráronse. Agora usa as clases driverHandler.DriverSetting en cambio.
* As clases SynthDriver xa non deberían expoñer índices a través da propiedade lastIndex.
 * En cambio, deberían notificar  a acción synthDriverHandler.synthIndexReached co índice, unha vez que todo o audio anterior finalizara de reproducirse antes dese índice.
* As clases SynthDriver agora deben notificar a acción synthDriverHandler.synthDoneSpeaking, unha vez todo o audio de unha chamada a SynthDriver.speak terminara de reproducirse.
* As clases SynthDriver deben admitir speech.PitchCommand no seu método speak, xa que os cambios no ton da fala do deletreo agora dependen desta funcionalidade.
* A función de fala getSpeechTextForProperties renomeouse a getPropertiesSpeech. (#10098)
* A función de braille getBrailleTextForProperties renomeouse a getPropertiesBraille. (#10469)
* Cambiáronse varias funcións da fala para devolver as secuencias de fala. (#10098)
 * getControlFieldSpeech
 * getFormatFieldSpeech
 * getSpeechTextForProperties chamada agora getPropertiesSpeech
 * getIndentationSpeech
 * getTableInfoSpeech
* Engadido un módulo textUtils para simplificar as diferencias de cadea entre as cadeas de Python 3 e as cadeas de Windows unicode. (#9545)
 * Consulta a documentación do módulo e o módulo textInfos.offsets para exemplos de implementacións.
* Agora borrouse funcionalidade obsoleta. (#9548)
 * AppModules eliminados:
  * Windows XP sound recorder.
  * Klango Player, que é un software abandoado.
 * configobj.validate wrapper eliminado.
  * Debería usarse o código novo configobj import validate en lugar de import validate
 * textInfos.Point e textInfos.Rect reemplazados por locationHelper.Point e locationHelper.RectLTRB respectivamente.
 * braille.BrailleHandler._get_tether e braille.BrailleHandler.set_tether elimináronse.
 * config.getConfigDirs borrouse.
 * config.ConfigManager.getConfigValidationParameter reemprazouse por getConfigValidation
 * A propiedade inputCore.InputGesture.logIdentifier eliminouse.
   * Usa _get_identifiers in inputCore.InputGesture en cambio.
 * synthDriverHandler.SynthDriver.speakText/speakCharacter, eliminouse.
 * Eliminadas varias clases synthDriverHandler.SynthSetting
   * Conservadas anteriormente para conpatibilidade con versións anteriores (#8214), agora considéranse obsoletas.
   * Os controladores que usen as clases SynthSetting deberían actualizarse para usar as clases DriverSetting.
 * Eliminouse algún código herdado, en particular:
  * Soporte para a listaxe de mensaxes de Outlook pre 2003.
  * Unha clase de superposición para o menú de Inicio clásico, que só se atopa en Windows Vista e anteriores.
  * Quitada a compatibilidade para Skype 7, xa que definitivamente non funciona máis.
* Un framework que permite aos desenvolvedores crear proveedores de melloras visuais; módulos que poden cambiar o contido da pantalla, opcionalmente baseados na entrada do NVDA acerca de localizacións dos obxectos. (#9064)
 * Os complementos poden abrupar os seus proprios proveedores nun cartafol visionEnhancementProviders.
 * Consulta os módulos vision e visionEnhancementProviders para a implementación do framework e exempros, respectivamente.
 * Os proporcionadores de melloras de visión están habilitados e configurados a través da categoría 'visión' no diálogo opcións de NVDA.
* As propiedades da clase Abstract agora sopórtanse en obxectos que herdan de baseObject.AutoPropertyObject (ex.:. NVDAObjects e TextInfos). (#10102)
* Introduciuse displayModel.UNIT_DISPLAYCHUNK coma unha constante de unidade textInfos específica para DisplayModelTextInfo. (#10165)
 * Esta nova constante permite andar sobre o texto nun DisplayModelTextInfo de xeito que semella máis a cómo se gardan os cachos de texto no modelo subxacente.
* displayModel.getCaretRect agora devolve unha instancia de locationHelper.RectLTRB. (#10233)
* As constantes UNIT_CONTROLFIELD e UNIT_FORMATFIELD movéronse dende virtualBuffers.VirtualBufferTextInfo ao paquete textInfos. (#10396)
* Para cada entrada no rexistro do NVDA, agora inclúese información sobre o fío orixinal. (#10259)
* Os obxectos UIA TextInfo agora poden moverse/expandirse pola páxina, histórico e unidades de texto formatField. (#10396)
* Os módulos externos (appModules e globalPlugins) agora é menos probable que podan romper a creación de NVDAObjects.
 * As excepcións causadas polos métodos "chooseNVDAObjectOverlayClasses" e "event_NVDAObject_init" agora son correctamente capturadas e rexistradas.
* O diccionario aria.htmlNodeNameToAriaLandmarkRoles renomeouse agora como aria.htmlNodeNameToAriaRoles. Tamén contén roles que non son rexións.
* scriptHandler.isCurrentScript eliminouse debido á falta de uso. Non hai reemprazo. (#8677)

## 2019.2.1

Esta é unha versión menor para arranxar varios bloqueos presentes en 2019.2. As correcións inclúen:

* Solucionáronse varios problemas en Gmail que se viron tanto en Firefox coma en Chrome ao se interactuar con determinados menús emerxentes como ao se crear filtros ou ao se cambiar certas opcións de Gmail. (#10175, #9402, #8924)
* En Windows 7, o NVDA xa non fai que o explorador de arquivos de Windows se bloquee cando se use o rato no menú Inicio. (#9435)
* O Explorador de Arquivos de Windows en Windows 7 xa non se bloquea ao acesar aos campos de edición dos metadatos. (#5337)
* O NVDA xa non se colga ao interactuar con imaxes cunha URI en base 64 en Mozilla Firefox ou en Google Chrome. (#10227)

## 2019.2

O subliñable desta versión inclúe a deteción automática de pantallas braille de Freedom Scientific, unha opción experimental no panel Avanzado para deter o modo exploración dende o movemento automático do foco (o que podería proporcionar melloras de rendemento), unha opción de alzado brusco para o sintetizador Windows OneCore para acadar velocidades moi rápidas, e moitas outras correcións de fallos.

### Novas Características

* O soporte de Miranda NG de NVDA funciona coas versións máis recentes do cliente. (#9053)
* Agora podes desactivar o modo Exploración de xeito predeterminado desactivando a nova opción "Activar o modo Exploración ao se cargar a páxina" na configuración do modo exploración do NVDA. (#8716)
 * Ten en conta que cando esta opción estea desactivada, aínda podes activar o modo exploración manualmente premendo NVDA+espazo.
* Agora podes filtrar símbolos na caixa de diálogo de pronunciación de signos de puntoación, de xeito semellante a como funciona o filtrado na listaxe de elementos e na caixa de diálogo de xestos de entrada. (#5761)
* Engadíuse unha orde para cambiar a resolución da unidade de texto do rato (cánto texto se falará ao se mover o rato), non se lle asignou un xesto predeterminado. (#9056)
* O sintetizador OneCore de Windows ten agora unha opción de aumento de velocidade, que permite unha fala significativamente máis rápida. (#7498)
* A opción Alzado Brusco é agora configurable dende o anel de axustes de sintetizador para sintetizadores de voz compatibles. (Actualmente eSpeak-NG e Windows OneCore). (#8934)
* Os perfís de configuración agora pódense activar manualmente con xestos. (#4209)
 * O xesto débese configurar na caixa de diálogo "Xestos de entrada".
* En Eclipse, engadiuse o soporte para o autocompletado no editor de código. (#5667)
 * Ademáis, a información Javadoc pode lerse dende o editor cando está presente usando NVDA+d.
* Engadiuse unha opción experimental ao panel de Configuración Avanzada que che permite deter o foco do sistema para que non siga ao cursor do modo exploración (Poñer automáticamente o foco do sistema nos elementos enfocables). (#2039) aíndaque pode non ser adoitado desactivalo en todos os sitios web, esto poderá arranxar:
 * Efecto banda elástica: o NVDA desfai esporádicamente a última pulsación de tecla do modo exploración saltando ao lugar anterior.
 * As caixas de edición quitan o foco do sistema cando se mova a través deles nalgúns sitios web.
 * As pulsacións de teclas do modo exploración son lentas de resposta.
* Para os controladores de pantalla braille que o admitan, agora pódense cambiar as opcións do controlador dende a categoría de opcións braille na caixa de diálogo de opcións do NVDA. (#7452)
* Agora as pantallas braille de Freedom Scientific admiten a deteción automática de pantallas braille. (#7727)
* Engadida unha orde para amosar o reemprazo do símbolo baixo o cursor de revisión. (#9286)
* Engadida unha opción experimental ao panel de Opcións avanzadas que che permite probar unha nova reescritura en curso do soporte do NVDA para a Consola de Windows usando a API Microsoft UI Automation. (#9614)
* Na Consola Python, o campo de entrada agora admite o pegado de varias liñas dende o portapapeis. (#9776)

### Cambios

* O volume do sintetizador aumenta e diminúe en 5 en lugar de en 10 cando se usa o anel de opcións. (#6754)
* Acrarado o texto no administrador de complementos cando se lanza o NVDA co indicador --disable-addons. (#9473)
* Actualizado Unicode Common Locale Data Repository anotacións emoji á versión 35.0. (#9445)
* En inglés, a tecla de atallo para o campo filtrar na listaxe de elementos no modo exploración cambiou a alt+y. (#8728)
* Cando unha pantalla braille autodetectada se conecte a través do Bluetooth, o NVDA seguerá procurando pantallas USB compatibles co mesmo controlador e cambiará a unha conexión USB se está dispoñible. (#8853)
* Actualizado eSpeak-NG a commit 67324cc.
* Actualizado o transcriptor braille liblouis á versión 3.10.0. (#9439, #9678)
* O NVDA agora anunciará a palabra 'selecionado' despois de anunciar o texto que un usuario acabe de selecionar. (#9028, #9909))
* En Microsoft Visual Studio Code, NVDA está en modo Foco por defecto. (#9828)

### corrección de Fallos

* O NVDA xa non se bloquea cando un directorio de complementos estea valdeiro. (#7686)
* As marcas LTR e RTL xa non se anuncian en Braille ou en voz por caracteres cando se accede á xanela de propiedades. (#8361)
* Cando se salte aos campos de formulario coa navegación rápida do modo Exploración, agora anúnciase todo o campo de formulario en lugar de só a primeira liña. (#9388)
* O NVDA xa non se silenciará despois de saír da aplicación Windows 10 Mail. (#9341)
* O NVDA xa non falla ao iniciarse cando os axustes rexionais dos usuarios se establezan nun lugar descoñecido para o NVDA, como por exemplo Inglés (Países Baixos). (#8726)
* Cando o modo Exploración estea activado en Microsoft Excel e se cambie a un navegador en modo foco ou viceversa, o estado do modo exploración agora notifícase apropriadamente. (#8846)
* O NVDA agora anuncia correctamente a liña no cursor do rato en Notepad++ e noutros editores baseados en Scintilla. (#5450)
* En Google Docs (e noutros editores baseados en web), o braille xa non amosa ás veces de forma incorrecta "lst end" antes do cursor na metade dun elemento da listaxe. (#9477)
* Na actualización de Windows 10 de mayo de 2019, o NVDA xa non fala moitas notificacións de volume se se cambia o volume con botóns de hardware cando o Explorador de arquivos teña o foco. (#9466)
* A carga do diálogo de pronunciación de signos de puntoación e símbolos é agora moito máis rápida cando se usen diccionarios de símbolos que conteñan máis de 1.000 entradas. (#8790)
* Nos controis de Scintilla coma Notepad++, o NVDA pode ler a liña correcta cando o axuste de liña estea activado. (#9424)
* En Microsoft Excel, a localización da celda anúnciase despois de que cambie debido aos xestos shift+intro ou shift+intro do teclado numérico. (#9499)
* Dende o Visual Studio 2017 en diante, na xanela do Explorador de obxectos, o elemento selecionado na árbore de obxectos ou na árbore de membros con categorías agora anúnciase correctamente. (#9311)
* Os complementos con nomes que só se diferencien nas maiúsculas xa non se tratan coma complementos separados. (#9334)
* No caso das voces de Windows OneCore, a velocidade establecida no NVDA xa non se ve afectada pola velocidade establecida na configuración de voz de Windows 10. (#7498)
* O rexistro pódese abrir agora con NVDA+F1 cando non hai información do desenvolvedor para o obxecto de navegador actual. (#8613)
* Tamén é posible usar as ordes de navegación de táboa do NVDA en Google Docs, en Firefox e en Chrome. (#9494)
* As teclas frontais agora funcionan correctamente nas pantallas braille de Freedom Scientific. (#8849)
* Ao se ler o primeiro carácter dun documento en Notepad++ 7.7 X64, o NVDA xa non se conxela durante un máximo de diez segundos. (#9609)
* HTCom agora pode usarse cunha pantalla braille Handy Tech en combinación co NVDA. (#9691)
* En Mozilla Firefox, as actualizacións para unha rexión activa xa non se anuncian se a rexión activa está nunha pestana de fondo. (#1318)
* O diálogo Procurar do modo exploración do NVDA xa non deixa de funcionar se o diálogo Acerca de... do NVDA está actualmente aberto de fondo. (#8566)

### Cambios para Desenvolvedores

* Agora podes configurar a propiedade "disableBrowseModeByDefault" nos módulos da aplicación para que deixe o modo exploración desactivado por defecto. (#8846)
* O estilo extendido de xanela dunha xanela agora exponse usando a propiedade `extendedWindowStyle` en obxectos xanela e os seus derivados. (#9136)
* Actualizado o paquete comtypes a 1.1.7. (#9440, #8522)
* Ao se usar a orde report module info, o orden da información cambiouse para presentar o módulo primeiro. (#7338)
* Engadido un exemplo para demostrar o uso de nvdaControllerClient.dll dende C#. (#9600)
* Engadida unha nova función isWin10 ao módulo winVersion que devolve se esta copia do NVDA se está a executar en (ao menos) a versión suministrada de Windows 10 (como a 1903). (#9761)
* A consola pytnon do NVDA agora contén módulos máis utis no seu namespace (como appModules, globalPlugins, config e textInfos). (#9789)
* O resultado da última orde executada na consola Python do NVDA agora é acesible dende a variable _ (line). (#9782)
 * Ten en conta que esto agocha a función de traducción gettext tamén chamada "_". Para acesar á función de traducción: del _

## 2019.1.1

Esta versión arranxa os seguintes fallos:

* O NVDA xa non fai que Excel 2007 se bloquee ou se negue a anunciar se unha celda ten unha fórmula. (#9431)
* Google Chrome xa non se bloquea ao interactuar con determinadas caixas de listaxe. (#9364)
* Solucionouse un problema que impedía copiar a configuración dun usuario no perfil de configuración do sistema. (#9448)
* En Microsoft Excel, o NVDA usa de novo a mensaxe localizada cando anuncia a a ubicación das celdas combinadas. (#9471)

## 2019.1

O subliñable desta versión inclúe a realización de melloras ao acesar a Microsoft word e a Excel, melloras de estabilidade e de seguridade como a admisión de complementos con información de compatibilidade de versión, e moitos outros arranxos de fallos.

Por favor ten en conta que a partires desta versión do NVDA, os módulos de aplicación, os Plugins globais, os controladores de pantallas braille e os controladores de sintetizador persoais xa non se cargarán automáticamente dende o teu directorio de configuración de usuario do NVDA.
No seu lugar, estos deberían instalarse coma parte dun complemento do NVDA. Para os que desenvolvan código para un complemento, o código para probas pódese poñer nun novo directorio scratchpad para desenvolvedores no directorio de configuración de usuarios do NVDA,  se a opción de desenvolvedor scratchpad está activada no novo panel Opcións Avanzadas do NVDA.
Estos cambios son necesarios para garantir unha mellor compatibilidade do código persoalizado, de xeito que o NVDA non se rompa cando este código se volte incompatible con versións máis novas.
Por favor, consulta a listaxe de cambios máis abaixo para obter máis detalles sobre esto e de cómo se versionan agora mellor os complementos.

### Novas Características

* Novas táboas braille: Afrikaans, braille computerizado árabe de 8 puntos, árabe grao 2, español grao 2. (#4435)
* Engadida unha opción ás opcións do rato do NVDA para facer que o NVDA manexe situacións nas que o rato estea controlado por outra aplicación. (#8452)
 * Esto permitirá ao NVDA rastrear o rato cando un sistema estea controlado remotamente utilizando o TeamViewer ou outros programas de control remoto.
* Engadido o parámetro de liña de ordes `--enable-start-on-logon` para permitir configurar se as instalacións silenciosas do NVDA configuran ao NVDA para arrancar na pantalla de inicio de Windows ou non. Especifica true para arrancar na pantalla de inicio ou false para non arrancar nela. Se o argumento --enable-start-on-logon non se especifica entón o NVDA iniciarase por defecto na pantalla de inicio, a non ser que xa estivera configurado para non facelo nunha instalación anterior. (#8574)
* É posible desactivar as funcións de rexistro do NVDA configurando o nivel do rexistro a "deshabilitado" dende o panel de Opcións Xerais. (#8516)
* Agora anúnciase a presenza de fórmulas nas follas de cálculo de LibreOffice e Apache OpenOffice. (#860)
* En Mozilla Firefox e Google Chrome, o modo exploración agora anuncia o elemento selecionado en caixas de listaxe e en árbores.
 * Esto funciona en Firefox 66 e posterior.
 * Esto non funciona para certas caixas de listaxe (controis HTML select) en Chrome.
* Soporte preliminar para aplicacións coma Mozilla Firefox en computadores con procesadores ARM64 (por ex.: Qualcom Snapdragon). (#9216)
* Engadiuse unha nova categoría de Opcións Avanzadas ao diálogo de opcións do NVDA, incluindo unha opción para probar o novo soporte do NVDA para Microsoft Word a través da API de Microsoft UI Automation. (#9200)
* Engadido o soporte para a vista gráfica no Administrador de Discos de Windows. (#1486)
* Engadido o soporte de Handy Tech Connect Braille e Basic Braille 84. (#9249)

### Cambios

* Actualizado o transcriptor braille liblouis á versión 3.8.0. (#9013)
* Os autores de complementos agora poden facer comprir cunha versión mínima requerida do NVDA para os seus complementos. O NVDA negarase a instalar ou cargar un complemento cunha versión mínima requerida do NVDA superior á versión actual do NVDA. (#6275)
* Os autores dos complementos agora poden especificar a última versión do NVDA coa que se probou o complemento. Se un complemento só se probou cunha versión do NVDA inferior á versión actual, o NVDA negarase a instalalo ou a cargalo. (#6275)
* Esta versión do NVDA permitirá a instalación e carga de complementos que aínda non conteñan información sobre a versión mínima e a última probada do NVDA, pero a actualización a futuras versións do NVDA (por exemplo, 2019.2) pode provocar que estos complementos máis vellos se desactiven automáticamente.
* A orde mover o rato ao navegador de obxectos agora está dispoñible tanto en Microsoft Word coma en controis UIA, especialmente en Microsoft Edge. (#7916, #8371)
* Mellorouse o anunciado de texto baixo o rato dentro do Microsoft Edge e outras aplicacións UIA. (#8370)
* Cando se inicia o NVDA co parámetro de liña de ordes `--portable-path`, a ruta proporcionada rechéase automáticamente cando se tenta crear unha copia portable do NVDA usando o menú NVDA. (#8623)
* Actualizada a ruta á táboa braille noruega para reflectir o estándar a partir do ano 2015. (#9170)
* Cando se navega por parágrafos (control+frechas) ou se navega por celdas de táboa (control+alt+frechas), a existenza de erros de ortografía xa non se anunciará, incluso se o NVDA está configurado para anuncialos automáticamente. Esto é porque os parágrafos e as celdas de táboa poden seren bastante longas, e calcular os erros de ortografía nalgunhas aplicacións pode ser moi custoso. (#9217)
* O NVDA xa non carga automáticamente appModules, globalPlugins e controladores braille e de sintetizador dende o directorio de configuración de usuario do NVDA. Este código debería ser empaquetado no seu lugar coma un complemento con información correcta de versión, asegurándose de que o código incompatible non sexa executado coas versións actuais do NVDA. (#9238)
 * Para os desenvolvedores que necesiten probar o código según se desenvolve,  habilítase o directorio developer scratchpad do NVDA na categoría Avanzado das opcións do NVDA, e colocar o código no directorio 'scratchpad' atopado no directorio de configuración do usuario cando esta opción estea habilitada.

### Arranxo de Fallos

* Cando se usa o sintetizador de voz OneCore en Windows 10 de Abril de 2018 e posteriores, xa non se insertan longos cachos de silencio entre as expresións orais. (#8985)
* Cando te movas por caracteres en controis de texto plano (coma Notepad) ou en modo exploración, os caracteres emoji de 32 bits que consistan en dous puntos de código UTF-16 (como ðŸ¤¦) agora leranse apropriadamente. (#8782)
* Mellorado o diálogo de confirmación de reinicio despois de cambiar a lingua da interfaz. O texto e as etiquetas dos botóns son agora máis concisos e menos confusos. (#6416)
* Se un sintetizador de voz de terceiros non se carga, o NVDA recurrirá a Windows OneCore en Windows 10, en lugar de a espeak. (#9025)
* Eliminada a entrada "Diálogo de benvida" no menú do NVDA nas pantallas seguras.
* Ao se tabular ou ao se utilizar a navegación rápida no modo de navegación, as lendas nos paneis de tabelas anúncianse agora de xeito máis coherente. (#709)
* O NVDA anunciará agora os cambios de seleción para determinados selectores de tempo como nas Alarmas e na aplicación Reloxo. (#5231)
* No Centro de actividades de Windows 10, o NVDA anunciará mensaxes de estado ao alternar entre accións rápidas coma o brilo e o enfoque. (#8954)
* No centro de actividades en Windows 10 actualización Outubro de 2018 e versións anteriores, o NVDA recoñecerá o control de brilo de acción rápida coma un botón en lugar de coma un botón conmutable. (#8845)
* O NVDA voltará a rastrexar o cursor e anunciará os caracteres borrados en Microsoft Excel e procurará os campos de edición. (#9042)
* Arranxado un fallo raro no modo de navegación en Firefox. (#9152)
* O NVDA xa non falla ao anunciar o enfoque dalgúns controis na cinta de Microsoft Office 2016 cando está contraída.
* O NVDA xa non falla ao anunciar o contacto suxerido ao introducir enderezos nas novas mensaxes de Outlook 2016. (#8502)
* As últimas teclas de enrutamento do cursor nas pantallas eurobraille de 80 celdas xa non dirixen o cursor a unha posición en ou xusto despois do comezo da pantalla braille. (#9160)
* Arranxada a navegación de táboas na vista en fío de Mozilla Thunderbird. (#8396)
* En Mozilla Firefox e Google Chrome, cambiar ao modo foco agora funciona correctamente para certas caixas de listaxe e árbores (onde a caixa de listaxe ou árbore non é en si mesmo enfocable pero os seus elementos si o son). (#3573, #9157)
* O modo Exploración está agora correctamente activado de xeito predeterminado cando se len mensaxes en Outlook 2016/365 se se usa a compatibilidade co soporte experimental de UI Automation do NVDA para documentos de Word. (#9188)
* Agora é menos probable que o NVDA se conxele de xeito que a única forma de escapar sexa pechar a sesión actual de Windows. (#6291)
* En Windows 10 actualización October 2018 e versións posteriores, ao abrir o historial do portapapeis da nube co portapapeis valdeiro, o NVDA anunciará o estado do portapapeis. (#9112)
* En Windows 10 actualización October 2018 e posteriores, ao procurar emojis no panel emoji, o NVDA anunciará o mellor resultado da búsqueda. (#9112)
* O NVDA xa non se conxela na xanela principal de Virtualbox 5.2 e superiores. (#9202)
* A resposta en Microsoft Word ao navegar por liñas, parágrafos ou celdas de táboa pode mellorarse significativamente nalgúns documentos. Lémbrase que para un mellor rendemento, establecerase a vista Borrador en Microsoft Word con alt+w,e despois de abrir un documento. (#9217)
* En Mozilla Firefox e Google Chrome, as alertas valdeiras xa non se notifican. (#5657)
* Melloras significativas no rendemento ao navegar polas celdas de Microsoft Excel, especialmente cando a folla de cálculo conteña comentarios e/ou listaxes despregables de validación. (#7348)
* Xa non debería ser necesario desactivar a edición na celda nas opcións de Microsoft Excel para acesar ao control de edición de celdas co NVDA en Excel 2016/365. (#8146).
* Arranxado un colgue en Firefox a veces visto ao navegar por rexións, se está en uso o complemento Enhanced Aria. (#8980)

### Cambios para Desenvolvedores

* O NVDA agora pode compilarse con todas as edicións de Microsoft Visual Studio 2017 (non só coa edición Community). (#8939)
* Agora podes incluir a saída do rexistro de liblouis no rexistro do NVDA configurando a bandeira booleana louis na sección debugLogging da configuración do NVDA. (#4554)
* Os autores de complementos agora poden proporcionar información sobre a compatibilidade das versións do NVDA nos manifests dos complementos. (#6275, #9055)
 * minimumNVDAVersion: a versión mínima requerida do NVDA para que un complemento funcione apropriadamente.
 * lastTestedNVDAVersion: a última versión do NVDA coa que foi probado un complemento.
* OffsetsTextInfo agora pode implementar o método _getBoundingRectFromOffset para permitir a recuperación de rectángulos delimitadores por caracteres en lugar de puntos. (#8572)
* Engadida unha propiedade boundingRect aos obxectos TextInfo para recuperar o rectángulo delimitador dun rango de texto. (#8371)
* As propiedades e métodos dentro das clases agora poden ser marcadas como abstractas no NVDA. Estas clases xerarán un erro se se instancian. (#8294, #8652, #8658)
* O NVDA pode rexistrar o tempo transcorrido dende que se introducíu o texto, o que axuda a medir a capacidade de resposta percibida. Esto pode activarse configurando a opción timeSinceInput como True na sección debugLog da configuración do NVDA. (#9167)

## 2018.4.1

Esta versión arranxa unha colgada ao arrancar se a lingua da interfaz de usuario do NVDA se configurou como Aragonés. (#9089)

## 2018.4

O máis subliñable desta versión inclúe as melloras no rendemento das últimas versións de Mozilla Firefox, o anunciado dos emojis con todos os sintetizadores, o anunciado das respostas e envíos en Outlook, a información da distancia do cursor ao borde dunha páxina de Microsoft Word e moitos arranxos de fallos.

### Novas Características

* Novas táboas braille: Chinés (China, Mandarín) grao 1 e grao 2. (#5553)
* Agora anúncianse os estados Respostado / Reenviado en elementos de correo na listaxe de mensaxes de Microsoft Outlook. (#6911)
* O NVDA agora pode ler descripcións para emoji así coma outros caracteres que son parte do repositorio Unicode Common Locale Data. (#6523)
* En Microsoft Word, a distancia do cursor dende as marxes superior e esquerda da páxina poden anunciarse  premendo NVDA+suprimir do teclado numérico. (#1939)
* En Google Sheets co modo braille habilitado, o NVDA xa non anuncia 'selecionado' en cada celda ao mover o foco entre elas. (#8879)
* Engadido o soporte para Foxit Reader e para Foxit Phantom PDF (#8944)
* Engadido o soporte para a utilidade de base de datos DBeaver. (#8905)

### Cambios

* "Anunciar globos de axuda" no diálogo Presentación de Obxectos renomeouse como "Anunciar notificacións" para incluir o anunciado de notificacións do sistema en Windows 8 e posteriores. (#5789)
* Nas opcións de teclado do NVDA, as caixas de verificación para activar ou desactivar as teclas modificadoras do NVDA agora amósanse nunha listaxe en lugar de en caixas de verificación separadas.
* O NVDA xa non presenta información redundante ao ler o reloxo da bandexa do sistema nalgunhas versións de Windows. (#4364)
* Actualizado o transcriptor braille liblouis á versión 3.7.0. (#8697)
* Actualizado eSpeak-NG a commit 919f3240cbb.

### Coreción de Erros

* En Outlook 2016/365, anúncianse a categoría e o estado da marca para as mensaxes. (#8603)
* Cando o NVDA se configure para idiomas coma Kirgyz, Mongol ou Macedonio, xa non amosa un diálogo nun aviso ao arrancar que a lingua non se admite polo sistema operativo. (#8064)
* Ao mover o rato ao navegador de obxectos agora será moito máis preciso mover o rato á posición dol modo exploración en Mozilla Firefox, Google Chrome e Acrobat Reader DC. (#6460)
* Mellorouse interactuar coas caixas combinadas na web en Firefox, Chrome e Internet Explorer. (#8664)
* Se se executa na versión xaponesa de Windows XP ou Vista, o NVDA agora amosa a alerta dos requisitos da versión do Sistema Operativo segundo se esperaba. (#8771)
* Auméntase o rendemento en Mozilla Firefox ao se navegar por páxinas longas con moitos cambios dinámicos. (#8678)
* O braille xa non amosa atributos de fonte se se deshabilitaron nas opcións Formateado de documento. (#7615)
* O NVDA xa non falla ao seguir ao foco no Explorador de Arquivos e outras aplicacións que usen UI Automation cando outra aplicación estea ocupada (coma o procesamento por lotes do audio). (#7345)
* Nos menús ARIA na web, a tecla Escape agora pasarase a través do menú e xa non desactivará o modo foco incondicionalmente. (#3215)
* Na nova interfaz do Gmail, ao se usar a navegación rápida dentro de mensaxes mentres se len, xa non se anuncia todo o corpo da mensaxe despois do elemento ao que rematas de navegar. (#8887)
* Despois de actualizar o NVDA, navegadores como Firefox e google Chrome xa non deberían romperse, e o modo exploración debería seguir reflectindo correctamente as actualizacións de calquera documento cargado actualmente. (#7641)
* O NVDA xa non informa de que se pode facer clic varias veces nunha fila ao navegar polo contido cliqueable en Modo Exploración. (#7430)
* Os xestos realizados en pantallas braille baum Vario 40 xa non fallarán ao se executar. (#8894)
* No Google Slides co Mozilla Firefox, o NVDA xa non anuncia o texto selecionado en cada control co foco. (#8964)

### Cambios para Desenvolvedores

* gui.nvdaControls agora contén dúas clases para crear listaxes accesibles con caixas de verificación. (#7325)
 * CustomCheckListBox é unha sub-clase accesible de wx.CheckListBox.
 * AutoWidthColumnCheckListCtrl engade caixas de verificación accesibles a un AutoWidthColumnListCtrl, o que está baseado en si mesmo en wx.ListCtrl.
* Se necesitas facer un wx widget accesible que non o é aínda, é posible facelo usando unha instancia de gui.accPropServer.IAccPropServer_impl. (#7491)
 * Consulta a implementación de gui.nvdaControls.ListCtrlAccPropServer para máis información.
* Actualizado configobj a 5.1.0dev commit 5b5de48a. (#4470)
* A acción config.post_configProfileSwitch agora toma o argumento opcional prevConf keyword, permitiendo aos manexadores tomar unha acción baseada en diferencias entre a configuración antes e despois do cambio de perfil. (#8758)

## 2018.3.2

Esta é unha versión menor para evitar unha colgada en Google Chrome ao navegar por chíos en [www.twitter.com](http://www.twitter.com). (#8777)

## 2018.3.1

Esta é unha versión menor para arranxar un erro crítico en NVDA que facía que as versións de 32 bits de Mozilla Firefox se colgaran. (#8759)

## 2018.3

O subliñable desta versión inclúe a deteción automática de moitas pantallas Braille, a admisión para algunhas características novas do Windows 10 incluíndo o panel de entrada de emojis do Windows 10, e moitos outros arranxos de fallos.

### Novas Características

* NVDA anunciará erros de gramática cando se expoñan apropriadamente polas páxinas web en Mozilla Firefox e Google Chrome. (#8280)
* O contido que se marca como sendo borrado ou insertado en páxinas web agora anúnciase en Google Chrome. (#8558)
* Engadida a compatibilidade para as rodas de desprazamento de BrailleNote QT e Apex BT cando se use BrailleNote coma unha pantalla braille co NVDA. (#6316)
* Engadidos scripts para anunciar o tempo transcorrido e o tempo total da pista actual en Foobar2000. (#6596)
* O símbolo da tecla Command do Mac (⌘) agora anúnciase ao se ler texto con calquera sintetizador. (#8366)
* Os roles persoalizados a través do atributo aria-roledescription attribute agora admítense en Firefox, Chrome e Internet Explorer.
* Novas táboas braille: braille sueco computerizado de 8 puntos, Curdo central, Esperanto, Húngaro, checo. (#8226, #8437)
* Engadiuse o soporte para a deteción automática de pantallas braille en segundo plano. (#1271)
 * Admítense actualmente as pantallas ALVA, Baum/HumanWare/APH/Orbit, Eurobraille, Handy Tech, Hims, SuperBraille e HumanWare BrailleNote e Brailliant BI/B.
 * Podes habilitar esta característica selecionando a opción automático dende a listaxe de pantallas braille no diálogo selecionar pantalla braille de NVDA.
 * Por favor consulta a documentación para detalles adicionais.
* Engadiuse o soporte para varias características de entrada modernas introducidas en versións recentes do Windows 10. Estas inclúen o panel de emoji (Fall Creators Update), dictado (Fall Creators Update), suxerencias de entrada do teclado hardware (April 2018 Update), e pegar no portapapeis na nube (October 2018 Update). (#7273)
* O contido marcado coma un bloque de cita utilizando ARIA (role blockquote) agora admítese en Mozilla Firefox 63. (#8577)

### Cambios

* A listaxe de linguas dispoñibles no diálogo opcións Xerais agora ordéase baseándose nos nomes das linguas en lugar de nos códigos ISO 639. (#7284)
* Engadidos xestos predeterminados para alt shift tab e windows tab con todas as pantallas braille compatibles de Freedom Scientific. (#7387)
* Para a ALVA BC680 e pantallas con conversor de protocolo, agora é posible assignar funcións diferentes aos smart pad esquerdo e dereito, ao thumb e ás teclas etouch. (#8230)
* Para as pantallas ALVA BC6, a combinación de teclas sp2+sp3 agora anunciará a hora e a data actuais, mentres que sp1+sp2 emula a tecla Windows. (#8230)
* Agora pregúntaselle ao usuario unha vez no arranque do NVDA se está de acordo enviando estadísticas de uso a NV Access cando se procuren actualizacións automáticamente. (#8217)
* Ao se procurar actualizacións, se o usuario está de acordo ao permitir o envío de estadísticas de uso a NV Access, o NVDA agora enviará o nome do controlador do sintetizador actual e da pantalla braille en uso, para axudar a establecer unha mellor orde de prioridades para o traballo futuro destes controladores. (#8217)
* Actualizado o transcriptor braille liblouis á versión 3.6.0. (#8365)
* Actualizada a ruta á táboa braille rusa de 8 puntos correcta. (#8446)
* Actualizado eSpeak-ng a 1.49.3dev commit 910f4c2 (#8561)

### Arranxo de Erros

* As etiquetas accesibles para controis en Google Chrome agora anúncianse máis lexiblemente en modo exploración cando a etiqueta non aparece como contido en si. (#4773)
* Agora sopórtanse as notificacións en Zoom. Por exempro, esto inclúe silenciar/desilenciar estado, e as mensaxes entrantes. (#7754)
* Cambiar a presentación do contexto braille cando se estea en modo exploración xa non causa que a saída braille deixe de seguir. (#7741)
* As pantallas braille ALVA BC680 xa non fallan intermitentemente ao se inicializar. (#8106)
* Por defecto, as pantallas ALVA BC6 xa non executarán teclas emuladas do sistema ao se premer combinacións de teclas que teñan que ver con sp2+sp3 para disparar funcionalidades internas. (#8230)
* Ao se premer sp2 nunha pantalla ALVA BC6 para emular a tecla alt agora funciona tal coma se anuncia. (#8360)
* O NVDA xa non anuncia cambios redundantes da distribución de teclado. (#7383, #8419)
* O seguemento do rato agora é moito máis preciso no Bloc de notas e noutros controis de edición de texto sen formato cando se atopen nun documento con máis de 65535 caracteres. (#8397)
* O NVDA recoñecerá máis diálogos en Windows 10 e outras aplicacións modernas. (#8405)
* Na actualización de ouctubro do 2018 de Windows 10 e de Server 2019 e posterior, O NVDA xa non falla ao seguir ao foco do sistema cando unha aplicación se conxela ou inunda ao sistema con eventos. (#7345, #8535)
* Agora infórmase aos usuarios cando tenten ler ou copiar unha barra de estado valdeira. (#7789)
* Arranxado un caso onde o estado "non marcado" en controis non se anuncia en voz se o control foi parcialmente marcado anteriormente. (#6946)
* Na listaxe de linguas nas opcións xerais do NVDA, o nome para a lingua birmana amósase correctamente en Windows 7. (#8544)
* En Microsoft Edge, o NVDA anunciará notificacións coma ler a dispoñibilidade da vista e o progreso da carga da páxina. (#8423)
* Ao navegar por unha listaxe na web, o NVDA agora anunciará a súa etiqueta se o autor da mesma proporcionou unha. (#7652)
* Cando se asignan manualmente funcións a xestos para unha pantalla braille en particular, estos xestos agora sempre aparecen como asignados a esa pantalla. Anteriormente, amosábanse coma se estiveran asignados á pantalla activa nese intre. (#8108)
* Agora admítese a versión de 64 bits do Media Player Classic. (#6066)
* Varias melloras ao soporte braille en Microsoft Word co UI Automation habilitado:
 * De xeito similar a outros campos de texto multiliña, cando se coloque ao comezo dun documento en Braille, a pantalla agora desprázase de tal xeito que o primeiro carácter do documento se atope ao comezo da pantalla. (#8406)
 * Redución da presentación demasiado verbosa do foco tanto en voz coma en braille cando se enfoque un documento Word. (#8407)
 * O enrutamento do cursor en braille agora funciona correctamente cando se está nunha listaxe nun documento de Word. (#7971)
 * As viñetas/números recén insertados nun documento Word anúncianse correctamente tanto en voz coma en braille. (#7970)
* En Windows 10 1803 e posteriores, agora é posible instalar complementos se está activada a característica "Usar Unicode UTF-8 para o soporte de linguas en todo o mundo". (#8599)
* O NVDA xa nno fará compretamente inusable a iTunes 12.9 e posteriores para interactuar. (#8744)

### Cambios para Desenvolvedores

* Engadido scriptHandler.script, o que pode funcionar coma un decorador para scripts en obxectos escriptables. (#6266)
* Introduciuse un framework de sistema de probas para o NVDA. (#708)
* Realizáronse algúns cambios no módulo hwPortUtils: (#1271)
 * listUsbDevices agora xenera diccionarios con información de dispositivo incluíndo hardwareID e devicePath.
 * Os diccionarios xerados por listComPorts agora tamén conteñen unha entrada usbID para portos COM con información USB VID/PID no seu ID de hardware.
* Actualizado wxPython a 4.0.3. (#7077)
* Dado que o NVDA agora só é compatible co Windows 7 SP1 e posterior, borrouse a clave "minWindowsVersion" usada para comprobar se UIA debería habilitarse para unha versión en particular de Windows. (#8422)
* Agora podes rexistrar para que se che notifique acerca de acións de gardar/reiniciar a configuración a través das novas acións config.pre_configSave, config.post_configSave, config.pre_configReset, e config.post_configReset. (#7598)
 * config.pre_configSave úsasse para que se che notifique cando a configuración do NVDA está a piques de gardarse, e config.post_configSave chámase despois de que a configuración se gardara.
 * config.pre_configReset e config.post_configReset inclúe un indicador de valores predeterminados  de fábrica para especificar se as opcións se recargan dende o disco (false) ou se reestablecen aos valores predeterminados (true).
* config.configProfileSwitch renomeouse a config.post_configProfileSwitch para refrectir o feito de que esta acción se chama despois de que o cambio de perfil teña lugar. (#7598)
* Interfaces de UI Automation actualizadas a Windows 10 October 2018 Update e Server 2019 (IUIAutomation6 / IUIAutomationElement9). (#8473)

## 2018.2.1

Esta versión inclúe actualizacións de traduccións debido ao borrado de última hora dunha característica que causou problemas.

## 2018.2

O subliñable desta versión inclúe o soporte para táboas en Kindle para PC, o soporte para pantallas Humanware BrailleNote Touch e BI14 Braille, melloras para sintetizadores de voz Onecore e Sapi5, melloras en Microsoft Outlook e moito máis.

### Novas Características

* Agora anúnciase o rango de filas e columnas para celdas de táboas  en voz e braille. (#2642)
* Agora sopórtanse as ordes de navegación de táboas de NVDA en Google Docs (co modo Braille habilitado). (#7946)
* Capacidade para ler e navegar táboas en Kindle for PC. (#7977)
* Soporte para as pantallas BrailleNote touch y Brailliant BI 14 a través tanto do USB coma do bluetooth. (#6524)
* No Windows 10 Fall Creators Update e posteriores, o NVDA pode anunciar notificacións dende aplicacións como a Calculadora e a Windows Store. (#8045)
* Novas táboas de transcripcción braille: Lithuano 8 puntos, ucranio, Mongol grado 2. (#7839)
* Engadido un script para anunciar información de formato para o texto baixo unha celda braille específica. (#7106)
* Novas linguas: Mongol, Alemán de Suiza.
* Ao se actualizar o NVDA, agora é posible retrasar a instalación da actualización a un momento posterior da túa elección. (#4263)
* Agora podes conmutar control, shift, alt, windows e NVDA dende o teu teclado braille e combinar estos modificadores coa entrada braille (ex.: premer control+s). (#7306)
 * Podes asignar estas novas conmutacións de modificadores usando a orde que se atopa en Teclas de sistema emuladas no diálogo Xestos de Entrada.
* Restaurado o soporte para pantallas Handy Tech Braillino e Modular (co firmware vello). (#8016)
* Agora sincronizaranse automáticamente co NVDA a data e a hora para os dispositivos Handy Tech soportados (como Active Braille e Active Star) cando estean desincronizados máis de cinco segundos. (#8016)
* Pódese asignar un xesto de entrada para desactivar temporalmente todos os disparadores dun perfil de configuración. (#4935)

### Cambios

* Cambiouse a columna de estado no administrador de complementos para indicar se o complemento está habilitado ou deshabilitado ademais de en execución ou suspendido. (#7929)
* Actualizado o transcriptor braille liblouis a 3.5.0. (#7839)
* A táboa braille lituana renomeouse a Lituano 6 puntos para evitar confusións coa nova táboa de 8 puntos. (#7839)
* As táboas Francés (Canadá) grao 1 e grao 2 borráronse. No seu lugar, utilizaranse as táboas Francés (unificado) 6 puntos e Grao 2 respectivamente. (#7839)
* Os sensores secundarios das pantallas braille Alva BC6, EuroBraille e Papenmeier agora anuncian información de formato para o texto baixo a celda braille dese sensor. (#7106)
* As táboas de entrada de braille contraído voltarán automáticamente a modo non contraído nos casos non editables (é dicir, controis onde non hai cursor ou en modo exploración). (#7306)
* O NVDA agora fala menos no calendario de Outlook cando unha cita ou unha franxa temporal cubre un día enteiro. (#7949)
* Agora pódense atopar todas as preferencias do NVDA nun único diálogo de opcións no menú NVDA -> Preferencias -> Opcións, en lugar de dispersarse en moitos diálogos. (#7302)
* O sintetizador de voz predeterminado ao se executar en Windows 10 agora é oneCore speech en lugar do eSpeak. (#8176)

### Correción de fallos

* O NVDA xa non falla ao ler controis enfocados na pantalla de inicio de sesión da conta de Microsoft en Configuración despois de introducir un enderezo de correo. (#7997)
* O NVDA xa non falla ao ler a páxina cando se retrocede a unha páxina anterior en Microsoft Edge. (#7997)
* O NVDA xa non anunciará incorrectamente o carácter final dun PIN de inicio de sesión de windows 10 segundo a máquina se desbloquee. (#7908)
* As etiquetas das caixas de verificación e dos botóns de opción en Chrome e Firefox xa non se anuncian dúas veces cando se tabule ou se use a navegación rápida en modo exploración. (#7960)
* Manéxase aria-current cun valor de false como false en lugares de true (#7892).
* O controlador do sintetizador Windows Onecore Voices xa non falla ao se cargar se a voz configurada se desinstalou. (#7999)
* Cambiar voces no controlador do sintetizador Windows Onecore Voices agora é moito máis rápido. (#7999)
* Arranxada a malformación da saída braille para varias táboas braille, incluindo signos en maiúsculas no braille danés contraído de 8 puntos. (#7526, #7693)
* O NVDA agora pode anunciar máis tipos de viñetas no Microsoft Word. (#6778)
* Ao se premer o script anunciar información xa non move incorrectamente a posición de revisión e polo tanto ao premelo varias veces xa non da resultados diferentes. (#7869)
* A entrada braille xa non che permitirá usar braille contraído nos casos onde non estea soportado (é dicir, xa non se enviarán palabras enteiras ao sistema fora do contido de texto e en modo exploración). (#7306)
* Arranxados problemas de estabilidade da conexión para as pantallas braille Handy Tech Easy Braille e Braille Wave. (#8016)
* En Windows 8 e posterior, o NVDA xa non anunciará "descoñecido" ao abrir o menú rápido de enlaces (Windows+X) e ao selecionar elementos deste menú. (#8137)
* Os xestos específicos do modelo para botóns nas pantallas Hims agora funcionan como se anuncia na Guía do Usuario. (#8096)
* O NVDA tentará agora arranxar os problemas de rexistro COM do sistema que causan que programas coma Firefox e Internet Explorer se volten inaccesibles e anuncien "Descoñecido" polo NVDA. (#2807).
* Traballouse na solución dun fallo no administrador de tarefas facendo que o NVDA non permita aos usuarios acesar aos contidos de detalles específicos sobre os procesos. (#8147)
* As voces máis novas do Microsoft SAPI5 xa non retrasan ao rematar a fala, o que fai que sexa moito máis doado navegar con estas voces. (#8174)
* O NVDA xa non anuncia (marcas LTR e  RTL) en Braille ou na fala por caracteres ao acceder ao reloxo en versións recentes do Windows. (#5729)
* A detección das teclas de desprazamento en pantallas Hims Smart Beetle xa non é pouco fiable. (#6086)
* Nalgúns controis de texto, particularmente en aplicacións Delphi, a información proporcionada na edición e na navegación agora é moito máis fiable. (#636, #8102)
* En Windows 10 RS5, NVDA xa non anuncia información extra redundante ao cambiar tarefas co alt+tab. (#8258)

### Cambios para Desenvolvedores

* A información para desenvolvedores para obxectos UIA agora contén unha listaxe dos patróns UIA dispoñibles. (#5712)
* Os módulos de aplicación agora poden forzar certas xanelas para usar sempre UIA implementando o método isGoodUIAWindow. (#7961)
* A bandeira booleana oculta "outputPass1Only" na seción braille da configuración borrouse de novo. Liblouis xa non soporta pasar 1 só na saída. (#7839)

## 2018.1.1

Esta é unha versión especial do NVDA que soluciona un problema no controlador do sintetizador Onecore Windows Speech, que facía que falara cun ton e velocidade máis altos en Windows 10 Redstone 4 (1803). (#8082)

## 2018.1

O subliñable desta versión inclúe o soporte para gráficos en Microsoft word e PowerPoint, o soporte para pantallas braille novas incluíndo as Eurobraille e o conversor de protocolo de Optelec, mellorado o soporte para as pantallas braille Hims e Optelec, melloras de rendemento para Mozilla Firefox 58 e posteriores, e moitho máis.

### Novas Características

* Agora é posible interactuar con gráficos en Microsoft Word e Microsoft PowerPoint, similar ao soporte existente para gráficos en Microsoft Excel. (#7046)
 * En Microsoft Word: cando se estea en modo exploración, pon o cursor nun gráfico integrado e preme intro para interactuar con el.
 * En Microsoft Powerpoint cando se edite unha diapositiva: tabula a un obxecto gráfico, e preme intro ou espazo para interactuar co gráfico.
 * Para deter a interación cun gráfico, preme escape.
* Nova lingua: Kyrgyz.
* Engadido o soporte para VitalSource Bookshelf. (#7155)
* Engadido o soporte para o protocolo conversor Optelec , un dispositivo que che permite usar as pantallas Braille Voyager e Satellite usando o protocolo de comunicación das ALVA BC6. (#6731)
* Agora é posible usar a entrada braille cunha pantalla braille ALVA 640 Comfort. (#7733)
 * A funcionalidade de entrada braille do NVDA pode usarse tanto con éstas coma con outras pantallas BC6 co firmware 3.0.0 e anterior.
* Soporte inicial para Google Sheets co modo Braille habilitado. (#7935)
* Soporte para pantallas braille Eurobraille Esys, Esytime e Iris. (#7488)

### Cambios

* reemplazáronse os controladores de pantallas braille HIMS Braille Sense/Braille EDGE/Smart Beetle e Hims Sync por un único controlador. O novo controlador activarase automáticamente para os antigos usuarios do controlador syncBraille. (#7459)
 * Algunhas teclas, especialmente as teclas de desprazamento, reasignáronse para seguir as convencións usadas polos productos de Hims. Consulta a guía do usuario para máis detalles.
* Ao se escrebir co teclado en pantalla a través da interación tactil, por defecto agora debes facer dobre tap en cada tecla do mesmo xeito no que activarías calquera outro control. (#7309)
 * Para usar o modo de "escritura tactil" existente onde chega con quitar o dedo da tecla para activala, habilita esta opción no novo diálogo Opcións de Interación Tactil que se atopa no menú Preferencias. (#7309)
* Xa non é necesario que o braille sega explícitamente ao foco ou á revisión, xa que esto ocorrirá automáticamente por omisión. (#2385)
 * Ten en conta que o seguemento automático á revisión só ocorirá ao se usar un cursor de revisión ou orden de navegación de obxectos. O desprazamento non activará este novo comportamento.

### Corrección de Fallos

* As mensaxes explorables como amosar o formato actual ao se premer NVDA+f dúas veces rápidamente, xa non fallan cando o NVDA se instala nunha ruta con caracteres non ASCII. (#7474)
* O foco agora restáurase unha vez máis correctamente cando se volta ao Spotify dende outra aplicación. (#7689)
* na actualización Windows 10 Fall Creators, NVDA xa non falla ao se actualizar cando o acceso controlado ao cartafol está habilitado dende Windows Defender Security Center. (#7696)
* A deteción das teclas de desprazamento nas pantallas Hims Smart Beetle xa non é pouco fiable. (#6086)
* Unha lixeira mellora no rendemento ao se procesar grandes cantidades de contido en Mozilla Firefox 58 e posterior. (#7719)
* En Microsoft Outlook, ler correos electrónicos que conteñan táboas xa non causa erros. (#6827)
* Os xestos das pantallas braille que emulan as teclas modificadoras do teclado do sistema agora poden combinarse tamén con outras teclas emuladas do teclado do sistema se uno ou máis dos xestos involucrados son específicos do modelo. (#7783)
* En Mozilla Firefox, o modo exploración agora funciona correctamente en xanelas emerxentes creadas por extensións como LastPass e bitwarden. (#7809)
* O NVDA xa non se bloquea ás veces en cada cambio do foco se o Firefox ou o Chrome deixaron de responder debido a unha conxelación ou un colgue. (#7818)
* En clientes de twitter como Chicken Nugget, o NVDA xa non ignorará os derradeiros 20 caracteres de tuits con 280 caracteres ao lelos. (#7828)
* O NVDA agora usa a lingua correcta ao anunciar os símbolos cando se selecione texto. (#7687)
* En versións recentes de Office 365, é de novo posible navegar gráficos de Excel usando as teclas de frechas. (#7046)
* En saídas de voz e braille, os estados dos controis agora sempre se anuncian no mesmo orden, sen importar se son positivos ou negativos. Arranxos #7076
* En aplicacións coma o Mail do Windows 10, NVDA xa non fallará ao anunciar os caracteres borrados cando se prema retroceso. (#7456)
* Agora todas as teclas nas pantallas Hims Braille Sense Polaris funcionan como se espera. (#7865)
* O NVDA xa non falla ao arrancar en Windows 7 queixándose acerca dunha dll api ms interna, cando unha versión particular do Visual Studio 2017 redistributable se instalara por outra aplicación. (#7975)

### Cambios para Desenvolvedores

* Engadida unha bandeira booleana oculta á seción braille na configuración: "outputPass1Only". (#7301, #7693, #7702)
 * Esta bandeira está predeterminada a true. Se é false, usaranse as regras liblouis multi pass para a saída braille.
* Engadiuse un novo diccionario (braille.RENAMED_DRIVERS) para permitir unha transición sen  problemas aos usuarios que utilizan controladores que foran substituidos por outros. (#7459)
* Actualizado o paquete comtypes a 1.1.3. (#7831)
* Implementado un sistema xenérico en braille.BrailleDisplayDriver para tratar coas pantallas que envían paquetes de confirmación/acuse de recibo. Consulta o controlador das pantallas braille handyTech como un exemplo. (#7590, #7721)
* Pódese usar unha nova variable "isAppX" no módulo config para detectar se o NVDA se está a executar coma unha aplicación Windows Desktop Bridge Store. (#7851)
* Para implementacións de documento coma NVDAObjects ou browseMode que teñan un textInfo, agora hai unha nova clase documentBase.documentWithTableNavigation que pode herdarse para obter scripts de navegación estándar de táboa. Por favor consulta esta clase para ver que métodos helper deben proporcionarse para a túa implementación para que funcione a navegación de táboa. (#7849)
* O ficheiro por lotes scons agora manéxase mellor cando Python 3 tamén está instalado, facendo o uso do lanzador para lanzar específicamente a python 2.7 de 32 bit. (#7541)
* hwIo.Hid agora toma un parámetro adicional exclusivo, o que por omisión é True. Se se configura a False, permítese a outras aplicacións comunicarse cun dispositivo mentres estea conectado ao NVDA. (#7859)

## 2017.4

O subliñable desta versión inclúe moitas correcións e melloras para o soporte web incluindo o modo exploración para diálogos web por defecto, mellor anunciado das etiquetas dos grupos de campos no modo exploración, o soporte para tecnoloxías novas de Windows 10 como a aplicación Windows Defender Guard e Windows 10 en ARM64, e o anunciado automático da orientación da pantalla e o estado da batería.
Por favor ten en conta que esta versión do NVDA xa non soporta o Windows XP ou o Windows Vista. Os requisitos mínimos para o NVDA agora son windows 7 co Service Pack 1.

### Novas Características

* No modo exploración, agora é posible saltar ao comezo das rexións usando as ordes saltar ao final ou ao comezo do contedor (coma/shift+coma). (#5482)
* En Firefox, Chrome e Internet Explorer, a navegación rápida por campos de edición e campos de formulario agora inclúe contido de texto enriquecido editable (ex.: contentEditable). (#5534)
* En navegadores web, a Lista de Elementos agora pode listar campos de formulario e botóns. (#588)
* Soporte inicial para o Windows 10 en ARM64. (#7508)
* Soporte preliminar para a lectura e a navegación interactiva de contido matemático para libros Kindle coas matemáticas acessibles. (#7536)
* Engadido o soporte para o lector de libros dixitais Azardi. (#5848)
* A información de versión para complementos agora anúnciase cando se estean actualizando. (#5324)
* Engadido o soporte para novos parámetros de liña de ordes para crear unha copia portable do NVDA. (#6329)
* Soporte para o Microsoft Edge executándose dentro do Windows Defender Application Guard (#7600)
* Se se executa nun portátil ou nunha tablet, o NVDA agora anunciará cando se conecte/desconecte un cargador e cando a orientación da pantalla cambie. (#4574, #4612)
* Lingua nova: Macedonio.
* Novas táboas de transcripción braille: Croata grao 1, Vietnamita grao 1. (#7518, #7565)
* Engadiuse o soporte para a pantalla braille Actilino de Handy Tech. (#7590)
* Agora sopórtase a entrada braille para as pantallas braille Handy Tech. (#7590)

### Cambios

* O menor Sistema Operativo soportado polo NVDA agora é o Windows 7 co Service Pack 1, ou o Windows Server 2008 R2 co Service Pack 1. (#7546)
* Os diálogos web nos navegadores Firefox e Chrome agora usan o modo exploración automáticamente, a non ser que se estea nunha aplicación web. (#4493)
* No modo exploración, ao se tabular ou se mover coas ordes de teclas de navegación rápida xa non anuncia saíndo de contedores coma listas e táboas, o que fai a navegación máis eficaz. (#2591)
* En modo exploración para Firefox e Chrome, agora anúncianse os nomes de grupos de campos de formulario ao se mover dentro deles coa navegación rápida ou cando se tabula. (#3321)
* No modo exploración, as ordes de navegación rápida para obxectos integrados (o e shift+o) agora inclúen elementos de audio e vídeo así coma elementos cos roles aria application e dialog. (#7239)
* Actualizouse o Espeak-ng 1.49.2),, esto resolve algúns problemas coa produción de versións. (#7385)
* Na terceira activación da orde 'ler bara de estado', o seu contido cópiase ao portapapeis. (#1785)
* Ao se asignar xestos a teclas nunha pantalla Baum, podes limitalas ao modelo da pantalla braille en uso (ex.: VarioUltra ou Pronto). (#7517)
* A tecla rápida para o campo filtrar na listaxe de elementos en modo exploración cambiouse de alt+f a alt+e. (#7569)
* Engadiuse unha orde para desvincular ao modo exploración para conmutar a inclusión de táboas de deseño ao vó. Podes atopar esta orde na categoría Modo exploración do diálogo Xestos de entrada. (#7634)
* Actualizado o transcriptor braille a 3.3.0. (#7565)
* A tecla rápida para o botón de opción Expresión regular no diálogo diccionario cambiouse de alt+r a alt+e. (#6782)
* Os ficheiros dos diccionarios da fala agora versionáronse e movéronse cara o directorio 'speechDicts/voiceDicts.v1'. (#7592)
* As modificacións dos ficheiros versionados (configuración do usuario, diccionarios da fala) xa non se gardan cando o NVDA se executa dende o lanzador. (#7688)
* As pantallas braille Braillino, Bookworm e Modular (con firmware antigo) de Handy Tech xa non se soportan ao sacalas da caixa. Instala o controlador universal de Handy Tech e o complemento de NVDA para usar as pantallas. (#7590)

### Corrección de Erros

* As ligas agora indícanse en braille en aplicacións coma no Microsoft Word. (#6780)
* O NVDA xa non se volta notablemente máis lento cando estean abertas moitas pestanas nos navegadores web Firefox ou Chrome. (#3138)
* O enrutamento do cursor para as pantallas MDV Lilli Braille xa non move incorrectamente unha celda braille antes de onde debería estar. (#7469)
* No Internet Explorer e outros documentos MSHTML, o atributo HTML5 requerido agora sopórtase para indicar o estado requerido dun campo de formulario. (#7321)
* As pantallas braille agora actualízanse ao se escrebir caracteres arábigos nun documento WordPad aliñado á esquerda (#511).
* As etiquetas acesibles para controis en Mozilla Firefox agora anúncianse máis sinxelamente no modo exploración cando a etiqueta non aparezca coma contido por si mesma. (#4773)
* Na actualización windows 10 Creators, o NVDA pode aceder de novo ao Firefox despois dun reinicio do NVDA. (#7269)
* Cando se reinicie o NVDA co Mozilla Firefox enfocado, o modo exploración estará dispoñible novamente, aíndaque é posible que teñas que premer alt+tab e voltar a premelo de novo. (#5758)
* Agora é posible aceder a contido matemático en Google Chrome nun sistema sen Mozilla Firefox instalado. (#7308)
* O sistema operativo e outras aplicacións deberían seren máis estables directamente despois de instalar o NVDA antes de reiniciar, en comparación coas instalacións de versións anteriores do NVDA. (#7563)
* Ao se usar unha orde de recoñecemento de contido (ex.: NVDA+r), agora o NVDA anuncia unha mensaxe de erro en lugar de non facer nada se o navegador de obxectos desapareceu. (#7567)
* A funcionalidade desprazamento cara atrás arransouse para pantallas de freedom Scientific que conteñan un balancín esquerdo. (#7713)

### Cambios para Desenvolvedores

* "scons tests" agora procura que as cadeas traducibles teñan comentarios para os traductores. Tamén podes executar esto só con "scons checkPot". (#7492)
* Agora hai un novo módulo extensionPoints que proporciona un framework xenérico para permitir a extensibilidade de código en puntos específicos no código. Esto permite que as partes interesadas se rexistren para seren notificadas cando ocurra algunha acción (extensionPoints.Action), para modificar un tipo específico de dato (extensionPoints.Filter) ou para participar na decisión de se se fará algo (extensionPoints.Decider). (#3393)
* Agora podes rexistrarte para seren notificado acerca dos cambios de perfiles de configuración a través da acción config.configProfileSwitched. (#3393)
* Os xestos de pantalla braille que emulan teclas modificadoras do teclado do sistema (coma control e alt) agora poden conbinarse con outras teclas emuladas do teclado do sistema sen definición explícita. (#6213)
 * Por exemplo: se tes unha tecla da pantalla vinculada á tecla alt e outra tecla da pantalla a frecha abaixo, ao se combinar estas teclas resultará na emulación de alt+frecha abaixo.
* A clase braille.BrailleDisplayGesture agora ten unha propiedade de modelo extra. Se se proporciona, premendo unha tecla xerará unha adicional, texto específico de identificador de modelo, esto permite a un usuario vencellar xestos limitados a un modelo de pantalla braille específico.
 * Consulta o controlador de baum coma un exemlo para esta funcionalidade nova.
* O NVDA agora compílase co Visual Studio 2017 e o SDK Windows 10. (#7568)

## 2017.3

O subliñable desta versión inclúe a entrada de braille contraído, o soporte para novas voces Windows OneCore dispoñibles en Windows 10, o soporte para o OCR integrado en Windows 10, e moitas melloras significativas referentes ao Braille e á web.

### Novas Características

* Engadiuse unha opción Braille para "amosar mensaxes indefinidamente". (#6669)
* Na listaxe de mensaxes do Microsoft Outlook, o NVDA agora anuncia se unha mensaxe está marcada. (#6374)
* No Microsoft PowerPoint, agora anúnciase o tipo exacto dunha forma cando se edita unha diapositiva coma triángulo, círculo, vídeo, frecha, en lugar de só 'forma'. (#7111)
* O contido matemático (proporcionado coma MathML) agora sopórtase en Google Chrome. (#7184)
* NVDA agora pode falar usando as novas voces Windows OneCore (tamén coñecidas coma voces mobile) incluidas no Windows 10. Accede a elas selecionando Voces Windows OneCore no diálogo Sintetizadores de NVDA. (#6159)
* Os ficheiros de configuración do usuario do NVDA agora poden almacenarse no cartafol local de datos de aplicacións do usuario. Esto habilítase a través dunha opción no rexistro. Consulta 'Parámetros do Sistema' na guía do usuario para máis detalles. (#6812)
* Nos navegadores web, NVDA agora anuncia valores de marcador de posición para campos (específicamente, agora sopórtase aria-placeholder). (#7004)
* No modo exploración de Microsoft Word, agora é posible navegar polos erros de ortografía usando navegación rápida (w e shift+w) (#6942)
* Engadido o soporte para o control Selector de Data que se atopa nos cadros de diálogo Citas de Microsoft Outlook. (#7217)
* Agora anúnciase a suxerencia actualmente selecionada nos campos de Windows 10 Mail para/cc e no campo Opcións de búsqueda de Windows 10. (#6241)
* Agora reprodúcese un son para indicar a aparición de suxerencias en certos campos de procura do Windows 10 (Ex.: pantalla de inicio, opcións de procura, campos de Windows 10 mail para/CC). (#6241)
* O NVDA agora anuncia as notificacións automáticamente no Skype for Business Desktop, coma cando alguén comeza unha conversa contigo.  (#7281)
* O NVDA agora anuncia automáticamente mensaxes de chat entrantes mentres se estea nunha conversa en Skype for Business. (#7286)
* O NVDA agora anuncia as notificacións automáticamente no Microsoft Edge, coma cando se comeza unha descarga. (#7281)
* Agora podes escrebir tanto en braille contraído coma sen contraer nunha pantalla braille cun teclado braille. Consulta a seción Entrada Braille da Guía do Usuario para detalles. (#2439)
* Agora podes introducir caracteres braille Unicode dende o teclado braille nunha pantalla braille selecionando Braille Unicode como a táboa de entrada nas Opcións de Braille. (#6449)
* Engadido o soporte para a pantalla braille SuperBraille usada en Taiwan. (#7352)
* Novas táboas de transcripción braille: braille danés computerizado de 8 puntos, Lituano, braille persa computerizado de 8 puntos, Persa grao 1, braille Esloveno computerizado de 8 puntos. (#6188, #6550, #6773, #7367)
* Mellorada a táboa de braille inglés computerizado de 8 puntos (U.S.), incluindo o soporte para viñetas, o signo de euro e letras acentuadas. (#6836)
* O NVDA agora pode usar a funcionalidade OCR incluida no Windows 10 para recoñecer o texto de imaxes ou de aplicacións inaccesibles. (#7361)
 * A lingua  pode configurarse dende o novo diálogo OCR de Windows 10 nas preferencias do NVDA.
 * Para recoñecer o contido do navegador de obxectos actual, preme NVDA+r.
 * Consulta a seción Recoñecemento de Contidos da Guía do Usuario para detalles adicionais.
* Agora podes escoller que información de contexto se amosa nunha pantalla braille cando un obxecto ten o foco usando a nova opción "Presentación de contexto do foco" no diálogo Opcións de Braille. (#217)
 * Por exempro, as opcións "Rechear pantalla para cambios de contexto" e "Só cando se despraza cara atrás" poden facer que traballar con listaxes e menús sexa máis eficiente, xa que os elementos non cambiarían contínuamente a súa posición na pantalla.
 * Consulta a seción na opción "Presentación de contexto do foco" na Guía do Usuario para detalles adicionais e exempros.
* En Firefox e Chrome, o NVDA agora soporta grades dinámicas comprexas coma follas de cálculo onde só se poda cargar ou amosar unha parte do contido (específicamente os atributos aria-rowcount, aria-colcount, aria-rowindex e aria-colindex introducidos en ARIA 1.1). (#7410)

### Cambios

* Engadiuse unha orde non vinculada para reiniciar o NVDA baixo demanda. Podes atopala na categoría Miscelánea do diálogo Xestos de entrada. (#6396)
* A distribución de teclado agora pode configurarse dende o diálogo Benvida do NVDA. (#6863)
* Abreviáronse moitos máis tipos de controis e estados en braille. as rexións tamén se abreviaron. Porfavor consulta "Tipo de Control, estado e Abreviaturas de rexións" en Braille na Guía do Usuario para unha listaxe compreta. (#7188, #3975)
* Actualizado o Espeak-ng á 1.49.1 (#7280).
* As listaxes de táboas de entrada e de saída no diálogo Opcións de Braille agora ordéanse alfabéticamente. (#6113)
* Actualizado o transcriptor braille liblouis a 3.2.0. (#6935)
* A tábuoa braille predeterminada agora é Braille Inglés Unificado Código Grao 1. (#6952)
* De xeito predeterminado, o NVDA agora só amosa as partes da información de contexto que cambiara nunha pantalla braille cando se enfoque un obxecto. (#217)
 * Anteriormente, sempre amosaba tanta información coma fora posible, independentemente de se viches a mesma información de contexto antes.
 * Podes voltar á anterior cambiando a nova opción "Presentación de Contexto do Foco" no diálogo Opcións de Braille a "Rechear Sempre pantalla".
* Ao se usar Braille, o cursor pode configurarse para ter unha forma diferente ao seguer ao foco ou á revisión. (#7112)
* O logo do NVDA actualizouse. O logo actualizado do NVDA é unha mistura estilizada das letras NVDA en branco, sobre un fondo sólido púrpura. Esto asegúrase de que será visible en calquera cor de fondo, e usará a cor púrpura do logo de NV Access. (#7446)

### Corrección de Erros

* Os elementos div editables en Chrome xa non teñen a súa etiqueta anunciada coma o seu valor mentres se estea en modo exploración. (#7153)
* Premer fin mentres se estea en modo exploración dun documento valdeiro do Microsoft Word xa non produce un erro en tempo de execución. (#7009)
* O modo exploración agora sopórtase correctamente no Microsoft Edge cando a un documento se lle dera un rol ARIA específico de documento. (#6998)
* En modo exploración, agora podes selecionar ou deselecionar ata o remate da liña usando shift+fin incluso cando o cursor estea sobre o derradeiro carácter da liña. (#7157)
* Se un diálogo contén unha barra de progreso, o texto do diálogo agora actualízase en braille cando a barra de progreso cambie. Esto siñifica, por exemplo, que o tempo restante agora pode lerse no diálogo do NVDA "Descargando Actualizacións". (#6862)
* NVDA agora anunciará cambios de seleción para certas caixas combinadas de Windows 10 tales como AutoReproducción en Opcións. (#6337).
* Xa non se anuncia información inxustificada ao entrar en diálogos de reunións / citas no Microsoft Outlook. (#7216)
* Pitidos indeterminados para barras de progreso de diálogo coma o actualizador só cando a saída da barra de progreso se configure para incluir pitidos. (#6759)
* No Microsoft Excel 2003 e 2007, as celdas anúncianse de novo ao se navegar a través dunha folla de cálculo. (#7243)
* Na actualización Windows 10 Creators e posterior, o modo exploración actívase de novo automáticamente ao ler correos electrónicos no Windows 10 Mail. (#7289)
* Na maioría de pantallas braille cun teclado braille, o punto 7 agora borra a derradeira celda ou carácter braille introducido, e o punto 8 preme a tecla intro. (#6054)
* No texto editable, ao se mover o cursor (ex.: coas teclas do cursor ou retroceso), a resposta falada do NVDA agora é máis precisa en moitos casos, especialmente no Chrome e nas aplicacións de terminal. (#6424)
* Agora pode lerse o contido do Editor de Firmas en Microsoft Outlook 2016. (#7253)
* Nas aplicacións Java Swing, NVDA xa non causa que ás veces a aplicación se colgue ao navegar polas táboas. (#6992)
* Na actualización Windows 10 Creators, NVDA xa non anunciará notificacións toast moitas veces. (#7128)
* No menú Inicio do Windows 10, ao se premer intro para pechalo despois dunha procura xa non se produce que o NVDA anuncie procurar texto. (#7370)
* Agora é significativamente máis rápido realizar a navegación rápida por cabeceiras no Microsoft Edge. (#7343)
* No Microsoft Edge, a navegación en modo exploración xa non se salta partes longas de certas páxinas web coma o tema Wordpress 2015. (#7143)
* No Microsoft Edge, as rexións localízanse correctamente noutras linguas diferentes do inglés. (#7328)
* O braille agora segue correctamente a selección ao se selecionar texto máis aló do ancho da pantalla. Por exempro, se selecionas varias liñas con shift+flecha abaixo, o braille agora amosa a última liña que selecionaches. (#5770)
* En Firefox, o NVDA xa non anuncia falsamente "seción" varias veces ao abrir detalles para un chío en twitter.com. (#5741)
* A ordes de navegación de táboa xa non están dispoñibles para tablas de desino en modo Exploración a menos que o anunciado das táboas de desino estea habilitado. (#7382)
* En Firefox e Chrome, as ordes de navegación de táboas en modo Exploración agora omiten as celdas ocultas da táboa. (#6652, #5655)

### Cambios para Desenvolvedores

* As marcass de tempo agora inclúen milésimas de segundo no rexistro. (#7163)
* NVDA agora debe compilarse co Visual Studio Community 2015. Visual Studio Express xa non se soporta. (#7110)
 * Agora tamén se requiren as Windows 10 Tools e o SDK, que poden habilitarse ao se instalar o Visual Studio.
 * Consulta a sección Installed Dependencies do readme para detalles adicionais.
* O soporte para recoñecedores de contido como as ferramentas OCR e descripción de imaxe poden implementarse sinxelamente usando o novo paquete contentRecog. (#7361)
* Agora inclúese o paquete de Python json package nas compilacións binarias do NVDA. (#3050)

## 2017.2

O subliñable desta versión inclúe o soporte compreto para a atenuación de audio na actualización Windows 10 Creators; correccións para varios problemas coa seleción no modo exploración, incluindo problemas con selecionar todo; meyoras significativas no soporte de Microsoft Edge; e melloras na web coma o indicado de elementos marcados como actual (usando aria-current).

### Novas Características

* Agora pódese anunciar a información do borde das celdas en Microsoft Excel usando NVDA+f. (#3044)
* Nos navegadores web, NVDA agora indica cando un elemento se marcou como actual (específicamente, usando o atributo aria-current). (#6358)
* Agora sopórtase o cambio autumático de linguas no Microsoft Edge. (#6852)
* Engadido o soporte para a Calculadora de Windows no Windows 10 Enterprise LTSB (Long-Term Servicing Branch) e Server. (#6914)
* Ao se realizar a orde ler liña actual tres veces rápidamente deletréase a liña con descripcións de caracteres. (#6893)
* Nova lingua: birmano.
* Agora fálanse apropriadamente as frechas arriba e abaixo  e os símbolos de fracción unicode. (#3805)

### Cambios

* Ao navegar coa revisión simple en aplicacións que usen UI Automation, ignóranse máis contedores sen contido facendo máis sinxela a navegación. (#6948, #6950)

### Correción de Fallos

* Os elementos de menú en páxinas Web (as caixas de verificación e os botóns de opción dos elementos de menús) agora poden activarse mentres se estea en modo exploración. (#6735)
* Premer escape mentres o indicativo "confirmar borrado" do perfil de configuración está activo agora pecha o diálogo. (#6851)
* Correxidos algúns colgues en Mozilla Firefox e outras aplicacións Gecko onde está habilitada a característica multi-proceso. (#6885)
* O anunciado da cor de fondo na revisión de pantalla agora é máis preciso cando o texto se dibuxou cun fondo trasparente. (#6467)
* Mellorado o soporte para aria-describedby en Internet Explorer 11, incluindo o soporte dentro de iframes e cando se proporcionan varios IDs. (#5784)
* Na actualización Windows Creators, a atenuación de audio do NVDA funciona de novo como en anteriores versións de Windows (ex.: Atenuar ca voz e sons, atenuar sempre, e non atenuar están dispoñibles todas). (#6933)
* NVDA xa non fallará ao navegar ou ao anunciar certos controis (UIA) onde non se definíu un atallo de teclado. (#6779)
* Xa non se engaden dous espazos valdeiros na información de atallos de teclado para certos controis (UIA). (#6790)
* Certas combinacións de teclas nas pantallas HIMS (ex.: espazo+punto4) xa non fallan intermittentemente. (#3157)
* Correxido un problema ao se abrir un porto serie en sistemas que usan certas linguas distintas ao inglés que causaban que fallara a conexión ás pantallas braille nalgúns casos. (#6845)
* Redúcese a posibilidade de que o ficheiro de configuración se corrompa ao se apagar o Windows. Os ficheiros de configuración agora escrébense nun ficheiro temporal antes de reemplazar o actual. (#3165)
* Ao se realizar a orde ler liña actual dúas veces rápidamente para deletreala, agora úsase a lingua apropriada para os caracteres deletreados. (#6726)
* Navegar por liñas no Microsoft Edge agora é ata tres veces máis rápido na Actualización Windows 10 Creators. (#6994)
* NVDA xa non anuncia "Web Runtime grouping" ao se enfocar documentos no Microsoft Edge na Actualización Windows 10 Creators (#6948)
* Agora sopórtanse todas as versións existentes do SecureCRT.  (#6302)
* Adobe Acrobat Reader xa non se rompe en certos documentos PDF (especialmente, en aqueles que conteñen atributos ActualText valdeiros). (#7021, #7034)
* No modo exploración en Microsoft Edge, as táboas interactivas (ARIA grids) xa non se saltan cando se navegan con t e shift+t. (#6977)
* No modo exploración, ao premer shift+inicio despois de selecionar cara adiante agora deseleciona ata o comezo da liña segundo se esperaba. (#5746)
* No modo exploración, selecionar todo (control+a) xa non falla para selecionar texto se o cursor do sistema non está ao comezo do texto. (#6909)
* Correxidos algúns outros problemas extranos de seleción no modo exploración. (#7131)

### Cambios para Desenvolvedores

* Os argumentos de liña de ordes agora procésanse co módulo argparser de Python, en lugar de co optparser. Esto permite a certas opcións coma -r e -q manexarse exclusivamente. (#6865)
* core.callLater agora pon en cola a devolución de chamada á cola principal do NVDA despois do retraso dado, en lugar de executala directamente despertando ao núcleo. Esto detén posibles colgues debidos a que o núcleo se vaia a dormir accidentalmente despois de procesar unha chamada, en medio dunha chamada modal coma o amosado dunha caixa de mensaxe. (#6797)
* A propiedade InputGesture.identifiers cambiouse tal que xa non se normaliza. (#6945)
 * As subclases xa non necesitan normalizar identificadores antes de devolvelos dende esta propiedade.
 * Se queres normalizar identificadores, agora hai unha propiedade InputGesture.normalizedIdentifiers a que normaliza os identificadores devoltos pola propiedade identifiers.
* A propiedade InputGesture.logIdentifier agora está obsoleta. As chamadas deberían utilizar InputGesture.identifiers[0] no seu lugar. (#6945)
* Borrouse algún código obsoleto:
 * As constantes `speech.REASON_*`, deberían usarse a cambio `controlTypes.REASON_*`. (#6846)
 * `i18nName` para opcións de sintetizador, `displayName` e `displayNameWithAccelerator` deberían usarse a cambio. (#6846, #5185)
 * `config.validateConfig`. (#6846, #667)
 * `config.save`: deberíase usar a cambio `config.conf.save`. (#6846)
* Aa listaxe de compretado no menú de contexto autocompretar da Consola Python xa non amosa calquera ruta de obxecto que leve ata o símbolo final que estea a ser compretado. (#7023)
* Agora hai unha unidade de proba do framework para o NVDA. (#7026)
 * A unidade de proba e a infraestructura atópanse no directorio tests/unit. Consulta a cadea de documentación no ficheiro tests\unit\init.py para detalles.
 * Podes executar probas utilizando "scons tests". Consulta a sección "Running Tests" do readme.md para detalles.
 * Se estás a enviar un pull request para o NVDA, deberías executar primeiro as probas e asegurarte de que se pasen.

## 2017.1

O subliñable desta versión inclúe o anunciado de secións e columnas de texto no Microsoft Word; o Soporte para lectura, navegación e anotación de libros no Kindle para PC; e o soporte mellorado para o Microsoft Edge.

### Novas Características

* Agora poden anunciarse no Microsoft Word o tipo de salto de sección e o número de sección. Esto habilítase coa opción "anunciar número de páxina" no diálogo Formateado de documentos. (#5946)
* No Microsoft Word agora pódense anunciar as columnas de texto. Esto habilítase coa opción "anunciar números de páxina" no diálogo Formateado de documentos. (#5946)
* Agora sopórtase o cambio automático de linguas no Wordpad. (#6555)
* A orde procurar do NVDA (NVDA+control+f) agora sopórtase en modo exploración para o Microsoft Edge. (#6580)
* A navegación rápida por botóns en modo exploración (b e shift+b) agora sopórtase no Microsoft Edge. (#6577)
* Cando se copìa unha folla no Microsoft Excel, lémbranse as  cabeceiras de columna e de fila configurados. (#6628)
* Soporte para ler e navegar libros no Kindle para PC versión 1.19, incluindo o acceso a ligas, notas ao pé, gráficos, texto resaltado e notas do usuario. Por favor consulta a sección Kindle para PC da Guía de Usuario do NVDA para información adicional. (#6247, #6638)
* Agora sopórtase a navegación de táboas no modo exploración no Microsoft Edge. (#6594)
* No Microsoft Excel, a orde anunciar localizaciónm do cursor de revisión (escritorio: NVDA+suprimir do teclado numérico, portátil: NVDA+suprimir) agora anuncia o nome da folla de cálculo e da localización da celda. (#6613)
* Engadida unha opción ao diálogo Saír para reiniciar co nivel depuración no rexistro. (#6689)

### Cambios

* A velocidade mínima do parpadeo do cursor braille agora é 200ms. Os perfís ou as configuracións con valores por embaixo deste incrementaranse en 200ms. (#6470)
* Engadiuse unha caixa de verificación ao diálogo opcións braille para permitir habilitar ou deshabilitar o parpadeo do cursor braille. Anteriormente usábase un valor de cero para lograr esto. (#6470)
* Actualizado o eSpeak NG (commit e095f008, 10 de xaneiro do 2017). (#6717)
* Debido aos cambios na actualización Windows 10 Creators, o modo "Atenuar sempre" xa non está dispoñible nas opcións de Atenuación de audio do NVDA. Aínda está dispoñible en versións máis vellas do windows 10. (#6684)
* Debido aos cambios na Actualización Windows 10 Creators, o modo "Atenuar cando saian voz e sons" xa non pode asegurarse de que o audio se atenuara compretamente antes de comezar a falar, nin manterá o audio atenuado o tempo suficiente despois de falar para deter o rebote rápido no volume. Estos cambios non afectan ás versións máis vellas do windows 10. (#6684)

### Correción de Fallos

* Correxido o colgue no Microsoft Word ao se mover por parágrafos a través dun documento longo mentres se está en modo exploración. (#6368)
* As táboas no Microsoft Word que se copiaran dende o Microsoft Excel xa non se tratan como táboas de deseño, e polo tanto, xa non se ignoran. (#5927)
* Cando se tenta teclear no Microsoft Excel mentres se estea en vista protexida, NVDA agora fai un son en lugar de falar os carácteres que non se escrebiron. (#6570)
* Premendo escape no Microsoft Excel xa non se cambia incorrectamente ao modo exploración, ao menos que o usuario cambiara anteriormente a modo exploración explícitamente con NVDA+espacio e logo entrado no modo foco premendo intro nun campo de formulario. (#6569)
* NVDA xa non se colga en follas de cálculo do Microsoft Excel onde se fusione unha fila ou columna enteira. 9#6216)
* O anunciado de texto recortado ou desbordado en celdas do Microsoft Excel agora debería de ser máis preciso (#6472)
* NVDA agora anuncia cando unha caixa de verificación é de só lectura. (#6563)
* O lanzador do NVDA xa non amosará un diálogo de aviso cando non poda reproducir o son de comezo debido a que non estea dispoñible o dispositivo de audio. (#6289)
* Os controis na cinta do Microsoft Excel que non estean dispoñibles agora anúncianse así. (#6430)
* NVDA xa non anunciará "panel" cando se minimicen xanelas. (#6671)
* Os caracteres que se escreben agora fálanse en aplicacións UWP (incluindo Microsoft Edge) na actualización Windows 10 Creators. (#6017)
* O seguemento do rato agora funciona en todas as pantallas en computadores con varios monitores. (#6598)
* NVDA xa non se volverá inusable despois de saír do Windows Media Player mentres se enfoca un control deslizador. (#5467)

### Cambios para Desenvolvedores

* Os ficheiros de perfís e configuración agora actualízanse automáticamente para cumprir cos requisitos das modificacións do esquema. Se hai un erro durante a actualización, amósase unha notificación, reiníciase a configuración, e o ficheiro de configuración antigo está dispoñible no rexistro do NVDA no nivel 'Info'. (#6470)

## 2016.4

O subliñable desta versión inclúe a mellora do soporte para o Microsoft Edge; o modo exploración na aplicación Correo de Windows 10; e melloras significativas para os diálogos do NVDA.

### Novas Características

* NVDA agora pode indicar a sangría de liñas utilizando tons. Esto pódese configurar usando a caixa combinada "Anunciar Sangría de Liñas" nas preferencias do diálogo Formateado de documentos do NVDA. (#5906)
* Soporte para a pantalla braille Orbit Reader 20 . (#6007)
* Engadiuse unha opción para abrir a xanela do visualizador de voz ao arrincar. Esto pode habilitarse a través dunha caixa de verificación na xanela do visualizador de voz. (#5050)
* Ao reabrir a xanela do visualizador de voz, a localización e as dimensións agora restauraranse. (#5050)
* Os campos de referencia cruzada no Microsoft Word agora trátanse coma hipervínculos. anúncianse coma ligas e pódense activar. (#6102)
* Soporte para as pantallas braille Baum SuperVario2, Baum Vario 340 e HumanWare Brailliant2. (#6116)
* Soporte inicial para a actualización Anniversary do Microsoft Edge. (#6271)
* Agora utilízase o modo exploración ao se ler correos electrónicos na aplicación correo do Windows 10. (#6271)
* Lingua nova: Lituano.

### Cambios

* Actualizado o transcriptor braille liblouis a 3.0.0. Esto inclúe melloras significativas para o Braille Inglés Unificado. (#6109, #4194, #6220, #6140)
* No administrador de complementos, os botóns Deshabilitar complemento e Habilitar complemento agora teñen atallos de teclado (alt+d e alt+e, respectivamente). (#6388)
* Resolvéronse varios problemas de recheo e aliñamento nos diálogos do NVDA. (#6317, #5548, #6342, #6343, #6349)
* O diálogo formateado de documento axustouse de xeito que o contido se deslice. (#6348)
* Axustada a distribución do diálogo pronunciación de símbolos polo que se utiliza todo o ancho do diálogo para a lista de símbolos. (#6101)
* No modo exploración en navegadores web, as ordes de navegación dunha soa letra dos campos de edición (e e shift+e) e dos campos de formulario (f e shift+f) agora moven a campos de edición de só lectura. (#4164)
* Nas opcións de formateado de documentos do NVDA, "Anunciar cambios de formato despois do cursor" renomeouse a "Anunciar cambios de formato despois  do cursor", de xeito que afecte tanto ao braille como á voz. Nota: esto non afecta á traducción ao galego xa que usamos announce e report como sinónimos. (#6336)
* Axustada a aparenza do "diálogo Benvida" do NVDA. (#6350)
* As caixas de diálogo do NVDA agora teñen os seus botóns "Aceptar" e "Cancelar" aliñados cara a dereita do diálogo. (#6333)
* Agora utilízanse controis de xiro para os campos de entrada numérica como a opción de "porcentaxe de ton de maiúsculas" no diálogo Opcións de Vopz. Podes introducir o valor decidido ou usar as teclhas de frecha arriba e abaixo para axustar o valor. (#6099)
* O modo no que se anuncia IFrames (documentos integrados dentro de documentos) fíxose moito máis consistente para os navegadores. IFrames agora anúnciase como "marco" en Firefox. (#6047)

### Correción de Fallos

* Correxido un extrano problema ao saír do  NVDA mentras o visualizador de voz está aberto. (#5050)
* Os mapas de imaxe agora procésanse coma se esperaba no modo exploración no Mozilla firefox. (#6051)
* Mentras se está no diálogo diccionarios, ao se premer a tecla intro agora gárdase calquera cambio que fixeras e péchase o diálogo. Anteriormente, ao premer intro non se facía nada. (#6206)
* Agora amósanse as mensaxes en braille ao cambiar os modos de entrada para un método de entrada (entrada nativa/alfanumérica, forma completa/ forma media, etc.). (#5892, #5893)
* Ao deshabilitar e logo inmediatamente rehabilitar un complemento ou viceversa, o estado do complemento  agora volta a tal e como estaba anteriormente. (#6299)
* Ao se usar Microsoft Word, os campos de número de páxina en cabeceiras agora poden lerse. (#6004)
* O rato agora pode usarse para mover o foco entre a lista de símbolos e os campos de edición no diálogo pronunciación de símbolos. (#6312)
* No modo exploración en Microsoft Word Correxiuse un problema que detén a aparición da lista de elementos cando contén un hipervínculo inválido. (#5886)
* Despois de seren pechado a través da barra de tarefas ou do atallo de teclado alt+F4, o estado da caixa de verificación visualizador de voz no menú NVDA agora reflitirá a visibilidade actual da xanela. (#6340)
* A orde recargar plugins xa non causa problemas para os perfís de configuración disparados, nos documentos novos en navegadores web e na revisión de pantalla. (#2892, #5380)
* Na lista de linguas no diálogo Opcións Xerais do NVDA, linguas como o Aragonés agora amósanse correctamente en Windows 10. (#6259)
* As teclas de sistema de emulación de teclado (ex.: un botón nunha pantalla braille que emule a pulsación da tecla tab) agora preséntanse na lingua configurada no NVDA na axuda de entrada e no diálogo Xestos de Entrada. Anteriormente, sempre se presentaban en inglés. (#6212)
* Ao cambiar a lingua do NVDA (dende o diálogo Opcións Xerais) agora non ten efecto ata que NVDA se reinicie. (#4561)
* Xa non é posible deixar o campo Patrón en branco para unha entrada de diccionario nova. (#6412)
* Correxido un extrano problema ao se escanear portos serie nalgúns sistemas que facía algúns controladores de pantallas braille inusables. (#6462)
* No Microsoft Word as viñetas numeradas agora lense dende as celdas das táboas ao se mover por celdas. (#6446)
* Agora é posible asignar xestos ás ordes para o controlador da pantalla braille Handy Tech no diálogo Xestos de Entrada. (#6461)
* No Microsoft Excel, ao se premer intro ou intro do teclado numérico cando se navega por unha folla de cálculo agora anúnciase correctamente a navegación á seguinte fila. (#6500)
* iTunes xa non se colga intermitentemente ao usar o modo exploración para a Tenda iTunes, Apple Music, etc. (#6502)
* Correxidos colgues nas aplicacións baseadas en Mozilla e Chrome de 64 bits. (#6497)
* No Firefox co multiproceso habilitado, o modo exploración e os campos de texto editables agora funcionan correctamente. (#6380)

### Cambios para Desenvolvedores

* Agora é posible proporcionar app modules para executables que conteñan un punto (.) nos seus nomes. Os puntos reemplázanse con subliñados (_). (#5323)
* O novo módulo gui.guiHelper inclúe utilidades para simplificar a creación de GUIs wxPython, incluíndo a xestión automática de espaciado. Esto facilita unha mellor  aparencia visual e consistencia, así como a creación sinxela de GUIs novas para desenvolvedores cegos. (#6287)

## 2016.3

O subliñable desta versión inclúe a capacidade para deshabilitar complementos individuais; o soporte para campos de formulario No Microsoft Excel; melloras significativas para o anunciado das cores; correcións e melloras relacionadas con varias pantallas braille; e correcións e melloras para o soporte do Microsoft Word.

### Novas Características

* O modo exploración agora pode utilizarse para ler documentos PDF No Microsoft Edge na actualización Windows 10 Anniversary. (#5740)
* O tachado e o dobre tachado agora anúncianse se é apropriado no Microsoft Word. (#5800)
* No Microsoft Word, agora anúnciase o título dunha táboa se se proporcionou un. Se hai unha descripción, pódese aceder a ela utilizando a opción Abrir descripción longa (NVDA+d) No modo exploración. (#5943)
* No Microsoft Word, NVDA agora anuncia información de posición cando se moven parágrafos (alt+shift+frecha abaixo e alt+shift+frecha arriba. (#5945)
* No Microsoft Word, agora anúnciase o espaciado a través da orde anunciar formato do NVDA, cando se cambie con varios atallos de teclado do Microsoft word, e cando ao te mover ao texto co espaciado de liña diferente se Anunciar Espaciado de Liña está activado nas Opcións de Formato de Documento do NVDA. (#2961)
* No Internet Explorer, os elementos estructurais HTML5 agora recoñécense. (#5591)
* O anunciado de comentarios (coma no Microsoft Word) agora poden deshabilitarse a través dunha caixa de verificación Anunciar Comentarios no diálogo de opcións de Formateado de Documentos do NVDA. (#5108)
* Agora é posible deshabilitar complementos individuais no administrador de complemento. (#3090)
* Engadíronse asignacións de teclas adicionais para as pantallas braille ALVA BC640/680 series. (#5206)
* Agora hai unha orde para mover a pantalla braille ao foco actual. Polo de agora, só as ALVA BC640/680 series teñen unha tecla asignada a esta orde, pero pode asignarse manualmente para outras pantallas no diálogo Xestos de Entrada se se desexa. (#5250)
* No Microsoft Excel, agora podes interactuar cos campos de formulario. Móvete cara os campos de formulario usando a Lista de Elementos ou a navegación de una soa letra no modo exploración. (#4953)
* Agora podes asignar un xesto de entrada para conmutar o modo de revisión sinxela usando o diálogo Xestos de Entrada. (#6173)

### Cambios

* NVDA agora anuncia as cores usando un conxunto básico comprensible de 9 tons e de 3 matices de cor, con variacións de brilo e palidez. Esto é mellor que utilizar nomes de cores máis subxetivos e menos intelixibles. (#6029)
* Modificouse o comportamento do existente NVDA+F9 logo NVDA+F10 para selecionar texto na primeira pulsación de F10. Cando se prema F10 dúas veces (en sucesión rápida) o texto cópiase ao portapapeis. (#4636)
* Actualizado eSpeak NG á versión Master 11b1a7b (22 de xunio de 2016). (#6037)

### Correción de Fallos

* No modo exploración No Microsoft Word, o copiado ao portapapeis agora conserva o formato. (#5956)
* No  Microsoft Word, NVDA agora anuncia apropriadamente ao utilizar as proprias ordes de navegación de táboas de Word (alt+inicio, alt+fin, alt+rePáx e alt+avPáx) e as ordes de seleción de táboa (shift engadido ás ordes de navegación). (#5961)
* Nas caixas de diálogo do Microsoft Word, a navegación de obxectos de NVDA foi moi mellorada. (#6036)
* Nalgunhas aplicacións coma o Visual Studio 2015, os atallos de teclado (ex.: control+c para Copiar) agora anúncianse coma se esperaba. (#6021)
* Correxiuse un raro problema ao se escanear os portos serie nalgúns sistemas que facían inusables algúns controladores de pantallas braille.  (#6015)
* O anunciado de cores no Microsoft Word agora é máis preciso tal que os cambios nos temas de Microsoft Office agora se teñan en conta. (#5997)
* Está dispoñible de novo o modo exploración en Microsoft Edge e o soporte para as suxerencias de procura do menú Inicio en compilacións de Windows 10 de despois de abril de 2016. (#5955)
* No Microsoft Word, a lectura automática de cabeceiras de táboa funciona mellor cando se traten celdas combinadas. (#5926)
* Na aplicación Mail de Windows 10, NVDA xa non falla ao ler o contido das mensaxes. (#5635)
* Cando estea activa a fala de teclas de ordes, as teclas de bloqueo coma o bloqueo de maiúsculas xa non se anuncian dúas veces. (#5490)
* Os diálogos de Control de Contas de Usuario do Windows lense correctamente de novamente na actualización Windows 10 Anniversary. (#5942)
* No Plugin Web Conference (coma se utilizou en out-of-sight.net) NVDA xa non pita e fala as actualizacións das barras de progreso relacionadas coa entrada de micrófono. (#5888)
* Ao se realizar unha orde Procurar Seguinte ou Procurar Anterior en modo exploración agora fará correctamente a procura sensible ás maiúsculas se a procura orixinal era sensible ás maiúsculas. (#5522)
* Ao se editar entradas de diccionario, agora dase retroalimentación para expresións regulares inválidas. NVDA xa non se colga se un ficheiro de diccionario contén unha expresión regular inválida. (#4834)
* Se NVDA non é capaz de comunicarse cunha pantalla braille (Por ex.: porque se desconectou), deshabilitarase automáticamente a utilización da pantalla. (#1555)
* Mellórase lixeiramente o rendemento do filtrado na Lista de Elementos do Modo Exploración nalgúns casos. (#6126)
* No Microsoft Excel, os nomes dos motivos de fondo anunciados polo NVDA agora coinciden con aqueles utilizados polo Excel. (#6092)
* Mellorado o soporte para a pantalla de autentificación de Windows 10, incluindo o anunciado de alertas e activación do campo de contrasinal co touch. (#6010)
* NVDA agora detecta correctamente os sensores de seguemento secundarios nas pantallas braille ALVA BC640/680 series. (#5206)
* NVDA pode anunciar de novo as notificacións de Windows Toast en compilacións recentes de Windows 10. (#6096)
* NVDA xa non detén ocasionalmente o recoñecemento de pulsacións das teclas nas pantallas braille Baum compatible e HumanWare Brailliant B. (#6035)
* Se está habilitado o anunciado de números de liña nas preferencias de Formato de Documento do NVDA, os números de liña agora amósanse nunha pantalla braille. (#5941)
* Cando o modo de voz estea desactivado, o anunciado de obxectos (coma premer NVDA+tab para anunciar o foco) agora aparece no Visualizador de Voz coma se agardaba. (#6049)
* Na listaxe de mensaxes de Outlook 2016, xa non se anuncia a información asociada ao borrador. (#6219)
* No Google Chrome e navegadores baseados en Chrome nunha lingua diferente ao inglés, o modo exploración xa non falla ao traballar en moitos documentos. (#6249)

### Cambios para Desenvolvedores

* A información de autentificación directamente dende unha propiedade xa non resulta en que a propiedade sexa chamada recursivamente unha e outra vez. (#6122)

## 2016.2.1

Esta versión corrixe colgues no Microsoft Word:

* NVDA xa non causa que o Microsoft Word se colgue imediatamente despois de arrancar en Windows XP. (#6033)
* Eliminado o anunciado de erros de gramática, xa que causa colgues no Microsoft Word. (#5954, #5877)

## 2016.2

O subliñable desta versión inclúe a capacidade para indicar erros de ortografía mentres se escrebe; o soporte para o anunciado de erros gramaticais en Microsoft Word; e melloras e correccións para o soporte do Microsoft Office.

### Novas Características

* No modo exploración en Internet Explorer e outros controis MSHTML, utilizando primeiro a navegación cunha soa letra para mover por anotación (a e shift+a) agora móvese ao texto insertado e eliminado. (#5691)
* En Microsoft Excel, NVDA agora anuncia o nivel dun grupo de celdas, así como se está contraído ou expandido. (#5690)
* Ao premer a orde Anunciar formato de texto (NVDA+f) dúas veces presenta a información en modo exploración para que se poida revisar. (#4908)
* En Microsoft Excel 2010 e posterior, o sombreado e o degradado de recheo de celda agora anúnciase. O anunciado automático contrólase pola opción Anunciar cores nas preferencias de Formateado de Documentos do NVDA. (#3683)
* Nova táboa de transcripción braille: Griego koiné. (#5393)
* No Visualizador de Rexistro, agora podes gardar o rexistro usando o atallo de teclado control+s. (#4532)
* Se o anunciado de erros de ortografía está habilitado e se soporta no control enfocado, NVDA reproducirá un son para alertarte dun erro de ortografía feito mentres tecleas. Esto pode deshabilitarse utilizando a nova opción "Reproducir son para erros de ortografía mentres se escrebe" no diálogo Opcións de teclado do NVDA. (#2024)
* Agora anúncianse erros gramaticais en Microsoft Word. Esto pode deshabilitarse utilizando a nova opción "Anunciar erros gramaticais" no diálogo Formateado de Documentos do NVDA. (#5877)

### Cambios

* No modo exploración e nos campos de texto editables, NVDA agora trata ao intro do teclado numérico do mesmo xeito que á tecla intro principal. (#5385)
* NVDA cambiou ao sintetizador de voz eSpeak NG. (#5651)
* En Microsoft Excel, NVDA xa non ignora unha cabeceira de columna dunha celda cando haxa unha fila en branco entre a celda e a cabeceira. (#5396)
* En Microsoft Excel, as coordinadas agora anúncianse desppois das cabeceiras para eliminar a ambigüedade entre as cabeceiras e o contido. (#5396)

### Corrección de Erros

* No modo exploración, cando se tenta utilizar a navegación cunha soa letra para moverte cara un elemento que non se soporta no documento, NVDA anuncia que esto non se soporta en lugar de anunciar que non hai elemento nesa dirección. (#5691)
* Cando se listan follas na lista de elementos en Microsoft Excel, as follas que conteñan só gráficos agora inclúense. (#5698)
* NVDA xa non anuncia información extrana cando se cambie entre xanelas nunha aplicación Java con múltiples xanelas como IntelliJ ou Android Studio. (#5732)
* En editores basados en Scintilla coma Notepad++, o braille agora actualízase correctamente ao moveren o cursor usando unha pantalla braille. (#5678)
* NVDA xa non se colga ás veces ao se habilitar a saída braille. (#4457)
* En Microsoft Word, a sangría de parágrafo agora sempre se anuncia na unidade de medida escollida polo usuario (ex.: centímetros ou pulgadas). (#5804)
* Ao se usar unha pantalla braille, moitas mensaxes de NVDA que anteriormente só se falaban agora braillifícanse tamén. (#5557)
* En aplicacións Java accesibles, o nivel dos elementos da vista en árbore agora se anuncia. (#5766)
* Correxidos colgues no Adobe Flash en Mozilla Firefox nalgúns casos. (#5367)
* En Google Chrome e navegadores baseados en Chrome, os documentos dentro de diálogos ou aplicacións agora poden lerse en modo exploración. (#5818)
* En Google Chrome e navegadores baseados en Chrome, agora podes forzar ao NVDA para cambiaren a modo exploración en diálogos web ou aplicacións. (#5818)
* En Internet Explorer e outros controis MSHTML, ao se mover o foco a certos controis (específicamente, onde se utilice aria-activedescendant) xa non cambia incorrectamente a modo exploración. Esto ocorría, por exemplo, ao moverse ás suxerencias en campos de enderezo cando se compón unha mensaxe en Gmail. (#5676)
* En Microsoft Word, NVDA xa non se colga en táboas longas cando o anunciado de cabeceiras de fila ou columna de táboa estea habilitado. (#5878)
* En Microsoft word, NVDA xa non anuncia incorrectamente texto cun nivel fora de liña (pero non un estilo de cabeceiras integradas) como unha cabeceira. (#5186)
* En modo exploración en Microsoft Word, as ordes Mover pasando a fin ou a comezo de contedor (coma e shift+coma) agora funcionan para táboas. (#5883)

### Cambios para Desenvolvedores

* Os compoñentes c++ do NVDA agora compílanse co Microsoft Visual Studio 2015. (#5592)
* Agora podes presentar un texto ou mensaxe HTML ao usuario en modo exploración utilizando ui.browseableMessage. (#4908)
* Na Guía do Usuario, cando se usa unha orde <!-- KC:setting para unha opción que ten unha tecla común para todas as distribucións, a tecla agora poderá colocarse despois dun dous puntos de ancho compreto (：) así coma os dous puntos regulares (:). (#5739) -->

## 2016.1

O subliñable desta versión inclúe a capacidade de baixar opcionalmente o volume doutros sons; melloras da saída braille e do soporte de pantallas braille; varias correcións significativas para o soporte de Microsoft Office; e correcións ao modo exploración en iTunes.

### Novas Características

* Novas táboas de transcripción braille: braille polaco computerizado de 8 puntos, mongol. (#5537), #5574)
* Podes desactivar o cursor braille e cambiar a súa forma usando as novas opcións Amosar cursor e Forma do cursor no diálogo Opcións de Braille. (#5198)
* NVDA agora pode conectar coa pantalla braille HIMS Smart Beetle  a través do Bluetooth. (#5607)
* NVDA pode baixar opcionalmente o volume doutros sons cando se instale en Windows 8 e posteriores. Esto pode configurarse usando a opción Modo de atenuación do audio no diálogo Sintetizador do NVDA ou premendo NVDA+shift+d. (#3830, #5575)
* Soporte para a APH Refreshabraille en modo HID e para a Baum VarioUltra e a Pronto! cando se conecten a través do USB. (#5609)
* Soporte para as pantallas braille HumanWare Brailliant BI/B cando o protocolo se pon en OpenBraille. (#5612)

### Cambios

* O anunciado de émfasis agora está deshabilitado por omisión. (#4920)
* No diálogo Lista de Elementos en Microsoft Excel, o atallo de teclado para Fórmulas foi cambiado a alt+r así é diferente ao atallo de teclado para o Filtro de campos. (#5527)
* Actualizado o transcriptor braille liblouis a 2.6.5. (#5574)
* A palabra "texto" xa non se anuncia cando se mova o foco ou o cursor de revisión a obxectos de texto. (#5452)

### Corrección de Fallos

* En iTunes 12, o modo exploración agora actualízase correctamente cando se carga unha páxina nova na iTunes Store. (#5191)
* En Internet Explorer e outros controis  MSHTML, ao se mover ós niveis de cabeceiras específicas ca navegación cunha soa letra agora compórtase como se esperaba cando o nivel dunha cabeceira se ignora con propósitos de accesibilidade (específicamente, cando aria-level non fai do nivel dunha etiqueta h). (#5434)
* En Spotify, o foco xa non aterriza de cotío en obxectos "descoñecido". (#5439)
* O foco agora restáurase correctamente ó voltar ó Spotify dende outra aplicación. (#5439)
* Ao se conmutar entre modo exploración e modo foco, o modo anúnciase en braille así como en voz. (#5239)
* O botón Inicio na Barra de Tareas xa non se anuncia coma unha lista e/ou como selecionado nalgunhas versións de Windows. (#5178)
* Mensaxes como "insertado" xa non se anuncian cando se creen correos en Microsoft Outlook. (#5486)
* Cando se utiliza unha pantalla braille e o texto se selecione na liña actual (ex.: ao procurar nun editor de textos para texto que ocurra na mesma liña), a pantalla braille desprazarase se é apropriado. (#5410)
* NVDA xa non sairá silenciosamente ao se pechar unha consola de ordes de Windows con alt+f4 en Windows 10. (#5343)
* Na Lista de Elementos en modo exploración, cando cambies o tipo de elemento, agora límpase o campo Filtrar por. (#5511)
* No texto editable en aplicacións de Mozilla, movendo o rato le de novo a liña, a palabra, etc. apropriada coma se esperaba en cambio de todo o contido. (#5535)
* Ao se mover o rato en texto editable en aplicacións de Mozilla, a lectura 		xa non se detén en elementos coma ligas dentro da palabra ou liña que se estea a ler. (#2160, #5535)
* En Internet Explorer, o sitio web shoprite.com agora pode lerse en modo exploración en lugar de anuncialo coma en branco. (Específicamente, os atributos lang mal formados agora manéllanse graciosamente.) (#5569)
* No Microsoft Word, o seguemento de cambios como "insertado" xa non se anuncia cando a marca de seguemento de cambios non se amosa. (#5566)
* Cando se enfoque un botón conmutable , NVDA agora anuncia cando se cambie de premedo a non premedo. (#5441)
* O anunciado da forma do rato agora funciona novamente como se agardaba. (#5595)
* Ao se falar a sangría de liña, os espazos de non separación agora trátanse como espazos normais. Con anterioridade, esto podía causar anunciamentos como "espazo espazo espazo" en lugar de "3 espazos". (#5610)
* Ao se pechar unha lista de métodos candidatos de entrada no Microsoft moderno, o foco restáurase correctamente ou a composición de entrada ou o documento subrayado. (#4145)
* No Microsoft Office 2013 e posteriores, cando as cintas están configuradas para amosar só pestanas, os elementos na cinta amósanse de novo como se esperaba cando se activa unha pestana. (#5504)
* Correcións e melloras para o ligado e a detección de xestos de pantalla tactil. (#5652)
* Os Touch screen hovers xa non se anuncian na axuda de entrada. (#5652)
* NVDA Xa non falla ao listar comentarios na Lista de Elementos para o Microsoft Excel se un comentario está sobre unha celda fusionada. (#5704)
* Nun caso moi pouco común, NVDA xa non falla ao ler o contido da folla no Microsoft Excel co anunciado de cabeceiras de fila e columna habilitado. (#5705)
* No Google Chrome, ao navegar dentro dunha Composición de Entrada cando se introducen carácteres do Este Asiático agora funciona coma se esperaba. (#4080)
* Cando se procura en Apple Music en iTunes, o modo exploración para o documento de resultados da procura agora actualízase coma se esperaba. (#5659)
* No Microsoft Excel, premendo shift+f11 para crear unha folla nova agora anuncia a túa nova posición en lugar de non anunciar nada. (#5689)
* Correxidos problemas coa saída da pantalla braille cando se introducen carácteres coreanos. (#5640)

### Cambios para Desenvolvedores

* A nova clase audioDucking.AudioDucker permite código que saca audio para indicar onde debería atenuarse o audio de fondo. (#3830)
* O constructor do nvwave.WavePlayer agora ten a palabra chave wantDucking como argumento que especifica se o audio de fondo debería se atenuar mentres se reproduce audio. (#3830)
 * Cando esto estea habilitado (o que está predeterminado), é esencial que WavePlayer.idle se chame cando sexa apropriado.
* Mellorada a Entrada/saída para pantallas braille: (#5609)
 * Os controladores Thread-safe de pantallas braille poden decrararse en si usando o atributo BrailleDisplayDriver.isThreadSafe. Un controlador thread-safe debe beneficiarse das seguintes características.
 * Os datos escríbense ó controlador de pantallas braille thread-safe en segundo plano, mellorando así o rendemento.
 * hwIo.Serial extende pyserial para chamar unha chamada cando os datos se reciban en lugar de que os controladores teñan que procuralos.
 * hwIo.Hid proporciona soporte para que as pantallas braille se comuniquen a través do USB HID.
 * hwPortUtils e hwIo poden proporcionar opcionalmente o rexistro detallado de depuración, incluindo dispositivos atopados e todos os datos enviados e recibidos.
* Hai varias propiedades novas accesibles dos xestos da pantalla táctil: (#5652)
 * Os obxectos MultitouchTracker agora conteñen unha propiedade childTrackers que contén o MultiTouchTrackers o tracker compoñíase de. Por exemplo, 2 dedos doble tap ten trackers de fillo ou dous taps de dous dedos. Os taps de dous dedos en sí mesmos teñe trackers fillos para dous taps.
 * Os obxectos MultiTouchTracker agora tamén conteñen unha propiedade rawSingleTouchTracker se o tracker foi o resultado dun só dedo facendo un tap, flick ou desprazamento. O SingleTouchTracker permite aceder ao ID subxacente asignado ao dedo polo sistema operativo e se o dedo segue ou non en contacto no momento actual.
 * TouchInputGestures agora ten propiedades x e y, eliminando a necesidade de aceder ao tracker por cousas triviais.
 * TouchInputGestures agora contén unha propiedade preheldTracker, a que é un obxecto MultitouchTracker representando os outros dedos suxeitos mentres se realiza esta ación.
* Pódense dar dous novos xestos de pantalla táctil: (#5652)
 * Premer e manter en Plural tap (ex.: doble tap e manter)
 * Un identificador xeralizado co reconto de dedos eliminados para o mantemento premedo  (ex.: hold+hover for 1finger_hold+hover).

## 2015.4

O subliñable nesta versión inclúe melloras de rendemento en Windows 10; a inclusión no Centro de Accesibilidade en Windows 8 e posterior; melloras para Microsoft Excel, incluindo o listado e o renomeado de follas e o aceso a celdas bloqueadas en follas con protección; e apoio para a edición de texto enriquecido en Mozilla Firefox, Google Chrome e Mozilla Thunderbird.

### Novas Características

* NVDA agora aparece no Centro de Accesibilidade en Windows 8 e posterior. (#308)
* Ó se mover por celdas en Excel, os cambios de formato agora anúncianse automáticamente se se activaron as opcións apropriadas nas opcións do diálogo Formato de Documento do NVDA. (#4878)
* Engadiuse unha opción Anunciar Énfase ó diálogo Opcións de Formato de Documento do NVDA. Activada por omisión, esta opción permite ó NVDA anunciar automáticamente a existencia de texto destacado en documentos. Ate o de agora só está soportado para as etiquetas em e strong en modo exploración para Internet Explorer e outros controis MSHTML. (#4920)
* A existencia de texto insertado e eliminado agora anúnciase en modo exploración para Internet Explorer e outros controis MSHTML, se a opción Anunciar Revisión do Editor do NVDA está activada. (#4920)
* Ó ver seguemento de cambios na lista de elementos do NVDA para Microsoft Word, agora amósase máis información como que propiedades de formato se cambiaron. (#4920)
* Microsoft Excel: agora é posible listar e renomear follas dende a Lista de Elementos do NVDA (NVDA+f7). (#4630, #4414)
* Agora é posible configurar se os símbolos actuais se envían ós sintetizadores de voz (ex.: para causar unha pausa ou para cambiar a entoación) no diálogo Pronunciación de Símbolos. (#5234)
* En Microsoft Excel, NVDA agora anuncia calquera mensaxe de entrada posto polo autor da folla nas celdas. (#5051)
* Apoio para as pantallas braille Baum Pronto! V4 e VarioUltra cando se conecten a través do Bluetooth. (#3717)
* Apoio para a edición de texto enriquecido en aplicacións de Mozilla como Google Docs co apoio ó braille habilitado en Mozilla Firefox e composición HTML en Mozilla Thunderbird. (#1668)
* Apoio para edición ou texto enriquecido en Google Chrome e navegadores baseados en Chrome como Google Docs co apoio braille habilitado. (#2634)
 * Esto require de Chrome versión 47 ou posterior.
* No modo exploración en Microsoft Excel, podes navegar a celdas bloqueadas en follas protexidas. (#4952)

### Cambios

* A opción Anunciar Revisións do Editor no diálogo Opcións de Formato de documento do NVDA agora actívase por omisión. (#4920)
* Ó moverse por carácteres no Microsoft Word ca opción do NVDA Anunciar Vevisións do Editor, agora anúnciase menos información para seguemento de cambios, o que fai a navegación máis eficiente. Para ver a información extra, usa a Lista de Elementos. (#4920)
* Actualizado o transcriptor braille liblouis translator  a 2.6.4. (#5341)
* Varios símbolos (incluindo símbolos básicos matemáticos) movéronse ó nivel algunha tal que sexan falados por omisión. (#3799)
* Se o sintetizador o soporta, a voz agora debería se pausar para os parénteses e o guión final (–). (#3799)
* Ó se selecionar texto, o texto anúnciase antes da indicación da selección en lugar de despois. (#1707)

### Corrección de fallos

* Grandes melloras de rendemento ó navegar pola barra de mensaxes en Outlook 2010/2013. (#5268)
* Nun gráfico en Microsoft Excel, ó navegar con certas teclas (como ó cambiar de folla con control+rePáx e control+avPáx) agora funciona correctamente. (#5336)
* Correxida a forma visual dos botóns no diálogo de advertencia que se amosa cando tentas actualizar NVDA a unha versión anterior. (#5325)
* En Windows 8 e posterior, NVDA agora arranca moito máis rápido cando se configurou para iniciarse despois de autentificarse en Windows. (#308)
 * Se habilitaches esto utilizando unha versión anterior  do NVDA, necesitarás deshabilitalo e habilitalo de novo no diálogo  Opcións Xerais para que o cambio teña efecto. Segue este procedemento:
  1. Abre o diálogo Opcións Xerais.
  1. Desmarca a caixa de verificación Iniciar Automáticamente NVDA Despois de Autentificarse en Windows.
  1. Preme o botón Aceptar.
  1. Abre o diálogo Opcións Xerais de novo.
  1. Marca a caixa de verificación Iniciar Automáticamente NVDA Despois de Autentificarse en Windows.
  1. Preme o botón Aceptar.
* Melloras de rendemento para UI Automation incluindo Explorador de Arquivos e Visualizador de Tarefas. (#5293)
* NVDA agora cambia correctamente a modo foco cando se tabula a controis read-only ARIA grid en modo Exploración para Mozilla Firefox e outros controis baseados en Gecko. (#5118)
* NVDA agora anuncia correctamente "non hai anterior" en lugar de "non hai seguinte" cando non hai máis obxectos ó facerse clic esquerdo nunha pantalla tactil.
* Correxidos problemas ó se teclear varias palabras dentro do campo filtro no diálogo Xestos de Entrada. (#5426)
* NVDA xa non se colga nalgúns casos cando se reconecta a unha pantalla HumanWare Brailliant BI/B series a través do USB. (#5406)
* En linguas con caracteres conxunción, as descripcións de carácter agora funciona como debera para mayúsculas de caracteres en inglés. (#5375)
* NVDA xa non debería colgarse ocasionalmente ó despregar o Menú de Inicio en Windows 10. (#5417)
* En Skype para Escritorio, agora anúncianse as notificacións que se amosan antes de que unha notificación anterior desapareza. (#4841)
* Agora anúncianse correctamente as notificacións no Skype para Escritorio 7.12 e posterior. (#5405)
* NVDA agora anuncia correctamente o foco ó pechar un menú de contexto nalgunhas aplicacións coma Jart. (#5302)
* En Windows 7 e posterior, anúnciase de novo a Cor en certas aplicacións coma Wordpad. (#5352)
* Ó se editar en Microsoft PowerPoint, premendo intro agora anúnciase automáticamente o texto introducido como unha viñeta ou número. (#5360)

## 2015.3

O subliñable nesta versión inclúe o apoio inicial para Windows 10; a capacidade de deshabilitar a navegación de unha soa letra no modo exploración (útil para algunhas aplicacións web); melloras no Internet Explorer; e correccións para texto ilexible ó se escrebir en certas aplicacións co braille habilitado.

### Novas Características

* A existencia de erros de ortografía anúnciase Nos campos editables para o Internet Explorer e outros controis MSHTML. (#4174)
* Agora fálanse moitos más  símbolos matemáticos unicode  cando aparezan  no texto. (#3805)
* Agora anúnciase automáticamente a procura de suxerencias na pantalla de inicio do Windows 10 (#5049)
* Soporte para as pantallas braille EcoBraille 20, EcoBraille 40, EcoBraille 80 e EcoBraille Plus. (#4078)
* No modo exploración, agora podes  activar e desactivar a navegación con unha soa letra premendo NVDA+shift+espazo. Cando se desactive, as teclas de unha soa letra pásanse á aplicación, o que é útil para algunhas aplicacións web como Gmail, Twitter e Facebook. (#3203)
* Novas táboas de transcripción braille: Finés de 6 puntos, Irlandés grao 1, Irlandés grao 2, Coreán grao 1 (2006), Coreán grao 2 (2006). (#5137, #5074, #5097)
* Agora sopórtase o teclado QWERTY na pantalla braille Papenmeier BRAILLEX Live Plus. (#5181)
* Apoio Experimental para o navegador web Microsoft Edge e o motor de exploración web no Windows 10. (#5212)
* Nova lingua: Canadá.

### Canbios

* Actualizado o transcriptor braille liblouis a 2.6.3. (#5137)
* Ó tentar instalar unha versión máis antiga do NVDA da que está instalada actualmente, agora avisaráseche de que esto non está recomendado e de que NVDA debería desinstalarse compretamente antes de proceder. (#5037)

### Corrección de Erros

* No modo exploración para  Internet Explorer e outros controis MSHTML, a navegación rápida por campos xa non inclúe incorrectamente elementos de listas presentacionais. (#4204)
* No Firefox, NVDA xa non anuncia inapropriadamente o contido dun ARIA tab panel cando o foco se mova dentro del. (#4638)
* No Internet Explorer e outros controis MSHTML, ó tabular dentro de seccións, artículos ou diálogos  xa non anuncia inapropriadamente todo o contido no contedor. (#5021, #5025)
* Ó utilizar as pantallas braille Baum/HumanWare/APH cun teclado braille, a entrada braille xa non detén o seu funcionamento despois de premer outro tipo de tecla na pantalla. (#3541)
* En Windows 10, agora xa non se anuncia información extrana ó se premer alt+tab ou alt+shift+tab para cambiar entre aplicacións. (#5116)
* O texto excrito xa non é ilexible ó se utilizar certas aplicacións como Microsoft Outlook con unha pantalla braille. (#2953)
* No modo exploración en Internet Explorer e outros controis MSHTML, agora anúnciase o contido correcto cando un elemento aparece ou cambia e enfócase inmediatamente. (#5040)
* No modo exploración en Microsoft Word, a navegación con unha soa tecla agora actualízase na pantalla braille e o cursor de revisión seguúndo se esperaba. (#4968)
* En braille, xa non se amosan extranos espazos en braille entre ou despois dos indicadores para controis e formato. (#5043)
* Cando unha aplicación está respondendo lentamente e cambias dende esa aplicación, NVDA agora é moito máis  sensible en outras aplicacións en máis casos. (#3831)
* As notificacións de Windows 10 Toast agora anúncianse como se esperaba. (#5136)
* O valor agora anúnciase segundo se  cambie en certas caixas combinadas (UI Automation) onde esto non funcionaba ate o de agora.
* No Modo exploración en navegadores web, ó tabular agora compórtase segundo se espera  despois de tabular a un marco de documento. (#5227)
* A pantalla de bloqueo do Windows 10 agora pode pecharse utilizando a pantalla tactil. (#5220)
* No Windows 7 e posteriores, o texto xa non é ilexible ó se teclear en certas aplicacións como Wordpad e Skype cunha pantalla braille. (#4291)
* Na pantalla de bloqueo do Windows 10, xa  non é posible ler o portapapeis, acesar a  aplicacións en execución co cursor de revisión, cambiar a configuración do NVDA, etc. (#5269)

### Cambios para Desenvolvedores

* Agora podes inxectar a entrada bruta dende un teclado de sistema que non se manexa nativamente polo Windows (ex.: un teclado QWERTY nunha pantalla braille) utilizando a nova función keyboardHandler.injectRawKeyboardInput . (#4576)
* Engadiuse eventHandler.requestEvents para solicitar eventos particulares que estean bloqueados por defecto; ex.: amosa eventos dende un control específico ou certos eventos aínda que estean de fondo. (#3831)
* En lugar dun só atributo i18nName, synthDriverHandler.SynthSetting agora ten os atributos  displayNameWithAccelerator e displayName separados para evitar o anunciado do acelerador no grupo de opcións do sintetizador nalgunhas linguas.
 * Por compatibilidade con versións anteriores, no constructor, displayName é opcional e deribarase de displayNameWithAccelerator se non se proporciona. Con todo, se tentas ter un acelerador para unha opción, deberían proporcionarse ámbolos dous.
 * O atributo i18nName está obsoleto e poderá eliminarse en unha versión futura.

## 2015.2

O subliñable desta  versión inclúe a capacidade de ler gráficos en  Microsoft Excel e o apoio para a lectura e a navegación interactiva de contido matemático.

### Novas Características

* Agora é posible moverse cara adiante ou atrás por frases no Microsoft Word e Outlook con alt+flecha abaixo e alt+flecha arriba respectivamente. (#3288)
* Novas táboas de transcripción braille para varias linguas da India. (#4778)
* No Microsoft Excel, NVDA agora anuncia cando unha celda ten contido desbordante ou cortado. (#3040)
* No Microsoft Excel, agora podes utilizar a Lista de Elementos (NVDA+f7) para permitir o listado de gráficos, comentarios e fórmulas. (#1987)
* Apoio para a lectura de gráficos en Microsoft Excel. Para utilizar esto, selecciona o gráfico utilizando a Lista de Elementos (NVDA+f7) e logo utiliza as teclas de cursor para moverte entre os puntos de datos. (#1987)
* Utilizando MathPlayer 4 from Design Science, NVDA agora pode ler e navegar interactivamente polo contido matemático nos navegadores web e en Microsoft Word e PowerPoint. Mira a sección "Lendo Contido Matemático" na Guía do Usuario para detalles. (#4673)
* Agora é posible asignar xestos de entrada (ordes de teclado, xestos táctiles, etc.) Para todos os diálogos de preferencias do NVDA e opcións de formato de documento utilizando o diálogo Xestos de Entrada. (#4898)

### Cambios

* No diálogo de formateado de documentos do NVDA, os atallos de teclado para Anunciar listas, Anunciar ligas, Anunciar números de Líña e Anunciar Nome da fonte cambiáronse. (#4650)
* No diálogo Opcións do Rato do NVDA, engadíronse atallos de teclado para Reproducir son cando se move o rato e O brilo controla o volume do audio das coordenadas. (#4916)
* Melloras significativas no anunciado de nomes de cor. (#4984)
* Actualizado o transcriptor braille liblouis a 2.6.2. (#4777)

### Corrección de Fallas

* As descripcións de carácter agora manéxanse correctamente para conxuntos de carácteres en certas linguas da India. (#4582)
* Se a opción "Confiar na Lingua da Voz ó Procesar Caracteres e Símbolos" está activada, o diálogo Pronunciación de Puntoación/Símbolos  agora utiliza correctamente a lingua da voz. Tamén, a lingua para a que a pronunciación estea sendo editada amósase no título do diálogo. (#4930)
* En Internet Explorer e outros controis MSHTML, os caracteres tecleados xa non se anuncian inapropriadamente en caixas combinadas editables como o campo de búsqueda de Google na páxina de inicio de Google. (#4976)
* Ó seleccionar cores en aplicacións de Microsoft Office, os nomes de cor agora anúncianse. (#3045)
* A saída braille en Danés agora funciona de novo. (#4986)
* AvPáx/rePáx poden utilizarse de novo para cambiar diapositivas dentro dunha presentación de diapositivas de PowerPoint. (#4850)
* En Skype para Escritorio 7.2 e posteriores, as notificacións de tecleo agora anúncianse e correxíronse os problemas imediatamente despois de mover o foco fora dunha conversa. (#4972)
* Correxidos problemas ó teclear certos símbolos de puntoación como parénteses dentro do campo de filtrado no diálogo Xestos de Entrada. (#5060)
* En Internet Explorer e outros controis MSHTML, ó premer g ou shift+g para navegar por gráficos agora inclúense elementos marcados como imaxes para propósitos de accesibilidade (por exemplo ARIA role img). (#5062)

### Cambios para Desenvolvedores

* brailleInput.handler.sendChars(mychar) xa non filtrará un carácter se é igual ó carácter anterior, asegurándose que a tecla enviada  se liberou correctamente.
* Os scripts para cambiar os modos táctiles agora cumplen cas novas etiquetas engadidas a touchHandler.touchModeLabels. (#4699)
* Os complementos poden proveer as súas proprias implementacións de presentación matemática. Mira o paquete mathPres para detalles. (#4509)
* Implementáronse ordes de voz para insertar unha ruptura entre palabras e para cambiar o ton, volume e velocidade. Mira BreakCommand, PitchCommand, VolumeCommand e RateCommand no módulo speech. (#4674)
 * Tamén hai speech.PhonemeCommand para insertar pronunciacións específicas, pero as implementacións actuais só soportan un número moi limitado de fonemas.

## 2015.1

O sinalable nesta versión  inclúe o modo exploración para documentos en Microsoft Word e Outlook; melloras maiores o soporte para Skype para Escritorio; e coreccións significativas para Microsoft Internet Explorer.

### Novas Características

* Agora podes engadir símbolos novos no diálogo Pronunciación de Símbolos. (#4354)
* No diálogo Xestos de Entrada, podes utilizar o novo campo "Filtrar por" para amosar só xestos que conteñan palabras específicas. (#4458)
* NVDA agora anuncia automáticamente texto novo en mintty. (#4588)
* No diálogo  Procurar en modo exploración, agora hai unha opción para realizar unha busca sensible ás maiúsculas. (#4584)
* Agora está dispoñible a navegación rápida (h para cabeceiras etc) máis a Lista de Elementos (NVDA+f7) en documentos de Microsoft Word activando o modo Exploración con NVDA+espazo. (#2975)
* Lendo mensaxes HTML en Microsoft Outlook 2007 e posterior mellorouse moito cando se activa automáticamente o modo Exploración para esas mensaxes. Se o modo exploración non se habilita nalgunhas situacións raras, podes forzalo con NVDA+espazo. (#2975)
* As cabeceiras de columna de táboa no Microsoft word anúncianse automáticamente para táboas onde se especificara unha cabeceira de fila polo autor a través das propiedades de táboa do Microsoft word. (#4510)
 * Sin embargo, para táboas onde as filas foran fusionadas esto non funcionará automáticamente. Nesta situación aínda podes fixar as cabeceiras de columna manualmente no NVDA con NVDA+shift+c.
* No Skype para Escritorio, agora anúncianse as notificacións. (#4741)
* No Skype para Escritorio, agora podes anunciar e revisar as mensaxes recentes utilizando NVDA+control+1 ata NVDA+control+0; por ex.: NVDA+control+1 para a mensaxe máis recente e NVDA+control+0 para a décima máis recente. (#3210)
* Nunha conversa No Skype para Escritorio, NVDA agora anuncia cando un contacto estea a teclear. (#3506)
* NVDA agora pode instalarse en silenzo a través da liña de ordes  sen iniciar a copia instalada despois da instalación. Para facer esto, utiliza --install-silent. (#4206)
* Soporte para as pantallas braille Papenmeier BRAILLEX Live 20, BRAILLEX Live e BRAILLEX Live Plus. (#4614)

### Cambios

* No diálogo de opcións de Formateado de documentos do NVDA, a opción para anunciar erros de ortografía agora ten un atallo de teclado (alt+r). (#793)
* NVDA agora utilizará a lingua do sintetizador ou voz para o procesamento do carácter e símbolo (incluindo nomes de símbolos de puntuación), xa o cambio automático de lingua estea activado ou non. Para desactivar esta característica para que NVDA utilice de novo a súa lingua de interface, desmarca a nova opción en Opcións de Voz chamada Confiar na lingua da Voz ó procesar caracteres e símbolos. (#4210)
* Eliminouse o soporte para o sintetizador Newfon. Agora Newfon está dispoñible como un complemento do NVDA. (#3184)
* Agora requírese Skype para Escritorio 7 ou posterior para utilizar co NVDA; non se soportan as versións anteriores. (#4218)
* A descarga das actualizacións do NVDA agora é máis segura. (en concreto, a información de actualización recupérase a través de https e o hash do ficheiro verifícase tras a súa descarga.) (#4716)
* Actualizouse o eSpeak á versión 1.48.04 (#4325)

### Corrección de Erros

* No Microsoft Excel, manéllase o caso cando as celdas de cabeceira de fila e columna se fusionan. Ex.: se A1 e B1 se fusionan, entón B2 agora terá A1 e B1 anunciado como a súa cabeceira de columna, en lugar de nada en absoluto. (#4617)
* Ó se editar o contido  dunha caixa de texto en Microsoft PowerPoint 2003, NVDA anunciará correctamente o contido de cada liña. Anteriormente as liñas  indicaríanse mal,   un cqarácter por cada novo parágrafo. (#4619)
* Todos os diálogos do NVDA agora céntranse na pantalla, mellorando a presentación visual e a usabilidade. (#3148)
* En Skype para sobremesa, ó se introducir unha mensaxe introductoria para engadir un contacto, a entrada e o movemento polo texto agora funciona correctamente. (#3661)
* Cando o foco se mova cara un elemento novo en vistas en árbore no IDE  Eclipse, se o elemento anteriormente enfocado é unha caixa de verificación, xa non anuncia incorrectamente. (#4586)
* No diálogo de corrección de ortografía do Microsoft Word, o seguinte erro anunciarase automáticamente cando o anterior se cambie ou ignore utilizando os atallos de teclado respectivos. (#1938)
* O texto pode lerse de novo correctamente en lugares como a xanela de terminal de Tera Term Pro e documentos en Balabolka. (#4229)
* O foco agora volta correctamente ó documento que se estea a editar cando se remate a composición de entrada de texto en coreano e outras linguas do este asiático mentras se edita dentro dun marco en Internet Explorer e outros documentos MSHTML. (#4045)
* No diálogo Xestos de entrada, ó seleccionar unha distribución de teclado para un xesto de teclado que se engade, agora premendo escape péchase o menú como se debera en lugar de pechar o diálogo. (#3617)
* Ó eliminar un complemento, o directorio do complemento agora bórrase correctamente despois de reiniciar o NVDA. Anteriormente, tiñas que reinicialo dúas veces. (#3461)
* Corexíronse os principais problemas ó utilizar Skype para Escritorio 7. (#4218)
* Cando envíes unha mensaxe en Skype para Escritorio, xa non o le dúas veces. (#3616)
* No Skype para Escritorio, NVDA xa non debería ler ocasionalmente unha grande cantidade de mensaxes en falso (quizáis incluso unha conversa enteira. (#4644)
* Correxido un problema onde a orde de NVDA Anunciar data e hora non tiña en conta nalgúns casos as opcións rexionais especificadas polo usuario. (#2987)
* No Modo exploración, xa non se presenta texto sen sentido (abranguendo ás veces varias liñas) para certos gráficos como os atopados en Google Groups. (en concreto, esto ocurría cas imaxes codificadas en base 64.) (#4793)
* NVDA xa non debería  conxelarse despois duns poucos segundos cando se saca o foco dunha aplicación de estilo Windows 8 Metro cando permanece suspendido. (#4572)
* O atributo aria-atomic en rexións activas en Mozilla Firefox agora tense en conta incluso aíndaque  o mesmo elemento atomic cambie. Anteiormente só afectaba a elementos descendentes. (#4794)
* O modo exploración reflictirá actualizacións, e as rexións activas anunciaranse,  para documentos en modo exploración dentro de aplicacións ARIA integradas nun documento en Internet Explorer ou outros controis MSHTML. (#4798)
* Cando o texto cambie ou se engada a rexións activas de texto relevante en Internet Explorer e outros controis MSHTML, só se anuncia o texto cambiado ou engadido, en lugar de todo o texto no elemento contedor. (#4800)
* O contido indicado polo atributo aria-labelledby en elementos en Internet Explorer e outros controis MSHTML reemplaza correctamente o contido orixinal  onde sexa apropriado facelo. (#4575)
* Cando se revisa a ortografía no Microsoft Outlook 2013, agora anúnciase a palabra mal escribida. (#4848)
* En Internet Explorer e outros controis MSHTML, o contido dentro de elementos ocultos con visibility:hidden xa non se presenta inapropriadamente no modo exploración. (#4839, #3776)
* En Internet Explorer e outros controis MSHTML, o atributo title en controis form xa non toma inapropriadamente preferencia sobre outras asociacións de etiqueta. (#4491)
* En Internet Explorer e outros controis MSHTML, NVDA xa non ignora o enfocado de elementos  debido ó atributo aria-activedescendant. (#4667)

### Cambios para desenvolvedores

* Actualizado wxPython a 3.0.2.0. (#3763)
* Actualizado Python a 2.7.9. (#4715)
* NVDA xa non se romperá cando se reinicie despois de eliminar ou actualizar un complemento que importe speechDictHandler no seu módulo installTasks. (#4496)

## 2014.4

### Novas Características

* Novos idiomas: Español de Colombia, Punjabi
* Agora é posible reiniciar o NVDA ou reiniciar NVDA cos complementos deshabilitados dende o diálogo saír do NVDA. (#4057)
 * NVDA tamén pode iniciarse cos complementos deshabilitados utilizando a opción de liña de ordes --disable-addons.
* Nos diccionarios da Fala, agora é posible especificar que un patrón só deba compararse se é unha palabra completa; é dicir,non ocurre como parte dunha palabra máis longa. (#1704)

### Cambios

* se un obxecto ó que te moveras ca navegación de obxectos está dentro dun documento en modo exploración, pero o obxecto no que estabas anteriormente non o estaba, o modo revisión ponse automáticamente en documentos. Con anterioridade esto só ocorría se o navegador de obxectos se movía debido ó cambio do foco. (#4369)
* As listas de pantallas Braille e de Sintetizadores nas súas respectivas caixas de diálogo agora ordéanse alfabéticamente excepto para Sen braille/Sen voz,  as que agora están ó fondo. (#2724)
* Actualizado o transcriptor braille liblouis a 2.6.0. (#4434, #3835)
* No modo exploración, ó se premer e e shift+e para  navegar ós campos de edición agora inclúense caixas combinadas editables. Esto inclúe a caixa procurar na última  versiónn de Google Search. (#4436)
* Ó facer Clic no icono do NVDA na Area de Notificación co botón esquerdo do rato agora ábrese o menú NVDA en lugar de non facer nada. (#4459)

### Corrección de Fallos

* Ó mover cara atrás o foco nun documento en modo exploración (ex.: indo a unha pestana a unha páxina web xa aberta) o cursor de revisión colócase apropriadamente no cursor virtual, en lugar de no control enfocado (ex.: nunha liga máis cercano). (#4369)
* En presentacións de diapositivas en Powerpoint, o cursor de revisión segue correctamente ó cursor virtual. (#4370)
* En Mozilla Firefox e outros navegadores baseados en Gecko, o contido novo dentro dunha rexión activa anunciarase incluso se o contido novo ten un tipo diferente de ARIA activa usable á rexión activa pai. Ex.: Contido marcado como assertive engádese a unha rexión activa marcada como polite. (#4169).
* En Internet Explorer e outros controis MSHTML, nalgúns casos nos que un documento estea contido dentro doutro documento xa non se evita que o usuario poda acceder  a algúns dos contidos (en concreto, framesets dentro de framesets). (#4418)
* NVDA xa non se colga cando intenta utilizar unha pantalla braille Handy Tech nalgúns casos. (#3709)
* En Windows Vista, xa non se amosa un expúreo diálogo "Entry Point Not Found" amosado en varios casos como cando se inicia NVDA dende o atallo do escritorio ou a través da tecla de acceso directo. (#4235)
* Correxíronse problemas serios con controis de texto editable en diálogos en versións recentes de Eclipse. (#3872)
* En Outlook 2010, agora mover o cursor funciona como se espera no campo de ubicación de citas e solicitudes de reunión. (#4126)
* Dentro dunha rexión activa, o contido que estea marcado como non activo (ex.: aria-live="off") agora ignórase correctamente. (#4405)
* Ó se anunciar o texto dunha barra de estado que ten un nome, o nome agora sepárase correctamente da primeira palabra do texto da barra de estado. (#4430)
* En campos de introdución de palabras chave ca fala de palabras ó se escreber activada, xa non se anuncian varios asteriscos inútilmente ó comezar palabras novas. (#4402)
* Na lista de mesaxes do Microsoft Outlook, os elementos xa non se anuncian inútilmente como elementos de Data. (#4439)
* Ó se seleccionar texto no control de edición de código no IDE Eclipse, xa non se anuncia toda a selección cada vez que a selección cambia. (#2314)
* Varias versións de Eclipse, como Spring Tool Suite e a versión incluída no paquete Android Developer Tools, agora recoñécense como Eclipse e manéllanse apropriadamente. (#4360, #4454)
* O seguemento do rato e a exploración tactil en Internet Explorer e outros controis MSHTML (incluíndo moitas aplicacións Windows 8) agora é moito máis preciso en pantallas de alta DPI ou cando se cambia o zoom do documento. (#3494)
* O seguemento do rato e a exploración tactil en Internet Explorer e outros controis MSHTML agora anuncia a etiqueta de máis botóns. (#4173)
* Ó se utilizar unha pantalla braille Papenmeier BRAILLEX co BrxCom, as teclas na pantalla agora funcionan como se agardaba. (#4614)

### Cambios para Desenvolvedores

* Para executables que abranguen moitas aplicacións diferentes (ex.: javaw.exe), agora o código pode proporcionarse para que cargue app modules específicos para cada aplicación en lugar de cargar o mesmo app module para todas as aplicacións incluídas. (#4360)
 * Olla  a documentación do código para appModuleHandler.AppModule para máis detalles.
 * Implementouse o soporte para javaw.exe.

## 2014.3

### Novas Características

* Os sons que se executan cando NVDA arranca e sae pódense desactivar a través dunha nova opción na caixa de diálogo Opcións Xerais. (#834)
* Pódese acceder á axuda para os complementos dende o Administrador de complementos para os que o soporten. (#2694)
* Soporte para o Calendario en Microsoft Outlook 2007 e superior (#2943) incluíndo:
 * O anunciado da hora actual ó te mover cas flechas,
 * O indicado de se a hora seleccionada está dentro dalgunha cita,
 * o anuncio da cita seleccionada ó premer tab
 * O filtrado intelixente da hora de xeito que só se anuncia a data se a nova hora ou cita seleccionada é nun día diferente á derradeira.
* Mellorado o soporte para a bandexa de entrada e outras listas de menxases  en Outlook 2010 e superior (#3834) incluíndo:
 * A capacidade de silenciar as cabeceiras de columna (de, Asunto etc) desactivando a opción Anunciar Cabeceiras de Fila e Columna de Táboa nas Opciones de Formateado de Texto,
 * A capacidade de utilizar as ordes de navegación de táboa (control + alt + flechas) para moverse ó longo das columnas individuais.
* Microsoft word: Se unha imaxe en liña non ten posto ningún texto alternativo, NVDA anunciará o título da imaxe, se o autor proporcionou un. (#4193)
* Microsoft Word: NVDA agora pode anunciar o sangrado do parágrafo ca orden anunciar formato (NVDA+f). Tamén pode anunciarse automáticamente cando a nova opción Anunciar Sangría de Parágrafo estea habilitada nas opcións de Formato de Documento. (#4165)
* Anúnciase o texto insertado automáticamente como unha nova viñeta, número ou sangría cando se prema intro en documentos e campos de texto editables. (#4185)
* Microsoft word: Ó se premer NVDA+alt+c anunciaráse o texto dun comentario se o cursor está dentro dun. (#3528)
* Mellorado o soporte para a lectura automática de cabeceiras de fila e columna no Microsoft Excel (#3568) incluíndo:
 * Soporte dos rangos de nomes definidos de Excel para identificar as celdas de cabeceira (compatible co lector de pantalla Jaws)
 * As ordes fixar cabeceira de columna (NVDA+shift+c) e fixar cabeceira de fila (NVDA+shift+r) agora almacenan as opcións na folla de cálculo para que estén dispoñibles a seguinte vez que a folla se abra  e estarán dispoñibles para outros lectores de pantalla que soporten o esquema de rango de nomes definidos.
 * Estas ordes agora tamén poden utilizarse múltiples veces por folla para fixar diferentes cabeceiras para diferentes rexións.
* Soporte para a lectura automática de  cabeceiras de columna e fila en Microsoft Word (#3110) incluíndo:
 * Soporte de marcas de MS Word para identificar celdas de cabeceira (compatible co lector de pantalla Jaws)
 -  as ordes fixar cabeceira de columna (NVDA+shift+c) e fixar cabeceira de fila (NVDA+shift+r) mentres se estea na primeira celda de cabeceira nunha táboa permiten dicir ó NVDA que esas cabeceiras  deberían anunciarse automáticamente.  As opcións almacénanse no documento tal que estén disponibles a seguinte vez que o documento se abra, e estarán dispoñibles para outros lectores de pantalla que soporten o esquema de marcas.
* Microsoft Word: Anuncia a distancia dende o borde esquerdo da páxina cando se prema a tecla tab. (#1353)
* Microsoft Word: proporciónase información en voz e en braille para a maioría de teclas de atallo dispoñibles  para o formato (negriña, cursiva, subliñado,  alineación, nivel de esquema, superíndice, subíndice e tamaño de fonte ). (#1353)
* Microsoft Excel: Se a celda seleccionada contén comentarios, poden ser agora anunciados premendo NVDA+alt+c (#2920)
* Microsoft Excel: proporciónase un diálogo específico para o NVDA para editar os comentarios sobre a celda seleccionada ó premer a orden de Excel shift + f2 para acceder ó modo de edición de comentarios. (#2920)
* Microsoft Excel: información en voz e en braille  para moitos máis atallos de teclado para movementos de selección (#4211) incluíndo:
 * Movemento de páxina Vertical (RePáx e AvPáx)
 * Movemento de páxina Horizontal (alt+RePáx e alt+AvPáx)
 * Ampliar a selección (as teclas anteriores engadindo Shift).
 * Selección da rexión actual (control+shift+8)
* Microsoft Excel: anunciar  alineación vertical e horizontal para as céldas ca orden anunciar formato(NVDA+f) e automáticamente se a opción Anunciar Alineación nas opcións Forrmato de Documentos está activada. (#4212)
* Microsoft Excel: anunciar o estilo dunha celda ca opción anunciar formato  (NVDA+f) e automáticamente se a opción Anunciar Estilo nas opcións de Formato de documento está activada. (#4213)
* Microsoft Powerpoint: cando se moven as formas dunha diapositiva cas teclas de flecha, agora anúnciase a ubicación actual da forma (#4214) incluíndo:
 * Anúnciase a distancia entre a forma e cada un dos bordes da diapositiva
 * Se a forma cubre ou está cuberta por outra forma, entón a distancia superposta, e a outra forma anúncianse.
 * Para anunciar esta información en calquera momento sen mover unha forma, preme a orden anunciar localización (NVDA+suprimir)
 * Ó seleccionar unha forma, se está cuberta por outra forma, anunciarase o estado oculto.
* A orden anunciar localización (NVDA+suprimir) é máis específica ó contexto nalgunhas situacións. (#4219):
 * Nos campos de edición estándar e no modo navegación, anúncianse a posición do cursor como unha porcentaxe do contido, e as súas cordinadas de pantalla .
 * En formas en presentacións de Powerpoint, anúnciase a posición da forma relativa á diapositiva  e outras formas.
 * Ó premer   esta orden dúas veces produciráse o vello comportamento do anunciado da información de localización para todo o control.
* Nova lingua: Catalán.

### Cambios

* Actualizado o transcriptor braille liblouis a 2.5.4. (#4103)

### Corrección de Fallos

* Nos navegadores Google Chrome e os baseados nél, certos anacos  de texto (como aqueles con énfase) xa non se repiten cando se anuncie o texto dunha alerta ou diálogo. (#4066)
* No modo navegación en aplicacións de Mozilla, ó premer intro sobre un botón, etc. xa non falla ó activalo (ou activa o control erróneo) en certos casos coma os botóns na parte superior do Facebook. (#4106)
* Xa non se anuncia información inútil ó tabular polo iTunes. (#4128)
* En certas listas en iTunes como a da música, ó moverse ó elemento seguinte utilizando a navegación de obxectos agora funciona correctamente. (#4129)
* Os elementos HTML considéranse cabeceiras  debido a que as marcas WAI ARIA agora están incluidas na lista de elementos do modo de navegación e a navegación rápida de documentos de Internet Explorer. (#4140)
* Ó seguir ligas á mesma páxina en versións recentes do Internet Explorer agora movémonos alí correctamente e anúnciase a posición de destiño nos documentos en modo navegación. (#4134)
* Microsoft Outlook 2010 e superior: mellórase todo o acceso ós diálogos seguros como os novos perfiles e caixas de diálogo de configuración de correo. (#4090, #4091, #4095)
* Microsoft Outlook: disminúese a verbosidade inútil das barras de Ferramentas de ordes cando se navega a través de certos diálogos. (#4096, #3407)
* Microsoft word: ó tabular por unha celda en branco nunha táboa xa non se anuncia incorrectamente saíndo de táboa. (#4151)
* Microsoft Word: O primeiro carácter máis aló do fin dunha táboa (incluíndo unha nova liña en branco), xa non se considera incorrectamente que está dentro da táboa. (#4152)
* Diálogo do corrector de ortografía do Microsoft Word 2010: Anuncia deletreando a palabra  real en lugar de só a primeira palabra  en negriña. (#3431)
* En modo navegación en Internet Explorer e outros controis MSHTML, ó tabular ou utilizar a navegación dunha soa tecla para moverte ós campos  de formulario anuncia a etiqueta de novo en moitos casos onde non debería (en concreto, cando se utilizan elementos da etiqueta HTML). (#4170)
* Microsoft Word: O anunciado sobre a existenza e ubicación dos comentarios é máis preciso. (#3528)
* Mellórase a navegación dalgunhas caixas de diálogo nos productos de MS Office como Word, Excel e Outlook xa non se anuncian  barras de ferramentas de control de contedores que non son útiles para o usuario. (#4198)
* Os paneis de tarefas como o administrador do portapapeis ou de recuperación de ficheiros xa non parecen obter o foco accidentalmente ó abrir unha aplicación como Microsoft Word ou Excel, o que ás veces provocaba que o usuario tivera que saír e voltar á aplicación para utilizar o documento ou folla de cálculo.  (#4199)
* NVDA xa non falla ó executarse nos últimos sistemas operativos Windows, se a lingua do Windows do usuario establécese en Serbio (Latino). (#4203)
* Ó premer o BloqueoNumérico mentras se estea no modo Axuda de Entrada agora conmutarase o bloqueoNumérico correctamente, en lugar de que o teclado e o sistema operativo se desincronicen con respecto ó estado desta tecla. (#4226)
* No Google Chrome, o título do documento anúnciase de novo ó cambiar as pestanas. No NVDA 2014.2, esto no ocurríu nalgúns casos. (#4222)
* No Google Chrome e navegadores baseados no Chrome, a URL do documento xa non se informa cando se anuncia o documento. (#4223)
* Ó executar ler todo co sintetizador Sen voz seleccionado (útil para realizar probas automatizadas), ler todo agora completarase en lugar de deterse tralas primeiras poucas liñas. (#4225)
* Diálogo Firmas de Microsoft Outlook: o campo de edición firma agora é accesible, o que permite o seguemento compreto do cursor e a detección do formato. (#3833)
* Microsoft Word: Ó ler a última liña dunha celda de táboa, xa non se le toda a celda da táboa. (#3421)
* Microsoft Word: Ó ler a primeira ou a última liña dunha táboa de índice, xa non se le toda a táboa de índice. (#3421)
* Ó falar palabras ó se escreber e nalgúns outros casos, as palabras xa non se separan incorrectamente en marcas como signos vocálicos e virama en linguas da India. (#4254)
* Os campos numéricos  de texto editable en GoldWave agora manéllanse correctamente. (#670)
* Microsoft Word: ó nos mover por parágrafo con control+flecha abaixo / control+flecha arriba, xa non é necesario premelos dúas veces se nos movemos por listas numeradas ou de viñetas. (#3290)

### Cambios para Desenvolvedores

* NVDA agora conta co apoio unificado de documentación para os complementos. Ver a sección de complementos da documentación da Guía do desenvolvedor para obter máis información. (#2694)
* Ó proporcionar  vínculos de xestos nun ScriptableObject a través de __gestures, agora é posible proporcionar a palabra chave None como o script. Esto lanza o xesto en calquera clase base. (#4240)
* Agora é posible cambiar a tecla de atallo utilizada para iniciar NVDA en traducións onde o atallo normal causa problemas. (#2209)
 * Esto faise a través de gettext.
 * Ten en conta que o texto para a opción Crear atallo de escritorio no diálogo Instalar NVDA, así coma o atallo de teclado na Guía do Usuario, tamén debe actualizarse.

## 2014.2

### Novas Características

* Agora é posible o anunciamento da selección do texto nalgúns campos de edición persoalizada onde se utiliza información da pantalla. (#770)
* En aplicacións  Java accesibles, agora anúnciase a información de posición para botóns de opción e outros controis que expoñan información de grupo. (#3754)
* En aplicacións Java accesibles, agora anúncianse os atallos de teclado para controis que os teñan. (#3881)
* No modo navegación, as etiquetas  nas rexións agora anúncianse. Tamén se inclúen no diálogo Lista de Elementos. (#1195)
* No modo navegación, as rexións etiquetadas agora trátanse como rexións. (#3741)
* En documentos e aplicacións en Internet Explorer, as rexións activas (parte do W3c ARIA standard) agora sopórtanse, permitindo así ós autores web  marcar contido particular para que se fale de xeito automático segundo cambie. (#1846)

### Cambios

* Ó saír dun diálogo ou aplicación dentro dun documento en modo navegación, o nome e tipo do documento en modo navegación xa non se anuncia. (#4069)

### Corrección de Fallos

* O menú estándar de sistema de Windows xa non se silencia accidentalmente en aplicacións Java. (#3882)
* Cando se copie texto dende a revisión de pantalla, os saltos de liña xa non se ignoran. (#3900)
* Os obxectos de espazo en branco sen sentido xa non se anuncian nalgunhas aplicacións cando o foco  cambie ou cando se utilice a navegación de obxectos ca revisión simple habilitada. (#3839)
* As caixas de mensaxe e outros diálogos producidos polo NVDA causan novamente a cancelación da fala anterior antes de anunciar o diálogo.
* No modo navegación, as etiquetas de controis como ligas e botóns agora procésanse correctamente cando a etiqueta se reemplazara polo autor con fins de accesibilidade (específicamente, a utilización de aria-label ou de aria-labelledby). (#1354)
* No modo Navegación  en Internet Explorer, o texto contido dentro dun elemento marcado como presentación (aria-presentation) xa non se ignora inapropriadamente. (#4031)
* Agora é posible de novo teclear texto en vietnamita utilizando o programa Unikey. Para facer esto, desmarca a caixa de verificación Manexar teclas desde outras aplicacións, añadido ó diálogo Opcións de Teclado de NVDA. (#4043)
* No modo navegación, os elementos de menú verificables e de opción anúncianse como controis en lugar de como texto se pode facer clic. (#4092)
* NVDA xa non cambia incorrectamente dende modo foco a modo navegación cando está enfocado un elemento de menú de opción ou verificable. (#4092)
* En Microsoft PowerPoint con falar palabras ó escreber habilitado, os carácteres eliminados co retroceso xa non se anuncian como parte da palabra escrebida. (#3231)
* Nos diálogos de opcións de Microsoft Office 2010, as etiquetas das caixas combinadas anúnncianse correctamente. (#4056)
* No modo navegación en aplicacións de Mozilla, a utilización de ordes de navegación rápida para moverse ó botón ou ó ccampo de edición seguinte ou anterior agora inclúe botóns conmutables como se esperaba. (#4098)
* O contido de alertas en aplicacións Mozilla xa non se anuncia dúas veces. (#3481)
* En modo navegación, os contedores  e rexións xa non se repiten inapropriadamente mentras se navega dentro deles ó mesmo tempo que o contido da páxina está a cambiar (por exemplo ó navegar polos sitios web de Facebook e Twitter). (#2199)
* NVDA recupérase en máis casos ó cambiar dende as aplicacións que deixan de responder. (#3825)
* O cursor (punto de inserción) actualízase correctamente de novo cando se da unha orde falarTodo mentras se está en texto editable dibuxado directamente na pantalla. (#4125)

## 2014.1

### Novas Características

* Soporte para o Microsoft PowerPoint 2013. Ten en conta que a Vista protexida non está soportada. (#3578)
* No Microsoft word e Excel, NVDA agora pode ler o símbolo selecionado cando se escollan símbolos utilizando o diálogo Insertar Símbolos. (#3538)
* Agora é posible escoller se o contido nos documentos debería identificarse  como cliqueable, a través dunha nova opción no diálogo Formateado de Documentos. Esta opción está activada por defecto (comportamento anterior). (#3556)
* Soporte para as pantallas braille conectadas a través do Bluetooth nun computador executando o  Software de Widcomm Bluetooth. (#2418)
* Cando se edita texto no PowerPoint, agora anúncianse os hipervínculos. (#3416)
* Cando se estea en aplicacións ARIA ou diálogos na web, agora é posible forzar ó NVDA para que cambie a modo navegación con NVDA+espazo seguindo a navegación de estilos de documento da aplicación ou do diálogo. (#2023)
* No Outlook Express / Windows Mail / Windows Live Mail, NVDA agora anuncia se unha mensaxe ten un adxunto ou está marcado. (#1594)
* Ó navegar por táboas en aplicacións Java accesibles, agora anúncianse as coordinadas de fila e columna, incluindo  as cabeceiras de columna e  fila se existen. (#3756)

### Cambios

* Para as pantallas braille Papenmeier, eliminouse a orde mover a revisión plana/foco. Os usuarios poden asignar as súas proprias teclas usando o diálogo de Xestos de entrada. (#3652)
* NVDA agora baséase na versión 11 do Microsoft VC runtime, o que significa que xa non se pode executar en sistemas operativos anteriores ó Windows XP Service Pack 2 ou Windows Server 2003 Service Pack 1.
* No nivel de puntoación Algunha agora falaránse os caracteres asterisco(*) e máis (+). (#3614)
* Actualizado eSpeak á versión 1.48.04, que inclúe moitas correccións de lingua e corrixe varios problemas. (# 3842, # 3739)

### Corrección de Fallos

* Cando te movas ou seleciones  celdas no Microsoft Excel, NVDA xa non debería  anunciar inapropriadamente a antiga celda en lugar da nova celda cando Microsoft Excel estea lento ó mover a seleción. (#3558)
* NVDA manella adecuadamente a apertura dunha lista despregable nunha celda no Microsoft Excel mediante o menú contextual. (#3586)
* Agora amósase apropriadamente o Novo contido da páxina nas páxinas da tenda en iTunes 11 en modo navegación cando se siga unha liga na tenda ou ó abrir a tenda inicialmente. (#3625)
* Os botóns para a vista previa das cancións na tenda de iTunes 11 agora amosan a súa etiqueta en modo navegación. (#3638)
* No modo navegación en Google Chrome, as etiquetas das caixas de verificación e dos botóns de opción agora procésanse correctamente. (#1562)
* En Instantbird, NVDA xa non anuncia información inútil cada vez que te movas a un contacto da lista de contactos. (#2667)
* En modo navegación no Adobe Reader, agora procésase o texto correcto para os botóns, etc. Onde a etiqueta reemplazouse polo uso dun tooltip ou outro recurso. (#3640)
* En modo navegación no Adobe Reader, os gráficos extranos que conteñen o texto "mc-ref" xa non se procesan. (#3645)
* NVDA xa non anuncia todas as celdas no Microsoft Excel como subliñadas na súa información de formato. (#3669)
* Xa non se amosan caracteres sen sentido en documentos de modo navegación como os que se atopan no rango de uso privado do Unicode. Nalgúns casos estos detiñan o amosado de etiquetas máis útiis. (#2963).
* A composición de entrada para a introducción de caracteres do este asiático xa non falla en PuTTY (#3432)
* ó navegar por un documento despois dunha cancelación de falar todo xa non resulta en que NVDA anuncie ás veces incorrectamente que se abandonou un campo (como unha táboa) máis abaixo no documento no que falar todo nunca estivo falando en realidade (#3688)
* Cando se utilicen ordes rápidas do modo navegación mentres se estea en falar todo ca lectura superficial activada, NVDA anuncia con máis precisión o novo campo (por exemplo, agora di que unha cabeceira é unha cabeceira, e non só o texto). (#3689)
* No salto ó final ou ó comezo dun contedor as ordes de navegación rápida agora afectan á opción lectura superficial durante falar todo (é dicir, que xa non cancelarán o falar todo actual). (#3675)
* Os nomes dos xestos táctiles listados no diálogo Xestos de entrada do NVDA agora son máis amigables e están traducidos. (#3624)
* NVDA xa non fai que certos programas se bloqueen cando se mova o punteiro do rato sobre os seus controis de edición enriquecidos (TRichEdit). Programas incluíndo Jarte 5.1 e BRfácil. (#3693, #3603, #3581)
* No Internet Explorer e outros controis MSHTML, os contedores como táboas marcadas como presentación por ARIA xa non se informan ó usuario. (#3713)
* No Microsoft Word, NVDA xa non repite de xeito inapropriado a fila da táboa e a información da columna dunha celda nunha pantalla braille
* En linguas que utilicen  un espazo como un díxito separador de grupos de milleiros  como no  Francés e no Alemán, os números de anacos separados de texto xa non se pronuncian como un so número. Esto era particularmente problemático  para as celdas de táboa que contiñan números. (#3698)
* O braille xa non falla ás veces ó se actualizar cando se move o cursor do sistema no Microsoft Word 2013. (#3784)
* Cando se estea posicionado sobre o primeiro carácter dunha cabeceira no Microsoft Word, o texto comunícase como unha cabeceira  (incluindo o nivel) e xa non desaparece dunha pantalla braille. (#3701)
* Cando se dispara un perfil de configuración por unha aplicación e esa aplicación se pecha, NVDA xa non falla ás veces ó desactivar o perfil. (#3732)
* Cando se escribe ca entrada Asiática nun control dentro do proprio NVDA (ex.: no diálogo Buscar no modo navegación), "NVDA" xa non se anuncia incorrectamente en lugar do candidato. (#3726)
* Agora anúncianse as pestanas no diálogo Opcións do Outlook 2013. (#3826)
* Mellorado o soporte  para  rexiones ARIA live en Firefox e outras aplicacións Gecko de Mozilla:
 * Soporte para actualizacións aria-atomic e filtrado de actualizacións aria-busy (#2640)
 * Inclúese o texto alternativo (como o atributo alt ou aria-label) se non hai outro texto útil. (#3329)
 * As actualizacións Live region xa non se silencian se se producen ó mesmo tempo que o desprazamento do foco. (# 3777)
* Certos elementos de presentación en Firefox e outras aplicacións  Gecko de Mozilla xa non se amosan inapropriadamente en modo navegación (expresamente cando o elemento se marcóu con aria-presentation pero tamén é enfocable). (#3781)
* Mellora do rendemento ó navegar por un documento en Microsoft Word ca corrección ortográfica activada. (#3785)
* Varias correccións ó soporte para aplicacións Java accesibles:
 * O control inicialmente enfocado nun marco ou  diálogo xa non falla ó se anunciar cando o marco ou diálogo pasa a primeiro prano. (#3753)
 * Xa non se anuncia información de posición inútil para os botóns de opción (por exemplo 1 de 1). (# 3754)
 * Mellor anunciado dos controis JComboBox (xa non se anuncia html, unha mellor información dos estados expandidos e colapsados). (#3755)
 * Inclúese máis texto nos cálculos automáticos de título de diálogo. (# 3857)
 * Os cambios do  nome, valor ou descripción do control enfocado agora anúncianse con maior precisión. (#3770)
* Arránxase un colgue no NVDA visto en Windows 8 ó se enfocar certos controis RichEdit que conteñen grandes cantidades de texto(por exemplo no Visualizador do rexistro de NVDA, windbg). (#3867)
* Nos sistemas cunha configuración de pantalla de alta DPI (que se produce de forma predeterminada para moitas pantallas modernas), NVDA xa non leva o rato ó lugar equivocado nalgunhas aplicacións. (#3758, #3703)
* Arranxouse un problema ocasional ó navegar pola web onde NVDA deixaba de funcionar correctamente ate que se reiniciaba, a pesares de que non se bloqueaba ou se conxelaba. (# 3804)
* Agora pódeSe utilizar unha pantalla bralle Papenmeier incluso se nunca se conectara a través de USB. (# 3712)
* NVDA xa non se  colga cando os modelos antigos das pantallas braille Papenmeier BRAILLEX se seleccionan sen unha pantalla conectada.

### Cambios para Desenvolvedores

* Os AppModules agora conteñen as propriedades productName e productVersion. Esta información tamén se inclúe agora na Información do desenvolvedor (NVDA+f1). (#1625)
* Na consola de Python, agora podes premer  a tecla tab para completar o identificador actual. (#433)
 * Se hai varias posibilidades, podes premer o tabulador por segunda vez para escoller de entre unha lista.

## 2013.3

### Novas Características

* Os campos de formulario  agora anúncianse nos documentos de Microsoft word. (#2295)
* O NVDA agora pode anunciar información de revisión en Microsoft Word cando o seguemento de cambios estea activado. Ten en conta que Anunciar revisións do editor no diálogo opcións de documentos de NVDA (desactivado por omisión) debe estar habilitado tamén para que se anuncien. (#1670)
* As listaxes despregables no Microsoft Excel 2003 ó 2010 agora anúncianse cando se abran e naveguen. (#3382)
* Unha nova opción 'Permitir Lectura superficial en falar Todo' no diálogo Opcións de Teclado permite a navegación por un documento cas ordes de navegación rápida do modo navegación e movementos de liña / parágrafo, mentres permañece lendo todo. Esta opción está desactivada de maneira predeterminada. (#2766)
* Agora hai un diálogo Xestos de Entrada para permitir a persoalización sinxela dos xestos de entrada(como teclas no teclado) para ordes do NVDA. (#1532)
* Agora podes ter diferentes opcións para diferentes situacións utilizando perfiles de configuración. Os perfiles pódense activar de xeito manual ou automático (ex.: para unha aplicación en particular). (#87, #667, #1913)
* No Microsoft Excel, as celdas que son ligas agora anúncianse como ligas. (#3042)
* No Microsoft Excel, agora anúnciase ó usuario a existencia de comentarios nunha celda. (#2921)

### Corrección de fallos

* Zend Studio agora funciona igual que Eclipse. (#3420)
* O cambio de estado de certas caixas de verificación no diálogo de regras de correo do Microsoft Outlook 2010 agora anúnciase automáticamente. (#3063)
* NVDA agora anunciará o estado fixado para controis fixos como  pestanas en Mozilla Firefox. (#3372)
* Agora é posible vincular scripts a xestos de teclado que conteñan as teclas Alt e/ou Windows como modificadoras. Anteriormente, se se facía esto, a execución do script causaba a activación do menú Inicio ou da barra de menú. (#3472)
* Ó seleccionar texto en documentos en modo navegación (por exemplo ó utilizar control+shift+fin) xa non causa que se cambie a distribución de teclado en sistemas con varias distribucións de teclado instaladas. (#3472)
* Internet Explorer xa non debería colgarse ou voltarse inusable  cando se pecha NVDA. (#3397)
* O movemento físico e outros eventos nalgúns ordenadores modernos xa  non se trata como pulsacións de teclas inapropriadas. Anteriormente, esto silenciaba a voz e algunhas veces facía funcionar ordes do NVDA. (#3468)
* NVDA agora compórtase como se esperaba enPoedit 1.5.7. os usuarios que utilicen versións anteriores necesitarán actualizar. (#3485)
* NVDA agora pode ler documentos protexidos en Microsoft Word 2010,  non causando xa que Microsoft Word se bloquee. (#1686)
* Se se da un parámetro de línea de comando descoñecido ó executar o paquete de distribución de NVDA, xa non se provoca un bucle sen fin de diálogos de mesaxes de erro. (# 3463)-
* NVDA xa non falla ó anunciar o texto alternativo dos gráficos e obxectos en Microsoft Word se o texto alternativo contén comiñas ou outros caracteres non estándar. (#3579)
* O número de elementos de certas listas horizontais en modo navegación agora está correcto. Anteriormente podía ter sido o doble da cantidade real. (#2151)
* Ó premer control+e nunha folla de cálculo de Microsoft Excel, agora anunciarase a selección actualizada. (#3043)
* NVDA agora pode ler correctamente os documentos XHTML en Microsoft Internet Explorer e outros controis MSHTML. (#3542)
* Diálogo de Opcións de teclado: se non se seleccionou ningunha tecla para ser utilizada como a tecla NVDA, preséntase un erro ó usuario cando se descarte o diálogo. Polo menos unha das teclas debe ser seleccionada para o uso apropriado do NVDA. (#2871)
* No Microsoft Excel, NVDA agora anuncia celdas fusionadas de xeito diferente ás múltiples celdas seleccionadas. (#3567)
* El cursor de modo navegación  ya no se coloca incorrectamente cuando se abandona un diálogo o aplicación dentro del documento. (#3145)
* Solucionouse un problema polo que o controlador das pantallas braille series da HumanWare Brailliant BI / B non se presenta como unha opción na caixa de diálogo Opcións de Braille nalgúns sistemas, a pesares de que dita pantalla se conecte a través do USB.
* NVDA xa non falla  ó cambiar a revisión de pantalla cando o navegador de obxectos non teña ningunha ubicación real na pantalla. Neste caso o cursor de revisión agora colócase na parte superior da pantalla. (#3454)
* Solucionouse un problema polo que o controlador da pantalla braille de Freedom Scientific falla cando o porto establécese en USB, nalgunhas circunstancias. (#3509, #3662)
* Solucionouse un problema polo que non se detectaron teclas en braille de Freedom Scientific nalgunhas circunstancias. (#3401, #3662)

### Cambios para Desenvolvedores

* Podes especificar a categoría a ser amosada ó usuario polos scripts utilizando o atributo scriptCategory en clases ScriptableObject e o atributo category en métodos de script. Mira a documentación para baseObject.ScriptableObject para máis detalles. (#1532)
* config.save está en desuso e pode eliminarse en futuras versións. Utiliza config.conf.save no seu lugar. (#667)
* config.validateConfig está en desuso e pode eliminarse en futuras versións. Os complementos que necesiten esto deben proporcionar a súa propria implementación. (#667, #3632)

## 2013.2

### Novas Características

* Soporte para o Chromium Embedded Framework, que é un control de navegador web utilizado en varias aplicaciones. (#3108)
* Nova variante de voz de eSpeak: Iven3.
* No Skype, anúncianse automáticamente as mesaxes novas do chat mentras a conversación estea enfocada. (#2298)
* Soporte para o Tween, incluindo o anunciado dos nomes de pestana e menor nivel de detalle cando se lean os twits.
* Agora podes deshabilitar o amosado das mesaxes do NVDA nunha pantalla braille configurando a duración da mesaxe a 0 no diálogo de Opcións de Braille. (#2482)
* No administrador de complementos, agora hai un botón Obter Complementos para abrir o sitio web dos Complementos do NVDA onde podes examinar y descargar os complementos dispoñibles. (#3209)
* No diálogo de benvida do NVDA que sempre aparece a primeira vez que  executas o NVDA, agora podes especificar se NVDA se inicia automáticamente despois de autentificarte no Windows. (#2234)
* O modo silencioso habilítase automáticamente cando se utilice Dolphin Cicero. (#2055)
* Agora sopórtase a versión Windows x64 do Miranda IM/Miranda NG. (#3296)
* Agora anúncianse automáticamente as suxerencias de busca na pantalla de inicio do  Windows 8.1. (#3322)
* Soporte para navegar e editar follas de cálculo en Microsoft Excel 2013. (#3360)
* As pantallas braille Freedom Scientific Focus 14 Blue e Focus 80 Blue, así como a Focus 40 Blue en certas configuracións que non se soportaba previamente, agora sopórtanse cando se conecten a traverso do Bluetooth. (#3307)
* Agora anúncianse as suxerencias de Autocompletado en Outlook 2010. (#2816)
* Novas táboas de transcripción braille: Braille computerizado Inglés (U.K.), Coreán grao 2, braille ruso para código informático.
* Nova lingua: Farsi. (#1427)

### Cambios

* nunha pantalla tactil, realizando un deslizamento cun so dedo cara a esquerda ou cara a dereita cando se estea en modo obxecto, agora móveste cara atrás ou adiante por  todos os obxectos e non só por aqueles que estean no mesmo contedor. Utiliza  un deslizamento con 2 dedos cara a esquerda ou cara a dereita para realizar a acción orixinal de anterior/seguinte obxecto limitado ó actual contedor.
* A caixa de verificación Anunciar táboas de deseño que se atopa no diálogo Opcións do Modo Navegación  agora renomeouse como Incluir Táboas de Deseño para reflectir que a navegación rápida non as localizará se a caixa está desmarcada. (#3140)
* A revisión cha foi reemplazada polos modos de revisión de obxectos, documentos e pantalla. (#2996)
 * A revisión de obxectos revisa o texto só dentro do navegador de obxectos, a revisión de documentos revisa todo o texto nun documento en modo navegación (se hai algún) e a revisión de pantalla revisa o texto na pantalla para a aplicación actual.
 * As ordes que anteriormente movían cara ou dende revisión plana agora cambian entre estos novos modos de revisión.
 * O navegador de obxectos segue automáticamente ó cursor de revisión de tal maneira que segue sendo o obxecto máis profundo na posición do cursor de revisión cando se está en modos de revisión de documentos ou de pantalla.
 * Despois de cambiar a modo revisión de pantalla, NVDA permanecerá neste modo hate que voltes explícitamente ós modos de revisión de documentos ou de obxectos.
 * Cando se estea en modo de revisión de documentos ou de obxectos, NVDA poderá cambiar automáticamente entre estos dous modos dependendo de se estás movéndote por un documento do modo navegación ou non.
* Actualizado o transcriptor braille liblouis a 2.5.3. (#3371)

### Corrección de Fallos

* A activación dun obxecto agora anuncia a acción antes da activación, en lugar da acción despois da activación (ex.: expandir cando se expande en lugar de contraer). (#2982)
* Unha lectura e seguemento do cursor máis precisos en diversos campos de entrada para as últimas versións de Skype, como chat e campos de busca. (#1601, #3036)
* Na lista de conversacións recentes de Skype, o número de novos eventos agora lese en cada conversación, se procede. (#1446)
* Melloras no control do cursor e a orde de lectura de texto de dereita a esquerda na pantalla. Ex.: Edición de texto en árabe no Microsoft Excel. (#1601)
* A navegación rápida en botóns e campos de formulario agora localizará as ligas marcadas como botóns para propósitos de accesibilidade en Internet Explorer. (#2750)
* No modo navegación, o contido no interior das vistas en árbore xa non se procesa como unha representación cha, non é útil. Puedes premer Intro sobre unha vista en árbore para  interactuar con ela no  modo foco. (#3023)
* Ó Premer alt+frecha abaixo ou alt+frecha arriba para expandir unha caixa combinada mentres se estea no modo foco xa non cambia incorrectamente a modo navegación. (#2340)
* En Internet Explorer 10, as celdas da táboa xa non activan o modo foco, a menos que se fixeran enfocables explícitamente polo autor da web (#3248)
* NVDA xa non falla ó arrancar se a hora do sistema é anterior á última revisión dunha actualización. (#3260)
* Se unha barra de progreso se amosa nunha pantalla Braille, o Braille actualízase cando cambie a barra de progreso. (#3258)
* En modo navegación en aplicacións de Mozilla, os títulos das táboas xa non se procesan dúas veces. Ademáis, o índice procésase cando hai tamén un título. (#3196)
* Ó cambiar a lingua de entrada de Windows 8, NVDA agora fala na lingua correcta en lugar de na anterior.
* NVDA agora anuncia cambios no modo de conversión de IME en Windows 8.
* NVDA xa non anuncia lixo no escritorio cando os métodos de entrada xaponeses Google ou IME ATOK están en uso. ;(# 3234)
* En Windows 7 e superiores, NVDA xa non anuncia indebidamente o recoñecemento de voz ou a entrada táctil como un cambio de lingua do teclado.
* NVDA xa non anuncia un carácter especial (0x7f) cando se prema control+retroceso en algúns editores mentres Falar Caracteres ó Escreber estea habilitado. (#3315)
* espeak xa non fai cambios inapropriados no ton, volume, etc. cando NVDA lea texto que conteña certos caracteres de control ou XML. (#3334) (regresión de #437)
* En aplicacións Java, os cambios no nivel ou no valor do control enfocado agora anúncianse automáticamente, e reflíctense ca subsiguinte saída do control. (#3119)
* En controis Scintilla, as liñas agora anúncianse correctamente cando o corte de palabras está habilitado. (#885)
* En aplicacións de Mozilla, o nome dos elementos de lista de só lectura agora anúnciase correctamente; ex.: cando se navega por twits no modo foco en twitter.com. (#3327)
* Nos diálogos de Confirmación en Microsoft Office 2013 agora lese o seu contido automáticamente cando aparezan.
* Melloras no rendemento cando se navega por certas táboas en Microsoft Word. (#3326)
* As ordes de navegación de táboas de NVDA (control+alt+flechas) funcionan mellor nalgunhas táboas de Microsoft Word cando unha celda abrangue varias filas.
* Se o administrador de complemenhtos está xa aberto, activalo de novo (ou dende o menú Ferramentas ou abrindo un ficheiro de complemento) xa non falla ou non imposibilita pechar dito administrador de complementos. (#3351)
* NVDA xa non se colga en certos diálogos cando se estea utilizando o IME no Office 2010 co Xaponés ou o chinés. (#3064)
* Os espazos múltiples xa non se comprimen a un so espazo nas pantallas braille. (#1366)
* As Zend Eclipse PHP Developer Tools agora funcionan igual que o Eclipse. (#3353)
* En Internet Explorer, xa non é necesario premer de novo tab para interactuar cun obxecto integrado (como o contido Flash) despois de premer intro sobre el. (#3364)
* Ó editar texto no Microsoft PowerPoint, a última liña xa non se presenta como a liña anterior se a última liña está en branco. (#3403)
* No Microsoft PowerPoint, os obxectos xa non  se falan ás veces  dúas veces cando os seleccionas ou escolles para editar. (#3394)
* O NVDA xa non causa que o Adobe Reader se bloquee ou se colgue para certos documentos PDF mal formados que conteñan filas fora das táboas. (#3399)
* NVDA agora detecta correctamente a seguinte diapositiva co foco cando se elimine unha na  vista de miniaturas no Microsoft PowerPoint. (#3415)

### Cambios para Desenvolvedores

* Engadiuse windowUtils.findDescendantWindow para procurar unha xanela descendente (HWND) localizando a visivilidade especificada, identificador do control e/ou nome da clase.
* A consola de python remota xa non espera despois de 10 segundos mentres agarda pola entrada. (#3126)
* A inclusión do módulo bisect en compilacións binarias está en desuso e poderá eliminarse nunha versión futura. (#3368)
 * Os complementos que dependan de bisect (incluindo o módulo urllib2) deberían actualizarse para incluir este módulo.

## 2013.1.1

Esta versión corrixe o problema onde o NVDA se colgaba ó iniciarse se se configuraba para utilizar a lingua irlandesa, así como inclúe actualizacións para traduccións e algunhas outras correccións de erros.

### Corrección de Erros

* Prodúcense caracteres correctos cando se teclean na propria interfaz do NVDA mentres se utiliza  un método de entrada Coreano ou Xaponés mentres sexa o método predeterminado. (#2909)
* En Internet Explorer e outros controis MSHTML, os campos marcados como contendo unha entrada inválida agora manéxanse correctamente. (#3256)
* NVDA xa non se colga cando se iniciou se se configurou para utilizar o idioma irlandés.

## 2013.1

O máis subliñable nesta versión inclúe unha distribución de teclado portátil máis intuitiva e consistente; soporte básico para o Microsoft PowerPoint; soporte para descripcións longas en navegadores web; e soporte para a entrada de braille computerizado para liñas braille que teñan un teclado braille.

### Importante

#### Nova Distribución Teclado Portátil

A distribución de teclado portátil redeseñouse por completo para facela máis intuitiva e consistente.
A nova distribución utiliza as teclas do cursor en combinación ca tecla NVDA e outras modificadoras para ordes de revisión.

Por favor ten en conta os seguintes  cambios para ordes comúnmente utilizadas:

| Nome |Tecla|
|---|---|
|Ler todo |NVDA+a|
|Ler liña actual |NVDA+l|
|Ler selección de texto actual |NVDA+shift+s|
|Anunciar barra de estado |NVDA+shift+fin|

Ademáis, entre outros cambios, variaron as ordes para toda a navegación de obxectos, revisión de texto, clic do rato e grupos de opcións do sintetizador.
Por favor mira o documento [Referencia Rápida de Ordes](keyCommands.html) para as novas teclas.

### Novas Características

* Soporte básico para editar e ler presentacións de Microsoft PowerPoint. (#501)
* Soporte básico para ler e escreber mensaxes en Lotus Notes 8.5. (#543)
* Soporte para o cambio automático de lingua cando se lean documentos no Microsoft Word. (#2047)
* No modo Navegación para MSHTML (ex.: Internet Explorer) e Gecko (ex.: Firefox), agora anúnciase a existencia de descripcións longas. Tamén é posible abrir a descripción longa nunha xanela nova premendo NVDA+d. (#809)
* As notificacións en Internet Explorer 9 e superior agora fálanse (como contido bloqueado ou descargas de ficheiros). (#2343)
* O anunciado automático das cabeceiras de fila e columna agora sopórtase para documentos en modo navegación en Internet Explorer e outros controis MSHTML. (#778)
* Novas linguas: Aragonés, irlandés.
* Novas táboas de transcripción braille:  Danés grado 2, Coreano grao 1.
* Soporte para liñas braille conectadas a traverso do bluetooth nun ordenador executando o Bluetooth Stack for Windows de Toshiba. (#2419)
* Soporte para a selección de porto cando se utilicen liñas freedom Scientific (Automático, USB ou Bluetooth).
* Soporte para a familia BrailleNote de anotadores electrónicos de Humanware cando actúen como unha terminal braille para un lector de pantalla. (#2012)
* Soporte para  modelos antigos das liñas braille Papenmeier BRAILLEX. (#2679)
* Soporte para a entrada de braille computerizado  para liñas braille que posúan un teclado braille. (#808)
* Novas opcións de teclado que permiten  escoller se NVDA debería interrumpir a fala para os caracteres escribidos e/ou a tecla Intro. (#698)
* Soporte para varios navegadores web baseados no Google chrome: Rockmelt, BlackHawk, Comodo Dragon e SRWare Iron. (#2236, #2813, #2814, #2815)

### Cambios

* Actualizado o transcriptor braille liblouis ó 2.5.2. (#2737)
* A distribución de teclado portátil redeseñouse  por completo para facela máis intuitiva e consistente. (#804)
* Actualizado o sintetizador de voz eSpeak a 1.47.11. (#2680, #3124, #3132, #3141, #3143, #3172)

### Corrección de Fallos

* As teclas de navegación rápida para brincar ó seguinte ou anterior separador en modo Navegación agora funcionan en Internet Explorer e outros controis MSHTML. (#2781)
* Se o NVDA se cambia a eSpeak debido a que o sintetizador de voz configurado falla cando NVDA arrinca, o sintetizador configurado xa non se deixa automáticamente na opción de eSpeak. Esto significa que agora, o sintetizador orixinal será probado de novo a próxima vez que NVDA arrinque. (#2589)
* Se o NVDA se cambia a sen braille debido a que a liña braille configurada  falla cando NVDA arrinca, a liña configurada xa non se deixa automáticamente na opción de sen braille. Esto significa que agora, a liña orixinal será probada de novo a próxima vez que NVDA arrinque. (#2264)
* No modo navegación en aplicacións de Mozilla, as actualizacións das táboas agora procésanse correctamente. Por exemplo, en actualización de celdas, as cordinadas de fila e columna anúncianse e a navegación da táboa funciona como debería. (#2784)
* No modo navegación en navegadores web, certos gráficos cliqueables non etiquetados que non se procesaban anteriormente agora procésanse correctamente. (#2838)
* As versións anteriores e actuais do SecureCRT (como a 6.1.1) agora sopórtanse. (#2800)
* Para métodos de entrada como Easy Dots IME baixo XP, a cadea de lectura agora anúnciase correctamente.
* A lista de candidatos do método de entrada Chinés Simplificado Microsoft Pinyin baixo Windows 7 agora lese correctamente cando se cambian páxinas cas flechas esquerda e dereita, e cando se abre primeiro con Inicio.
* Cando se garda a información de pronunciación persoalizada de símbolos , o campo avanzado "preserve" xa non se elimina. (#2852)
* Cando se desactiva a detección automática de actualizacións, NVDA xa non ten de reiniciarse para que todos os cambios teñan efecto.
* NVDA xa non falla ó iniciarse se un complemento non se pode eliminar debido a que o seu directorio está a ser utilizado actualmente por outra aplicación. (#2860)
* As etiquetas de pestanas no diálogo de preferencias do DropBox agora poden verse ca Revisión Cha.
* Se a lingua de entrada se cambia a algúnha outra que a predeterminada, NVDA agora detecta as teclas correctamente para ordes e o modo de axuda de entrada.
* Para linguas como a alemana onde o signo + (máis) é unha  tecla soa no teclado, agora é posible vincularlle ordes utilizando a palabra "plus". (#2898)
* En Internet Explorer e outros controis  MSHTML, as comiñas agora anúncianse onde proceda. (#2888)
* O controlador das liñas HumanWare Brailliant BI/Bbraille agora pode  seleccionarse cando a liña estea conectada a través do Bluetooth pero nunca se conectaran a través do USB.
* O filtrado de elementos na Lista de Elementos do modo navegación co filtro de texto en maiúsculas agora devolve resultados non sensibles ás maiúsculas igual que nas minúsculas en lugar de nada en absoluto. (#2951)
* Nos navegadores de Mozilla, o modo navegación pode utilizarse de novo cando se enfoque contido Flash. (#2546)
* Cando se utilice unha táboa de braille contraído e estea habilitada a opción expandir a braille computerizado para a palabra no cursor , o cursor braille agora colócase correctamente cando se atope despóis dunha palabra onde un carácter se  represente con varias celdas braille (ex.: signo de maiúsculas, signo de diálogo, signo de número, etc.). (#2947)
* A selección do texto agora amósase correctamente nunha liña braille en aplicacións como controis de edición de Microsoft word 2003 e Internet Explorer.
* É posible de novo seleccionar texto nunha dirección cara atrás en Microsoft Word mentres estea habilitado o Braille.
* Cando se estea en revisión,  eliminando caracteres co retroceso ou suprimir en controis de edición de Scintilla, NVDA anuncia correctamente caracteres multibyte. (#2855)
* NVDA xa non fallará ó instalar cando a ruta do perfil do usuario conteña certos caracteres multibyte. (#2729)
* O anunciado de grupos para controis Vista de Lista (SysListview32) en aplicacións de 64 bit xa non causa un erro.
* No modo navegación nas aplicacións de Mozilla, o contido de texto xa non se trata incorrectamente como editable nalgúns casos extranos. (#2959)
* No IBM Lotus Symphony e no OpenOffice, movendo o cursor do sistema agora móvese o cursor de revisión se procede.
* O contido do Adobe Flash agora é accesible en Internet Explorer en Windows 8. (#2454)
* Correxido o soporte Bluetooth para a Papenmeier Braillex Trio. (#2995)
* Correxida a incapacidade para utilizar certas voces de Microsoft Speech API versión 5 como as voces de Koba Speech 2. (#2629)
* En aplicacións que utilicen o Java Access Bridge, agora as liñas braille actualízanse correctamente cando o cursor se mova en campos de texto editables . (#3107)
* Sopórtase a rexión en formulario en modo navegación en documentos que soporten rexións. (#2997)
* O controlador do sintetizador de voz eSpeak agora manexa a lectura por caracteres máis apropriadamente (ex.: anuncia un nome de letra extranxeiro ou un valor en lugar de só o seu son ou nome xenérico). (#3106)
* NVDA xa non falla ó copiar as opcións do usuario para utilizalas na autentificación e noutras pantallas seguras cando a ruta do perfil do usuario contén caracteres non ASCII. (#3092)
* NVDA xa non se bloquea cando se utiliza a entrada de caracteres asiáticos nalgunhas aplicacións .NET. (#3005)
* Agora é posible utilizar o modo navegación para páxinas en Internet Explorer 10 cando se estea no modo estándar; ex.: [www.gmail.com](http://www.gmail.com) login page. (#3151)

### Cambios para Desenroladores

* Os controladores de liña Braille agora poden soportar a selección manual de portos. (#426)
 * Esto é maioritariamente útil para liñas braille que soporten conexión a traverso dun porto serie.
 * Esto faise utilizando o método da clase getPossiblePorts na clase BrailleDisplayDriver.
* Agora sopórtase a entrada braille  dende teclados braille. (#808)
 * A entrada braille abránguese pola crase brailleInput.BrailleInputGesture ou unha subcrase da mesma.
 * As subcrases de braille.BrailleDisplayGesture (segundo se implementaron nos controladores das liñas braille) tamén poden herdar de brailleInput.BrailleInputGesture. Esto permite amosar ordes  e que a entrada braille se manelle pola mesma crase gesture.
* Agora podes utilizar comHelper.getActiveObject para conseguer un obxecto COM activo dende un proceso normal cando NVDA estea executándose co privilexio UIAccess. (#2483)

## 2012.3

O subliñable desta versión inclúe o soporte para a entrada de caracteres asiáticos; soporte experimental para pantallas tactiles en Windows 8; anunciado de números de páxina e soporte mellorado para táboas en Adobe Reader; ordes de navegación de táboa en filas de táboa enfocadas e controis de vista en lista de Windows; o soporte para algunhas liñas braille máis; e cabeceiras de columna no Microsoft Excel.

### Novas Características

* NVDA agora pode soportar entrada de caracteres asiáticos utilizando IME e métodos de servicio de entrada de texto en todas as aplicacións, incluindo:
 * anunciado e navegación de listas candidatas;
 * Anunciado e navegación de cadeas de composición; e
 * Anunciado de lectura de cadeas.
* A presenza de subliñados e tachados agora anúnciase nos documentos de Adobe Reader. (#2410)
* Cando a función Windows Sticky Keys está activada, a tecla modificadora de NVDA agora comportarase como as outras teclas modificadoras. Esto permíteche utilizar a tecla modificadora do NVDA sen a necesidade de manter premeda mentres premes outras teclas. (#230)
* Agora sopórtase o anunciado automático de cabeceiras de columna e de fila no Microsoft Excel. Preme NVDA+shift+c para configurar a fila que conteña cabeceiras de columna e NVDA+shift+r para a columna que conteña cabeceiras de fila. Preme o script dúas veces en sucesión rápida para limpiar a opción. (#1519)
* Soporte para as liñas braille HIMS Braille Sense, Braille EDGE y SyncBraille. (#1266, #1267)
* Cando as Notificacións de Windows 8 aparezan, NVDA anunciaráas se os globos de axuda están habilitados. (#2143)
* Soporte experimental para pantallas Tactiles no Windows 8, incluíndo:
 * Lectura de texto directamente baixo o teu dedo mentres o moves
 * Moitos xestos para levar a cabo a navegación por obxectos, revisión de texto, e outras ordes de NVDA.
* Soporte para o VIP Mud. (#1728)
* No Adobe Reader, se unha táboa ten un resumo, agora preséntase. (#2465)
* No Adobe Reader, as cabeceiras de fila e columna de táboa agora poden anunciarse. (#2193 #2527 #2528)
* Novas linguas: Amárico, Coreano, Nepalí, Esloveno.
* NVDA agora pode ler suxerencias de autocompletado cando se introduzan enderezos de correo no Microsoft Outlook 2007. (#689)
* Novas variantes de voz de eSpeak: Gene, Gene2. (#2512)
* No Adobe Reader, agora poden anunciarse os números de páxina. (#2534)
 * No Reader XI, as etiquetas de páxina anúncianse onde estean presentes, reflectindo cambios na numeración de páxinas en seccións diferentes, etc. en versións anteriores, esto non é posible e só se anunciaban os números de páxinas secuenciales.
* Agora é posible reiniciar a configuración do NVDA ós valores predeterminados de fábrica premendo NVDA+control+r tres veces rápidamente ou escollendo Reiniciar ós Valores Predeterminados de Fábrica dende o menú NVDA (#2086).
* Soporte para as liñas braille Seika Versión 3, 4 e 5 e Seika80 de Nippon Telesoft. (#2452)
* O primeiro e o último dos sensores superiores das liñas braille Freedom Scientific Pacmate e Focus agora pódense utilizar para desprazar cara atrás ou adiante. (#2556).
* Sopórtanse moitas máis características nas liñas braille Freedom Scientific Focus como barras avanzadas, barras de balancíns e certas combinacións de puntos para accións comúns. (#2516)
* En aplicacións que utilicen IAccessible2 como aplicacións de Mozilla, as cabeceiras de fila e columna de táboa agora poden anunciarse fora do modo Navegación. (#926)
* Soporte preliminario para o control de documento no Microsoft Word 2013. (#2543)
* O alineamento de texto agora pode se anunciar nas aplicacións que utilicen IAccessible2 como aplicacións de Mozilla. (#2612)
* Cando se enfoca unha fila de táboa ou un control estándar vista en lista de Windows con múltiples columnas, agora podes utilizar as ordes de navegación por táboas para acceder ás celdas individuais. (#828)
* Novas táboas de transcripción braille: Estonio grado 0, braille computerizado Portugués de 8 puntos e braille italiano computerizado de 6 puntos. (#2319, #2662)
* Se NVDA se instala no sistema, a apertura directa dun paquete de complemento do NVDA (é dicir dende o explorador de Windows ou despois de descargalo dun navegador web) instalarao no NVDA. (#2306)
* Soporte para os modelos máis modernos das liñas de Papenmeier BRAILLEX. (#1265)
* A información de posición (ex.: 1 de 4) agora anúnciase para os elementos de lista de Windows Explorer en Windows 7 e posterior. Esto tamén inclúe calquer control UIAutomation que soporte as propriedades personalizables itemIndex e itemCount. (#2643)

### Cambios

* No diálogo Preferencias do Cursor de Revisión de NVDA, a opción Seguer foco do teclado foi renomeada a Seguer ó foco do sistema para consistencia ca terminoloxía utilizada noutras partes no NVDA.
* Cando o braille estea seguindo á revisión e o cursor estea sobre un obxecto que non sexa un obxecto de texto (ex.: un campo de texto editable), as teclas dos sensores do cursor agora activarán o obxecto. (#2386)
* A opción Gardar a Configuración ó Saír agora está activada de maneira predeterminada para novas configuracións.
* Cando se actualiza unha copia do NVDA instalada anteriormente, a tecla de atallo do escritorio xa non se forza a control+alt+n se foi cambiada manualmente a algunha outra diferente polo usuario. (#2572)
* A lista de complementos no Administrador de Complementos agora amosa o nome do paquete antes do seu estado. (#2548)
* Ó instalar a mesma ou outra versión dun complemento instalado actualmente, NVDA preguntarache se desexas actualizar o complemento antigo primeiro, en lugares de amosar un erro e abortar a instalación. (#2501)
* As ordes de navegación de obxectos (excepto a orde anunciar obxecto actual) agora anuncian con menos verbosidade. Aínda podes obter a información extra utilizando a orde de anunciar obxecto actual. (#2560)
* Actualizado o transcriptor braille liblouis a 2.5.1.
* O documento Referencia Rápida de Ordes de teclado de NVDA foi renomeado a Referencia Rápida de Ordes, así agora inclúe tanto ordes tactiles coma ordes de teclado.
* A Lista de elementos en Modo Navegación agora lembrará o último tipo de elemento amosado (ex.: ligas, cabeceiras ou zoas) cada vez que se amose o diálogo dentro da mesma sesión de NVDA. (#365)
* A maioría das aplicacións Metro en Windows 8 (ex.: Mail, Calendar) xa non activan o Modo Navegación para toda a aplicación.
* Actualizado o Handy Tech BrailleDriver COM-Server a 1.4.2.0.

### Corrección de Fallos

* No Windows Vista e posterior, NVDA xa non trata incorrectamente a tecla Windows como é ó mantela premeda cando se desbloquea Windows despóis de bloqueala premendo Windows+l. (#1856)
* No Adobe Reader, as cabeceiras de fila agora recoñécense correctamente como celdas de táboa; é dicir, as coordinadas anúncianse e pódense acceder utilizando ordes de navegación de táboa. (#2444)
* No Adobe Reader, as celdas de táboa que abranghen máis dunha columna e/ou fila agora manéxanse correctamente. (#2437)
* O paquete de distribución de NVDA agora verifica a súa integridade antes de se executar. (#2475)
* Os ficheiros descargados temporalmente agora elimínanse se se descarga un ficheiro de actualización do NVDA. (#2477)
* NVDA xa non se colgará cando se estea a executar coma un administrador mentres se copia a configuración do usuario á configuración do sistema (para utilizala na autentificación de Windows e noutras pantallas seguras). (#2485)
* Os mosaicos na Pantalla de inicio de Windows 8 agora preséntanse mellor en voz e braille. O nome xa non se repite, xa non se anuncia non seleccioado en todos os mosaicos, e a información de estado en directo preséntase segundo a descripción da mosaico (ex.: temperatura actual para a mosaico do Tempo).
* Os  contrasinais xa non se anuncian cando se lean campos de contrasinal no Microsoft Outlook e outros controis de edición estándar que estean marcados como protexidos. (#2021)
* No Adobe Reader, os cambios para campos de formulario agora reflíctense correctamente no modo navegación. (#2529)
* Melloras no soporte para o corrector de ortografía de Microsoft Word, incluíndo a lectura máis precisa do erro ortográfico actual, e a capacidade de soportar o corrector de ortografía cando se execute unha copia instalada do NVDA en Windows Vista ou superior.
* Os complementos que inclúan ficheiros contendo caracteres que non estean en Inglés agora poden instalarse correctamente na maioría dos casos. (#2505)
* No Adobe Reader, a lingua do texto xa non se perde cando se actualiza ou se despraza. (#2544)
* Cando se instala un complemento, o diálogo de confirmación agora amosa correctamente o nome traducido do complemento se está dispoñible. (#2422)
* Nas aplicacións que utilizan UI Automation (como aplicacións de .net e Silverlight), o cálculo de valores numéricos para controis como deslizadores correxiuse. (#2417)
* A configuración para o anunciado de barras de progreso agora recoñécese para barras de progreso indeterminadas amosadas por NVDA cando se está a instalar, a crear unha copia portable, etc. (#2574)
* As ordes de NVDA xa non poden executarse dende unha liña braille mentres unha pantalla segura de Windows (como a pantalla de desbloqueo) estea activa. (#2449)
* No modo navegación, o braille agora actualízase se o texto que se está a desplazar cambia. (#2074)
* Cando se está en pantallas seguras de  Windows como a pantalla de desbloqueo as mensaxes das aplicacións que están a falar ou a amosar braille directamente a través do NVDA agora ignóranse.
* No modo navegación, xa non é posible sobrepasar a parte inferior do documento ca tecla flecha dereitha cando se está no carácter final, ou saltando o fin dun contedor cando ese contedor é o derradeiro elemento do documento. (#2463)
* Xa non se inclúe incorrectamente contido extrano cando se anuncia o texto de diálogos en aplicaciones web (específicamente, diálogos ARIA sen o atributo aria-describedby). (#2390)
* NVDA xa non localiza ou anuncia incorrectamente certos campos de edición nos documentos MSHTML (ex.: Internet Explorer), específicamente onde se utilizara un rol ARIA explícito polo autor da páxina web. (#2435)
* A tecla retroceso agora manéllase correctamente cando se falan palabras ó se escribir nas consolas de ordes de Windows. (#2586)
* As coordinadas das celdas agora amósanse de novo en Braille en Microsoft Excel.
* No Microsoft Word, NVDA xa non te deixa enganchado nun parágrafo con formato de lista cando tentas navegar por unha viñeta ou número con flecha esquerda ou control + flecha esquerda. (#2402)
* No modo navegación en aplicacións de Mozilla, os elementos en certas caixas de lista (específicamente, caixas de lista de ARIA) xa non se procesan incorrectamente.
* No modo navegación nas aplicacións de Mozilla, certos controis que foron procesados con unha etiqueta incorrecta ou como espazo en branco agora procésanse ca etiqueta correcta.
* No modo navegación nas aplicacións de Mozilla, elimináronse espazos en branco extranos.
* En modo navegación nos navegadores web, certos gráficos que se marcaron explícitamente como presentables (específicamente, cun atributo alt="") agora ignóranse correctamente.
* Nos navegadores web, NVDA agora agacha contido que se marcou como oculto para lectores de pantalla (específicamente, utilizando o atributo aria-hidden). (#2117)
* As cantidades negativas en moneda (ex.: -$123) agora fálanse correctamente como negativos, independentemente do nivel de símbolos. (#2625)
* Durante ler todo, NVDA xa non voltará incorrectamente a á lingua predeterminada se unha liña non remata unha frase. (#2630)
* Agora detéctase correctamente a información de fonte en Adobe Reader 10.1 e posteriores. (#2175)
* No Adobe Reader, se se proporciona texto alternativo, só se procesará ese texto. Anteriormente, algunhas veces incluíase texto extrano. (#2174)
* Cando un documento contén unha aplicación, o contido da aplicación xa non se inclúe no modo navegación. Esto prevén de movementos inesperados dentro da aplicación cando se navega. Podes interactuar ca aplicación do mesmo modo que para os obxectos integrados. (#990)
* En aplicacións de Mozilla, o valor dos botóns de flecha agora anúnciase correctamente cando cambian. (#2653)
* Actualizado o soporte do Adobe Digital Editions para que funcione na versión 2.0. (#2688)
* Premendo NVDA+flecha arriba mentres se estea nunha caixa combinada en Internet Explorer e outros documentos MSHTML xa non se lerán incorrectamente todos os elementos. Pola contra, só se lerá o elemento activo. (#2337)
* Os diccionarios da fala agora gardaranse apropriadamente cando se utilice un signo de número (#) dentro dos campos de edición patrón ou reemprazar. (#961)
* O modo navegación para documentos MSHTML (ex.: Internet Explorer) agora amosa correctamente o contido visible que hai dentro do contido oculto. Específicamente: elementos cun estilo visibility:visible nun elemento con estilo visibility:hidden. (#2097)
* As ligas no Centro de Seguridade de Windows XP xa non anuncian lixo aleatoriamente despois dos seus nomes. (#1331)
* Os controis de texto UI Automation ex.:  o campo de procura no menú de inicio do Windows 7 agora anúncianse correctamente cando se move o rato sobor deles en lugar de quedar en silenzo.
* Os cambios de distribución do teclado xa non se anuncian durante ler todo, o que era especialmente problemático para documentos multilingües incluíndo texto árabe. (#1676)
* Todo o contido dalgúns controis de texto editable UI Automation (ex.: a caixa de procura no menú de inicio do Windows 7/8) xa non se anuncia cada vez que cambie.
* Cando te movas entre grupos na pantalla de inicio de Windows 8, os grupos non etiquetados xa non anunciarán o seu primeiro mosaico coma o nome do grupo. (#2658)
* Ó abrir a pantalla de inicio de Windows 8, o foco colócase correctamente sobre o primeiro mosaico en lugar de saltar á raíz da pantalla de inicio, o que pode confundir na navegación. (2720)
* NVDA xa non fallará ó arrancar cando a ruta de perfiles do usuario conteña certos caracteres multibyte. (#2729)
* No modo navegación en Google Chrome, o texto das pestanas agora  procésase correctamente.
* No modo navegación, os botóns de menú agora anúncianse correctamente.
* No Calc de OpenOffice.org/LibreOffice, a lectura das celdas das follas de cálculo agora funciona correctamente. (#2765)
* NVDA pode funcionar de novo na lista de mensaxes de Yahoo! Mail cando se utiliza dende Internet Explorer. (#2780)

### Cambios para Desenroladores

* O ficheiro rexistro anterior agora cópiase en nvda-old.log na inicialización do NVDA. Polo tanto, se NVDA se bloquea ou se reinicia, o rexistro de información  de esa sesión aínda é accesible para a súa inspección. (#916)
* A obtención da propiedade de rol en chooseNVDAObjectOverlayClasses xa non causa que o rol sexa incorrecto e polo tanto non se anuncie en foco para certos obxectos como consolas de ordes de Windows e controis de Scintilla. (#2569)
* Os menús do NVDA Preferencias, Ferramentas e Axuda agora son accesibles como atributos en gui.mainFrame.sysTrayIcon chamándose preferencesMenu, toolsMenu e helpMenu, respectivamente. Esto permite ós plugins engadir elementos moito máis sinxelamente a estos menús.
* O script navigatorObject_doDefaultAction en globalCommands foi renomeado a review_activate.
* Agora sopórtanse as mensaxes contextuais de Gettext. Esto permite que sexan definidas múltiples traduccións para unha soa mensaxe en Inglés dependendo do contexto. (#1524)
 * Esto faise utilizando a función pgettext(context, message).
 * Esto sopórtase tanto para NVDA mesmo como para os complementos.
 * Deben utilizarse xgettext e msgfmt de GNU gettext para criar calquera ficheiro PO e MO. As ferramentas de Python non soportan mensaxes contextuais.
 * Para xgettext, pasa o argumento de liña de órdenes --keyword=pgettext:1c,2 para habilitar a inclusión de mensaxes contextuais.
 * Mira https://www.gnu.org/software/gettext/manual/html_node/Contexts.html#Contexts para máis información.
* Agora é posible acceder ós módulos compilados de NVDA onde foran sobreescribidos por módulos de terceiros. Olla o módulo nvdaBuiltin para detalles.
* Agora pode utilizarse o soporte de traducción de complementos dentro do módulo installTasks do complemento. (#2715)

## 2012.2.1

Esta versión aborda varios problemas de seguridade potenciais (mediante a actualización do Python á 2.7.3).

## 2012.2

O subliñable desta versión inclúe unha característica que integra o instalador e a creación do portable, un auto actualizador, administración sinxela dos novos complementos do NVDA, anunciado de gráficos en Microsoft Word, soporte para o estilo de aplicacións de Windows 8 Metro, e varias correccións de fallos importantes.

### Novas Características

* NVDA agora pode procurar automáticamente, descargar e instalar actualizacións. (#73)
* Fíxose máis doada a extensión da funcionalidade do NVDA ca adición dun Administrador de Complementos (que se atopa baixo Ferramentas no menú NVDA) permitíndoche instalar e desinstalar paquetes de complementos do NVDA (ficheiros .nvda-addon) que conteñan plugins e controladores. Ten en conta que o Administrador de Complementos non debería amosar os antigos plugins persoais e controladores copiados manualmente no teu directorio de configuración. (#213)
* Agora funcionan Moitas máis características comúns do NVDA no estilo de aplicacións de Windows 8 Metro cando se utiliza unha versión instalada do NVDA, incluíndo a fala de carácteres ó se escreber e modo navegación para documentos web (inclúese soporte para a versión metro do Internet Explorer 10). As copias portables do NVDA non poden acceder ó estilo de aplicacións metro. (#1801)
* En documentos en modo Navegación (Internet Explorer, Firefox etc) agora podes saltar ó comezo, ou pasar ó remate, de certos elementos contedores (incluíndo listas e táboas) con shift+, e , respectivamente. (#123)
* Nova lingua: Grego.
* Agora anúncianse os gráficos e textos alternativos nos documentos de Microsoft Word. (#2282, #1541)

### Cambios

* O anunciado de coordeadas de celda en Microsoft Excel agora faise despóis do contido en lugar de antes, e agora só se inclúe se as opcións de anunciado de táboas e de anunciado de coordeadas da celda da táboa están activadas nas opcións do diálogo Formato de Documento. (#320)
* NVDA agora distribúese nun paquete. En lugar dunha versión portable e unha instalable, agora só hai un ficheiro que cando se execute, iniciará unha copia temporal do NVDA, e permitirache instalar, ou xerar unha distribución portable.
* NVDA agora sempre se instala en Program Files en todos os sistemas. Ó actualizar unha instalación tamén se moverá automáticamente se anteriormente non se instalóu ahí.

### Corrección de Fallas

* Co Cambio automático de lingua activado, o Contido tal coma o texto alternativo para gráficos e etiquetas para certos outros controis en Mozilla Gecko (ex.: Firefox) agora anúncianse na lingua correcta se se marcou apropriadamente.
* Ler todo en BibleSeeker (e outros controis TRxRichEdit) xa non se detén no medio dunha pasaxe.
* As listas que se atopan nas propiedades de ficheiro en Windows 8 Explorer (pestana permisos) e en Windows 8 Windows Update agora lense correctamente.
* Correxidos posibles colgues en MS Word que poderían ocorrer cando lle levou máis de 2 segundos extraer texto  dende un documento (líñas extremadamente longas ou táboas de contido). (#2191)
* A detección de partición de palabras agora funciona correctamente onde un espazo en branco sexa seguido por certa puntuación. (#1656)
* No modo navegación en Adobe Reader, agora é posible navegar por cabeceiras fora dun nivel utilizando navegación rápida e a Lista de Elementos. (#2181)
* No Winamp, o braille agora actualízase correctamente cando te moves a un elemento diferente no Editor de listas de reproducción. (#1912)
* A árbore nos Elementos de Lista (dispoñible para documentos en modo navegación) agora dimensiónase apropiadamente para amosar o texto de cada elemento. (#2276)
* Nas aplicacións que utilicen Java Access Bridge, os campos de texto editable agora amósanse correctamente en braille. (#2284)
* Nas aplicacións que utilicen Java Access Bridge, os campos de texto editable xa non informan de caracteres extranos en certas circumstancias. (#1892)
* Nas aplicacións que utilicen Java Access Bridge, cando se estea ó final dun campo de texto editable, a liña actual  agora anúnciase correctamente. (#1892)
* No modo navegación en aplicacións que utilicen Mozilla Gecko 14 e posterior (ex.: Firefox 14), agora a navegación rápida funciona en bloques de citas e obxectos integrados. (#2287)
* No Internet Explorer 9 NVDA xa non le contido indeseado cando o foco se move dentro de certas zoas ou elementos enfocables (específicamente un elemento div que é enfocable ou que ten un rol de zoa ARIA).
* As iconas para os atallos para o NVDA no Escritorio e no Menú de Inicio agora se amosan correctamente en edicións de 64 bit de Windows. (#354)

### Cambios para Desenroladores

* Debido á substitución do instalador anterior NSIS para o NVDA por un compilado en Python, xa non é necesario para os traductores manter un ficheiro langstrings.txt para o instalador. Todas as cadeas de localización agora adminístranse con ficheiros po de gettext.

## 2012.1

O subliñable desta versión inclúe características para unha lectura máis fluída en braille; indicación de formato de documento en braille; acceso a moita máis información de formato e mellora do rendemento en Microsoft Word; e soporte para a Store de iTunes.

### Novas Características

* NVDA pode anunciar o número de tabuladores ou espacios iniciais da liña actual na orde na que se introduzan. Esto pode activarse seleccionando Anunciar sangrado de liña  no diálogo formato de documento. (#373)
* NVDA agora pode detectar pulsacións de teclas xeradas dende a emulación alternativa de entrada de teclado coma nas aplicacións de teclado en pantalla e recoñecemento de fala.
* NVDA agora pode detectar cores en consolas de ordes de Windows.
* Agora as negriñas, cursivas e subliñados indícanse en braille utilizando signos apropriados ca táboa de transcripción configurada. (#538)
* Agora anúnciase moita máis información en documentos de Microsoft Word, incluindo:
 * Información en liña coma números de cabeceiras e notas ó pe, niveis de cabeceira, a existencia de comentarios, niveis de aniñamento de táboa, ligas, e cor de texto;
 * Anúnciase cando se entra ás seccións do documento coma ó histórico de comentarios, ó histórico de notas ó pe e notas finais, e ós históricos de cabeceiras e pes.
* O braille agora indica o texto seleccionado utilizando os puntos 7 e 8. (#889)
* O braille agora anuncia información acerca dos controis dentro dos documentos coma ligas, botóns e cabeceiras. (#202)
* Soporte para as liñas braille USB hedo ProfiLine e MobilLine. (#1863)
* NVDA agora evita a separación de palabras en braille cando sexa possible de maneira predeterminada.  Esto pode desactivarse no diálogo Opcións de Braille. (#1890, #1946)
* Agora é posible amosar o braille por parágrafos en lugar de liñas, o que podería permitir unha maior fluideza na lectura de longas cantidades de texto. Esto é configurable utilizando a opción Ler por parágrafos no diálogo Opcións de Braille. (#1891)
* No modo navegación, podes activar o obxecto baixo o cursor utilizando unha liña braille. Esto faise premendo a tecla de guiado do cursor onde estea situado o cursor (o que significa premelo dúas veces se o cursor non está aínda alí). (#1893)
* Soporte básico para áreas web en iTunes coma na Store. Outras aplicacións que utilicen WebKit 1 tamén poderían soportarse. (#734)
* Nos libros en Adobe Digital Editions 1.8.1 e posteriores, agora as páxinas vóltanse automáticamente cando se utiliza ler todo.  (#1978)
* Novas táboas de transcripción braille: Portugués grao 2, braille islandés computerizado de 8 puntos, Tamil grao 1, Braille español computerizado de 8 puntos, persa grao 1. (#2014)
* Agora podes configurar se se anuncian os marcos nos documentos dende o diálogo de preferencias de Formato de Documentos. (#1900)
* O modo durminte actívase automáticamente cando se utiliza OpenBook. (#1209)
* En Poedit, os traductores agora poden ler os comentarios engadidos ou extraídos automáticamente para o traductor. As mensaxes que estean sen traducir ou provisionais márcanse cun asterisco e escóitase un pitido cando se navegue sobre eles (#1811).
* Soporte para as liñas braille de HumanWare Brailliant series BI e B. (#1990)
* Nova língua: Noruego Bokmål.

### Cambios

* As ordes que describen o carácter actual ou o deletreo da palabra ou liña agora deletrearán na lingua apropriada de acordo co texto, se o cambio automático de lingua está activado e a información apropriada de idioma está dispoñible.
* Actualizado o sintetizador de voz eSpeak á 1.46.02.
* Agora NVDA filtrará os nomes extremadamente longos (30 caracteres ou máis) deducidos de URLs de gráfícos e ligas dado que o máis probable é que sexan lixo que obstaculice a lectura.
* Abreviouse algunha información amosada en braille. (#1955, #2043)
* Cando os cursores de sistema ou de revisión se moven, agora o braille desprázase de igual xeito como se se desprazase manualmente. Esto faino máis apropriado cando o braille configurouse para ler por párágrafos e/ou para evitar partición de palabras. (#1996)
* Actualizado a unha nova táboa de transcripción braille Española de grao 1.
* Actualizado o transcriptor braille liblouis a 2.4.1.

### Corrección de Erros

* No Windows 8, o foco xa non se move incorrectamente do campo de procura de Windows Explorer, o que non permitía ó NVDA interactuar con el.
* Melloras no rendemento cando se le e se navega polos documentos de Microsoft word mentres o anunciado automático do formato está activado, así agora é un pouco máis confortable probar a ler o formato etc. O rendemento tamén podería mellorarse sobre todo para algúns usuarios.
* O modo navegación agora úsase para toda a pantalla no contido de Adobe Flash.
* Correxida a mala calidade do audio nalgúns casos cando se usan voces do Microsoft Speech API versión 5 co dispositivo de saída de audio configurado a algún outro co predeterminado (Microsoft Sound Mapper). (#749)
* Permítese novamente a NVDA utilizarse co sintetizador "no speech", confiando únicamente no braille ou no visualizador de voz. (#1963)
* As ordes de navegación de obxectos xa non anuncian "Sen fillos" e "Sen pais", pero nembargantes anuncian mensaxes consistentes ca documentación.
* Cando NVDA se configurou para utilizar outra lingua que o Inglés, o nome da tecla tab agora anúnciase na lingua adecuada.
* En Mozilla Gecko (ex.: Firefox), NVDA xa non cambia intermitentemente a modo navegación mentres se navega por menús en documentos. (#2025)
* Na Calculadora, a tecla retroceso agora anuncia o resultado actualizado en lugar de non anunciar nada. (#2030)
* No modo navegación, a orde mover o rato ó navegador de obxectos actual agora móvese ó centro do obxecto no cursor de revisión en lugar de á esquina esquerda superior, facéndoo máis preciso en algúns casos. (#2029)
* No modo navegación co modo foco automático para cambios do foco activado, o enfocado dunha barra de ferramentas agora cambiará a modo foco. (#1339)
* A orde anunciar título funciona correctamente de novo en Adobe Reader.
* Co modo foco automático para cambios do foco activado, o modo foco agora utilízase correctamente para as celdas de táboa enfocadas; ex.: en rexiñas ARIA. (#1763
* No iTunes, a información de posición en certas listas agora anúnciase correctamente.
* No Adobe Reader, algunhas ligas xa non se tratan coma contendo campos de texto editable de só lectura.
* As etiquetas dalgúns campos de texto editable xa non se inclúen incorrectamente cando se anuncia o texto dun diálogo. (#1960)
* A descripción de grupos anúnciase unha vez de novo se o anunciado de descripcións de obxecto está activado.
* Os tamanos lexibles agora inclúense no texto do diálogo de propriedades da unidade en Windows Explorer.
* O anunciado doble de texto en páxinas de propiedades foi suprimido nalgúns casos. (#218)
* Mellorado o seguemento do cursor do sistema en campos de texto editable que confían en texto escrito na pantalla. En particular, esto mellora a edición no editor de celdas de Microsoft Excel e o editor de mensaxes de Eudora. (#1658)
* En Firefox 11, a orde mover a contido de modo virtual (NVDA+control+espazo) agora funciona como debería para saír de obxectos integrados como contido Flash.
* NVDA agora reiníciase correctamente (ex.: despois de cambiar a lingua configurada) cando se localice nun directorio con contidos de carácteres non ASCII. (#2079)
* O Braille respecta correctamente as opcións para o anunciado de teclas de atallo dos obxectos, información de posición e descripcións.
* En aplicacións Mozilla, o cambio entre modos navegación e foco xa non enlentece co braille activado. (#2095)
* Guiar o cursor ó espazo no remate da liña/parágrafo utilizando os sensores do cursor braille nalgúns campos de texto editable agora funciona correctamente en lugar de levar ó comezo do texto. (#2096)
* NVDA funciona de novo correctamente co sintetizador Audiologic Tts3. (#2109)
* Os documentos de Microsoft Word trátanse correctamente como multi-liña. Esto causa que o braille se comporte de maneira máis adecuada cando un documento se enfoque.
* No Microsoft Internet Explorer, xa non ocorren erros cando se enfoca sobre certos controis raros. (#2121)
* Cambiar a puntoación e símbolos polo usuario agora terá efecto inmediato, en lugar de requerir un reinicio do NVDA, ou que se desactive o cambio automático de lingua.
* Cando se utiliza eSpeak, a voz xa non queda en silenzo nalgúns casos no diálogo Gardar Como... do Visualizador de Rexistro do NVDA. (#2145)

### Cambios para Desenrroladores

* Agora hai unha Consola Python remota para situacións onde a depuración remota é útil. Mira a Developer Guide para detalles.
* A ruta base do código de NVDA agora quitouse dos tracebacks no rexistro para mellorar lexibilidade. (#1880)
* Os obxectos TextInfo agora teñen un método activate() para activar a posición representada polo TextInfo.
 * Esto utilízase polo braille para activar a posición utilizando teclas de guiado do cursor nunha liña braille. Nembargantes, podería haber outras chamadas no futuro.
* Os treeInterceptors e os NVDAObjects que só expoñen unha páxina de texto á vez poden soportar o cambio automático de páxina durante ler todo utilizando o textInfos.DocumentWithPageTurns misturado. (#1978)
* Movéronse ou cambiáronse os nomes de varios controis e constantes de saída. (#228)
 * As constantes speech.REASON_* movéronse a controlTypes.
 * Renomeáronse controlTypes, speechRoleLabels e speechStateLabels só a roleLabels and stateLabels, respectivamente.
* Agora a saída braille rexístrase no nivel input/output. Primeiro, o texto sen transcribir de todas as rexións rexístrase, seguido polas celdas braille da xanela que se están a amosar. (#2102)
* As subclasses do synthDriver sapi5  agora poden sobreescribirse _getVoiceTokens e extender init para soportaren fichas de voces personalizadas como con sapi.spObjectTokenCategory para obter fichas dun rexistro personalizado.

## 2011.3

O subliñable nesta versión inclúe o cambio automático de idioma da voz cando se len documentos ca información de idioma apropriada;  soporte para ambentes Java Runtime de 64 bit; anunciado de formato de texto en Modo navegación en aplicacións de Mozilla; mellor manexo de rupturas e colgues de aplicacións; e correccións iniciais para Windows 8.

### Novas Características

* NVDA agora pode cambiar a lingua do sintetizador eSpeak ó vo cando le certos documentos web/pdf ca información de lingua  apropriada. O cambio automático da lingua/dialecto pode activarse ou desactivarse dende o diálogo Opcións de Voz. (#845)
* No Mozilla Gecko (ex.: Firefox) os niveis de cabeceira agora anúncianse cando se utiliza a navegación de obxectos.
* O formato de texto agora pódese anunciar cando se utiliza o modo navegación en Mozilla Gecko (ex.: Firefox e Thunderbird). (#394)
* O texto con subliñado e/ou tachado agora pode detectarse e anunciarse nos controis de texto estándar IAccessible2 como nas aplicacións de Mozilla.
* NVDA agora reiniciarase se se colga.
* No modo Navegación en Adobe Reader, agora infórmase da conta das filas e das columnas.
* Engadiuse soporte para a Plataforma de Síntese de Voz de Microsoft. (#1735)
* Os números de liña e de páxina agora anúncianse para o cursor en IBM Lotus Symphony. (#1632)
* A porcentaxe de cánto cambia o ton cando se fale unha letra maiúscula agora é configurable dende o diálogo Opcións de voz. Polo tanto, esto reemplaza a vella caixa de verificación elevar o ton para maiúsculas (polo tanto para desactivar esta característica ca porcentaxe a 0). (#255)
* A cor de texto e fondo agora inclúese no anunciado de formato para celdas en Microsoft Excel. (#1655)
* En aplicacións que utilizen o Java Access Bridge, a orde activar actual navegador de obxectos agora funciona en controis onde sexa apropriado. (#1744)
* Nova lingua: Tamil.
* Soporte básico para Design Science MathPlayer.

### Cambios

* NVDA agora reiniciarase se se colga.
* Algunha información amosada en braille foi abreviada. (#1288)
* O script Ler xanela activa (NVDA+b) foi mellorado para filtrar controis inútiles e agora tamén é moito máis sinxelo de silenciar. (#1499)
* Ler Todo automáticamente cando se carga un documento en Modo Navegación agora é opcional a través dunha opción no diálogo Opcións do Modo Navegación. (#414)
* Cando se tratan de ler barras de estado (Sobremesa NVDA+fin), se non se pode localizar un obxecto de barra de estado real, NVDA recurrirá no seu lugar a utilizar a liña final de texto escribida na pantalla da aplicación activa. (#649)
* Cando se le con ler todo en documentos en modo navegación, NVDA agora fará unha pausa no final de encabezados e outros elementos de nivel de bloque, en lugar de falar o texto xunto co seguinte bloque como se fora unha frase longa.
* En modo navegación, presionando intro o espacio en una pestaña ahora la activa en lugar de cambiar a modo foco. (#1760)
* Actualizado o sintetizador de voz eSpeak á 1.45.46.

### Corrección de Erros

* NVDA xa non amosa viñetas ou numeración para listas en Internet Explorer e outros controis MSHTML cando o autor indicou que éstas non deberíam amosarse (é dicir, o estilo de lista é "none"). (#1671)
* Reiniciar NVDA cando se colgou (ex.: premendo control+alt+n) xa non sae da copia previa sen comezar outra nova.
* Premer retroceso ou flechas nunha consola de ordes de Windows xa non causa resultados extranos nalgúns casos. (#1612)
* O elemento seleccionado en caixas combinadas WPF (e posiblemente algunhas outras caixas combinadas amosadas utilizando UI Automation) que non permiten edición de texto agora anúnciase correctamente.
* En modo Navegación en Adobe Reader, agora sempre é posible moverte á seguinte fila dende a fila de cabeceira e viceversa utilizando as ordes moverse á seguinte fila e moverse á fila anterior. Tamén,  a fila de cabeceira xa non se anuncia como fila 0. (#1731)
* En modo navegación en Adobe Reader, agora é posible mover a (e polo tanto pasar) celdas valdeiras nunha táboa.
* Información de posición sen sentido  (ex.: 0 de 0 nivel 0) xa non se anuncia en braille.
* Cando o braille siga á revisión, agora poderá amosarse contido en revisión chan. (#1711)
* Un texto do control de texto xa non se presenta dúas veces nunha liña braille en algúns casos, ex.: desprazándose atrás dende o comezo de documentos de Wordpad.
* En modo navegación en Internet Explorer, premendo intro sobre un botón de subir un ficheiro agora preséntase correctamente o diálogo para escoller un ficheiro para subir en lugar de cambiar a modo foco.  (#1720)
* Os cambios de contido dinámico como en consolas do Dos xa non se anuncian se  o modo durminte para esa aplicación está actualmente activado. (#1662)
* En modo navegación, o comportamento de alt+flecha arriba e alt+flecha abaixo para contraer e expandir caixas combinadas foi mellorado. (#1630)
* NVDA agora recupérase de moitas máis situacións como aplicacións que deixan de responder nas que anteriormente causaba un colgue compreto. (#1408)
* Para documentos en modo navegación de Mozilla Gecko (Firefox etc) NVDA xa non fallará ó interpretar texto nunha situación moi específica onde un elemento is styled as display:table. (#1373)
* NVDA xa non anunciará controis etiqueta cando o foco se mova por eles. Detén o anunciado doble de etiquetas para algúns campos de formulario en Firefox (Gecko) e Internet Explorer (MSHTML). (#1650)
* NVDA xa non falla ó ler unha celda en Microsoft Excel despois de pegar con control+v. (#1781)
* En Adobe Reader, xa non se anuncia información extraña acerca do documento cando se mova cara un control nunha páxina diferente en modo foco. (#1659)
* En modo navegación en aplicacións de Mozilla Gecko (ex.: Firefox), os botóns de comnutación agora detéctanse e anúncianse correctamente. (#1757)
* NVDA agora pode ler correctamente a barra de enderezos do Explorador de Windows en Windows 8 developer preview.
* NVDA xa non colga aplicacións como winver y wordpad en Windows 8 developer preview debido a malas traduccións de glyph.
* En modo navegación en aplicacións que utilizan Mozilla Gecko 10 e posteriores (ex.: Firefox 10), o cursor colócase correctamente máis de cotío cando se carga unha páxina cun áncora. (#360)
* En Modo navegación en aplicacións Mozilla Gecko (ex.: Firefox), as etiquetas para mapas de imaxen agora interprétanse.
* Co seguemento do rato activado, ó mover o rato sobre certos campos de texto editable (como en Synaptics Pointing Device Settings e SpeechLab SpeakText) xa non causa que a aplicación se colgue. (#672)
* NVDA agora funciona correctamente en varios diálogos Acerca de... en aplicacións distribuídas co Windows XP, incluindo o diálogo de acerca de... en Notepad e o diálogo de acerca de  en Windows. (#1853, #1855)
* Correxida a revisión por palabras en controis de edición de Windows. (#1877)
* Moverse fora dun campo de texto editable con flecha esquerda, flecha arriba ou avpáz mentres se está en modo foco agora cambia correctamente a modo navegación cando está habilitado o modo foco automático para movementos do cursor. (#1733)

### Ccambios para Desenrroladores

* NVDA agora pode instruir ós sintetizadores de voz para cambiar as linguas para seccións en particular de voz.
 * Para soportar esto, os controladores deben manellar speech.LangChangeCommand en secuencias pasadas ó SynthDriver.speak().
 * Os obxectos SynthDriver tamén deberían proporcionar o argumento de lingua ós obxectos VoiceInfo (ou sobreescribir o atributo de lingua para capturar a lingua actual). de outro modo, a lingua da interface do usuario do NVDA será utilizada.

## 2011.2

O subliñable nesta revisión inclúe melloras maiores concernintes á puntoación e símbolos, incluíndo niveis configurables, etiquetado e descripcións de carácteres persoalizados; sen pausas ó remate das liñas durante a lectura completa; soporte mellorado para ARIA en Internet Explorer; e moito mellor soporte para documentos PDF XFA/LiveCycle en Adobe Reader; acceso a texto escribido na pantalla en máis aplicacións; e acceso a formato e información de cor para texto escrito na pantalla.

### Novas Características

* Agora é posible escoitar a descripción para calquera carácter dado premendo o script revisar carácter actual dúas veces en sucesión rápida.  Para carácteres en Inglés esto é o alfabeto fonético inglés estándar. Para idiomas pictográficos como o Chinese Mandarín, proporciónanse unha ou máis frases de exemplo utilizando o símbolo dado. Tamén premendo revisar palabra actual ou revisar liña actual tres veces deletreará a palabra/liña utilizando a primeira destas descripcións. En galego utilízase o alfabeto de deletreo radioaficionado lixeiramente modificado(#55)
* Pode verse máis texto en revisión chan para aplicacións como Mozilla Thunderbird que escriben o seu texto directamente á pantalla como glyphs.
* Agora é posible escoller varios niveis de anunciado de puntuación e símbolos. (#332)
* Cando a puntuación ou outros símbolos repítense máis dunha vez, agora anúnciase o número de repeticións  en lugar de dicir os símbolos repetidamente. (#43)
* Unha nova táboa de transcripción braille: braille computerizado noruego de 8 puntos. (#1456)
* A voz xa non fai pausas antinaturais ó remate de cada liña cando se utiliza a orde para ler todo. (#149)
* NVDA agora anunciará se algo se ordea (de acordo ca propiedade aria-sort) en navegadores Web. (#1500)
* Os patróns Braille unicode agora amósanse correctamente nas liñas braille. (#1505)
* En Internet Explorer e outros controis MSHTML cando o foco se move dentro dun grupo de controis (surrounded by a fieldset), NVDA agora anunciará o nome do grupo (the legend). (#535)
* En Internet Explorer e outros controis MSHTML, as propiedades aria-labelledBy e aria-describedBy are now honoured.
* En Internet Explorer e outros controis MSHTML, foi mellorado o soporte para controis ARIA list, gridcell, slider e progressbar.
* Os usuarios agora poden cambiar a pronunciación de puntuación e outros símbolos, así como o nivel en que se falen. (#271, #1516)
* En Microsoft Excel, o nome da folla activa agora anúnciase cando se cambie de páxina con control+rePáx ou control+avPáx. (#760)
* Cando se navega por unha táboa en Microsoft Word ca tecla tab NVDA agora anunciará a celda actual segundo te movas. (#159)
* Agora podes configurar se as coordinadas dunha celda de táboa anúncianse dende o diálogo de preferencias de formato de documento. (#719)
* NVDA agora pode detectar formato e cor para texto escribido na pantalla.
* Na lista de mensaxes de Outlook Express/Windows Mail/Windows Live Mail, NVDA agora anunciará o feito de que unha mensaxe estea non lida e tamén se está expandido ou contraído no caso de fíos de conversa. (#868)
* eSpeak agora ten unha opción de tasa de aumento que triplica a velocidade da voz.
* Soporte para o control calendario que se atopa no diálogo de Información de Data e Hora accedido dende o reloxo de Windows 7. (#1637)
* Engadíronse combinacións de teclas adicionais para a liña braille MDV Lilli. (#241)
* Novas linguas: Búlgaro, Albanés.

### Cambios

* Para mover o cursor do sistema ó cursor de revisión, agora preme o script mover foco ó navegador de obxectos (Sobremesa NVDA+shift+menos teclado numérico, portátil NVDA+shift+retroceso) dúas veces en sucesión rápida. Esto libera máis teclas no teclado. (#837)
* Para escoitar a representación decimal e hexadecimal do carácter baixo o cursor de revisión, agora preme revisar carácter actual tres veces en lugar de dúas veces, xa que dúas veces agora di a descripción do carácter.
* Actualizado o sintetizador de voz eSpeak a 1.45.03. (#1465)
* As táboas de deseño xa non se anuncian en aplicacións de Mozilla Gecko mentres se move o foco cando se está en modo foco ou fora dun documento.
* En Internet Explorer e outros controis  MSHTML, o modo navegación agora funciona para os documentos dentro de aplicacións ARIA. (#1452)
* Actualizado o transcriptor braille  liblouis a 2.3.0.
* Cando se está en modo navegación e se salta a un control con quicknav ou foco, a descripción do control agora anúnciase se ten un.
* As barras de progreso agora anúncianse en modo navegación.
* Os nodos marcados cun rol ARIA de presentación en Internet Explorer e outros controis MSHTML agora fíltranse fora da revisión simple e o ancestro do foco.
* A interface de usuario e a documentación de NVDA agora refírense ós modos virtuais como modo navegación , xa que o termo "virtual buffer" é menos comprensible para a maioría dos usuarios. (#1509)
* Cando o usuario desexe copiar as súas opcións de usuario ó perfil do sistema para utilizalas en pantallas de autentificación, etc., e as súas opcións conteñan plugins persoais, agora serán advertidos de que esto podería supor un risco de seguridade. (#1426)
* O servicio NVDA xa non inicia e detén ó NVDA en escritorios de entrada de usuario.
* En Windows XP e Windows Vista, NVDA xa non fai uso de UI Automation aínda se está dispoñible a través da actualización da plataforma. Aíndaque utilizando UI Automation pódese mellorar a accesibilidade dalgunhas aplicacións modernas, en XP e Vista había moitos colgues, rupturas e perdíase toda a boa funcionalidade utilizándoo. (#1437)
* En aplicacións que utilizan Mozilla Gecko 2 e posterior (tales como Firefox 4 e posterior), agora pode lerse un documento en modo navegación antes de que a carga remate compretamente.
* NVDA anuncia agora o estado dun contedor cando o foco se mova a un control dentro del (ex.: se o foco se move dentro dun documento que aínda se estea cargando anunciaráo como ocupado).
* A interface de usuario e documentación do NVDA xa non utiliza os termos "primeiro fillo" e "pai" con respecto á navegación de obxectos, pois estos termos son confusos para moitos usuarios.
* Xa non se anuncia contraído para algúns elementos de menú que teñen submenús.
* O script reportCurrentFormatting (NVDA+f) agora anuncia o formato na posición do cursor de revisión antes que o cursor do sistema / foco. Xa que de forma predeterminada o cursor de revisión segue ó do sistema, a maior parte da xente non debería notar a diferencia.  Nembargantes esto agora posibilita ó usuario mirar o formato cando se mova o cursor de revisión, tal como na revisión chan.

### Corrección de erros

* Contraer caixas combinadas en documentos en modo navegación cando o modo foco foi forzado con NVDA+espacio xa non volta automáticamente a modo navegación. (#1386)
* En documentos Gecko (ex.: Firefox) e MSHTML (ex.: Internet Explorer), NVDA agora procesa correctamente  certo texto na mesma liña que previamente foi procesado en liñas separadas. (#1378)
* Cando o Braille segue á revisión e o navegador de obxectos se move a un documento en modo navegación, ou manualmente ou debido a un cambio de foco, o braille amosará adecuadamente o contido do modo de navegación. (#1406, #1407)
* Cando a fala da puntuación estea desactivada, certa puntuación xa non se di incorrectamente cando se utilicen algúns sintetizadores. (#332)
* Xa non ocurren problemas cando se carga a configuración para sintetizadores que non soportan a opción de voz como Audiologic Tts3. (#1347)
* O menú de Skype Extras agora lese correctamente. (#648)
* Marcando a caixa de verificación Brilo Controla o Volume no diálogo Opcións do Rato xa non debería causar un retraso maior para pitidos cando se mova o rato ó longo da pantalla en Windows Vista/Windows 7 con Aero activado. (#1183)
* Cando NVDA se configura para utilizar a distribución de teclado portátil, NVDA+suprimir agora funciona como se documentou para anunciar as dimensións do navegador de obxectos actual. (#1498)
* NVDA agora cumpre apropriadamente co atributo aria-selected en documentos de Internet Explorer.
* cando NVDA cambia automáticamente a modo foco en documentos de modo navegación, agora anuncia información acerca do contexto do foco. Por exemplo, se un elemento dunha caixa de lista recive o foco, a caixa de lista anunciarase primeiro. (#1491)
* En Internet Explorer e outros controis MSHTML, os controis ARIA listbox agora trátanse como listas, en lugar de como elementos de lista.
* Cando un control editable de texto de so lectura recibe o foco, NVDA agora informa de que é de só lectura. (#1436)
* No modo navegación, NVDA agora funciona correctamente con respecto ós campos de texto editable de so lectura.
* Nos documentos en modo navegación, NVDA xa non cambia incorrectamente de modo foco cando aria-activedescendant está configurado; ex.: cando o remate da lista aparece nalgúns controis con autocompletado.
* No Adobe Reader, o nome dos controis agora anúnciase cando se mova o foco ou utilízase navegación rápida en modo navegación.
* Nos documentos XFA PDF no Adobe Reader, botóns, ligas e gráficos agora procésanse correctamente.
* Nos documentos XFA PDF no Adobe Reader, todos os elementos agora procésanse en liñas por separado.  Este cambio fíxose porque as seccións grandes (ás veces todo o documento) procesábanse sen saltos debido ó retraso xeral da estructura nestos documentos.
* Correxidos problemas cando se move o foco dende campos de texto editable nos documentos XFA PDF no Adobe Reader.
* Nos documentos XFA PDF no Adobe Reader, os cambios ó valor dunha caixa combinada enfocada agora anunciaranse.
* As caixas combinadas Owner-drawn como os de escoller cores no Outlook Express agora son accesibles co NVDA. (#1340)
* Nas linguas que utilizan un espazo como separador de grupo de milleiro como francés e alemán, os números de grupos separados de texto xa non se pronuncian como un só número. Esto era particularmente problemático para celdas de táboas que conteñan números. (#555)
* Os nodos cun rol de descripción de ARIA no Internet Explorer e outros controis MSHTML agora clasifícanse como texto estático, non como campos de edición.
* Correxidos varios problemas cando se preme tab mentres o foco está nun documento en modo navegación (ex.: tab móvese inapropriadamente á barra de enderezos no Internet Explorer). (#720, #1367)
* Cando se entra en listas mentres se le texto, NVDA agora di, por exemplo, "lista con 5 elementos" en lugar de "listacon 5 elementos". (#1515)
* No modo de axuda de entrada, os xestos están no sistema aínda se os seus scripts deixan pasar a axuda de entrada como as ordes de desprazamento da líña braille cara adiante e atrás.
* No modo de axuda de entrada, cando unha modificadora se mantén pulsada no teclado, NVDA xa non anuncia a modificadora como se se modificase a sí mesma; ex.: NVDA+NVDA.
* Nos documentos do Adobe Reader, a pulsación da c ou shift+c para navegar a unha caixa combinada agora funciona.
* O estado seleccionado de filas de táboa seleccionables agora anúnciase do mesmo modo que para os elementos de lista e árbore.
* Os controis no Firefox e outras aplicacións Gecko agora poden activarse mentres se está no modo navegación aínda se o seu contido estivo flotando fora da pantalla. (#801)
* Xa non se pode amosar un diálogo de opcións de NVDA mentres se está amosando unha mensaxe de diálogo, xa que o diálogo de opcións colgábase neste caso. (#1451)
* No Microsoft Excel, xa non hai un retraso cando se mantiñan pulsadas ou se pulsaban teclas rápidamente para moverse entre celdas ou seleccionalas.
* Correxidas rupturas do servicio NVDA que significaban que NVDA paraba de executarse en xanelas seguras de Windows.
* Correxidos problemas que ocurrían ás veces con liñas braille cando un cambio causaba que o texto que estaba amosándose desaparecera.
* A xanela de descargas no Internet Explorer 9 agora pode navegarse e lerse co NVDA. (#1280)
* Xa non é posible iniciar accidentalmente múltiples copias do NVDA ó mesmo tempo. (#507)
* En sistemas lentos, NVDA xa non causa que a súa xanela principal se amose inapropriadamente todo o tempo mentres se executa. (#726)
* NVDA xa non se rompe en Windows xP cando se inicia unha aplicación WPF. (#1437)
* Ler todo e ler todo co cursor de revisión agora poderá funcionar en algúns controis de texto UI automation que soporten todos os métodos necesarios. (ex.: agora podes utilizar dicir toda a revisión en documentos de XPS Viewer).
* NVDA xa non clasifica inapropriadamente algúns elementos de lista no aplique de regras de mensaxes no Outlook Express / Windows Live Mail agora o diálogo é como caixas de verificación. (#576)
* As caixas combinadas xa non se anuncian como tendo un submenú.
* NVDA agora poderá ler o recipiente nos campos para, CC e CCO no Microsoft Outlook. (#421)
* Correxido o fallo no diálogo de Opcións de Voz de NVDA onde o valor das barras de desprazamento  ás veces non se anunciaba cando cambiaban. (#1411)
* NVDA xa non falla ó anunciar a celda nova cando se move nunha folla Excel despóis de cortar e pegar. (#1567)
* NVDA xa non o fai tan mal adiviñando os nomes das cores anunciando a maioría das mesmas.
* No Internet Explorer e outros controis MSHTML, correxiuse a incapacidade para ler partes de páxinas extranas que conteñen iframes marcados cun rol ARIA de presentación. (#1569)
* No Internet Explorer e outros controis MSHTML, correxiuse un problema extrano onde o foco permanecía rebotando infinitamente entre o documento e un campo editable de texto multilínea en modo foco. (#1566)
* No Microsoft Word 2010 NVDA agora lerá automáticamente os diálogos de confirmación. (#1538)
* Nos campos editables multilínea de texto en Internet Explorer e outros controis MSHTML, a selección en liñas despóis do primeiro agora anúnciase correctamente. (#1590)
* Mellorado o movemento por palabras en moitos casos, incluíndo modo navegación e controis de edición de Windows. (#1580)
* O instalador do NVDA xa non amosa texto confuso para versións para Hong Kong de Windows Vista e Windows 7. (#1596)
* NVDA xa non falla ó cargar o sintetizador de Microsoft Speech API versión 5 se a configuración contén opcións para ese sintetizador pero falta a opción da voz. (#1599)
* En campos de texto editable en Internet Explorer e outros controis MSHTML, o NVDA xa non se retrasa ou se conxela cando o braille estea activado.
* No modo navegación de firefox, NVDA xa non se nega a incluir contido que estea dentro dun nodo enfocable con un rol ARIA de presentación.
* No Microsoft Word co braille activado, as liñas en páxinas despóis da primeira páxina agora anúncianse correctamente. (#1603)
* No Microsoft Word 2003, as liñas de texto de dereita a esquerda poden lerse unha vez de novo co braille activado. (#627)
* No Microsoft Word, ler todo agora funciona correctamente cando o documento non remata cun final de frase.
* Cando se abre unha mensaxe de texto chan no Windows Live Mail 2011, NVDA enfocará correctamente o documento de mensaxe permitindo que se lea.
* NVDA xa non se colga ou se nega a falar temporalmente cando está nos diálogos Mover a / Copiar a no Windows Live Mail. (#574)
* No Outlook 2010, NVDA agora seguirá correctamente o foco na lista de mensaxes. (#1285)
* Resolvéronse algúns problemas de conexión de USB ca liña braille MDV Lilli. (#241)
* En Internet explorer e outros controis MSHTML, os espazos xa non se ignoran en modo navegación en certos casos (é dicir despois dunha liga).
* En Internet Explorer e outros controis MSHTML, foron eliminados algúns extranos cambios de liña en modo navegación. Específicamente, elementos HTML cun estilo de pantalla None xa non forza un salto de liña. (#1685)
* Se NVDA non é capaz de iniciarse, o fracaso para reproducir o son de parada crítica de Windows xa non anula a mensaxe de erro crítico no ficheiro do rexistro.

### Cambios para Desenroladores

* A documentación de desenvolvedores agora pode xerarse utilizando SCons. mira readme.txt na raíz da distribución fonte para detalles, incluíndo dependencias asociadas.
* As Localizacións agora poden proporcionar descripcións para carácteres. Mira a sección Character Descriptions da Developer Guide para detalles. (#55)
* As Localizacións agora poden proporcionar información acerca da pronunciación de puntuación específica e outros símbolos. Mira a sección Symbol Pronunciation da Developer Guide para detalles. (#332)
* Agora podes compilar NVDAHelper con varias opcións de depuración utilizando a variable nvdaHelperDebugFlags SCons. Mira readme.txt na raíz da distribución de fontes para detalles. (#1390)
* Os controladores de síntesis agora pásanse como unha secuencia de texto e ordes de voz a se falar, en lugar de só texto e un índice.
 * Esto permite índices integrados, cambios de parámetros, etc.
 * Os controladores deberían implementar SynthDriver.speak() en lugar de SynthDriver.speakText() e SynthDriver.speakCharacter().
 * Os métodos antigos utilizaranse se SynthDriver.speak() non se implementou, pero quedaron en desuso e eliminaranse nunha versión futura.
* Eliminouse gui.execute(). Debería utilizarse wx.CallAfter() no seu lugar.
* Eliminouse gui.scriptUI .
 * Para diálogos de mensaxe, utiliza wx.CallAfter(gui.messageBox, ...).
 * Para todos os demáis diálogos, deberían utilizarse os diálogos proprios de wx no seu lugar.
 * Unha nova función gui.runScriptModalDialog() simplifica a utilización de diálogos modais de scripts.
* Agora os controladores de sintetizador poden soportar opcións booleanas.  Mira SynthDriverHandler.BooleanSynthSetting.
* SCons agora accepta unha variable certTimestampServer especifycando a URL dun servidor timestamping para utilizar unhas marcas timestamp authenticode. (#1644)

## 2011.1.1

Esta versión corrixe varios problemas de seguridade e outros importantes atopados en NVDA 2011.1.

### Corrección de Erros

* O elemento Doar no menú NVDA agora desactívase cando se executa na autentificación, bloqueo, UAC e outras xanelas de pantallas seguras, xa que esto é un risco de seguridade. (#1419)
* Agora é imposible copiar ou pegar dentro da xanela de interface do usuario do NVDA mentres se está en escritorios seguros (Pantalla bloqueada, pantalla do UAC e autentificación de windows) xa que esto é un risco de seguridade. (#1421)
* En Firefox 4, a orde mover ó contido do modo virtual (NVDA+control+espazo) agora funciona como debería escapar de obxectos integrados como contido Flash. (#1429)
* Cando falar teclas de ordes estea activado, os caracteres maiusculados xa non se falan incorrectamente como teclas de ordes. (#1422)
* Cando falar teclas de ordes estea activado,, premendo espazo con outros modificadores que shift (como control e alt) agora anúncianse como unha tecla de ordes. (#1424)
* O Logging agora desactívase completamente cando se execute dende a autentificación, bloqueo, UAC e outras xanelas seguras, xa que esto é un risco de seguridade. (#1435)
* No modo de axuda de entrada, os xestos agora conéctanse aínda se non están vencellados a un script (de acordo ca guía do usuario. (#1425)

## 2011.1

O subliñable nesta versión inclúe o anunciado de cores para algúns controis; anunciado automático da saída de texto novo en mIRC, PuTTY, Tera Term e SecureCRT; soporte para plugins globais; anunciado de viñetas  e numeración en Microsoft Word; combinacións de teclas adicionais para liñas braille, incluíndo teclas para moverse á liña seguinte e anterior; e soporte para varias liñas braille Baum, HumanWare e APH.

### Novas Características

* Agora pódense anunciar as cores para algúns controis. O anunciado automático pódese configurar no diálogo de preferencias de formateado de documentos. Tamén se poden anunciar baixo demanda utilizando a orde de anunciado de formato de texto (NVDA+f).
 * Inicialmente, esto sopórtase en controis de texto estándar IAccessible2 (como en aplicacións de Mozilla), controis RichEdit (como en Wordpad) e controis de texto de IBM Lotus Symphony.
* Nos modos virtuais, agora podes seleccionar por páxina (utilizando shift+AvPáx e shift+RePáx) e por parágrafos  (utilizando shift+control+Flecha Abaixo e shift+control+Flecha Arriba). (#639)
* NVDA agora anuncia a saída do texto novo en mIRC, PuTTY, Tera Term e SecureCRT. (#936)
* Os usuarios agora poden engadir novas combinacións de teclas ou sobreescribir as existentes para calquer script no NVDA proporcionando un sinxelo mapa de movementos de entrada do usuario. (#194)
* Soporte para plugins globais. Os plugins globais poden engadir nova funcionalidade ó NVDA que funcione en todas as aplicacións. (#281)
* Agora escóitase un pequeño pitido cando se teclean caracteres ca tecla shift mentres o BloqMaius estea activado. Esto pódese desactivar desmarcando a nova opción relacionada no diálogo de Opcións de Teclado . (#663)
* Agora anúncianse os saltos de páxina cando nos movemos por liñas en Microsoft Word. (#758)
* As viñetas e a numeración fálanse agora en Microsoft Word cando nos movemos por liñas. (#208)
* Agora está dispoñible unha orde para activar ou desactivar o modo Durminte para a aplicación actual (NVDA+shift+s). O Modo Durminte (anteriormente coñecido como modo de voz propia) desactiva toda a funcionalidade de lectura da pantalla no NVDA para unha aplicación en particular. Moi útil para aplicacións que proporcionan a súa propria voz e ou características de lectura de pantalla. Preme esta orde de novo para desactivar o Modo Durminte.
* Engadíronse algunhas combinacións de teclas adicionais para liñas braille. Mira a sección Liñas braille Soportadas da Guía do Usuario para detalles. (#209)
* Para conveniencia de desenroladores de terceiras partes, os app modules así como os plugins globais agora pódense recargar sen reinicializar ó NVDA. Utiliza Herramientas -> Recargar plugins en el menú de NVDA o NVDA+control+f3. (#544)
* NVDA agora lembra a posición onde estabas cando voltas a unha páxina anteriormente visitada. Esto aplícase ata que ou o navegador ou NVDA sexan pechados. (#132)
* As liñas braille Handy Tech agora poden utilizarse sen instalar o controlador universal de Handy Tech. (#854)
* Soporte para varias liñas braille Baum, HumanWare e APH. (#937)
* Agora recoñécese a barra de estado en Media Player Classic Home Cinema.
* Agora a liña braille Freedom Scientific Focus 40 Blue pode utilizarse cando se conecte a través do bluetooth. (#1345)

### Cambios

* A información de posición xa non se anuncia de maneira predeterminada nalgúns casos ónde era normalmente incorrecto; ex.: a maioría dos menús, a barra de aplicacións en execución, a área de notificacións, etc. Nemvargantes, esto pode activarse de novo cunha opción engadida no diálogo de Opcións de presentación de obxectos.
* Axuda de Teclado renomeouse a Axuda de entrada para refrexar que se manexa entrada dende outras fontes que o teclado.
* A localización dun script no código xa non se anuncia na axuda de entrada posto que é irrelevante e críptica para o usuario.
* Cando NVDA detecta que se colgou, continúa interceptando  as teclas modificadoras de NVDA, aíndaque deixa pasar todas as demáis teclas do sistema. Esto prevén ó usuario de conmutar inintencionalmente o BlogMaius, etc. Se premen unha tecla modificadora de NVDA sen realising NVDA has frozen. (#939)
* Se as teclas se manteñen pulsadas despóis de utilizar a orden de deixar pasar, todas as teclas (incluindo repeticións de teclas) agora pásanse ata que a última tecla  sexa soltada.
* Se unha tecla modificadora de NVDA se preme dúas veces en sucesión rápida para pasala e a segunda presionada está pulsada, todas as teclas repetidas agora pasaránse tamén.
* As teclas subir, baixar volume e silenciar agora anúncianse na Axuda de Entrada. Esto podería ser de utilidade se o usuario non sabe que fan esas teclas.
* A tecla rápida para o elemento Cursor de Revisión no menú de Preferencias do NVDA foi cambiado de r a c para eliminar o conflicto co elemento de Opcións de Braille.

### Corrección de Erros

* Cando se engade unha nova entrada do diccionario da fala, o título do diálogo agora é "Engadir Entrada de Diccionario" en lugar de "Editar entrada de diccionario". (#924)
* Nos diálogos do diccionario da fala, o contido das columnas da Expresión Regular e sensible ás maiúsculas da lista de entradas de diccionario  preséntase agora na lingua configurada no NVDA en lugar de sempre en Inglés.
* En AIM, a información de posición agora anúnciase en árbores.
* Nas barras de deslizamiento no diálogo Opcións de Voz, flecha arriba/rePáx/inicio agora incrementan a opción e flecha abaixo/AvPáx/fin decreméntana.  Anteriormente, ocurría o oposto, o cal non é lóxico e é inconsistente cas opcións do grupo synth. (#221)
* Nos modos virtuais ca distribución de pantalla deshabilitada, xa non aparecen algunhas extranas liñas en branco.
* Se unha tecla modificadora de NVDA se preme dúas veces rápidamente pero hai unha tecla premeda intervindo, a tecla modificadora de NVDA xa non pasa na segunda presión.
* As teclas de puntuación agora fálanse na axuda de entrada cando a fala da puntuación estea desactivada. (#977)
* No diálogo Opcións de Teclado, os nomes de distribución de teclado agora preséntanse na lingua configurada para o NVDA en lugar de sempre en Inglés. (#558)
* Correxido un problema onde algúns elementos se renderizaban como valdeiros en documentos de Adobe Reader; ex.: as ligas na táboa de contido da Guía do usuario do Apple iPhone IOS 4.1.
* O botón "Utilizar opcións actuais gardadas no logon e outras pantallas seguras" no diálogo de Opcións Xerais de NVDA, funciona se se utilizou inmediatamente despois de que NVDA sexa instalado novamente pero antes de que unha pantalla segura aparecera.  Anteriormente, NVDA anunciaba que o copiado tivo éxito, pero actualmente non tiña efecto. (#1194)
* Xa non é posible ter dous diálogos de opcións do NVDA abertos simultáneamente. Esto corrixe erros onde un diálogo aberto depende doutro diálogo aberto; é dicir, cambiar o sintetizador mentres o diálogo Opcións de Voz está aberto. (#603)
* En sistemas co UAC activado, o botón "Utilizar opcións actualmente gardadas no logon e pantallas seguras" no diálogo de Opcións Xerais do NVDA, xa non falla despois do UAC se o nome da conta do usuario contén un espazo. (#918)
* En Internet Explorer e outros controis MSHTML, NVDA utiliza agora a URL como un derradeiro resorte para determinar o nome dunha liga, máis que presentar ligas valdeiras. (#633)
* NVDA xa non ignora o foco nos menús de AOL Instant Messenger 7. (#655)
* Anunciar a etiqueta correcta para erros no diálogo do corrector de ortografía de Microsoft Word (ex.: Non en diccionario, erro gramatical, pontuación). Anteriormente todos se anunciaban como erro gramatical. (#883)
* Tecleando no Microsoft Word mentres se utiliza unha liña braille xa non debería causar que sexa tecleado texto ilexible, e un extrano colgue cando se preme un sensor de seguemento braille en documentos de Word foi correxido. (#1212) Non obsstante unha limitación é que o texto en árabe pode non lerse xa en Word 2003 e superior, mentres se utiliza unha liña braille. (#627)
* Cando se preme a tecla supr nun campo de edición, o texto/cursor nunha liña braille agora debería actualizarse sempre apropriadamente para reflexar o cambio. (#947)
* Os cambios en páxinas en documentos Gecko2 (Ex.: Firefox 4) mentres se abren múltiples pestanas agora refléxase  adecuadamente por NVDA. Anteriormente só os cambios na primeira pestana se reflexaban. (Mozilla bug 610985)
* NVDA agora pode anunciar apropriadamente as suxerencias para erros gramaticais e de puntuación no diálogo do corrector de ortografía de Microsoft Word. (#704)
* En Internet Explorer e outros controis MSHTML, NVDA xa non presenta áncoras de destiño como ligas valdeiras no seu modo virtual. No seu lugar, estas áncoras agáchanse segundo debería ser. (#1326)
* A navegación de obxectos sobre e dentro de brupos estándar de windows xa non rompe e é asimétrico.
* En Firefox e outros controis baseados en Gecko, NVDA xa non se queda pegado nun submarco se remata cargando antes de outro documento.
* NVDA agora anuncia apropriadamente o seguinte caracter cando se elimina un caracter co suprimir do teclado numérico. (#286)
* Na pantalla de autentificación de Windows XP, O nome de usuario anúnciase unha vez de novo cando o usuario seleccionado se cambiou.
* Correxidos problemas cando ó ler texto en consolas de ordes de Windows o anunciado de números de liña está activado.
* O diálogo de lista de elementos para modos virtuais agora é utilizable por usuarios videntes.  Todos os controis son visibles en pantalla. (#1321)
* A lista de entradas no diálogo Diccionarios da fala, agora é máis lexible por usuarios videntes.  A lista agora é bastante grande para amosar todas as súass columnas en pantalla. (#90)
* En liñas braille ALVA BC640/BC680 NVDA xa non fai caso omiso das teclas da liña que aínda están sendo pulsadas despois que outra tecla sexa liberada.
* Adobe Reader X xa non rompe cando se pecha un documento sen opcións non etiquetadas antes de que apareza o diálogo de procesamento. (#1218)
* NVDA agora cambia ó controlador de liña braille apropriado cando tornes á configuración gardada. (#1346)
* O asistente de proxecto do Visual Studio 2008 lese correctamente novamente. (#974)
* NVDA xa non falla compretamente ó traballar en aplicacións que conteñan caracteres non ASCII no seu nome do executable. (#1352)
* Cando se le por liñas en AkelPad co salto de palabras activado, NVDA xa non le o primeiro carácter da liña seguinte no final da liña actual.
* No editor de código do Visual Studio 2005/2008, NVDA xa non le todo o texto despois de cada carácter tecleado. (#975)
* Correxido o problema onde algunhas liñas braille non se limpiaban correctamente cando NVDA se pechaba ou se cambiaba a liña braille.
* O foco inicial xa non se fala nalgunhas ocasións dúas veces cando NVDA arrinca. (#1359)

### Cambios para Desenroladores

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
* the appModule events: event_appLoseFocus and event_appGainFocus have now been renamed to event_appModule_loseFocus and event_appModule_gainFocus respectivly, in order to keep the naming sintax the same between appModules and treeInterceptors etc.
* All braille display drivers should now use braille.BrailleDisplayDriver instead of braille.BrailleDisplayDriverWithCursor.
 * The cursor is now managed outside of the driver.
 * Existing drivers need only change their class statement accordingly and rename their _display method to display.

## 2010.2

As características máis notables de esta versión inclúen unha grande simplificación da navegación de obxectos; modos virtuais para contido de Adobe Flash; acceso a moitos controi anteriormente inaccesibles capturando texto escribido á pantalla; revisión chan de texto na pantalla; soporte para documentos de IBM Lotus Symphony; anunciado de cabeceiras de fila e columna de táboa en Mozilla Firefox; unha mellora significativa da documentación do usuario.

### Novas Características

* A navegación por obxectos co cursor de revisión foi moi simplificada. O cursor de revisión agora exclúe obxectos que non sexan útiles para o usuario; é dicir, obxectos só utilizados para propósitos de deseño e obxectos non dispoñibles.
* En aplicacións que utilizan o Java Access Bridge (incluindo OpenOffice.org), o formato agora pode informarse nos controis de texto. (#358, #463)
* Cando se move o rato sobre celdas en Microsoft Excel, NVDA anunciaráas apropriadamente.
* En aplicacións que utilizan o Java Access Bridge, o texto dun diálogo agora anúnciase cando o diálogo apareza. (#554)
* Agora pódese utilizar un modo virtual para navegar polo contido de adobe Flash. Navegar por obxectos e interactuar cos controis directamente (activando o modo foco) Xa se soporta. (#453)
* Os controis de texto editable no IDE Eclipse, incluindo o editor de código, agora son accesibles. Debes utilizar Eclipse 3.6 ou superior. (#256, #641)
* NVDA agora pode recuperar a maioría do texto escrito na pantalla. (#40, #643)
 * Esto permite a lectura de controis que non expoñen información en formas máis directas/fiables.
 * Os controis que se accesibilizan por esta característica inclúen: algúns elementos de menú que amosan iconos (ex.: O menú Abrir con en ficheiros en Windows XP) (#151), campos de texto editables en aplicacións Windows Live (#200), a lista de erros en Outlook Express (#582), o control de texto editable en TextPad (#605), listas en Eudora, moitos controis en Australian E-tax e a barra de fórmulas en Microsoft Excel.
* Soporte para o editor de código en Microsoft Visual Studio 2005 e 2008. Ó menos requírese Visual Studio Standard; esto non funciona nas edicións Express. (#457)
* Soporte para documentos en IBM Lotus Symphony.
* Soporte primario e experimental paraGoogle Chrome. Por favor ten en conta que o soporte para lectores de pantalla de Chrome está lonxe de compretarse e requerirá traballo adicional tamén en NVDA. Necesitarás unha compilación de desenrolo recente de Chrome para probar esto.
* O estado das teclas conmutables (Bloq Maius, bloq núm e bloqueo de desprazamento) agora amósase en braille cando se pulsan. (#620)
* Os globos de axuda agora amósanse en braille cando aparezan. (#652)
* Engadido un controlador para a liña braille MDV Lilli. (#241)
* Cando se selecciona unha fila ou unha columna completa en MS Excel cas teclas de atallo shift+espazo e control+espazo, a nova selección agora anúnciase (#759)
* As cabeceiras de fila e columna agora poden anunciarse. Esto é configurable dende o diálogo de preferencias de formato de documento.
 * Actualmente, esto sopórtase en documentos en aplicacións de Mozilla como Firefox e Thunderbird. (#361)
* Introducidas ordes para a revisión chan: (#58)
 * NVDA+7 teclado numérico cambia a revisión plana, poñendo o cursor de revisión na posición do obxecto actual, permitíndoche revisar a pantalla (ou un documento se se está dentro dun) cas ordes de revisión de texto.
 * NVDA+1 teclado numérico move o cursor de revisión ó obxecto representado polo texto na posición do cursor de revisión, permitíndoche navegar por obxectos dende ese punto.
* As opcións de usuario actuais do NVDA poden copiarse para utilizarse nas pantallas de autentificación/UAC, premendo un botón no diálogo Opcións Xerais.
* Soporte para Mozilla Firefox 4.
* Soporte para Microsoft Internet Explorer 9.

### Ccambios

* Ler todo no navegador de obxectos  (NVDA+máis do teclado numérico), seguinte obxecto en fluxo do navegador de obxectos (NVDA+shift+6 do teclado numérico) e anterior obxecto en fluxo no navegador de obxectos (NVDA+shift+4 do teclado numérico) foron eliminados de momento, debido a fallos e para liberar as teclas para outras posibles características.
* No diálogo de sintetizadores de NVDA, agora só se amosa o sintetizador listado. Anteriormente, prefixábase co nome do controlador, que só é relevante internamente.
* Cando se está en aplicacións empotradas ou modos virtuais dentro doutro modo virtual (ex.: Flash), agora podes premer nvda+control+espazo para saír da aplicación empotrada ou modo virtual, ó documento principal. Anteriormente, nvda+espazo   utilizábase para esto. Agora nvda+espazo é só específicamente para conmutar os modos revisión/foco nos modos virtuais.
* Se ó visor de voz (activable no menú Ferramentas) se lle deu o foco (ex.: fíxose clic) o texto novo non aparecerá no control ata que o foco se mova. Esto permítese para seleccionar o texto con maior facilidade (ex.: para copiar).
* O visualizador do Rexistro e a consola de Python maximízanse cando se activen.
* Cando se enfoca unha folla de cálculo en MS Excel, e hai máis dunha celda seleccionada, anúnciase o alcance da selección, en lugar de só a celda activa. (#763)
* O gardado da configuración, e o cambio de opcións sensibles en particular, agora desactívase cando se execute en modo seguro (nas pantallas de autentificación/UAC).
* Actualizado o sintetizador de voz eSpeak a 1.44.01.
* Se NVDA xa está executándose, activando o atallo de teclado do NVDA no escritorio (que é o premedo de control+alt+n) reiniciará ó NVDA.
* Elimínase a caixa de verificación anunciar texto baixo o rato do diálogo Opcións do Rato e reenprázase cunha caixa de verificación Activar seguemento do Rato, que mellora o emparellado do conmutado do script de seguemento do rato (NVDA+m).
* Actualízase a distribución de teclado laptop tal que inclúa todas as ordes dispoñibles na distribución desktop e funciona correctamente en teclados non ingleses. (#798, #800)
* Melloras significativas e actualizacións á documentación do usuario, incluindo documentación das ordes de teclado laptop e sincronización da Referencia Rápida de Ordes de Teclado ca Guía do Usuario. (#455)
* Actualizado o transcriptor braille liblouis á versión 2.1.0. Notablemente, esto corrixe algúns problemas relacionados co Braille Chinés

### Corrección de Fallos

* En µTorrent, o elemento enfocado na lista de torrents xa non informa repetidamente ou escamotea o foco cando se abre un menú.
* En µTorrent, os nomes dos ficheiros na listaxe de contidos de Torrent agora anúncianse.
* En aplicacións de Mozilla, agora o foco detéctase correctamente cando aterriza nunha táboa valdeira ou árbore.
* En aplicacións de Mozilla, "non marcado" agora infórmase correctamente para controis marcables como celdas de táboa marcables. (#571)
* En aplicacións de Mozilla, o texto de diálogos aria correctamente implementados xa non se ignora e agora informarase cando o diálogo apareza.
* En Internet Explorer e outros controis MSHTML, o atributo nivel de ARIA agora se cumpre correctamente.
* En Internet Explorer e outros controis MSHTML, o rol ARIA agora escóllese sobre outro tipo de información para dar unha experiencia de ARIA moito máis correcta e predecible.
* Detido un raro colgue en Internet Explorer cando se navega por marcos ou iFrames.
* En documentos de Microsoft Word, as liñas de dereita a esquerda (como no texto árabe) poden lerse de novo. (#627)
* Forte reducción de retraso cando grandes cantidades de texto amosábanse nunha consola de ordes de Windows en sistemas de 64 bits. (#622)
* Se Skype xa está arrancado  cando arranque o NVDA, xa non é necesario reiniciar Skype para habilitar a accesibilidade. Esto pode tamén ser certo para outras aplicacións que comproben a bandeira do sistema para o lector de pantallas .
* En aplicacións de Microsoft Office, NVDA xa non se colga cando se premeu falar primeiro plano (NVDA+b) ou cando se navegan algúns obxectos en barras de ferramentas. (#616)
* Correxida a fala incorrecta de números que conteñen un 0 despois dun separador; ex.: 1.023. (#593)
* Adobe Acrobat Pro e Reader 9 xa non se colgan cando se pecha un ficheiro ou se levan a cabo outras certas tarefas. (#613)
* A selección anúnciase agora cando se preme control+a para seleccionar todo o texto nalgúns controis de texto editables como en Microsoft Word. (#761)
* Nos controis de Scintilla (ex.: Notepad++), O texto xa non se selecciona incorrectamente cando NVDA move o cursor do sistema tal como durante ler todo. (#746)
* É posible de novo revisar o contido de celdas en MS Excel co cursor de revisión.
* NVDA pode ler de novo por liñas en certos campos de área de texto problemáticos en Internet Explorer 8. (#467)
* Windows Live Messenger 2009 xa non se pecha inmediatamente despois de iniciarse mentres NVDA se executa. (#677)
* Nos navegadores web, xa non é necesario premer tab para interactuar cun obxecto empotrado (tal como contido Flash) despois de premer intro no obxecto empotrado ou voltando dende outra aplicación. (#775)
* En controis de Scintilla (ex.: Notepad++), o comezo de liñas longas xa non se curta cando sobrepasan a pantalla. Tamén, estas liñas longas amosaránse correctamente en braille cando se seleccionen.
* En Loudtalks, agora é posible acceder á lista de contactos.
* A URL do documento e "MSAAHTML Registered Handler" xa non se anuncia ás veces falso en Internet Explorer e outros controis MSHTML. (#811)
* En árbores no IDE de Eclipse,  o elemento enfocado anteriormente xa non se anuncia incorrectamente cando o foco se move a un novo elemento.
* NVDA agora funciona correctamente nun sistema onde o actual directorio de traballo se eliminara da ruta de búsqueda das DLL (configurando a entrada de rexistro CWDIllegalInDllSearch a 0xFFFFFFFF). ten en conta que esto non é relevante para a maioría dos usuarios. (#907)
* Cando as ordes de navegación de táboas se usen fora dunha en Microsoft Word, "borde de táboa" xa non falan despois de "non en táboa". (#921)
* Cando as ordes de navegación de táboa non podan mover debido a estar no borde dunha táboa en Microsoft Word, "borde de táboa" agora fala na lingua configurada do NVDA en lugar de sempre en inglés. (#921)
* En Outlook Express, Windows Mail e Windows Live Mail, o estado das caixas de verificación en listaxes de regras de mensaxes agora anúnciase. (#576)
* A descripción das regras de mensaxes agora pode lerse en Windows Live Mail 2010.

## 2010.1

Esta revisión enfócase principalmente en corrección de fallos e melloras á experiencia do usuario, incluindo algunhas correccións significativas de estabilidade.

### Novas características

* NVDA xa non falla ó arrancar nun sistema sen dispositivos de saída de audio. Obviamente, será necesario utilizar unha líña braille ou o Display synthesiser para a saída neste caso. (#425)
* Foi engadida unha caixa de verificación Anunciar rexións ó diálogo de Opcións de formato de Documento que che permite configurar se NVDA debería anunciar rexións en documentos web. Para compatibilidade ca versión anterior, a opción está activada de maneira predeterminada.
* Se falar teclas de ordes está activada NVDA agora anunciará os nomes das teclas multimedia (ex.: reproducir, deter, páxina de comezo, etc.) cando sexan premedas. (#472)
* NVDA agora anuncia a palabra que estea sendo eliminada cando se prema control+retroceso en controis que o soporten. (#491)
* As flechas de cursor agora poden ser utilizadas na xanela do formateador Web para navegar e ler o texto. (#452)
* A listaxe de entradas na libreta de enderezos de Microsoft Office Outlook agora está soportada.
* Mellor soporte de documentos empotrados editables do NVDA (modo de deseño) en Internet Explorer. (#402)
* Un novo script (nvda+shift+menos do teclado numérico) permíteche mover o foco do sistema ó navegador de obxectos actual.
* Novos scripts para bloquear e desbloquear os botóns esquerdo e dereito do rato. Útil para levar a cabo operacións de arrastrar e soltar. shift+dividir do teclado numérico para bloquear/desbloquear o esquerdo, shift+multiplicar do teclado numérico para bloquear/desbloquear o dereito.
* Novas táboas de transcripción braille: braille computerizado Alemán de 8 puntos, Alemán grao 2, braille computerizado Finés de 8 puntos, Chinés (Hong Kong, Cantonés), Chinés (Taiwan, Mandarín). (#344, #369, #415, #450)
* Agora é posible desactivar a creación do atallo do escritorio (e así a tecla de atallo) cando se instala o NVDA. (#518)
* NVDA agora pode utilizar IAccessible2 cando estean presentes en aplicacións de 64 bit. (#479)
* Mellorado o soporte para rexións vivas en aplicaciónes de Mozilla. (#246)
* A API NVDA Controller Client proporciónase agora para permitir ás aplicacións controlar ó NVDA; ej.: para falar texto, silenciar a voz, amosar unha mensaxe en Braille, etc.
* As mensaxes de información e erro agora lense na pantalla do logon no Windows Vista e no Windows 7. (#506)
* No Adobe Reader, os formularios PDF interactivos desenvolvidos co Adobe LiveCycle agora son soportados. (#475)
* No Miranda IM, NVDA agora le automáticamente as mensaxes de entrada en xanelas de chat se o anunciado de cambios de contido dinámico se activaron. Tamén, foron engadidas as ordes para anunciar as tres mensaxes máis recentes (NVDA+control+número). (#546)
* Agora sopórtanse campos de entrada de texto en contido de Adobe Flash. (#461)

### Cambios

* A mensaxe de axuda de teclado extremadamente verboso no menú de Inicio de Windows 7 Xa non se anuncia.
* O sintetizador Display agora foi reemplazado cun novo Visualizador de Fala. Para activalo, escolle Visualizador da Fala dende o menú Ferramentas. O Visualizador da Fala pode ser utilizado independientemente de con que outro sintetizador de voz estés a traballar.
* As mensaxes na liña braille serán rexeitados automáticamente se o usuario preme unha tecla que signifique un cambio como o movemento do foco. Anteriormente a mensaxe sempre permanecería segundo o seu tempo configurado.
* A Opción para axustar o braille ó foco ou ó cursor de revisión (NVDA+control+t) agora pode ser tamén configurada dende o diálogo de opcións braille, e agora tamén se garda na configuración do usuario.
* Actualizado o sintetizador de voz eSpeak a 1.42.04.
* Actualizado o transcriptor braille liblouis a 1.8.0.
* Nos modos virtuais, o anunciado de elementos cando se move por caracteres ou palabras foi moi mellorado. Anteriormente, era anunciada unha grande cantidade de información irrelevante e o anunciado era moi diferente a eso cando se move por liñas. (#490)
* A tecla Control agora sinxelamente detén a voz como outras teclas, en lugar de pausar a voz. Para pausar/reanudar a voz, utiliza a tecla shift.
* Xa non se anuncia a conta de filas e columnas de táboa cando se anuncian os cambios do foco, posto que este anunciado é demasiado verboso e normalmente non é útil.

### Corrección de Fallos

* NVDA xa non falla ó arrancar se o soporte UI Automation parece estár dispoñible pero falla ó inicializarse por algunha razón. (#483)
* Todo o contido dunha fila dunha táboa xa non é anunciado ás veces cando se move o foco entre celdas en aplicacións de Mozilla. (#482)
* NVDA xa non se retrasa durante un tempo longo cando se expanden elementos da vista en árbore que conteñan unha cantidade moi grande de sub-elementos.
* Cando se listan voces SAPI 5, NVDA agora intenta detectar voces defectuosas e excluilas do diálogo de Opcións de Voz e do grupo de Opcións de Sintetizador. Anteriormente, cando había unha voz problemática, o controlador SAPI 5 de NVDA fallaba algunhas veces ó iniciarse.
* Os modos virtuais agora anuncian as teclas de atallo do obxecto opción que se atopa no diálogo Presentación de Obxectos. (#486)
* Nos modos virtuais, as coordenadas de fila/columna xa non se len incorrectamente por cabeceiras de fila e columna cando o anunciado de táboas está desactivado.
* Nos modos virtuais, as coordenadas de fila/columna agora son correctamente lidas cando abandoas unha táboa e logo voltas a entrar na mesma celda da táboa sen visitar outra celda primeiro; ex.: premendo flecha arriba e logo flecha abaixo sobre a primeira celda dunha táboa. (#378)
* As liñas en branco nos documentos do Microsoft Word e dos controis de edición de Microsoft HTML agora amósanse apropriadamente en liñas braille. Anteriormente NVDA amosaba a frase actual na liña, non a liña actual para estas situacións. (#420)
* Múltiples correccións de seguridade cando se executa ó NVDA no Logon de Windows e en outros Escritorios Seguros.
* A posición do cursor (cursor do sistema) agora actualízase correctamente cando se leva a cabo unha Lectura Compreta que se pase do final da pantalla, en campos de edición estándar de Windows e documentos de Microsoft Word. (#418)
* Nos modos virtuais, o texto xa non é incluído incorrectamente por imaxes dentro de ligas e cliqueables que son marcados como irrelevantes para os lectores de pantalla. (#423)
* Correccións para a distribución de teclado laptop. (#517)
* Cando o braille está seguindo á revisión cando enfocas nunha xanela de consola do dos, o cursor de revisión agora pode navegar apropriadamente polo texto na consola.
* Mentres se traballa con TeamTalk3 ou TeamTalk4 Classic VU a barra de progreso contador na xanela principal xa non se anuncia segundo se actualiza. Tamén os caracteres especiales poden lerse apropriadamente na xanela de entrada do chat.
* Os elementos xa non son falados dúas veces no menú de inicio de Windows 7. (#474)
* Activando ligas á mesma páxina en Firefox 3.6 móvese o cursor apropriadamente no modo virtual ó lugar correcto na páxina.
* Correxido o problema onde algún texto non era proporcionado en Adobe Reader en certos documentos PDF.
* NVDA xa non fala incorrectamente certos números separados por un guión; ex.: 500-1000. (#547)
* En Windows XP, NVDA xa non causa que Internet Explorer se colgue cando se conmutan caixas de verificación en Windows Update. (#477)
* Cando se utiliza no sintetizador eSpeak incorporado, simultáneamente voz e pitidos xa non causa colgues intermitentes en algúns sistemas. Esto era máis evidente, por exemplo, cando se copian cantidades grandes de datos en Windows Explorer.
* NVDA xa non anuncia que un documento de Firefox se encheu (ex.: debido a unha actualización ou refresco) cando ese documento está en segundo plano. Esto tamén causaba que a barra de estado da aplicación en primeiro plano sexa anunciada falsamente.
* Cando se cambian distribucións de teclado de Windows (con control+shift ou alt+shift), o nome completo da distribución anúnciase en voz e braille. Anteriormente só se anunciaba en voz, e distribucións alternativas (ex.: Dvorak) non se anunciaban.
* Se o anunciado de táboas se desactivou, a información de táboa xa non se anuncia cando o foco ccambie.
* Certos controis estándar de vista en árbore en aplicacións de 64 bit (ex.: a vista en árbore de contidos en Microsoft HTML Help) agora son acesibles. (#473)
* Arranxados algúns problemas con mensaxes de rexistro que conteñen caracteres non ASCII. Esto podía provocar erros expúreos nalgúns casos en sistemas que non estean en inglés. (#581)
* A información no diálogo Acerca de no NVDA agora aparece na lingua configurada do usuario en lugar de aparecer sempre en inglés. (#586)
* Xa non se atopan problemas ao se usar o anel de opcións do sintetizador despois de que a voz se cambie a unha que teña menos opcións que a voz anterior.
* En Skype 4.2, os nomes de contacto xa non se falan dúas veces na listaxe de contactos.
* Arranxadas algunhas fugas de memoria potencialmente importantes na interface gráfica de usuario e nos búferes virtuais. (#590, #591)
* Solucionado un ero desagradable nalgúns sintetizadores SAPI 4 que estaba causando frecuentes fallos e bloqueos de NVDA. (#597)

## 2009.1

O máis suliñable desta versión inclúe o soporte para edicións de 64 bit de Windows; soporte moi mellorado para os documentos de Microsoft Internet Explorer e de Adobe Reader; soporte para Windows 7; a leitura das pantallas de  logon de Windows, control+alt+supr e el control de contas de usuario (UAC); e a capacidade para interactuar cos contidos de Adobe Flash e de Sun Java en páxinas web. Tamén tivemos varias correccións siñificativas de estabilidade e melloras á experiencia de usuario xeral.

### Novas Características

* ¡Soporte oficial para edicións de 64 bit de Windows! (#309)
* Engadido un controlador de sintetizador para o sintetizador Newfon. Ten en conta que esto require unha versión especial de Newfon. (#206)
* Nos modos virtuais, o modo foco e o modo revisión agora poden ser anunciados utilizando sons en lugar da voz. Esto está activado de maneira predeterminada. Pode ser configurado dende o diálogo de Modo Virtual. (#244)
* NVDA xa non cancela a voz cando as teclas de control do volume son premedas no teclado, permitindo ó usuario cambiar o volume e escoitar os resultados actuais inmediatamente. (#287)
* Reescribido Completamente o soporte para documentos de Microsoft Internet Explorer e Adobe Acrobat. Este soporte foi unificado co soporte interno utilizado por Mozilla Gecko, así características como a interpretación máis rápida de páxina, navegación extensa e rápida, lista de ligas, selección de texto, modo foco automático e soporte de braille están agora dispoñibles con estos documentos.
* Mellorado o soporte para o control da selección de data atopado no diálogo de propiedades de data/Hora en Windows Vista.
* Mellorado o soporte para o menú de inicio Moderno XP/Vista (específicamente os menús Todos os programas e lugares). A información de nivel apropriada é agora anunciada.
* A cantidade de texto que é anunciada co movemento do rato, é agora configurable dende o diálogo Opcións do rato. unha elección de párrafo, liña, palabra ou caracter pode ser feita.
* Anúncianse erros de ortografía baixo o cursor en Microsoft Word.
* soporte para a corrección ortográfica en Microsoft Word 2007. Soporte Parcial podería estar dispoñible para versións anteriores de Microsoft Word.
* soporte para Windows Live Mail (específicamente agora as mensaxes de texto chan poden seren lidos).
* En Windows Vista, se o usuario se move ó escritorio seguro (ou porque un diálogo de control do UAC aparece, ou porque foi premedo control+alt+supr), NVDA anunciará o feito de que o usuario agora está no escritorio seguro.
* NVDA pode anunciar texto baixo o rato dentro de xanelas da consola do dos.
* Soporte para UI Automation a traverso da API cliente UI Automation dispoñible en Windows 7, así como se mellora a experiencia de NVDA en Windows 7.
* NVDA pode ser configurado para iniciarse automáticamente despois de que te identifiques no Windows. a opción está  no diálogo Opcións Xerais.
* NVDA pode ler pantallas seguras de Windows como a autentificación de Windows (logon), control+alt+suprimir e pantallas do UAC en Windows XP e posteriores. A leitura das pantallas de autentificación de Windows (logon) pode ser configurada dende o diálogo de Opcións Xerais. (#97)
* Engadido un controlador para as liñas braille da serie Optelec ALVA BC6.
* Cando se navega por documentos web, agora podes premer n e shift+n para saltar cara adiante e cara atrás pasando bloques de ligas, respectivamente.
* Cando se navega por documentos web, as rexións de ARIA agora son anunciadas, e podes moverte adiante e atrás a traverso delas utilizando d e shift+d, respectivamente. (#192)
* O diálogo de lista de ligas dispoñible cando se exploran documentos web convertiuse agora nun diálogo Lista de Elementos que pode listar ligas, cabeceiras e rexións. As cabeceiras e rexións son presentadas xerárquicamente. (#363)
* O novo diálogo Lista de Elementos filtra a lista segundo escribas para conter só aquéles elementos incluído o texto que foi tecleado. Podes premer retroceso para limpiar o filtro tal que todos os elementos sexan presentados novamente. (#173)
* As versións portátiles do NVDA agora procuran no directorio 'userConfig' dentro do directorio de NVDA, as configuracións do usuario. Como a versión do instalador, esto mantén a configuración do usuario separada do NVDA.
* Os módulos personais de apps, os controladores de liñas braille e os controladores de sintetizadores agora poden ser almacenados  no directorio da configuración do usuario. (#337)
* Os modos virtuais agora son interpretados en segundo plano, permitindo ó usuario interactuar co sistema ata certo punto durante o proceso de interpretado. O usuario será notificado de que o documento está sendo interpretado se lle levará máis dun segundo.
* Se NVDA detecta que se colgou por algunha razón, Pasará automáticamente por todas as pulsacións para que o usuario teña unha mellor posibilidade de recuperación do sistema.
* Soporte para arrastrar e soltar en ARIA en Mozilla Gecko. (#239)
* A selección do título do documento e liña actual agora é falada cando movas o foco dentro dun modo virtual. Esto fai que o comportamento cando se move o foco nos modos virtuais sexa consistente como nun documento normal. (#210)
* Nos modos virtuais, agora podes interactuar cos obxectos empotrados (como contidos Adobe Flash e Sun Java) premendo intro sobre o obxecto. Se é accesible, podes entón tabular por el como calquera outra aplicación. Para voltar o foco ó documento, preme NVDA+espacio. (#431)
* Nos modos virtuais, o e shift+o moven ó seguinte e ó anterior obxecto empotrado, respectivamente.
* NVDA agora pode acceder completamente a aplicacións que se executen como administrador en Windows Vista e posterior. Debes instalar unha versión oficial de NVDA para que esto funcione. Esto non funciona para versións portables e snapshots. (#397)

### Cambios

* NVDA xa non anuncia "NVDA activado" cando arranca.
* Os sons de arranque e finalización agora son reproducidos utilizando o dispositivo de saída de audio configurado en NVDA en lugar do dispositivo de audio predeterminado de Windows. (#164)
* O anunciado das barras de progreso foi mellorado. O máis notable é que agora podes configurar ó NVDA para anunciálas a traverso da voz e pitidos ó mesmo tempo.
* Algúns roles xenéricos, como panel, aplicación e marco, xa non son anunciados  no foco a menos que o control non teña nome.
* A orde de copia de revisión (NVDA+f10) copia o texto dende enriba da marca de comezo e inclúe a posición actual de revisión, en lugar de excluir a posición actual. Esto permite que o último caracter de unha liña seren copiado, o que non era posible anteriormente. (#430)
* O script  navigatorObject_where (ctrl+NVDA+numpad5) foi eliminado. Esta combinación de teclas non funcionaba nalgúns teclados, nin o script era atopado útil.
* O script navigatorObject_currentDimentions foi remapeado a NVDA+supr do teclado numérico. A antiga combinación de teclas non funcionaba nalgúns teclados. Este script agora tamén anuncia o ancho e o alto do obxecto en lugar das coordenadas dereita/inferior.
* Mellorado o rendemento (especialmente en netbooks) cando ocurren moitos pitidos en sucesión rápida; ej.: movementos rápidos co rato cas coordenadas de audio activadas. (#396)
* Os sons de erro do NVDA xa non se reproducen en versións candidatas e finais. Ten een conta que os erros aínda se rexistran.

### Corrección de Erros

* Cando o NVDA está executándose dende unha ruta de DOS 8.3, pero está instalado na ruta longa relacionada (ej.: progra~1 versus program files) NVDA identificará correctamente que é unha copia instalada e carga apropriadamente as opcións de usuario.
* A fala do título da xanela actual en primeiro plano con nvda+t funciona agora correctamente cando se está nos menús.
* O braille xa non amosa información innecesaria no seu contexto de foco tal como paneis non etiquetados.
* Detense o anunciado de algunha información innecesaria cando o foco cambia como paneis raíz, paneis solapados e paneis deslizables en aplicacións Java ou Lotus.
* Faise que o campo de procurar palabras clave  no visualizador de Axuda de Windows (CHM) sexa moito máis usable. Debido á cantidade de fallos nese control, a palabra clave actual non podería ser lida xa que estaría continuamente cambiando.
* Anúncianse os números correctos de páxina en Microsoft Word se a numeración de páxina foi específicamente configurada  no documento.
* Mellor soporte para campos de edición atopados en diálogos de Microsoft Word (ex.: o diálogo Fontes). agora é posible navegar estos controis cas flechas.
* mellor soporte para consolas do Dos. específicamente: NVDA agora pode ler o contido de consolas particulares que Sempre se pensou que estaban en blanco. Premendo control+break xa non apagan a NVDA.
* En Windows Vista, o instalador de NVDA agora arranca a NVDA con privilexios dun usuario normal cando se requira para executar ó NVDA  na pantalla final.
* O Retroceso agora é manexado correctamente cando se falan palabras ó se escribir. (#306)
* Non se anuncia incorrectamente "Menú inicio" para certos menús de contexto no Windows Explorer/Windows shell. (#257)
* NVDA agora manexa correctamente etiquetas de ARIA en Mozilla Gecko cando non hai outro contido útil. (#156)
* NVDA xa non activa incorrectamente o modo foco automáticamente para campos de texto editable que actualizan o seu valor cando o foco cambia; ex.: https://tigerdirect.com/. (#220)
* NVDA agora intentará recuperarse dalgunhas situacións que anteriormente causarían que se colgara completamente. Poderá tomar sobre 10 segundos para que NVDA detecte e se recupere de tales colgues.
* Cando a lingua do NVDA está axustada a "User default", utiliza a lingua do usuario de Windows configurada en lugar da local de windows.
* NVDA agora recoñece a existencia de controis en AIM 7.
* A orde de deixar pasar a tecla xa non se queda atascada se unha tecla é mantida premeda. Anteriormente, NVDA detiña o aceptado de ordes se esto ocurría e tiña que ser reiniciado. (#413)
* A barra de tarefas xa non é ignorada cando recibe o foco, o que amenudo ocurre cando se sae dunha aplicación. Anteriormente, NVDA comportábase como se o foco non tivera cambiado.
* Cando se len campos de texto en aplicacións que utilizan o Java Access Bridge (incluindo OpenOffice.org), NVDA agora funciona correctamente cando o anunciado de números de liña está activado.
* A orde de copia en revisión (NVDA+f10) manexa elegantemente o caso onde sexa utilizado nunha posición antes do marcador de comezo. Anteriormente, esto podía causar problemas como colgues en Notepad++.
* Certo caracter de control (0x1) xa non causa unha extrana conducta en eSpeak (como cambios  no volume tono) cando se atopa nun texto. (#437)
* A orde anunciar seleción de texto (NVDA+shift+frecha arriba) agora informa con elegancia de que non hay seleción en obxectos que non soporten seleción de texto.
* Arranxado o fallo onde ao premer a tecla intro en certos botóns ou ligazóns de Miranda-IM causaba que o NVDA se conxelase. (#440)
* A liña actual ou seleción agora respétase correctamente ao se deletrear ou copiar o navegador de obxetos actual.
* Arranxouse un erro de Windows que provocaba que se dixera lixo despois do nome dos controis de ligazón nos diálogos de Windows Explorer e Internet Explorer. (#451)
* Arranxado un problema co anunciado da orde de hora e a data (NVDA+f12). anteriormente, anuncciado de data foi truncado nalgúns sistemas. (#471)
* Arranxado o problema onde o indicador do lector de pantalla do sistema ás veces borrábase de xeito inadecuada despois de interactuar con pantallas seguras de Windows. Esto podía causar problemas en aplicacións que comproban o indicador do lector de pantalla como Skype, Adobe Reader e Jart. (#462)
* Nunha caixa combinada de Internet Explorer 6, o elemento activo agora anúnciase cando cambia. (#342)

## 0.6p3

### Novas Características

* Como a barra de fórmulas de Microsoft Excel é inaccesible para NVDA, proporciónase unha caixa de diálogo específico de NVDA para editar cando o usuario prema f2 sobre unha celda.
* Soporte para formato en controis de texto de IAccessible2, incluindo aplicacións de Mozilla.
* Deletrear erros pode ser anunciado agora onde sexa posible. Esto é configurable dende o diálogo de preferencias Formato de Documentos.
* NVDA pode ser configurado para pitar para todas ou só para as barras de progreso visibles. Alternativamente, pode ser configurado para falar os valores das barras de progreso cada 10%.
* As ligas poden agora ser identificadas en controis de edición multiliña.
* O rato pode agora ser movido ó caracter baixo o cursor de revisión  na maioría dos controis de texto editables. Previamente, O rato só podía ser movido ó centro do control.
* Nos modos virtuais, O cursor de revisión agora revisa o texto do modo, antes que só o texto interno do navegador de obxectos (o que amenudo non é útil para o usuario). Esto siñifica que podes navegar o modo virtual xerárquicamente utilizando navegación de obxectos e o cursor de revisión moverá a ese punto  no modo.
* Manexo dalgúns estados adicionais en controis de Java.
* Se a orde de título (NVDA+t) é premeda dúas veces rápidamente, deletrea o título. Se se premeu tres veces, é copiado ó portapapeis.
* A axuda de teclado agora le os nomes das teclas modificadoras cando se premeron soas.
* Os nomes de tecla anunciados pola axuda de teclado están agora traducidos.
* Engadido soporte para o texto recoñecido en campos de SiRecognizer. (#198)
* ¡Soporte para liñas braille!
* Engadida unha orde (NVDA+c) para anunciar o texto  no portapapeis de Windows. (#193)
* agora podes premer escape cando estás en modo foco para voltar ó modo revisión.
* Nos modos virtuais, cando o foco cambia ou o cursor é movido, NVDA pode cambiar automáticamente a modo foco ou modo revisión segundo proceda para o control baixo o cursor. Esto é configurado dende o diálogo de Modo virtual. (#157)
* Reescribido o controlador de sintetizador SAPI4 o que reemplaza ós controladores sapi4serotek e sapi4activeVoice e debería solucionar os problemas atopados con estos controladores.
* A aplicación NVDA agora inclúe un manifesto, o que siñifica que non se executará máis en modo de compatibilidade en Windows Vista.
* O ficheiro de configuración e os diccionarios da Fala son gardados agora  no directorio de datos do usuario se NVDA foi instalado utilizando o instalador. Esto é necesario para Windows Vista e tamén permite a múltiples usuarios ter configuracións individuais para NVDA.
* Engadido soporte para información de posición para controis IAccessible2.
* Engadida a capacidade para copiar texto ó portapapeis utilizando o cursor de revisión. NVDA+f9 axusta a marca de comezo na posición actual do cursor de revisión. NVDA+f10 recupera o texto entre a marca de comezo e a posición actual do cursor de revisión e cópiao ó portapapeis. (#240)
* Engadido soporte para algúns controis de edición  no programa pinacle tv.
* Cando se anuncia texto seleccionado para selecciones longas (512 caracteres ou máis), NVDA fala agora o número de caracteres seleccionados, en lugar de falar toda a selección. (#249)

### Cambios

* Se o dispositivo de saída de audio é axustado para utilizar o dispositivo predeterminado de Windows (Microsoft Sound Mapper), NVDA cambiará agora ó novo dispositivo predeterminado para eSpeak e tons cando o dispositivo predeterminado cambie. Por exemplo, NVDA cambiará a un dispositivo de audio USB se se fai dispositivo predeterminado automáticamente cando se conecte.
* Mellórase o rendemento de eSpeak con algúns controladores de audio en Windows Vista.
* Ler por frase en controis de texto enriquecido se é posible.
* O anunciado de ligas, cabeceiras, listas e citas en documentos é configurado agora  no diálogo de 	* A velocidade é agora a opción predeterminada  no grupo das opcións de voz do sintetizador.
* Mellórase a carga e descarga dos appModules.
* A orde de título (NVDA+t) agora só informa do título en lugar de todo o obxecto. Se o obxecto en primeiro plano non ten nome, o nome de proceso da aplicación é utilizado.
* En lugar de activar e desactivar o paso a traverso do modo virtual, NVDA agora anuncia modo foco (paso por modo virtual activado) e modo revisión (paso por modo virtual desactivado).
* As voces agora son gardadas  no ficheiro de configuración por ID en lugar de por index. Esto fai as opcións de voz máis seguras a traverso dos cambios dos sistemas e as configuracións. A opción de voz non será preservada en todas as configuracións e un erro poderá ser amosado no rexistro a primeira vez que un sintetizador sexa utilizado. (#19)
* O nivel dun elemento de vista de árbore agora é anunciado primeiro se cambiou dende o elemento enfocado anteriormente para todas as vistas en árbore. Anteriormente, esto só ocurría para vistas en árbore nativas de Windows (SysTreeView32).

### Corrección de Erros

* O derradeiro anaco de audio non é cortado xa cando se utilice NVDA co eSpeak nun servidor de escritorio remoto.
* Corríxense problemas co gardado de diccionarios da fala para certas voces.
* Eliminación de retraso cando se mova por outras unidades que non sexan caracter (palabra, liña, etc.) cara o final dos documentos de texto plano longos nos modos virtuais de Mozilla Gecko. (#155)
* Se falar palabras ó se escribir está habilitado, anuncia a palabra cando se prema intro.
* Correxidos algúns grupos de sucesións de caracteres en documentos enriquecidos. preferencias de Formato de Documentos. Esto inclúe modos virtuais de Mozilla Gecko.
* O visualizador do rexistro de NVDA agora utiliza caixas multiliña en lugar de só editar para amosar o log. Esto mellora a leitura por palabras co NVDA e permítelle ler o texto do rexistro máis aló dos 65535 bytes.
* Correxidos algúns fallos relacionados cos obxectos empotrados en controis de edición multiliña.
* NVDA agora le os números de páxina en Microsoft Word. (#120)
* corríxese o fallo cando tabulando cara unha caixa de verificación marcada nun modo virtual de Mozilla Gecko e premendo espazo non anunciaba que a caixa de verificación estaba sendo desmarcada.
* Informa correctamente as caixas de verificación parcialmente marcadas en aplicacións Mozilla.
* Se a selección de texto expándese ou contráese en ambas direccións, le a selección coma un anaco en lugar de dous.
* Cando se le co rato, o texto nos campos de edición de Mozilla Gecko deberían ser agora lido.
* Ler todo non debería causar que certos sintetizadores SAPI5 se colguen.
* Correxido un fallo que siñificaba que cambios  na selección de texto non estiveran sendo lidos en controis estándares de edición de Windows antes do primeiro cambio do foco despois que NVDA fora iniciado.
* Correxido o seguemento do rato en obxectos Java. (#185)
* NVDA xa non anuncia os elementos das árbores Java sen fillos como se estiveran contraídos.
* Anuncia o obxecto co foco cando unha xanela Java é traída ó primeiro plano. Anteriormente, só o obxecto de nivel superior Java era anunciado.
* O controlador do sintetizador eSpeak non se detén xa completamente mentres fala despois de un sinxelo erro.
* Corríxese o fallo mediante o que actualizar parámetros de voz (velocidade, ton, etc.) non foi gardado cando a voz foi cambiada dende o grupo das opcións de sintetizador.
* Mellorada a fala de caracteres e palabras escritas.
* Algún texto novo que anteriormente non era falado en aplicacións da consola de texto (como algún texto de xogos conversacionais) é agora falado.
* NVDA agora ignora cambios do foco nas xanelas en segundo plano. Anteriormente, un cambio do foco en segundo plano podía ser tratado como se o foco real cambiase.
* Mellorada a detección do foco cando se abandoan os menús de contexto. Anteriormente, NVDA amenudo non reaccionaba de todo cando se abandoaba un menú de contexto.
* NVDA agora anuncia cando o menú de contexto é activado  no menú de Inicio.
* O menú de Inicio clásico agora é anunciado como Menú de Inicio en lugar de Menú Aplicación.
* Mellorada a leitura de alertas como aquélas atopadas en Mozilla Firefox. O texto non debería ser lido xa múltiples veces e outra información extrana non será xa lida. (#248)
* O texto enfocable, campos de edición de só leitura non serán xa incluídos cando se recolla o texto de diálogos. Esto corrixe, por exemplo, a leitura automática de toda a aceptación da licencia nos instaladores.
* NVDA xa non anuncia a deselección de texto cando se abandoen algúns controis de edición (exemplo: barra de enderezo en Internet Explorer, campos de enderezo en correo electrónico en Thunderbird 3 ).
* Cando se abran correos en texto plano  en Outlook Express e Windows Mail, o foco está correctamente colocado  na mensaxe lista para que o usuario o lea. Anteriormente o usuario tiña que premer tab ou facer clic sobre a mensaxe en orden a utilizar as teclas do cursor para lelo.
* Correxidos varios problemas maiores ca funcionalidade "falar Teclas de ordes".
* NVDA agora pode ler texto que pase de 65535 caracteres en controis estándar de edición (ex.: un ficheiro grande en Notepad).
* Mellorada a leitura de liñas en campos de edición de MSHTML (mensaxes editables de Outlook Express e campos de entrada de texto en Internet Explorer).
* NVDA xa non se colga ás veces completamente cando se edita texto en OpenOffice. (#148, #180)

## 0.6p2

* Mellorada a voz predeterminada de ESpeak en NVDA
* Engadida unha disposición de teclado para ordenadores portátiles. As disposicións de teclado poden ser configuradas dende o diálogo de Opcións de teclado de NVDA. (#60)
* Soporte para grupos de elementos en controis SysListView32, atopados principalmente en Windows Vista. (#27)
* Informar do estado verificado de elementos de vista en árbore en controis SysTreeview32.
* Engadidas teclas de atallo para moitos dos diálogos de configuración de NVDA
* Soporte para IAccessible2 habilitado para aplicacións como Mozilla Firefox cando se executa ó NVDA dende un medio portátil, sen ter que rexistrar ningún ficheiro Dll en especial
* Correxido un pete ca lista de ligas do modo virtual en aplicacións Gecko. (#48)
* NVDA non debería petar xa con aplicacións Mozilla Gecko como Firefox e Thunderbird se NVDA está executándose con privilexios máis altos que os da aplicación Mozilla Gecko. Ex. NVDA está executándose como Administrador.
* Diccionarios da fala (anteriormente diccionarios de usuario) agora poden ser ou sensibles ás maiúsculas ou insensibles, e os patróns poden ser opcionalmente expresións regulares. (#39)
* Si ou non NVDA utiliza un 'modo de disposición de pantalla' para os documentos do modo virtual pode agora ser configurado dende un diálogo de opcións
* Non se informa máis sobre ancoraxe de etiquetas sen href en documentos Gecko como ligas. (#47)
* A orde procurar de NVDA agora lembra que é o último que se procurou, a traverso de todas as aplicacións. (#53)
* Correxidos problemas onde o estado marcado non era anunciado en algunhas caixas de verificación e botóns de radio nos modos virtuais
* O modo de paso a traverso do modo virtual é específico agora para cada documento, en lugar de globalmente para NVDA. (#33)
* Correxida alguna lentitude cos cambios do foco e interrupción incorrecta da voz que algunhas veces ocurría cando se utiliza NVDA en un sistema que estivera en sobre aviso ou estaba máis ben lento
* Mellora o soporte para caixas combinadas en Mozilla Firefox. Específicamente cando se navega cas flechas pou os seus textos non é repetido, e cando saltando fóra deles, os controis ancestros non son anunciados innecesariamente. agora tamén as ordes do modo virtual funcionan cando reciben o foco en un cando estás nun modo virtual.
* Mellora a precisión da procura da barra de estado en moitas aplicacións. (#8)
* engadida a ferramenta da consola de python interactiva de NVDA, para habilitar ós desenroladores para mirar e manipular cuestións internas do NVDA segundo se está a executar
* Os scripts DicirTodo, AnunciarSelección e anunciarLiñaActual funcionan agora apropriadamente cando se está  no modo pasar a traverso do modo virtual. (#52)
* Os scripts incrementar velocidade e decrementar velocidade foron eliminados. Os usuarios deberían utilizar os scripts do grupo das opcións de sintetizador (control+nvda+flechas) ou o diálogo de opcións de Voz
* Mellórase o rango e a escala dos pitidos da barra de progreso
* Engadidas máis teclas rápidas ó novo modo virtual:  l para lista, i para elemento de lista, e para campo de edición, b para botón, x para caixa de verificación, r para botón de radio, g para gráfico, q para citas, c para caixa combinada, 1 a 6 para os respectivos niveis de cabeceira, s para separador, m para marco. (#67, #102, #108)
* A cancelación da carga dun novo documento en Mozilla Firefox permite agora ó usuario seguir utilizando o antigo documento do  modo virtual se o vello documento non foi realmente destruido aínda. (#63)
* Navegar por palabras nos modos virtuais é agora máis exacto mentres as palabras non conteñan accidentalmente texto de máis de un campo. (#70)
* Mellorada a exactitude do seguemento do foco e a actualización do foco cando se navega en modos virtuais de Mozilla Gecko.
* Engadido un script atoparAnterior (shift+NVDA+f3) para utilizar  no novo modo virtual
* Mellorada a lentitude en diálogos Mozilla Gecko (en Firefox e Thunderbird). (#66)
* Engadida a capacidade para ver o ficheiro rexistro actual para NVDA. pode ser atopado no menú NVDA -> Ferramentas
* Scripts como dicirData e hora teñen en conta agora a lingua actual; puntuación e ordeamento das palabras agora refrexan a lingua
* A caixa combinada de lingua no diálogo de Opcións Xerais de NVDA amosa agora os nomes da lingua completo para facilidade de uso
* Cando se revisa texto no navegador de obxectos actual, o texto está sempre actualizado se cambia dinámicamente. Ex.: revisando o texto dun elemento de lista  na Bandexa de Tarefas. (#15)
* Cando te moves co rato, o parágrafo actual de texto baixo o rato agora é anunciado, en lugar de todo o texto nese obxecto particular ou só a palabra actual. Tamén as coordenadas de audio, e o anunciado dos roles do obxecto é opcional, son desactivados de maneira predeterminada
* Soporte para leitura de texto co rato en Microsoft Word
* Correxido un erro onde ó abandoar a barra de menú en aplicacións como Wordpad podería causar que a selección de texto non sexa anunciada nunca máis
* En Winamp, o título da pista non é xa anunciado unha e outra vez cando se cambia de pistas, ou ó pausar/reanudar/deter a reproducción.
* En Winamp, engadida a capacidade de anunciar o estado dos controis Aleatorio e repetición segundo son activados. Funciona na xanela principal e  no editor de listas de reproducción
* Mellorada a capacidade para activar campos particulares nos modos virtuais de Mozilla Gecko. Poderá incluir gráficos clicables, ligas que conteñan parágrafos, e outras estructuras raras
* Correxido un retraso inicial cando se abren diálogos de NVDA nalgúns sistemas. (#65)
* Engadido soporte específico para a aplicación Total Commander
* Correxido un fallo  no controlador sapi4serotek onde o ton bloqueábase nun valor particular, é dicir, quedábase alto despois de ler unha letra en maiúscula. (#89)
* Anúnciase texto cliqueable e outros campos como cliqueables en modos virtuais de Mozilla Gecko. ex.:  a campo que teña un atributo onclick HTML. (#91)
* Cando nos movemos polos modos virtuais de Mozilla Gecko, desprázase o campo actual para ver -- útil para que os pares videntes teñan unha idea de onde está o usuario  no documento (#57)
* Engádese soporte básico para que área de rexións activas amose eventos en aplicacións habilitadas para IAccessible2 Útil  na aplicación de IRC Chatzilla, as mensaxes novas serán agora lidas automáticamente
* Algunhas melloras pequenas para axudar a utilizar aplicacións web con capacidade de ARIA,  ex.: Google Docs
* Detense a adición de liñas en blanco extra ó texto cando se copia dende un modo virtual
* Detense a tecla espazo de activar unha liga na lista de ligas.  agora pode ser utilizado como outras letras en orden a comezar o tecleo do nome dunha liga en particular á que desexes ir
* O script moveMouseToNavigator (NVDA+barra do teclado numérico) agora move o rato ó centro do navegador de obxectos, en lugar  de á esquina superior esquerda
* Engadidos scripts para facer clic nos botóns esquerdo e dereito do rato (barra e asterisco do teclado numérico respectivamente)
* Mellorado o acceso á Bandexa do Sistema de Windows. Ca esperanza de que o foco xa non debería parecer quedarse atrás nun elemento en particular. Recordatorio: para ir á Bandexa do sistema utiliza a orde de Windows Tecla Windows+b. (#10)
* Mellórase o rendemento e parada de anunciado de texto extra cando se mantén pulsada unha tecla de cursor nun campo de edición e alcanza o final
* Detense a capacidade de NVDA para facer que o usuario agarde mentres mensaxes en particular son falados. Arranxa algúns petes/cuelgues con sintetizadores de voz en particular. (#117)
* Engadido soporte para o sintetizador de voz Audiologic Tts3, contribución de Gianluca Casalino. (#105)
* Posiblemente mellora de rendemento cando se navega polos documentos en Microsoft Word
* Mellorada a precisión cando se le texto de avisos en aplicacións de Mozilla Gecko
* Detéñense posibles petes cando se trata de gardar a configuración en versións non en inglés de Windows. (#114)
* Engádese un diálogo de benvida de NVDA. Este diálogo está deseñado para proporcionar información esencial para novos usuarios e permite ó BloqMaius ser configurado como unha tecla modificadora do NVDA. Este diálogo será amosado cando NVDA sexa iniciado predeterminadamente ata que se deshabilite.
* Correxido soporte básico para Adobe Reader tal que é posible ler documentos en  versións 8 e 9
* Correxidos algúns erros que poderían ter ocurrido cando se manteñen premedas teclas antes de que NVDA sexa apropriadamente inicializado
* Se o usuario configurou ó NVDA para gardar a configuración ó saír, asegúrase de que a configuración é apropriadamente gardada cando se apaga ou se sae de Windows.
* Engadido un son de logo de NVDA ó comezo do instalador, contribuído por Victor Tsaran
* NVDA, tanto ó se executar  no instalador coma de outra maneira, debería quitar apropriadamente o seu icono da bandexa do sistema cando saia
* Etiquetas para controis estándar en diálogos de NVDA (como botóns Aceptar e cancelar) deberían amosarse agora  na lingua na que NVDA está axustado, en lugar de só quedarse en Inglés.
* O icono do NVDA debería ser agora utilizado polas teclas de atallo do NVDA  no menú de inicio e no escritorio, en lugar de un icono de aplicación predeterminado.
* Ler celdas en MS Excel cando te moves con tab e shift+tab. (#146)
* Correxidas algunhas verbalizacións duplicadas en listas en particular en Skype.
* Mellorado o seguemento do cursor en aplicacións IAccessible2 e Java; ex.: en Open Office e Lotus Symphony, NVDA agarda adecuadamente que o cursor se mova en documentos en lugar de ler accidentalmente a palabra incorrecta ou liña  no final de algúns parágrafos. (#119)
* Soporte para controis AkelEdit atopados en Akelpad 4.0
* NVDA xa non se bloquea en Lotus Synphony cando te moves dende o documento á  barra de menú.
* NVDA xa non se colga nos applets de programas Add/Remove en Windows XP cando se lanza un desinstalador. (#30)
* NVDA xa non se colga cando se abre Spybot Search and Destroy

## 0.6p1

### Acceso ó contido da web cos novos modos virtuais en proceso (ata aquí para aplicaciónsMozilla Gecko incluíndo Firefox3 e Thunderbird3)

* Os tempos de carga foron mellorados case por un factor de trenta (xa non tes que agardar en toda a maior parte das páxinas web para cargarse  no modo virtual)
* Engadida unha lista de ligas (NVDA+f7)
* Mellorado o diálogo procurar (control+nvda+f) así que leva a cabo unha procura insensible ás maiúsculas, máis arranxo duns poucos problemas co foco con esa caixa de diálogo.
* agora é posible seleccionar e copiar texto nos novos modos virtuais
* De maneira predeterminada os novos modos virtuais representan o documento nunha disposición de pantalla (ligas e controis non están en liñas separadas a menos que realmente sexan visualmente así). podes conmutar esta característica con NVDA+v.
* É posible moverse por parágrafos con control+flecha arriba e control+flecha abaixo.
* Mellorado o soporte para contido dinámico
* Mellorada por enriba toda a precisión da leitura de liñas e campos cando se sube ou se baixa cas flechas.

### Internacionalización

* agora é posible teclear caracteres acentuados que  dependen de un "caracter só", mentres NVDA está executándose.
* NVDA anuncia agora cando a distribución de teclado é cambiada (cando se preme alt+shift).
* A característica de anunciado de data e hora toma agora as opcións rexional e de idioma actuais do sistema.
* Engadida traducción ó Checo (por Tomas Valusek ca axuda de Jaromir Vit)
* Engadida traducción ó vietnamita por Dang Hoai Phuc
* Engadida ttraducción ó Africaans (af_ZA), por Willem van der Walt.
* Engadida traducción ó ruso por Dmitry Kaslin
* Engadida traducción ó polaco por DOROTA CZAJKA e amigos.
* Engadida traducción ó japonés por Katsutoshi Tsuji.
* Engadida tradución ó tailandés por Amorn Kiattikhunrat
* Engadida traducción ó croata por Mario Percinic e Hrvoje Katic
* Engadida traducción ó galego por Juan C. buño
* Engadida traducción ó ucraniano por Aleksey Sadovoy

### Voz

* NVDA ven agora co eSpeak 1.33 empaquetado que contén moitas melloras, entre as que están idiomas mellorados, variantes nomeadas, capacidade para falar máis rápido.
* O diálogo de opcións de voz agora permíteche cambiar a variante dun sintetizador si o soporta. A variante é normalmente unha lixeira variación da voz actual. (eSpeak soporta variantes).
* Engadida a capacidade para cambiar a inflexión dunha voz  no diálogo de Opcións de Voz se o sintetizador actual o soporta. (eSpeak soporta inflexión).
* Engadida a capacidade para deter a verbalización da información de posición do obxecto (ex.:. 1 de 4). Esta opción pode ser atopada no diálogo de Opcións de Presentación de obxectos.
* NVDA pode pitar agora cando verbalice unha letra en maiúsculas. Esto pode ser activado e desactivado cunha caixa de verificación  no diálogo de Opcións de Voz. Tamén se engadíu unha caixa de verificación de elevación do ton para maiúsculas para configurar se NVDA actualmente debería ter a súa elevación de ton normal para as maiúsculas. Así agora podes ter o ton elevado, dicir maius, ou pitar, para maiúsculas.
* Engadida a capacidade para pausar a voz en NVDA (como a atopada en Voice Over para o Mac). Cando NVDA está falando algo, podes premer as teclas control ou shift para silenciar a voz normalmente, pero se entón pulsas a tecla shift de novo (tanto en canto non premeras calquera outra tecla) a voz continuará exactamente dende onde o deixaramos.
* Engadido un controlador de sintetizador virtual o que saca texto a unha xanela en lugar de falalo a traverso dun sintetizador de voz. Esto debería ser máis agradable para os desenroladores videntes que non son usuarios da síntese de voz pero queren saber que está a dicir o NVDA. Todavía hai probablemente algúns fallos, así que a retroalimentación é máis benvida se cabe.
* NVDA xa non fala de maneira predeterminada a puntuación, podes habilitar a fala de puntuación con NVDA+p.
* eSpeak de maneira predeterminada agora fala un pouco máis amodo, o que debería facelo máis sinxelo para xente que van a utilizar eSpeak por primeira vez, cando instalan ou comezan a utilizar NVDA.
* Engadidos diccionarios de usuario ó NVDA. Éstos permítenche facer que NVDA fale certo texto de modo diferente. Hai tres diccionarios: predeterminado, voz, e temporal. As entradas que engadas ó diccionario predeterminado sucederán todo o tempo en NVDA. Os diccionarios por voz son específicos ó sintetizador actual e a voz que actualmente teñas axustada. e o diccionario temporal é para aquelas ocasións nas que queras fixar rápidamente unha regra mentres vas a facer unha tarefa en particular, pero non queres que sexa permanente (desaparecerá se pechas ó NVDA). Por agora as regras son expresións regulares, non só texto normal.
* Os sintetizadores poden agora utilizar calquera dispositivo de audio de saída no teu sistema, axustando a caixa combinada de dispositivo de saída no diálogo Sintetizador antes de seleccionar o sintetizador que queras.

### Rendemento

* NVDA xa non toma unha grande cantidade de memoria do sistema, cando se editan mensaxes en controis de edición mshtml
* Mellorado o rendemento cando se revisa texto dentro de moitos controis que non teñen actualmente un cursor real. Ex.: xanela de históricos de MSN Messenger, elementos de vistas en árbore, elementos de vista de lista etc.
* Mellorado o rendemento en documentos enriquecidos.
* NVDA xa non debería enlentecerse consumindo tamano de memoria do sistema sen razón
* Correxidos fallos cando se pon o foco nunha xanela de consola do dos máis de tres veces ou así. NVDA tiña unha tendencia a petar completamente.

### Teclas de ordes

* NVDA+shift+numpad6 e NVDA+shift+numpad4 permítenche navegar ó seguinte ou ó anterior obxecto en fluxo respectivamente. Esto siñifica que podes navegar nunha aplicación só utilizando estas dúas teclas sen preocuparte acerca de subir ó pai, ou baixar ó primeiro fillo segundo te movas a traverso da xerarquía de obxectos. Por exemplo nun navegador web tal como firefox, poderías navegar o documento por obxectos, só utilizando estas dúas teclas. Se o seguinte en fluxo ou o anterior en fluxo acércate e sácate dun obxecto, ou abaixo nun obxecto, mandará pitidos indicando a dirección.
* agora podes configurar opcións de voz sin abrir o diálogo opcións de voz, utilizando o grupo de opcións de sintetizador. O grupo de opcións do sintetizador é un grupo de opcións de voz que podes conmutar a traverso da pulsación de control+NVDA+dereita e control+NVDA+esquerda. Para cambiar unha opción utiliza control+NVDA+arriba e control+NVDA+abaixo.
* Engadida unha orde para anunciar a selección actual en campos de edición (NVDA+shift+flecha arriba).
* Un bo número de ordes de NVDA que falan texto (como anunciar liña actual etc) agora poden deletrear o texto se se premen dúas veces rápidamente.
* O BloqMaius, insert do teclado numérico e insert do extendido poden ser todos utilizados como a tecla modificadora do NVDA. Tamén se unha destas teclas é utilizada, preméndoa dúas veces rápidamente sen premer ningunha outra tecla enviará a tecla ó sistema operativo, como se premeses a tecla sen NVDA executándose. Para facer que unha destas teclas sexa a modificadora de NVDA, marca a súa caixa de verificación  no diálogo de Opcións de Teclado (utilizado para seren chamado o diálogo de eco de teclado).

### Soporte de aplicacións

* Mellorado o soporte para documentos de Firefox3 e Thunderbird3. Os tempos de carga foron mellorados case que por un factor de trenta, unha distribución de pantalla é utilizada predeterminadamente (preme nvda+v para activar ou desactivar esta distribución de pantalla), unha lista de ligas (nvda+f7 foi engadida), o diálogo procurar (control+nvda+f) é agora insensible ás maiúsculas, moito mellor soporte para contido dinámico, a selección de copiado de texto é agora posible.
* nas xanelas dos históricos do MSN Messenger e Windows Live Messenger, agora é posible seleccionar e copiar texto.
* Mellorado o soporte para a aplicación audacity
* Engadido soporte para uns poucos controis edit/text en Skype
* Mellorado o soporte para a aplicación Miranda instant messenger
* Correxidos algúns problemas do foco cando se abren mensaxes html e de texto planno en Outlook Express.
* Os campos de mensaxes de noticias de Outlook express son agora etiquetados correctamente
* NVDA agora pode ler os enderezos nos campos de mensaxes de Outlook Express (para/de/cc etc)
* NVDA agora debería estár máis certeiro ó anunciar a seguinte mensaxe en outlook express cando se elimina unha mensaxe dende a lista de mensaxes.

### APIs e toolkits

* Mellorada a navegación de obxectos polos obxectos de MSAA. Se unha xanela como un menú do sistema, barra de título, ou barras de desprazamento, agora podes navegar por elas.
* Engadido soporte para a API de accesibilidade IAccessible2. unha parte da capacidade para anunciar máis tipos de controis, esto tamén permite ó NVDA acceder ó cursor en aplicacións como Firefox 3 e Thunderbird 3, permitíndoche navegar, seleccionar ou editar texto.
* Engadido soporte para controis de edición de Scintilla (tales controis poden ser atopados no Notepad++ ou no Tortoise SVN).
* Engadido soporte para aplicacións Java (a traverso do Java Access Bridge). Esto pode proporcionar soporte básico para Open Office (se Java está activado), e calquera outra aplicación autónoma Java. Ten en conta que os Applets de java dentro dun navegador web non poderán funcionar aínda.

### rato

* Mellorado o soporte para a leitura do que estea baixo o punteiro do rato segundo se move. agora é moito máis rápido, e agora tamén ten a capacidade nalgúns controis como campos de edición estándares, controis Java e IAccessible2, para ler a palabra actual, non só o obxecto actual. Esto poderá ser de algún uso a persoas con deficiencia visual que só queran ler un anaco específico do texto co rato.
* Engadida unha nova opción de configuración, atopada  no diálogo Opcións do rato. Reproducir audio cando o rato se move, cando está verificada, reproduce un pitido de 40 ms cada vez que o rato se move, co seu ton (entre 220 e 1760 hz) representando o eixo y, e o  volume esquerda/dereita, representando o eixo x. Esto capacita a unha persoa cega alcanzar unha idea aproximada de onde está o rato  na pantalla segundo se está a mover. Esta característica tamén depende de que reportObjectUnderMouse tamén vaia a ser activado. Así esto siñifica que se necesitas deshabilitar rápidamente tanto o pitado como o anunciado de obxectos, entón só preme NVDA+m. Os pitidos tamén son máis altos ou máis baixos dependendo de como brile a pantalla nese punto.

### Presentación de obxectos e interacción

* Mellorado o soporte para a maioría dos controis comúns de vista en árbore. NVDA diche agora cantos elementos están  na póla cando a expandes. Tamén anuncia o nivel cando te moves en e fóra das pólas. E, anuncia o número do elemento actual e o número de elementos, de acordo ca actual póla, non a árbore enteira.
* Mellorado o que é anunciado cando o foco cambia segundo te moves por aplicacións ou o sistema Operativo. agora en lugar de só escoitar o control no que aterrizas, escoitas información interna acerca de calquer control sobre o que este control esté posicionado. Por exemplo se tabulas e aterrizas sobre un botón dentro de un grupo, o grupo tamén será anunciado.
* NVDA agora trata de falar a mensaxe interior de moitas caixas de diálogo segundo aparecen. Esto é exacto na maior parte das ocasións, aíndaque todavía hai moitos diálogos que non son tan bos como deberían ser.
* Engadida unha caixa de verificación anunciar descripcións do obxecto ó diálogo de Opcións de presentación de obxectos. Os usuarios avanzados poderán en ocasións desmarcar esto para deter o anunciado de NVDA de un montón de descripcións extra en controis en particular, como en aplicacións Java.
* NVDA anuncia automáticamente texto seleccionado en controis de edición cando o foco se move cara eles. Se non hai ningún texto seleccionado, entón só anuncia a liña actual como normalmente.
* NVDA é moito máis cuidadoso agora cando reproduce pitidos para indicar cambios nas barras de progreso en aplicacións. xa non se volve tolo en aplicacións de Eclipse como Lotus Notes/Symphony, e Accessibility Probe.

### Interface do Usuario

* Eliminada a xanela de interface de NVDA, e reemplazada cun sinxelo menú de NVDA desplegable.
* O diálogo opcións de Interface de NVDA é agora chamado Opcións Xerais. Tamén contén unha opción extra: unha caixa combinada para axustar o nivel do rexistro, para que as mensaxes podan ir ó ficheiro de rexistro do NVDA. Ten en conta que o ficheiro de rexistro do NVDA é agora chamado nvda.log non debug.log.
* Eliminada a caixa de verificación Anunciar nomes de grupos de obxectos do diálogo Opcións de presentación de obxectos, O anunciado de nomes de obxectos é agora manexado diferentemente.

## 0.5

* NVDA ten agora un sintetizador incorporado chammado eSpeak, desenrolado por Jonathan Duddington. é moi áxil e lixeiro, e ten soporte para moitas linguas diferentes. Os sintetizadores Sapi todavía poden ser utilizados, pero eSpeak será utilizado de maneira predeterminada. eSpeak non depende de ningún software especial para seren instalado, así que pode ser utilizado con NVDA en calquier ordenador, nun lápiz de memoria USB, ou calquer outro. Para máis información sobre eSpeak, ou para atopar outras versións, vai a https://espeak.sourceforge.net/.
 * eSpeak non depende de ningún software especial para instalarse, así que pode usarse co NVDA en calquera computador, nunha memoria USB ou en calquera lugar.
 * Para máis información sobre eSpeak, ou para atopar outras versións, vai a http://espeak.sourceforge.net/.
* Corrección do fallo onde era anunciado o caracter incorrecto cando se premía Suprimir en paneis editables de Internet Explorer / Outlook Express.
* Engadido soporte para máis campos de edición en Skype.
* Os modos virtuais só se cargan cando o foco está sobre a xanela que necesita ser cargada. Esto arranxa algúns problemas cando o panel anterior está activado en Outlook Express.
* Engadidos argumentos de liña de ordes a NVDA:
 * -m, --minimal: non reproduce os sons de comezo/saír e non amosa a interface ó arrancar se se axustou a tal cousa.
 * -q, --quit: abandoa calquera outra instancia xa en execución do NVDA e logo sae
 * -s, --stderr-file nomeFicheiro: especifica onde debería colocar NVDA os erros e excepcións
 * -d, --debug-file nomeFicheiro: especifica onde debería colocar NVDA as mensaxes de depuración
 * -c, --config-file: especifica un ficheiro de configuración alternativo
 * -h, -help: amosa unha mensaxe de axuda listando os argumentos de liña de ordes
* Correxido un fallo onde os símbolos de puntuación non deberían ser traducidos á lingua apropriada, cando se utiliza outra lingua que o inglés, e cando falar caracteres ó se escribir estivera activado.
* Engadidos ficheiros da lingua eslovaca gracias a Peter Vagner
* Engadido o diálogo de Opcións de Modo virtual e un diálogo de opcións de formato de documento, de Peter Vagner.
* Engadida traducción ó francés gracias a Michel Such
* Engadido un script para activar e desactivar o pitido das barras de progreso (insert+u). Colaboración de Peter Vagner.
* Faise que máis mensaxes en NVDA sexan traducibles para outras linguas. Esto inclúe descripcións de script cando se está  na axuda de teclado.
* Engadido un diálogo de procura ós modos virtuais (internet Explorer e Firefox). Premendo control+f cando se está nunha páxina desplega un diálogo  no que podes teclear algún texto a atopar. Premendo intro despois procurará este texto e colocará o cursor do modo virtual sobre esta liña. Premendo f3 tamén procurarás a seguinte ocurrencia do texto.
* Cando falar caracteres ó se escribir está activado, máis caracteres deberían ser falados agora. Técnicamente, agora os caracteres ascii dende o 32 ó 255 poden ser falados.
* Renomeados algúns tipos de controis para unha mellor lexibilidade. O Texto editable é agora edición, outline é agora árbore e botón pulsable é agora botón.
* Cando se navega ó longo dos elementos de unha lista, ou elementos de árbore nunha árbore, o tipo de control (elemento de lista, elemento de árbore) xa non é falado, para unha navegación rápida.
* Ten desplegable (para indicar que un menú ten un submenú) é agora falado como submenú.
* Cando algunhas linguas utilizan control e alt (ou altGR) para introducir un caracter especial, NVDA falará agora estos caracteres cando falar caracteres ó se escribir estea activado.
* Arranxados algúns problemas ca revisión de controis con texto estático.
* Engadida traducción ó Chino Tradicional, gracias a Coscell Kao.
* Reestructurada unha parte importante do código de NVDA, que debería correxir agora moitos fallos ca interface de usuario de NVDA (incluyndo opcións de diálogos).
* Engadido soporte Sapi4 para NVDA. Actualmente hay dous controladores sapi4, un basado en código escrito por Serotek Corporation, e outro utilizando a interface ActiveVoice.ActiveVoice com. Ambos controladores teñen problemas, mira cal funciona mellor para ti.
* agora cando se trata de executar unha nova copia de NVDA mentres unha copia anterior está todavía executándose causará que a nova copia saia. Esto arranxa un problema maior cando se executan múltiples copias do NVDA facendo que o teu sistema sexa moi inusable.
* Renomeado o título da interface de usuario de NVDA de Interface de NVDA a NVDA.
* Correxido un fallo en Outlook Express cando ó pulsar Retroceso  no inicio dunha mensaxe editable causaba un erro.
* Engadido un parche de Rui Batista que engade un script para anunciar o actual estado da batería en portátiles (insert+shift+b).
* Engadido un controlador de sintetizador chamado Silence. Este é un controlador de sintetizador que non fala nada, permitindo a NVDA permanecer completamente silencioso todo o tempo. Eventualmente esto sería utilizado xunto co soporte Braille, cando o teñamos.
* Engadida opción capitalPitchChange para sintetizadores gracias a J.J. Meddaugh
* Engadido parche de J.J. Meddaugh que fai que o script conmutar anunciado de obxectos baixo o rato sexa máis parecido a outros scripts conmutables (dicindo activado/desactivado en lugar de cambiando  todo o estado).
* Engadida traducción ó español (es) colaboración de Juan C. buño.
* Engadido ficheiro de lingua Húmgara de Tamas Gczy.
* Engadido ficheiro de lingua portuguesa de Rui Batista.
* O cambio de voz no diálogo Opcións de voz axusta agora os deslizadores de velocidade, ton e volume ós novos de acordo co sintetizador, en lugar de forzar ó sintetizador a seren axustado ós valores anteriores. Esto arranxa fallos cando un sintetizador como eloquence ou viavoice parecen falar a unha velocidade moito máis rápida que todos os outros sintetizadores.
* Correxido un fallo onde o sintetizador de voz detíase, o NVDA petaba completamente, cando se estaba nunha xanela da consola do Dos.
* Se existe soporte para un idioma en particular, NVDA agora pode amosar automáticamente a súa interface e falar as súas mensaxes  na lingua na que Windows estea axustado. Unha lingua particular pode aínda ser elexida manualmente dende o diálogo Opcións de Interface de Usuario como tamén.
* Engadido un script 'toggleReportDynamicContentChanges' (insert+5). Esto conmuta se o texto novo, ou outros cambios dinámicos deberían ser anunciados automáticamente. Ata aquí esto só funcionaba en xanelas de consola do Dos.
* Engadido o script 'toggleCaretMovesReviewCursor' (insert+6). Esto conmuta se o cursor de revisión debería ser volto a poñer automáticamente cando o cursor do sistema se move. Esto é útil en xanelas de Consola do Dos cando se trata de ler información cando a pantalla se está a actualizar.
* Engadido o script 'toggleFocusMovesNavigatorObject' (insert+7). Esto conmuta se o navegador de obxectos é volto a poñer sobre o obxecto co foco cando cambia.
* Engadida algunha documentación traducida en varias linguas. Ata aquí hai Francés, Español e Finlandés.
* Eliminada algunha documentación de desenroladores da distribución binaria do NVDA, agora so está  na versión das fontes.
* Correxido un posible fallo en Windows Live Messanger e MSN Messenger onde ó navegar arriba e abaixo pola lista de contactos causaba erros.
* Novas mensaxes son agora faladas automáticamente cando se está nunha conversación utilizando Windows Live Messenger. (só funciona para versións en Inglés ata agora)
* A xanela de históricos nunha conversación en Windows Live Messenger agora pode ser lida utilizando as teclas de flechas. (Só funciona para versións en Inglés ata o momento)
* Engadido o script 'passNextKeyThrough' (insert+f2). Preme esta tecla, e entón a seguinte tecla premeda será pasada directamente ó Windows. Esto é útil se has premer unha tecla nunha aplicación pero NVDA utiliza esa tecla para algo.
* NVDA xa non se conxela por máis dun minuto cando se habren documentos moi grandes en MS Word.
* Correxido un fallo cando se move fóra dunha táboa en MS Word, e logo se volta a ela, causaba que os números da actual fila/columna non sexan falados se voltas exactamente á mesma celda.
* Cando se comeza NVDA cun sintetizador que non existe, ou non está funcionando, o sintetizador sapi5 tratará de ser cargado no seu lugar, ou se sapi5 non está funcionando, entón a voz será axustada a silence.
* Os scripts de Incrementar e decrementar a velocidade xa non poden tomar a velocidade por enriba de 100 ou por debaixo de 0.
* Se hay un erro cunha lingua cando se elixa  no diálogo Opcións de Interface de Usuario, unha caixa de mensaxe alertará ó usuario do feito.
* NVDA agora pregunta se debería gardar a configuración e reiniciar se o usuario cambiou a lingua no diálogo Opcións de Interface de Usuario. NVDA debe ser reiniciado para que o cambio de lingua teña un efecto completo.
* Se un sintetizador non pode ser cargado, cando se o selecciona dende o diálogo Sintetizadores, Unha caixa de mensaxe alerta ó usuario do feito.
* Cando se carga un sintetizador por primeira vez, NVDA permite ó sintetizador elexir a voz máis convinte, os parámetros de velocidade e ton, en lugar de forzalo a deixalo como pense que está ben. Esto corrixe un problema onde os sintetizadores sapi4 Eloquence e Viavoice comezan a falar dun modo bastante rápido para unha primeira vez.
