# Qué hay de Nuevo en NVDA

## 2024.4

Esta versión incluye un número de mejoras en Microsoft Office, en el braille y en el formato de documentos.

En Word o Excel, ahora es posible pulsar dos veces el gesto de comentarios para leer el comentario o nota en un diálogo explorable.
Puedes utilizar la orden de selección del cursor de  revisión para seleccionar texto en PowerPoint.
NVDA ya no salta caracteres basura al mostrar texto de encabezado de fila o columna en tablas de Word cuando se utiliza el modelo de objetos.

NVDA puede configurarse ahora para anunciar los atributos de fuente en voz y braille por separado.

Se ha añadido una nueva opción para configurar el tiempo de espera para realizar un gesto de pulsación múltiple, como el comando de informar hora y fecha.

Ahora puedes configurar cómo NVDA muestra el formato de texto en braille, y ajustarlo para que muestre el inicio de los párrafos en braille.
NVDA ahora puede verbalizar el carácter en el cursor cuando se realiza una acción de enrutamiento del cursor braille.
Se ha mejorado la fiabilidad del enrutamiento del cursor y se ha añadido compatibilidad con las teclas de enrutamiento en PowerPoint.
Ahora se utilizarán todas las líneas de celdas cuando se utilice una pantalla braille multilínea mediante HID braille.
NVDA ya no es inestable después de reiniciar NVDA durante un escaneo automático de Bluetooth Braille.

La versión mínima requerida de Poedit que funciona con NVDA es ahora la versión 3.5.

eSpeak NG se ha actualizado y ahora es compatible con las lenguas feroesa y xextana.

LibLouis se ha actualizado, añadiendo nuevas tablas braille para braille internacional tailandés y griego con letras acentuadas en una sola celda.

También se han realizado una serie de correcciones, como el seguimiento del ratón en Firefox y el modo de voz a petición.

### Nuevas Características

* Nuevas características braille:
  * Ahora es posible cambiar el modo en que NVDA muestra ciertos atributos de formato de texto en braille.
    Las opbiones disponibles son:
    * Liblouis (predeterminado): utiliza las marcas de formato definidas en la tabla braille seleccionada.
    * Etiquetas: utiliza etiquetas de inicio y fin para indicar donde comienzan y terminan ciertos atributos de fuente. (#16864)
  * Cuando la opción "Leer por párrafos" está activada, ahora se puede configurar NVDA para que indique el inicio de los párrafos en braille. (#16895, @nvdaes)
  * Al realizar una acción de enrutamiento del cursor braille, NVDA ahora puede verbalizar automáticamente el carácter en el cursor. (#8072, @LeonarddeR)
    * Esta opción está deshabilitada por defecto.
      Puedes habilitar "Verbalizar caracteres al enrutar el cursor en el text" en las opciones de NVDA.
* La orden comentarios en Microsoft Word y la orden notas en Microsoft Excel ahora se puede pulsar dos veces para mostrar el comentario o la nota en un mensaje explorable. (#16800, #16878, @Cary-Rowen)
* NVDA ahora puede configurarse para anunciar atributos de fuente en voz y braille por separado. (#16755)
* El tiempo de espera para realizar una pulsación de teclas múltiple ahora es configurable; esto podría ser especialmente útil para personas con deficiencias de destreza. (#11929, @CyrilleB79)

### Cambios

* Las opciones de órdenes de línea `-c`/`--config-path` y `--disable-addons` ahora se respetan al lanzar una actualización desde dentro de NVDA. (#16937)
* Actualización de componentes:
  * Actualizado el transcriptor braille LibLouis a [3.31.0](https://github.com/liblouis/liblouis/releases/tag/v3.31.0). (#17080, @LeonarddeR, @codeofdusk)
    * Corregida la transcripción de los números braille en español.
    * Nuevas tablas braille:
      * Thai grado 1
      * Braille griego internacional (aceptadas letras de una sola celda)
    * Tablas renombradas:
      * "Thai de 6 puntos" se renombró a "Thai grado 0" por razones de consistencia.
      * La tabla "Braille griego internacional" existente se renombró a "Braille griego internacional (aceptadas letras de dos letras)" para aclarar la distinción entre los dos sistemas de griego.
  * eSpeak NG se ha actualizado a 1.52-dev commit `961454ff`. (#16775)
    * Añadidos nuevos idiomas Feroés y Xextan.
* Al utilizar una pantalla braille de varias líneas a través del controlador estándar braille  HID, se utilizarán todas las líneas de celdas. (#16993, @alexmoon)
* La estabilidad del soporte de Poedit en NVDA se ha mejorado con el efecto secundario que la versión mínima requerida de Poedit es ahora la versión 3.5. (#16889, @LeonarddeR)

### Corrección de Fallos

* Correcciones de braille:
  * Ahora es posible utilizar los sensores de la pantalla braille para mover el cursor de texto en Microsoft PowerPoint. (#9101)
  * Al acceder a Microsoft Word sin UI Automation, NVDA ya no saca caracteres basura en cabeceras de tabla definidas con las órdenes fijar fila y columna. (#7212)
  * El controlador del Seika Notetaker ahora genera correctamente la entrada braille para espacio, retroceso y puntos con gestos con espacio y retroceso. (#16642, @school510587)
  * El enrutamiento del cursor ahora es mucho más fiable cuando una línea contenga uno o más selectores de variante Unicode o caracteres descompuestos. (#10960, @mltony, @LeonarddeR)
  * NVDA ya no arroja un error al desplazar la pantalla braille hacia adelante en algunos controles de edición vacíos. (#12885)
  * NVDA ya no es inestable después de reiniciar NVDA durante un escaneo automático de Bluetooth Braille. (#16933)
* Ahora es posible utilizar las órdenes de selección del cursor de revisión para seleccionar texto en Microsoft PowerPoint. (#17004)
* En el modo voz bajo demanda, NVDA no habla cuando un mensaje se abra en Outlook, cuando se cargue una página nueva en un navegador, o cuando se muestre una diapositiva nueva en una presentación de PowerPoint. (#16825, @CyrilleB79)
* En Mozilla Firefox, mover el ratón sobre el texto antes o después de un enlace ahora informa del texto de forma fiable. (#15990, @jcsteh)
* NVDA ya no falla ocasionalmente al abrir mensajes explorables (como pulsar `NVDA+f` dos veces). (#16806, @LeonarddeR)
* Actualizar NVDA mientras las actualizaciones de complementes están pendientes ya no resulta en la eliminación del complemento. (#16837)
* Ahora es posible interactuar con las listas desplegables de validación de Datos en Microsoft Excel 365. (#15138)
* NVDA ya no es tan lento cuando se desplacía hacia arriba o hacia abajo a través de ficheros grandes en VS Code. (#17039)
* NVDA ya no deja de responder después de mantener pulsada una flecha durante mucho tiempo en el modo de exploración, especialmente en Microsoft Word y Microsoft Outlook. (#16812)
* NVDA ya no lee la última línea cuando el cursor esté en la penúltima línea de un control de edición multilínea en aplicaciones Java. (#17027)

### Cambios para Desarrolladores

Por favor consulta [la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre la obsolesncencia de la API de NVDA y sobre el proceso de eliminación.

* Actualización de componentes:
  * Actualizado py2exe a 0.13.0.2 (#16907, @dpy013)
  * Actualizado setuptools a 72.0 (#16907, @dpy013)
  * Actualizado Ruff a 0.5.6. (#16868, @LeonarddeR)
  * Actualizado nh3 a 0.2.18 (#17020, @dpy013)
* Añadido un fichero `.editorconfig` al repositorio de NVDA para varios IDEs para recoger las reglas básicas del estilo de código de NVDA por defecto. (#16795, @LeonarddeR)
* Añadido el soporte para diccionarios personalizados de símbolos de voz. (#16739, #16823, @LeonarddeR)
  * Los diccionarios pueden proporcionarse en carpetas locales específicas en un paquete de complementos, ej.: `locale\en`.
  * Los metadatos del diccionario pueden añadirse a una sección opcional `symbolDictionaries` en el manifiesto del complemento.
  * Por favor consulta la [sección Diccionarios de símbolos de habla personalizados en la Guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#AddonSymbolDictionaries) para más detalles.
* Ahora es posible redirigir objetos recuperados de coordenadas en la pantalla, utilizando el método `NVDAObject.objectFromPointRedirect`. (#16788, @Emil-18)
* Ejecutar SCons con el parámetro `--all-cores` eligirá automáticamente el número máximo de núcleos disponibles de CPU. (#16943, #16868, @LeonarddeR)
* La info del desarrollador ahora incluye información sobre la acquitectura de la app (como AMD64) para el navegador de objetos. (#16488, @josephsl)

#### Obsolescencias

* La clave de configuración `bool` `[documentFormatting][reportFontAttributes]` está obsoleta para su eliminación en 2025.1, en su lugar utiliza `[fontAttributeReporting]`. (#16748)
  * La clave nueva tiene un valor `int` emparejando un `OutputMode` `enum` con opciones para voz, braille, speech y braille y desactivado.
  * Los consumidores de la API pueden utilizar el valor `bool` como anteriormente, o comprobar el `OutputMode` si manejan específicamente voz o braille.
  * Estas claves actualmente están sincronizadas hasta 2025.1.
* `NVDAObjects.UIA.InaccurateTextChangeEventEmittingEditableText` está obsoleta sin reemplazo. (#16817, @LeonarddeR)

## 2024.3.1

Este es un lanzamiento de un parche para corregir un fallo con la notificación de actualizaciones automáticas de complementos.

### Correción de Fallos

* Al buscar automáticamente actualizaciones de complementos, NVDA ya no se bloquea en conexiones deficientes. (#17036)

## 2024.3

La tienda de complementos ahora te notificará si cualquier actualización de complemento está disponible al arrancar NVDA.

Ahora hay opciones para aplicar normalización Unicode a la salida de voz y de braille.
Esto puede ser útil al leer caracteres que sean desconocidos para un sintetizador de voz en particular o una tabla braille que tenga una alternativa compatible, como los caracteres en negrita y en cursiva utilizados normalmente en redes sociales.
También permite la lectura de ecuaciones en el editor de ecuaciones de Microsoft Word.

Ahora se admiten las pantallas braille Help Tech Activator Pro.

Se han añadido órdenes sin asignar para desplazar la rueda del ratón verticalmente y horizontalmente.

Hay varias correcciones de fallos, particularmente para el panel emoji de Windows 11 y para el histórico del portapapeles.
Para navegadores web, hay correcciones para el anunciado de mensajes de error, figuras, pies de foto, etiquetas de tabla y elementos de menú con casillas de verificación y botones de opción.

Liblouis se ha actualizado, añadiendo nuevas tablas braille para Serbio cirílico, Yiddish, varios idiomas antiguos, Turco y el alfabeto fonético internacional.
eSpeak se ha actualizado, añadiendo soporte para el idioma Karakalpak.
Unicode CLDR también se ha actualizado.

### Nuevas Características

* Nuevas teclas de órdenes:
  * Añadidas órdenes sin asignar para el desplazamiento vertical y horizontal de la rueda del ratón, para mejorar la navegación en páginas web y en aplicaciones con contenido dinámico, como Dism++. (#16462, @Cary-Rowen)
* Añadido soporte para normalización Unicode para la salida de voz y braille. (#11570, #16466 @LeonarddeR).
  * Esto puede ser útil al leer caracteres que son desconocidos para un sintetizador de voz en particular o tabla braille y que tenga una alternativa compatible, como los caracteres en negrita y cursiva utilizados comúnmente en redes sociales.
  * También permiten la lectura de ecuaciones en el editor de ecuaciones de Microsoft Word. (#4631)
  * Puedes abilitar esta funcionalidad para voz y braille en sus respectivas categorías de opciones en el diálogo de opciones de NVDA.
* Por defecto, después de arrancar NVDA, se te notificará si cualquier actualización de complemento está disponible. (#15035)
  * Esto puede desactivarse en la categoría "Tienda de Complementos" de las opciones.
  * NVDA comprueba diariamente las actualizaciones de complementos.
  * Sólo se comprobarán las actualizaciones dentro del mismo canal (ej.: los complementos beta instalados sólo se notificarán para las actualizaciones en el canal beta).
* Añadido soporte para las pantallas Help Tech Activator Pro. (#16668)

### Cambios

* Actualizaciones de componentes:
  * eSpeak NG se ha actualizado a 1.52-dev commit `54ee11a79`. (#16495)
    * Añadido nuevo idioma Karakalpak.
  * Actualizado Unicode CLDR a la versión 45.0. (#16507, @OzancanKaratas)
  * Actualizado fast_diff_match_patch (utilizado para detectar cambios en terminales y otro contenido dinámico) a la versión 2.1.0. (#16508, @codeofdusk)
  * Actualizado el transcriptor braille LibLouis a [3.30.0](https://github.com/liblouis/liblouis/releases/tag/v3.30.0). (#16652, @codeofdusk)
    * Nuevas tablas braille:
      * Serbio cirílico.
      * Yiddish.
      * Varios idiomas antiguos: hebreo bíblico, acadio, sirio, Ugarítico y texto cuneiforme transliteralizado.
      * Turco grado 2. (#16735)
      * Alfabeto Fonético Internacional. (#16773)
  * Actualizado NSIS a 3.10 (#16674, @dpy013)
  * Actualizado markdown a 3.6 (#16725, @dpy013)
  * Actualizado nh3 a 0.2.17 (#16725, @dpy013)
* La tabla de entrada de reserva ahora es igual a la tabla de salida de reserva, que es braille inglés unificado Código grado 1. (#9863, @JulienCochuyt, @LeonarddeR)
* NVDA ahora anunciará figuras sin hijos accesibles, pero con una etiqueta o descripción. (#14514)
* Al leer por líneas en modo exploración, "pie de foto" ya no se anuncia en cada línea de una figura grande o de pie de tabla. (#14874)
* En la consola Python, la última orden no ejecutada ya no se perderá al moverte por el histórico de entradas. (#16653, @CyrilleB79)
* Ahora se envía un ID anónimo único como parte de la recopilación opcional de estadísticas de uso. (#16266)
* Por defecto, se creará una nueva carpeta al hacer una copia portable.
Un mensaje de advertencia te avisará si intentas escribir en un directorio no vacío. (#16684)

### Corrección de Fallos

* Correcciones para Windows 11:
  * NVDA ya no parecerá atascarse al cerrar el histórico del portapapeles y el panel de emoji. (#16346, #16347, @josephsl)
  * NVDA anunciará los candidatos visibles de nuevo al abrir la interfaz IME. (#14023, @josephsl)
  * NVDA ya no anunciará "histórico del portapapeles" dos veces al navegar por los elementos de menú del panel de emoji. (#16532, @josephsl)
  * NVDA ya no cortará la voz y el braille al revisar kaomojis y símbolos en el panel de emoji. (#16533, @josephsl)
* Correcciónes para el navegador web:
  * Los mensajes de error referenciados con `aria-errormessage` ahora se anuncian en Google Chrome y en Mozilla Firefox. (#8318)
  * Si está presente, NVDA ahora utilizará `aria-labelledby` para proporcionar nombres accesibles para tablas en Mozilla Firefox. (#5183)
  * NVDA anunciará correctamente elementos de menú con botones de opción y casillas de verificación al entrar por primera vez en submenús en Google Chrome y en Mozilla Firefox. (#14550)
  * La funcionalidad de búsqueda en modo exploración en NVDA ahora es más precisa cuando la página contiene emojis. (#16317, @LeonarddeR)
  * En Mozilla Firefox, NVDA ahora anuncia correctamente el carácter, palabra y línea actuales cuando el cursor esté en el punto de inserción al final de una línea. (#3156, @jcsteh)
  * Ya no causa que Google Chrome se cuelgue al cerrar un documento o al salir de Chrome. (#16893)
* NVDA anunciará correctamente el autocompletado de sugerencias en Eclipse y otros entornos basados en él en Windows 11. (#16416, @thgcode)
* Mejorada la fiabilidad de la lectura automática de texto, especialmente  en aplicaciones de terminal. (#15850, #16027, @Danstiv)
* Es posible una vez más reiniciar la configuración a los valores predeterminados de fábrica de forma fiable. (#16755, @Emil-18)
* NVDA anunciará correctamente los cambios de selección al editar una celda de texto en Microsoft Excel. (#15843)
* En aplicaciones que utilicen Java Access Bridge, NVDA ahora leerá correctamente la última línea en blanco de un texto en lugar de repetir la línea anterior. (#9376, @dmitrii-drobotov)
* En LibreOffice Writer (versión 24.8 y más modernas), al conmutar el formateado de texto (negrita, cursiva, subrayado, subíndice/superíndice, alineación) utilizando los atajos de teclado correspondientes, NVDA anuncia el nuevo atributo de formato (ej.: "negrita activada", "negrita desactivada"). (#4248, @michaelweghorn)
* Al navegar con las flechas en cuadros de texto en aplicaciones que utilicen UI Automation, NVDA ya no anuncia a veces el carácter, palábra, etc. erróneas (#16711, @jcsteh)
* Al pegar en la calculadora de Windows 10/11, NVDA ahora anuncia correctamente el número entero pegado. (#16573, @TristanBurchett)
* La voz ya no queda en silencio después de desconectarse y volver a conectarse a una sesión de Escritorio Remoto. (#16722, @jcsteh)
* Añadido soporte para órdenes de revisión de texto para el nombre de un objeto en Visual Studio Code. (#16248, @Cary-Rowen)
* Reproducir sonidos de NVDA ya no falla en un dispositivo de audio mono. (#16770, @jcsteh)
* NVDA anunciará las direcciones cuando te muevas con las flechas por los campos PARA/CC/BCC en outlook.com  y Outlook moderno. (#16856)
* NVDA ahora maneja los fallos de instalación de complementos con más elegancia. (#16704)

### Cambios para Desarrolladores

* NVDA ahora utiliza Ruff en lugar de flake8 para linting. (#14817)
* Corregido el sistema de compilación para NVDA para que funcione correctamente cuando se utilice Visual Studio 2022 versión 17.10 y superiores. (#16480, @LeonarddeR)
* Ahora se utiliza una fuente de ancho fijo en el Visualizador de Registro y en la Consola Python de NVDA para que el cursor permanezca en la misma columna durante la navegación vertical.
Es especialmente útil para leer los marcadores de localización de errores en los tracebacks. (#16321, @CyrilleB79)
* Se añadió el soporte para las tablas braille personalizadas. (#3304, #16208, @JulienCochuyt, @LeonarddeR)
  * Las tablas pueden proporcionarse en la carpeta `brailleTables` en un paquete de complemento.
  * Los metadatos de la tabla pueden añadirse a una sección opcional `brailleTables` en el manifiesto del complemento o en un fichero `.ini` con el mismo formato encontrado en el subdirectorio brailleTables del directorio scratchpad.
  * Por favor consulta la [sección braille translation tables en la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#BrailleTables) para más detalles.
* Cuando se pone en cola un evento `gainFocus` con un objeto que tiene una propiedad `focusRedirect` válida, el objeto apuntado por la propiedad `focusRedirect` es ahora mantenido por `eventHandler.lastQueuedFocusObject`, en lugar del objeto puesto en cola originalmente. (#15843)
* NVDA registrará su arquitectura ejecutable (x86) al iniciarse. (#16432, @josephsl)
* `wx.CallAfter`, que está envuelto en  `monkeyPatches/wxMonkeyPatches.py`, ahora incluye la indicación apropiada `functools.wraps`. (#16520, @XLTechie)
* Hay un nuevo módulo para programar tareas `utils.schedule`, utilizando el módulo pip `schedule`. (#16636)
  * Puedes utilizar `scheduleThread.scheduleDailyJobAtStartUp` para programar automáticamente un trabajo que ocurra después de que NVDA arranque, y cada 24 hhoras después de eso.
  Los trabajos se programan con un retraso para evitar conflictos.
  * `scheduleThread.scheduleDailyJob` y `scheduleJob` se pueden utilizar para programar trabajos en tiempos personalizados, donde un `JobClashError` se activará cuando se conozca un conflicto en la programación de un trabajo.
* Ahora es posible crear app modules para aplicaciones alojando controles WebView2 (msedgewebview2.exe). (#16705, @josephsl)

## 2024.2

Hay una característica nueva llamada separación de sonido.
Esto permite separar los sonidos de NVDA en un canal (ej: el izquierdo) mientras los sonidos de todas las demás aplicaciones se colocan en el otro canal (ej.: el derecho).

Hay nuevas órdenes para modificar las opciones del anillo del sintetizador, permitiendo a los usuarios saltar a la primera o a la última opción, y aumentar o disminuir la opción actual en pasos más grandes.
También hay nuevas órdenes de navegación rápida, permitiendo a los usuarios vincular gestos para saltar rápidamente entre: párrafo, párrafo alineado verticalmente, mismo estilo de texto, diferente estilo de texto, elemento de menú, botón conmutable, barra de progreso, figura y fórmula matemática.

Hay muchas características braille nuevas y correcciones de errores.
Se ha añadido un nuevo modo braille llamado "mostrar salida de voz".
Cuando esté activo, la pantalla braille muestra exactamente lo que NVDA vaya a hablar.
También se añadió el soporte para las pantallas BrailleEdgeS2 y BrailleEdgeS3.
LibLouis se actualizó, añadiendo las nuevas tablas braille detalladas (con letras mayúsculas indicadas) para bieloruso y ucraniano, una tabla Lao y una tabla en español para leer texto en griego.

eSpeak se actualizó, añadiendo el nuevo idioma Tigrinya.

Hay muchas otras correcciones menores de fallos para aplicaciones tales como Thunderbird, Adobe Reader, navegadores web, Nudi y Geekbench.

### Nuevas Características

* Nuevas teclas de órdenes:
  * Nueva órden de navegación rápida `p` para saltar al siguiente y anterior párrafo de texto en modo exploración. (#15998, @mltony)
  * Nuevas órdenes de navegación rápida no asignadas, que pueden utilizarse para saltar al siguiente y anterior:
    * figura (#10826)
    * párrafo alineado verticalmente (#15999, @mltony)
    * elemento de menú (#16001, @mltony)
    * botón conmutable (#16001, @mltony)
    * barra de progreso (#16001, @mltony)
    * fórmula matemática (#16001, @mltony)
    * mismo estilo de texto (#16000, @mltony)
    * diferente estilo de texto (#16000, @mltony)
  * Añadidas órdenes para saltar a la primera, última, adelante y atrás por las opciones del anillo del sintetizador. (#13768, #16095, @rmcpantoja)
    * Establecer la opción primera y última en el anillo del sintetizador no tiene gesto asignado. (#13768)
    * Disminuir y aumentar la opción actual del anillo de opciones del sintetizador en pasos grandes (#13768):
      * Escritorio: `NVDA+control+rePág` y `NVDA+control+avPág`.
      * Portátil: `NVDA+control+shift+rePág` y `NVDA+control+shift+avPág`.
  * Añadido un nuevo gesto de entrada no asignado para conmutar el anunciado de figuras y pies de foto. (#10826, #14349)
* Braille:
  * Añadido el soporte para las pantallas braille BrailleEdgeS2 y BrailleEdgeS3. (#16033, #16279, @EdKweon)
  * Se ha añadido un nuevo modo braille llamado "mostrar salida de voz". (#15898, @Emil-18)
    * Cuando se activa, la pantalla braille muestra exactamente lo que NVDA va a verbalizar.
    * Puede conmutarse pulsando `NVDA+alt+t`, o desde el diálogo Opciones de Braille.
* Separación de sonido: (#12985, @mltony)
  * Permite separar sonidos de NVDA en un canal (ej.: izquierda) mientras los sonidos de las demás aplicaciones se colocan en el otro canal (ej.: derecha).
  * Conmutado con `NVDA+alt+s`.
* Ahora se admite el anunciado de encabezamientos de fila y de columna en elementos HTML contenteditable. (#14113)
* Añadida una opción para deshabilitar el anunciado de figuras y pies de foto en las opciones de formateado de documentos. (#10826, #14349)
* En Windows 11, NVDA anunciará alertas desde la escritura de voz y acciones sugeridas incluyendo la sugerencia superior al copiar datos como números de teléfono al portapapeles (Windows 11 2022 Update y posterior). (#16009, @josephsl)
* NVDA mantendrá el dispositivo de audio activo después de que se detenga el habla para evitar que  se corte el inicio de la siguiente verbalización con algunos dispositivos de audio como auriculares bluetooth. (#14386, @jcsteh, @mltony)
* Ahora se soporta HP Secure Browser. (#16377)

### Cambios

* Tienda de Complementos:
  * La versión mínima y la última comprobada de NVDA para un complemento ahora se muestran en el área "otros detalles". (#15776, @Nael-Sayegh)
  * La acción reseñas de la comunidad estará disponible en todas las pestañas de la tienda. (#16179, @nvdaes)
* Actualización de componentes:
  * Actualizado el transcriptor braille LibLouis a [3.29.0](https://github.com/liblouis/liblouis/releases/tag/v3.29.0). (#16259, @codeofdusk)
    * Nuevas tablas detalladas braille (con letras mayúsculas indicadas) para bieloruso y ucraniano.
    * Nueva tabla braille española para leer textos en griego.
    * Nueva tabla para Lao grado 1.
  * eSpeak NG se ha actualizado a 1.52-dev commit `cb62d93fd7`. (#15913)
    * Añadido nuevo idioma Tigrinya.
* Se cambiaron varios gestos para dispositivos BrailleSense para evitar conflictos con caracteres de la tabla braille francesa. (#15306)
  * `alt+flecha izquierda` ahora se asigna a `punto2+punto7+espacio`
  * `alt+flecha derecha` ahora se asigna a `punto5+punto7+espacio`
  * `alt+flecha arriba` ahora se asigna a `punto2+punto3+punto7+espacio`
  * `alt+flecha abajo` ahora se asigna a `punto5+punto6+punto7+espacio`
* Los puntos de relleno utilizados habitualmente en los índices ya no se indican en los niveles de puntuación baja. (#15845, @CyrilleB79)

### Corrección de Fallos

* Correcciones para Windows 11:
  * NVDA volverá a anunciar las sugerencias de entrada de teclado por hardware. (#16283, @josephsl)
  * En la Versión 24H2 (actualización de 2024 y Windows Server 2025), la interacción con el ratón y táctil puede utilizarse en ajustes rápidos. (#16348, @josephsl)
* Tienda de Complementos:
  * Al pulsar `ctrl+tab`, el foco se mueve apropiadamente al título de la pestaña actual. (#14986, @ABuffEr)
  * Si los ficheros de caché no son correctos, NVDA ya no se reiniciará. (#16362, @nvdaes)
* Correcciones para navegadores web basados en Chromium cuando se utilizan con UIA:
  * Corregidos fallos que provocan que NVDA se cuelgue. (#16393, #16394)
  * La tecla retroceso ahora funciona correctamente en campos de inicio de sesión en Gmail. (#16395)
* El retroceso ahora funciona correctamente al utilizar Nudi 6.1 con la opción de NVDA "Manejar teclas de otras aplicaciones" habilitada. (#15822, @jcsteh)
* Corregido un fallo donde las coordenadas de audio se reproducían mientras la aplicación estaba en modo durmiente cuando "Reproducir coordenadas de audio al mover el ratón" esté activada. (#8059, @hwf1324)
* En Adobe Reader, NVDA ya no ignora el texto alternativo en las fórmulas en PDFs. (#12715)
* Corregido un fallo que causa que NVDA falle al leer la cinta y las opciones dentro de Geekbench. (#16251, @mzanm)
* Corregido un caso poco frecuente en el que al guardar la configuración podía fallar el guardado de todos los perfiles. (#16343, @CyrilleB79)
* En Firefox y navegadores basados en Chromium, NVDA entrará correctamente en modo foco al pulsar intro cuando se posicione dentro de una lista de presentación (ul / ol) dentro de contenido editable. (#16325)
* El cambio de estado de columna ahora se notifica correctamente al seleccionar las columnas que se mostrarán en la lista de mensajes de Thunderbird. (#16323)
* El conmutador de línea de órdenes `-h`/`--help` funciona apropiadamente de nuevo. (#16522, @XLTechie)
* El soporte de NVDA para el software de traducción Poedit versión 3.4 o superior funciona corectamente al traducir idiomas con 1 o más de 2 formas plurales (ej.: Chino, Polaco). (#16318)

### Cambios para desarrolladores

Por favor consulta [la guía del desarrollador ](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre obsolescencias de la API de NVDA y el proceso de eliminación.

* La instanciación de objetos `winVersion.WinVersion` con versiones de Windows desconocidas por encima de 10.0.22000 como 10.0.25398 devuelve "Windows 11 unknown" en lugar de "Windows 10 unknown" para el nombre de versión. (#15992, @josephsl)
* Se facilita el proceso de compilación de AppVeyor para las bifurcaciones de NVDA, añadiendo variables configurables en appveyor.yml para deshabilitar o modificar partes específicas de los scripts de compilación de NV Access. (#16216, @XLTechie)
* Añadido un documento how-to, explicando el proceso de compilación de las bifurcaciones de NVDA en AppVeyor. (#16293, @XLTechie)

## 2024.1

Se ha añadido un nuevo modo de voz "bajo demanda".
Cuando la voz esté bajo demanda, NVDA no habla automáticamente (ej. al mover el cursor) pero aún habla al dar órdenes cuyo objetivo sea explícitamente anunciar algo (ej. anunciar el título de la ventana).
En la categoría Voz de las opciones de NVDA, ahora es posible excluir modos de voz no deseados desde la orden recorrer modos de voz (`NVDA+s`).

Un nuevo modo de selección nativa (conmutado con `NVDA+shift+f10`) ahora está disponible en el modo exploración de NVDA para Mozilla Firefox.
Cuando se active, seleccionar texto en modo exploración también manipulará la propia selección nativa en Firefox.
Copiar el texto con `control+c` pasará directamente a Firefox, copiando así el contenido enriquecido, en lugar de la representación en texsto plano de NVDA.

La Tienda de Complementos ahora admite acciones masivas (ej. instalar, habilitar complementos) seleccionando varios complementos
Hay una nueva acción para abrir una página de reseñas para el complemento seleccionado.

Las opciones dispositivo de salida audio y  modo de atenuación se han eliminado del diálogo "Seleccionar Sintetizador".
Ahora pueden encontrarse en en el panel de opciones de audio el cual se puede abrir con `NVDA+control+u`.

se han actualizado eSpeak-NG, el transcriptor braille Liblouis y el Unicode CLDR.
Están disponibles nuevas tablas braille Thai, Filipino y Rumano.

Hay muchos otros fallos corregidos, particularmente para la Tienda de Complementos, para el braille, para Libre Office, para Microsoft Office y para el audio.

### Notas importantes

* Esta versión rompe la compatibilidad con los complementos existentes.
* Ya no se soportan Windows 7 y Windows 8.
Windows 8.1 es la versión mínima soportada.

### Nuevas Características

* Tienda de Complementos:
  * La Tienda de Complementos ahora admite acciones masivas (ej. instalar, habilitar complementos) seleccionando varios complementos. (#15350, #15623, @CyrilleB79)
  * Se ha añadido una nueva acción para abrir una página web dedicada para ver o proporcionar comentarios acerca del complemento seleccionado. (#15576, @nvdaes)
* Añadido el soporte para pantallas braille Bluetooth Low Energy HID. (#15470)
* Un nuevo modo de selección nativa (conmutado con `NVDA+shift+f10`) ahora está disponible en el modo exploración de NVDA para Mozilla Firefox.
Cuando se active, seleccionar texto en modo exploración también manipulará la propia selección nativa en Firefox.
Copiar el texto con `control+c` pasará directamente a Firefox, copiando así el contenido enriquecido, en lugar de la representación en texsto plano de NVDA.
Ten en cuenta sin embargo que como Firefox está manejando la copia real, NVDA no anunciará un mensaje "copiar al portapapeles" en este modo. (#15830)
* Al copiar texto en Microsoft Word con el modo exploración de NVDA activado, ahora se incluye también el formato.
Un efecto colateral de esto es que NVDA ya no anunciará un mensaje "copiar al portapapeles" al pulsar `control+c` en el modo exploración en Microsoft Word y en Outlook, ya que la aplicación es la que ahora maneja el copiado, no NVDA. (#16129)
* Se ha añadido un nuevo modo de voz "bajo demanda".
Cuando la voz esté bajo demanda, NVDA no habla automáticamente (ej. al mover el cursor) pero aún habla al dar órdenes cuyo objetivo sea explícitamente anunciar algo (ej. anunciar el título de la ventana). (#481, @CyrilleB79)
* En la categoría Voz de las opciones de NVDA, ahora es posible excluir modos de voz no deseados desde la orden recorrer modos de voz (`NVDA+s`). (#15806, @lukaszgo1)
  * Si utilizas actualmente el complemento NoBeepsSpeechMode plantéate desinstalarlo y deshabilitar los modos "pitidos" y "bajo demanda" en las opciones.

### Cambios

* NVDA ya no soporta Windows 7 y Windows 8.
Windows 8.1 es la versión mínima soportada. (#15544)
* Actualización de componentes:
  * Actualizado el transcriptor braille LibLouis a [3.28.0](https://github.com/liblouis/liblouis/releases/tag/v3.28.0). (#15435, #15876, @codeofdusk)
    * Añadidas nuevas tablas braille para Thai, Rumano y Filipino.
  * eSpeak NG ha sido actualizado a 1.52-dev commit `530bf0abf`. (#15036)
  * CLDR emoji y symbol annotations han sido actualizados a la versión 44.0. (#15712, @OzancanKaratas)
  * Actualizado Java Access Bridge a 17.0.9+8Zulu (17.46.19). (#15744)
* Teclas de órdenes:
  * Las siguientes órdenes ahora admiten dos y tres pulsaciones para deletrear la información anunciada y para deletrear con descripción de caracteres: anunciar selección, anunciar texto del portapapeles y anunciar objeto enfocado. (#15449, @CyrilleB79)
  * La orden para conmutar la Cortina de Pantalla ahora tiene un gesto predeterminado: `NVDA+control+escape`. (#10560, @CyrilleB79)
  * Al pulsar cuatro veces, la orden de anunciar selección ahora muestra la selección en un mensaje explorable. (#15858, @Emil-18)
* Microsoft Office:
  * Al solicitar información de formato en celdas de Excel, márgenes y fondo sólo se anunciará si hay ese formato. (#15560, @CyrilleB79)
  * NVDA no anunciará de nuevo grupos no etiquetados como en menús en versiones recientes de Microsoft Office 365. (#15638)
* Las opciones dispositivo de salida audio y  modo de atenuación se han eliminado del diálogo "Seleccionar Sintetizador".
Ahora pueden encontrarse en en el panel de opciones de audio el cual se puede abrir con `NVDA+control+u`. (#15512, @codeofdusk)
* La opción "Anunciar rol cuando el ratón entre en el objeto" en la categoría opciones de Ratón de NVDA se ha renombrado a "Anunciar objeto cuando el ratón entre en él".
Esta opción ahora anuncia información relevante adicional acerca de un objeto cuando el ratón entre en él, tal como los estados  (marcado/pulsado) o coordenadas de celda en una tabla. (#15420, @LeonarddeR)
* Se han añadido nuevos elementos al menú Ayuda para la página "Obtener Ayuda" y para la tienda de NV Access. (#14631)
* El soporte de NVDA para [Poedit](https://poedit.net) ha sido revisado para Poedit versión 3 y superiores.
Se recomienda mucho a los usuarios de Poedit 1 que actualicen a Poedit 3 si quieren contar con la accesibilidad mejorada en Poedit, como los atajos para leer las notas y los comentarios para el traductor. (#15313, #7303, @LeonarddeR)
* El visualizador Braille y el visualizador de voz ahora se han desactivado en modo seguro. (#15680)
* Durante la navegación de objetos, los objetos deshabilitados (no disponibles) ya no se ignorarán. (#15477, @CyrilleB79)
* Añadido un índice al documento de órdenes clave. (#16106)

### Corrección de Fallos

* Tienda de Complementos:
  * Cuando se cambie el estado de un complemento mientras tenga el foco, ej. un cambio de "descargando" a "descargado", el elemento actualizado ahora se anuncia correctamente. (#15859, @LeonarddeR)
  * Al instalar complementos, los avisos de instalación ya no se solapan con el diálogo de reinicio. (#15613, @lukaszgo1)
  * Al reinstalar un complemento incompatible, ya no se desactiva forzosamente. (#15584, @lukaszgo1)
  * Los complementos deshabilitados e incompatibles ahora se pueden actualizar. (#15568, #15029)
  * NVDA ahora se recupera y muestra un error en caso de que un complemento no se descargue correctamente. (#15796)
  * NVDA ya no falla al reiniciarse intermitentemente después de abrir y cerrar la Tienda de Complementos. (#16019, @lukaszgo1)
* Audio:
  * NVDA ya no se conjela brevemente cuando se reproducen varios sonidos en sucesión rápida. (#15311, #15757, @jcsteh)
  * Si el dispositivo de salida de audio está configurado a algo distinto del predeterminado y ese dispositivo volviera a estar disponible después de no estarlo, NVDA ahora cambiará nuevamente al dispositivo configurado en lugar de seguir utilizando el predeterminado. (#15759, @jcsteh)
  * NVDA ahora reanuda el audio si la configuración del dispositivo cambia u otra aplicación libera el control exclusivo del dispositivo. (#15758, #15775, @jcsteh)
* Braille:
  * Las pantallas braillde con varias líneas ya no bloquearán el controlador BRLTTY y se tratarán como una pantalla contínua. (#15386)
  * Se detectan más objetos que contienen texto útil y el contenido del texto se muestra en braille. (#15605)
  * La entrada de braille contraído vuelve a funcionar correctamente. (#15773, @aaclause)
  * El braille ahora se actualiza al mover el navegador de objetos entre celdas de tabla en más situaciones. (#15755, @Emil-18)
  * Ahora se muestra en braille el resultado de las órdenes anunciar foco actual, navegador de objetos actual y selección actual. (#15844, @Emil-18)
  * El controlador braille de la Albatross ya no maneja un microcontrolador Esp32 como una pantalla Albatross. (#15671)
* LibreOffice:
  * Las palabras eliminadas utilizando el atajo de teclado `control+retroceso` ahora también se anuncian apropiadamente cuando las palabras borradas van seguidas de espacios en blanco(como espacios y tabuladores). (#15436, @michaelweghorn)
  * El anuncio de la barra de estado utilizando el atajo de teclado `NVDA+fin` ahora también funciona para diálogos en LibreOffice versión 24.2 y posteriores. (#15591, @michaelweghorn)
  * Ahora se admiten todos los atributos de texto esperados en las versiones de LibreOffice 24.2 y superiores.
  Esto hace que el anuncio de errores de ortografía funcione al anunciar una línea en Writer. (#15648, @michaelweghorn)
  * El anunciado de niveles de encabezado ahora también funciona para LibreOffice versiones 24.2 y posteriores. (#15881, @michaelweghorn)
* Microsoft Office:
  * En Excel con UIA deshabilitado, el braille se actualiza y se verbaliza la celda activa cuando se pulse `control+y`, `control+z` o `alt+retroceso`. (#15547)
  * En Word con UIA deshabilitado el braille se actualiza cuando se pulsa `control+v`, `control+x`, `control+y`, `control+z`, `alt+retroceso`, `retroceso` o `control+retroceso`.
  También se actualiza con UIA habilitado cuando se teclea texto y el braille siga a los cursores de revisión y del sistema. (#3276)
  * En Word, ahora se anunciará correctamente la celda donde se aterrice cuando se utilicen las órdenes nativas de Word para la navegación de tabla `alt+inicio`, `alt+fin`, `alt+rePág` y `alt+avPág`. (#15805, @CyrilleB79)
* Se ha mejorado el anunciado de los atajos de teclado de los objetos. (#10807, #15816, @CyrilleB79)
* El sintetizador de voz SAPI4 ahora soporta correctamente  los cambios de volumen, velocidad y tono integrados en la voz. (#15271, @LeonarddeR)
* Ahora se anuncia correctamente del estado multilínea en aplicaciones que utilizan Access Bridge. (#14609)
* NVDA anunciará contenido de diálogo para más diálogos en Windows 10 y 11. (#15729, @josephsl)
* NVDA ya no fallará al leer una página recién cargada en Microsoft Edge al utilizar UI Automation. (#15736)
* Cuando se utiliza leer todo u órdenes que deletreen testo, las pausas entre frases o caracteres ya no disminuyen gradualmente con el tiempo. (#15739, @jcsteh)
* NVDA ya no se congela a veces cuando se verbaliza una gran cantidad de texto. (#15752, @jcsteh)
* Al acceder a Microsoft Edge utilizando UI Automation, NVDA puede activar más controles en modo exploración. (#14612)
* NVDA ya no fallará al arrancar cuando el fichero de configuración esté corrompido, sino que restaurará la configuración a la predeterminada como lo hacía en el pasado. (#15690, @CyrilleB79)
* Corregido el soporte para los controles System List view (`SysListView32`) en aplicaciones Windows Forms. (#15283, @LeonarddeR)
* Ya no es posible sobrescribir el historial de la consola Python de NVDA. (#15792, @CyrilleB79)
* NVDA debería continuar respondiendo cuando se inunda con muchos eventos UI Automation, ej. cuando se imprimen grandes trozos de texto en una terminal o cuando se escuchan mensajes de voz en WhatsApp messenger. (#14888, #15169)
  * Este nuevo comportamiento se puede deshabilitar utilizando la nueva opción "Utilizar proceso mejorado de eventos" en las opciones avanzadas de NVDA.
* NVDA es capaz de nuevo de seguir el foco en aplicaciones que se ejecuten dentro de Windows Defender Application Guard (WDAG). (#15164)
* El texto verbalizado ya no se actualiza cuando el ratón se mueve en el Visualizador de Voz. (#15952, @hwf1324)
* NVDA volverá a cambiar al modo exploración al cerrar cuadros combinados con `escape` o `alt+Flecha arriba` en Firefox o Chrome. (#15653)
* Moverse arriba y abajo con las flechas en cuadros combinados en iTunes ya no cambiará inapropiadamente a modo exploración. (#15653)

### Cambios para Desarrolladores

Por favor consulta [la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre el proceso de obsolescencia y eliminación de la API de NVDA.

* Nota: esta es una versión que rompe la compatibilidad con la API de complementos.
Los complementos necesitarán volver a comprobarse y tener sus manifiestos actualizados.
* Compilar NVDA ahora requiere de Visual Studio 2022.
Por favor consulta los [NVDA docs](https://github.com/nvaccess/nvda/blob/release-2024.1/projectDocs/dev/createDevEnvironment.md) para una lista específica de componentes de Visual Studio. (#14313)
* Añadidos los siguientes puntos de extensión:
  * `treeInterceptorHandler.post_browseModeStateChange`. (#14969, @nvdaes)
  * `speech.speechCanceled`. (#15700, @LeonarddeR)
  * `_onErrorSoundRequested` (debería recuperarse llamando `logHandler.getOnErrorSoundRequested()`) (#15691, @CyrilleB79)
* Ahora es posible utilizar formas plurales en las traducciones de complementos. (#15661, @beqabeqa473)
* Incluido python3.dll en la distribución de binarios para utilizar por complementos con librerías externas utilizando la [stable ABI](https://docs.python.org/3.11/c-api/stable.html). (#15674, @mzanm)
* La clase base `BrailleDisplayDriver` ahora tiene las propiedades `numRows` y `numCols` para proporcionar información acerca de pantallas braille de varias líneas.
La configuración de `numCells` todavía está admitida para pantallas braille de una sola línea y `numCells` devolverá el número total de celdas para pantallas braille de varias líneas. (#15386)
* Actualizado BrlAPI para BRLTTY a la versión 0.8.5y su correspondiente módulo python a la compilación compatible Python 3.11. (#15652, @LeonarddeR)
* Añadida la función `speech.speakSsml`, que te permite escribir secuencias de voz de NVDA utilizando [SSML](https://www.w3.org/TR/speech-synthesis11/). (#15699, @LeonarddeR)
  * Las siguientes etiquetas se admiten actualmente y se traducen a las órdenes de voz  apropiadas de NVDA:
    * `Prosody` (`pitch`, `rate` y `volume`). sólo multiplicación (ej. `200%` se soporta.
    * `say-as` con el atributo `interpret` configurado a `characters`
    * `voice` con el `xml:lang` configurado a un lenguaje XML
    * `break` con el atributo `time` configurado a un valor en milésimas de segundo, ej. `200ms`
    * `mark` con el atributo `name` configurado a un nombre de marca, ej. `mark1`, requiere proporcionar una callback
  * Ejemplo: `speech.speakSsml('<speak><prosody pitch="200%">hello</prosody><break time="500ms" /><prosody rate="50%">John</prosody></speak>')`
  * Las funciones de análisis sintáctico de SSML están respaldadas por la clase `SsmlParser` en el módulo `speechXml`.
* Cambios para la librería NVDA Controller Client:
  * Los nombres de fichero de la librería ya no contienen un sufijo denotando la arquitectura, es decir, `nvdaControllerClient32/64.dll` ahora se llama `nvdaControllerClient.dll`. (#15718, #15717, @LeonarddeR)
  * Añadido un ejemplo para demostrar el uso de nvdaControllerClient.dll desde Rust. (#15771, @LeonarddeR)
  * Añadidas las siguientes funciones al controller client: (#15734, #11028, #5638, @LeonarddeR)
    * `nvdaController_getProcessId`: para obtener el id de proceso (PID) de la instancia actual que está utilizando el NVDA controller client.
    * `nvdaController_speakSsml`: para instruir a NVDA que hable de acuerdo con el SSML dado. Esta función también soporta:
      * Proporcionar el nivel de símbolos.
      * Proporcionar la prioridad de la voz a ser verbalizada.
      * Verbalizar síncronamente (bloqueando) y asíncronamente (devolución instantánea).
    * `nvdaController_setOnSsmlMarkReachedCallback`: Para registrar una llamada de tipo `onSsmlMarkReachedFuncType` eso se llama en modo síncrono para cada `<mark />` tag encontrado en la secuencia SSML proporcionada a `nvdaController_speakSsml`.
  * Nota: las funciones nuevas en el controller client sólo soportan NVDA 2024.1 y posteriores.
* Actualizadas dependencias `include`:
  * detours a `4b8c659f549b0ab21cf649377c7a84eb708f5e68`. (#15695)
  * ia2 a `3d8c7f0b833453f761ded6b12d8be431507bfe0b`. (#15695)
  * sonic a `8694c596378c24e340c09ff2cd47c065494233f1`. (#15695)
  * w3c-aria-practices a `9a5e55ccbeb0f1bf92b6127c9865da8426d1c864`. (#15695)
  * wil a `5e9be7b2d2fe3834a7107f430f7d4c0631f69833`. (#15695)
* Información del dispositivo por `hwPortUtils.listUsbDevices` ahora contiene el bus que anuncia la descripción del dispositivo USB (key `busReportedDeviceDescription`). (#15764, @LeonarddeR)
* Para dispositivos USB serie, `bdDetect.getConnectedUsbDevicesForDriver` y `bdDetect.getDriversForConnectedUsbDevices` ahora produce coincidencias de dispositivo que contienen un diccionario `deviceInfo` enriquecido con datos sobre el dispositivo USB, como `busReportedDeviceDescription`. (#15764, @LeonarddeR)
* Cuando el fichero de configuración `nvda.ini` está corrompido, se guarda una copia de seguridad antes de reiniciarse. (#15779, @CyrilleB79)
* Cuando se define un script con el decorador de script, el argumento booleano `speakOnDemand` puede especificarse para controlar si un script debería hablar mientras se esté en el modo de voz "bajo demanda". (#481, @CyrilleB79)
  * Los Scripts que proporcionan información (ej. decir título de ventana, anunciar hora/fecha) deberían hablar en el modo de voz "bajo demanda".
  * Los Scripts que realicen una acción (ej. mover el cursor, cambiar un parámetro) no deberían verbalizarse en el modo "bajo demanda".
* Corregido un fallo donde al eliminar ficheros git-tracked durante `scons -c` resultaba en falta de interfaces UIA COM al recompilar. (#7070, #10833, @hwf1324)
* Corregido un fallo donde algunos cambios de código no se detectaban al compilar `dist`, lo que impedía que se activara una nueva compilación.
Ahora `dist` siempre recompila. (#13372, @hwf1324)
* Un `gui.nvdaControls.MessageDialog` con un tipo predeterminado de estándar, ya no lanza una excepción de conversión none porque no se haya asignado ningún sonido. (#16223, @XLTechie)

#### Cambios que Rompen la API

Estos son los cambios que rompen la API.
Por favor abre un GitHub issue si tu complemento tiene un problema con la actualización a la nueva API.

* NVDA ahora se compila con Python 3.11. (#12064)
* Actualizadas las dependencias pip:
  * configobj a 5.1.0dev commit `e2ba4457c4651fa54f8d59d8dcdd3da950e956b8`. (#15544)
  * Comtypes a 1.2.0. (#15513, @codeofdusk)
  * Flake8 a 4.0.1. (#15636, @lukaszgo1)
  * py2exe a 0.13.0.1dev commit `4e7b2b2c60face592e67cb1bc935172a20fa371d`. (#15544)
  * robotframework a 6.1.1. (#15544)
  * SCons a 4.5.2. (#15529, @LeonarddeR)
  * sphinx a 7.2.6. (#15544)
  * wxPython a 4.2.2a commit `0205c7c1b9022a5de3e3543f9304cfe53a32b488`. (#12551, #16257)
* Dependencias pip eliminadas:
  * typing_extensions, estas se soportarían nativamente en Python 3.11 (#15544)
  * nota, en su lugar se utiliza unittest-xml-reporting para generar informes XML. (#15544)
* `IAccessibleHandler.SecureDesktopNVDAObject` se ha eliminado.
En su lugar, cuando NVDA está en ejecución en el perfil de usuario, rastrea la existencia del escritorio seguro con el punto de extensión: `winAPI.secureDesktop.post_secureDesktopStateChange`. (#14488)
* `braille.BrailleHandler.handlePendingCaretUpdate` se ha eliminado sin remplazo público. (#15163, @LeonarddeR)
* `bdDetect.addUsbDevices y bdDetect.addBluetoothDevices` se han eliminado.
Los controladores de pantallas braille deberían implementar el método de la clase `registerAutomaticDetection` en su lugar.
Ese método recibe un objeto `DriverRegistrar` en el que los métodos `addUsbDevices` y `addBluetoothDevices` pueden usarse. (#15200, @LeonarddeR)
* La implementación predeterminada del método de  comprobación en `BrailleDisplayDriver` ahora requiere que los atributos `threadSafe` y `supportsAutomaticDetection` estén configurados a `True`. (#15200, @LeonarddeR)
* Pasar funciones lambda a `hwIo.ioThread.IoThread.queueAsApc` ya no es posible, ya que las funciones deberían ser débilmente referenciables. (#14627, @LeonarddeR)
* `IoThread.autoDeleteApcReference` ha sido eliminada. (#14924, @LeonarddeR)
* Para admitir cambios de tonos para mayúsculas, los sintetizadores deben declarar ahora explícitamente su comptaibilidad con `PitchCommand` en el atributo `supportedCommands` en el controlador. (#15433, @LeonarddeR)
* `speechDictHandler.speechDictVars` se ha eliminado. Utiliza `NVDAState.WritePaths.speechDictsDir` en lugar de `speechDictHandler.speechDictVars.speechDictsPath`. (#15614, @lukaszgo1)
* `languageHandler.makeNpgettext` y `languageHandler.makePgettext` se han eliminado.
`npgettext` y `pgettext` ahora se soportan nativamente. (#15546)
* El app module para [Poedit](https://poedit.net) ha sido cambiado significativamente. La función `fetchObject` function se ha eliminado. (#15313, #7303, @LeonarddeR)
* Los siguientes tipos y constantes redundantes se han eliminado  de `hwPortUtils`: (#15764, @LeonarddeR)
  * `PCWSTR`
  * `HWND` (remplazado por `ctypes.wintypes.HWND`)
  * `ULONG_PTR`
  * `ULONGLONG`
  * `NULL`
  * `GUID` (remplazado por `comtypes.GUID`)
* `gui.addonGui.AddonsDialog` se ha eliminado. (#15834)
* `touchHandler.TouchInputGesture.multiFingerActionLabel` se ha eliminado sin remplazo. (#15864, @CyrilleB79)
* `NVDAObjects.IAccessible.winword.WordDocument.script_reportCurrentHeaders` se ha eliminado sin remplazo. (#15904, @CyrilleB79)
* Los siguientes app modules se han eliminado.
El código que importe de uno de ellos debería importar de sus substitutos. (#15618, @lukaszgo1)

| Nombre del módulo eliminado |Módulo de remplazo|
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

* Utilizar `watchdog.getFormattedStacksForAllThreads` está obsoleto - por favor utiliza `logHandler.getFormattedStacksForAllThreads` en su lugar. (#15616, @lukaszgo1)
* `easeOfAccess.canConfigTerminateOnDesktopSwitch` ha quedado obsoleto, ya que quedó obsoleto al terminarse el soporte de Windows 7. (#15644, @LeonarddeR)
* `winVersion.isFullScreenMagnificationAvailable` ha quedado obsoleto - utiliza `visionEnhancementProviders.screenCurtain.ScreenCurtainProvider.canStart` en su lugar. (#15664, @josephsl)
* Las siguientes constantes de versión de Windows han quedado obsoletas  del módulo winVersion (#15647, @josephsl):
  * `winVersion.WIN7`
  * `winVersion.WIN7_SP1`
  * `winVersion.WIN8`
* Las constantes `bdDetect.KEY_*` han quedado obsoletas.
Utiliza `bdDetect.DeviceType.*` en su lugar. (#15772, @LeonarddeR).
* Las constantes `bdDetect.DETECT_USB` y `bdDetect.DETECT_BLUETOOTH` han quedado obsoletas  sin remplazo público. (#15772, @LeonarddeR).
* Utilizar `gui.ExecAndPump` está obsoleto - por favor utiliza `systemUtils.ExecAndPump` en su lugar. (#15852, @lukaszgo1)

## 2023.3.4

Este es un parche para corregir un fallo de seguridad y un fallo del instalador.
Por favor comunica responsablemente los problemas de seguridad siguiendo las [políticas de seguridad de NVDA](https://github.com/nvaccess/nvda/blob/master/security.md).

### Correcciones de Seguridad

* Evita cargar la configuración personalizada mientras se fuerza el modo seguro .
([GHSA-727q-h8j2-6p45](https://github.com/nvaccess/nvda/security/advisories/GHSA-727q-h8j2-6p45))

### Corrección de Fallos

* Corregido un fallo que provocaba que el proceso de NVDA fallase al no salir correctamente. (#16123)
* Se corrige un fallo donde si el proceso de NVDA anterior fallaba al salir correctamente, una instalación podía entrar en un estado irrecuperable. (#16122)

## 2023.3.3

Se trata de un parche para solucionar un problema de seguridad.
Por favor revela responsablemente los problemas de seguridad siguiendo las [políticas de seguridad](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correcciones de seguridad

* Evita un posible ataque XSS reflejado a partir de contenido crafteado para provocar la ejecución de código arbitrario.
([GHSA-xg6w-23rw-39r8](https://github.com/nvaccess/nvda/security/advisories/GHSA-xg6w-23rw-39r8))

## 2023.3.2

Se trata de un parche para solucionar un problema de seguridad.
El parche de seguridad en 2023.3.1 no se resolvió correctamente.
Por favor revela responsablemente los problemas de seguridad siguiendo las [políticas de seguridad](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correcciones de Seguridad

* El parche de seguridad en 2023.3.1 no se resolvió correctamente.
Evita el posible acceso al sistema y la ejecución de código arbitrario con privilegios del sistema para usuarios no autenticados..
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3.1

Se trata de un parche para solucionar un problema de seguridad.
Por favor revela responsablemente los problemas de seguridad siguiendo las [políticas de seguridad](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correcciones de Seguridad

* Evita el posible acceso al sistema y la ejecución de código arbitrario con privilegios del sistema para usuarios no autenticados.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3

Esta versión incluye mejoras en el rendimiento, la respuesta y la estabilidad de la salida de audio.
Se han añadido opciones para controlar el volumen de los sonidos y pitidos de NVDA, o para tenerlos siguiendo el volumen de la voz que estés usando.

NVDA ahora puede refrescar periódicamente los resultados del OCR, verbalizando el texto nuevo según aparezca.
Esto puede configurarse en la categoría de OCR de Windows del diálogo opciones de NVDA.

Se han realizado varias correcciones en el braille, mejorando la detección de dispositivos, y en el movimiento del cursor.
Ahora es posible excluir controladores no deseados de la detección automática para mejorar el rendimiento de la autodetección.
También hay nuevas órdenes para BRLTTY.

También se han corregido errores en la tienda de complementos, en Microsoft Office, en los menús de contexto de Microsoft Edge, y en la calculadora de Windows.

### Nuevas Características

* Mejorada la gestión del sonido:
  * Un nuevo panel de opciones de Audio:
    * Esto puede abrirse con `NVDA+control+u`. (#15497)
    * Una opción para hacer que el volumen de los sonidos y pitidos de NVDA siga a la configuración de volúmen de la voz que estés utilizando. (#1409)
    * Una opción para configurar por separado el volumen de los sonidos de NVDA. (#1409, #15038)
    * Las opciones para cambiar el dispositivo de salida de audio y conmutar la atenuación de audio se han movido al nuevo diálogo Opciones de audio del diálogo Seleccionar Sintetizador.
    Estas opciones se eliminarán del diálogo "seleccionar Sintetizador" en 2024.1. (#15486, #8711)
  * NVDA ahora sacará el audio a través de la Windows Audio Session API (WASAPI), lo que puede mejorar la respuesta, el rendimiento y la estabilidad de la voz y de los sonidos de NVDA. (#14697)
  * Nota: WASAPI es incompatible con algunos complementos.
  Hay actualizaciones compatibles disponibles para estos complementos, por favor actualízalos antes de actualizar NVDA.
  Las versiones incompatibles de estos complementos se deshabilitarán al actualizar NVDA:
    * Tony's Enhancements versión 1.15 o anteriores. (#15402)
    * NVDA global commands extension 12.0.8 o anteriores. (#15443)
* NVDA ahora puede actualizar continuamente el resultado al realizar el reconocimiento óptico de caracteres (OCR), verbalizando el texto nuevo según aparezca. (#2797)
  * Para habilitar esta funcionalidad, activa la opción "Refrescar periódicamente el contenido reconocido" en la categoría OCR de Windows del diálogo de opciones de NVDA.
  * Una vez habilitado, puedes conmutar la verbalización de texto nuevo activando anunciar cambios de contenido dinámico (pulsando `NVDA+5`).
* Al utilizar la detección automática de pantallas braille, ahora es posible excluir los controladores de la detección del diálogo de selección de pantalla braille. (#15196)
* Una nueva opción en las opciones de Formateado de Documentos, "Ignorar líneas en blanco para el anunciado de sangría de línea". (#13394)
* Se añadió un gesto sin asignar para navegar por grupos de pestañas en modo exploración. (#15046)

### Cambios

* Braille:
  * Cuando el texto en una terminal cambia sin actualizar el cursor del sistema, el texto en una pantalla braille ahora se actualizará correctamente al situarse sobre una línea que haya cambiado.
  Esto incluye situaciones donde el braille esté siguiendo a la revisión. (#15115)
  * Más combinaciones de teclas para BRLTTY están asignadas ahora a órdenes de NVDA (#6483):
    * `learn`: conmuta la ayuda de entrada de NVDA
    * `prefmenu`: abre el menú de NVDA
    * `prefload` y `prefsave`: carga y guarda la configuración de NVDA
    * `time`: muestra la hora
    * `say_line`: verbaliza la línea actual donde esté colocado el cursor de revisión
    * `say_below`: lee todo utilizando el cursor de revisión
  * El controlador BRLTTY sólo está disponible cuando esté en ejecución una instancia BRLTTY con BrlAPI habilitado. (#15335)
  * Se ha eliminado la configuración avanzada para habilitar la compatibilidad con HID braille en favor de una nueva opción.
  Ahora puedes desactivar la auto detección de controladores específicos para pantallas braille en el diálogo de selección de pantalla braille. (#15196)
* Tienda de complementos: los complementos instalados ahora se enumerarán en la pestaña Complementos Disponibles, si todavía están disponibles en la tienda. (#15374)
* Algunos atajos de teclado se han actualizado en el menú NVDA. (#15364)

### Corrección de Fallos

* Microsoft Office:
  * Corrección de un fallo en Microsoft Word cuando las opciones de formateado de documentos "anunciar encabezados" y "anunciar comentarios y notas" no estaban activadas. (#15019)
  * En Word y Excel, la alineación de texto se anunciará correctamente en más situaciones. (#15206, #15220)
  * Corrección del anunciado de algunos atajos de formato de celda en Excel. (#15527)
* Microsoft Edge:
  * NVDA ya no retrocederá a la última posición del modo exploración al abrir el menú de contexto en Microsoft Edge. (#15309)
  * NVDA vuelve a ser capaz de leer menús de contexto de descargas en Microsoft Edge. (#14916)
* Braille:
  * El cursor braille y los indicadores de selección ahora siempre se actualizan correctamente después de mostrar u ocultar los indicadores respectivos con un gesto. (#15115)
  * Corregido un fallo donde las pantallas braille Albatross intentan inicializarse aunque otro dispositivo braille haya sido conectado. (#15226)
* Tienda de Complementos:
  * Corregido un fallo donde al desmarcar "incluir complementos incompatibles" provocaría que los complementos incompatibles siguieran apareciendo en la tienda. (#15411)
  * Los complementos bloqueados debido a razones de compatibilidad ahora deberían filtrarse correctamente al conmutar el filtro por estado habilitado y deshabilitado. (#15416)
  * Corregido un fallo que evita que se actualicen o substituyan complementos incompatibles instalados y habilitados mediante la herramienta de instalación externa. (#15417)
  * Corregido un fallo donde NVDA no hablaría hasta que se reiniciase después de la instalación de un complemento. (#14525)
  * Corregido un fallo donde los complementos no pueden instalarse si falló o se canceló una descarga anterior. (#15469)
  * Corregidos problemas con el manejo de complementos imcompatibles al actualizar NVDA. (#15414, #15412, #15437)
* NVDA vuelvbe a anunciar los resultados de cálculo en la calculadora de Windows 32bit en las versiones Server, LTSC y LTSB de Windows. (#15284)
* NVDA ya no ignora los cambios del foco cuando una ventana anidada (ventana hija) obtiene el foco. (#15432)
* Se corrigió una posible causa de bloqueo durante el arranque de NVDA. (#15517)

### Cambios para Desarrolladores

Por favor consulta [la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre el proceso de obsolescencia y eliminación de la API de NVDA.

* `braille.handler.handleUpdate` y `braille.handler.handleReviewMove` han sido cambiadas para no actualizar instantáneamente.
Antes de este cambio, cuando se llamaba a cualquiera de estos métodos con mucha frecuencia, esto consumiría muchos recursos.
Estos métodos ahora ponen en cola una actualización al final de cada ciclo del núcleo en su lugar.
También deberían ser seguros para los hilos, haciendo posible llamarlos desde hilos en segundo plano. (#15163)
* Se añadió el soporte oficial para registrar controladores personalizados de pantallas braille en el proceso de detección automática de pantallas braille.
Consulta la documentación de la clase `braille.BrailleDisplayDriver` para más detalles.
En particular, el atributo `supportsAutomaticDetection` debe tener el valor `True` y debe implementarse el método `registerAutomaticDetection` `classmethod`.  (#15196)

#### Obsolescencias

* `braille.BrailleHandler.handlePendingCaretUpdate` está obsoleto y no tiene substituto público.
Se eliminará en 2024.1. (#15163)
* Importar las constantes `xlCenter`, `xlJustify`, `xlLeft`, `xlRight`, `xlDistributed`, `xlBottom`, `xlTop` desde `NVDAObjects.window.excel` está obsoleto.
Utiliza las enumeraciones `XlHAlign` o `XlVAlign` en su lugar. (#15205)
* La asignación `NVDAObjects.window.excel.alignmentLabels` está obsoleta.
Utiliza los métodos `displayString` de las enumeraciones `XlHAlign` o `XlVAlign` en su lugar. (#15205)
* `bdDetect.addUsbDevices` y `bdDetect.addBluetoothDevices` están obsoletas.
Los controladores de pantallas Braille deberían implementar el método de clase `registerAutomaticDetection` en su lugar.
Ese método recibe un objeto `DriverRegistrar` en cuyos métodos `addUsbDevices` y`addBluetoothDevices` pueden utilizarse. (#15200)
* La implementación predeterminada del método de comprobación en `BrailleDisplayDriver` utiliza `bdDetect.driverHasPossibleDevices` para los dispositivos que están marcados como hilo seguro.
A partir de NVDA 2024.1, para que el método base utilice `bdDetect.driverHasPossibleDevices`, el atributo `supportsAutomaticDetection` también debe tener el valor `True`. (#15200)

## 2023.2

Esta versión introduce la Tienda de Complementos para remplazar el Administrador de Complementos.
En la Tienda de Complementos puedes explorar, buscar, instalar y actualizar complementos de la comunidad.
También puedes anular manualmente problemas de incompatibilidad con complementos desactualizados bajo tu propia responsabilidad.

Hay nuevas características, órdenes y soporte para pantallas braille.
También hay nuevos gestos de entrada para el OCR y para la navegación plana de objetos.
Se mejoró la navegación y el anunciado del formato en Microsoft Office.

Hay muchos más fallos corregidos, particularmente para el braille, Microsoft Office, navegadores web y Windows 11.

se han actualizado eSpeak-NG, el transcriptor braille Liblouis y Unicode CLDR.

### Nuevas Características

* Se ha añadido la Tienda de Complementos a NVDA. (#13985)
  * Explorar, buscar, instalar y actualizar complementos de la comunidad.
  * Anular manualmente los problemas de compatibilidad con complementos obsoletos.
  * El Gestor de Complementos se ha eliminado y remplazado por la tienda de Complementos.
  * Para más información lee por favor la Guía del usuario actualizada.
* Nuevos gestos de entrada:
  * Un gesto no asignado para recorrer los idiomas disponibles para el OCR de Windows. (#13036)
  * Un gesto no asignado para recorrer los modos de mostrado de mensajes braille. (#14864)
  * Un gesto no asignado para conmutar el mostrado del indicador de selección para el Braille. (#14948)
  * Se añadieron asignaciones para gestos de teclado predeterminados para desplazarse a los objetos siguientes o anteriores en una vista plana  de la jerarquía de objetos. (#15053)
    * Escritorio: `NVDA+9 teclado numérico` y `NVDA+3 teclado numérico` para desplazarse a los objetos anterior y siguiente respectivamente.
    * Portátil: `shift+NVDA+[` y `shift+NVDA+]` para desplazarse a los objetos anterior y siguiente respectivamente.
* Nuevas características Braille:
  * Se añadió el soporte para el activador Help Tech de pantallas Braille. (#14917)
  * Una opción nueva para conmutar  el mostrado del indicador de selección (puntos 7 y 8). (#14948)
  * Una opción nueva para mover el cursor del sistema o el foco opcionalmente cuando se cambie la posición del cursor de revisión con los sensores Braille. (#14885, #3166)
  * Al pulsar el `2 teclado numérico` tres veces para anunciar el valor numérico del carácter en la posición del cursor de revisión, la información ahora también se proporciona en Braille. (#14826)
  * Se añadió el soporte para el atributo ARIA 1.3 `aria-brailleroledescription` , permitiendo a los autores web anular el tipo de un elemento mostrado en la pantalla Braille. (#14748)
  * Controlador de Baum Braille: se añadieron varios gestos cor Braille para realizar órdenes comunes de teclado tales como `windows+d` y `alt+tab`.
  Por favor consulta la Guía del Usuario de NVDA para una lista completa. (#14714)
* Se añadió la pronunciación de símbolos Unicode:
  * símbolos braille como `⠐⠣⠃⠗⠇⠐⠜`. (#14548)
  * El símbolo de la tecla Opción del Mac `⌥`. (#14682)
* Se añadieron gestos para pantallas braille Tivomatic Caiku Albatross. (#14844, #15002)
  * mostrar el diálogo de opciones braille
  * acceder a la barra de estado
  * recorrer las formas del cursor braille
  * recorrer los modos de mostrado de mensajes braille
  * activar y desactivar el cursor braille
  * conmutar el mostrado del estado del indicador de selección braille
  * recorrer los modos "braille mueve el cursor del sistema al enrutar el cursor de revisión". (#15122)
* Características de Microsoft Office:
  * Cuando el texto subrayado esté habilitado en el formateado de documentos, ahora se anuncian los colores de resaltado en Microsoft Word. (#7396, #12101, #5866)
  * Cuando los colores estén habilitados en formateado de documentos, los colores de fondo ahora se anuncian en Microsoft Word. (#5866)
  * Al utilizar atajos de teclado de Excel para conmutar formato como negrita, cursiva, subrayado y tachado en una celda, ahora se anuncia el resultado. (#14923)
* Mejora experimental de la gestión del sonido:
  * NVDA ahora puede sacar el audio a través de la Windows Audio Session API (WASAPI), la cual puede mejorar la respuesta, el rendimiento y la estabilidad de la voz y los sonidos de NVDA. (#14697)
  * El uso de WASAPI puede habilitarse en las opciones Avanzadas.
  Adicionalmente, si WASAPI está habilitado, también pueden configurarse las siguientes opciones avanzadas.
    * Una opción para tener el volumen de los sonidos y pitidos de NVDA siguiendo a la opción de volumen de la voz que estés usando. (#1409)
    * Una opción para configurar por separado el volumen de los sonidos de NVDA. (#1409, #15038)
  * Hay un fallo conocido con un cuelgue intermitente cuando WASAPI está habilitado. (#15150)
* En Mozilla Firefox y en Google Chrome, NVDA ahora anuncia cuando un control abre un diálogo, una cuadrícula, una lista o un árbol si el autor ha especificado este uso de `aria-haspopup`. (#14709)
* Ahora es posible utilizar variables del sistema (tales como `%temp%` o `%homepath%`) en la especificación de la ruta mientras se crean copias portables de NVDA. (#14680)
* En la actualización Windows 10 May 2019 y posteriores, NVDA puede anunciar los nombres de los escritorios virtuales al abrirlos, cambiarlos y cerrarlos. (#5641)
* Se ha añadido un parámetro en todo el sistema para permitir a los usuarios y a los administradores del sistema forzar a NVDA a arrancar en modo seguro. (#10018)

### Cambios

* Actualizaciones de componentes:
  * eSpeak NG se ha actualizado a 1.52-dev commit `ed9a7bcf`. (#15036)
  * Actualizado el transcriptor braille LibLouis a [3.26.0](https://github.com/liblouis/liblouis/releases/tag/v3.26.0). (#14970)
  * CLDR se ha actualizado a la versión 43.0. (#14918)
* Cambios para LibreOffice:
  * Al anunciar la posición del cursor de revisión, la posición actual del cursor ahora se anuncia relativa a la página actual en LibreOffice Writer para versiones de LibreOffice >= 7.6, de modo similar a lo que se hace para Microsoft Word. (#11696)
  * El anunciado de la barra de estado  (ej.: disparada por `NVDA+fin`) funciona para LibreOffice. (#11698)
  * Al desplazarse a una celda diferente en LibreOffice Calc, NVDA ya no anuncia incorrectamente las coordenadas de la celda enfocada anteriormente cuando el anunciado de coordenadas de celda esté deshabilitado en las opciones de NVDA. (#15098)
* Cambios braille:
  * Al utilizar una pantalla braille a través del controlador Standard HID braille, el dpad puede utilizarse para emular las flechas y el intro.
  También `espacio+punto1` y `espacio+punto4` ahora se asignan a flechas arriba y abajo respectivamente. (#14713)
  * Las actualizaciones para el contenido web dinámico (regiones ARIA live) ahora se muestran en braille.
  Esto puede deshabilitarse en el panel de las opciones Avanzadas. (#7756)
* Los símbolos guión y raya siempre se enviarán al sintetizador. (#13830)
* La distancia anunciada en Microsoft Word ahora respetará la unidad definida en las opciones avanzadas de Word, incluso cuando se utilice UIA para acceder a documentos de Word. (#14542)
* NVDA responde más rápido al mover el cursor en controles de edición. (#14708)
* El script para anunciar el destino de un enlace ahora anuncia desde la posición del cursor del sistema o del foco en lugar desde el navegador de objetos. (#14659)
* La creación de la copia portable ya no requiere que se introduzca una letra de unidad como parte de la ruta absoluta. (#14681)
* Si Windows se configura para mostrar segundos en el reloj de la bandeja del sistema, utilizar `NVDA+f12` para anunciar la hora ahora hace caso a esa configuración. (#14742)
* NVDA ahora anunciará grupos sin etiquetar que tengan una información de posición útil, tales como en los menús en versiones recientes de Microsoft Office 365. (#14878)

### Corrección de Fallos

* Braille:
  * Varias correcciones de estabilidad de entrada/salida para pantallas braille, resultando en menos errores frecuentes y cuelgues de NVDA. (#14627)
  * NVDA ya no cambia innecesariamente a sin braille muchas veces durante la autodetección, resultando en un registro más limpio y menos consumo general. (#14524)
  * NVDA ahora volverá a USB si un dispositivo HID Bluetooth (como la HumanWare Brailliant o la APH Mantis) se detecta automáticamente y una conexión USB queda disponible.
  Esto sólo funciona para puertos serie Bluetooth antes. (#14524)
  * Cuando la pantalla sin braille esté conectada y el visualizador braille esté cerrado pulsando `alt+f4` o haciendo clic en el botón cerrar, el tamaño de la pantalla del subsistema braille se reiniciará de nuevo a sin celdas. (#15214)
* Navegadores Web:
  * NVDA ya no provoca ocasionalmente que Mozilla Firefox se cuelgue o deje de responder. (#14647)
  * En Mozilla Firefox y Google Chrome, los caracteres escritos ya no se anuncian en algunos cuadros de texto cuando verbalizar caracteres al escribir esté desactivado. (#14666)
  * Ahora puedes utilizar modo exploración en controles integrados de Chromium donde no era posible anteriormente. (#13493, #8553)
  * En Mozilla Firefox, mover el ratón sobre el texto después de un enlace ahora anuncia el texto de forma fiable. (#9235)
  * El destino de los enlaces gráficos ahora se anuncia corectamente en Chrome y en Edge. (#14779)
  * Al intentar anunciar la URL para un enlace sin un atributo href NVDA ya no queda en silencio.
  En su lugar NVDA anuncia que el enlace no tiene destino. (#14723)
  * En modo exploración, NVDA ya no ignora incorrectamente el movimiento del foco a un control padre o hijo por ejemplo moverse desde un control elemento de lista a su padre. (#14611)
    * Ten en cuenta, no obstante, que esta corrección sólo se aplica cuando la opción "Poner automáticamente el foco en elementos enfocables" en las opciones de Modo exploración esté desactivada (lo cual es lo predeterminado).
* Correcciones para Windows 11:
  * NVDA puede volver a anunciar el contenido de la barra de estado de Notepad. (#14573)
  * Al cambiar entre pestañas se anunciará el nombre de la nueva pestaña y la posición para Notepad y para el Explorador de Archivos. (#14587, #14388)
  * NVDA volverá a anunciar los elementos candidatos al introducir texto en idiomas como el Chino y el Japonés. (#14509)
  * De nuevo es posible abrir los elementos Colaboradores y Licencia en el menú ayuda de NVDA. (#14725)
* Correcciones para Microsoft Office:
  * Al desplazarse rápidamente por las celdas en Excel,  ahora es menos probable que NVDA anuncie la celda o selección incorrectas. (#14983, #12200, #12108)
  * Al aterrizar en una celda de Excel desde fuera de una hoja de cálculo, el braille y el resaltador del foco ya no se actualizan innecesariamente al objeto que tenía el foco anteriormente. (#15136)
  * NVDA ya no falla al anunciar campos de contraseña enfocables en Microsoft Excel y en Outlook. (#14839)
* Para símbolos que no tengan una descripción de símbolo en el idioma actual, se utilizará el nivel de símbolo en inglés. (#14558, #14417)
* Ahora es posible utilizar el carácter barra inversa en el campo remplazar de una entrada de diccionario, cuando el tipo no se ajusta como una expresión regular. (#14556)
* En la calculadora de Windows 10 y 11, una copia portable de NVDA ya no hará nada ni reproducirá tonos de error al introducir expresiones en la calculadora estándar en el modo de superposición compacto. (#14679)
* NVDA vuelve a recuperarse de muchas más situaciones, como aplicaciones que dejan de responder, que antes provocaban que se congelara por completo. (#14759)
* Al forzar la compatibilidad con UIA con determinadas terminales y consolas, se corrige un error que provocaba la congelación y la basura en el archivo de registro. (#14689)
* NVDA ya no rechazará guardar la configuración después de que se reinicie una configuración. (#13187)
* Al ejecutar una versión temporal  desde un lanzador, NVDA no engañará al usuario haciéndole creer que  puede guardar la configuración. (#14914)
* NVDA ahora responde generalmente un poco más rápido a las órdenes y a los cambios del foco. (#14928)
* La visualización de las opciones del OCR no fallará en algunos sistemas nunca más. (#15017)
* Se corrige un fallo relacionado con guardar y cargar la configuración de NVDA, incluyendo cambiar sintetizadores. (#14760)
* Se corrige un fallo que hacía que el gesto táctil de revisión de texto "flic arriba" moviese páginas en lugar de mover a la línea anterior. (#15127)

### Cambios para Desarrolladores

Por favor, consulta [la Guía del Desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para obtener información sobre el proceso de obsolescencia y de eliminación de la API de NVDA.

* Se han añadido convenciones sugeridas a la especificación del manifiesto de complemento.
Son opcionales para la compatibilidad con NVDA, pero se recomiendan o exigen para el envío a la tienda de complementos.
  * Utilizar `lowerCamelCase` para el campo de nombre.
  * Utilizar el formato `<major>.<minor>.<patch>` para el campo versión (requerido para el almacén de datos del complemento).
  * Utilizar `https://` como esquema para el campo url (requerido para el almacén de datos del complemento).
* Se añadió un nuevo tipo de punto de extensión llamado `Chain`, que puede utilizarse para iterar sobre iterables devueltos por manejadores registrados. (#14531)
* Se añadió el punto de extensión `bdDetect.scanForDevices`.
Los manejadores se pueden registrar para producir `BrailleDisplayDriver/DeviceMatch` pares que no encajan en categorías existentes, como USB o Bluetooth. (#14531)
* Se añadió el punto de extensión: `synthDriverHandler.synthChanged`. (#14618)
* El anillo de opciones del sintetizador ahora almacena en caché los valores de opciones disponibles la primera vez que se necesitan, en lugar de hacerlo al cargar el sintetizador. (#14704)
* Ahora se puede llamar al método de exportación de un mapa de gestos para exportarlo a un diccionario.
Este diccionario puede importarse en otro gesto pasándolo al constructor de `GlobalGestureMap` o al método update en un mapa existente. (#14582)
* `hwIo.base.IoBase` y sus derivados ahora tienen un nuevo parámetro constructor para tomar un `hwIo.ioThread.IoThread`.
Si no se proporciona, se utiliza el hilo predeterminado. (#14627)
* `hwIo.ioThread.IoThread` ahora tiene  un método `setWaitableTimer` para establecer un temporizador de espera utilizando una función python.
Del mismo modo, el nuevo método `getCompletionRoutine` te permite convertir un método python en una rutina de finalización de forma segura. (#14627)
* `offsets.OffsetsTextInfo._get_boundingRects` ahora debería devolver siempre `List[locationHelper.rectLTWH]` como se esperaba para una subclase de `textInfos.TextInfo`. (#12424)
* `highlight-color` ahora es un atributo de campo de formato. (#14610)
* NVDA debería de determinar con mayor precisión si un mensaje registrado proviene del núcleo de NVDA. (#14812)
* NVDA ya no registrará advertencias o errores inexactos sobre appModules obsoletos. (#14806)
* Todos los puntos de extensión de NVDA ahora se describen brevemente en un capítulo nuevo específico de la guía del desarrollador . (#14648)
* `scons checkpot` ya no comprobará más la subcarpeta `userConfig`. (#14820)
* Las cadenas traducibles ahora pueden definirse con una forma singular y una plural utilizando `ngettext` y `npgettext`. (#12445)

#### Obsolescencias

* Pasar funciones lambda a `hwIo.ioThread.IoThread.queueAsApc` está obsoleto.
En su lugar, las funciones deberían ser débilmente referenciables. (#14627)
* Importar `LPOVERLAPPED_COMPLETION_ROUTINE` desde `hwIo.base` está obsoleto.
En su lugar importa desde `hwIo.ioThread`. (#14627)
* `IoThread.autoDeleteApcReference` está obsoleta.
Se introdujo en NVDA 2023.1 y nunca se pretendió que formase parte de la API pública.
Hasta su eliminación, se comporta como un no-op, es decir, un gestor de contexto que no produce nada. (#14924)
* `gui.MainFrame.onAddonsManagerCommand` está obsoleto, utiliza `gui.MainFrame.onAddonStoreCommand` en su lugar. (#13985)
* `speechDictHandler.speechDictVars.speechDictsPath` está obsoleta, utiliza `NVDAState.WritePaths.speechDictsDir` en su lugar. (#15021)
* Importar `voiceDictsPath` y `voiceDictsBackupPath` desde `speechDictHandler.dictFormatUpgrade` está obsoleto.
En su lugar utiliza `WritePaths.voiceDictsDir` y `WritePaths.voiceDictsBackupDir` from `NVDAState`. (#15048)
* `config.CONFIG_IN_LOCAL_APPDATA_SUBKEY` está obsoleto.
En su lugar utiliza `config.RegistryKey.CONFIG_IN_LOCAL_APPDATA_SUBKEY`. (#15049)

## 2023.1

Se ha añadido una nueva orden "Estilo de Párrafo" en la "navegación de Documento".
Esto puede utilizarse con editores de texto que no admitan la navegación por párrafos nativamente, tales como el Bloc de Notas y Notepad++.

Hay una nueva orden global para anunciar el destino de un enlace, mapeada a `NVDA+k`.

El soporte para el contenido web anotado (como los comentarios y las notas al pie) ha sido mejorado.
Pulsa `NVDA+d` para recorrer los resúmenes cuando se anuncien las anotaciones (por ejemplo, "tiene comentario, tiene nota al pie").

Ahora se admiten las pantallas braille Tivomatic Caiku Albatross 46/80.

Se ha mejorado el soporte para versiones ARM64 y AMD64 de Windows.

Hay muchas correcciones de fallos, en particular correcciones de Windows 11.

se han actualizado eSpeak, LibLouis, Sonic rate boost y Unicode CLDR.
Hay nuevas tablas braille para Georgiano, Swahili (Kenya) y Chichewa (Malawi).

Nota:

* Esta versión rompe la compatibilidad con los complementos existentes.

### Nuevas Características

* Microsoft Excel a través de UI Automation: anunciado automático de encabezados de fila y columna en tablas. (#14228)
  * Nota: esto se refiere a tablas formateadas a través del botón "Tabla" en el panel Insertar de la Cinta.
  "Primera Columna" y "Cabecera de Fila" en "Opciones de Estilo de Tabla" se corresponden con encabezados de columna y fila respectivamente.
  * Esto no se refiere a los encabezados específicos del lector de pantalla a través de rangos denominados, lo cual actualmente no se admite a través de UI Automation.
* Se ha añadido un script no asignado para conmutar las descripciones retrasadas de caracteres. (#14267)
* Se añadió una opción experimental para aprovechar el soporte de notificaciones UIA en la Terminal de Windows para anunciar el texto nuevo o cambiado en la terminal, lo que mejora la estabilidad y la capacidad de respuesta. (#13781)
  * Consulta la Guía del Usuario para conocer las limitaciones de esta opción experimental.
* En Windows 11 ARM64, el modo exploración ahora está disponible en aplicaciones AMD64 tales como Firefox, Google Chrome y 1Password. (#14397)
* Se ha añadido una nueva opción, "Estilo de Párrafo" en "Navegación de Documento".
Esto añade el soporte para salto de una sola línea (normal) y salto de múltiples líneas (bloque) a la navegación de párrafos.
Esto puede utilizarse con editores de texto que no admitan la navegación por párrafos nativamente, tales como Notepad y Notepad++. (#13797)
* Ahora se  anuncia la presencia de varias anotaciones.
`nvda+d` ahora recorre el sumario de cada anotación anunciando el objetivo para los orígenes con varios objetivos de anotaciones.
Por ejemplo, cuando el texto tiene un comentario y una nota al pie asociada con ella. (#14507, #14480)
* Se añadió el soporte para las pantallas braille Tivomatic Caiku Albatross 46/80. (#13045)
* Nueva orden global: anunciar destino del enlace (`NVDA+k`).
Pulsándola una vez verbalizará y mostrará en braille el destino del enlace que esté en el navegador de objetos.
Pulsándola dos veces la mostrará en una ventana para una revisión más detallada. (#14583)
* Una nueva orden global no mapeada (Categoría Herramientas): anuncia el destino del enlace en una ventana.
Lo mismo que pulsar `NVDA+k` dos veces, pero puede ser más útil para usuarios de braille. (#14583)

### Cambios

* Se actualizó el transcriptor braille LibLouis a [3.24.0](https://github.com/liblouis/liblouis/releases/tag/v3.24.0). (#14436)
  * Actualizaciones grandes al braille úngaro, UEB y Chino bopomofo.
  * Soporte para el braille danés estándar 2022.
  * Nuebas tablas braille para braille georgiano literario, Swahili (Kenya) y Chichewa (Malawi).
* Se actualizó Sonic rate boost library a commit `1d70513`. (#14180)
* CLDR se ha actualizado a la versión 42.0. (#14273)
* eSpeak NG se ha actualizado a 1.52-dev commit `f520fecb`. (#14281, #14675)
  * Corregido el anunciado de números grandes. (#14241)
* Las aplicaciones Java con controles que utilicen el estado seleccionable ahora anunciarán cuando un elemento no esté seleccionado en lugar de cuando el elemento esté seleccionado. (#14336)

### Corrección de Fallos

* Correcciones de Windows 11:
  * NVDA anunciará los elementos resaltados de la búsqueda al abrir el menú Inicio. (#13841)
  * En ARM, las aplicaciones x64 ya no se identifican como aplicaciones ARM64. (#14403)
  * Se puede acceder a los elementos de menú del historial del portapapeles como "elemento anclado". (#14508)
  * En Windows 11 22H2 y más modernos, es posible de nuevo utilizar el ratón y la interactuación táctil para interactuar con áreas tales como la ventana de desbordamiento de la bandeja del sistema y el diálogo "Abrir Ccon". (#14538, #14539)
* Se anuncian las sugerencias al escribir una @mención en los comentarios en Microsoft Excel. (#13764)
* En la barra de ubicaciones de Google Chrome, los controles de sugerencias (cambiar a pestaña, eliminar sugerencia etc) ahora se anuncian cuando se seleccionen. (#13522)
* Al pedir información de formato, los colores ahora se anuncian explícitamente en Wordpad o en el Visualizador de Registro, en lugar de sólo "color predeterminado". (#13959)
* En Firefox, ahora funciona la activación del botón "Mostrar Opciones" en las páginas de incidencias de GitHub de forma fiable. (#14269)
* Los controles del selector de fecha en el cuadro de diálogo Búsqueda Avanzada de Outlook 2016 / 365 ahora anuncian su etiqueta y valor. (#12726)
* Los controles de conmutación ARIA ahora se anuncian realmente como conmutadores en Firefox, Chrome y Edge, en lugar de como casillas de verificación. (#11310)
* NVDA anunciará automáticamente el estado de ordenación en una cabecera de columna de tabla HTML cuando se cambie pulsando un botón interior. (#10890)
* El nombre de un punto de referencia o de una región siempre se verbaliza automáticamente al saltar al interior desde el exterior utilizando la navegación rápida o el foco en el modo exploración. (#13307)
* Cuando se habilita pitar o anunciar 'mayús' para letras mayúsculas con descripciones retrasadas de caracteres, NVDA ya no pita ni anuncia 'mayus' dos veces. (#14239)
* Los controles en tabla en aplicaciones Java ahora se anunciarán con más precisión en NVDA. (#14347)
* Algunas opciones ya no serán inesperadamente diferentes cuando se utilicen con varios perfiles. (#14170)
  * Se han abordado las siguientes opciones:
    * Sangría de línea en opciones de Formateado de Documento.
    * Bordes de celda en opciones de formateo de documento
    * Mostrar mensajes en opciones de braille
    * Seguimiento de Braille en opciones de braille
  * En algunos casos poco comunes, estas opciones utilizadas en perfiles pueden modificarse inesperadamente al instalar esta versión de NVDA.
  * Por favor, comprueba estas opciones en tus perfiles después de actualizar NVDA a esta versión.
* Los Emojis ahora deberían anunciarse en más idiomas. (#14433)
* La presencia de una anotación ya no falta en braille para algunos elementos. (#13815)
* Corregido un problema donde los cambios de configuración no se guardaban correctamente al cambiar entre una opción "Predeterminada" y el valor de la opción "predeterminada". (#14133)
* Al configurar NVDA siempre habrá al menos una tecla que se defina como tecla NVDA. (#14527)
* Al acceder al menú NVDA a través del área de notificaciones, NVDA ahora no sugerirá una actualización pendiente cuando no haya ya ninguna disponible. (#14523)
* El tiempo restante, transcurrido y total ahora se anuncia correctamente para ficheros de audio de más de un día en foobar2000. (#14127)
* En navegadores web como Chrome y Firefox, las alertas como descargas de ficheros se muestran en braille además de ser verbalizadas. (#14562)
* Corregido un fallo al navegar a la primera y última columna en una tabla en Firefox (#14554)
* Cuando NVDA se lance con el parámetro `--lang=Windows`, es posible de nuevo abrir el diálogo Opciones Generales de NVDA. (#14407)
* NVDA ya no falla en la lectura continua en Kindle para PC después de pasar la página. (#14390)

### Cambios para Desarrolladores

Nota: esta es una versión que rompe la compatibilidad con la API del complemento.
Los complementos tendrán que volver a probarse y actualizar su manifiesto.
Por favor consulta [la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para información sobre las obsolescencias en la API de NVDA y procesos borrados.

* Las pruebas de sistema ahora deberían pasar al ejecutarse localmente en sistemas no en inglés. (#13362)
* En Windows 11 en ARM, las aplicaciones x64 ya no se identifican como aplicaciones ARM64. (#14403)
* Ya no es necesario utilizar `SearchField` y `SuggestionListItem` `UIA` `NVDAObjects` en nuevos escenarios UI Automation, donde se anuncian automáticamente las sugerencias de búsqueda, y donde la escritura se ha espuesto a través de UI Automation con el patrón `controllerFor`.
Esta funcionalidad ahora está disponible genéricamente a través de `behaviours.EditableText` y la base `NVDAObject` respectivamente.
* La categoría UIA debug logging cuando está habilitada ahora produce un registro significativamente mayor para los eventos, manejadores y utilidades UIA. (#14256)
* Actualizados los estándares de compilación de NVDAHelper. (#13072)
  * Ahora utiliza los estándares C++20, eran C++17.
  * Ahora utiliza la bandera del compilador `/permissive-` que deshabilita comportamientos permisivos, y establece las opciones del compilador `/Zc` para una conformidad estricta.
* Algunos objetos de plugin (por ejemplo: controladores y complementos) ahora tienen una descripción más informativa en la consola python de NVDA. (#14463)
* NVDA ahora puede compilarse completamente con Visual Studio 2022, ya no se requiere de las herramientas de compilación de Visual Studio 2019.
* Registro más detallado de los bloqueos de NVDA para ayudar a la depuración. (#14309)
* Se ha substituido la clase singleton `braille._BgThread` por `hwIo.ioThread.IoThread`. (#14130)
  * Una única instancia `hwIo.bgThread` (en el núcleo de NVDA) de esta clase proporciona entrada/salida en segundo plano para hilos seguros de controladores de pantalla braille.
  * Esta nueva clase no es un singleton por diseño, se recomienda a los autores de complementos que utilicen su propia instancia cuando realicen entrada/salida hardware.
* La arquitectura del procesador del ordenador puede consultarse a partir del atributo `winVersion.WinVersion.processorArchitecture.` (#14439)
* Se han añadido nuevos puntos de extensión. (#14503)
  * `inputCore.decide_executeGesture`
  * `tones.decide_beep`
  * `nvwave.decide_playWaveFile`
  * `braille.pre_writeCells`
  * `braille.filter_displaySize`
  * `braille.decide_enabled`
  * `braille.displayChanged`
  * `braille.displaySizeChanged`
* Es posible ajustar useConfig a  False en las opciones soportadas para un controlador de sintetizador. (#14601)

#### Cambios de Ruptura de la API

Son cambios de última hora en la API.
Por favor abre una incidencia en GitHub si tu complemento tiene un problema con la actualización a la nueva API.

* Se ha alterado la especificación de configuración, se han eliminado o modificado claves:
  * En la sección `[documentFormatting]`: 14233)
    * `reportLineIndentation` almacena un valor entero (de 0 a 3) en lugar de un booleano
    * `reportLineIndentationWithTones` se ha eliminado.
    * `reportBorderStyle` y `reportBorderColor` se han eliminado y se han remplazado por `reportCellBorders`.
  * En la sección `[braille]`: (#14233):
    * `noMessageTimeout` se ha eliminado, remplazado por un valor para `showMessages`.
    * `messageTimeout` no puede tomar el valor 0 nunca más, se remplazó por un valor para `showMessages`.
    * `autoTether` se ha eliminado; `tetherTo` ahora puede tomar el valor "auto" en su lugar.
  * En la sección `[keyboard]` (#14528):
    * `useCapsLockAsNVDAModifierKey`, `useNumpadInsertAsNVDAModifierKey`, `useExtendedInsertAsNVDAModifierKey` se han eliminado.
    Se remplazaron por `NVDAModifierKeys`.
* La clase `NVDAHelper.RemoteLoader64` ha sido eliminada sin remplazo. (#14449)
* Las siguientes funciones en `winAPI.sessionTracking` se eliminaron sin remplazo. (#14416, #14490)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`
* Ya no es posible habilitar o deshabilitar el manejador braille con la opción `braille.handler.enabled`.
Para deshabilitar el manejador braille por programa, registra un manejador a `braille.handler.decide_enabled`. (#14503)
* Ya no es posible actualizar el tamaño de la pantalla del manejador configurando `braille.handler.displaySize`.
Para actualizar el tamaño de la pantalla por programa, registra un manejador a `braille.handler.filter_displaySize`.
Consulta `brailleViewer` para ver un ejemplo de cómo hacerlo. (#14503)
* Ha habido cambios en la utilización de `addonHandler.Addon.loadModule`. (#14481)
  * `loadModule` ahora espera el punto como un separador, en lugar de la barra inversa.
  Por ejemplo "lib.example" en lugar de "lib\example".
  * `loadModule` ahora lanza una excepción cuando un módulo no se pueda cargar  o tenga errores, en lugar de devolver silenciosamente `None` sin dar información sobre la causa.
* Los siguientes símbolos se han eliminado de `appModules.foobar2000` sin un remplazo directo. (#14570)
  * `statusBarTimes`
  * `parseIntervalToTimestamp`
  * `getOutputFormat`
  * `getParsingFormat`
* Los siguientes ya no son singletons - su método get ha sido eliminado.
El uso de `Example.get()` ahora es `Example()`. (#14248)
  * `UIAHandler.customAnnotations.CustomAnnotationTypesCommon`
  * `UIAHandler.customProps.CustomPropertiesCommon`
  * `NVDAObjects.UIA.excel.ExcelCustomProperties`
  * `NVDAObjects.UIA.excel.ExcelCustomAnnotationTypes`

#### Obsolescencias

* `NVDAObjects.UIA.winConsoleUIA.WinTerminalUIA` está obsoleto y se desaconseja su uso. (#14047)
* `config.addConfigDirsToPythonPackagePath` se ha movido.
Utiliza `addonHandler.packaging.addDirsToPythonPackagePath` en su lugar. (#14350)
* `braille.BrailleHandler.TETHER_*` está obsoleto.
Utiliza `configFlags.TetherTo.*.value` en su lugar. (#14233)
* `utils.security.postSessionLockStateChanged` está obsoleta.
Utiliza `utils.security.post_sessionLockStateChanged` en su lugar. (#14486)
* `NVDAObject.hasDetails`, `NVDAObject.detailsSummary`, `NVDAObject.detailsRole` están obsoletos.
Utiliza `NVDAObject.annotations` en su lugar. (#14507)
* `keyboardHandler.SUPPORTED_NVDA_MODIFIER_KEYS` está obsoleta sin ningún remplazo directo.
Considera utilizar la clase `config.configFlags.NVDAKey` en su lugar. (#14528)
* `gui.MainFrame.evaluateUpdatePendingUpdateMenuItemCommand` ha quedado obsoleto.
Utiliza `gui.MainFrame.SysTrayIcon.evaluateUpdatePendingUpdateMenuItemCommand` en su lugar. (#14523)

## 2022.4

Esta versión incluye varias teclas de órdenes nuevas, incluyendo órdenes para leer toda la tabla.
Se ha añadido una sección "Guía de Inicio Rápido" a la Guía del Usuario.
También hay varias correcciones de fallos.

se han actualizado eSpeak y LibLouis.
Hay nuevas tablas braille para Chino, sueco, Luganda y Kinyarwanda.

### Nuevas Características

* Se añadió una sección "Guía de Inicio rápido" a la Guía del Usuario. (#13934)
* Se introdujo una nueva orden para buscar el atajo de teclado del foco actual. (#13960)
  * Escritorio: `shift+2 del teclado numérico`.
  * Portátil: `NVDA+ctrl+shift+.`.
* Se introdujeron nuevas órdenes para mover el cursor de revisión por páginas donde se admita por la aplicación. (#14021)
  * Mover a la página anterior:
    * Escritorio: `NVDA+rePág`.
    * Portátil: `NVDA+shift+rePág`.
  * Mover a la página siguiente:
    * Escritorio: `NVDA+avPág`.
    * Portátil: `NVDA+shift+avPág`.
* Se añadieron las siguientes órdenes de tabla. (#14070)
  * Verbalizar todo en la columna: `NVDA+control+alt+flechaAbajo`
  * Verbalizar todo en la fila: `NVDA+control+alt+flechaDerecha`
  * Leer toda la columna:  `NVDA+control+alt+flechaArriba`
  * Leer toda la fila: `NVDA+control+alt+FlechaIzquierda`
* Microsoft Excel a través de UI Automation: NVDA ahora anuncia cuando se salga de una tabla dentro de una hoja de cálculo. (#14165)
* Anunciar cabeceras de tabla ahora puede configurarse separadamente por filas y columnas. (#14075)

### Cambios

* eSpeak NG se ha actualizado a 1.52-dev commit `735ecdb8`. (#14060, #14079, #14118, #14203)
  * Corregido el anunciado de caracteres latinos al utilizar Mandarín. (#12952, #13572, #14197)
* Se actualizó el transcriptor braille LibLouis a [3.23.0](https://github.com/liblouis/liblouis/releases/tag/v3.23.0). (#14112)
  * Se añadieron tablas braille:
    * Braille común chino (caracteres de chino simplificado)
    * Braille literario Kinyarwanda
    * Braille literario Luganda
    * Braille sueco sin contracción
    * Braille sueco parcialmente contraído
    * Braille sueco contraído
    * Chino (China, Mandarín) Sistema braille actual (sin tonos) (#14138)
* NVDA ahora incluye la arquitectura del sistema operativo como parte del seguimiento de estadísticas de usuario. (#14019)

### Corrección de Fallos

* Al actualizar NVDA utilizando el Windows Package Manager CLI (aka winget), una versión liberada de NVDA ya no se trata siempre como una versión más moderna que cualquier versión alfa que esté instalada. (#12469)
* NVDA ahora anunciará correctamente cuadros de grupo en aplicaciones Java. (#13962)
* El cursor del sistema sigue apropiadamente el texto hablado durante "verbalizar todo" en aplicaciones tales como Bookworm, WordPad, o el visualizador del registro de NVDA. (#13420, #9179)
* En programas que utilicen UI Automation, las casillas de verificación parcialmente marcadas se anunciarán correctamente. (#13975)
* Mejorado el rendimiento y la estabilidad en Microsoft Visual Studio, Windows Terminal y otras aplicaciones basadas en UI Automation. (#11077, #11209)
  * Estas correcciones se aplican a Windows 11 Sun Valley 2 (versión 22H2) y posteriores.
  * El registro selectivo para eventos UI Automation y cambios de propiedad ahora se habilita por omisión.
* El anunciado de texto, la salida Braille y la supresión de contraseñas ahora funcionan como se esperaba en el control integrado de la Terminal de Windows en Visual Studio 2022. (#14194)
* NVDA ahora es consciente de los DPI cuando se utilicen varios monitores.
Hay varias correcciones para utilizar una configuración de DPI superior a 100% o varios monitores.
Todavía pueden seguir existiendo problemas con versiones de Windows más antiguas que Windows 10 1809.
Para que funcionen estas correcciones, las aplicaciones con las que interactúe NVDA también tienen que ser conscientes de DPI.
Ten en cuenta que todavía hay fallos conocidos con Chrome y Edge. (#13254)
  * Los marcos de resaltado visual ahora deberían colocarse correctamente en la mayoría de las aplicaciones. (#13370, #3875, #12070)
  * La interacción con la pantalla táctil ahora debería ser precisa para la mayoría de las aplicaciones. (#7083)
  * El seguimiento del ratón ahora debería funcionar para la mayoría de las aplicaciones. (#6722)
* Los cambios del estado de la orientación (apaisado o vertical) ahora se ignoran correctamente cuando no hay cambio (ej. cambios del monitor). (#14035)
* NVDA anunciará elementos arrastrables en la pantalla en lugares tales como en la reorganización de los mosaicos del menú Inicio en Windows 10 y en los escritorios virtuales en Windows 11. (#12271, #14081)
* En las opciones avanzadas, la opción "reproducir un sonido para registro de errores" ahora se restaura correctamente a este valor predeterminado al pulsar el botón "Restaurar predeterminados". (#14149)
* NVDA ahora puede seleccionar texto utilizando el atajo de teclado `NVDA+f10` en aplicaciones Java. (#14163)
* NVDA ya no se atascará en un menú al subir y bajar con las flechas por un hilo de conversaciones en Microsoft Teams. (#14355)

### Cambios para Desarrolladores

Por favor consulta [la guía del desarrollador](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) para obtener información sobre la obsolescencia de la API de NVDA y el proceso de eliminación.

* Se creó la [lista de correo de Anuncios de la API de NVDA](https://groups.google.com/a/nvaccess.org/g/nvda-api/about). (#13999)
* NVDA ya no procesa eventos `textChange` para la mayoría de las aplicaciones UI Automation debido al impacto de su extremo rendimiento negativo. (#11002, #14067)

#### Obsolescencias

* `core.post_windowMessageReceipt` está obsoleto, utiliza `winAPI.messageWindow.pre_handleWindowMessage` en su lugar.
* `winKernel.SYSTEM_POWER_STATUS` está obsoleto y se desaconseja su uso, esto se ha movido a `winAPI._powerTracking.SystemPowerStatus`.
* Las constantes `winUser.SM_*` están obsoletas, utiliza `winAPI.winUser.constants.SystemMetrics` en su lugar.

## 2022.3.3

Esta es una versión menor para corregir problemas con 2022.3.2, 2022.3.1 y 2022.3.
Esto también aborda un problema de seguridad.

### Correcciones de Seguridad

* Evita un posible acceso al sistema (por ejemplo: en la consola Python de NVDA) para usuarios no autenticados.
([GHSA-fpwc-2gxx-j9v7](https://github.com/nvaccess/nvda/security/advisories/GHSA-fpwc-2gxx-j9v7))

### Corrección de Fallos

* Corregido un fallo en el que si NVDA se congela cuando se bloquea, NVDA permitirá acceder a los usuarios de escritorio mientras se esté en la pantalla de bloqueo de Windows. (#14416)
* Corregido un fallo en el que si NVDA se congela cuando se bloquea, NVDA no se comportará correctamente, como si el dispositivo siguiera aún bloqueado. (#14416)
* Corregidos problemas de accesibilidad con el proceso de Windows "olvidé mi PIN" y con la experiencia de actualizar o instalar Windows. (#14368)
* Corregido un fallo al intentar instalar NVDA en algunos ambientes de Windows, por ejemplo en Windows Server. (#14379)

### Cambios para Desarrolladores

#### Obsolescencias

* `utils.security.isObjectAboveLockScreen(obj)` está obsoleto, en su lugar utiliza `obj.isBelowLockScreen`. (#14416)
* Las siguientes funciones en `winAPI.sessionTracking` están obsoletas para su eliminación en 2023.1. (#14416)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`

## 2022.3.2

Esta es una versión menor para corregir regresiones con 2022.3.1 y para abordar un problema de seguridad.

### Correcciones de Seguridad

* Evita el posible acceso a nivel de sistema para usuarios no autentificados.
([GHSA-3jj9-295f-h69w](https://github.com/nvaccess/nvda/security/advisories/GHSA-3jj9-295f-h69w))

### Corrección de Fallos

* Se corrige una regresión de 2022.3.1 donde ciertas funcionalidades se deshabilitaban en pantallas seguras. (#14286)
* Se corrige una regresión de 2022.3.1 donde ciertas funcionalidades se deshabilitaban después de autentificarse si NVDA se iniciaba en la pantalla de bloqueo. (#14301)

## 2022.3.1

Esta es una versión menor para corregir varios problemas de seguridad.
Por favor comunica responsablemente los problemas de seguridad a <info@nvaccess.org>.

### Correcciones de Seguridad

* Se ha corregido el exploit por el que era posible elevar al usuario los privilegios de sistema.
([GHSA-q7c2-pgqm-vvw5](https://github.com/nvaccess/nvda/security/advisories/GHSA-q7c2-pgqm-vvw5))
* Se ha corregido un problema de seguridad que permitía el acceso a la consola de python en la pantalla de bloqueo a través de una condición race para el arranque de NVDA.
([GHSA-72mj-mqhj-qh4w](https://github.com/nvaccess/nvda/security/advisories/GHSA-72mj-mqhj-qh4w))
* Se ha corregido un problema por el que el texto del visualizador de voz se almacenaba en caché al bloquear Windows.
([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

### Corrección de Fallos

* Se evita que un usuario no autentificado actualice las opciones para los visualizadores de voz y Braille en la pantalla de bloqueo. ([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

## 2022.3

La comunidad de desarrolladores de NVDA ha contribuido en gran medida a esta versión.
Esto incluye el retraso de las descripciones de los caracteres y la mejora del soporte de la Consola de Windows.

Esta versión también incluye varias correcciones de fallos.
En particular, las versiones actualizadas de Adobe Acrobat/Reader ya no se bloquean al leer un documento PDF.

eSpeak se ha actualizado, lo cual introduce tres idiomas nuevos: Bielorruso, Luxemburgués y Totontepec Mixe.

### Nuevas Características

* En la Consola de Windows se utiliza Host por el Símbolo del Sistema, por PowerShell y por el subsistema de Windows para Linux en Windows 11 versión 22H2 (Sun Valley 2) y posterior:
  * Rendimiento y estabilidad muy mejorados. (#10964)
  * Al pulsar `control+f` para buscar texto, la posición del cursor de revisión se actualiza para seguir al término encontrado. (#11172)
  * El anunciado del texto escrito que no aparezca en la pantalla (tal como las contraseñas) se deshabilita predeterminadamente.
Puede volver a habilitarse en el panel Avanzado de los ajustes de NVDA. (#11554)
  * El texto que se haya desplazado fuera de la pantalla se puede revisar sin desplazar la ventana de la consola. (#12669)
  * Está disponible más información detallada de formato de texto. ([microsoft/terminal PR 10336](https://github.com/microsoft/terminal/pull/10336))
* Se ha añadido una nueva opción de Voz para leer las descripciones de caracteres tras un retraso. (#13509)
* Se ha añadido una nueva opción de Braille para determinar si el desplazamiento hacia adelante o hacia atrás de la pantalla debería interrumpir la voz. (#2124)

### Cambios

* eSpeak NG se ha actualizado a 1.52-dev commit `9de65fcb`. (#13295)
  * Idiomas añadidos:
    * Bielorruso
    * Luxemburgués
    * Totontepec Mixe
* Al utilizar UI Automation para acceder a controles de hoja de cálculo de Microsoft Excel, NVDA ahora puede anunciar cuando una celda está fusionada. (#12843)
* En lugar de anunciar "tiene detalles" se incluye el propósito de los detalles cuando sea posible, por ejemplo "tiene comentarios". (#13649)
* El tamaño de instalación de NVDA ahora se muestra en la sección Programas y Características de Windows. (#13909)

### Corrección de Fallos

* Adobe Acrobat / Reader de 64 bits ya no se bloqueará al leer un documento PDF. (#12920)
  * Ten en cuenta que es necesaria también la versión más actualizada de Adobe Acrobat / Reader para evitar el bloqueo.
* Las medidas de tamaño de fuente ahora son traducibles en NVDA. (#13573)
* Se ignoran los eventos de Java Access Bridge en los que no se pueda encontrar un manejador de ventana para las aplicaciones Java.
Esto mejorará el rendimiento para algunas aplicaciones Java incluyendo IntelliJ IDEA. (#13039)
* El anunciado de celdas seleccionadas para LibreOffice Calc es más eficaz y ya no da lugar a la congelación de Calc cuando se seleccionen muchas celdas. (#13232)
* Cuando se ejecute en un usuario diferente, Microsoft Edge ya no es inaccesible. (#13032)
* Cuando el aumento brusco de velocidad esté desactivado, la velocidad de eSpeak no desciende más entre velocidades del 99% y 100%. (#13876)
* Se ha corregido un fallo que permitía que se abrieran 2 diálogos de Gestos de Entrada. (#13854)

### Cambios para Desarrolladores

* Actualizado Comtypes a la versión 1.1.11. (#12953)
* En compilaciones de la Consola de Windows (`conhost.exe`) con un nivel 2 de la API de NVDA (`FORMATTED`) o más grandes, tal como aquellos incluídos con Windows 11 versión 22H2 (Sun Valley 2), UI Automation ahora se utiliza por defecto. (#10964)
  * Esto se puede anular cambiando la opción "Soporte de la Consola de Windows" en el panel Avanzado de la configuración de NVDA.
  * Para encontrar tu nivel de API de NVDA para la Consola de Windows, configura "Soporte de Consola de Windows" a "UIA cuando esté disponible", entonces verifica que el registro esté abierto con NVDA+F1 desde una instancia de Consola de Windows en ejecución.
* El Búfer virtual de Chromium ahora se carga incluso cuando el objeto documento tenga el MSAA `STATE_SYSTEM_BUSY` expuesto a través de IA2. (#13306)
* Se ha creado un tipo específico de configuración `featureFlag` para utilizar con características experimentales en NVDA. Consulta `devDocs/featureFlag.md` para más información. (#13859)

#### Obsolescencias

No se proponen obsolescencias en 2022.3.

## 2022.2.4

Este es un parche liberado para corregir un fallo de seguridad.

### Corrección de Fallos

* Se ha corregido un fallo por el que era posible abrir la consola python de NVDA a través del visualizador del registro en la pantalla de bloqueo.
([GHSA-585m-rpvv-93qg](https://github.com/nvaccess/nvda/security/advisories/GHSA-585m-rpvv-93qg))

## 2022.2.3

Este es un parche liberado para corregir una ruptura accidental de la API introducida en 2022.2.1.

### Corrección de Fallos

* Corregido un fallo donde NVDA no anunciaba "Escritorio Seguro" al entrar en un escritorio seguro.
Esto provocaba que NVDA remote no reconociera los escritorios seguros. (#14094)

## 2022.2.2

Este es un parche liberado para corregir un fallo introducido en 2022.2.1 con los gestos de entrada.

### Corrección de Fallos

* Corregido un fallo donde los gestos de entrada no siempre funcionaban. (#14065)

## 2022.2.1

Esta es una versión menor para corregir un problema de seguridad.
Por favor, comunica responsablemente los fallos de seguridad a <info@nvaccess.org>.

### Correcciones de Seguridad

* Se ha corregido un fallo por el que era posible ejecutar una consola python desde la pantalla de bloqueo. (GHSA-rmq3-vvhq-gp32)
* Se ha corregido el fallo por el que era posible escapar de la pantalla de bloqueo utilizando la navegación de objetos. (GHSA-rmq3-vvhq-gp32)

### Cambios para desarrolladores

#### Obsolescencias

Estas obsolescencias no se han programado actualmente para su eliminación.
Los alias obsoletos permanecerán hasta nuevo aviso.
Por favor, prueba la nueva API y proporciona retroalimentación.
Para autores de complementos, por favor abrid una incidencia en GitHub si estos cambios impiden que la API satisfaga vuestras necesidades.

* `appModules.lockapp.LockAppObject` debería reemplazarse con `NVDAObjects.lockscreen.LockScreenObject`. (GHSA-rmq3-vvhq-gp32)
* `appModules.lockapp.AppModule.SAFE_SCRIPTS` debería reemplazarse con `utils.security.getSafeScripts()`. (GHSA-rmq3-vvhq-gp32)

## 2022.2

Esta versión incluye muchas correcciones de fallos.
En particular, hay mejoras significativas para aplicaciones basadas en Java, para pantallas braille y para características de Windows.

Se han introducido nuevas órdenes de navegación de tablas.
Se ha actualizado Unicode CLDR.
Se ha actualizado LibLouis, lo que incluye una tabla braille alemana nueva .

### Nuevas Características

* Soporte para interactuar con Microsoft Loop Components en productos de Microsoft Office. (#13617)
* Se han añadido nuevas órdenes de navegación por tablas. (#957)
 * `control+alt+inicio/fin` para saltar a la primera/última columna.
 * `control+alt+repág/avpág` para saltar a la primera/última fila.
* Se ha añadido un script sin asignar para moverse circularmente entre cambio de modos de idioma y de dialecto. (#10253)

### Cambios

* NSIS se ha actualizado a la versión 3.08. (#9134)
* CLDR se ha actualizado a la versión 41.0. (#13582)
* Actualizado el transcriptor braille libLouis a [3.22.0](https://github.com/liblouis/liblouis/releases/tag/v3.22.0). (#13775)
  * Nueva tabla braille: alemán grado 2 (detallada)
* Se añadió un nuevo rol para controles "indicador ocupado". (#10644)
* NVDA ahora anuncia cuando no se pueda realizar una acción. (#13500)
  * Esto incluye cuando:
    * Se utilice la versión de NVDA de la Tienda de Windows.
    * En un contexto seguro.
    * Esperando por la respuesta de un diálogo modal.

### Corrección de Fallos

* Correcciones para aplicaciones basadas en Java:
  * NVDA ahora anunciará el estado de sólo lectura. (#13692)
  * NVDA ahora anunciará los estados deshabilitado/habilitado correctamente. (#10993)
  * NVDA ahora anunciará los atajos de teclas de función. (#13643)
  * NVDA ahora puede pitar o hablar en barras de progreso. (#13594)
  * NVDA ya no eliminará incorrectamente texto de los widgets cuando se presenten al usuario. (#13102)
  * NVDA ahora anunciará el estado de los botones conmutables. (#9728)
  * NVDA ahora identificará la ventana en una aplicación Java con varias ventanas. (#9184)
  * NVDA ahora anunciará información de la posición para controles de pestaña. (#13744)
* Correcciones de braille:
  * Corregida la salida braille al navegar por cierto texto en conroles de edición enriquecidos de Mozilla, como redactar un mensaje en Thunderbird. (#12542)
  * Cuando se sigue al braille automáticamente y el ratón se mueve con el seguimiento del ratón habilitado,
   las órdenes de revisión de texto ahora actualizan la pantalla braille con el contenido verbalizado. (#11519)
  * Ahora es posible desplazar la pantalla braille por el contenido al utilizar las órdenes de revisión de texto. (#8682)
* El instalador de NVDA ahora puede ejecutarse desde directorios con caracteres especiales. (#13270)
* En Firefox, NVDA ya no falla al anunciar elementos en páginas web donde los atributos aria-rowindex, aria-colindex, aria-rowcount o aria-colcount sean inválidos. (#13405)
* El cursor ya no cambia de fila o de columna al utilizar la navegación de tablas para navegar por las celdas fusionadas. (#7278)
* Al leer PDFs no interactivos en Adobe Reader, el tipo y estado de los campos de formulario (tales como  casillas de verificación y botones de opción) ahora se anuncian. (#13285)
* "Reiniciar la configuración a los valores predeterminados de fábrica" ahora es accesible en el menú de NVDA durante el modo seguro. (#13547)
* Cualquier tecla de ratón bloqueada se desbloqueará cuando se salga de NVDA, anteriormente el botón del ratón permanecía bloqueado. (#13410)
* Visual Studio ahora anuncia los números de línea. (#13604)
  * Ten en cuenta que para que funcione el anunciado de números de línea, debe estar habilitado el mostrado de números de línea en Visual Studio y en NVDA.
* Visual Studio ahora anuncia correctamente la sangría de líneas. (#13574)
* NVDA anunciará de nuevo una vez los detalles de los resultados de la búsqueda del menú Inicio en versiones recientes de Windows 10 y 11. (#13544)
* En la versión 10.1908 y superior de la calculadora en Windows 10 y 11,
NVDA anunciará resultados cuando se pulsen más órdenes, tales como órdenes del modo científico. (#13386)
* En Windows 11, es posible de nuevo navegar e interactuar con elementos de la interfaz de usuario,
tales como Barra de tareas y visualizador de Tareas utilizando interacción de ratón y táctil. (#13508)
* NVDA anunciará el contenido de la barra de estado en Notepad en Windows 11. (#13386)
* El resaltado del navegador de objetos ahora aparece inmediatamente tras la activación de la característica. (#13641)
* Se corrige la lectura de los elementos de la vista de lista de una sola columna. (#13659, #13735)
* Se corrige el cambio automático de idioma de eSpeak para inglés y francés volviendo a ser inglés británico y francés (Francia). (#13727)
* Se corrige el cambio automático de idioma de OneCore cuando se intenta cambiar a un idioma ya instalado. (#13732)

### Cambios para Desarrolladores

* Ahora se admite compilar las dependencias de NVDA con Visual Studio 2022 (17.0).
Todavía se utiliza Visual Studio 2019 para compilaciones de desarrollo y de lanzamiento. (#13033)
* Cuando se recupera la cuenta de los hijos seleccionados a través de accSelection,
el caso si un ID de hijo negativo o si devuelve un IDispatch por `IAccessible::get_accSelection` ahora se maneja apropiadamente. (#13276)
* Nuevas funciones convenientes `registerExecutableWithAppModule` y `unregisterExecutable` se añadieron al módulo `appModuleHandler`.
Pueden utilizarse para usar un solo App Module con varios ejecutables. (#13366)

#### Obsolescencias

Estos son los cambios propuestos que rompen la API.
La parte obsoleta de la API continuará estando disponible hasta la versión especificada.
Si no se especifica una versión, el plan para la eliminación no ha sido determinado.
Nota, la hoja de ruta para la eliminación es 'un esfuerzo muy grande' y puede estar sujeta a cambios.
Por favor prueba la nueva API y proporciona retroalimentación.
Para autores de complementos, por favor abre un comentario de GitHub si estos cambios hacen que la API no cumpla tus necesidades.

* Se puso como obsoleto `appModuleHandler.NVDAProcessID` - utiliza `globalVars.appPid` en su lugar. (#13646)
* `gui.quit` ha sido puesto como obsoleto. Utiliza `wx.CallAfter(mainFrame.onExitCommand, None)` directamente en su lugar.
  -
* Algunos alias appModules se marcan como obsoletos.
El código que se importe desde uno de ellos, debería importarse desde el módulo reemplazado en su lugar.  (#13366)

| Nombre del módulo eliminado |Módulo de reemplazo|
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

Esta versión incluye grandes mejoras para el soporte UIA con MS Office.
Para Microsoft Office 16.0.15000 y superiores en Windows 11, NVDA utilizará UI Automation para acceder a documentos de Microsoft Word por defecto.
Esto proporciona una mejora de rendimiento significativa sobre el antiguo modelo de acceso de objetos.

Hay mejoras para los controladores de pantalla braille incluyendo Seika Notetaker, Papenmeier e HID Braille.
También hay varias correcciones de errores para Windows 11, para aplicaciones tales como la Calculadora, la Consola, la Terminal, Mail y el Panel de Emoji.

se han actualizado eSpeak-NG y LibLouis, se añadieron nuevas tablas Japonesa, Alemana y Catalana.

Nota:

 * Esta versión rompe la compatibilidad con los complementos existentes.

### Nuevas Características

* Soporte para el anunciado de notas en MS Excel con UI Automation habilitado en Windows 11. (#12861)
* En compilaciones recientes de Microsoft Word a través de UI Automation en Windows 11, la existencia de marcas, borradores de comentarios y comentarios resueltos ahora se anuncia en voz y en braille. (#12861)
* El nuevo parámetro de línea de órdenes `--lang` siempre sobrescribe el idioma configurado de NVDA. (#10044)
* NVDA ahora advierte sobre los parámetros de línea de órdenes que son desconocidos y que no se utilizan por ningún complemento. (#12795)
* En Microsoft Word accedido a través de UI Automation, NVDA ahora hará uso de mathPlayer para leer y navegar las ecuaciones matemáticas de Office. (#12946)
  * Para que esto funcione, debes estar ejecutando Microsoft Word 365/2016 compilación 14326 o posterior.
  * Las ecuaciones MathType también deben convertirse manualmente a Office Math seleccionando cada una y eligiendo Opciones de Ecuación -> Convertir a Office Math en el menú de contexto.
* Se ha actualizado el anunciado de "tiene detalles" y la orden asociada para resumir la relación de detalles para que funcionen en modo foco. (#13106)
* La Seika Notetaker ahora puede autodetectarse al conectarla a través de USB y de Bluetooth. (#13191, #13142)
  * Esto afecta a los siguientes dispositivos: MiniSeika (16, 24 celdas), V6 y V6Pro (40 celdas)
  * La selección manual del puerto bluetooth COM también se admite ahora.
* Añadida una orden para conmutar el Visualizador de braille; no hay un gesto predeterminado asociado. (#13258)
* Añadidas órdenes para conmutar varios modificadores simultáneamente con una pantalla braille (#13152)
* El diálogo diccionarios del habla ahora implementa un botón "Eliminar todo" para ayudar a borrar  un diccionario entero. (#11802)
* Añadido el soporte para la Calculadora de Windows 11. (#13212)
* En Microsoft Word con UI Automation habilitado en Windows 11,  ahora pueden anunciarse los números de línea y de sección.  (#13283, #13515)
* Para Microsoft Office 16.0.15000 y superiores en Windows 11, NVDA utilizará UI Automation para acceder a documentos de Microsoft Word por defecto, proporcionando una significativa mejora de rendimiento sobre el acceso al antiguo modelo de objetos. (#13437)
 * Esto incluye documentos en el propio Microsoft Word y también en el lector y redactor de mensajes en Microsoft Outlook.

### Cambios

* Espeak-ng se ha actualizado a 1.51-dev commit `7e5457f91e10`. (#12950)
* Actualizado el transcriptor braille liblouis a [3.21.0](https://github.com/liblouis/liblouis/releases/tag/v3.21.0). (#13141, #13438)
  * Añadida nueva tabla braille: braille literario Japonés (Kantenji)
  * Añadida nueva tabla alemana braille computerizado de 6 puntos.
  * Añadida tabla braille catalana grado 1. (#13408)
* NVDA anunciará la selección y la fusión de celdas en LibreOffice Calc 7.3 y posterior. (#9310, #6897)
* Actualizado el Unicode Common Locale Data Repository (CLDR) a 40.0. (#12999)
* `NVDA+Suprimir del teclado numérico` anuncia la localización del cursor o del objeto enfocado por defecto. (#13060)
* `NVDA+Shift+Suprimir del teclado numérico` anuncia la localización del cursor de revisión. (#13060)
* Añadidos bindings predeterminados para conmutar las teclas modificadoras a las pantallas  braille de Freedom Scientific (#13152)
* Ya no se anuncia "Baseline" a través de la orden anunciar formato de texto (`NVDA+F`). (#11815)
* Activar descripción larga ya no tiene un gesto predeterminado asignado. (#13380)
* Anunciar resumen de detalles ahora tiene un gesto predeterminado, `NVDA+d`. (#13380)
* NVDA necesita reiniciarse después de instalar MathPlayer. (#13486)

### Corrección de Fallos

* El panel del gestor del portapapeles ya no debería secuestrar incorrectamente el foco al abrir algunos programas de Office. (#12736)
* En un sistema donde el usuario haya elegido cambiar el botón primario del ratón de la izquierda a la derecha, NVDA ya no desplegará accidentalmente un menú de contexto en lugar de activar un elemento, en aplicaciones tales como navegadores web. (#12642)
* Al mover el cursor de revisión más allá del fin de los controles de texto, como en Microsoft Word con UI Automation, "inferior" se anuncia correctamente en más situaciones. (#12808)
* NVDA puede anunciar el nombre de la aplicación y la versión para los binarios colocados en system32 cuando se ejecuten en una versión de 64 bits de Windows. (#12943)
* Se ha mejorado la consistencia de la lectura de la salida de los programas de terminal. (#12974)
  * Ten en cuenta que en algunas situaciones, al insertar o eliminar caracteres en el medio de una línea, los caracteres después del cursor pueden ser leídos de nuevo.
* MS word con UIA: la navegación rápida por encabezados en modo exploración ya no se queda atascada en el encabezado final de un documento, ni este encabezado se muestra dos veces en la lista de elementos de NVDA. (#9540)
* En Windows 8 y posterior, la barra de estado del Explorador de Archivos ahora se puede recuperar utilizando el gesto estándar NVDA+fin (escritorio) / NVDA+shift+fin (portátil). (#12845)
* Los mensajes entrantes en el chat de Skype for Business se anuncian de nuevo. (#9295)
* NVDA puede volver a atenuar el audio al utilizar el sintetizador SAPI5 en Windows 11. (#12913)
* En la Calculadora de Windows 10, NVDA anunciará las etiquetas de la lista de elementos del historial y de la memoria. (#11858)
* Los gestos tales como el desplazamiento y enrutamiento vuelven a funcionar con los dispositivos HID Braille. (#13228)
* Windows 11 Mail: después de cambiar el foco entre aplicaciones, mientras se leía un correo electrónico largo, NVDA se quedaba atascado en una línea del correo. (#13050)
* HID braille: los gestos cor (por ejemplo: `espacio+punto4`) se pueden realizar con éxito desde la pantalla braille. (#13326)
* Corregido un fallo por el que se podían abrir varios diálogos de opciones al mismo tiempo. (#12818)
* Corregido un problema por el que algunas pantallas braille Focus Blue dejaban de funcionar después de que se despertase el ordenador tras la suspensión. (#9830)
* Ya no se anuncia 'Baseline' cuando la opción 'anunciar superíndice y subíndice' esté activa. (#11078)
* En Windows 11, NVDA ya no impedirá la navegación en el panel de emoji al seleccionar emojis. (#13104)
* Se evita un error que causaba un doble anunciado al utilizar la consola de Windows y la Terminal. (#13261)
* Corregidos varios casos en los que los elementos de la lista no se podían anunciar en aplicaciones de 64 bits, tales como REAPER. (#8175)
* En el gestor de descargas de Microsoft Edge, NVDA ahora cambiará automáticamente a modo Foco una vez el elemento de lista con la descarga más reciente obtenga el foco. (#13221)
* NVDA ya no provoca que las versiones de 64 bits de Notepad++ 8.3 y superiores se cuelguen. (#13311)
* Adobe Reader ya no se cuelga al arrancar si el modo protegido de Adobe Reader está habilitado. (#11568)
* Corregido un fallo donde al seleccionar el controlador de la pantalla braille Papenmeier provocaba que NVDA se colgase. (#13348)
* En Microsoft word con UIA: el número de página y otros formatos ya no se anuncian inapropiadamente al moverse desde una celda de tabla en blanco a una celda con contenido, o desde el final del documento a un contenido existente. (#13458, #13459)
* NVDA ya no falla al anunciar el título de página y al comenzar la lectura automática cuando se cargue una página en Google chrome 100. (#13571)
* NVDA ya no se bloquea al reiniciar la configuración de NVDA a los valores predeterminados de fábrica mientras verbalizar teclas de órdenes esté activado. (#13634)

### Cambios para Desarrolladores

* Nota: esta es una versión que rompe la compatibilidad con la API de los complementos. Los complementos tendrán que volver a probarse y actualizar su manifiesto.
* Aunque NVDA sigue requiriendo Visual Studio 2019, las compilaciones ya no deberían fallar si se instala una versión más reciente de Visual Studio (por ejemplo, 2022) junto con 2019. (#13033, #13387)
* Actualizado SCons a la versión 4.3.0. (#13033)
* Actualizado py2exe a la versión 0.11.0.1.0 (#13510)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` se ha eliminado. Utiliza `apiLevel` en su lugar. (#12955, #12660)
* `TVItemStruct` se ha eliminado de `sysTreeView32`. (#12935)
* `MessageItem` se ha eliminado del appModule Outlook. (#12935)
* Las constantes `audioDucking.AUDIODUCKINGMODE_*` ahora son una `DisplayStringIntEnum`. (#12926)
  * su uso debería substituirse con `AudioDuckingMode.*`
  * el uso de `audioDucking.audioDuckingModes` debería reemplazarse con `AudioDuckingMode.*.displayString`
* El uso de las constantes `audioDucking.ANRUS_ducking_*` debería reemplazarse con `ANRUSDucking.*`. (#12926)
* Cambios en `synthDrivers.sapi5` (#12927):
  * el uso de `SPAS_*` debería reemplazarse con `SPAudioState.*`
  * el uso de `constants.SVSF*` debería reemplazarse con `SpeechVoiceSpeakFlags.*`
    * Nota: `SVSFlagsAsync` debería reemplazarse con `SpeechVoiceSpeakFlags.Async` no con `SpeechVoiceSpeakFlags.lagsAsync`
  * el uso de `constants.SVE*` cebería reemplazarse con `SpeechVoiceEvents.*`
* El appModule `soffice` ha eliminado las siguientes classes y funciones `JAB_OOTableCell`, `JAB_OOTable`, `gridCoordStringToNumbers`. (#12849)
* `core.CallCancelled` ahora es `exceptions.CallCancelled`. (#12940)
* Todas las constantes que comiencen con RPC de `core` y de `logHandler` se movieron a `RPCConstants.RPC` enum. (#12940)
* Se recomienda que las funciones `mouseHandler.doPrimaryClick` y `mouseHandler.doSecondaryClick` deberían utilizarse para hacer clic con el ratón que realicen una acción lógica tal como activar (primario) o secundario (mostrar menú de contexto),
en lugar de utilizar `executeMouseEvent` y especificar los botones izquierdo y derecho del ratón específicamente.
Esto asegura que el código respetará la configuración del usuario de Windows para intercambiar el botón primario del ratón. (#12642)
* `config.getSystemConfigPath` se ha eliminado - no hay reemplazo. (#12943)
* `shlobj.SHGetFolderPath` se ha eliminado - por favor utiliza `shlobj.SHGetKnownFolderPath` en su lugar. (#12943)
* Se han eliminado las constantes `shlobj`. Se ha creado una nueva enumeración, `shlobj.FolderId` for usage with `SHGetKnownFolderPath`. (#12943)
* `diffHandler.get_dmp_algo` y `diffHandler.get_difflib_algo` se han reemplazado con `diffHandler.prefer_dmp` y `diffHandler.prefer_difflib` respectivamente. (#12974)
* `languageHandler.curLang` se ha eliminado - para obtener el idioma actual de NVDA utiliza `languageHandler.getLanguage()`. (#13082)
* Puede implementarse un nuevo método `getStatusBarText` en un appModule para personalizar el modo en que NVDA obtiene el texto de la barra de estado. (#12845)
* `globalVars.appArgsExtra` se ha eliminado. (#13087)
  * Si tu complemento necesita procesar argumentos adicionales de línea de órdenes consulta la documentación de `addonHandler.isCLIParamKnown` y la guía de desarrolladores para más detalles.
* El módulo UIA handler y otros módulos UIA soportados ahora son parte de un paquete UIAHandler. (#10916)
  * `UIAUtils` ahora es `UIAHandler.utils`
  * `UIABrowseMode` ahora es `UIAHandler.browseMode`
  * `_UIAConstants` ahora es `UIAHandler.constants`
  * `_UIACustomProps` ahora es `UIAHandler.customProps`
  * `_UIACustomAnnotations` ahora es `UIAHandler.customAnnotations`
* Las constantes `IAccessibleHandler` `IA2_RELATION_*` se han reemplazado con la `IAccessibleHandler.RelationType` enum. (#13096)
  * Eliminado `IA2_RELATION_FLOWS_FROM`
  * Eliminado `IA2_RELATION_FLOWS_TO`
  * Eliminado `IA2_RELATION_CONTAINING_DOCUMENT`
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` y `LOCALE_SLANGDISPLAYNAME` se eliminaron de `languageHandler` - utiliza miembros de `languageHandler.LOCALE` en su lugar. (#12753)
* Cambiamos de Minhook a Microsoft Detours como librería de enganche para NVDA. El enganche con esta librería se utiliza principalmente para ayudar al modelo de visualización. (#12964)
* `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` se eliminó. (#13211)
* SCons ahora se compila con varias tareas concurrrentes, igual al número de procesadores lógicos del sistema.
Esto puede reducir dramáticamente los tiempos de compilación en sistemas multinúcleo. (#13226)
* Las constantes `characterProcessing.SYMLVL_*` se eliminaron - por favor utiliza `characterProcessing.SymbolLevel.*` en su lugar. (#13248)
* Las funciones `loadState` y `saveState` se eliminaron de addonHandler - por favor utiliza `addonHandler.state.load` y `addonHandler.state.save` en su lugar. (#13245)
* Se movió la capa de interacción UWP/OneCore de NVDAHelper [de C++/CX a C++/Winrt](https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/move-to-winrt-from-cx). (#10662)
* Ahora es obligatorio utilizar la subclase `DictionaryDialog`. (#13268)
* `config.RUN_REGKEY`, `config.NVDA_REGKEY` están obsoletas, por favor utiliza `config.RegistryKey.RUN`, `config.RegistryKey.NVDA` en su lugar. Se eliminarán en 2023. (#13242)
* `easeOfAccess.ROOT_KEY`, `easeOfAccess.APP_KEY_PATH` están obsoletas, por favor utiliza `easeOfAccess.RegistryKey.ROOT`, `easeOfAccess.RegistryKey.APP` en su lugar. Se eliminarán en 2023. (#13242)
* `easeOfAccess.APP_KEY_NAME` ha quedado obsoleta, se elimina en 2023. (#13242)
* `DictionaryDialog` y `DictionaryEntryDialog` se movieron desde `gui.settingsDialogs` to `gui.speechDict`. (#13294)
* Las relaciones IAccessible2 ahora se muestran en información para desarrolladores para objetos IAccessible2. (#13315)
* `languageHandler.windowsPrimaryLCIDsToLocaleNames` se ha eliminado, en su lugar utiliza `languageHandler.windowsLCIDToLocaleName` or `winKernel.LCIDToLocaleName`. (#13342)
* La propiedad `UIAAutomationId` para objetos UIA debería preferirse a `cachedAutomationId`. (#13125, #11447)
  * `cachedAutomationId` puede utilizarse si se obtiene directamente del elemento.
* `NVDAObjects.window.scintilla.CharacterRangeStruct` se ha movido a `NVDAObjects.window.scintilla.Scintilla.CharacterRangeStruct`. (#13364)
* El booleano `gui.isInMessageBox` se eliminó, por favor utiliza la función `gui.message.isModalMessageBoxActive` en su lugar. (#12984, #13376)
* `controlTypes` se ha separado en varios submodules. (#12510, #13588)
  * `ROLE_*` y `STATE_*` se han reemplazado por `Role.*` y `State.*`.
  * Aunque todavía están disponibles, las siguientes deben considerarse obsoletas:
    * `ROLE_*` y `STATE_*`, utiliza `Role.*` y `State.*` en su lugar.
    * `roleLabels`, `stateLabels` y `negativeStateLabels`, usos como `roleLabels[ROLE_*]` deberían reemplazarse por sus equivalencias `Role.*.displayString` o `State.*.negativeDisplayString`.
    * `processPositiveStates` y `processNegativeStates` deberían utilizar `processAndLabelStates` en su lugar.
* Las constantes de celda de Excel (`NVSTATE_*`) ahora son valores en el enum `NvCellState`, reflejadas en la enum `NvCellState` en `NVDAObjects/window/excel.py` y mapeadas en `controlTypes.State` a través de _nvCellStatesToStates. (#13465)
* El mienbro de la estructura `EXCEL_CELLINFO` `state` ahora es `nvCellStates`.
* `mathPres.ensureInit` se ha eliminado, MathPlayer ahora se inicializa cuando NVDA arranca. (#13486)

## 2021.3.5

Esta es una versión menor para corregir un problema de seguridad.
Por favor, comunica responsablemente los fallos de seguridad a <info@nvaccess.org>.

### Correcciones de Seguridad

* Se ha corregido el aviso de seguridad `GHSA-xc5m-v23f-pgr7`.
  * El diálogo pronunciación de símbolos ahora se deshabilita en modo seguro.

## 2021.3.4

Esta es una versión menor para corregir varios problemas de seguridad descubiertos.
Por favor, comunica responsablemente los fallos de seguridad a <info@nvaccess.org>.

### Correcciones de Seguridad

* Se ha corregido el aviso de seguridad `GHSA-354r-wr4v-cx28`. (#13488)
  * Se elimina la capacidad de arrancar NVDA con el registro de depuración habilitado cuando NVDA se ejecuta en modo seguro.
  * Se elimina la capacidad de actualizar NVDA cuando NVDA se ejecute en modo seguro.
* Se ha corregido el aviso de seguridad `GHSA-wg65-7r23-h6p9`. (#13489)
  * Se elimina la capacidad de abrir el diálogo Gestos de Entrada en modo seguro.
  * Se elimina la capacidad de abrir los diálogos de diccionario predeterminado, diccionario temporal y diccionario por voces en modo seguro.
* Se ha corregido el aviso de seguridad `GHSA-mvc8-5rv9-w3hx`. (#13487)
  * La utilidad wx GUI inspection ahora está desactivada en modo seguro.

## 2021.3.3

Esta versión es idéntica a la 2021.3.2.
Existía un error en NVDA 2021.3.2 en el que se identificaba incorrectamente como 2021.3.1.
En esta versión se identifica correctamente como 2021.3.3.

## 2021.3.2

Esta es una versión menor para corregir varios problemas de seguridad encontrados.
Por favor, comunica responsablemente los fallos de seguridad a <info@nvaccess.org>.

### Corrección de Errores

* Corrección de seguridad: se evita la navegación de objetos fuera de la pantalla de bloqueo en Windows 10 y Windows 11. (#13328)
* Corrección de seguridad: El cuadro de diálogo del Administrador de complementos está ahora desactivado en las pantallas seguras. (#13059)
* Corrección de seguridad: La ayuda de contexto de NVDA ya no está disponible en pantallas seguras. (#13353)

## 2021.3.1

Esta es una versión menor para corregir varios problemas en 2021.3.

### Cambios

* El nuevo protocolo HID Braille ya no es el preferido cuando se pueda utilizar otro controlador de pantalla braille. (#13153)
* El nuevo protocolo HID Braille puede deshabilitarse a través de una configuración en el panel de opciones avanzadas. (#13180)

### Corrección de Fallos

* De nuevo se abrevian las regiones en braille. #13158
* Corregida la autodetección inestable de las pantallas braille Humanware Brailliant y APH Mantis Q40 cuando se utiliza Bluetooth. (#13153)

## 2021.3

Esta versión introduce el soporte para la nueva especificación Braille HID.
Esta especificación pretende estandarizar el soporte de pantallas braille sin la necesidad de controladores individuales.
Hay actualizaciones para eSpeak-NG y LibLouis, incluyendo tablas nuevas para ruso y Tshivenda.
Los sonidos de error pueden habilitarse en compilaciones estables de NVDA a través de una opción nueva en las opciones avanzadas.
Verbalizar todo en Word ahora desplaza la vista para mantener visible la posición actual.
Hay montones de mejoras al utilizar Office con UIA.
Una de las correcciones de UIA es que Outlook ahora ignora más tipos de tablas de diseño en los mensajes.

Notas importantes:

Debido a una actualización de nuestro certificado de seguridad, un pequeño número de usuarios obtiene un error cuando NVDA 2021.2 busca actualizaciones.
NVDA ahora pide a Windows que actualice los certificados de seguridad, lo que evitará este error en el futuro.
Los usuarios afectados tendrán que descargar esta actualización manualmente.

### Nuevas Características

* Se añade un gesto de entrada para conmutar opciones para anunciar el estilo de bordes de la celda. (#10408)
* Soporte para la nueva especificación HID Braille que pretende estandarizar el soporte para pantallas Braille. (#12523)
  * Los dispositivos que admitan esta especificación se autodetectarán por NVDA.
  * Para más detalles técnicos sobre la implementación de NVDA de esta especificación, consulta https://github.com/nvaccess/nvda/blob/master/devDocs/hidBrailleTechnicalNotes.md
* Añadido el soporte para el dispositivo braille VisioBraille Vario 4. (#12607)
* Se pueden habilitar las notificaciones de error (opciones avanzadas) cuando se utilice cualquier versión de NVDA. (#12672)
* En Windows 10 y posterior, NVDA anunciará el recuento de sugerencias al introducir términos de búsqueda en aplicaciones como la configuración y la Tienda de Microsoft. (#7330, #12758, #12790)
* La navegación por tablas es ahora compatible con los controles de cuadrícula creados mediante el cmdlet Out-GridView en PowerShell. (#12928)

### Cambios

* Espeak-ng se ha actualizado a 1.51-dev commit `74068b91bcd578bd7030a7a6cde2085114b79b44`. (#12665)
* NVDA utilizará por defecto eSpeak si no hay voces OneCore instaladas que admitan el idioma preferido en NVDA. (#10451)
* Si las voces OneCore no hablan con consistencia se vuelve a utilizar a eSpeak como sintetizador. (#11544)
* Al leer la barra de estado con `NVDA+fin`, el cursor de revisión ya no se mueve a su localización.
Si necesitas esta funcionalidad por favor asigna un gesto al script apropiado en la categoría Navegador de objetos en el diálogo Gestos de Entrada. (#8600)
* Al abrir un cuadro de diálogo de opciones que ya esté abierto, NVDA pone el foco en el cuadro de diálogo existente en lugar de generar un error. (#5383)
* Actualizado el transcriptor braille liblouis a [3.19.0](https://github.com/liblouis/liblouis/releases/tag/v3.19.0). (#12810)
  * Nuevas tablas braille: Ruso grado 1, Tshivenda grado 1, Tshivenda grado 2
* En lugar de "contenido marcado" o "mar", se anunciará "resaltado" o "rstd" para la voz y el braille respectivamente. (#12892)
* NVDA ya no intentará salir cuando los diálogos estén esperando una acción requerida (ej.: Confirmar/Cancelar). (#12984)

### Corrección de Fallos

* El seguimiento de las teclas modificadoras (como Control, o Insertar) es más robusto cuando watchdog se esté recuperando. (#12609)
* Vuelve a ser posible comprobar las actualizaciones de NVDA en ciertos sistemas; por ejemplo, instalaciones limpias de Windows. (#12729)
* NVDA anuncia correctamente las celdas de la tabla en blanco en Microsoft Word cuando se utiliza UI automation. (#11043)
* En las celdas de la cuadrícula de datos ARIA en la web, la tecla Escape ahora se pasará a la cuadrícula y ya no desactivará el modo foco incondicionalmente. (#12413)
* Al leer una celda de cabecera de una tabla en Chrome, se corrige que el nombre de la columna se anuncie dos veces. (#10840)
* NVDA ya no informa de un valor numérico para los deslizadores UIA que tengan definida una representación textual de su valor. (Ahora se prefiere UIA ValuePattern a RangeValuePattern). (#12724)
* NVDA ya no trata el valor de los deslizadores de UIA como si fuera siempre porcentual.
* La notificación de la ubicación de una celda en Microsoft Excel cuando se accede a través de UI Automation vuelve a funcionar correctamente en Windows 11. (#12782)
* NVDA ya no establece configuraciones regionales de Python no válidas. (#12753)
* Si se desinstala un complemento deshabilitado y se vuelve a instalar, se vuelve a habilitar. (#12792)
* Se han corregido los errores relacionados con la actualización y eliminación de complementos cuando la carpeta de complementos se haya renombrado o tenga archivos abiertos. (#12792, #12629)
* Cuando se utiliza UI automation para acceder a los controles de las hojas de cálculo de Microsoft Excel, NVDA ya no anuncia de forma redundante cuando se selecciona una sola celda. (#12530)
* Se lee automáticamente más texto de diálogo en LibreOffice Writer, como en los diálogos de confirmación. (#11687)
* La lectura y navegación con el modo exploración en Microsoft Word a través de UI automation ahora garantiza que el documento siempre se desplace para que la posición actual del modo exploración sea visible, y que la posición del cursor en el modo foco refleja correctamente la posición del modo exploración. (#9611)
* Cuando se realiza la función "Verbalizar todo" en Microsoft Word mediante UI automation, el documento se desplaza automáticamente y la posición del cursor se actualiza correctamente. (#9611)
* Cuando se leen correos electrónicos en Outlook y NVDA está accediendo al mensaje con UI automation, ciertas tablas están ahora marcadas como tablas de diseño, lo que significa que ya no serán anunciadas por defecto. (#11430)
* Se ha corregido un error poco frecuente al cambiar los dispositivos de audio. (#12620)
* La entrada con tablas braille literarias debería comportarse de forma más fiable cuando se trata de campos de edición. (#12667)
* Al navegar por el calendario de la bandeja del sistema de Windows, NVDA anuncia ahora el día de la semana en su totalidad. (#12757)
* Cuando se utiliza un método de entrada en chino como Taiwán - Microsoft Quick en Microsoft Word, el desplazamiento de la pantalla braille hacia adelante y hacia atrás ya no salta incorrectamente a la posición original del cursor. (#12855)
* Al acceder a documentos de Microsoft Word a través de UIA, la navegación por frases (alt+flecha abajo / alt+flecha arriba) vuelve a ser posible. (#9254)
* Al acceder a MS Word con UIA, ahora se anuncia la sangría de los párrafos. (#12899)
* Al acceder a MS Word con UIA, ahora se anuncia la orden de seguimiento de cambios y algunas otras órdenes localizadas en Word . (#12904)
* Corregidos los duplicados en braille y voz cuando la 'descripción' coincida con el 'contenido' o el 'nombre'. (#12888)
* En MS Word con UIA activado, hay una reproducción más precisa de los sonidos de errores ortográficos mientras se escribe. (#12161)
* En Windows 11, NVDA ya no anunciará "panel" al pulsar Alt+Tab para cambiar de programa. (#12648)
* El nuevo panel lateral de seguimiento de Comentarios Modernos ahora es compatible con MS Word cuando no se acceda al documento a través de UIA. Pulsa alt+f12 para moverte entre el panel lateral de seguimiento y el documento. (#12982)

### Cambios para Desarrolladores

* Compilar NVDA ahora requiere de Visual Studio 2019 16.10.4 o posterior.
Para que coincida con el entorno de compilación de producción, actualiza Visual Studio para que esté sincronizado con la [versión actual que AppVeyor está utilizando](https://www.appveyor.com/docs/windows-images-software/#visual-studio-2019). (#12728)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` han sido marcados como obsoletos y se eliminarán en 2022.1. (#12660)
  * En su lugar utiliza `apiLevel` (consulta los comentarios  en `_UIAConstants.WinConsoleAPILevel` para más detalles).
* La transparencia del color de fondo del texto procedente de las aplicaciones GDI (a través del modelo de visualización), está ahora expuesta para los complementos o appModules. (#12658)
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` y `LOCALE_SLANGDISPLAYNAME` se han movido al enum de `LOCALE` en languageHandler.
Todavía están disponibles a nivel de módulo, pero están obsoletos y se eliminarán en NVDA 2022.1. (#12753)
* El uso de las funciones `addonHandler.loadState` y `addonHandler.saveState` debe sustituirse por sus equivalentes `addonHandler.state.save` y `addonHandler.state.load` antes de 2022.1. (#12792)
* La salida braille ahora se puede comprobar en pruebas del sistema. (#12917)

## 2021.2

Esta versión introduce el soporte preliminar para Windows 11.
Aunque Windows 11 aún no ha sido lanzado, esta versión se ha probado en versiones preliminares de Windows 11.
Se incluye una corrección importante para la Cortina de Pantalla (consulta Notas importantes).
La herramienta COM Registration Fixing ahora puede resolver más problemas cuando se ejecuta NVDA.
Hay actualizaciones para el sintetizador eSpeak y para el transcriptor braille LibLouis.
También hay varias correcciones de fallos y mejoras, en particular para el soporte de braille y para las terminales de Windows, para la calculadora, el panel de emoji y para el historial del portapapeles.

### Notas importantes

Debido a un cambio en la API Windows Magnification, la Cortina de Pantalla tuvo que ser actualizada para admitir las versiones más nuevas de Windows.
Utiliza NVDA 2021.2 para activar la Cortina de Pantalla con Windows 10 21H2 (10.0.19044) o posteriores.
Esto incluye Windows 10 Insiders y Windows 11.
Por razones de seguridad, al utilizar una versión nueva de Windows, obtén una confirmación visual de que la Cortina de Pantalla haga que ésta esté totalmente negra.

### Nuevas características

* Soporte experimental para anotaciones ARIA:
  * añade una orden para leer un resumen de detalles de un objeto con aria-details. (#12364)
  * añade una opción en preferencias avanzadas para anunciar si un objeto tiene detalles en modo Exploración. (#12439)
* En Windows 10 Versión 1909 y posteriores (incluyendo Windows 11), NVDA anunciará el recuento de sugerencias al realizar búsquedas en el Explorador de Archivos. (#10341, #12628)
* En Microsoft Word, NVDA ahora anuncia el resultado de los atajos de sangría y sangría francesa cuando se ejecuten. (#6269)

### Cambios

* Espeak-ng se ha actualizado a 1.51-dev commit `ab11439b18238b7a08b965d1d5a6ef31cbb05cbb`. (#12449, #12202, #12280, #12568)
* Si se activa artículo en las preferencias de usuario para formateado de documentos, NVDA anuncia "artículo" después del contenido. (#11103)
* Actualizado el transcriptor braille liblouis a [3.18.0](https://github.com/liblouis/liblouis/releases/tag/v3.18.0). (#12526)
  * Nuevas tablas braille: Búlgaro grado 1, Birmano grado 1, Birmano grado 2, Kazajo grado 1, Jemer grado 1, Kurdo del norte grado 0, Sepedi grado 1, Sepedi grado 2, Sesotho grado 1, Sesotho grado 2, Setswana grado 1, Setswana grado 2, Tártaro grado 1, Vietnamita grado 0, Vietnamita grado 2, Vietnamita del sur grado 1, Xhosa grado 1, Xhosa grado 2, Yakut grado 1, Zulú grado 1, Zulú grado 2
* El OCR de Windows 10 pasó a denominarse OCR de Windows. (#12690)

### Corrección de Errores

* En la Calculadora de Windows 10, NVDA anunciará las expresiones de la calculadora sobre la pantalla braille. (#12268)
* En los programas de terminal en Windows 10 versión 1607 y posterior, al insertar o eliminar caracteres en el medio de una línea, ya no se leen los caracteres a la derecha del cursor. (#3200)
  * Ahora Diff Match Patch se activa por defecto. (#12485)
* La entrada braille funciona correctamente con las siguientes tablas contraídas: Árabe grado 2, Español grado 2, Urdu grado 2, Chino (China, Mandarín) grado 2. (#12541)
* La Herramienta COM Registration Fixing ahora resuelve más problemas, especialmente en Windows de 64 bit. (#12560)
* Mejoras al manejo de botones para el dispositivo braille Seika Notetaker de Nippon Telesoft. (#12598)
* Mejoras para anunciar el panel de emoji de Windows y el historial del portapapeles. (#11485)
* Se han actualizado las descripciones de los caracteres del alfabeto Bengalí. (#12502)
* NVDA sale de forma segura cuando se inicie un nuevo proceso. (#12605)
* Volver a seleccionar el controlador de la pantalla braille Handy Tech desde el diálogo Seleccionar Pantalla Braille ya no provoca errores. (#12618)
* La versión de Windows 10.0.22000 o posterior se reconoce como Windows 11, no como Windows 10. (#12626)
* Se ha corregido y probado la compatibilidad de la cortina de pantalla para versiones de Windows hasta la 10.0.22000. (#12684)
* Si no se muestran resultados al filtrar los gestos de entrada, el diálogo de configuración de gestos de entrada sigue funcionando como se esperaba. (#12673)
* Se corrigió un fallo donde el primer elemento de menú de un submenú no se anuncia en algunos contextos. (#12624)

### Cambios para Desarrolladores

* La constante `characterProcessing.SYMLVL_*` debería substituirse utilizando su equivalente `SymbolLevel.*` antes de 2022.1. (#11856, #12636)
* `controlTypes` se ha dividido en varios submódulos, los símbolos marcados como obsoletos deben reemplazarse antes de 2022.1. (#12510)
  * Las constantes `ROLE_*` y `STATE_*` deberían reemplazarse por sus equivalentes `Role.*` y `State.*`.
  * Las constantes `roleLabels`, `stateLabels` y `negativeStateLabels` han quedado obsoletas, los usos tales como `roleLabels[ROLE_*]` deberían reemplazarse por sus equivalentes `Role.*.displayString` o `State.*.negativeDisplayString`.
  * Las etiquetas `processPositiveStates` y `processNegativeStates` han quedado obsoletas para su eliminación.
* En Windows 10 Versión 1511 y posterior (incluyendo compilaciones Insider Preview), el nombre actual de la versión de la característica de actualización de Windows se obtiene del Registro de Windows. (#12509)
* Obsoleto: `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` se eliminará en 2022.1, no hay un reemplazo directo. (#12544)

## 2021.1

Esta versión incluye soporte experimental opcional para UIA en Excel y navegadores Chromium.
Hay correcciones para varios idiomas y para acceso a los enlaces en braille.
Hay actualizaciones para Unicode CLDR, para símbolos matemáticos y para LibLouis.
Así como muchas otras correcciones y mejoras incluyendo Office, Visual Studio y varios idiomas.

Nota:

 * Esta versión rompe la compatibilidad con los complementos existentes.
 * Esta versión también deja de ser compatible con Adobe Flash.

### Nuevas Características

* Soporte preliminar para UIA con navegadores basados en Chromium (como Edge). (#12025)
* Soporte experimental opcional para Microsoft Excel a través de UI Automation. Sólo se recomienda para Microsoft Excel compilación 16.0.13522.10000 o superior. (#12210)
* Navegación más fácil de la salida en la Consola Python de NVDA. (#9784)
  * alt+arriba/abajo salta al resultado anterior/siguiente (añade shift para seleccionar).
  * control+l borra el panel de salida.
* NVDA ahora anuncia las categorías asignadas a una cita en Microsoft Outlook si la hay. (#11598)
* Soporte para la pantalla braille del Anotador Electrónico Seika de Nippon Telesoft. (#11514)

### Cambios

* En modo Exploración, los controles ahora pueden activarse con los sensores de seguimiento braille sobre su descriptor (Ej.: "enl" para un enlace). esto es especialmente útil para activar, por ejemplo, casillas de verificación sin etiquetas. (#7447)
* NVDA ahora evita que el usuario realice el OCR de Windows 10 si la cortina de pantalla está habilitada. (#11911)
* Actualizado el repositorio Unicode Common Locale Data (CLDR) a 39.0. (#11943), #12314)
* Añadidos más signos matemáticos al diccionario de símbolos. (#11467)
* La guía del usuario, el fichero de cambios y el listado de teclas de órdenes ahora tienen un aspecto renovado. (#12027)
* Ahora se anuncia "no soportado" cuando se intente cambiar el diseño de pantalla en aplicaciones que no lo admitan tales como Microsoft Word. (#7297)
* La opción 'Intentar cancelar la voz para eventos de foco caducados' en el panel de opciones avanzadas ahora está activada por defecto. (#10885)
  * Este comportamiento se puede desactivar configurando esta opción como "No".
  * Las aplicaciones web (Ej.: Gmail) ya no verbalizan información obsoleta cuando se mueva el foco rápidamente.
* Actualizado el transcriptor braille liblouis a [3.17.0](https://github.com/liblouis/liblouis/releases/tag/v3.17.0). (#12137)
  * Nuevas tablas braille: braille literario bielorruso, braille computerizado bielorruso, Urdu grado 1, Urdu grado 2.
* El soporte para contenido Adobe Flash se ha eliminado de NVDA debido a que Adobe  desaconseja activamente el uso de Flash. (#11131)
* NVDA saldrá incluso con ventanas todavía abiertas, el proceso de salida ahora cierra todas las ventanas y diálogos de NVDA. (#1740)
* El Visualizador de Voz ahora puede cerrarse con `alt+F4` y tiene un botón cerrar estándar para una interacción más fácil con los usuarios de dispositivos señaladores. (#12330)
* El Visualizador Braille ahora tiene un botón cerrar estándar para una interacción más fácil con usuarios de dispositivos señaladores. (#12328)
* En el cuadro de diálogo lista de elementos, se ha eliminado la tecla rápida del botón "Activar" en algunas localizaciones para evitar la colisión con la etiqueta del botón de opción del tipo de elemento. Cuando esté disponible, el botón sigue siendo el predeterminado del diálogo y, como tal, puede seguir siendo invocado simplemente pulsando intro desde la propia lista de elementos. (#6167)

### Corrección de Fallos

* La lista de mensajes en Outlook 2010 vuelve a ser legible. (#12241)
* En programas de terminal en Windows 10 versión 1607 y posteriores, al insertar o eliminar caracteres en medio de una línea, ya no se leen los caracteres a la derecha del cursor. (#3200)
  * Esta corrección experimental debe habilitarse manualmente en el panel de opciones avanzadas de NVDA cambiando el algoritmo diff a Diff Match Patch.
* En MS Outlook, ya no debería producirse un anunciado de distancia inapropiada cuando se haga shift+tabulador desde el cuerpo del mensaje al campo de asunto. (#10254)
* En la consola de Python, ahora se admite la inserción de un tabulador para la sangría al principio de una línea de entrada no vacía y la realización de un tabulador en medio de una línea de entrada. (#11532)
* La información de formato y otros mensajes navegables ya no presentan líneas en blanco inesperadas cuando el diseño de pantalla esté desactivado. (#12004)
* Ahora es posible leer comentarios en MS Word con UIA activado. (#9285)
* Se ha mejorado el rendimiento al interactuar con Visual Studio. (#12171)
* Se han corregido errores gráficos como la falta de elementos cuando se utiliza NVDA con un diseño de derecha a izquierda. (#8859)
* Se respeta la dirección de la disposición de la GUI basada en el idioma de NVDA, no en la configuración regional del sistema. (#638)
  * problema conocido para idiomas de derecha a izquierda: el borde derecho de los clips de agrupaciones con etiquetas/control. (#12181)
* La configuración regional de Python se establece para que coincida con el idioma seleccionado en las preferencias de forma consistente, y ocurrirá cuando se utilice el idioma por defecto. (#12214)
* TextInfo.getTextInChunks ya no se congela cuando se llame a controles de edición enriquecida como el visor de registro de NVDA. (#11613)
* Vuelve a ser posible utilizar NVDA en idiomas que contengan guiones bajos en el nombre de la configuración regional, como de_CH, en Windows 10 1803 y 1809. (#12250)
* En WordPad, la configuración del anunciado de superíndice y subíndice funciona como se esperaba. (#12262)
* NVDA ya no falla al anunciar el contenido recién enfocado en una página web si el antiguo foco desaparece y es reemplazado por el nuevo foco en la misma posición. (#12147)
* El tachado, el superíndice y el subíndice de las celdas enteras de Excel ahora se anuncian si la opción correspondiente está activada. (#12264)
* Se ha corregido la copia de la configuración durante la instalación desde una copia portátil cuando el directorio de configuración de destino por defecto está vacío. (#12071, #12205)
* Corregido el anuncio incorrecto de algunas letras con acentos o diacríticos cuando la opción 'Decir mayús antes de las mayúsculas' está marcada. (#11948)
* Se ha corregido el fallo de cambio de tono en el sintetizador de voz SAPI4. (#12311)
* El instalador de NVDA ahora también respeta el parámetro de línea de órdenes `--minimal` y no reproduce el sonido de inicio, siguiendo el mismo comportamiento documentado que un ejecutable de NVDA instalado o con copia portátil. (#12289)
* En MS Word o Outlook, la tecla rápida de navegación de la tabla ahora puede saltar a la tabla de diseño si la opción "Incluir tablas de diseño" está activada en la configuración del modo de navegación. (#11899)
* NVDA ya no anunciará "↑↑↑" para emojis en idiomas en particular. (#11963)
* Espeak ahora admite de nuevo Cantonés y Mandarín. (#10418)
* En el nuevo Microsoft Edge basado en Chromium los campos de texto tales como la barra de direcciones ahora se anuncian cuando estén vacíos. (#12474)
* Corregido el controlador braille de Seika. (#10787)

### Cambios para Desarrolladores

* Nota: esta es una versión que rompe la compatibilidad con la API de los complementos. Los complementos tendrán que volver a probarse y actualizar su manifiesto.
* El sistema de compilación de NVDA ahora obtiene todas las dependencias de Python con pip y las almacena en un entorno virtual de Python. Todo esto se hace de forma transparente.
  * Para compilar NVDA, se debe seguir utilizando SCons de la forma habitual. Por ejemplo, ejecutando scons.bat en la raíz del repositorio. Ejecutar `py -m SCons` ya no se admite, y `scons.py` también ha sido eliminado.
  * Para ejecutar NVDA desde el código fuente, en lugar de ejecutar `source/nvda.pyw` directamente, el desarrollador debe ahora utilizar `runnvda.bat` en la raíz del repositorio. Si intentas ejecutar `source/nvda.pyw`, un cuadro de mensaje te avisará de que esto ya no se admite.
  * Para realizar pruebas unit, ejecuta `rununittests.bat [<extra unittest discover options>]`
  * Para realizar pruebas del sistema: ejecuta `runsystemtests.bat extra robot options>]`
  * Para realizar linting, ejecuta `runlint.bat <base branch>`
  * Por favor, consulta el archivo readme.md para más detalles.
* También se han actualizado las siguientes dependencias de Python:
  * comtypes actualizado a 1.1.8.
  * pySerial actualizado a 3.5.
  * wxPython actualizado a 4.1.1.
  * Py2exe actualizado a 0.10.1.0.
* Se ha eliminado `LiveText._getTextLines`. (#11639)
  * En su lugar, sobreescribe `_getText` que devuelve una cadena de todo el texto del objeto.
* Los objetos `LiveText` ahora pueden calcular las diferencias por carácter. (#11639)
  * Para alterar el comportamiento de las diferencias para algún objeto, sobreescribe la propiedad `diffAlgo` (consulta el docstring para más detalles).
* Al definir un script con el decorador de script, se puede especificar el argumento booleano 'allowInSleepMode' para controlar si un script está disponible en modo de suspensión o no. (#11979)
* Se han eliminado las siguientes funciones del módulo de configuración. (#11935)
  * canStartOnSecureScreens - utiliza config.isInstalledCopy en su lugar.
  * hasUiAccess y execElevated - utilízalas desde el módulo systemUtils.
  * getConfigDirs - utiliza globalVars.appArgs.configPath en su lugar.
* Las constantes Module level REASON_* se han eliminado de controlTypes - utiliza en su lugar controlTypes.OutputReason. (#11969)
* Se ha eliminado REASON_QUICKNAV de browseMode - utiliza controlTypes.OutputReason.QUICKNAV en su lugar. (#11969)
* La propiedad `NVDAObject` (y derivados) `isCurrent` ahora devuelve estrictamente la clase Enum `controlTypes.IsCurrent`. (#11782)
  * La propiedad `isCurrent` ya no es Opcional, y por tanto no devolverá Ninguno.
    * Cuando un objeto no es actual, se devuelve `controlTypes.IsCurrent.NO`.
* El mapeado `controlTypes.isCurrentLabels` se ha eliminado. (#11782)
  * En su lugar utiliza la propiedad `displayString` en un valor enum `controlTypes.IsCurrent`.
    * Por ejemplo: `controlTypes.IsCurrent.YES.displayString`.
* Se ha eliminado `winKernel.GetTimeFormat` - se debe utilizar `winKernel.GetTimeFormatEx`.
* Se ha eliminado `winKernel.GetDateFormat` - se utiliza `winKernel.GetDateFormatEx` en su lugar. (#12139)
* Se ha eliminado `gui.DriverSettingsMixin` - utiliza `gui.AutoSettingsMixin`. (#12144)
* Se ha eliminado `speech.getSpeechForSpelling` - utiliza `speech.getSpellingSpeech`. (#12145)
* Los comandos no se pueden importar directamente desde speech como `import speech; speech.ExampleCommand()` o `import speech.manager; speech.manager.ExampleCommand()` - utiliza `from speech.commands import ExampleCommand` en su lugar. (#12126)
* `speakTextInfo` ya no enviará la voz a través de `speakWithoutPauses` si el motivo es `SAYALL`, ya que `SayAllHandler` lo hace ahora manualmente. (#12150)
* El módulo `synthDriverHandler` ya no se importa por defecto en `globalCommands` y `gui.settingsDialogs` - utiliza `from synthDriverHandler import synthFunctionExample` en su lugar. (#12172)
* Se ha eliminado `ROLE_EQUATION` de controlTypes - utiliza `ROLE_MATH` en su lugar. (#12164)
* Se han eliminado las clases `autoSettingsUtils.driverSetting` de `driverHandler` - utilízalas desde `autoSettingsUtils.driverSetting`. (#12168)
* Se han eliminado las clases `autoSettingsUtils.utils` de `driverHandler` - por favor, utilízalas desde `autoSettingsUtils.utils`. (#12168)
* Se ha eliminado el soporte de los `TextInfo` que no heredan de `contentRecog.BaseContentRecogTextInfo`. (#12157)
* Se ha eliminado `speech.speakWithoutPauses` - por favor, utiliza `speech.speechWithoutPauses.SpeechWithoutPauses(speakFunc=speech.speak).speakWithoutPauses` en su lugar. (#12195, #12251)
* Se ha eliminado `speech.re_last_pause` - por favor, utiliza `speech.speechWithoutPauses.SpeechWithoutPauses.re_last_pause` en su lugar. (#12195, #12251)
* Los diálogos `WelcomeDialog`, `LauncherDialog` y `AskAllowUsageStatsDialog` se han trasladado a `gui.startupDialogs`. (#12105)
* Se ha movido `getDocFilePath` de `gui` al módulo `documentationUtils`. (#12105)
* El módulo gui.accPropServer, así como las clases AccPropertyOverride y ListCtrlAccPropServer del módulo gui.nvdaControls se han eliminado en favor del soporte nativo de WX para anular las propiedades de accesibilidad. Al mejorar la accesibilidad de los controles WX, implementa wx.Accessible en su lugar. (#12215)
* Los ficheros en `source/comInterfaces/` son ahora más fácilmente consumibles por las herramientas de desarrollo, como los IDE. (#12201)
* Se han añadido métodos y tipos convenientes al módulo winVersion para obtener y comparar versiones de Windows. (#11909)
  * se ha eliminado la función isWin10 que se encontraba en el módulo winVersion.
  * la clase winVersion.WinVersion es un tipo comparable y ordenable que encapsula la información de la versión de Windows.
  * Se ha añadido la función winVersion.getWinVer para obtener una winVersion.WinVersion que represente el sistema operativo que se está ejecutando actualmente.
  * Se han añadido constantes de conveniencia para las versiones conocidas de Windows, véase winVersion.WIN* constants.
* IAccessibleHandler ya no importa de forma estelar todo lo de las interfaces IAccessible y IA2 COM - por favor, utilízalas directamente. (#12232)
* Los objetos TextInfo tienen ahora propiedades de inicio y fin que pueden compararse matemáticamente con operadores como < <= == != >= >. (#11613)
  * Por ejemplo, ti1.start <= ti2.end
  * Ahora se prefiere este uso en lugar de ti1.compareEndPoints(ti2, "startToEnd") <= 0
* Las propiedades de inicio y fin de TextInfo también pueden establecerse entre sí. (#11613)
  * Por ejemplo, ti1.start = ti2.end
  * Se prefiere este uso en lugar de ti1.SetEndPoint(ti2, "startToEnd")
* Se eliminan `wx.CENTRE_ON_SCREEN` y `wx.CENTER_ON_SCREEN`, en su lugar se utiliza `self.CentreOnScreen()`. (#12309)
* Se ha eliminado `easeOfAccess.isSupported`, NVDA sólo admite versiones de Windows en las que se evalúa como `True`. (#12222)
* Se ha movido `sayAllHandler` a `speech.sayAll`. (#12251)
  * `speech.sayAll.SayAllHandler` expone las funciones `stop`, `isRunning`, `readObjects`, `readText`, `lastSayAllMode`.
  * El comando `SayAllHandler.stop` también reinicia la instancia `SayAllHandler` `SpeechWithoutPauses`.
  * Se ha sustituido `CURSOR_REVIEW` y `CURSOR_CARET` por `CURSOR.REVIEW` y `CURSOR.CARET`.
* Se ha movido `speech.SpeechWithoutPauses` a `speech.speechWithoutPauses.SpeechWithoutPauses`. (#12251)
* Se ha cambiado el nombre de `speech.curWordChars` a `speech._curWordChars`. (#12395)
* se han eliminado de `speech` y se puede acceder a ellos a través de `speech.getState()`. Ahora son valores de sólo lectura. (#12395)
  * speechMode
  * speechMode_beeps_ms
  * beenCanceled
  * isPaused
* para actualizar `speech.speechMode` utiliza `speech.setSpeechMode`. (#12395)
* se ha movido lo siguiente a `speech.SpeechMode`. (#12395)
  * `speech.speechMode_off` se convierte en `speech.SpeechMode.off`
  * `speech.speechMode_beeps` pasa a ser `speech.SpeechMode.beeps`
  * `speechMode_talk` pasa a ser `speech.Speech.SpeechMode.talk`
* `IAccessibleHandler.IAccessibleObjectIdentifierType` es ahora `IAccessibleHandler.types.IAccessibleObjectIdentifierType`. (#12367)
* Cambiaron `NVDAObjects.UIA.WinConsoleUIA` (#12094)
  * `NVDAObjects.UIA.winConsoleUIA.is21H1Plus` renombrado a `NVDAObjects.UIA.winConsoleUIA.isImprovedTextRangeAvailable`.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfo` renombrado al nombre de la clase de inicio en mayúsculas.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfoPre21H1` renombrado a `NVDAObjects.UIA.winConsoleUIA.ConsoleUIATextInfoWorkaroundEndInclusive`
    * La implementación funciona en ambos siendo incluidos los puntos finales (en rangos de texto) antes de [microsoft/terminal PR 4018](https://github.com/microsoft/terminal/pull/4018)
    * Soluciones para `expand`, `collapse`, `compareEndPoints`, `setEndPoint`, etc

## 2020.4

Esta versión incluye métodos nuevos de entrada de chino, una actualización de Liblouis y la Lista de Elementos (NVDA+f7) ahora funciona en modo foco.
La ayuda sensible al contexto ahora está disponible al pulsar F1 en diálogos de NVDA.
Mejoras para las reglas de pronunciación de símbolos, diccionarios del habla, mensajes braille y lectura superficial.
Corrección de fallos y mejoras para Mail, Outlook, Teams, Visual Studio, Azure Data Studio, Foobar2000.
En la web, hay mejoras para Google Docs y mucho mejor soporte para ARIA.
Más muchas otras importantes correcciones de fallos  y mejoras.

### Nuevas Características

* Al pulsar F1 dentro de los diálogos de NVDA ahora se abrirá el fichero de ayuda para la sección más relevante. (#7757)
* Soporte para autocompletado de sugerencias (IntelliSense) en Microsoft SQL Server Management Studio más Visual Studio 2017 y superior. (#7504)
* Pronunciación de símbolos: soporte para agrupaciones en una definición de símbolos compleja y soporte de referencias de grupo en una regla de substitución que los hace más sencillos y más poderosos. (#11107)
* Ahora se notifica a los usuarios cuando intenten crear entradas de diccionarios del habla con sustituciones inválidas de expresiones regulares. (#11407)
  * Específicamente ahora se detectan errores de agrupación.
* Se ha añadido el soporte para los nuevos métodos de entrada para chino tradicional rápido y para Pinyin en Windows 10. (#11562)
* Los encabezados de pestaña ahora se consideran campos de formulario con la tecla de navegación rápida f. (#10432)
* Añadida una orden para conmutar el anunciado de texto marcado (resaltado); No hay ningún gesto asociado por omisión. (#11807)
* Añadido el parámetro de línea de comandos --copy-portable-config que te permite copiar automáticamente la configuración proporcionada a la cuenta de usuario cuando se instala NVDA en silencio. (#9676)
* Ahora se admite el enrutamiento Braille con el Visualizador Braille para usuarios de ratón, desplazándose para enrutar a una celda braille. (#11804)
* NVDA ahora detectará automáticamente los dispositivos Humanware Brailliant BI 40X y 20X a través de USB y Bluetooth. (#11819)

### Cambios

* Actualizado el transcriptor braille liblouis a la versión 3.16.1:
 * Se abordan múltiples cuelgues
 * Se añade la tabla Braille grado 1 de Baskir
 * Se añade una tabla braille de ordenador copto de 8 puntos
 * Se añaden tablas de braille literario ruso y braille literario ruso (detallado)
 * Se añade la tabla braille para Afrikaans grado 2
 * Se elimina la tabla braille rusa de grado 1
* Cuando se lee con leer todo en el modo exploración, las órdenes buscar siguiente y anterior no detienen la lectura si la opción permitir lectura superficial está activada; leer todo reanuda a partir de después del término siguiente o anterior encontrado. (#11563)
* Para las pantallas braille HIMS se ha remapeado F3 a Espacio + puntos 148. (#11710)
* Mejoras para el UX de las opciones "Tiempo de espera del mensaje braille" y "mostrar mensajes indefinidamente". (#11602)
* En navegadores web y otras aplicaciones que soporten modo exploración, el diálogo Lista de Elementos (NVDA+F7) ahora puede llamarse al estar en modo foco. (#10453)
* Las actualizaciones de regiones ARIA live ahora se suprimen cuando se desactive el anunciado de cambios de contenido dinámico. (#9077)
* NVDA ahora anunciará "Copiado al portapapeles" antes del texto copiado. (#6757)
* Se ha mejorado la presentación de la tabla de vistas gráficas en el gestor de discos. (#10048)
* Las etiquetas de los controles ahora están desactivadas (en gris) cuando el control está desactivado. (#11809)
* Actualizada la anotación emoji de CLDR a la versión 38. (#11817)
* La funcionalidad incorporada "Resaltado del Foco" se ha renombrado a "Resaltado Visual". (#11700)

### Corrección de Fallos

* NVDA vuelve a funcionar correctamente con los campos de edición al utilizar la aplicación Fast Log Entry. (#8996)
* Se anuncia el tiempo transcurrido en Foobar2000 si no se dispone de un tiempo total (por ejemplo, cuando se reproduce una transmisión en directo). (#11337)
* NVDA ahora respeta el atributo aria-roledescription en elementos en contenido editable en páginas web. (#11607)
* Ya no se anuncia 'lista' en cada línea de una lista en Google Docs u otro contenido editable en Google Chrome. (#7562)
* Cuando se navega con las flechas por caracteres o palabras desde un elemento de lista a otro en contenido editable en la web, ahora se anuncia la entrada en el nuevo elemento de lista. (#11569)
* NVDA ahora lee la línea correcta cuando el cursor se coloca en el final de un enlace en el final de un elemento de lista en Google Docs u otro contenido editable en la web. (#11606)
* En Windows 7, al abrir o cerrar el menú Inicio desde el escritorio ahora se pone el foco correctamente. (#10567)
* Cuando se activa "intentar cancelar eventos del foco esperados", el título de la pestaña ahora se anuncia de nuevo al cambiar pestañas en Firefox. (#11397)
* NVDA ya no falla al anunciar un elemento de lista después de escribir un carácter en una lista cuando se verbaliza con las voces Ivona SAPI5 . (#11651)
* Es posible de nuevo utilizar modo exploración al leer correos electrónicos en Windows 10 Mail 16005.13110 y posteriores. (#11439)
* Cuando se usen las voces  Ivona SAPI5 desde harposoftware.com, NVDA ahora es capaz de guardar la configuración, cambiar de sintetizador y ya no se quedará en silencio después de reiniciar. (#11650)
* Ahora es posible introducir el número 6 en braille computerizado desde un teclado braille en pantallas HIMS. (#11710)
* Mejoras importantes en el rendimiento en Azure Data Studio. (#11533, #11715)
* Con "Intentar Cancelar la voz para eventos de foco expirados" activado el título del diálogo buscar de NVDA se anuncia de nuevo. (#11632)
* NVDA ya no debería congelarse cuando se despierta el ordenador y el foco aterriza en un documento de Microsoft Edge. (#11576)
* Ya no es necesario pulsar tab o mover el foco después de cerrar un menú de contexto en MS Edge para que el modo Exploración vuelva a ser funcional de nuevo. (#11202)
* NVDA ya no falla al leer elementos en vistas de lista dentro de una aplicación de 64 bits tal como Tortoise SVN. (#8175)
* Los ARIA treegrids ahora se exponen como tablas normales en modo Exploración tanto en Firefox como en Chrome. (#9715)
* Ahora se puede iniciar una búsqueda inversa con 'buscar anterior' a través de NVDA+shift+F3 (#11770)
* Un script de NVDA ya no se considera repetido si ocurre una pulsación de tecla no relacionada entre las dos ejecuciones del script. (#11388)
* Puede suprimirse de nuevo el anunciado de las etiquetas strong y emphasis en Internet Explorer desactivando Anunciar Énfasis en las opciones de Formato de Documentos de NVDA. (#11808)
* Ya no debería producirse un congelado de varios segundos experimentado por una pequeña cantidad de usuarios al pasar entre las celdas de Excel. (#11818)
* En las compilaciones de Microsoft Teams con números de versión como 1.3.00.28xxx, NVDA ya no falla al leer mensajes en chats o en canales de Teams debido a un menú incorrectamente enfocado. (#11821)
* El texto marcado como error ortográfico y gramatical al mismo tiempo en Google Chrome se anunciará apropiadamente como error ortográfico y gramatical por NVDA. (#11787)
* Al utilizar Outlook (localización al francés), el atajo para "Responder a todos" (control+shift+R) funciona de nuevo. (#11196)
* En Visual Studio, los consejos de la herramienta IntelliSense que proporcionan detalles adicionales sobre el elemento IntelliSense seleccionado actualmente sólo se anuncian una vez. (#11611)
* En la calculadora de Windows 10, NVDA no anunciará el progreso de los cálculos si se desactiva verbalizar caracteres al escribir. (#9428)
* NVDA ya no se bloquea cuando se utilice el inglés grado 2 de Estados unidos y se expande a braille computerizado cuando esté sobre el cursor al mostrar cierto contenido como una URL en braille. (#11754)
* Es posible de nuevo anunciar información de formato para la celda de Excel enfocada utilizando NVDA+F. (#11914)
* La entrada QWERTY en pantallas braille Papenmeier que lo admitan funciona de nuevo y ya no causa que NVDA se congele aleatoriamente. (#11944)
* En navegadores basados en Chromium, se resolvieron varios casos donde la navegación de tablas no funcionaba y NVDA no anunciaba el número de filas y columnas de la tabla. (#12359)

### Cambios para Desarrolladores

* Las pruebas de sistema ahora pueden enviar teclas utilizando spy.emulateKeyPress, que toma un identificador de tecla que se ajusta a los propios nombres de tecla de NVDA y por defecto también la bloquea hasta que se ejecute la acción. (#11581)
* NVDA ya no requiere que el directorio actual sea el directorio de la aplicación NVDA para funcionar. (#6491)
* La opción aria live politeness para live regions ahora puede encontrarse en objetos de NVDA que utilicen la propiedad liveRegionPoliteness. (#11596)
* Ahora es posible definir gestos separados para documentos de Outlook y Word. (#11196)

## 2020.3

Esta versión incluye varias grandes mejoras para la estabilidad y el rendimiento, especialmente en las aplicaciones de Microsoft Office. Hay nuevas opciones para conmutar el soporte de las pantallas táctiles y del anunciado de gráficos.
La existencia de contenido marcado (resaltado) puede anunciarse en los navegadores, y hay nuevas tablas braille alemanas.

### Nuevas Características

* Ahora puedes conmutar el anunciado de gráficos desde las opciones de Formateado de Documentos de NVDA.  Ten en cuenta que deshabilitando esta opción todavía leerá el texto alternativo de los gráficos. (#4837)
* Ahora puedes conmutar el soporte de pantallas táctiles de NVDA. Se ha añadido una opción al panel de interacción táctil de las opciones de NVDA. El gesto predeterminado es NVDA+control+alt+t. (#9682)
* Añadidas nuevas tablas braille para el Alemán. (#11268)
* NVDA ahora detecta controles de texto de sólo lectura de UIA. (#10494)
* La existentcia de contenido marcado (resaltado) se informa tanto en voz como en braille en todos los navegadores web. (#11436)
 * Esto puede activarse y desactivarse con una nueva opción de Formateado de Documento de NVDA para Resaltado.
* Pueden añadirse nuevas teclas al sistema de teclado emulado desde el diálogo Gestos de Entrada de NVDA. (#6060)
  * Para hacerlo, pulsa el botón Añadir después de que selecciones la categoría Teclas de sistema de teclado emulado.
* Ahora se admite Handy Tech Active Braille con joystick. (#11655)
* La opción "Modo foco automático para movimientos del cursor" ahora es compatible con deshabilitar "Poner automáticamente el foco en elementos enfocables". (#11663)

### Cambios

* El script anunciar formato (NVDA+f) ahora se ha cambiado para anunciar el formato en el cursor del sistema en lugar de en la posición del cursor de revisión.  Para anunciar el formato en la posición del Cursor de Revisión ahora utiliza NVDA+shift+f. (#9505)
* NVDA ya no pone automáticamente el foco del sistema en los elementos enfocables por defecto en modo Exploración, mejorando el rendimiento y la estabilidad. (#11190)
* Actualizado CLDR desde la versión 36.1 a la versión 37. (#11303)
* Actualizado eSpeak-NG a 1.51-dev, commit 1fb68ffffea4
* Ahora puedes utilizar la navegación de tablas en cuadros de lista con elementos de lista marcables cuando una lista en particular tenga varias columnas. (#8857)
* En el Administrador de complementos, cuando se te pregunte para confirmar la eliminación de un complemento, ahora  "No", es la predeterminada. (#10015)
* En Microsoft Excel, el diálogo de lista de elementos ahora presenta fórmulas en su forma localizada. (#9144)
* NVDA ahora anuncia la terminología correcta para notas en MS Excel. (#11311)
* Al utilizar la orden "mover cursor de revisión al foco" en modo Exploración, el cursor de revisión ahora se pone en la posición del cursor virtual. (#9622)
* La información anunciada en el modo exploración, como la información de formato con NVDA+F, se muestra ahora en una ventana ligeramente más grande centrada en la pantalla. (#9910)

### Corrección de Errores

* NVDA ahora habla siempre al navegar por palabras y aterriza en cualquier símbolo seguido por un espacio en blanco, cualquiera que sean las opciones de verbosidad. (#5133)
* En aplicaciones que utilicen QT 5.11 o más modernas, las descripciones de los objetos se anuncian de nuevo. (#8604)
* Al eliminar una palabra con control+suprimir, NVDA ya no permanece en silencio. (#3298, #11029)
  * Ahora se anuncia la palabra a la derecha de la eliminada.
* En el panel Opciones Generales, la lista de idiomas ahora se ordena correctamente. (#10348)
* En el diálogo Gestos de Entrada, se mejoró significativamente el rendimiento mientras se filtra. (#10307)(
* Ahora puedes enviar caracteres Unicode más allá de U+FFFF desde una pantalla braille. (#10796)
* NVDA anunciará diálogo Abierto Con contenido en Windows 10 May 2020 Update. (#11335)
* Una opción nueva experimental en Opciones Avanzadas (Habilitar el registro selectivo para eventos y cambios de propiedad de UI Automation) puede proporcionar mayores mejoras de rendimiento en Microsoft Visual Studio y otras aplicaciones basadas en UIAutomation si se habilita. (#11077, #11209)
* Para elementos de lista marcables, el estado seleccionado ya no se anuncia redundantemente, y si es aplicable, se anuncia el estado deseleccionado en su lugar. (#8554)
* En Windows 10 May 2020 Update, NVDA ahora muestra el Mapeador de Sonido de Microsoft al revisar los dispositivos de salida desde el diálogo Sintetizador. (#11349)
* En Internet Explorer, los números ahora se anuncian correctamente para listas ordenadas si la lista no comienza con 1. (#8438)
* En Google chrome, NVDA ahora anunciará no marcado para todos los controles marcables (no sólo casillas de verificación) que actualmente no estén marcados. (#11377)
* Una vez más es posible de nuevo navegar por varios controles cuando el idioma de NVDA esté puesto en Aragonés. (#11384)
* NVDA ya no debería congelarse a veces en Microsoft Word al mover rápidamente las flechas arriba y abajo o al escribir caracteres con el Braille habilitado. (#11431, #11425, #11414)
* NVDA ya no añade un espacio no existente en el arrastre al copiar el navegador de objetos actual al portapapeles. (#11438)
* NVDA ya no activa el perfil Leer todo si no hay nada que leer. (#10899, #9947)
* NVDA ya no es incapaz de leer la lista de características en el administrador Internet Information Services (IIS). (#11468)
* NVDA ahora mantiene el dispositivo de audio abierto mejorando el rendimiento en algunas tarjetas de sonido (#5172, #10721)
* NVDA ya no se congelará ni se apagará cuando mantengas pulsado control+shift+flecha abajo en Microsoft Word. (#9463)
* El estado expandido/contraído de los directorios en el árbol de navegación de drive.google.com ahora siempre se anuncia por NVDA. (#11520)
* NVDA detectará automáticamente la pantalla braille NLS eReader Humanware a través de Bluetooth, ya que su nombre Bluethooth es ahora "NLS eReader Humanware". (#11561)
* Grandes mejoras en el rendimiento de Visual Studio Code. (#11533)

### Cambios para Desarrolladores

* El GUI Helper's BoxSizerHelper.addDialogDismissButtons soporta una nueva palabra clave de argumento "separated", para añadir un separador horizontal estándar a los diálogos (que no sean mensajes y diálogos de entrada simples). (#6468)
* Se añadieron propiedades adicionales a los app modules, incluyendo la ruta para el ejecutable (appPath), es una app de almacenamiento de Windows (isWindowsStoreApp), y arquitectura de máquina para la app (appArchitecture). (#7894)
* Ahora es posible crear app modules para apps hospedadas dentro de wwahost.exe en Windows 8 y posteriores. (#4569)
* Ahora se puede delimitar un fragmento del registro y luego copiarlo al portapapeles usando NVDA+control+shift+F1. (#9280)
* Los objetos específicos de NVDA que se encuentran por el recolector de basura cíclica de Python ahora se registran cuando se borran por el recolector para ayudar en la eliminación de los ciclos de referencia de NVDA. (#11499)
 * La mayoría de las clases de NVDA se rastrean incluyendo NVDAObjects, appModules, GlobalPlugins, SynthDrivers, y TreeInterceptors.
 * Una clase que se necesita rastrear debe heredar de garbageHandler.TrackedObject.
* El registro de depuración significativo para los eventos de MSAA ahora puede habilitarse en la configuración avanzada de NVDA. (#11521)
* Los eventos de MSAA para el objeto enfocado actualmente ya no se filtran junto con otros eventos si se excede la cuenta de eventos para un hilo determinado. (#11520)

## 2020.2

Lo reseñable de esta versión incluye el soporte de una nueva pantalla braille de Nattiq, un soporte mejor para la interfaz gráfica de usuario del antivirus ESET y la Terminal de Windows, mejoras de rendimiento de 1Password y con el sintetizador Windows OneCore. Además de muchas otras importantes mejoras y correcciones de fallos.

### Nuevas Características

* Admisión de nuevas pantallas braille:
  * Nattiq nBraille (#10778)
* Añadido un script para abrir el directorio de configuración de NVDA (sin gesto predeterminado). (#2214)
* Mejor soporte para la interfaz gráfica de usuario del antivirus ESET. (#10894)
* Añadido el soporte para la Terminal de Windows. (#10305)
* Añadida una orden para anunciar el perfil de configuración activo (no hay gesto predeterminado). (#9325)
* Añadida una orden para conmutar el anunciado de subíndices y superíndices (no hay gesto predeterminado). (#10985)
* Las aplicaciones web (Ej. Gmail) ya no verbalizan información incorrecta cuando se mueva el foco rápidamente. (#10885)
  * Esta solución experimental debe activarse manualmente a través de la opción 'Intentar cancelar la voz para eventos de enfoque caducados'  en el panel de opciones avanzadas.
* Se han añadido más símbolos al diccionario de símbolos predeterminado. (#11105)

### Cambios

* Actualizado el transcriptor braille liblouis de 3.12 a [3.14.0](https://github.com/liblouis/liblouis/releases/tag/v3.14.0) (from 3.12.0). (#10832, #11221)
* El anunciado de superíndices y subíndices ahora se controla por separado al anunciado de atributos de fuente. (#10919)
* Debido a cambios hechos en VS Code, NVDA ya no desactiva el modo Exploración en Code por defecto. (#10888)
* NVDA ya no anuncia los mensajes "superior" e "inferior" al mover el cursor de revisión directamente a la primera o última línea del actual navegador de objetos con los scripts mover cursor de revisión arriba o abajo respectivamente. (#9551)
* NVDA ya no anuncia los mensajes "izquierda" y "derecha" al mover el cursor de revisión directamente al primer o último carácter del actual navegador de objetos con los scripts mover cursor de revisión a la izquierda o a la derecha respectivamente. (#9551)

### Corrección de Errores

* NVDA ahora arranca correctamente cuando el fichero de registro no se pueda crear. (#6330)
* En versiones recientes de Microsoft Word 365, NVDA ya no anunciará "borrar palabra atrás" cuando se pulse Control+Retroceso mientras se edita un documento. (#10851)
* En Winamp, NVDA anunciará de nuevo el estado de conmutación de aleatorio o de repetir. (#10945)
* NVDA ya no es extremadamente lento al moverte dentro de la lista de elementos en 1Password. (#10508)
* El sintetizador de voz Windows OneCore ya no tiene retraso entre las frases. (#10721)
* NVDA ya no se congela cuando abres el menú  de contexto para 1Password en el área de notificaciones del sistema. (#11017)
* En Office 2013 y anteriores:
  * Las cintas se anuncian cuando el foco se mueva a ellas por primera vez. (#4207)
  * Los elementos del menú de contexto se anuncian de nuevo apropiadamente. (#9252)
  * Las secciones de las cintas se anuncian consistentemente al navegar con Control+flechas. (#7067)
* En modo Exploración en Mozilla Firefox y Google Chrome, el texto ya  no aparece incorectamente en una línea separada cuando el contenido web utiliza en el CSS display: inline-flex. (#11075)
* En modo Exploración con el foco automático del sistema configurado a elementos enfocables desactivado, ahora es posible activar elementos que no sean enfocables.
* En modo Exploración con el foco automático del sistema configurado a elementos enfocables desactivado, ahora es posible activar elementos alcanzables pulsando la tecla tab. (#8528)
* En modo Exploración con el foco automático del sistema configurado a elementos enfocables desactivado, activar ciertos elementos ya no hace clic en un lugar incorrecto. (#9886)
* Los sonidos de error de NVDA ya no se escuchan cuando se acceda a controles de texto de DevExpress. (#10918)
* Los consejos de los iconos en la bandeja del sistema ya no se anuncian al navegar con el teclado si su texto es igual a su nombre, para evitar un anunciado duplicado. (#6656)
* En modo Exploración con el foco automático del sistema configurado a elementos enfocables desactivado, cambiar a modo Foco con NVDA+espacio ahora enfoca el elemento bajo el cursor. (#11206)
* De nuevo es posible buscar actualizaciones de NVDA en ciertos sistemas; ej.: instalaciones limpias de Windows. (#11253)
* El foco no se mueve en una aplicación Java cuando la selección se cambie en un árbol, tabla o lista no enfocable. (#5989)

### Cambios para Desarrolladores

* execElevated y hasUiAccess se han movido del módulo  config al módulo systemUtils. La utilización a través del módulo config es obsoleta. (#10493)
* Actualizado configobj a 5.1.0dev commit f9a265c4. (#10939)
* Ahora es posible la comprobación automatizada de NVDA con Chrome y un ejemplo HTML. (#10553)
* IAccessibleHandler se ha convertido en un paquete, OrderedWinEventLimiter se ha extraído a un módulo y se añadieron pruebas de unidad (#10934)
* Actualizado BrlApi a la versión 0.8 (BRLTTY 6.1). (#11065)
* La recuperación de la barra de estado ahora puede ser personalizada por un AppModule. (#2125, #4640)
* NVDA ya no escucha al IAccessible EVENT_OBJECT_REORDER. (#11076)
* Un ScriptableObject roto (tal como un GlobalPlugin que pierda una llamada a su clase base ' método init ) ya no rompe el manejo de scripts de NVDA. (#5446)

## 2020.1

Lo reseñable de esta versión incluye la admisión de varias nuevas pantallas braille de HumanWare y de APH, más muchas otras importantes correcciones de fallos tales como la capacidad de leer de nuevo matemáticas en Microsoft Word utilizando MathPlayer y MathType.

### Nuevas Características

* El elemento actualmente seleccionado en cuadros de lista se presenta nuevamente en modo exploración en Chrome, similar a NVDA 2019.1. (#10713)
* Ahora puedes realizar clics con el botón derecho del ratón en dispositivos táctiles haciendo un tap con un dedo y manteniéndolo. (#3886)
* Soporte para pantallas braille nuevas: APH Chameleon 20, APH Mantis Q40, HumanWare BrailleOne, BrailleNote Touch v2, y NLS eReader. (#10830)

### Cambios

* NVDA evitará que el sistema se bloquee o se suspenda cuando esté leyendo todo. (#10643)
* Soporte para iframes fuera de proceso en Mozilla Firefox. (#10707)
* Actualizado el transcriptor braille liblouis a la versión 3.12. (#10161)

### Corrección de Fallos

* Corregido el no anunciado del símbolo menos Unicode (U+2212) (#10633)
* Al instalar complementos desde el administrador de complementos los nombres de los ficheros y carpetas en la ventana de exploración ya no se anuncian dos veces. (#10620, #2395)
* En Firefox, al cargar Mastodon con la interfaz de web avanzada habilitada, ahora todas las cronologías se procesan correctamente en modo exploración. (#10776)
* En modo exploración, NVDA ahora anuncia "no marcado" para casillas de verificación no marcadas donde no lo hacía en ocasiones anteriormente. (#10781)
* Los controles ARIA switch ya no anuncian información confusa tal como "no pulsado marcado" o "pulsado marcado". (#9187)
* Las voces SAPI4 ya no deberían rechazar verbalizar cierto texto. (#10792)
* NVDA puede leer e interactuar de nuevo con ecuaciones matemáticas en Microsoft Word. (#10803)
* NVDA anunciará de nuevo el texto que se deselecione en modo exploración si se pulsa una flecha mientras el texto se selecciona. (#10731).
* NVDA ya no sale si hay un error inicializando eSpeak. (#10607)
* Los errores causados por unicode en traducciones para atajos ya no detienen el instalador, mitigados por la vuelta al texto en inglés. (#5166, #6326)
* El hecho de salir  de las listas y tablas en Leer todo con la lectura superficial habilitada ya no anuncia continuamente la salida de la lista o tabla. (#10706)
* Corregido el seguimiento del ratón para algunos elementos MSHTML en Internet Explorer. (#10736)

### Cambios para Desarrolladores

* Ahora se compila la documentación para el desarrollador usando sphinx. (#9840)
* Se han dividido en dos varias funciones del habla. (#10593)
  La versión speakX permanece, pero ahora depende de una función getXSpeech la cual devuelve una secuencia de voz.
  * speakObjectProperties ahora se basa en getObjectPropertiesSpeech
  * speakObject ahora se basa en getObjectSpeech
  * speakTextInfo ahora se basa en getTextInfoSpeech
  * speakWithoutPauses se ha convertido en una clase, y se ha refactorizado, pero no debería romper la retrocompatibilidad.
  * getSpeechForSpelling está obsoleta (aunque todavía disponible) utiliza getSpellingSpeech en su lugar.
  Cambios privados que no deberían afectar a los desarrolladores de complementos:
  * _speakPlaceholderIfEmpty ahora es _getPlaceholderSpeechIfTextEmpty
  * _speakTextInfo_addMath ahora es _extendSpeechSequence_addMathForTextInfo
* Speech 'reason' se ha convertido a un Enum, Consulta la clase controlTypes.OutputReason. (#10703)
  * Las constantes Module level 'REASON_*' están obsoletas.
* Las dependencias de compilación de NVDA ahora requieren Visual Studio 2019 (16.2 o más reciente). (#10169)
* Actualizado SCons a la versión 3.1.1. (#10169)
* De nuevo se permite a behaviors._FakeTableCell no tener una localización definida (#10864)

## 2019.3

NVDA 2019.3 es una versión muy significativa que contiene muchos cambios bajo el capó, incluyendo la actualización de Python 2 a Python 3, y una importante reescritura del sistema de habla de NVDA.
Aunque estos cambios rompan la compatibilidad con los antiguos complemenhtos de NVDA, la actualización a Python 3 es necesaria por motivos de seguridad, y los cambios en el habla permiten algunas innovaciones interesantes en un futuro próximo.
 Otros aspectos destacados en esta versión incluyen el soporte para 64 bits para Java VMs, las funcionalidades Cortina de Pantalla y Resaltado del Foco, admisión de más pantallas braille y un nuevo visor braille, y muchas otras correcciones de fallos.

### Nuevas Características

* La precisión de la orden mover el ratón al navegador de objetos se ha mejorado en campos de texto en aplicaciones Java. (#10157)
* Añadido el soporte para las siguientes pantallas braille Handy Tech (#8955):
 * Basic Braille Plus 40
 * Basic Braille Plus 32
 * Connect Braille
* Todos los gestos definidos por el usuario pueden ahora eliminarse mediante un nuevo botón "Restablecer los valores predeterminados de fábrica" en el cuadro de diálogo Gestos de entrada. (#10293)
* El anunciado de fuente en Microsoft Word ahora incluye si el texto se marca como oculto. (#8713)
* Añadida una orden para mover el cursor de revisión a la posición anteriormente ajustada como marca de comienzo de selección o copia: NVDA+shift+F9. (#1969)
* En Internet Explorer, Microsoft Edge y versiones recientes de Firefox y Chrome, las regiones ahora se anuncian en modo foco y en el navegador de objetos. (#10101)
* En Internet Explorer, Google Chrome y Mozilla Firefox, ahora puedes navegar por artículos y grupos utilizando los scripts de navegación rápida. Estos scripts no están vinculados por omisión y pueden asignarse en el diálogo Gestos de Entrada cuando el diálogo se abra desde un documento en modo exploración. (#9227)
 * Ahora se anuncian las figuras. Se consideran objetos y, por lo tanto, navegables con la tecla de navegación rápida o.
* En Internet Explorer, Google Chrome y Mozilla Firefox, ahora se anuncian los elementos artículo con el navegador de objeto, y opcionalmente, en modo Exploración si se activó en las opciones de Formateado de Documentos. (#10424)
* Se añadió una Cortina de Pantalla que, al activarse, hace que toda la pantalla se vuelva negra en Windows 8 y posteriores. (#7857)
 * Se agregó un script para habilitar la cortina de pantalla (hasta el siguiente reinicio con una sola pulsación, o siempre mientras NVDA esté en ejecución con dos pulsaciones), no se asigna ningún gesto predeterminado.
 * Puede habilitarse y configurarse a través de la categoría 'visión' en el diálogo opciones de NVDA.
* Añadida la funcionalidad Resaltado de pantalla a NVDA. (#971, #9064)
 * El resaltado del foco, del navegador de objetos y de la posición del cursor del modo Exploración pueden habilitarse y configurarse a través de la categoría 'visión' en el diálogo Opciones de NVDA.
 * Nota: esta característica es incompatible con el complemento focus highlight, sin embargo, el complemento todavía puede utilizarse mientras el resaltador incorporado esté deshabilitado.
* Añadida la herramienta Visualizador de Braille, que permite ver la salida braille a través de una ventana sobre la pantalla. (#7788)

### Cambios

* La Guía del Usuario ahora describe cómo utilizar NVDA en la consola de Windows. (#9957)
* La ejecución de nvda.exe ahora está predeterminada para reemplazar una copia ya en ejecución de NVDA. El parámetro de línea de órdenes -r|--replace todavía se acepta, pero se ignora. (#8320)
* En Windows 8 y posterior, NVDA ahora anunciará la información de nombre del producto y de versión para aplicaciones nativas tales como las aplicaciones descargadas de la Tienda de Microsoft utilizando información proporcionada por la aplicación. (#4259, #10108)
* Al activar y desactivar los cambios de seguimiento con el teclado de Microsoft Word, NVDA anunciará el estado de la configuración. (#942)
* El número de versión de NVDA ahora se registra como el primer mensaje en el registro. Esto ocurre incluso si se ha desactivado el registro desde la Interfaz Gráfica de Usuario. (#9803)
* El diálogo de opciones ya no permite cambiar el nivel del registro configurado si se ha substituido desde la línea de órdenes. (#10209)
* En Microsoft Word, NVDA ahora anuncia el estado de visualización de los caracteres no imprimibles al pulsar el atajo conmutable Ctrl+Shift+8. (#10241)
* Actualizado el transcriptor braille Liblouis a commit 58d67e63. (#10094)
* Cuando el anunciado de caracteres CLDR (incluyendo emojis) está activado, se anuncian en los niveles de toda la puntuación. (#8826)
* Los paquetes python de terceros incluídos en NVDA como comtypes, ahora registran sus advertencias y errores en el registro de NVDA. (#10393)
* Actualizado Unicode Common Locale Data Repository emoji annotations a la versión 36.0. (#10426)
* Al enfocar un grupo en el modo Exploración, ahora también se lee la descripción. (#10095)
* Ahora se incluye el Java Access Bridge con NVDA para permitir el acceso a aplicaciones Java, incluso para máquinas Java de 64 bits. (#7724)
* Si el Java Access Bridge no está habilitado para el usuario, NVDA lo habilita actomáticamente al arrancar. (#7952)
* Actualizado eSpeak-NG a 1.51-dev, commit ca65812ac6019926f2fbd7f12c92d7edd3701e0c. (#10581)

### Corrección de fallos

* Los Emoji y otros caracteres unicode de 32 bits ahora ocupan menos espacio en las pantallas braille cuando se muestran como valores hexadecimales. (#6695)
* En Windows 10, NVDA anunciará los consejos de las aplicaciones universales si NVDA se configuró para anunciar consejos en el diálogo Presentación de Objetos. (#8118)
* En Windows 10 version 1607 y posterior, ahora se anuncia el texto escrito en Mintty. (#1348)
* En Windows 10 version 1607 y posterior, la salida en la consola de Windows que aparezca cerca del cursor ya no se deletrea. (#513)
* Los controles en el diálogo compresor de Audacity ahora se anuncian al navegar por él. (#10103)
* NVDA ya no trata los espacios como palabras en revisión de objetos en editores basados en Scintilla tales como Notepad++. (#8295)
* NVDA evitará que el sistema entre en el modo durmiente al desplazarse por el texto con gestos de la pantalla braille. (#9175)
* En Windows 10, el braille ahora seguirá al editar contenido de celdas en Microsoft Excel y en otros controles de texto UIA donde se quedaba atrás. (#9749)
* NVDA volverá a anunciar las sugerencias en la barra de dirección de Microsoft Edge. (#7554)
* NVDA ya no se silencia cuando se enfoque un control de encabezado de pestaña HTML en Internet Explorer. (#8898)
* En Microsoft Edge basado en EdgeHTML, NVDA ya no reproducirá el sonido de sugerencia de búsqueda al maximizar la ventana. (#9110, #10002)
* Los cuadros combinados de ARIA 1.1 ahora se admiten en Mozilla Firefox y en Google Chrome. (#9616)
* NVDA ya no anunciará el contenido de las columnas visualmente oculto  para los elementos de lista en controles SysListView32. (#8268)
* El diálogo Opciones ya no muestra "info" como el nivel de registro actual cuando se esté en modo seguro. (#10209)
* En el menú Inicio de Windows 10 Anniversary Update y posterior, NVDA anunciará detalles de los resultados de la búsqueda. (#10232)
* En modo Exploración, si al mover el cursor o al utilizar la navegación rápida se produce un cambio en el documento, NVDA ya no verbaliza contenido incorrecto en algunos casos. (#8831, #10343)
* Se han corregido algunos nombres de viñetas en Microsoft Word. (#10399)
* En Windows 10 May 2019 Update y posteriores, NVDA anunciará otra vez el primer emoji o elemento del portapapeles seleccionado cuando se abra el panel de emojis y el historial del portapapeles respectivamente. (#9204)
* En Poedit, una vez más es posible ver algunas traducciones para los idiomas de derecha a izquierda. (#9931)
* En la aplicación de configuración de Windows 10 April 2018 Update y posteriores, NVDA ya no anunciará la información de las barras de progreso de los medidores de volumen que se encuentran en la página sistema/Sonido. (#10284)
* Las expresiones regulares inválidas en los diccionarios del habla ya no interrumpen completamente la voz en NVDA. (#10334)
* Cuando se leen elementos con viñetas en Microsoft Word con UIA activado, la viñeta del siguiente elemento de la lista ya no se anuncia de forma inapropiada. (#9613)
* Se han resuelto algunos problemas raros de transcripción braille y errores con liblouis. (#9982)
* Las aplicaciones Java iniciadas antes de NVDA ahora son accesibles sin la necesidad de iniciar la aplicación Java. (#10296)
* En Mozilla Firefox, cuando el elemento enfocado se marca como actual (aria-current), este cambio ya no se verbaliza varias veces. (#8960)
* NVDA ahora tratará a ciertos caracteres de composición unicode tales como e-acute como un solo carácter al moverse por el texto. (#10550)
* Ahora se admite Spring Tool Suite Versión 4. (#10001)
* No se pronuncia el nombre por duplicado cuando aria-labelledby relation target es un elemento interior. (#10552)
* En Windows 10 version 1607 y posterior, los caracteres escritos desde teclados Braille se verbalizan en más situaciones. (#10569)
* Al cambiar el dispositivo de salida de audio, los tonos reproducidos por NVDA ahora se reproducirán por el dispositivo recientemente seleccionado. (#2167)
* En Mozilla Firefox, mover el foco en modo Exploración es más rápido. Esto hace que mover el cursor en modo Exploración sea más ágil en muchos casos. (#10584)

### Cambios para Desarrolladores

* Actualizado Python a 3.7. (#7105)
* Actualizado pySerial a la versión 3.4. (#8815)
* Actualizado wxPython a 4.0.3 para soportar Python 3.5+ (#9630)
* Actualizado six a la versión 1.12.0 (#9630)
* Actualizado py2exe a la versión 0.9.3.2 (en desarrollo, commit b372a8e from albertosottile/py2exe#13). (#9856)
* Actualizado UIAutomationCore.dll módulo comtypes a la versión 10.0.18362. (#9829)
* El completado con tab en la consola de Python sólo sugiere atributos que comiencen con un guión bajo si el guión bajo se escribe primero. (#9918)
* La herramienta Flake8 se ha integrado con SCons para reflejar los requisitos del código para Pull Requests. (#5918)
* Como NVDA ya no depende de pyWin32, módulos tales como win32api y win32con ya no están disponibles para los complementos. (#9639)
 * las llamadas a win32api pueden reemplazarse con llamadas directas a funciones win32 dll a través de ctypes.
 * las constantes win32con deberían definirse en tus ficheros.
* El argumento "async" en nvwave.playWaveFile se ha renombrado a "asynchronous". (#8607)
* los métodos speakText y speakCharacter en objetos synthDriver ya no se admiten.
 * Esta funcionalidad se maneja con SynthDriver.speak.
* Las clases SynthSetting en synthDriverHandler se han eliminado. Ahora utiliza las clases driverHandler.DriverSetting en su lugar.
* Las clases SynthDriver ya no deberían exponer índices a través de la propiedad lastIndex.
 * En su lugar, deberían notificar  la acción synthDriverHandler.synthIndexReached con el índice, una vez que todo el audio anterior haya finalizado de reproducirse antes de ese índice.
* Las clases SynthDriver ahora deben notificar la acción synthDriverHandler.synthDoneSpeaking, una vez todo el audio de una llamada a SynthDriver.speak haya terminado de reproducirse.
* Las clases SynthDriver deben admitir speech.PitchCommand en su método speak, ya que los cambios en el tono de la verbalización del deletreo ahora dependen de esta funcionalidad.
* La función de habla getSpeechTextForProperties se ha renombrado a getPropertiesSpeech. (#10098)
* La función de braille getBrailleTextForProperties se ha renombrado a getPropertiesBraille. (#10469)
* Se han cambiado varias funciones del habla para devolver las secuencias de verbalización. (#10098)
 * getControlFieldSpeech
 * getFormatFieldSpeech
 * getSpeechTextForProperties llamada ahora getPropertiesSpeech
 * getIndentationSpeech
 * getTableInfoSpeech
* Añadido un módulo textUtils para simplificar las diferencias de cadena entre las cadenas de Python 3 y las cadenas de Windows unicode. (#9545)
 * Consulta la documentación del módulo y el módulo textInfos.offsets para ejemplos de implementaciones.
* Ahora se ha eliminado funcionalidad obsoleta. (#9548)
 * AppModules eliminados:
  * Windows XP sound recorder.
  * Klango Player, el cual es  un software abandonado.
 * configobj.validate wrapper eliminado.
  * Debería utilizarse el código nuevo configobj import validate en lugar de import validate
 * textInfos.Point y textInfos.Rect reemplazados por locationHelper.Point y locationHelper.RectLTRB respectivamente.
 * braille.BrailleHandler._get_tether y braille.BrailleHandler.set_tether se han eliminado.
 * config.getConfigDirs se ha eliminado.
 * config.ConfigManager.getConfigValidationParameter se ha reemplazado por getConfigValidation
 * la propiedad inputCore.InputGesture.logIdentifier se ha eliminado.
   * Utiliza _get_identifiers in inputCore.InputGesture en su lugar.
 * synthDriverHandler.SynthDriver.speakText/speakCharacter, se ha eliminado.
 * Eliminadas varias clases synthDriverHandler.SynthSetting.
   * Conservadas anteriormente para conpatibilidad con versiones anteriores (#8214), ahora se consideran obsoletas.
   * Los controladores que usen las clases SynthSetting deberían actualizarse para utilizar las clases DriverSetting.
 * Se ha eliminado algún código heredado, en particular:
  * Soporte para la lista de mensajes de Outlook pre 2003.
  * Una clase de superposición para el menú de Inicio clásico, que sólo se encuentra en Windows Vista y anteriores.
  * Quitada la compatibilidad para Skype 7, ya que definitivamente no funciona más.
* Un framework que permite a los desarrolladores crear proveedores de mejoras visuales; módulos que pueden cambiar el contenido de la pantalla, opcionalmente basados en la entrada de NVDA acerca de localizaciones de los objetos. (#9064)
 * Los complementos pueden abrupar sus propios proveedores en una carpeta visionEnhancementProviders.
 * Consulta los módulos vision y visionEnhancementProviders para la implementación del framework y ejemplos, respectivamente.
 * Los proporcionadores de mejoras de visión están habilitados y configurados a través de la categoría 'visión' en el diálogo opciones de NVDA.
* Las propiedades de la clase Abstract ahora se soportan en objetos que heredan de baseObject.AutoPropertyObject (ej.:. NVDAObjects y TextInfos). (#10102)
* Se introdujo displayModel.UNIT_DISPLAYCHUNK como una constante de unidad textInfos específica para DisplayModelTextInfo. (#10165)
 * Esta nueva constante permite andar sobre el texto en un DisplayModelTextInfo de modo que se asemeja más a cómo se guardan los trozos de texto en el modelo subyacente.
* displayModel.getCaretRect ahora devuelve una instancia de locationHelper.RectLTRB. (#10233)
* Las constantes UNIT_CONTROLFIELD y UNIT_FORMATFIELD se han movido desde virtualBuffers.VirtualBufferTextInfo al paquete textInfos. (#10396)
* Para cada entrada en el registro de NVDA, ahora se incluye información sobre el hilo original. (#10259)
* Los objetos UIA TextInfo ahora pueden moverse/expandirse por la página, histórico y unidades de texto formatField. (#10396)
* Los módulos externos (appModules y globalPlugins) ahora es menos probable que puedan romper la creación de NVDAObjects.
 * Las excepciones causadas por los métodos "chooseNVDAObjectOverlayClasses" y "event_NVDAObject_init" ahora son correctamente capturadas y registradas.
* El diccionario aria.htmlNodeNameToAriaLandmarkRoles se ha renombrado ahora como aria.htmlNodeNameToAriaRoles. También contiene roles que no son regiones.
* scriptHandler.isCurrentScript se ha eliminado debido a la falta de uso. No hay reemplazo. (#8677)

## 2019.2.1

Esta es una versión menor para corregir varios bloqueos presentes en 2019.2. Las correcciones incluyen:

* Se solucionaron varios problemas en Gmail que se observaron tanto en Firefox como en Chrome al interactuar con determinados menús emergentes tales como al crear filtros o al cambiar ciertas opciones de Gmail. (#10175, #9402, #8924)
* En Windows 7, NVDA ya no hace que el explorador de archivos de Windows se bloquee cuando se utilice el ratón en el menú Inicio. (#9435)
* El Explorador de Archivos de Windows en Windows 7 ya no se bloquea al acceder a los campos de edición de los metadatos. (#5337)
* NVDA ya no se cuelga al interactuar con imágenes con una URI en base 64 en Mozilla Firefox o en Google Chrome. (#10227)

## 2019.2

Lo reseñable de esta versión incluye la detección automática de pantallas braille de Freedom Scientific, una opción experimental en el panel Avanzado para detener el modo exploración desde el movimiento automático del foco (lo cual podría proporcionar mejoras de rendimiento), una opción de alzado brusco para el sintetizador Windows OneCore para lograr velocidades muy rápidas, y muchas otras correcciones de fallos.

### Nuevas Características

* El soporte de Miranda NG de NVDA funciona con las versiones más recientes del cliente. (#9053)
* Ahora puedes desactivar el modo exploración de forma predeterminada desactivando la nueva opción "Activar el modo exploración al cargar la página" en la configuración del modo exploración de NVDA. (#8716)
 * Ten en cuenta que cuando esta opción esté desactivada, todavía puedes activar el modo exploración manualmente pulsando NVDA+espacio.
* Ahora puedes filtrar símbolos en el cuadro de diálogo de pronunciación de signos de puntuación, de forma similar a como funciona el filtrado en la lista de elementos y en el cuadro de diálogo de gestos de entrada. (#5761)
* Se ha añadido una orden para cambiar la resolución de la unidad de texto del ratón (cuánto texto se verbalizará al moverse el ratón), no se le ha asignado un gesto predeterminado. (#9056)
* El sintetizador OneCore de Windows tiene ahora una opción de aumento de velocidad, que permite un habla significativamente más rápida. (#7498)
* La opción Alzado Brusco es ahora configurable desde el anillo de ajustes de sintetizador para sintetizadores de voz compatibles. (Actualmente eSpeak-NG y Windows OneCore). (#8934)
* Los perfiles de configuración ahora se pueden activar manualmente con gestos. (#4209)
 * El gesto se debe configurar en el cuadro de diálogo "Gestos de entrada".
* En Eclipse, se agregó soporte para el autocompletado en el editor de código. (#5667)
 * Además, la información Javadoc puede leerse desde el editor cuando está presente utilizando NVDA+d.
* Se agregó una opción experimental al panel de Configuración Avanzada que te permite detener el foco del sistema para que no siga al cursor del modo exploración (Poner automáticamente el foco del sistema en los elementos enfocables). (#2039) Aunque puede no ser adecuado desactivar esto en todos los sitios web, ello podría arreglar:
 * Efecto banda elástica: NVDA deshace esporádicamente la última pulsación de tecla del modo exploración saltando a la ubicación anterior.
 * Los cuadros de edición quitan el foco del sistema cuando se mueva a través de ellos en algunos sitios web.
 * Las pulsaciones de teclas del modo exploración son lentas de respuesta.
* Para los controladores de pantalla braille que lo admitan, ahora se pueden cambiar las opciones del controlador desde la categoría de opciones braille en el cuadro de diálogo de opciones de NVDA. (#7452)
* Ahora las pantallas braille de Freedom Scientific admiten la detección automática de pantallas braille. (#7727)
* Añadida una orden para mostrar el reemplazo del símbolo bajo el cursor de revisión. (#9286)
* Añadida una opción experimental al panel de Opciones avanzadas que te permite probar una nueva reescritura en curso del soporte de NVDA para la Consola de Windows utilizando la API Microsoft UI Automation. (#9614)
* En la Consola Python, el campo de entrada ahora admite el pegado de varias líneas desde el portapapeles. (#9776)

### Cambios

* El volumen del sintetizador aumenta y disminuye en 5 en lugar de en 10 cuando se utiliza el anillo de opciones. (#6754)
* Aclarado el texto en el administrador de complementos cuando se lanza NVDA con el indicador --disable-addons. (#9473)
* Actualizado Unicode Common Locale Data Repository anotaciones emoji a la versión 35.0. (#9445)
* En inglés, la tecla de acceso directo para el campo filtrar en la lista de elementos en modo exploración ha cambiado a alt+y. (#8728)
* Cuando una pantalla braille autodetectada se conecte a través de Bluetooth, NVDA seguirá buscando pantallas USB compatibles con el mismo controlador y cambiará a una conexión USB si está disponible. (#8853)
* Actualizado eSpeak-NG a commit 67324cc.
* Actualizado el transcriptor braille liblouis a la versión 3.10.0. (#9439, #9678)
* NVDA ahora anunciará la palabra 'seleccionado' después de anunciar el texto que un usuario acabe de seleccionar. (#9028, #9909))
* En Microsoft Visual Studio Code, NVDA está en modo Foco por defecto. (#9828)

### Corrección de Fallos

* NVDA ya no se bloquea cuando un directorio de complementos esté vacío. (#7686)
* Las marcas LTR y RTL ya no se anuncian en Braille o en voz por caracteres cuando se accede a la ventana de propiedades. (#8361)
* Cuando se salte a los campos de formulario con la navegación rápida del modo Exploración, ahora se anuncia todo el campo de formulario en lugar de sólo la primera línea. (#9388)
* NVDA ya no se silenciará después de salir de la aplicación Windows 10 Mail. (#9341)
* NVDA ya no falla al iniciarse cuando los ajustes regionales de los usuarios se establezcan en una ubicación desconocida para NVDA, como por ejemplo Inglés (Países Bajos). (#8726)
* Cuando el modo Exploración esté habilitado en Microsoft Excel y se cambie a un navegador en modo foco o viceversa, el estado del modo exploración ahora se notifica adecuadamente. (#8846)
* NVDA ahora anuncia correctamente la línea en el cursor del ratón en Notepad++ y otros editores basados en Scintilla. (#5450)
* En Google Docs (y otros editores basados en web), el braille ya no muestra a veces de forma incorrecta "lst end" antes del cursor en medio de un elemento de la lista. (#9477)
* En la actualización de Windows 10 de mayo de 2019, NVDA ya no verbaliza muchas notificaciones de volumen si se cambia el volumen con botones de hardware cuando el Explorador de archivos tenga el foco. (#9466)
* La carga del diálogo de pronunciación de signos de puntuación/símbolos es ahora mucho más rápida cuando se utilicen diccionarios de símbolos que contengan más de 1.000 entradas. (#8790)
* En los controles de Scintilla como Notepad++, NVDA puede leer la línea correcta cuando el ajuste de línea esté activado. (#9424)
* En Microsoft Excel, la ubicación de la celda se anuncia después de que cambie debido a los gestos shift+intro o shift+intro del teclado numérico. (#9499)
* Desde Visual Studio 2017 en adelante, en la ventana del Explorador de objetos, el elemento seleccionado en el árbol de objetos o en el árbol de miembros con categorías ahora se anuncia correctamente. (#9311)
* Los complementos con nombres que sólo difieran en las mayúsculas ya no se tratan como complementos separados. (#9334)
* En el caso de las voces de Windows OneCore, la velocidad establecida en NVDA ya no se ve afectada por la velocidad establecida en la configuración de voz de Windows 10. (#7498)
* El registro se puede abrir ahora con NVDA+F1 cuando no hay información del desarrollador para el objeto de navegador actual. (#8613)
* También es posible utilizar las órdenes de navegación de tabla de NVDA en Google Docs, en Firefox y en Chrome. (#9494)
* Las teclas frontales ahora funcionan correctamente en las pantallas braille de Freedom Scientific. (#8849)
* Al leer el primer carácter de un documento en Notepad++ 7.7 X64, NVDA ya no se congela durante un máximo de diez segundos. (#9609)
* HTCom ahora puede utilizarse con una pantalla braille Handy Tech en combinación con NVDA. (#9691)
* En Mozilla Firefox, las actualizaciones para una región activa ya no se anuncian si la región activa está en una pestaña en segundo plano. (#1318)
* El diálogo buscar del modo exploración de NVDA ya no deja de funcionar si el diálogo Acerca de... de NVDA está actualmente abierto en segundo plano. (#8566)

### Cambios para Desarrolladores

* Ahora puedes configurar la propiedad "disableBrowseModeByDefault" en los módulos de la aplicación para que deje el modo Exploración desactivado por defecto. (#8846)
* El estilo extendido de ventana de una ventana  ahora se expone utilizando la propiedad `extendedWindowStyle` en objetos ventana y sus derivados. (#9136)
* Actualizado el paquete comtypes a 1.1.7. (#9440, #8522)
* Al utilizar la orden report module info, el orden de la información se ha cambiado para presentar el módulo primero. (#7338)
* Añadido un ejemplo para demostrar el uso de nvdaControllerClient.dll desde C#. (#9600)
* Añadida una nueva función isWin10 al módulo winVersion que devuelve si esta copia de NVDA se está ejecutando en (al menos) la versión suministrada de Windows 10 (tal como la 1903). (#9761)
* La consola pytnon de NVDA ahora contiene módulos más útiles en su namespace (tales como appModules, globalPlugins, config y textInfos). (#9789)
* El resultado de la última orden ejecutada en la consola Python de NVDA ahora es accesible desde la variable _ (line). (#9782)
 * Ten en cuenta que esto oculta la función de traducción gettext también llamada "_". Para acceder a la función de traducción: del _

## 2019.1.1

Esta versión corrige los siguientes fallos:

* NVDA ya no hace que Excel 2007 se bloquee o se niegue a anunciar si una celda tiene una fórmula. (#9431)
* Google Chrome ya no se bloquea al interactuar con determinados cuadros de lista. (#9364)
* Se ha solucionado un problema que impedía copiar la configuración de un usuario en el perfil de configuración del sistema. (#9448)
* En Microsoft Excel, NVDA utiliza nuevamente el mensaje localizado cuando anuncia la ubicación de las celdas combinadas. (#9471)

## 2019.1

Lo reseñable de esta versión incluye la realización de mejoras al acceder a Microsoft word y a Excel, mejoras de estabilidad y de seguridad tales como la admisión de complementos con información de compatibilidad de versión, y muchas otras correcciones de fallos.

Por favor ten en cuenta que a partir de esta versión de NVDA, los módulos de aplicación, los Plugins globales, los controladores de pantallas braille y los controladores de sintetizador personales ya no se cargarán automáticamente desde tu directorio de configuración de usuario de NVDA.
En su lugar, estos deberían instalarse como parte de un complemento de NVDA. Para quienes desarrollen código para un complemento, el código para pruebas se puede colocar en un nuevo directorio scratchpad para desarrolladores en el directorio de configuración de usuarios de NVDA,  si la opción de desarrollador scratchpad está activada en el nuevo panel Opciones Avanzadas de NVDA.
Estos cambios son necesarios para garantizar una mejor compatibilidad del código personalizado, de modo que NVDA no se rompa cuando este código se vuelva incompatible con versiones más modernas.
Por favor, consulta la lista de cambios más abajo para obtener más detalles sobre esto y de cómo se versionan ahora mejor los complementos.

### Nuevas Características

* Nuevas tablas braille: Afrikaans, braille computerizado árabe de 8 puntos, árabe grado 2, español grado 2. (#4435)
* Añadida una opción a las opciones de ratón de NVDA para hacer que NVDA maneje situaciones en las que el ratón esté controlado por otra aplicación. (#8452)
 * Esto permitirá a NVDA rastrear el ratón cuando un sistema esté controlado remotamente utilizando TeamViewer u otros programas de control remoto.
* Añadido el parámetro de línea de órdenes `--enable-start-on-logon` para permitir configurar si las instalaciones silenciosas de NVDA configuran a NVDA para arrancar en la pantalla de inicio de Windows o no. Especifica true para arrancar en la pantalla de inicio o false para no arrancar en ella. Si el argumento --enable-start-on-logon no se especifica entonces NVDA se iniciará por defecto en la pantalla de inicio, a menos que ya estuviera configurado para no hacerlo en una instalación anterior. (#8574)
* Es posible desactivar las funciones de registro de NVDA configurando el nivel de registro a "deshabilitado" desde el panel de Opciones Generales. (#8516)
* Ahora se anuncia la presencia de fórmulas en las hojas de cálculo de LibreOffice y Apache OpenOffice. (#860)
* En Mozilla Firefox y Google Chrome, el modo exploración ahora anuncia el elemento seleccionado en cuadros de lista y en árboles.
 * Esto funciona en Firefox 66 y posterior.
 * Esto no funciona para ciertos cuadros de lista (controles HTML select) en Chrome.
* Soporte preliminar para aplicaciones tales como Mozilla Firefox en ordenadores con procesadores ARM64 (por ej.: Qualcom Snapdragon). (#9216)
* Se ha añadido una nueva categoría Opciones Avanzadas al diálogo de opciones de NVDA, incluyendo una opción para probar el nuevo soporte de NVDA para Microsoft Word a través de la API de Microsoft UI Automation. (#9200)
* Añadido el soporte para la vista gráfica en el Administrador de Discos de Windows. (#1486)
* Añadido el soporte de Handy Tech Connect Braille y Basic Braille 84. (#9249)

### Cambios

* Actualizado el transcriptor braille liblouis a la versión 3.8.0. (#9013)
* Los autores de complementos ahora pueden hacer cumplir una versión mínima requerida de NVDA para sus complementos. NVDA se negará a instalar o cargar un complemento cuya versión mínima requerida de NVDA sea superior a la versión actual de NVDA. (#6275)
* Los autores de los complementos pueden ahora especificar la última versión de NVDA con la que se ha probado el complemento. Si un complemento sólo se ha probado con una versión de NVDA inferior a la versión actual, NVDA se negará a instalarlo o a cargarlo. (#6275)
* Esta versión de NVDA permitirá la instalación y carga de complementos que aún no contengan información sobre la versión mínima y la última probada de NVDA, pero la actualización a futuras versiones de NVDA (por ejemplo, 2019.2) puede provocar que estos complementos más antiguos se desactiven automáticamente.
* La orden mover el ratón al navegador de objetos ahora está disponible tanto en Microsoft Word como en controles UIA, especialmente en Microsoft Edge. (#7916, #8371)
* Se ha mejorado el anunciado de texto bajo el ratón dentro de Microsoft Edge y otras aplicaciones UIA. (#8370)
* Cuando se inicia NVDA con el parámetro de línea de órdenes `--portable-path`, la ruta proporcionada se rellena automáticamente cuando se intenta crear una copia portable de NVDA utilizando el menú NVDA. (#8623)
* Actualizada la ruta a la tabla braille noruega para reflejar el estándar a partir del año 2015. (#9170)
* Cuando se navega por párrafos (control+flechas) o se navega por celdas de tabla (control+alt+flechas), la existencia de errores de ortografía ya no se anunciará, incluso si NVDA está configurado para anunciarlos automáticamente. Esto es porque los párrafos y las celdas de tabla pueden ser bastante grandes, y calcular los errores de ortografía en algunas aplicaciones puede ser muy costoso. (#9217)
* NVDA ya no carga automáticamente appModules, globalPlugins y controladores braille y de sintetizador desde el directorio de configuración de usuario de NVDA. Este código debería ser empaquetado en su lugar como un complemento con información correcta de versión, asegurándose de que el código incompatible no sea ejecutado con las versiones actuales de NVDA. (#9238)
 * Para los desarrolladores que necesiten probar el código según se desarrolla, se habilita el directorio developer scratchpad de NVDA en la categoría Avanzado de las opciones de NVDA, y colocar el código en el directorio 'scratchpad' encontrado en el directorio de configuración del usuario cuando esta opción esté habilitada.

### Corrección de Fallos

* Cuando se utiliza el sintetizador de voz OneCore en Windows 10 de Abril de 2018 y posteriores, ya no se insertan grandes trozos de silencio entre las expresiones orales. (#8985)
* Cuando te muevas por caracteres en controles de texto plano (tales como Notepad) o en modo exploración, los caracteres emoji de 32 bits que consistan en dos puntos de código UTF-16 (tales como ðŸ¤¦) ahora se leerán apropiadamente. (#8782)
* Mejorado el diálogo de confirmación de reinicio después de cambiar el idioma de la interfaz. El texto y las etiquetas de los botones son ahora más concisos y menos confusos. (#6416)
* Si un sintetizador de voz de terceros no se carga, NVDA recurrirá a Windows OneCore en Windows 10, en lugar de espeak. (#9025)
* Eliminada la entrada "Diálogo de bienvenida" en el menú de NVDA en las pantallas seguras.
* Al tabular o al utilizar la navegación rápida en el modo de navegación, las leyendas en los paneles de pestañas se informan ahora de forma más coherente. (#709)
* NVDA anunciará ahora los cambios de selección para determinados selectores de tiempo tales como en las Alarmas y en la aplicación Reloj. (#5231)
* En el Centro de actividades de Windows 10, NVDA anunciará mensajes de estado al alternar entre acciones rápidas como el brillo y el enfoque. (#8954)
* En el centro de actividades en Windows 10 actualización Octubre de 2018 y versiones anteriores, NVDA reconocerá el control de brillo de acción rápida como un botón en lugar de como un botón conmutable. (#8845)
* NVDA volverá a rastrear el cursor y anunciará los caracteres eliminados en Microsoft Excel y buscará los campos de edición. (#9042)
* Corregido un fallo raro en el modo de navegación en Firefox. (#9152)
* NVDA ya no falla al anunciar el enfoque de algunos controles en la cinta de Microsoft Office 2016 cuando está contraída.
* NVDA ya no falla al anunciar el contacto sugerido al introducir direcciones en los nuevos mensajes de Outlook 2016. (#8502)
* Las últimas teclas de enrutamiento del cursor en las pantallas eurobraille de 80 celdas ya no dirigen el cursor a una posición en o justo después del inicio de la línea braille. (#9160)
* Corregida la navegación de tablas en la vista en hilo de Mozilla Thunderbird. (#8396)
* En Mozilla Firefox y Google Chrome, cambiar al modo foco ahora funciona correctamente para ciertos cuadros de lista y árboles (donde el cuadro de lista o árbol no es en sí mismo enfocable pero sus elementos sí lo son). (#3573, #9157)
* El modo Exploración está ahora correctamente activado de forma predeterminada cuando se leen mensajes en Outlook 2016/365 si se utiliza la compatibilidad con el soporte experimental de UI Automation de NVDA para documentos de Word. (#9188)
* Ahora es menos probable que NVDA se congele de tal manera que la única forma de escapar sea cerrar la sesión actual de Windows. (#6291)
* En Windows 10 actualización October 2018 y versiones posteriores, al abrir el historial del portapapeles de la nube con el portapapeles vacío, NVDA anunciará el estado del portapapeles. (#9112)
* En Windows 10 actualización October 2018 y posteriores, al buscar emojis en el panel emoji, NVDA anunciará el mejor resultado de la búsqueda. (#9112)
* NVDA ya no se congela en la ventana principal de Virtualbox 5.2 y superiores. (#9202)
* La respuesta en Microsoft Word al navegar por líneas, párrafos o celdas de tabla puede mejorarse significativamente en algunos documentos. Se recuerda que para un mejor rendimiento, se establecerá la vista Borrador en Microsoft Word con alt+w,e después de abrir un documento. (#9217)
* En Mozilla Firefox y Google Chrome, las alertas vacías ya no se notifican. (#5657)
* Mejoras significativas en el rendimiento al navegar por las celdas de Microsoft Excel, especialmente cuando la hoja de cálculo contenga comentarios y/o listas desplegables de validación. (#7348)
* Ya no debería ser necesario desactivar la edición en la celda en las opciones de Microsoft Excel para acceder al control de edición de celdas con NVDA en Excel 2016/365. (#8146).
* Corregido un cuelgue en Firefox visto a veces al navegar por regiones, si está en uso el complemento Enhanced Aria. (#8980)

### Cambios para Desarrolladores

* NVDA ahora puede compilarse con todas las ediciones de Microsoft Visual Studio 2017 (no sólo con la edición Community). (#8939)
* Ahora puedes incluir la salida del registro de liblouis en el registro de NVDA configurando la bandera booleana louis en la sección debugLogging de la configuración de NVDA. (#4554)
* Los autores de complementos ahora pueden proporcionar información sobre la compatibilidad de las versiones de NVDA en los manifests de los complementos. (#6275, #9055)
 * minimumNVDAVersion: La versión mínima requerida de NVDA para que un complemento funcione apropiadamente.
 * lastTestedNVDAVersion: La última versión de NVDA con la que ha sido probado un complemento.
* OffsetsTextInfo ahora puede implementar el método _getBoundingRectFromOffset para permitir la recuperación de rectángulos delimitadores por caracteres en lugar de puntos. (#8572)
* Añadida una propiedad boundingRect a los objetos TextInfo para recuperar el rectángulo delimitador de un rango de texto. (#8371)
* Las propiedades y métodos dentro de las clases ahora pueden ser marcadas como abstractas en NVDA. Estas clases generarán un error si se instancian. (#8294, #8652, #8658)
* NVDA puede registrar el tiempo transcurrido desde que se introdujo el texto, lo que ayuda a medir la capacidad de respuesta percibida. Esto puede activarse configurando la opción timeSinceInput como True en la sección debugLog de la configuración de NVDA. (#9167)

## 2018.4.1

Esta versión corrige un cuelgue al arrancar si el idioma de interfaz de usuario de NVDA se configuró como Aragonés. (#9089)

## 2018.4

Lo más destacado de esta versión incluye las mejoras en el rendimiento de las últimas versiones de Mozilla Firefox, el anunciado de emojis con todos los sintetizadores, el anunciado de las respuestas y envíos en Outlook, la información de la distancia del cursor al borde de una página de Microsoft Word y muchas correcciones de fallos.

### Nuevas Características

* Nuevas tablas braille: Chino (China, Mandarín) grado 1 y grado 2. (#5553)
* Ahora se anuncian los estados Respondido / Reenviado en elementos de correo en la lista de mensajes de Microsoft Outlook. (#6911)
* NVDA ahora puede leer descripciones para emoji así como otros caracteres que son parte del repositorio Unicode Common Locale Data. (#6523)
* En Microsoft Word, la distancia del cursor desde los márgenes superior e izquierdo de la página puede anunciarse  pulsando NVDA+suprimir del teclado numérico. (#1939)
* En Google Sheets con el modo braille habilitado, NVDA ya no anuncia 'seleccionado' en cada celda al mover el foco entre ellas. (#8879)
* Añadido el soporte para Foxit Reader y para Foxit Phantom PDF (#8944)
* Añadido el soporte para la utilidad de base de datos DBeaver. (#8905)

### Cambios

* "Anunciar globos de ayuda" en el diálogo Presentación de Objetos se ha renombrado como "Anunciar notificaciones" para incluir el anunciado de notificaciones del sistema en Windows 8 y posteriores. (#5789)
* EN las opciones de teclado de NVDA, las casillas de verificación para activar o desactivar las teclas modificadoras de NVDA ahora se muestran en una lista en lugar de en casillas de verificación separadas.
* NVDA ya no presenta información redundante al leer el reloj de la bandeja del sistema en algunas versiones de Windows. (#4364)
* Actualizado el transcriptor braille liblouis a la versión 3.7.0. (#8697)
* Actualizado eSpeak-NG a commit 919f3240cbb.

### Corrección de Errores

* En Outlook 2016 y 365, se anuncian la categoría y el estado de la marca para los mensajes. (#8603)
* Cuando NVDA se configure para idiomas tales como Kirgyz, Mogol o Macedonio, ya no muestra un diálogo en un aviso al arrancar que el idioma no se admite por el sistema operativo. (#8064)
* Al mover el ratón al navegador de objetos ahora será mucho más preciso mover el ratón a la posición del modo exploración en Mozilla Firefox, Google Chrome y Acrobat Reader DC. (#6460)
* Se ha mejorado interactuar con cuadros combinados en la web en Firefox, Chrome e Internet Explorer. (#8664)
* Si se ejecuta en la versión japonesa de Windows XP o Vista, NVDA ahora muestra la alerta de los requisitos de la versión del Sistema Operativo según se esperaba. (#8771)
* Se aumenta el rendimiento en Mozilla Firefox al navegar por páginas grandes con muchos cambios dinámicos. (#8678)
* El braille ya no muestra atributos de fuente si se deshabilitaron en  las opciones Formateado de documento. (#7615)
* NVDA ya no falla al seguir al foco en el Explorador de Archivos y otras aplicaciones que utilicen UI Automation cuando otra aplicación esté ocupada (tal como el procesamiento por lotes del audio). (#7345)
* En los menús ARIA en la web, la tecla Escape ahora se pasará a través del menú y ya no desactivará el modo foco incondicionalmente. (#3215)
* En la interfaz nueva de Gmail, al utilizar la navegación rápida dentro de mensajes mientras se leen, ya no se anuncia todo el cuerpo del mensaje después del elemento al que acabas de navegar. (#8887)
* Después de actualizar NVDA, navegadores tales como Firefox y google Chrome ya no deberían romperse, y el modo exploración debería seguir reflejando correctamente las actualizaciones de cualquier documento cargado actualmente. (#7641)
* NVDA ya no informa de que se puede hacer clic varias veces en una fila al navegar por contenido cliqueable en Modo Exploración. (#7430)
* Los gestos realizados en pantallas braille baum Vario 40 ya no fallarán al ejecutarse. (#8894)
* En Google Slides con Mozilla Firefox, NVDA ya no anuncia el texto seleccionado en cada control con el foco. (#8964)

### Cambios para Desarrolladores

* gui.nvdaControls ahora contiene dos clases para crear listas accesibles con casillas de verificación. (#7325)
 * CustomCheckListBox es una sub-clase accesible de wx.CheckListBox.
 * AutoWidthColumnCheckListCtrl añade casillas de verificación accesibles a un AutoWidthColumnListCtrl, el cual está basado en si mísmo en wx.ListCtrl.
* Si necesitas hacer un wx widget accesible que no lo es todavía, es posible hacerlo utilizando una instancia de gui.accPropServer.IAccPropServer_impl. (#7491)
 * Consulta la implementación de gui.nvdaControls.ListCtrlAccPropServer para más información.
* Actualizado configobj a 5.1.0dev commit 5b5de48a. (#4470)
* La acción config.post_configProfileSwitch ahora toma el argumento opcional prevConf keyword, permitiendo a los manejadores tomar una acción basada en diferencias entre la configuración antes y después del cambio de perfil. (#8758)

## 2018.3.2

Esta es una versión menor para evitar un cuelgue en Google Chrome al navegar por tuits en [www.twitter.com](http://www.twitter.com). (#8777)

## 2018.3.1

Esta es una versión menor para corregir un error crítico en NVDA que causaba que las versiones de 32 bits de Mozilla Firefox se colgasen. (#8759)

## 2018.3

Lo subrayable de esta versión incluye la detección automática de muchas pantallas Braille, la admisión para algunas características nuevas de Windows 10 incluyendo el panel de entrada de emojis de Windows 10, y muchas otras correcciones de fallos.

### Nuevas Características

* NVDA anunciará errores de gramática cuando se expongan apropiadamente por las páginas web en Mozilla Firefox y Google Chrome. (#8280)
* El contenido que se marca como siendo borrado o insertado en páginas web ahora se anuncia en Google Chrome. (#8558)
* Añadida la compatibilidad para las ruedas de desplazamiento de BrailleNote QT y Apex BT cuando se utilice BrailleNote como una pantalla braille con NVDA. (#6316)
* Añadidos scripts para anunciar el tiempo transcurrido y el tiempo total de la pista actual en Foobar2000. (#6596)
* El símbolo de la tecla Command del Mac (⌘) ahora se anuncia al leer texto con cualquier sintetizador. (#8366)
* Los roles personalizados a través del atributo aria-roledescription attribute ahora se admiten en Firefox, Chrome e Internet Explorer.
* Nuevas tablas braille: braille sueco computerizado de 8 puntos, Curdo central, Esperanto, Húngaro, checo. (#8226, #8437)
* Se ha añadido el soporte para la detección automática de pantallas braille en segundo plano. (#1271)
 * Se admiten actualmente las pantallas ALVA, Baum/HumanWare/APH/Orbit, Eurobraille, Handy Tech, Hims, SuperBraille y HumanWare BrailleNote y Brailliant BI/B.
 * Puedes habilitar esta característica seleccionando la opción automático desde la lista de pantallas braille en el diálogo seleccionar pantalla braille de NVDA.
 * Por favor consulta la documentación para detalles adicionales.
* Se añadió el soporte para varias características de entrada modernas introducidas en versiones recientes de Windows 10. Estas incluyen el panel de emoji (Fall Creators Update), dictado (Fall Creators Update), sugerencias de entrada del teclado hardware (April 2018 Update), y pegar en el portapapeles en la nube (October 2018 Update). (#7273)
* El contenido marcado como un bloque de cita utilizando ARIA (role blockquote) ahora se admite en Mozilla Firefox 63. (#8577)

### Cambios

* La lista de idiomas disponibles en el diálogo opciones Generales ahora se ordena basándose en los nombres de los idiomas en lugar de en los códigos ISO 639. (#7284)
* Añadidos gestos predeterminados para alt shift tab y windows tab con todas las pantallas braille compatibles de Freedom Scientific. (#7387)
* Para la ALVA BC680 y pantallas con conversor de protocolo, ahora es posible assignar funciones diferentes a los smart pad izquierdo y derecho, al thumb y a las teclas etouch. (#8230)
* Para las pantallas ALVA BC6, la combinación de teclas sp2+sp3 ahora anunciará la hora y la fecha actuales, mientras que sp1+sp2 emula la tecla Windows. (#8230)
* Ahora se le pregunta al usuario una vez en el arranque de NVDA si están de acuerdo enviando estadísticas de uso a NV Access cuando se busquen actualizaciones automáticamente. (#8217)
* Al buscar actualizaciones, si el usuario está de acuerdo al permitir el envío de estadísticas de uso a NV Access, NVDA ahora enviará el nombre del controlador del sintetizador actual y de la pantalla braille en uso, para ayudar a establecer un mejor orden de prioridades para el trabajo futuro de estos controladores. (#8217)
* Actualizado el transcriptor braille liblouis a la versión 3.6.0. (#8365)
* Actualizada la ruta a la tabla braille rusa de 8 puntos correcta. (#8446)
* Actualizado eSpeak-ng a 1.49.3dev commit 910f4c2 (#8561)

### Corrección de Errores

* Las etiquetas accesibles para controles en Google Chrome ahora se anuncian más legiblemente en modo exploración cuando la etiqueta no aparece como contenido en sí. (#4773)
* Ahora se soportan las notificaciones en Zoom. Por ejemplo, esto incluye silenciar/desilenciar estado, y los mensajes entrantes. (#7754)
* Cambiar la presentación del contexto braille cuando se esté en modo exploración ya no causa que la salida braille deje de seguir. (#7741)
* Las pantallas braille ALVA BC680 ya no fallan intermitentemente al inicializarse. (#8106)
* Por defecto, las pantallas ALVA BC6 ya no ejecutarán teclas emuladas del sistema al pulsar combinaciones de teclas que tengan que ver con sp2+sp3 para disparar funcionalidades internas. (#8230)
* Al pulsar sp2 en una pantalla ALVA BC6 para emular la tecla alt ahora funciona tal como se anuncia. (#8360)
* NVDA ya no anuncia cambios redundantes de la distribución de teclado. (#7383, #8419)
* El seguimiento del ratón ahora es mucho más preciso en el Bloc de notas y en otros controles de edición de texto sin formato cuando se encuentre en un documento con más de 65535 caracteres. (#8397)
* NVDA reconocerá más diálogos en Windows 10 y otras aplicaciones modernas. (#8405)
* En la actualización de octubre de 2018 de Windows 10 y de Server 2019 y posterior, NVDA ya no falla al seguir al foco del sistema cuando una aplicación se congela o inunda al sistema con eventos. (#7345, #8535)
* Ahora se informa a los usuarios cuando intenten leer o copiar una barra de estado vacía. (#7789)
* Corregido un caso donde el estado "no marcado" en controles no se anuncia en voz si el control ha sido parcialmente marcado anteriormente. (#6946)
* En la lista de idiomas en las opciones generales de NVDA, el nombre para el idioma birmano se muestra correctamente en Windows 7. (#8544)
* En Microsoft Edge, NVDA anunciará notificaciones tales como leer la disponibilidad de la vista y el progreso de la carga de la página. (#8423)
* Al navegar por una lista en la web, NVDA ahora anunciará su etiqueta si el autor de la misma ha proporcionado una. (#7652)
* Cuando se asignan manualmente funciones a gestos para una pantalla braille en particular, estos gestos ahora siempre aparecen como asignados a esa pantalla. Anteriormente, se mostraban como si estuviesen asignados a la pantalla activa en ese momento. (#8108)
* Ahora se admite la versión de 64 bits del Media Player Classic. (#6066)
* Varias mejoras al soporte braille en Microsoft Word con UI Automation habilitado:
 * De forma similar a otros campos de texto multilínea, cuando se coloque al comienzo de un documento en Braille, la pantalla ahora se desplaza de tal forma que el primer carácter del documento se encuentre al principio de la pantalla. (#8406)
 * Reducción de la presentación demasiado verbosa del foco tanto en voz como en braille cuando se enfoque un documento Word. (#8407)
 * El enrutamiento del cursor en braille ahora funciona correctamente cuando se está en una lista en un documento de Word. (#7971)
 * Las viñetas/números recién insertados en un documento Word se anuncian correctamente tanto en voz como en braille. (#7970)
* En Windows 10 1803 y posteriores, ahora es posible instalar complementos si está activada la característica "Utilizar Unicode UTF-8 para el soporte de idioma en todo el mundo". (#8599)
* NVDA ya no hará completamente inusable a iTunes 12.9 y posteriores para interactuar. (#8744)

### Cambios para Desarrolladores

* Añadido scriptHandler.script, el cual puede funcionar como un decorador para scripts en objetos escriptables. (#6266)
* Se ha introducido un framework de sistema de pruebas para NVDA. (#708)
* Se han realizado algunos cambios en el módulo hwPortUtils: (#1271)
 * listUsbDevices ahora genera diccionarios con información de dispositivo incluyendo hardwareID y devicePath.
 * Los diccionarios generados por listComPorts ahora también contienen una entrada usbID para puertos COM con información USB VID/PID en su ID de hardware.
* Actualizado wxPython a 4.0.3. (#7077)
* Dado que NVDA ahora solo es compatible con Windows 7 SP1 y posterior, se ha eliminado la clave "minWindowsVersion" utilizada para comprobar si UIA debería habilitarse para una versión en particular de Windows. (#8422)
* Ahora puedes registrar para que se te notifique acerca de acciones de guardar/reiniciar la configuración a través de las nuevas acciones config.pre_configSave, config.post_configSave, config.pre_configReset, y config.post_configReset. (#7598)
 * config.pre_configSave se utiliza para que se te notifique cuando la configuración de NVDA está a punto de guardarse, y config.post_configSave se llama después de que la configuración se haya guardado.
 * config.pre_configReset y config.post_configReset incluye un indicador de valores predeterminados  de fábrica para especificar si las opciones se recargan desde el disco (false) o se reestablecen a los valores predeterminados (true).
* config.configProfileSwitch se ha renombrado a config.post_configProfileSwitch para reflejar el hecho de que esta acción se llama después de que el cambio de perfil tenga lugar. (#7598)
* Interfaces de UI Automation actualizadas a Windows 10 October 2018 Update y Server 2019 (IUIAutomation6 / IUIAutomationElement9). (#8473)

## 2018.2.1

Esta versión incluye actualizaciones de traducciones debido a la eliminación de última hora de una característica que causó problemas.

## 2018.2

Lo reseñable de esta versión incluye el soporte para tablas en Kindle para PC, el soporte para pantallas Humanware BrailleNote Touch y BI14 Braille, mejoras para sintetizadores de voz Onecore y Sapi5, mejoras en Microsoft Outlook y mucho más.

### Nuevas Características

* ahora se anuncia el rango de filas y columnas para celdas de tablas  en voz y braille. (#2642)
* Ahora se soportan las órdenes de navegación de táblas de NVDA en Google Docs (con el modo Braille habilitado). (#7946)
* Capacidad para leer y navegar tablas en Kindle for PC. (#7977)
* Soporte para las pantallas BrailleNote touch y Brailliant BI 14 a través tanto de USB como de bluetooth. (#6524)
* En Windows 10 Fall Creators Update y posteriores, NVDA puede anunciar notificaciones desde aplicaciones tales como Calculadora y Windows Store. (#8045)
* Nuevas tablas de transcripcción braille: Lithuano 8 puntos, ucraniano, Mongol grado 2. (#7839)
* Añadido un script para anunciar información de formato para el texto bajo una celda braille específica. (#7106)
* Nuevos idiomas: Mongol, Alemán de Suiza.
* Al actualizar NVDA, ahora es posible posponer la instalación de la actualización a un momento posterior de tu elección. (#4263)
* Ahora puedes conmutar control, shift, alt, windows y NVDA desde tu teclado braille y combinar estos modificadores con la entrada braille (ej.: pulsar control+s). (#7306)
 * Puedes asignar estas nuevas conmutaciones de modificadores utilizando la orden que se encuentra en Teclas de sistema emuladas en el diálogo Gestos de Entrada.
* Restaurado el soporte para pantallas Handy Tech Braillino y Modular (con  el firmware antiguo). (#8016)
* Ahora se sincronizarán automáticamente con NVDA la fecha y la hora para los dispositivos Handy Tech soportados (tal como Active Braille y Active Star) cuando estén desincronizados más de cinco segundos. (#8016)
* Se puede asignar un gesto de entrada para deshabilitar temporalmente todos los disparadores de un perfil de configuración. (#4935)

### Cambios

* Se ha cambiado la columna de estado en el administrador de complementos para indicar si el complemento está habilitado o deshabilitado además de en ejecución o suspendido. (#7929)
* Actualizado el transcriptor braille liblouis a 3.5.0. (#7839)
* La tabla braille lituana se ha renombrado a Lituano 6 puntos para evitar confusiones con la nueva tabla de 8 puntos. (#7839)
* Las tablas Francés (Canadá) grado 1 y grado 2 se han eliminado. En su lugar, se utilizarán las tablas Francés (unificado) 6 puntos y Grado 2 respectivamente. (#7839)
* Los sensores secundarios de las pantallas braille Alva BC6, EuroBraille y Papenmeier ahora anuncian información de formato para el texto bajo la celda braille de ese sensor. (#7106)
* Las tablas de entrada de braille contraído volverán automáticamente a modo no contraído  en casos no editables (es decir, controles donde no haya cursor o en modo exploración). (#7306)
* NVDA ahora habla menos en el calendario de Outlook cuando una cita o una franja temporal cubre un día entero. (#7949)
* Ahora se pueden encontrar todas las preferencias de NVDA en un único diálogo de opciones en el menú NVDA -> Preferencias -> Opciones, en lugar de dispersarse en muchos diálogos. (#7302)
* El sintetizador de voz predeterminado al ejecutarse en Windows 10 ahora es oneCore en lugar de eSpeak. (#8176)

### Corrección de fallos

* NVDA ya no falla al leer controles enfocados en la pantalla de inicio de sesión de la cuenta de Microsoft en Configuración después de introducir una dirección de correo. (#7997)
* NVDA ya no falla al leer la página cuando se retrocede a una página anterior en Microsoft Edge. (#7997)
* NVDA ya no anunciará incorrectamente el carácter final de un PIN de inicio de sesión de windows 10 según la máquina se desbloquee. (#7908)
* Las etiquetas de las casillas de verificación y de los botones de opción en Chrome y Firefox ya no se anuncian dos veces cuando se tabule o se utilice la navegación rápida en modo exploración. (#7960)
* se maneja aria-current con un valor de false como false en lugar de true (#7892).
* El controlador del sintetizador Windows Onecore Voices ya no falla al cargar si la voz configurada se ha desinstalado. (#7999)
* Cambiar voces en el controlador del sintetizador Windows Onecore Voices ahora es mucho más rápido. (#7999)
* Corregida la malformación de la salida braille para varias tablas braille, incluyendo signos en mayúsculas en el braille danés contraído de 8 puntos. (#7526, #7693)
* NVDA ahora puede anunciar más tipos de viñetas en Microsoft Word. (#6778)
* Al pulsar el script anunciar información ya no mueve incorrectamente la posición de revisión y por lo tanto al pulsarlo varias veces ya no da resultados diferentes. (#7869)
* La entrada braille ya no te permitirá utilizar braille contraído en casos donde no esté soportado (es decir, ya no se enviarán palabras enteras al sistema fuera del contenido de texto y en modo exploración). (#7306)
* Corregidos problemas de estabilidad de conexión para las pantallas braille Handy Tech Easy Braille y Braille Wave. (#8016)
* En Windows 8 y posterior, NVDA ya no anunciará "desconocido" al abrir el menú rápido de enlaces (Windows+X) y al seleccionar elementos de este menú. (#8137)
* Los gestos específicos del modelo para botones en las pantallas Hims ahora funcionan tal y como se anuncia en la Guía del Usuario. (#8096)
* NVDA intentará ahora corregir los problemas de registro COM del sistema que causan que programas como Firefox e Internet Explorer se vuelvan inaccesibles y anuncien "Desconocido" por NVDA. (#2807).
* Se trabajó en la solución de un fallo en el administrador de tareas haciendo que NVDA no permita a los usuarios acceder a los contenidos de detalles específicos sobre los procesos. (#8147)
* Las voces más nuevas de Microsoft SAPI5 ya no retrasan al final de la verbalización, lo que hace que sea mucho más eficiente navegar con estas voces. (#8174)
* NVDA ya no anuncia (marcas LTR y  RTL) en Braille o en la verbalización por caracteres al acceder al reloj en versiones recientes de Windows. (#5729)
* La detección de las teclas de desplazamiento en pantallas Hims Smart Beetle ya no es poco fiable. (#6086)
* En algunos controles de texto, particularmente en aplicaciones Delphi, la información proporcionada en la edición y en la navegación ahora es mucho más fiable. (#636, #8102)
* En Windows 10 RS5, NVDA ya no anuncia información extra redundante al cambiar tareas con alt+tab. (#8258)

### Cambios para Desarrolladores

* La información para desarrolladores para objetos UIA ahora contiene una lista de los patrones UIA disponibles. (#5712)
* Los módulos de aplicación ahora pueden forzar ciertas ventanas para utilizar siempre UIA implementando el método isGoodUIAWindow. (#7961)
* La bandera booleana oculta "outputPass1Only" en la sección braille de la configuración se ha eliminado de nuevo. Liblouis ya no soporta pasar 1 solo en la salida. (#7839)

## 2018.1.1

Esta es una versión especial de NVDA que soluciona un problema en el controlador del sintetizador Onecore Windows Speech, que causaba que hablase con un tono y velocidad más altos en Windows 10 Redstone 4 (1803). (#8082)

## 2018.1

Lo reseñable de esta versión incluye el soporte para gráficos en Microsoft word y PowerPoint, el soporte para pantallas braille nuevas incluyendo las Eurobraille y el conversor de protocolo de Optelec, mejorado el soporte para las pantallas braille Hims y Optelec, mejoras de rendimiento para Mozilla Firefox 58 y posteriores, y mucho más.

### Nuevas Características

* Ahora es posible interactuar con gráficos en Microsoft Word y Microsoft PowerPoint, similar al soporte existente para gráficos en Microsoft Excel. (#7046)
 * En Microsoft Word: cuando se esté en modo exploración, pon el cursor en un gráfico integrado y pulsa intro para interactuar con él.
 * En Microsoft Powerpoint cuando se edite una diapositiva: tabula a un objeto gráfico, y pulsa intro o espacio para interactuar con el gráfico.
 * Para detener la interacción con un gráfico, pulsa escape.
* Nuevo idioma: Kyrgyz.
* Añadido el soporte para VitalSource Bookshelf. (#7155)
* Añadido el soporte para el protocolo conversor Optelec , un dispositivo que te permite utilizar las pantallas Braille Voyager y Satellite utilizando el protocolo de comunicación de las ALVA BC6. (#6731)
* Ahora es posible utilizar la entrada braille con una pantalla braille ALVA 640 Comfort. (#7733)
 * La funcionalidad de entrada braille de NVDA puede utilizarse tanto con éstas como con otras pantallas BC6 con el firmware 3.0.0 y anterior.
* Soporte inicial para Google Sheets con el modo Braille habilitado. (#7935)
* Soporte para pantallas braille Eurobraille Esys, Esytime e Iris. (#7488)

### Cambios

* Se han reemplazado los controladores de pantallas braille HIMS Braille Sense/Braille EDGE/Smart Beetle y Hims Sync por un único controlador. El nuevo controlador se activará automáticamente para los antiguos usuarios del controlador syncBraille. (#7459)
 * Algunas teclas, especialmente las teclas de desplazamiento, se han reasignado para seguir las convenciones utilizadas por los productos de Hims. Consulta la guía del usuario para más detalles.
* Al escribir con el teclado en pantalla a través de la interacción táctil, por omisión ahora debes hacer doble tap en cada tecla del mismo modo en que activarías cualquier otro control. (#7309)
 * Para utilizar el modo de "escritura táctil" existente donde basta con quitar el dedo de la tecla para activarla, habilita esta opción en el nuevo diálogo Opciones de Interacción Táctil que se encuentra en el menú Preferencias. (#7309)
* Ya no es necesario que el braille siga explícitamente al foco o a la revisión, ya que esto ocurrirá automáticamente por omisión. (#2385)
 * Ten en cuenta que el seguimiento automático a la revisión sólo ocurirá al utilizar un cursor de revisión u orden de navegación de objetos. El desplazamiento no activará este nuevo comportamiento.

### Corrección de Fallos

* Los mensajes explorables tales como mostrar el formato actual al pulsar NVDA+f dos veces rápidamente, ya no fallan cuando NVDA se instala en una ruta con caracteres no ASCII. (#7474)
* El foco ahora se restaura una vez más correctamente cuando se regresa a Spotify desde otra aplicación. (#7689)
* En la actualización Windows 10 Fall Creators, NVDA ya no falla al actualizar cuando el acceso controlado a la carpeta está habilitado desde Windows Defender Security Center. (#7696)
* La detección de las teclas de desplazamiento en las pantallas Hims Smart Beetle ya no es poco fiable. (#6086)
* Una ligera mejora en el rendimiento al procesar grandes cantidades de contenido en Mozilla Firefox 58 y posterior. (#7719)
* En Microsoft Outlook,  leer correos electrónicos que contengan tablas ya no causa errores. (#6827)
* Los gestos de las pantallas braille que emulan las teclas modificadoras del teclado del sistema ahora pueden combinarse también con otras teclas emuladas del teclado del sistema si uno o más de los gestos involucrados son específicos del modelo. (#7783)
* En Mozilla Firefox, el modo exploración ahora funciona correctamente en ventanas emergentes creadas por extensiones tales como LastPass y bitwarden. (#7809)
* NVDA ya no se bloquea a veces en cada cambio del foco si Firefox o Chrome han dejado de responder debido a una congelación o un cuelgue. (#7818)
* En clientes de twitter tales como Chicken Nugget, NVDA ya no ignorará los últimos 20 caracteres de tuits con 280 caracteres al leerlos. (#7828)
* NVDA ahora utiliza el idioma correcto al anunciar los símbolos cuando se seleccione texto. (#7687)
* En versiones recientes de Office 365, es nuevamente posible navegar gráficos de Excel utilizando las teclas de flechas. (#7046)
* En salidas de voz y braille, los estados de los controles ahora siempre se anuncian en el mismo orden, sin importar si son positivos o negativos. Correcciones #7076
* En aplicaciones tales como Mail de Windows 10, NVDA ya no fallará al anunciar los caracteres eliminados cuando se pulse retroceso. (#7456)
* Ahora todas las teclas en las pantallas Hims Braille Sense Polaris funcionan como se espera. (#7865)
* NVDA ya no falla al arrancar en Windows 7 quejándose acerca de una dll api ms interna, cuando una versión particular del Visual Studio 2017 redistributable se haya instalado por otra aplicación. (#7975)

### Cambios para Desarrolladores

* Añadida una bandera booleana oculta a la sección braille en la configuración: "outputPass1Only". (#7301, #7693, #7702)
 * Esta bandera está predeterminada a true. Si es false, se utilizarán las reglas liblouis multi pass para la salida braille.
* Se ha añadido un nuevo diccionario (braille.RENAMED_DRIVERS) para permitir una transición sin  problemas a los usuarios que utilizan controladores que hayan sido substituidos por otros. (#7459)
* Actualizado el paquete comtypes a 1.1.3. (#7831)
* Implementado un sistema genérico en braille.BrailleDisplayDriver para tratar con las pantallas que envían paquetes de confirmación/acuse de recibo. Consulta el controlador de las pantallas braille handyTech como un ejemplo. (#7590, #7721)
* Se puede utilizar una nueva variable "isAppX" en el módulo config para detectar si NVDA se está ejecutando como una aplicación Windows Desktop Bridge Store. (#7851)
* Para implementaciones de documento tales como NVDAObjects o browseMode que tengan un textInfo, ahora hay una nueva clase documentBase.documentWithTableNavigation que puede heredarse para obtener scripts de navegación estándar de tabla. Por favor consulta esta clase para ver qué métodos helper deben proporcionarse para tu implementación para que funcione la navegación de tabla. (#7849)
* El fichero por lotes scons ahora se maneja mejor cuando Python 3 también está instalado, haciendo el uso del lanzador para lanzar específicamente a python 2.7 de 32 bit. (#7541)
* hwIo.Hid ahora toma un parámetro adicional exclusivo, el cual por omisión es True. Si se configura a False, se permite a otras aplicaciones comunicarse con un dispositivo mientras esté conectado a NVDA. (#7859)

## 2017.4

Lo reseñable de esta versión incluye muchas correcciones y mejoras para el soporte web incluyendo el modo exploración para diálogos web por defecto, mejor anunciado de las etiquetas de los grupos de campos en modo exploración, el soporte para tecnologías nuevas de Windows 10 tales como la aplicación Windows Defender Guard y Windows 10 en ARM64, y el anunciado automático de la orientación de la pantalla y estado de batería.
Por favor ten en cuenta que esta versión de NVDA ya no soporta Windows XP o Windows Vista. Los requisitos mínimos para NVDA ahora son windows 7 con el Service Pack 1.

### Nuevas Características

* En modo exploración, ahora es posible saltar al inicio de las regiones utilizando las órdenes saltar al final o al principio del contenedor (coma/shift+coma). (#5482)
* En Firefox, Chrome e Internet Explorer, la navegación rápida por campos de edición y campos de formulario ahora incluye contenido de texto enriquecido editable (ej.: contentEditable). (#5534)
* En navegadores web, la Lista de Elementos ahora puede listar campos de formulario y botones. (#588)
* Soporte inicial para Windows 10 en ARM64. (#7508)
* Soporte preliminar para la lectura y la navegación interactiva de contenido matemático para libros Kindle con matemáticas accessibles. (#7536)
* Añadido soporte para el lector de libros digitales Azardi. (#5848)
* La información de versión para complementos ahora se anuncia cuando se estén actualizando. (#5324)
* Añadido el soporte para nuevos parámetros de línea de órdenes para crear una copia portable de NVDA. (#6329)
* Soporte para Microsoft Edge ejecutándose dentro de Windows Defender Application Guard (#7600)
* Si se ejecuta en un portátil o en una tablet, NVDA ahora anunciará cuando se conecte/desconecte un cargador y cuando la orientación de la pantalla cambie. (#4574, #4612)
* Idioma nuevo: Macedonio.
* Nuevas tablas de transcripción braille: Croata grado 1, Vietnamita grado 1. (#7518, #7565)
* Se ha añadido el soporte para la pantalla braille Actilino de Handy Tech. (#7590)
* Ahora se soporta la entrada braille para las pantallas braille Handy Tech. (#7590)

### Cambios

* El menor Sistema Operativo soportado por NVDA ahora es Windows 7 con el Service Pack 1, o Windows Server 2008 R2 con el Service Pack 1. (#7546)
* Los diálogos web en los navegadores Firefox y Chrome ahora utilizan el modo exploración automáticamente, al menos que se esté en una aplicación web. (#4493)
* En modo exploración, al tabular o moverse con las órdenes de teclas de navegación rápida ya no anuncia saliendo de contenedores tales como listas y tablas, Lo cual hace la navegación más eficaz. (#2591)
* En modo exploración para Firefox y Chrome, ahora se anuncian los nombres de grupos de campos de formulario al moverse dentro de ellos con la navegación rápida o cuando se tabula. (#3321)
* En modo exploración, las órdenes de navegación rápida para objetos integrados (o y shift+o) ahora incluyen elementos de audio y vídeo así como elementos con los roles aria application y dialog. (#7239)
* Se ha actualizado Espeak-ng 1.49.2),, esto resuelve algunos problemas con la producción de versiones. (#7385)
* En la tercera activación de la orden 'leer bara de estado', su contenido se copia al portapapeles. (#1785)
* Al asignar gestos a teclas en una pantalla Baum, puedes limitarlas al modelo de la pantalla braille en uso (ej.: VarioUltra o Pronto). (#7517)
* La tecla rápida para el campo filtrar en la lista de elementos en modo exploración se cambió de alt+f a alt+e. (#7569)
* Se ha añadido una orden para desvincular al modo exploración para conmutar la inclusión de tablas de diseño al vuelo. Puedes encontrar esta orden en la categoría Modo exploración del diálogo Gestos de entrada. (#7634)
* Actualizado el transcriptor braille a 3.3.0. (#7565)
* La tecla rápida para el botón de opción Expresión regular en el diálogo diccionario se cambió de alt+r a alt+e. (#6782)
* Los ficheros de los diccionarios del habla ahora se versionaron y se han movido al directorio 'speechDicts/voiceDicts.v1'. (#7592)
* Las modificaciones de los ficheros versionados (configuración del usuario, diccionarios del habla) ya no se guardan cuando NVDA se ejecuta desde el lanzador. (#7688)
* Las pantallas braille Braillino, Bookworm y Modular (con firmware antiguo) de Handy Tech ya no se soportan al sacarlas de la caja. Instala el controlador universal de Handy Tech y el complemento de NVDA para utilizar las pantallas. (#7590)

### Corrección de Fallos

* Los enlaces ahora se indican en braille en aplicaciones tales como Microsoft Word. (#6780)
* NVDA ya no se vuelve notablemente más lento cuando estén abiertas muchas pestañas en los navegadores web Firefox o Chrome. (#3138)
* El enrutamiento de cursor para las pantallas MDV Lilli Braille ya no mueve incorrectamente una celda braille antes de donde debería estar. (#7469)
* En Internet Explorer y otros documentos MSHTML, el atributo HTML5 requerido ahora se soporta para indicar el estado requerido de un campo de formulario. (#7321)
* Las pantallas braille ahora se actualizan al escribir caracteres arábigos en un documento WordPad alineado a la izquierda (#511).
* Las etiquetas accesibles para controles en Mozilla Firefox ahora se anuncian más fácilmente en modo exploración cuando la etiqueta no aparezca como contenido por sí misma. (#4773)
* En la actualización windows 10 Creators, NVDA puede acceder de nuevo a Firefox después de un reinicio de NVDA. (#7269)
* Cuando se reinicie NVDA con Mozilla Firefox enfocado, el modo exploración estará disponible nuevamente, aunque es posible que tengas que pulsar alt+tab y volver a pulsarlo de nuevo. (#5758)
* Ahora es posible acceder a contenido matemático en Google Chrome en un sistema sin Mozilla Firefox instalado. (#7308)
* El sistema operativo y otras aplicaciones deberían ser más estables directamente después de instalar NVDA antes de reiniciar, en comparación con las instalaciones  de versiones anteriores de NVDA. (#7563)
* Al utilizar una orden de reconocimiento de contenido (ej.: NVDA+r), ahora NVDA anuncia un mensaje de error en lugar de no hacer nada si el navegador de objetos ha desaparecido. (#7567)
* La funcionalidad desplazamiento hacia atrás se ha corregido para pantallas de freedom Scientific que contengan un balancín izquierdo. (#7713)

### Cambios para Desarrolladores

* "scons tests" ahora busca que las cadenas traducibles tengan comentarios para los traductores. También puedes ejecutar esto sólo con "scons checkPot". (#7492)
* Ahora hay un nuevo módulo extensionPoints que proporciona un framework genérico para permitir la extensibilidad de código en puntos específicos en el código. Esto permite que las partes interesadas se registren para ser notificadas cuando ocurra alguna acción (extensionPoints.Action), para modificar un tipo específico de dato (extensionPoints.Filter) o para participar en la decisión de si se hará algo (extensionPoints.Decider). (#3393)
* Ahora puedes registrarte para ser notificado acerca de los cambios de perfiles de configuración a través de la acción config.configProfileSwitched. (#3393)
* Los gestos de pantalla braille que emulan teclas modificadoras del teclado del sistema (tales como control y alt) ahora pueden conbinarse con otras teclas emuladas del teclado del sistema sin definición explícita. (#6213)
 * Por ejemplo: si tienes una tecla de la pantalla vinculada a la tecla alt y otra tecla de la pantalla a flecha abajo, al combinar estas teclas resultará la emulación de alt+flecha abajo.
* La clase braille.BrailleDisplayGesture ahora tiene una propiedad de modelo extra. Si se proporciona, pulsando una tecla generará una adicional, texto específico de identificador de modelo, esto permite a un usuario vincular gestos limitados a un modelo de pantalla braille específico.
 * Consulta el controlador de baum como un ejemlo para esta funcionalidad nueva.
* NVDA ahora se compila con Visual Studio 2017 y el SDK Windows 10. (#7568)

## 2017.3

Lo subrayable de esta versión incluye la entrada de braille contraído, el soporte para nuevas voces Windows OneCore disponibles en Windows 10, el soporte para el OCR integrado en Windows 10, y muchas mejoras significativas referentes al Braille y a la web.

### Nuevas Características

* Se ha añadido una opción Braille para "mostrar mensajes indefinidamente". (#6669)
* En la lista de mensajes de Microsoft Outlook, NVDA ahora anuncia si un mensaje está marcado. (#6374)
* En Microsoft PowerPoint, ahora se anuncia el tipo exacto de una forma cuando se edita una diapositiva tal como triángulo, círculo, vídeo, flecha, en lugar de sólo 'forma'. (#7111)
* El contenido matemático (proporcionado como MathML) ahora se soporta en Google Chrome. (#7184)
* NVDA ahora puede hablar utilizando las nuevas voces Windows OneCore (también conocidas como voces mobile) incluidas en Windows 10. Accede a ellas seleccionando Voces Windows OneCore en el diálogo Sintetizadores de NVDA. (#6159)
* Los ficheros de configuración de usuario de NVDA ahora pueden almacenarse en la carpeta local de datos de aplicaciones de usuario. Esto se habilita a través de una opción en el registro. Consulta 'Parámetros del Sistema' en la guía del usuario para más detalles. (#6812)
* En los navegadores web, NVDA ahora anuncia valores de marcador de posición para campos (específicamente, ahora se soporta aria-placeholder). (#7004)
* En el modo exploración de Microsoft Word, ahora es posible navegar por los errores de ortografía utilizando navegación rápida (w y shift+w) (#6942)
* Añadido el soporte para el control Selector de Fecha que se encuentra en los cuadros de diálogo Citas de Microsoft Outlook. (#7217)
* Ahora se anuncia la sugerencia actualmente seleccionada en los campos de Windows 10 Mail para/cc y en el campo Opciones de búsqueda de Windows 10. (#6241)
* Ahora se reproduce un sonido para indicar la aparición de sugerencias en ciertos campos de búsqueda de Windows 10 (Ej.: pantalla de inicio, Opciones de búsqueda, campos de Windows 10 mail para/CC). (#6241)
* NVDA ahora anuncia automáticamente las notificaciones en Skype for Business Desktop, tales como cuando alguien inicia una conversación contigo.  (#7281)
* NVDA ahora anuncia automáticamente mensajes de chat entrantes mientras se esté en una conversación en Skype for Business. (#7286)
* NVDA ahora anuncia automáticamente las notificaciones en Microsoft Edge, tales como cuando se inicia una descarga. (#7281)
* Ahora puedes escribir tanto en braille contraído como sin contraer en una pantalla braille con un teclado braille. Consulta la sección Entrada Braille de la Guía del Usuario para detalles. (#2439)
* Ahora puedes introducir caracteres braille Unicode desde el teclado braille en una pantalla braille seleccionando Braille Unicode como la tabla de entrada en Opciones de Braille. (#6449)
* Añadido el soporte para la pantalla braille SuperBraille utilizada en Taiwan. (#7352)
* Nuevas tablas de transcripción braille: braille danés computerizado de 8 puntos, Lituano, braille persa computerizado de 8 puntos, Persa grado 1, braille Esloveno computerizado de 8 puntos. (#6188, #6550, #6773, #7367)
* Mejorada la tabla de braille inglés computerizado de 8 puntos (U.S.), incluyendo el soporte para viñetas, el signo de euro y letras acentuadas. (#6836)
* NVDA ahora puede utilizar la funcionalidad OCR incluida en Windows 10 para reconocer el texto de imágenes o de aplicaciones inaccesibles. (#7361)
 * El idioma puede configurarse desde el nuevo diálogo OCR de Windows 10 en las preferencias de NVDA.
 * Para reconocer el contenido del navegador de objetos actual, pulsa NVDA+r.
 * Consulta la sección Reconocimiento de Contenidos de la Guía del Usuario para detalles adicionales.
* Ahora puedes elegir qué información de contexto se muestra en una pantalla braille cuando un objeto tiene el foco utilizando la nueva opción "Presentación de contexto del foco" en el diálogo Opciones de Braille. (#217)
 * Por ejemplo, las opciones "Rellenar pantalla para cambios de contexto" y "Sólo cuando se desplaza hacia atrás" pueden hacer que trabajar con listas y menús sea más eficiente, ya que los elementos no cambiarían contínuamente su posición en la pantalla.
 * Consulta la sección en la opción "Presentación de contexto del foco" en la Guía del Usuario para detalles adicionales y ejemplos.
* En Firefox y Chrome, NVDA ahora soporta rejillas dinámicas complejas tales como hojas de cálculo donde sólo se pueda cargar o mostrar una parte del contenido (específicamente los atributos aria-rowcount, aria-colcount, aria-rowindex y aria-colindex introducidos en ARIA 1.1). (#7410)

### Cambios

* Se ha añadido una orden no vinculada para reiniciar NVDA bajo demanda. Puedes encontrarla en la categoría Miscelánea del diálogo Gestos de entrada. (#6396)
* La distribución de teclado ahora puede configurarse desde el diálogo Bienvenida de NVDA. (#6863)
* Se han abreviado muchos más tipos de controles y estados en braille. Las regiones también se han abreviado. Porfavor consulta "Tipo de Control, estado y Abreviaturas de regiones" en Braille en la Guía del Usuario para una lista completa. (#7188, #3975)
* Actualizado Espeak-ng a 1.49.1 (#7280).
* Las listas de tablas de entrada y de salida en el diálogo Opciones de Braille ahora se ordenan alfabéticamente. (#6113)
* Actualizado el transcriptor braille liblouis a 3.2.0. (#6935)
* La tabla braille predeterminada ahora es Braille Inglés Unificado Código Grado 1. (#6952)
* Por omisión, NVDA ahora sólo muestra las partes de la información de contexto que haya cambiado en una pantalla braille cuando se enfoque un objeto. (#217)
 * Anteriormente, siempre mostraba tanta información como fuera posible, independientemente de si has visto la misma información de contexto antes.
 * Puedes volver a la anterior cambiando la nueva opción "Presentación de Contexto del Foco" en el diálogo Opciones de Braille a "Rellenar Siempre pantalla".
* Al utilizar Braille, el cursor puede configurarse para tener una forma diferente al seguir al foco o a la revisión. (#7112)
* El logo de NVDA se ha actualizado. El logo actualizado de NVDA es una mezcla estilizada de las letras NVDA en blanco, sobre un fondo sólido púrpura. Esto se asegura de que será visible en cualquier color de fondo, y utilizará el color púrpura del logo de NV Access. (#7446)

### Corrección de Fallos

* Los elementos div editables en Chrome ya no tienen su etiqueta anunciada como su valor mientras se esté en modo exploración. (#7153)
* Pulsar fin mientras se esté en modo exploración de un documento vacío de Microsoft Word ya no provoca un error en tiempo de ejecución. (#7009)
* El modo exploración ahora se soporta correctamente en Microsoft Edge cuando a un documento se le haya dado un rol ARIA específico de documento. (#6998)
* En modo exploración, ahora puedes seleccionar o deseleccionar hasta el fin de la línea utilizando shift+fin incluso cuando el cursor esté sobre el último carácter de la línea. (#7157)
* Si un diálogo contiene una barra de progreso, el texto del diálogo ahora se actualiza en braille cuando la barra de progreso cambie. Esto significa, por ejemplo, que el tiempo restante ahora puede leerse en el diálogo de NVDA "Descargando Actualizaciones". (#6862)
* NVDA ahora anunciará cambios de selección para ciertos cuadros combinados de Windows 10 tales como AutoReproducción en Opciones. (#6337).
* Ya no se anuncia información injustificada al entrar en diálogos de reuniones / citas en Microsoft Outlook. (#7216)
* Pitidos indeterminados para barras de progreso de diálogo tales como el actualizador sólo cuando la salida de la barra de progreso se configure para incluir pitidos. (#6759)
* En Microsoft Excel 2003 y 2007, las celdas se anuncian de nuevo al navegar a través de una hoja de cálculo. (#7243)
* En la actualización Windows 10 Creators y posterior, el modo exploración se activa de nuevo automáticamente al leer correos electrónicos en Windows 10 Mail. (#7289)
* En la mayoría de pantallas braille con un teclado braille, el punto 7 ahora borra la última celda o carácter braille introducido, y el punto 8 pulsa la tecla intro. (#6054)
* En el texto editable, al mover el cursor (ej.: con las teclas del cursor o retroceso), la respuesta hablada de NVDA ahora es más precisa en muchos casos, especialmente en Chrome y aplicaciones de terminal. (#6424)
* El contenido de Editor de Firmas en Microsoft Outlook 2016 ahora puede leerse. (#7253)
* En aplicaciones Java Swing, NVDA ya no causa que a veces la aplicación se cuelgue al navegar por las tablas. (#6992)
* En la actualización Windows 10 Creators, NVDA ya no anunciará notificaciones toast múltiples veces. (#7128)
* En el menú Inicio de Windows 10, al pulsar intro para cerrarlo después de una búsqueda ya no se produce que NVDA anuncie buscar texto. (#7370)
* Ahora es significativamente más rápido realizar la navegación rápida por encabezados en Microsoft Edge. (#7343)
* En Microsoft Edge, la navegación en modo exploración ya no se salta secciones largas de ciertas páginas web tales como el tema Wordpress 2015. (#7143)
* En Microsoft Edge, las regiones se localizan correctamente en otros idiomas diferentes al inglés. (#7328)
* El braille ahora sigue correctamente la selección al seleccionar texto más allá del ancho de la pantalla. Por ejemplo, si seleccionas varias líneas con shift+flecha abajo, el braille ahora muestra la última línea que seleccionaste. (#5770)
* En Firefox, NVDA ya no anuncia falsamente "sección" varias veces al abrir detalles para un tuit en twitter.com. (#5741)
* Las órdenes de navegación de tabla ya no están disponibles para tablas de diseño en modo Exploración al menos que el anunciado de las tablas de diseño esté habilitado. (#7382)
* En Firefox y Chrome, las órdenes de navegación de tablas en modo Exploración ahora omiten las celdas ocultas de la tabla. (#6652, #5655)

### Cambios para Desarrolladores

* Las marcass de tiempo ahora incluyen milésimas de segundo en el registro. (#7163)
* NVDA ahora debe compilarse con Visual Studio Community 2015. Visual Studio Express ya no se soporta. (#7110)
 * Ahora también se requieren las Windows 10 Tools y el SDK, que pueden habilitarse al instalar Visual Studio.
 * Consulta la sección Installed Dependencies del readme para detalles adicionales.
* El soporte para reconocedores de contenido tales como las herramientas OCR y descripción de imagen pueden implementarse fácilmente utilizando el nuevo paquete contentRecog. (#7361)
* Ahora se incluye el paquete de Python json package en las compilaciones binarias de NVDA. (#3050)

## 2017.2

Lo reseñable de esta versión incluye soporte completo para la atenuación de audio en la actualización Windows 10 Creators; correcciones para varios problemas con la selección en modo exploración, incluyendo problemas con seleccionar todo; mejoras significativas en el soporte de Microsoft Edge; y mejoras en la web tales como el indicado de elementos marcados como actual (utilizando aria-current).

### Nuevas Características

* Ahora se puede anunciar la información de borde de celdas en Microsoft Excel utilizando NVDA+f. (#3044)
* En los navegadores web, NVDA ahora indica cuando un elemento se ha marcado como actual (específicamente, utilizando el atributo aria-current). (#6358)
* Ahora se soporta el cambio autumático de idiomas en Microsoft Edge. (#6852)
* Añadido el soporte para la Calculadora de Windows en Windows 10 Enterprise LTSB (Long-Term Servicing Branch) y Server. (#6914)
* Al realizar la orden leer línea actual tres veces rápidamente se deletrea la línea con descripciones de caracteres. (#6893)
* Nuevo idioma: birmano.
* Ahora se verbalizan apropiadamente las flechas arriba y abajo  y los símbolos de fracción unicode. (#3805)

### Cambios

* Al navegar con revisión simple en aplicaciones que utilicen UI Automation, se ignoran más contenedores sin contenido haciendo más fácil la navegación. (#6948, #6950)

### Corrección de Fallos

* Los elementos de menú en páginas Web (las casillas de verificación y los botones de opción de los elementos de menús) ahora pueden activarse mientras se esté en modo exploración. (#6735)
* Pulsar Escape mientras el indicativo "confirmar eliminación" del perfil de configuración está activo ahora cierra el diálogo. (#6851)
* Corregidos algunos cuelgues en Mozilla Firefox y otras aplicaciones Gecko donde está habilitada la característica multi-proceso. (#6885)
* El anunciado del color de fondo en la revisión de pantalla ahora es más preciso cuando el texto se dibujó con un fondo transparente. (#6467)
* Mejorado el soporte para aria-describedby en Internet Explorer 11, incluyendo el soporte dentro de iframes y cuando se proporcionan varios IDs. (#5784)
* En la actualización Windows Creators, la atenuación de audio de NVDA funciona de nuevo como en anteriores versiones de Windows (ej.: Atenuar con voz y sonidos, atenuar siempre, y no atenuar están disponibles todas). (#6933)
* NVDA ya no fallará al navegar o al anunciar ciertos controles (UIA) donde no se definió un atajo de teclado. (#6779)
* Ya no se añaden dos espacios vacíos en la información de atajos de teclado para ciertos controles (UIA). (#6790)
* Ciertas combinaciones de teclas en las pantallas HIMS (ej.: espacio+punto4) ya no fallan intermittentemente. (#3157)
* Corregido un problema al abrir un puerto serie en sistemas que utilizan ciertos idiomas distintos al inglés que causaban que fallase la conexión a pantallas braille en algunos casos. (#6845)
* Se reduce la posibilidad de que el fichero de configuración se dañe al apagarse Windows. Los ficheros de configuración ahora se escriben en un fichero temporal antes de reemplazar el actual. (#3165)
* Al realizar la orden leer línea actual dos veces rápidamente para deletrearla, ahora se utiliza el idioma apropiado para los caracteres deletreados. (#6726)
* Navegar por líneas en Microsoft Edge ahora es hasta tres veces más rápido en la Actualización Windows 10 Creators. (#6994)
* NVDA ya no anuncia "Web Runtime grouping" al enfocar documentos en Microsoft Edge en la Actualización Windows 10 Creators (#6948)
* Ahora se soportan todas las versiones existentes de SecureCRT. (#6302)
* Adobe Acrobat Reader ya no se rompe en ciertos documentos PDF (específicamente, en aquellos que contengan  atributos empty ActualText). (#7021, #7034)
* En modo exploración en Microsoft Edge, las tablas interactivas (ARIA grids) ya no se saltan cuando se navegan con t y shift+t. (#6977)
* En modo exploración, al pulsar shift+inicio después de seleccionar hacia adelante ahora deselecciona hasta el comienzo de la línea según se esperaba. (#5746)
* En modo exploración, seleccionar todo (control+a) ya no falla para seleccionar texto si el cursor del sistema no está al comienzo del texto. (#6909)
* Corregidos algunos otros problemas extraños de selección en modo exploración. (#7131)

### Cambios para Desarrolladores

* Los argumentos de línea de órdenes ahora se procesan con el módulo argparser de Python, en lugar de con optparser. Esto permite a ciertas opciones tales como -r y -q manejarse exclusivamente. (#6865)
* core.callLater ahora pone en cola la devolución de llamada a la cola principal de NVDA después del retraso dado, en lugar de ejecutarla directamente despertando al núcleo. Esto detiene posibles cuelgues debidos a que el núcleo se vaya a dormir accidentalmente después de procesar una llamada, en medio de una llamada modal tal como el mostrado de un cuadro de mensaje. (#6797)
* La propiedad InputGesture.identifiers se ha cambiado tal que ya no se normaliza. (#6945)
 * Las subclases ya no necesitan normalizar identificadores antes de devolverlos desde esta propiedad.
 * Si quieres normalizar identificadores, ahora hay una propiedad InputGesture.normalizedIdentifiers la cual normaliza los identificadores devueltos por la propiedad identifiers.
* La propiedad InputGesture.logIdentifier ahora está obsoleta. Las llamadas deberían utilizar InputGesture.identifiers[0] en su lugar. (#6945)
* Se eliminó algún código obsoleto:
 * las constantes `speech.REASON_*`, deberían utilizarse en su lugar `controlTypes.REASON_*`. (#6846)
 * `i18nName` para opciones de sintetizador, `displayName` y `displayNameWithAccelerator` deberían utilizarse en su lugar. (#6846, #5185)
 * `config.validateConfig`. (#6846, #667)
 * `config.save`: se debería usar en su lugar `config.conf.save`. (#6846)
* La lista de completado en el menú de contexto autocompletar de la Consola Python ya no muestra cualquier ruta de objeto que lleve hasta el símbolo final que esté siendo completado. (#7023)
* Ahora hay una unidad de prueba del framework para NVDA. (#7026)
 * La unidad de prueba y la infraestructura se encuentran en el directorio tests/unit. Consulta la cadena de documentación en el fichero tests\unit\init.py para detalles.
 * Puedes ejecutar pruebas utilizando "scons tests". Consulta la sección "Running Tests" de readme.md para detalles.
 * Si estás enviando un pull request para NVDA, deberías ejecutar primero las pruebas y asegurarte de que se pasen.

## 2017.1

Lo reseñable de esta versión incluye el anunciado de secciones y columnas de texto en Microsoft Word; el Soporte para lectura, navegación y anotación de libros en Kindle para PC; y el soporte mejorado para Microsoft Edge.

### Nuevas Características

* Ahora pueden anunciarse en Microsoft Word el tipo de salto de sección y el número de sección. Esto se habilita con la opción "anunciar número de página" en el diálogo Formateado de documentos. (#5946)
* En Microsoft Word ahora pueden anunciarse las columnas de texto. Esto se habilita con la opción "anunciar números de página" en el diálogo Formateado de documentos. (#5946)
* Ahora se soporta el cambio automático de idiomas en Wordpad. (#6555)
* La orden buscar de NVDA (NVDA+control+f) ahora se soporta en modo exploración para Microsoft Edge. (#6580)
* La navegación rápida por botones en modo exploración (b y shift+b) ahora se soporta en Microsoft Edge. (#6577)
* Cuando se copìa una hoja en Microsoft Excel, se recuerdan los encabezados de columna y de fila configurados. (#6628)
* Soporte para leer y navegar libros en Kindle para PC versión 1.19, incluyendo el acceso a enlaces, notas al pie, gráficos, texto resaltado y notas de usuario. Por favor consulta la sección Kindle para PC de la Guía de Usuario de NVDA para información adicional. (#6247, #6638)
* Ahora se soporta la navegación de tablas en modo exploración en Microsoft Edge. (#6594)
* En Microsoft Excel, la orden anunciar localizaciónm del cursor de revisión (escritorio: NVDA+suprimir del teclado numérico, portátil: NVDA+suprimir) ahora anuncia el nombre de la hoja de cálculo y de la localización de la celda. (#6613)
* Añadida una opción al diálogo Salir para reiniciar con el nivel depuración en el registro. (#6689)

### Cambios

* La velocidad mínima del parpadeo del cursor braille ahora es 200ms. Los perfiles o las configuraciones con valores por debajo de este se incrementarán en 200ms. (#6470)
* Se ha añadido una casilla de verificación al diálogo opciones braille para permitir habilitar o deshabilitar el parpadeo del cursor braille. Anteriormente se utilizaba un valor de cero para lograr esto. (#6470)
* Actualizado eSpeak NG (commit e095f008, 10 de enero de 2017). (#6717)
* Debido a cambios en la actualización Windows 10 Creators, el modo "Atenuar siempre" ya no está disponible en las opciones de Atenuación de audio de NVDA. Todavía está disponible en versiones más antiguas de windows 10. (#6684)
* Debido a cambios en la Actualización Windows 10 Creators, el modo "Atenuar cuando salgan voz y sonidos" ya no puede asegurarse de que el audio se haya atenuado completamente antes de comenzar a hablar, ni mantendrá el audio atenuado el tiempo suficiente después de hablar para detener el rebote rápido en el volumen. Estos cambios no afectan a versiones más antiguas de windows 10. (#6684)

### Corrección de Fallos

* Corregido el cuelgue en Microsoft Word al moverse por párrafos a través de un documento largo mientras se está en modo exploración. (#6368)
* Las tablas en Microsoft Word que se hayan copiado desde Microsoft Excel ya no se tratan como tablas de diseño, y por lo tanto, ya no se ignoran. (#5927)
* Cuando se intenta teclear en Microsoft Excel mientras se esté en vista protegida, NVDA ahora hace un sonido en lugar de verbalizar los caracteres que no se escribieron. (#6570)
* Pulsando escape en Microsoft Excel ya no se cambia incorrectamente a modo exploración, al menos que el usuario haya cambiado anteriormente a modo exploración explícitamente con NVDA+espacio y luego entrado en el modo foco pulsando intro en un campo de formulario. (#6569)
* NVDA ya no se cuelga en hojas de cálculo de Microsoft Excel donde se fusione una fila o columna entera. 9#6216)
* El anunciado de texto recortado o desbordado en celdas de Microsoft Excel ahora debería de ser más preciso (#6472)
* NVDA ahora anuncia cuando una casilla de verificación es de sólo lectura. (#6563)
* El lanzador de NVDA ya no mostrará un diálogo de advertencia cuando no pueda reproducir el sonido de inicio debido a que no esté disponible el dispositivo de audio. (#6289)
* Los controles en la cinta de Microsoft Excel que no estén disponibles ahora se anuncian como tales. (#6430)
* NVDA ya no anunciará "panel" cuando se minimicen ventanas. (#6671)
* Los caracteres que se escriben ahora se verbalizan en aplicaciones UWP (incluyendo Microsoft Edge) en la actualización Windows 10 Creators. (#6017)
* El seguimiento del ratón ahora funciona en todas las pantallas en ordenadores con varios monitores. (#6598)
* NVDA ya no se volverá inusable después de salir de Windows Media Player mientras se enfoca un control deslizador. (#5467)

### Cambios para Desarrolladores

* Los ficheros de perfiles y configuración ahora se actualizan automáticamente para cumplir con los requisitos de las modificaciones del esquema. Si hay un error durante la actualización, se muestra una notificación, se reinicia la configuración, y el fichero de configuración antiguo está disponible en el registro de NVDA en el nivel 'Info'. (#6470)

## 2016.4

Lo reseñable de esta versión incluye la mejora del soporte para Microsoft Edge; el modo exploración en la aplicación Correo de Windows 10; y mejoras significativas para los diálogos de NVDA.

### Nuevas Características

* NVDA ahora puede indicar la sangría de líneas utilizando tonos. Esto se puede configurar utilizando el cuadro combinado "Anunciar Sangría de Líneas" en las preferencias del diálogo Formateado de documentos de NVDA. (#5906)
* Soporte para la pantalla braille Orbit Reader 20 . (#6007)
* Se ha añadido una opción para abrir la ventana del visualizador de voz al arrancar. Esto puede habilitarse a través de una casilla de verificación en la ventana del visualizador de voz. (#5050)
* Al reabrir la ventana del visualizador de voz, la localización y las dimensiones ahora se restaurarán. (#5050)
* Los campos de referencia cruzada en Microsoft Word ahora se tratan como hipervínculos. Se anuncian como enlaces y se pueden activar. (#6102)
* Soporte para las pantallas braille Baum SuperVario2, Baum Vario 340 y HumanWare Brailliant2. (#6116)
* Soporte inicial para la actualización Anniversary de Microsoft Edge. (#6271)
* Ahora se utiliza el modo exploración al leer correos electrónicos en la aplicación correo de Windows 10. (#6271)
* Idioma nuevo: Lituano.

### Cambios

* Actualizado el transcriptor braille liblouis a 3.0.0. Esto incluye mejoras significativas para el Braille Inglés Unificado. (#6109, #4194, #6220, #6140)
* En el administrador de complementos, los botones Deshabilitar complemento y Habilitar complemento ahora tienen atajos de teclado (alt+d y alt+e, respectivamente). (#6388)
* Se han resuelto varios problemas de relleno y alineación en diálogos de NVDA. (#6317, #5548, #6342, #6343, #6349)
* El diálogo formateado de documento se ha ajustado de manera que el contenido se deslice. (#6348)
* Ajustada la distribución del diálogo pronunciación de símbolos por lo que se utiliza todo el ancho del diálogo para la lista de símbolos. (#6101)
* En modo exploración en navegadores web, las órdenes de navegación de una sola letra de los campos de edición (e y shift+e) y de los campos de formulario (f y shift+f) ahora mueven a campos de edición de sólo lectura. (#4164)
* En las opciones de formateado de documentos de NVDA, "Anunciar cambios de formato después del cursor" se ha renombrado a "Anunciar cambios de formato después  del cursor", tal que afecte tanto al braille como a la voz. Nota: esto no afecta a la traducción al español ya que usamos announce y report como sinónimos. (#6336)
* Ajustada la apariencia del "diálogo Bienvenida" de NVDA. (#6350)
* Los cuadros de diálogo de NVDA ahora tienen sus botones "Aceptar" y "Cancelar" alineados a la derecha del diálogo. (#6333)
* Ahora se utilizan controles de giro para los campos de entrada numérica tal como la opción de "porcentaje de tono de mayúsculas" en el diálogo Opciones de Vopz. Puedes introducir el valor decidido o utilizar las teclhas de flecha arriba y abajo para ajustar el valor. (#6099)
* El modo en el que IFrames se anuncia (documentos integrados dentro de documentos) se ha hecho mucho más consistente para los navegadores. IFrames ahora se anuncia como "marco" en Firefox. (#6047)

### Corrección de Fallos

* Corregido un extraño problema al salir de  NVDA mientras el visualizador de voz está abierto causa un error. (#5050)
* Los mapas de imagen ahora se procesan como se esperaba en el modo exploración en Mozilla firefox. (#6051)
* Mientras se está en el diálogo diccionarios, al pulsar la tecla intro ahora se guarda cualquier cambio que hayas hecho y se cierra el diálogo. Anteriormente, al pulsar intro no se hacía nada. (#6206)
* Ahora se muestran los mensajes en braille al cambiar los modos de entrada para un método de entrada (entrada nativa/alfanumérica, forma completa/ forma media, etc.). (#5892, #5893)
* Al deshabilitar y luego inmediatamente rehabilitar un complemento o viceversa, el estado del complemento  ahora vuelve a tal y como estaba anteriormente. (#6299)
* Al utilizar Microsoft Word, los campos de número de página en encabezados ahora pueden leerse. (#6004)
* El ratón ahora puede utilizarse para mover el foco entre la lista de símbolos y los campos de edición en el diálogo pronunciación de símbolos. (#6312)
* En modo exploración en microsoft Word se corrigió un problema que detiene la aparición de la lista de elementos cuando contiene un hipervínculo inválido. (#5886)
* Después de cerrarse a través de la barra de tareas o del atajo de teclado alt+F4, el estado de la casilla de verificación visualizador de voz en el menú NVDA ahora reflejará la visibilidad actual de la ventana. (#6340)
* La orden recargar plugins ya no causa problemas para los perfiles de configuración disparados, en los documentos nuevos en navegadores web y en revisión de pantalla. (#2892, #5380)
* En la lista de idiomas en el diálogo Opciones Generales de NVDA, idiomas tales como el Aragonés ahora se muestran correctamente en Windows 10. (#6259)
* Las teclas de sistema de emulación de teclado (ej.: un botón en una pantalla braille que emule la pulsación de la tecla tab) ahora se presentan en el idioma configurado en NVDA en la ayuda de entrada y en el diálogo Gestos de Entrada. Anteriormente, siempre se presentaban en inglés. (#6212)
* Al cambiar el idioma de NVDA (desde el diálogo Opciones Generales) ahora no tiene efecto hasta que NVDA se reinicie. (#4561)
* Ya no es posible dejar el campo Patrón en blanco para una entrada de diccionario nueva. (#6412)
* Corregido un extraño problema al escanear puertos serie en algunos sistemas que hacía algunos controladores de pantallas braille inusables. (#6462)
* En Microsoft word las viñetas numeradas ahora se leen desde las celdas de las tablas al moverse por celdas. (#6446)
* Ahora es posible asignar gestos a órdenes para el controlador de la pantalla braille Handy Tech en el diálogo Gestos de Entrada. (#6461)
* En Microsoft Excel, al pulsar intro o intro del teclado numérico cuando se navega por una hoja de cálculo ahora se anuncia correctamente la navegación a la siguiente fila. (#6500)
* iTunes ya no se cuelga intermitentemente al utilizar el modo exploración para la Tienda iTunes, Apple Music, etc. (#6502)
* Corregidos cuelgues en aplicaciones basadas en Mozilla y Chrome de 64 bits. (#6497)
* En Firefox con el multiproceso habilitado, el modo exploración y los campos de texto editables ahora funcionan correctamente. (#6380)

### Cambios para Desarrolladores

* Ahora es posible proporcionar app modules para ejecutables que contengan un punto (.) en sus nombres. Los puntos se reemplazan con subrayados (_). (#5323)
* El nuevo módulo gui.guiHelper incluye utilidades para simplificar la creación de GUIs wxPython, incluyendo la gestión automática de espaciado. Esto facilita una mejor  apariencia visual y consistencia, así como la creación fácil de GUIs nuevas para desarrolladores ciegos. (#6287)

## 2016.3

Lo reseñable de esta versión incluye la capacidad para deshabilitar complementos individuales; el soporte para campos de formulario en Microsoft Excel; mejoras significativas para el anunciado de colores; correcciones y mejoras relacionadas con varias pantallas braille; y correcciones y mejoras para el soporte de Microsoft Word.

### Nuevas Características

* El modo exploración ahora puede utilizarse para leer documentos PDF en Microsoft Edge en la actualización Windows 10 Anniversary. (#5740)
* El tachado y el doble tachado ahora se anuncian si es apropiado en Microsoft Word. (#5800)
* En Microsoft Word, ahora se anuncia el título de una tabla si se ha proporcionado uno. Si hay una descripción, se puede acceder a ella utilizando la opción Abrir descripción larga (NVDA+d) en modo exploración. (#5943)
* En Microsoft Word, NVDA ahora anuncia información de posición cuando se mueven párrafos (alt+shift+flecha abajo y alt+shift+flecha arriba. (#5945)
* En Microsoft Word, ahora se anuncia el espaciado a través de la orden anunciar formato de NVDA, cuando se cambie con varios atajos de teclado de Microsoft word, y cuando al moverte al texto con espaciado de línea diferente si Anunciar Espaciado de Línea está activado en las Opciones de Formato de Documento de NVDA. (#2961)
* En Internet Explorer, los elementos estructurales  HTML5 ahora se reconocen. (#5591)
* El anunciado de comentarios (tales como en Microsoft Word) ahora pueden deshabilitarse a través de una casilla de verificación Anunciar Comentarios en el diálogo de opciones de Formateado de Documentos de NVDA. (#5108)
* Ahora es posible deshabilitar complementos individuales en el administrador de complementos. (#3090)
* Se han añadido asignaciones de teclas adicionales para las pantallas braille ALVA BC640/680 series. (#5206)
* Ahora hay una orden para mover la pantalla braille al foco actual. Por ahora, sólo las ALVA BC640/680 series tienen una tecla asignada a esta orden, pero puede asignarse manualmente para otras pantallas del diálogo Gestos de Entrada si se desea. (#5250)
* En Microsoft Excel, ahora puedes interactuar con campos de formulario. Muévete a los campos de formulario utilizando la Lista de Elementos o la navegación de una sola letra en modo exploración. (#4953)
* Ahora puedes asignar un gesto de entrada para conmutar el modo de revisión simple utilizando el diálogo Gestos de Entrada. (#6173)

### Cambios

* NVDA ahora anuncia colores utilizando un conjunto básico comprensible de 9 tonos y de 3 matices de color, con variaciones de brillo y palidez. Esto es mejor que utilizar nombres de colores más subjetivos y menos inteligibles. (#6029)
* Se ha modificado el comportamiento del existente NVDA+F9 después NVDA+F10 para seleccionar texto en la primera pulsación de F10. Cuando se pulse F10 dos veces (en sucesión rápida) el texto se copia al portapapeles. (#4636)
* Actualizado eSpeak NG a la versión Master 11b1a7b (22 de junio de 2016). (#6037)

### Corrección de Fallos

* En modo exploración en Microsoft Word, el copiado al portapapeles ahora conserva el formato. (#5956)
* En Microsoft Word, NVDA ahora anuncia apropiadamente al utilizar las propias órdenes de navegación de tablas de Word (alt+inicio, alt+fin, alt+rePág y alt+avPág) y las órdenes de selección de tabla (shift añadido a las órdenes de navegación). (#5961)
* En los cuadros de diálogo de Microsoft Word, la navegación de objetos de NVDA ha sido muy mejorada. (#6036)
* En algunas aplicaciones tales como Visual Studio 2015, los atajos de teclado (ej.: control+c para Copiar) ahora se anuncian como se esperaba. (#6021)
* SE corrigió un extraño problema al escanear los puertos serie en algunos sistemas que hacían inusables algunos controladores de pantallas braille.  (#6015)
* El anunciado de colores en Microsoft Word ahora es más preciso tal que los cambios en los temas de Microsoft Office ahora se tengan en cuenta. (#5997)
* Está disponible de nuevo el modo exploración en Microsoft Edge y el soporte para las sugerencias de búsqueda del menú Inicio en compilaciones de Windows 10 de después de abril de 2016. (#5955)
* En Microsoft Word, la lectura automática de emcabezados de tabla funciona mejor cuando se traten celdas combinadas. (#5926)
* En la aplicación Mail de Windows 10, NVDA ya no falla al leer el contenido de los mensajes. (#5635)
* Cuando esté activa la bervalización de teclas de órdenes, las teclas de bloqueo tales como el bloqueo de mayúsculas ya no se anuncian dos veces. (#5490)
* Los diálogos de Control de Cuentas de Usuario de Windows se leen correctamente de nuevo en la actualización Windows 10 Anniversary. (#5942)
* En el Plugin Web Conference (tal como se utilizó en out-of-sight.net) NVDA ya no pita y habla las actualizaciones de las barras de progreso relacionadas con la entrada de micrófono. (#5888)
* Al realizar una orden Buscar Siguiente o Buscar Anterior en modo exploración ahora hará correctamente la búsqueda sensible a mayúsculas si la Búsqueda original era sensible a las mayúsculas. (#5522)
* Al editar entradas de diccionario, ahora se da retroalimentación para expresiones regulares inválidas. NVDA ya no se cuelga si un fichero de diccionario contiene una expresión regular inválida. (#4834)
* Si NVDA no es capaz de comunicarse con una pantalla braille (Por ej.: porque se ha desconectado), se deshabilitará automáticamente la utilización de la pantalla. (#1555)
* Se mejora ligeramente el rendimiento del filtrado en la Lista de Elementos del Modo Exploración en algunos casos. (#6126)
* En Microsoft Excel, Los nombres de los motivos de fondo anunciados por NVDA ahora coinciden con aquellos utilizados por Excel. (#6092)
* Mejorado el soporte para la pantalla de autentificación de Windows 10, incluyendo el anunciado de alertas y activación del campo de contraseña con touch. (#6010)
* NVDA ahora detecta correctamente los sensores de seguimiento secundarios en las pantallas braille ALVA BC640/680 series. (#5206)
* NVDA puede anunciar de nuevo notificaciones de Windows Toast en compilaciones recientes de Windows 10. (#6096)
* NVDA ya no detiene ocasionalmente el reconocimiento de pulsaciones de teclas en pantallas braille Baum compatible y HumanWare Brailliant B. (#6035)
* Si está habilitado el anunciado de números de línea en las preferencias de Formato de Documento de NVDA, los números de línea ahora se muestran en una pantalla braille. (#5941)
* Cuando el modo de voz esté desactivado, el anunciado de objetos (tal como pulsar NVDA+tab para anunciar el foco) ahora aparece en el Visualizador de Voz como se esperaba. (#6049)
* En la lista de mensajes de Outlook 2016, ya no se anuncia la información asociada al borrador. (#6219)
* En Google Chrome y navegadores basados en Chrome en un idioma diferente al inglés, el modo exploración ya no falla al trabajar en muchos documentos. (#6249)

### Cambios para Desarrolladores

* La información de autentificación directamente desde una propiedad ya no resulta en que la propiedad sea llamada recursivamente una y otra vez. (#6122)

## 2016.2.1

Esta versión corrige cuelgues en Microsoft Word:

* NVDA ya no causa que Microsoft Word se cuelgue imediatamente después de arrancar en Windows XP. (#6033)
* Eliminado el anunciado de errores de gramática, ya que causa cuelgues en Microsoft Word. (#5954, #5877)

## 2016.2

Lo subrayable de esta versión incluye la capacidad para indicar errores de ortografía mientras se escribe; el soporte para el anunciado de errores gramaticales en Microsoft Word; y mejoras y correcciones para el soporte de Microsoft Office.

### Nuevas Características

* En modo exploración en Internet Explorer y otros controles MSHTML, utilizando primero la navegación con una sola letra para mover por anotación (a y shift+a) ahora se mueve a texto insertado y eliminado. (#5691)
* En Microsoft Excel, NVDA ahora anuncia el nivel de un grupo de celdas, así como si está contraído o expandido. (#5690)
* Al pulsar la orden Anunciar formato de texto (NVDA+f) dos veces presenta la información en modo exploración para que se pueda revisar. (#4908)
* En Microsoft Excel 2010 y posterior, el sombreado y el degradado de relleno de celda ahora se anuncia. El anunciado automático se controla por la opción Anunciar colores en las preferencias de Formateado de Documentos de NVDA. (#3683)
* Nueva tabla de transcripción braille: Griego koiné. (#5393)
* En el Visualizador de Registro, ahora puedes guardar el registro utilizando el atajo de teclado control+s. (#4532)
* Si el anunciado de errores de ortografía está habilitado y se soporta en el control enfocado, NVDA reproducirá un sonido para alertarte de un error de ortografía cometido mientras tecleas. Esto puede deshabilitarse utilizando la nueva opción "Reproducir sonido para errores de ortografía mientras se escribe" en el diálogo Opciones de teclado de NVDA. (#2024)
* Ahora se anuncian errores gramaticales en Microsoft Word. Esto puede deshabilitarse utilizando la nueva opción "Anunciar errores gramaticales" en el diálogo Formateado de Documentos de NVDA. (#5877)

### Cambios

* En modo exploración y en campos de texto editables, NVDA ahora trata al intro del teclado numérico del mismo modo que la tecla intro principal. (#5385)
* NVDA ha cambiado al sintetizador de voz eSpeak NG. (#5651)
* En Microsoft Excel, NVDA ya no ignora un encabezado de columna de una celda cuando haya una fila en blanco entre la celda y el encabezado. (#5396)
* En Microsoft Excel, las coordenadas ahora se anuncian después de los encabezados para eliminar la ambigüedad entre los encabezados y el contenido. (#5396)

### Corrección de Fallos

* En modo exploración, cuando se intenta utilizar la navegación con una sola letra para moverte a un elemento que no se soporta en el documento, NVDA anuncia que esto no se soporta en lugar de anunciar que no hay elemento en esa dirección. (#5691)
* Cuando se listan hojas en la lista de elementos en Microsoft Excel, las hojas que contengan sólo gráficos ahora se incluyen. (#5698)
* NVDA ya no anuncia información extraña cuando se cambie entre ventanas en una aplicación Java con múltiples ventanas tales como IntelliJ o Android Studio. (#5732)
* En editores basados en Scintilla tales como Notepad++, el braille ahora se actualiza correctamente al mover el cursor utilizando una pantalla braille. (#5678)
* NVDA ya no se cuelga a veces al habilitar la salida braille. (#4457)
* En Microsoft Word, la sangría de párafo ahora siempre se anuncia en la unidad de medida elegida por el usuario (ej.: centímetros o pulgadas). (#5804)
* Al utilizar una pantalla braille, muchos mensajes de NVDA que anteriormente sólo se verbalizaban ahora se braillifican también. (#5557)
* En aplicaciones Java accesibles, el nivel de los elementos de la vista en árbol ahora se anuncia. (#5766)
* Corregidos cuelgues en Adobe Flash en Mozilla Firefox en algunos casos. (#5367)
* En Google Chrome y navegadores basados en Chrome, los documentos dentro de diálogos o aplicaciones ahora pueden leerse en modo exploración. (#5818)
* En Google Chrome y navegadores basados en Chrome, ahora puedes forzar a NVDA para cambiar a modo exploración en diálogos web o aplicaciones. (#5818)
* En Internet Explorer y otros controles MSHTML, al mover el foco a ciertos controles (específicamente, donde se utilice aria-activedescendant) ya no cambia incorrectamente a modo exploración. Esto ocurría, por ejemplo, al moverse a sugerencias en campos de dirección cuando se compone un mensaje en Gmail. (#5676)
* En Microsoft Word, NVDA ya no se cuelga en tablas largas cuando el anunciado de encabezados de fila o columna de tabla esté habilitado. (#5878)
* En Microsoft word, NVDA ya no anuncia incorrectamente texto con un nivel fuera de línea (pero no un estilo de encabezados integrados) como un encabezado. (#5186)
* En modo exploración en Microsoft Word, las órdenes Mover pasando de fin o a inicio de contenedor (coma y shift+coma) ahora funcionan para tablas. (#5883)

### Cambios para Desarrolladores

* Los componentes c++ de NVDA ahora se compilan con Microsoft Visual Studio 2015. (#5592)
* Ahora puedes presentar un texto o mensaje HTML al usuario en modo exploración utilizando ui.browseableMessage. (#4908)
* En la Guía del Usuario, cuando se utiliza una orden <!-- KC:setting para una opción que tiene una tecla común para todas las distribuciones, la tecla ahora podrá colocarse después de un dos puntos de ancho completo (：) así como los dos puntos regulares (:). (#5739)

## 2016.1

Lo reseñable de esta versión incluye la capacidad de bajar opcionalmente el volumen de otros sonidos; mejoras de la salida braille y del soporte de pantallas braille; varias correcciones significativas para el soporte de Microsoft Office; y correcciones al modo exploración en iTunes.

### Nuevas Características

* Nuevas tablas de transcripción braille: braille polaco computerizado de 8 puntos, mongol. (#5537), #5574)
* Puedes desactivar el cursor braille y cambiar su forma utilizando las nuevas opciones Mostrar cursor y Forma del cursor en el diálogo Opciones de Braille. (#5198)
* NVDA ahora puede conectar con la pantalla braille HIMS Smart Beetle  a través de Bluetooth. (#5607)
* NVDA puede bajar opcionalmente el volumen de otros sonidos cuando se instale en Windows 8 y posteriores. Esto puede configurarse utilizando la opción Modo de atenuación de audio en el diálogo Sintetizador de NVDA o pulsando NVDA+shift+d. (#3830, #5575)
* Soporte para la APH Refreshabraille en modo HID y para la Baum VarioUltra y Pronto! cuando se conecten a través de USB. (#5609)
* Soporte para las pantallas braille HumanWare Brailliant BI/B cuando el protocolo se pone en OpenBraille. (#5612)

### Cambios

* El anunciado de émfasis ahora está deshabilitado por omisión. (#4920)
* En el diálogo Lista de Elementos en Microsoft Excel, el atajo de teclado para Fórmulas ha sido cambiado a alt+r así es diferente al atajo de teclado para el Filtro de campos. (#5527)
* Actualizado el transcriptor braille liblouis a 2.6.5. (#5574)
* La palabra "texto" ya no se anuncia cuando se mueva el foco o el cursor de revisión a objetos de texto. (#5452)

### Corrección de Fallos

* En iTunes 12, el modo exploración ahora se actualiza correctamente cuando se carga una página nueva en la iTunes Store. (#5191)
* En Internet Explorer y otros controles  MSHTML, al moverse a los niveles de encabezados específicos con la navegación con una sola letra ahora se comporta como se esperaba cuando el nivel de un encabezado se ignora con propósitos de accesibilidad (específicamente, cuando aria-level hace caso omiso del nivel de una etiqueta h). (#5434)
* En Spotify, el foco ya no aterriza frecuentemente en objetos "desconocido". (#5439)
* El foco ahora se restaura correctamente al regresar a Spotify desde otra aplicación. (#5439)
* Al conmutar entre modo exploración y modo foco, el modo se anuncia en braille así como en voz. (#5239)
* El botón Inicio en la Barra de Tareas ya no se anuncia como una lista y/o como seleccionado en algunas versiones de Windows. (#5178)
* Mensajes tales como "insertado" ya no se anuncian cuando se creen correos en Microsoft Outlook. (#5486)
* Cuando se utiliza una pantalla braille y el texto se seleccione en la línea actual (ej.: al buscar en un editor de textos para texto que ocurra en la misma línea), la pantalla braille se desplazará si es apropiado. (#5410)
* NVDA ya no saldrá silenciosamente al cerrar una consola de órdenes de Windows con alt+f4 en Windows 10. (#5343)
* En la Lista de Elementos en modo exploración, cuando cambies el tipo de elemento, ahora se limpia el campo Filtrar por. (#5511)
* En texto editable en aplicaciones de Mozilla, moviendo el ratón lee de nuevo la línea, la palabra, etc. apropiada como se esperaba en lugar de todo el contenido. (#5535)
* Al mover el ratón en texto editable en aplicaciones de Mozilla, la lectura 		ya no se detiene en elementos tales como enlaces dentro de la palabra o línea que esté leyéndose. (#2160, #5535)
* En Internet Explorer, el sitio web shoprite.com ahora puede leerse en modo exploración en lugar de anunciarlo como en blanco. (Específicamente, los atributos lang mal formados ahora se manejan graciosamente.) (#5569)
* En Microsoft Word, el seguimiento de cambios tales como "insertado" ya no se anuncia cuando la marca de seguimiento de cambios no se muestra. (#5566)
* Cuando se enfoque un botón conmutable , NVDA ahora anuncia cuando se cambie de pulsado a no pulsado. (#5441)
* El anunciado de la forma del ratón ahora funciona de nuevo como se esperaba. (#5595)
* Al verbalizar el sangrado de línea, los espacios de no separación ahora son tratados como espacios normales. Anteriormente, esto podía causar anunciados tales como "espacio espacio espacio" en lugar de "3 espacios". (#5610)
* Al cerrar una lista de métodos candidatos de entrada en Microsoft moderno, el foco se restaura correctamente o la composición de entrada o el documento subrayado. (#4145)
* En Microsoft Office 2013 y posteriores, cuando las cintas están configuradas para mostrar sólo pestañas, los elementos en la cinta se muestran de nuevo como se esperaba cuando se activa una pestaña. (#5504)
* Correcciones y mejoras para el enlazado y la detección de gestos de pantalla táctil. (#5652)
* Los Touch screen hovers ya no se anuncian en ayuda de entrada. (#5652)
* NVDA ya no falla al listar comentarios en la Lista de Elementos para Microsoft Excel si un comentario está sobre una celda fusionada. (#5704)
* En un caso muy poco común, NVDA ya no falla al leer el contenido de la hoja en Microsoft Excel con el anunciado de encabezados de fila y columna habilitado. (#5705)
* En Google Chrome, al navegar dentro de una Composición de Entrada cuando se introducen caracteres del Este Asiático ahora funciona como se esperaba. (#4080)
* Cuando se busca en Apple Music en iTunes, el modo exploración para el documento de resultados de la búsqueda ahora se actualiza como se esperaba. (#5659)
* En Microsoft Excel, pulsando shift+f11 para crear una hoja nueva ahora anuncia tu nueva posición en lugar de no anunciar nada. (#5689)
* Corregidos problemas con la salida de la pantalla braille cuando se introducen caracteres coreanos. (#5640)

### Cambios para Desarrolladores

* La nueva clase audioDucking.AudioDucker permite código que saca audio para indicar dónde debería atenuarse el audio de fondo. (#3830)
* el constructor del nvwave.WavePlayer ahora tiene la palabra clave wantDucking como argumento que especifica si el audio de fondo debería atenuarse mientras se reproduce audio. (#3830)
 * Cuando esto esté habilitado (lo cual está predeterminado), es esencial que WavePlayer.idle se llame cuando sea apropiado.
* Mejorada la Entrada/salida para pantallas braille: (#5609)
 * Los controladores Thread-safe de pantallas braille pueden declararse como tales utilizando el atributo BrailleDisplayDriver.isThreadSafe. Un controlador thread-safe debe beneficiarse de las siguientes características.
 * Los datos se escriben al controlador de pantallas braille thread-safe en segundo plano, mejorando así el rendimiento.
 * hwIo.Serial extiende pyserial para llamar una llamada cuando los datos se reciban en lugar de que los controladores tengan que buscarlos.
 * hwIo.Hid proporciona soporte para que las pantallas braille se comuniquen a través de USB HID.
 * hwPortUtils y hwIo pueden proporcionar opcionalmente el registro detallado de depuración, incluyendo dispositivos encontrados y todos los datos enviados y recibidos.
* Hay varias propiedades nuevas accesibles de los gestos de la pantalla táctil: (#5652)
 * Los objetos MultitouchTracker ahora contienen una propiedad childTrackers que contiene el MultiTouchTrackers el tracker se componía de. Por ejemplo, 2 dedos doble tap tiene trackers de hijo o dos taps de dos dedos. Los taps de dos dedos en sí mismos tiene trackers hijos para dos taps.
 * Los objetos MultiTouchTracker ahora también contienen una propiedad rawSingleTouchTracker si el tracker fue el resultado de un solo dedo haciendo un tap, flick o desplazamiento. El SingleTouchTracker permite acceder al ID subyacente asignado al dedo por el sistema operativo y si el dedo sigue o no en contacto en el momento actula.
 * TouchInputGestures ahora tiene propiedades x e y, eliminando la necesidad de acceder al tracker por cosas triviales.
 * TouchInputGestures ahora contiene una propiedad preheldTracker, la cual es un objeto MultitouchTracker representando los otros dedos sujetos mientras se realiza esta acción.
* Se pueden dar dos nuevos gestos de pantalla táctil: (#5652)
 * Pulsar y mantener en Plural tap (ej.: doble tap y mantener)
 * Un identificador generalizado con el recuento de dedos eliminados para el mantenimiento pulsado  (ej.: hold+hover for 1finger_hold+hover).

## 2015.4

Lo subrayable en esta versión incluye mejoras de rendimiento en Windows 10; la inclusión en el Centro de Accesibilidad en Windows 8 y posterior; mejoras para Microsoft Excel, incluyendo el listado y el renombrado de hojas y el acceso a celdas bloqueadas en hojas con protección; y apoyo para la edición de texto enriquecido en Mozilla Firefox, Google Chrome y Mozilla Thunderbird.

### Nuevas Características

* NVDA ahora aparece en el Centro de Accesibilidad en Windows 8 y posterior. (#308)
* Al moverse por celdas en Excel, los cambios de formato ahora se anuncian automáticamente si se activaron las opciones apropiadas en las opciones del diálogo Formato de Documento de NVDA. (#4878)
* Se ha añadido una opción Anunciar Énfasis al diálogo Opciones de Formato de Documento de NVDA. Activada por omisión, esta opción permite a NVDA anunciar automáticamente la existencia de texto destacado en documentos. Hasta ahora sólo está soportado para las etiquetas em y strong en modo exploración para Internet Explorer y otros controles MSHTML. (#4920)
* La existencia de texto insertado y eliminado ahora se anuncia en modo exploración para Internet Explorer y otros controles MSHTML, si la opción Anunciar Revisión del Editor de NVDA está activada. (#4920)
* Al ver seguimiento de cambios en la lista de elementos de NVDA para Microsoft Word, ahora se muestra más información tal como qué propiedades de formato se cambiaron. (#4920)
* Microsoft Excel: ahora es posible listar y renombrar hojas desde la Lista de Elementos de NVDA (NVDA+f7). (#4630, #4414)
* Ahora es posible configurar si los símbolos actuales se envían a los sintetizadores de voz (ej.: para causar una pausa o para cambiar la entonación) en el diálogo Pronunciación de Símbolos. (#5234)
* En Microsoft Excel, NVDA ahora anuncia cualquier mensaje de entrada puesto por el autor de la hoja en las celdas. (#5051)
* Apoyo para las pantallas braille Baum Pronto! V4 y VarioUltra cuando se conecten a través de Bluetooth. (#3717)
* Apoyo para la edición de texto enriquecido en aplicaciones de Mozilla tales como Google Docs con el apoyo al braille habilitado en Mozilla Firefox y composición HTML en Mozilla Thunderbird. (#1668)
* Apoyo para edición o texto enriquecido en Google Chrome y navegadores basados en Chrome tales como Google Docs con el apoyo braille habilitado. (#2634)
 * Esto requiere de Chrome versión 47 o posterior.
* En modo exploración en Microsoft Excel, puedes navegar a celdas bloqueadas en hojas con protección. (#4952)

### Cambios

* La opción Anunciar Revisiones del Editor en el diálogo Opciones de Formato de documento de NVDA ahora se activa por omisión. (#4920)
* Al moverse por caracteres en Microsoft Word con la opción de NVDA Anunciar Vevisiones del Editor, ahora se anuncia menos información para seguimiento de cambios, lo cual hace la navegación más eficiente. Para ver la información extra, utiliza la Lista de Elementos. (#4920)
* Actualizado el transcriptor braille liblouis translator  a 2.6.4. (#5341)
* Varios símbolos (incluyendo símbolos básicos matemáticos) se han movido al nivel alguna tal que sean verbalizados por omisión. (#3799)
* Si el sintetizador lo soporta, la voz ahora debería pausar para los paréntesis y el guión final (–). (#3799)
* Al seleccionar texto, el texto se anuncia antes de la indicación de la selección en lugar de después. (#1707)

### Corrección de fallos

* Grandes mejoras de rendimiento al navegar por la barra de mensajes en Outlook 2010/2013. (#5268)
* En un gráfico en Microsoft Excel, al navegar con ciertas teclas (tales como al cambiar de hoja con control+rePág y control+avPág) ahora funciona correctamente. (#5336)
* Corregida la apariencia visual de los botones en el diálogo de advertencia que se muestra cuando intentas actualizar NVDA a una versión anterior. (#5325)
* En Windows 8 y posterior, NVDA ahora arranca mucho más rápido cuando se configuró para iniciarse después de autentificarse en Windows. (#308)
 * Si habilitaste esto utilizando una versión anterior  de NVDA, necesitarás deshabilitarlo y habilitarlo de nuevo en el diálogo  Opciones Generales para que el cambio tenga efecto. Sigue este procedimiento:
  1. Abre el diálogo Opciones Generales.
  1. Desmarca la casilla de verificación Iniciar Automáticamente NVDA Después de Autentificarse en Windows.
  1. Pulsa el botón Aceptar.
  1. Abre el diálogo Opciones Generales de nuevo.
  1. Marca la casilla de verificación Iniciar Automáticamente NVDA Después de Autentificarse en Windows.
  1. Pulsa el botón Aceptar.
* Mejoras de rendimiento para UI Automation incluyendo Explorador de Archivos y Visualizador de Tareas. (#5293)
* NVDA ahora cambia correctamente a modo foco cuando se tabula a controles read-only ARIA grid en modo Exploración para Mozilla Firefox y otros controles basados en Gecko. (#5118)
* NVDA ahora anuncia correctamente "no hay anterior" en lugar de "no hay siguiente" cuando no hay más objetos al hacerse clic izquierdo en una pantalla táctil.
* Corregidos problemas al teclear varias palabras dentro del campo filtro en el diálogo Gestos de Entrada. (#5426)
* NVDA ya no se cuelga en algunos casos cuando se reconecta a una pantalla HumanWare Brailliant BI/B series a través de USB. (#5406)
* En idiomas con caracteres conjunción, las descripciones de carácter ahora funciona como debiera para mayúsculas de caracteres en inglés. (#5375)
* NVDA ya no debería colgarse ocasionalmente al desplegar el Menú de Inicio en Windows 10. (#5417)
* En Skype para Escritorio, ahora se anuncian las notificaciones que se muestran antes de que una notificación anterior desaparezca. (#4841)
* Ahora se anuncian correctamente las notificaciones en Skype para Escritorio 7.12 y posterior. (#5405)
* NVDA ahora anuncia correctamente el foco al cerrar un menú de contexto en algunas aplicaciones tales como Jart. (#5302)
* En Windows 7 y posterior, se anuncia de nuevo el Color en ciertas aplicaciones tales como Wordpad. (#5352)
* Al editar en Microsoft PowerPoint, pulsando intro ahora se anuncia automáticamente el texto introducido tal como una viñeta o número. (#5360)

## 2015.3

Lo reseñable en esta versión incluye el apoyo inicial para Windows 10; la capacidad de deshabilitar la navegación de una sola letra en modo exploración (útil para algunas aplicaciones web); mejoras en Internet Explorer; y correcciones para texto ilegible al escribir en ciertas aplicaciones con el braille habilitado.

### Nuevas Características

* La existencia de errores de ortografía se  anuncia en campos editables para Internet Explorer y otros controles MSHTML. (#4174)
* Ahora se verbalizan muchos más  símbolos matemáticos unicode  cuando aparezcan  en el texto. (#3805)
* Ahora se anuncia automáticamente Buscar sugerencias en la pantalla de inicio de Windows 10 (#5049)
* Soporte para las pantallas braille EcoBraille 20, EcoBraille 40, EcoBraille 80 y EcoBraille Plus. (#4078)
* En modo exploración, ahora puedes  activar y desactivar la navegación con una sola letra pulsando NVDA+shift+espacio. Cuando se desactive, las teclas de una sola letra se pasan a la aplicación, lo cuál es útil para algunas aplicaciones web tales como Gmail, Twitter y Facebook. (#3203)
* Nuevas tablas de transcripción braille: Finlandés de 6 puntos, Irlandés grado 1, Irlandés grado 2, Coreano grado 1 (2006), Coreano grado 2 (2006). (#5137, #5074, #5097)
* Ahora se soporta el teclado QWERTY en la pantalla braille Papenmeier BRAILLEX Live Plus. (#5181)
* Apoyo Experimental para el navegador web Microsoft Edge y el motor de exploración web en Windows 10. (#5212)
* Nuevo idioma: Canadá.

### Canbios

* Actualizado el transcriptor braille liblouis a 2.6.3. (#5137)
* Al intentar instalar una versión más antigua de NVDA de la que está instalada actualmente, ahora se te avisará de que esto no está recomendado y de que NVDA debería desinstalarse completamente antes de proceder. (#5037)

### Corrección de Fallos

* En modo exploración para  Internet Explorer y otros controles MSHTML, la navegación rápida por campos ya no incluye incorrectamente elementos de listas presentacionales. (#4204)
* En Firefox, NVDA ya no anuncia inapropiadamente el contenido de un ARIA tab panel cuando el foco se mueva dentro de él. (#4638)
* En Internet Explorer y otros controles MSHTML, al tabular dentro de secciones, artículos o diálogos  ya no anuncia inapropiadamente todo el contenido en el contenedor. (#5021, #5025)
* Al utilizar las pantallas braille Baum/HumanWare/APH con un teclado braille, la entrada braille ya no detiene su funcionamiento después de pulsar otro tipo de tecla en la pantalla. (#3541)
* En Windows 10, ahora ya no se anuncia información extraña al pulsar alt+tab o alt+shift+tab para cambiar entre aplicaciones. (#5116)
* El texto excrito ya no es ilegible al utilizar ciertas aplicaciones tales como Microsoft Outlook con una pantalla braille. (#2953)
* En modo exploración en Internet Explorer y otros controles MSHTML, ahora se anuncia el contenido correcto cuando un elemento aparece o cambia y se enfoca inmediatamente. (#5040)
* En modo exploración en Microsoft Word, la navegación con una sola tecla ahora se actualiza en la pantalla braille y el cursor de revisión según se esperaba. (#4968)
* En braille, ya no se muestran extraños espacios en braille entre o después de los indicadores para controles y formato. (#5043)
* Cuando una aplicación está respondiendo lentamente y cambias desde esa aplicación, NVDA ahora es mucho más  sensible en otras aplicaciones en más casos. (#3831)
* Las notificaciones de Windows 10 Toast ahora se anuncian como se esperaba. (#5136)
* El valor ahora se anuncia según cambie en ciertos cuadros combinados (UI Automation) donde esto no funcionaba anteriormente.
* En Modo exploración en navegadores web, al tabular ahora se comporta según se espera  después de tabular a un marco de documento. (#5227)
* La pantalla de bloqueo de Windows 10 ahora puede cerrarse utilizando la pantalla táctil. (#5220)
* En Windows 7 y posteriores, el texto ya no es ilegible al teclear en ciertas aplicaciones tales como Wordpad y Skype con una pantalla braille. (#4291)
* En la pantalla de bloqueo de Windows 10, ya  no es posible leer el portapapeles, acceder a  aplicaciones en ejecución con el cursor de revisión, cambiar la configuración de NVDA, etc. (#5269)

### Cambios para Desarrolladores

* Ahora puedes inyectar la entrada bruta desde un teclado de sistema que no se maneja nativamente por Windows (ej.: un teclado QWERTY en una pantalla braille) utilizando la nueva función keyboardHandler.injectRawKeyboardInput . (#4576)
* se ha añadido eventHandler.requestEvents para solicitar eventos particulares que estén bloqueados por omisión; ej.: muestra eventos desde un control específico o ciertos eventos aunque estén en segundo plano. (#3831)
* En lugar de un sólo atributo i18nName, synthDriverHandler.SynthSetting ahora tiene los atributos  displayNameWithAccelerator y displayName separados para evitar el anuncio del acelerador en el grupo de opciones del sintetizador en algunos idiomas.
 * Por compatibilidad con versiones anteriores, en el constructor, displayName es opcional y se deribará de displayNameWithAccelerator si no se proporciona. Sin embargo, si intentas tener un acelerador para una opción, deberían proporcionarse ambos.
 * El atributo i18nName está obsoleto y se podrá eliminar en una versión futura.

## 2015.2

Lo reseñable de esta  versión incluye la capacidad de leer gráficos en  Microsoft Excel y el apoyo para la lectura y la navegación interactiva de contenido matemático.

### Nuevas Características

* Ahora es posible moverse hacia adelante o atrás por frases en Microsoft Word y Outlook con alt+flecha abajo y alt+flecha arriba respectivamente. (#3288)
* Nuevas tablas de transcripción braille para varios idiomas de la India. (#4778)
* En Microsoft Excel, NVDA ahora anuncia cuando una celda tiene contenido desbordante o cortado. (#3040)
* En Microsoft Excel, ahora puedes utilizar la Lista de Elementos (NVDA+f7) para permitir el listado de gráficos, comentarios y fórmulas. (#1987)
* Apoyo para la lectura de gráficos en Microsoft Excel. Para utilizar esto, selecciona el gráfico utilizando la Lista de Elementos (NVDA+f7) y luego utiliza las teclas de cursor para moverte entre los puntos de datos. (#1987)
* Utilizando MathPlayer 4 from Design Science, NVDA ahora puede leer y navegar interactivamente por el contenido matemático en los navegadores web y en Microsoft Word y PowerPoint. Mira la sección "Leyendo Contenido Matemático" en la Guía del Usuario para detalles. (#4673)
* Ahora es posible asignar gestos de entrada (órdenes de teclado, gestos táctiles, etc.) Para todos los diálogos de preferencias de NVDA y opciones de formato de documento utilizando el diálogo Gestos de Entrada. (#4898)

### Cambios

* En el diálogo de formateado de documentos de NVDA, los atajos de teclado para Anunciar listas, Anunciar enlaces, Anunciar números de Línea y Anunciar Nombre de fuente se ha cambiado. (#4650)
* En el diálogo Opciones del ratón de NVDA se han añadido atajos de teclado para Reproducir sonido cuando se mueve el ratón y El brillo controla el volumen del audio de las coordenadas. (#4916)
* Mejoras significativas en el anunciado de nombres de color. (#4984)
* Actualizado el transcriptor braille liblouis a 2.6.2. (#4777)

### Corrección de Fallos

* Las descripciones de carácter ahora se manejan correctamente para conjuntos de caracteres en ciertos idiomas de la India. (#4582)
* Si la opción "Confiar en el Idioma de la Voz al Procesar Caracteres y Símbolos" está activada, el diálogo Pronunciación de Puntuación/Símbolos  ahora utiliza correctamente el idioma de la voz. También, el idioma para el que la pronunciación esté siendo editada se muestra en el título del diálogo. (#4930)
* En Internet Explorer y otros controles MSHTML, los caracteres tecleados ya no se anuncian inapropiadamente en cuadros combinados editables tales como el campo de búsqueda de Google en la página de inicio de Google. (#4976)
* Al seleccionar colores en aplicaciones de Microsoft Office, los nombres de color ahora se anuncian. (#3045)
* La salida braille en Danés ahora funciona de nuevo. (#4986)
* AvPág/rePág pueden utilizarse de nuevo para cambiar diapositivas dentro de una presentación de diapositivas de PowerPoint. (#4850)
* En Skype para Escritorio 7.2 y posteriores, las notificaciones de tecleo ahora se anuncian y se han corregido los problemas imediatamente después de mover el foco fuera de una conversación. (#4972)
* Corregidos problemas al teclear ciertos símbolos de puntuación tales como paréntesis dentro del campo de filtrado en el diálogo Gestos de Entrada. (#5060)
* En Internet Explorer y otros controles MSHTML, al pulsar g o shift+g para navegar por gráficos ahora se incluyen elementos marcados como imágenes para propósitos de accesibilidad (por ejemplo ARIA role img). (#5062)

### Cambios para Desarrolladores

* brailleInput.handler.sendChars(mychar) ya no filtrará un carácter si es igual al carácter anterior, asegurándose que la tecla enviada  se liberó correctamente.
* Los scripts para cambiar los modos táctiles ahora cumplen con las nuevas etiquetas añadidas a touchHandler.touchModeLabels. (#4699)
* Los complementos pueden proveer sus propias implementaciones de presentación matemática. Mira el paquete mathPres para detalles. (#4509)
* Se han implementado órdenes de voz para insertar una ruptura entre palabras y para cambiar el tono, volumen y velocidad. Mira BreakCommand, PitchCommand, VolumeCommand y RateCommand en el módulo speech. (#4674)
 * También hay speech.PhonemeCommand para insertar pronunciaciones específicas, pero las implementaciones actuales sólo soportan un número muy limitado de fonemas.

## 2015.1

Lo reseñable en esta versión  incluye el modo exploración para documentos en Microsoft Word y Outlook; mejoras mayores al soporte para Skype para Escritorio; y correcciones significativas para Microsoft Internet Explorer.

### Nuevas Características

* Ahora puedes añadir símbolos nuevos en el diálogo Pronunciación de Símbolos. (#4354)
* En el diálogo Gestos de Entrada, puedes utilizar el nuevo campo "Filtrar por" para mostrar sólo gestos que contengan palabras específicas. (#4458)
* NVDA ahora anuncia automáticamente texto nuevo en mintty. (#4588)
* En el diálogo  Buscar en modo exploración, ahora hay una opción para realizar una búsqueda sensible a las mayúsculas. (#4584)
* La navegación rápida (h para encabezados etc) y la Lista de Elementos (NVDA+f7) ahora está disponible en documentos de Microsoft Word activando el modo Exploración con NVDA+espacio. (#2975)
* Leyendo mensajes HTML en Microsoft Outlook 2007 y posterior se ha mejorado mucho cuando se activa automáticamente el modo Exploración para esos mensajes. Si el modo exploración no se habilita en algunas situaciones raras, puedes forzarlo con NVDA+espacio. (#2975)
* Los encabezados de columna de tabla en Microsoft word se anuncian automáticamente para tablas donde se haya especificado un encabezado de fila por el autor a través de las propiedades de tabla de Microsoft word. (#4510)
 * Sin embargo, para tablas donde las filas hayan sido fusionadas esto no funcionará automáticamente. En esta situación todavía puedes fijar los encabezados de columna manualmente en NVDA con NVDA+shift+c.
* En Skype para Escritorio, ahora se anuncian las notificaciones. (#4741)
* En Skype para Escritorio, ahora puedes anunciar y revisar los mensajes recientes utilizando NVDA+control+1 hasta NVDA+control+0; por ej.: NVDA+control+1 para el mensaje más reciente y NVDA+control+0 para el décimo más reciente. (#3210)
* En una conversación en Skype para Escritorio, NVDA ahora anuncia cuando un contacto esté tecleando. (#3506)
* NVDA ahora puede instalarse en silencio a través de la línea de órdenes  sin iniciar la copia instalada después de la instalación. Para hacer esto, utiliza la opción --install-silent. (#4206)
* Soporte para las pantallas braille Papenmeier BRAILLEX Live 20, BRAILLEX Live y BRAILLEX Live Plus. (#4614)

### Cambios

* En el diálogo de opciones de Formateado de documentos de NVDA, la opción para anunciar errores de ortografía ahora tiene un atajo de teclado (alt+r). (#793)
* NVDA ahora utilizará el idioma del sintetizador o voz para el procesamiento del carácter y símbolo (incluyendo nombres de símbolos de puntuación), ya el cambio automático de idioma esté activado o no. Para desactivar esta característica para que NVDA utilice de nuevo su idioma de interfaz, desmarca la nueva opción en Opciones de Voz llamada Confiar en el idioma de la Voz al procesar caracteres y símbolos. (#4210)
* Se ha eliminado el soporte para el sintetizador Newfon. Ahora Newfon está disponible como un complemento de NVDA. (#3184)
* Ahora se requiere Skype para Escritorio 7 o posterior para utilizar con NVDA; no se soportan las versiones anteriores. (#4218)
* La descarga de las actualizaciones de NVDA ahora es más segura. (en concreto, la información de actualización se recupera a través de https y el hash del fichero se verifica tras su descarga.) (#4716)
* se ha actualizado eSpeak a la versión 1.48.04 (#4325)

### Corrección de Fallos

* En Microsoft Excel, se maneja el caso cuando las celdas de encabezado de fila y columna se fusionan. Ej.: si A1 y B1 se fusionan, entonces B2 ahora tendrá A1 y B1 anunciado como su encabezado de columna, en lugar de nada en absoluto. (#4617)
* Al editar el contenido  de un cuadro de texto en Microsoft PowerPoint 2003, NVDA anunciará correctamente el contenido de cada línea. Anteriormente las líneas  se indicarían mal,   un cqarácter por cada nuevo párrafo. (#4619)
* Todos los diálogos de NVDA ahora se centran en la pantalla, mejorando la presentación visual y la usabilidad. (#3148)
* En Skype para sobremesa, al introducir un mensaje introductorio para añadir un contacto, la entrada y el movimiento por el texto ahora funciona correctamente. (#3661)
* Cuando el foco se mueva a un elemento nuevo en vistas en árbol en el IDE  Eclipse, si el elemento anteriormente enfocado es una casilla de verificación, ya no la anuncia incorrectamente. (#4586)
* En el diálogo de corrección de ortografía de Microsoft Word, el siguiente error se anunciará automáticamente cuando el anterior se haya cambiado o ignorado utilizando los atajos de teclado respectivos. (#1938)
* El texto puede leerse de nuevo correctamente en lugares tales como la ventana de terminal de Tera Term Pro y documentos en Balabolka. (#4229)
* El foco ahora vuelve correctamente al documento que se esté editando cuando se finalice la composición de entrada de texto en coreano y otros idiomas del este asiático mientras se edita dentro de un marco en Internet Explorer y otros documentos MSHTML. (#4045)
* En el diálogo Gestos de entrada, al seleccionar una distribución de teclado para un gesto de teclado que se añade, ahora pulsando escape se cierra el menú como se debiera en lugar de cerrar el diálogo. (#3617)
* Al eliminar un complemento, el directorio del complemento ahora se borra correctamente después de reiniciar NVDA. Anteriormente, tenías que reiniciar dos veces. (#3461)
* Se corrigieron los principales problemas al utilizar Skype para Escritorio 7. (#4218)
* Cuando envíes un mensaje en Skype para Escritorio, ya no lo lee dos veces. (#3616)
* En Skype para Escritorio, NVDA ya no debería leer ocasionalmente una gran cantidad de mensajes en falso (quizás incluso una conversación entera. (#4644)
* corregido un problema donde la orden de NVDA Anunciar fecha y hora no tenía en cuenta en algunos casos las opciones regionales especificadas por el usuario. (#2987)
* En Modo exploración, ya no se presenta texto sin sentido (abarcando a veces varias líneas) para ciertos gráficos tales como los encontrados en Google Groups. (en concreto, esto ocurría con imágenes codificadas en base 64.) (#4793)
* NVDA ya no debería  congelarse después de unos pocos segundos cuando se saca el foco de una aplicación de estilo Windows 8 Metro cuando permanece suspendido. (#4572)
* El atributo aria-atomic en regiones activas en Mozilla Firefox ahora se tiene en cuenta incluso aunque el mismo elemento atomic cambie. Anteiormente sólo afectaba a elementos descendientes. (#4794)
* El modo exploración reflejará actualizaciones, y las regiones activas se anunciarán,  para documentos en modo exploración dentro de aplicaciones ARIA integradas en un documento en Internet Explorer u otros controles MSHTML. (#4798)
* Cuando el texto cambie o se añada a regiones activas de texto relevante en Internet Explorer y otros controles MSHTML, sólo se anuncia el texto cambiado o añadido, en lugar de todo el texto en el elemento contenedor. (#4800)
* El contenido indicado por el atributo aria-labelledby en elementos en Internet Explorer y otros controles MSHTML reemplaza correctamente el contenido original  donde sea apropiado hacerlo. (#4575)
* Cuando se revisa la ortografía en Microsoft Outlook 2013, ahora se anuncia la palabra mal escrita. (#4848)
* En Internet Explorer y otros controles MSHTML, el contenido dentro de elementos ocultos con visibility:hidden ya no se presenta inapropiadamente en modo exploración. (#4839, #3776)
* En Internet Explorer y otros controles MSHTML, el atributo title en controles form ya no toma inapropiadamente preferencia sobre otras asociaciones de etiqueta. (#4491)
* En Internet Explorer y otros controles MSHTML, NVDA ya no ignora el enfocado de elementos  debido al atributo aria-activedescendant. (#4667)

### Cambios para Desarrolladores

* Actualizado wxPython a 3.0.2.0. (#3763)
* Actualizado Python a 2.7.9. (#4715)
* NVDA ya no se romperá cuando se reinicie después de eliminar o actualizar un complemento que importe speechDictHandler en su módulo installTasks. (#4496)

## 2014.4

### Nuevas Características

* Nuevos idiomas: Español de Colombia, Punjabi.
* Ahora es posible reiniciar NVDA o reiniciar NVDA con los complementos deshabilitados desde el diálogo salir de NVDA. (#4057)
 * NVDA también puede iniciarse con los complementos deshabilitados utilizando la opción de línea de órdenes --disable-addons.
* En diccionarios del habla, ahora es posible especificar que un patrón sólo deba compararse si es una palabra completa; es decir,no ocurre como parte de una palabra más larga. (#1704)

### Cambios

* Si un objeto al que te hayas movido con la navegación de objetos está dentro de un documento en modo exploración, pero el objeto en el que estabas anteriormente no lo estaba, el modo revisión se pone automáticamente en documentos. Con anterioridad esto sólo ocurría si el navegador de objetos se movía debido al cambio del foco. (#4369)
* Las listas de pantallas Braille y de Sintetizadores en sus respectivos cuadros de diálogo ahora se ordenan alfabéticamente excepto para Sin braille/Sin voz,  las cuales ahora están al fondo. (#2724)
* Actualizado el transcriptor braille liblouis a 2.6.0. (#4434, #3835)
* En modo exploración, al pulsar e y shift+e para  navegar a campos de edición ahora se incluyen cuadros combinados editables. Esto incluye el cuadro buscar en la última  versiónn de Google Search. (#4436)
* Al hacer Clic en el icono de NVDA en el Area de Notificación con el botón izquierdo del ratón ahora se abre el menú NVDA en lugar de no hacer nada. (#4459)

### Corrección de Fallos

* Al mover atrás el foco en un documento en modo exploración (ej.: yendo a una pestaña a una página web ya abierta) el cursor de revisión se coloca apropiadamente en el cursor virtual, en lugar de en el control enfocado (ej.: en un enlace más cercano). (#4369)
* En presentaciones de diapositivas en Powerpoint, el cursor de revisión sigue correctamente al cursor virtual. (#4370)
* En Mozilla Firefox y otros navegadores basados en Gecko, el contenido nuevo dentro de una región activa se anunciará incluso si el contenido nuevo tiene un tipo diferente de ARIA activa usable a la región activa padre. Ej.: Contenido marcado como assertive se añade a una región activa marcada como polite. (#4169).
* En Internet Explorer y otros controles MSHTML, en algunos casos en los que un documento esté contenido dentro de otro documento ya no se evita que el usuario pueda acceder  a algunos de los contenidos (en concreto, framesets dentro de framesets). (#4418)
* NVDA ya no se cuelga cuando intenta utilizar una pantalla braille Handy Tech en algunos casos. (#3709)
* En Windows Vista, ya no se muestra un expúreo diálogo "Entry Point Not Found" mostrado en varios casos como cuando se inicia NVDA desde el atajo del escritorio o a través de la tecla de acceso directo. (#4235)
* Se han corregido problemas serios con controles de texto editable en diálogos en versiones recientes de Eclipse. (#3872)
* En Outlook 2010, ahora mover el cursor funciona como se espera en el campo de ubicación de citas y solicitudes de reunión. (#4126)
* Dentro de una región activa, el contenido que esté marcado como no activo (ej.: aria-live="off") ahora se ignora correctamente. (#4405)
* Al anunciar el texto de una barra de estado que tiene un nombre, el nombre ahora se separa correctamente de la primera palabra del texto de la barra de estado. (#4430)
* En campos de introdución de palabras clave con la verbalización de palabras al escribir activada, ya no se anuncian varios asteriscos inútilmente al comenzar palabras nuevas. (#4402)
* En la lista de mensajes de Microsoft Outlook, los elementos ya no se anuncian inútilmente como elementos de Fecha. (#4439)
* Al seleccionar texto en el control de edición de código en el IDE Eclipse, ya no se anuncia toda la selección cada vez que la selección cambia. (#2314)
* Varias versiones de Eclipse, tales como Spring Tool Suite y la versión incluída en el paquete Android Developer Tools, ahora se reconocen como Eclipse y se manejan apropiadamente. (#4360, #4454)
* El seguimiento del ratón y la exploración táctil en Internet Explorer y otros controles MSHTML (incluyendo muchas aplicaciones Windows 8) ahora es mucho más preciso en pantallas de alta DPI o cuando se cambia el zoom de documento. (#3494)
* El seguimiento del ratón y la exploración táctil en Internet Explorer y otros controles MSHTML ahora anuncia la etiqueta de más botones. (#4173)
* Al utilizar una pantalla braille Papenmeier BRAILLEX con BrxCom, las teclas en la pantalla ahora funcionan como se esperaba. (#4614)

### Cambios para Desarrolladores

* Para ejecutables que albergan muchas aplicaciones diferentes (ej.: javaw.exe), ahora el código puede proporcionarse para que cargue app modules específicos para cada aplicación en lugar de cargar el mismo app module para todas las aplicaciones incluídas. (#4360)
 * Mira  la documentación del código para appModuleHandler.AppModule para más detalles.
 * Se ha implementado el soporte para javaw.exe.

## 2014.3

### Nuevas Características

* Los sonidos que se ejecutan cuando NVDA arranca y sale se pueden desactivar a través de una nueva opción en el cuadro de diálogo Opciones generales. (#834)
* Se puede acceder a la ayuda para los complementos desde el Administrador de complementos para los que lo soporten. (#2694)
* Soporte para el Calendario en Microsoft Outlook 2007 y superior (#2943) incluyendo:
 * Anunciado de la hora actual al moverte con las flechas.
 * Indicado de si la hora seleccionada está dentro de alguna cita.
 * anunciado de la cita seleccionada al pulsar tab.
 * El filtrado inteligente de la hora de manera que sólo se anuncia la fecha si la nueva hora o cita seleccionada es en un día diferente a la última.
* Mejorado el soporte para la bandeja de entrada y otras listas de mensajes en Outlook 2010 y posterior (#3834) incluyendo:
 * La capacidad de silenciar los encabezados de columna (de, Asunto etc) desactivando la opción Anunciar Encabezados de Fila y Columna de Tabla en Opciones de Formateado de Texto.
 * La capacidad de utilizar las órdenes de navegación de tabla (control + alt + flechas) para moverse a lo largo de las columnas individuales.
* Microsoft word: Si una imagen en línea no tiene puesto ningún texto alternativo, NVDA anunciará el título de la imagen, si el autor ha proporcionado uno. (#4193)
* Microsoft Word: NVDA ahora puede anunciar el sangrado de párrafo con  la orden anunciar formato (NVDA+f). También puede anunciarse automáticamente cuando la nueva opción Anunciar Sangría de Párrafo esté habilitada en  las opciones de Formato de Documento. (#4165)
* Se anuncia el texto insertado automáticamente tal como una nueva viñeta, número o sangría cuando se pulse intro en documentos y campos de texto editables. (#4185)
* Microsoft word: Al pulsar NVDA+alt+c se anunciará el texto de  un comentario si el cursor está dentro de uno. (#3528)
* Mejorado el soporte para la lectura automática de encabezados de fila y columna en Microsoft Excel (#3568) incluyendo:
 * Soporte de los rangos de nombres definidos de Excel para identificar las celdas de encabezado (compatible con el lector de pantalla Jaws)
 * Las órdenes fijar encabezado de columna (NVDA+shift+c) y fijar encabezado de fila (NVDA+shift+r) ahora almacenan las opciones en la hoja de cálculo tal que estén disponibles la siguiente vez que la hoja se abra  y estarán disponibles para otros lectores de pantalla que soporten el esquema de rango de nombres definidos.
 * Estas órdenes ahora también pueden utilizarse múltiples veces por hoja para fijar diferentes encabezados para diferentes regiones.
* Soporte para la lectura automática de  encabezados de columna y fila en Microsoft Word (#3110) incluyendo:
 * Soporte de marcas de MS Word para identificar celdas de encabezado (compatible con el lector de pantalla Jaws)
 -  las órdenes fijar encabezado de columna (NVDA+shift+c) y fijar encabezado de fila (NVDA+shift+r) mientras se esté en la primera celda de encabezado en una tabla permiten decir a NVDA que esos encabezados  deberían anunciarse automáticamente.  Las opciones se almacenan en el documento tal que estén disponibles la siguiente vez que el documento se abra, y estarán disponibles para otros lectores de pantalla que soporten el esquema de marcas.
* Microsoft Word: Anuncia la distancia desde el borde izquierdo de la página cuando se pulse la tecla tab. (#1353)
* Microsoft Word: se proporciona información en voz y en braille para la mayoría de teclas de atajo disponibles  para el formato (negrita, cursiva, subrayado,  alineación,  nivel de esquema,superíndice, subíndice y tamaño de fuente ). (#1353)
* Microsoft Excel: Si la celda seleccionada contiene comentarios, pueden ser ahora anunciados pulsando NVDA+alt+c (#2920)
* Microsoft Excel: se Proporciona un diálogo específico para NVDA para editar los comentarios sobre la celda seleccionada al pulsar la orden de Excel shift + f2 para acceder al modo de edición de comentarios. (#2920)
* Microsoft Excel: información en voz y en braille  para muchos más atajos de teclado para movimientos de selección (#4211) incluyendo:
 * Movimiento de página Vertical (Re Pág y Av Pág)
 * Movimiento de página Horizontal (alt+RePág y alt+AlPág)
 * Ampliar la selección (las teclas anteriores añadiendo Shift).
 * Selección de la región actual (control+shift+8)
* Microsoft Excel: anunciar  alineación vertical y horizontal para las céldas con la orden anunciar formato(NVDA+f) y automáticamente si la opción Anunciar Alineación en las opciones Forrmato de Documentos está activada. (#4212)
* Microsoft Excel: anunciar el estilo de una celda con la opción anunciar formato  (NVDA+f) y automáticamente si la opción Anunciar Estilo en las opciones de Formato de documento está activada. (#4213)
* Microsoft Powerpoint: cuando se mueven las formas de una diapositiva con las teclas de flecha, ahora se anuncia la ubicación actual de la forma (#4214) incluyendo:
 * Se anuncia la distancia entre la forma y cada uno de los bordes de la diapositiva.
 * Si la forma cubre o está cubierta por otra forma, entonces la distancia superpuesta, y la otra forma se anuncian.
 * Para anunciar esta información en cualquier momento sin mover una forma, pulsa la orden anunciar localización (NVDA+suprimir)
 * Al seleccionar una forma, si está cubierta por otra forma, se anunciará el estado oculto.
* La orden anunciar localización (NVDA+suprimir) es más específica al contexto en algunas situaciones. (#4219):
 * En los campos de edición estándar y en el modo exploración, se anuncian la posición del cursor como un porcentaje del contenido, y sus coordenadas de pantalla .
 * En formas en presentaciones de Powerpoint, se anuncia la posición de la forma relativa a la diapositiva  y otras formas.
 * Al pulsar   esta orden dos veces se producirá el antiguo comportamiento del anunciado de la información de localización para todo el control.
* Nuevo idioma: Catalán.

### Cambios

* Actualizado el transcriptor braille liblouis a 2.5.4. (#4103)

### Corrección de Fallos

* En los navegadores Google Chrome y los basados en él, ciertos pedazos  de texto (tales como aquellos con énfasis) ya no se repiten cuando se anuncie el texto de una alerta o diálogo. (#4066)
* En modo exploración en aplicaciones de Mozilla, al pulsar intro sobre un botón, etc. ya no falla al activarlo (o activa el control erróneo) en ciertos casos tales como los botones en la parte superior de Facebook. (#4106)
* Ya no se anuncia información inútil al tabular por iTunes. (#4128)
* En ciertas listas en iTunes tales como la de música, al moverse al elemento siguiente utilizando la navegación de objetos ahora funciona correctamente. (#4129)
* Los elementos HTML se consideran encabezados  debido a que las marcas WAI ARIA ahora están incluidas en la lista de elementos del modo exploración y la navegación rápida de documentos de Internet Explorer. (#4140)
* Al seguir enlaces a la misma página en versiones recientes de Internet Explorer ahora nos movemos allí correctamente y se anuncia la posición de destino en los documentos en modo exploración. (#4134)
* Microsoft Outlook 2010 y superior: se mejora todo el acceso a diálogos seguros tales como los nuevos perfiles y cuadros de diálogo de configuración de correo. (#4090, #4091, #4095)
* Microsoft Outlook: se disminuye la verbosidad inútil de las barras de herramientas de órdenes cuando se navega a través de ciertos diálogos. (#4096, #3407)
* Microsoft word: al tabular por una celda en blanco en una tabla ya no se anuncia incorrectamente saliendo de tabla. (#4151)
* Microsoft Word: El primer carácter más allá de fin de una tabla (incluyendo una nueva línea en blanco), ya no se considera incorrectamente que está dentro de la tabla. (#4152)
* Diálogo del corrector de ortografía de Microsoft Word 2010: Anuncia deletreando la palabra  real en lugar de sólo la primera palabra  en negrita. (#3431)
* En modo exploración en Internet Explorer y otros controles MSHTML, al tabular o utilizar la navegación de una sola tecla para moverte a campos  de formulario anuncia la etiqueta de nuevo en muchos casos donde no debería (en concreto, cuando se utilizan elementos de la etiqueta HTML). (#4170)
* Microsoft Word: el anunciado sobre la existencia y ubicación de comentarios es más preciso. (#3528)
* Se mejora la navegación de algunos cuadros de diálogo en los productos de MS Office como Word, Excel y Outlook ya no se anuncian  barras de herramientas de control de contenedores que no son útiles para el usuario. (#4198)
* Los paneles de tareas tales como el administrador del portapapeles o de recuperación de ficheros ya no parecen obtener el foco accidentalmente al abrir una aplicación tal como Microsoft Word o Excel, lo que a veces provocaba que el usuario tuviera que salir y volver a la aplicación para utilizar el documento u hoja de cálculo.  (#4199)
* NVDA ya no falla al ejecutarse en los últimos sistemas operativos Windows, si el idioma de Windows del usuario se establece en Serbio (Latino). (#4203)
* Al pulsar BloqueoNumérico mientras se esté en el modo Ayuda de Entrada ahora se conbmutará el bloqueoNumérico correctamente, en lugar de que el teclado y el sistema operativo se desincronicen con respecto al estado de esta tecla. (#4226)
* En Google Chrome, el título del documento se anuncia de nuevo al cambiar las pestañas. En NVDA 2014.2, esto no ocurrió en algunos casos. (#4222)
* En Google Chrome y navegadores basados en Chrome, la URL del documento ya no se informa cuando se anuncia el documento. (#4223)
* Al ejecutar leer todo con el sintetizador Sin voz seleccionado (útil para realizar pruebas automatizadas), leer todo ahora se completará en lugar de detenerse tras las primeras pocas líneas. (#4225)
* Diálogo Firmas de Microsoft Outlook: el campo de edición firma ahora es accesible, lo que permite el seguimiento completo de cursor y la detección de formato. (#3833)
* Microsoft Word: Al leer la última línea de una celda de tabla, ya no se lee toda la celda de la tabla. (#3421)
* Microsoft Word: Al leer la primera o la última línea de una tabla de índice, ya no se lee toda la tabla de índice. (#3421)
* Al verbalizar palabras al escribir y en algunos otros casos, las palabras ya no se separan incorrectamente en marcas tales como signos vocálicos y virama en Idiomas de la India. (#4254)
* Los campos numéricos  de texto editable en GoldWave ahora se manejan correctamente. (#670)
* Microsoft Word: al moverse por párafo con control+flecha abajo / control+flecha arriba, ya no es necesario pulsarlos dos veces si nos movemos por listas numeradas o de viñetas. (#3290)

### Cambios para Desarrolladores

* NVDA ahora cuenta con el apoyo unificado de documentación para los complementos. Véase la sección de complementos de la documentación de la Guía del desarrollador para obtener más información. (#2694)
* Al proporcionar  vínculos de gestos en un ScriptableObject a través de __gestures, ahora es posible proporcionar la palabra clave None como el script. Esto lanza el gesto en cualquier clase base. (#4240)
* Ahora es posible cambiar la tecla de atajo utilizada para iniciar NVDA en traducciones donde el atajo normal causa problemas. (#2209)
 * Esto se hace a través de gettext.
 * Ten en cuenta que el texto para la opción Crear atajo de escritorio en el diálogo Instalar NVDA, así como el atajo de teclado en la Guía del Usuario, también debe actualizarse.

## 2014.2

### Nuevas Características

* Ahora es posible el anunciado de la selección de texto en algunos campos de edición personalizada donde se utiliza información de la pantalla. (#770)
* En aplicaciones  Java accesibles, ahora se anuncia la información de posición para botones de opción y otros controles que expongan información de grupo. (#3754)
* En aplicaciones Java accesibles, ahora se anuncian los atajos de teclado para controles que los tengan. (#3881)
* En modo exploración, las etiquetas  en las regiones ahora se anuncian. También se incluyen en el diálogo Lista de Elementos. (#1195)
* En modo exploración, las regiones etiquetadas ahora se tratan como regiones. (#3741)
* En documentos y aplicaciones en Internet Explorer, las regiones activas (parte del W3c ARIA standard) ahora se soportan, permitiendo así a los autores web  marcar contenido particular para que se verbalice de forma automática según cambia. (#1846)

### Cambios

* Al salir de un diálogo o aplicación dentro de un documento en modo exploración, el nombre y tipo del documento en modo exploración ya no se anuncia. (#4069)

### Corrección de Fallos

* El menú estándar de sistema de Windows ya no se silencia accidentalmente en aplicaciones Java. (#3882)
* Cuando se copie texto desde la revisión de pantalla, los saltos de línea ya no se ignoran. (#3900)
* Los objetos de espacio en blanco sin sentido ya no se anuncian en algunas aplicaciones cuando el foco  cambie o cuando se utilice la navegación de objetos con la revisión simple habilitada. (#3839)
* Los cuadros de mensaje y otros diálogos producidos por NVDA causan nuevamente la cancelación de la verbalización anterior antes de anunciar el diálogo.
* En modo exploración, las etiquetas de controles tales como enlaces y botones ahora se procesan correctamente cuando la etiqueta se haya reemplazado por el autor con fines de accesibilidad (específicamente, la utilización de aria-label o de aria-labelledby). (#1354)
* En modo exploración  en Internet Explorer, el texto contenido dentro de un elemento marcado como presentación (aria-presentation) ya no se ignora inapropiadamente. (#4031)
* Ahora es posible de nuevo teclear texto en vietnamita utilizando el programa Unikey. Para hacer esto, desmarca la casilla de verificación Manejar teclas desde otras aplicaciones, añadido al diálogo Opciones de Teclado de NVDA. (#4043)
* En modo exploración, los elementos de menú verificables y de opción se anuncian como controles en lugar de como texto admite clic. (#4092)
* NVDA ya no cambia incorrectamente desde modo foco a modo exploración cuando está enfocado un elemento de menú de opción o verificable. (#4092)
* En Microsoft PowerPoint con Verbalizar palabras al escribir habilitado, los caracteres eliminados con retroceso ya no se anuncian como parte de la palabra escrita. (#3231)
* En los diálogos de opciones de Microsoft Office 2010, las etiquetas de los cuadros combinados se anuncian correctamente. (#4056)
* En modo exploración en aplicaciones de Mozilla, la utilización de órdenes de navegación rápida para moverse al botón o al ccampo de edición siguiente o anterior ahora incluye botones conmutables como se esperaba. (#4098)
* El contenido de alertas en aplicaciones Mozilla ya no se anuncia dos veces. (#3481)
* En modo exploración, los contenedores  y las regiones ya no se repiten inapropiadamente mientras se navegue dentro de ellos al mismo tiempo que el contenido de la página esté cambiando (por ejemplo al navegar por los sitios web de Facebook y Twitter). (#2199)
* NVDA se recupera en más casos al cambiar desde las aplicaciones que dejan de responder. (#3825)
* El cursor (punto de inserción) se actualiza correctamente de nuevo cuando se da una orden VerbalizarTodo mientras se está en texto editable dibujado directamente en la pantalla. (#4125)

## 2014.1

### Nuevas Características

* Soporte para Microsoft PowerPoint 2013. Ten en cuenta que la Vista protegida no está soportada. (#3578)
* En Microsoft word y Excel, NVDA ahora puede leer el símbolo seleccionado cuando se elijan símbolos utilizando el diálogo Insertar Símbolos. (#3538)
* Ahora es posible elegir si el contenido en documentos debería identificarse  como cliqueable, a través de una nueva opción en el diálogo Formateado de Documentos. Esta opción está activada por defecto (comportamiento anterior). (#3556)
* Soporte para pantallas braille conectadas a través de Bluetooth en un ordenador ejecutando el  Software de Widcomm Bluetooth. (#2418)
* Cuando se edita texto en PowerPoint, ahora se anuncian los hipervínculos. (#3416)
* Cuando se esté en aplicaciones ARIA o diálogos en la web, ahora es posible forzar a NVDA para que cambie a modo exploración con NVDA+espacio siguiendo la navegación de estilos de documento de la aplicación o del diálogo. (#2023)
* En Outlook Express / Windows Mail / Windows Live Mail, NVDA ahora anuncia si un mensaje tiene un adjunto o está marcado. (#1594)
* Al navegar por tablas en aplicaciones Java accesibles, ahora se anuncian las coordenadas de fila y columna, incluyendo  los encabezados de columna y  fila si existen. (#3756)

### Cambios

* Para las pantallas braille Papenmeier, se ha eliminado la orden mover a revisión plana/foco. Los usuarios pueden asignar sus propias teclas usando el diálogo de gestos de entrada. (#3652)
* NVDA ahora se basa en la versión 11 del Microsoft VC runtime, lo que significa que ya no se puede ejecutar en sistemas operativos anteriores a Windows XP Service Pack 2 o Windows Server 2003 Service Pack 1.
* En el nivel de puntuación Alguna ahora se verbalizarán los caracteres asterisco(*) y más (+). (#3614)
* Actualizado eSpeak a la versión 1.48.04, que incluye muchas correcciones de lenguaje y corrige varios problemas. (# 3842, # 3739)

### Corrección de Fallos

* Cuando te muevas o selecciones  celdas en Microsoft Excel, NVDA ya no debería  anunciar inapropiadamente la antigua celda en lugar de la nueva celda cuando Microsoft Excel esté lento al mover la selección. (#3558)
* NVDA maneja adecuadamente la apertura de una lista desplegable en una celda en Microsoft Excel mediante el menú contextual. (#3586)
* Ahora se muestra apropiadamente el Nuevo contenido de la página en las páginas de la tienda en iTunes 11 en modo exploración cuando se siga un enlace en la tienda o al abrir la tienda inicialmente. (#3625)
* Los botones para la vista previa de las canciones en la tienda de iTunes 11 ahora muestran su etiqueta en modo exploración. (#3638)
* En modo exploración en Google Chrome, las etiquetas de las casillas de verificación y de los botones de opción ahora se procesan correctamente. (#1562)
* En Instantbird, NVDA ya no anuncia información inútil cada vez que te muevas a un contacto de la lista de contactos. (#2667)
* En modo exploración en Adobe Reader, ahora se procesa el texto correcto para los botones, etc. donde la etiqueta se ha reemplazado por el uso de un tooltip u otro recurso. (#3640)
* En modo exploración en Adobe Reader, los gráficos extraños que contienen el texto "mc-ref" ya no se procesan. (#3645)
* NVDA ya no anuncia todas las celdas en Microsoft Excel como subrayadas en su información de formato. (#3669)
* Ya no se muestran caracteres sin sentido en documentos de modo exploración tales como los que se encuentran en el rango de uso privado de Unicode. En algunos casos estos detenían el mostrado de etiquetas más útiles. (#2963).
* La composición de entrada para la introducción de caracteres del este asiático ya no falla en PuTTY (#3432)
* Al navegar por un documento después de una cancelación de Verbalizar todo ya no resulta en que NVDA anuncie a veces incorrectamente que se ha abandonado un campo (tal como una tabla) más abajo en el documento en que Verbalizar todo nunca estuvo hablando en realidad (#3688)
* Cuando se utilicen órdenes rápidas del modo exploración mientras se esté en verbalizar todo con la lectura superficial activada, NVDA anuncia con más precisión el nuevo campo (por ejemplo, ahora dice que un encabezado es un encabezado, y no sólo el texto). (#3689)
* En el salto al final o al comienzo de un contenedor las órdenes de navegación rápida ahora afectan a la opción lectura superficial durante verbalizar todo (es decir, que ya no cancelarán el verbalizar todo actual). (#3675)
* Los nombres de los gestos táctiles listados en el diálogo Gestos de entrada de NVDA ahora son más amigables y están traducidos. (#3624)
* NVDA ya no hace que ciertos programas se bloqueen cuando se mueva el puntero del ratón sobre sus controles de edición enriquecidos (TRichEdit). Programas incluyendo Jarte 5.1 y BRfácil. (#3693, #3603, #3581)
* En Internet Explorer y otros controles MSHTML, los contenedores tales como tablas marcadas como presentación por ARIA ya no se informan al usuario. (#3713)
* en Microsoft Word, NVDA ya no repite de manera inapropiada la fila de la tabla y la información de la columna de una celda en una pantalla braille varias veces. (#3702)
* En idiomas que utilicen  un espacio como un dígito separador de grupos de miles  tal como en el  Francés y en el Alemán, los números de trozos separados de texto ya no se pronuncian como un solo número. Esto era particularmente problemático  para las celdas de tabla que contenían números. (#3698)
* El braille ya no falla a veces al actualizarse cuando se mueve el cursor del sistema en Microsoft Word 2013. (#3784)
* Cuando se esté posicionado sobre el primer carácter de un encabezado en Microsoft Word, el texto se comunica como un encabezado  (incluyendo el nivel) y ya no desaparece de una pantalla braille. (#3701)
* Cuando se dispara un perfil de configuración por una aplicación y esa aplicación se cierra, NVDA ya no falla a veces al desactivar el perfil. (#3732)
* Cuando se escribe con la entrada Asiática en un control dentro del propio NVDA (ej.: en el diálogo Buscar en el modo exploración), "NVDA" ya no se anuncia incorrectamente en lugar del candidato. (#3726)
* Ahora se anuncian las pestañas en el diálogo Opciones de Outlook 2013. (#3826)
* Mejorado el soporte  para  regiones ARIA live en Firefox y otras aplicaciones Gecko de Mozilla:
 * Soporte para actualizaciones aria-atomic y filtrado de actualizaciones aria-busy (#2640)
 * Se incluye El texto alternativo (tal como el atributo alt o aria-label) si no hay otro texto útil. (#3329)
 * Las actualizaciones Live region ya no se silencian si se producen al mismo tiempo que el desplazamiento del foco. (# 3777)
* Ciertos elementos de presentación en Firefox y otras aplicaciones  Gecko de Mozilla ya no se muestran inapropiadamente en modo exploración (expresamente cuando el elemento se marcó con aria-presentation pero también es enfocable). (#3781)
* Mejora del rendimiento al navegar por un documento en Microsoft Word con la corrección ortográfica activada. (#3785)
* Varias correcciones al soporte para aplicaciones Java accesibles:
 * El control inicialmente enfocado en un marco o  diálogo ya no falla al ser anunciado cuando el marco o diálogo pasa a primer plano. (#3753)
 * Ya no se anuncia información de posición inútil para los botones de opción (por ejemplo 1 de 1). (# 3754)
 * Mejor anunciado de los controles JComboBox (ya no se anuncia html, una mejor información de los estados expandidos y colapsados). (#3755)
 * Se incluye más texto en los cálculos automáticos de título de diálogo. (# 3857)
 * Los cambios del  nombre, valor o descripción del control enfocado ahora se anuncian con mayor precisión. (#3770)
* Se  Arregla un cuelgue en NVDA visto en Windows 8 al enfocar ciertos controles RichEdit que contienen grandes cantidades de texto(por ejemplo en el Visualizador de registro de NVDA, windbg). (#3867)
* En sistemas con una configuración de pantalla de alta DPI (que se produce de forma predeterminada para muchas pantallas modernas), NVDA ya no lleva el ratón al lugar equivocado en algunas aplicaciones. (#3758, #3703)
* Se ha corregido un problema ocasional al navegar por la web donde NVDA dejaba de funcionar correctamente hasta que se reiniciaba, a pesar de que no se bloqueaba o se congelaba. (# 3804)
* Ahora Se puede utilizar una pantalla bralle Papenmeier incluso si nunca se hubiese conectado a través de USB. (# 3712)
* NVDA ya no se  cuelga cuando los modelos antiguos de las pantallas braille Papenmeier BRAILLEX se seleccionan sin una pantalla conectada.

### Cambios para Desarrolladores

* Los AppModules ahora contienen las propiedades productName y productVersion. Esta información también se incluye ahora en la Información del desarrollador (NVDA+f1). (#1625)
* En la consola de Python, ahora puedes pulsar  la tecla tab para completar el identificador actual. (#433)
 * Si hay varias posibilidades, puedes pulsar el tabulador por segunda vez para elegir de entre una lista.

## 2013.3

### Nuevas Características

* Los campos de formulario  ahora se anuncian en documentos de Microsoft word. (#2295)
* NVDA ahora puede anunciar información de revisión en Microsoft Word cuando el seguimiento de cambios esté activado. Ten en cuenta que Anunciar revisiones del editor en en diálogo opciones de documentos de NVDA (desactivado por omisión) debe estar habilitado también para que se anuncien. (#1670)
* Las listas desplegables en Microsoft Excel 2003 a 2010 ahora se anuncian cuando se abran y naveguen. (#3382)
* una nueva opción 'Permitir Lectura superficial en Verbalizar Todo' en el diálogo Opciones de Teclado permite la navegación por un documento con las órdenes de navegación rápida del modo exploración y movimientos de línea / párrafo, mientras permanece leyendo todo. Esta opción está desactivada de forma predeterminada. (#2766)
* Ahora hay un diálogo Gestos de Entrada para permitir la fácil personalización de los gestos de entrada(tales como teclas en el teclado) para órdenes de NVDA. (#1532)
* Ahora puedes tener diferentes opciones para diferentes situaciones utilizando perfiles de configuración. Los perfiles se pueden activar de forma manual o automática(ej.: para una aplicación en particular). (#87, #667, #1913)
* En Microsoft Excel, las celdas que son enlaces ahora se anuncian como enlaces. (#3042)
* En Microsoft Excel, ahora se anuncia al usuario la existencia de comentarios en una celda. (#2921)

### Corrección de fallos

* Zend Studio ahora funciona igual que Eclipse. (#3420)
* El cambio de estado de ciertas casillas de verificación en el diálogo de reglas de correo de Microsoft Outlook 2010 ahora se anuncia automáticamente. (#3063)
* NVDA ahora anunciará el estado fijado para controles fijos tales como  pestañas en Mozilla Firefox. (#3372)
* Ahora es posible vincular scripts a gestos de teclado que contengan las teclas Alt y/o Windows como modificadoras. Anteriormente, si se hacía esto, la ejecución del script causaba la activación del menú Inicio o de la barra de menú. (#3472)
* Al seleccionar texto en documentos en modo exploración (por ejemplo al utilizar control+shift+fin) ya no causa que se cambie la distribución de teclado en sistemas con varias distribuciones de teclado instaladas. (#3472)
* Internet Explorer ya no debería colgarse o volverse inusable  cuando se cierra NVDA. (#3397)
* El movimiento físico y otros eventos en algunos ordenadores modernos ya  no se trata como pulsaciones de teclas inapropiadas. Anteriormente, esto silenciaba la voz y algunas veces hacía funcionar órdenes de NVDA. (#3468)
* NVDA ahora se comporta como se esperaba enPoedit 1.5.7. Los usuarios que utilicen versiones anteriores necesitarán actualizar. (#3485)
* NVDA ahora puede leer documentos protegidos en Microsoft Word 2010,  no causando ya que Microsoft Word se bloquee. (#1686)
* Si se da un parámetro de línea de comando desconocido al ejecutar el paquete de distribución de NVDA, ya no se provoca un bucle sin fin de diálogos de mensajes de error. (# 3463)-
* NVDA ya no falla al anunciar el texto alternativo de los gráficos y objetos en Microsoft Word si el texto alternativo contiene comillas u otros caracteres no estándar. (#3579)
* El número de elementos de ciertas listas horizontales en modo exploración ahora está correcto. Anteriormente podía haber sido el doble de la cantidad real. (#2151)
* Al presionar control+e en una hoja de cálculo de Microsoft Excel, ahora se anunciará la selección actualizada. (#3043)
* NVDA ahora puede leer correctamente los documentos XHTML en Microsoft Internet Explorer y otros controles MSHTML. (#3542)
* Diálogo de Opciones de teclado: si no se ha seleccionado ninguna tecla para ser utilizada como la tecla NVDA, se presenta un error al usuario cuando se descarte el diálogo. Al menos una de las teclas debe ser seleccionada para el uso apropiado de NVDA. (#2871)
* En Microsoft Excel, NVDA ahora anuncia celdas fusionadas de manera diferente a múltiples celdas seleccionadas. (#3567)
* El cursor de modo exploración  ya no se coloca incorrectamente cuando se abandona un diálogo o aplicación dentro del documento. (#3145)
* Se ha solucionado un problema por el que el controlador de  las pantallas braille series de la HumanWare Brailliant BI / B no se presenta como una opción en el cuadro de diálogo Opciones de Braille en algunos sistemas, a pesar de que dicha pantalla se conecte a través de USB.
* NVDA ya no falla  al cambiar a revisión de pantalla cuando el navegador de objetos no tenga ninguna ubicación real en la pantalla. En este caso el cursor de revisión ahora se coloca en la parte superior de la pantalla. (#3454)
* Se ha solucionado un problema por el que el controlador de la pantalla braille de Freedom Scientific falla cuando el puerto se establece en USB, en algunas circunstancias. (#3509, #3662)
* Se ha solucionado un problema por el que no se detectaron teclas en braille de Freedom Scientific en algunas circunstancias. (#3401, #3662)

### Cambios para Desarrolladores

* Puedes especificar la categoría a mostrar al usuario por los scripts utilizando el atributo scriptCategory en clases ScriptableObject y el atributo category en métodos de script. Mira la documentación para baseObject.ScriptableObject para más detalles. (#1532)
* config.save está en desuso y puede ser eliminada en futuras versiones. Utiliza config.conf.save en su lugar. (#667)
* config.validateConfig está en desuso y puede ser eliminada en futuras versiones. Los complementos que necesiten esto deben proporcionar su propia implementación. (#667, #3632)

## 2013.2

### Nuevas Características

* Soporte para el Chromium Embedded Framework, que es un control de navegador web utilizado en varias aplicaciones. (#3108)
* Nueva variante de voz de eSpeak: Iven3.
* En Skype, se anuncian automáticamente los mensajes nuevos de chat mientras la conversación esté enfocada. (#2298)
* Soporte para Tween, incluyendo el anunciado de los nombres de pestaña y menor nivel de detalle cuando se lean los twits.
* Ahora puedes deshabilitar el mostrado de mensajes de NVDA en una pantalla braille configurando la duración del mensaje a 0 en el diálogo de Opciones de Braille. (#2482)
* En el administrador de complementos, ahora hay un botón Obtener Complementos para abrir el sitio web de Complementos de NVDA donde puedes examinar y descargar los complementos disponibles. (#3209)
* En el diálogo de bienvenida de NVDA que siempre aparece la primera vez que  ejecutas NVDA, ahora puedes especificar si NVDA se inicia automáticamente después de autentificarte en Windows. (#2234)
* El modo silencioso se habilita automáticamente cuando se utilice Dolphin Cicero. (#2055)
* Ahora se soporta la versión Windows x64 de Miranda IM/Miranda NG. (#3296)
* Ahora se anuncian automáticamente las sugerencias de búsqueda en  la pantalla de inicio de  Windows 8.1. (#3322)
* Soporte para navegar y editar hojas de cálculo en Microsoft Excel 2013. (#3360)
* Las pantallas braille Freedom Scientific Focus 14 Blue y Focus 80 Blue, así como la Focus 40 Blue en ciertas configuraciones que no se soportaba previamente, ahora se soportan cuando se conecten a través de Bluetooth. (#3307)
* Ahora se anuncian las sugerencias de Autocompletado en Outlook 2010. (#2816)
* Nuevas tablas de transcripción braille: Braille computerizado Inglés (U.K.), Coreano grado 2, braille ruso para código informático.
* Nuevo idioma: Farsi. (#1427)

### Cambios

* En una pantalla táctil, realizando un deslizamiento con un solo dedo a la izquierda o a la derecha cuando se esté en modo objeto, ahora te mueves hacia atrás o adelante por  todos los objetos y no sólo por aquellos que estén en el mismo contenedor. Utiliza  un deslizamiento con 2 dedos a la izquierda o a la derecha para realizar la acción original de anterior/siguiente objeto limitado al actual contenedor.
* la casilla de verificación Anunciar tablas de diseño que se encuentra en el diálogo Opciones de modo exploración  ahora se ha renombrado como Incluir Tablas de Diseño para reflejar que la navegación rápida no las localizará si la casilla está desmarcada. (#3140)
* La revisión plana ha sido reemplazada por los modos de revisión de objetos, documentos y pantalla. (#2996)
 * La revisión de objetos revisa el texto sólo dentro del navegador de objetos, la revisión de documentos revisa todo el texto en un documento en modo exploración (si hay alguno) y la revisión de pantalla revisa el texto en la pantalla para la aplicación actual.
 * Las órdenes que anteriormente movían a o desde revisión plana ahora cambian entre estos nuevos modos de revisión.
 * El navegador de objetos sigue automáticamente al cursor de revisión de tal manera que sigue siendo el objeto más profundo en la posición del cursor de revisión cuando se está en modos de revisión de documentos o de pantalla.
 * Después de cambiar a modo revisión de pantalla, NVDA permanecerá en este modo hasta que vuelvas explícitamente a los modos de revisión de documentos o de objetos.
 * Cuando se esté en modo de revisión de documentos o de objetos, NVDA podrá cambiar automáticamente entre estos dos modos dependiendo de si estás moviéndote por un documento del modo exploración o no.
* Actualizado el transcriptor braille liblouis a 2.5.3. (#3371)

### Corrección de Fallos

* La activación de un objeto ahora anuncia la acción antes de la activación, en lugar de la acción después de la activación (ej.: expandir cuando se expande en lugar de contraer). (#2982)
* Una lectura y seguimiento del cursor más precisos en diversos campos de entrada para las últimas versiones de Skype, tales como chat y campos de búsqueda. (#1601, #3036)
* En la lista de conversaciones recientes de Skype, el número de nuevos eventos ahora se lee en cada conversación, si procede. (#1446)
* Mejoras en el control del cursor y el orden de lectura de texto de derecha a izquierda en la pantalla. Ej.: Edición de texto en árabe en Microsoft Excel. (#1601)
* La navegación rápida en botones y campos de formulario ahora localizará los enlaces marcados como botones para propósitos de accesibilidad en Internet Explorer. (#2750)
* En modo exploración, el contenido en el interior de vistas en árbol ya no se procesa como una representación plana, no es útil. Puedes pulsar Intro sobre una vista en árbol para  interactuar con ella en  modo foco. (#3023)
* Al Pulsar alt+flecha abajo o alt+flecha arriba para expandir un cuadro combinado mientras se esté en modo foco ya no cambia incorrectamente a modo exploración. (#2340)
* En Internet Explorer 10, las celdas de la tabla ya no activan el modo foco, a menos que se hayan hecho enfocables explícitamente por el autor de la web (#3248)
* NVDA ya no falla al arrancar si la hora del sistema es anterior a la última revisión de una actualización. (#3260)
* Si una barra de progreso se muestra en una pantalla Braille, el Braille se actualiza cuando cambie la barra de progreso. (#3258)
* En modo exploración en aplicaciones de Mozilla, los títulos de las tablas ya no se procesan dos veces. Además, el índice se procesa cuando hay también un título. (#3196)
* Al cambiar el idioma de entrada de Windows 8, NVDA ahora habla en el idioma correcto en lugar de en el anterior.
* NVDA ahora anuncia cambios en el modo de conversión de IME en Windows 8.
* NVDA ya no anuncia basura en el escritorio cuando los métodos de entrada japoneses Google o IME ATOK están en uso. ;(# 3234)
* En Windows 7 y superiores, NVDA ya no anuncia indebidamente el reconocimiento de voz o la entrada táctil como un cambio de idioma del teclado.
* NVDA ya no anuncia un carácter especial (0x7f) cuando se pulse control+retroceso en algunos editores mientras Verbalizar Caracteres al Escribir esté habilitado. (#3315)
* espeak ya no hace cambios inapropiados en el tono, volumen, etc. cuando NVDA lea texto que contenga ciertos caracteres de control o XML. (#3334) (regresión de #437)
* En aplicaciones Java, los cambios en el nivel o en el valor del control enfocado ahora se anuncian automáticamente, y se reflejan con la subsiguiente salida del control. (#3119)
* En controles Scintilla, las líneas ahora se anuncian correctamente cuando el corte de palabras está habilitado. (#885)
* En aplicaciones de Mozilla, el nombre de los elementos de lista de sólo lectura ahora se anuncia correctamente; ej.: cuando se navega por twits en modo foco en twitter.com. (#3327)
* En los diálogos de Confirmación en Microsoft Office 2013 ahora se lee su contenido automáticamente cuando aparezcan.
* Mejoras en el rendimiento cuando se navega por ciertas tablas en Microsoft Word. (#3326)
* Las órdenes de navegación de tablas de NVDA (control+alt+flechas) funcionan mejor en algunas tablas de Microsoft Word cuando una celda abarca varias filas.
* Si el administrador de complemenhtos está ya abierto, activarlo de nuevo (o desde el menú Herramientas o abriendo un fichero de complemento) ya no falla o no imposibilita cerrar dicho administrador de complementos. (#3351)
* NVDA ya no se cuelga en ciertos diálogos cuando se esté utilizando el IME en Office 2010 con el japonés o el chino. (#3064)
* Los espacios múltiples ya no se comprimen a un solo espacio en las pantallas braille. (#1366)
* Las Zend Eclipse PHP Developer Tools ahora funcionan igual que Eclipse. (#3353)
* En Internet Explorer, ya no es necesario pulsar de nuevo tab para interactuar con un objeto integrado (tal como el contenido Flash) después de pulsar intro sobre él. (#3364)
* Al editar texto en Microsoft PowerPoint, la última línea ya no se presenta como la línea anterior si la última línea está en blanco. (#3403)
* En Microsoft PowerPoint, los objetos ya no  se verbalizan a veces  dos veces cuando los seleccionas o eliges para editar. (#3394)
* NVDA ya no causa que Adobe Reader se bloquee o se cuelgue para ciertos documentos PDF mal formados que contengan filas fuera de las tablas. (#3399)
* NVDA ahora detecta correctamente la siguiente diapositiva con el foco cuando se elimine una en  la  vista de miniaturas en Microsoft PowerPoint. (#3415)

### Cambios para Desarrolladores

* se ha añadido windowUtils.findDescendantWindow para buscar una ventana descendiente (HWND) localizando la visivilidad especificada, identificador del control y/o nombre de clase.
* La consola de python remota ya no espera después de 10 segundos mientras aguarda por la entrada. (#3126)
* La inclusión del módulo bisect en compilaciones binarias está en desuso y podrá eliminarse en una versión futura. (#3368)
 * Los complementos que dependan de bisect (incluyendo el módulo urllib2) deberían actualizarse para incluir este módulo.

## 2013.1.1

Esta versión corrige el problema donde NVDA se colgaba al iniciarse si se configuraba para utilizar el idioma irlandés, así como incluye actualizaciones para traducciones y algunas otras correcciones de errores.

### Corrección de Fallos

* Se producen caracteres correctos cuando se teclean en la propia interfaz de NVDA mientras se utiliza  un método de entrada Coreano o Japonés mientras sea el método predeterminado. (#2909)
* En Internet Explorer y otros controles MSHTML, los campos marcados como conteniendo una entrada inválida ahora se manejan correctamente. (#3256)
* NVDA ya no se cuelga cuando se inició si se configuró para utilizar el idioma irlandés.

## 2013.1

Lo más subrayable en esta versión incluye una distribución de teclado portátil más intuitiva y consistente; soporte básico para Microsoft PowerPoint; soporte para descripciones largas en navegadores web; y soporte para la entrada de braille computerizado para pantallas braille que tengan un teclado braille.

### Importante

#### Nueva Distribución Teclado Portátil

La distribución de teclado portátil se rediseñó por completo para hacerla más intuitiva y consistente.
La nueva distribución utiliza las teclas de cursor en combinación con la tecla NVDA y otras modificadoras para órdenes de revisión.

Por favor ten en cuenta los siguientes  cambios para órdenes comúnmente utilizadas:

| Nombre |Tecla|
|---|---|
|Leer todo |NVDA+a|
|Leer línea actual |NVDA+l|
|Leer selección de texto actual |NVDA+shift+s|
|Anunciar barra de estado |NVDA+shift+fin|

Además, entre otros cambios, han variado las órdenes para toda la navegación de objetos, revisión de texto, clic del ratón y grupos de opciones del sintetizador.
Por favor mira el documento [Referencia Rápida de Órdenes](keyCommands.html) para las nuevas teclas.

### Nuevas Características

* Soporte básico para editar y leer presentaciones de Microsoft PowerPoint. (#501)
* Soporte básico para leer y escribir mensajes en Lotus Notes 8.5. (#543)
* Soporte para el cambio automático de idioma cuando se lean documentos en Microsoft Word. (#2047)
* En modo exploración para MSHTML (ej.: Internet Explorer) y Gecko (ej.: Firefox), ahora se anuncia la existencia de descripciones largas. También es posible abrir la descripción larga en una ventana nueva pulsando NVDA+d. (#809)
* Las notificaciones en Internet Explorer 9 y superior (tales como contenido bloqueado o descargas de ficheros) ahora se verbalizan. (#2343)
* Ahora se soporta el anunciado automático de los encabezados de fila y columna para documentos en modo exploración en Internet Explorer y otros controles MSHTML. (#778)
* Nuevos idiomas: Aragonés, irlandés
* Nuevas tablas de transcripción braille:  Danés grado 2, Coreano grado 1.
* Soporte para pantallas braille conectadas a través de bluetooth en un ordenador ejecutando el Bluetooth Stack for Windows de Toshiba. (#2419)
* Soporte para la selección de puerto cuando se utilicen pantallas freedom Scientific (Automático, USB o Bluetooth).
* Soporte para la familia BrailleNote de anotadores electrónicos de Humanware cuando actúen como una terminal braille para un lector de pantalla. (#2012)
* Soporte para  modelos antiguos de las pantallas braille Papenmeier BRAILLEX. (#2679)
* Soporte para la entrada de braille computerizado  para pantallas braille que tengan un teclado braille. (#808)
* Nuevas opciones de teclado que permiten  elegir si NVDA debería interrumpir la voz para los caracteres escritos y/o la tecla Intro. (#698)
* Soporte para varios navegadores web basados en Google chrome: Rockmelt, BlackHawk, Comodo Dragon y SRWare Iron. (#2236, #2813, #2814, #2815)

### Cambios

* Actualizado el transcriptor braille liblouis a 2.5.2. (#2737)
* La distribución de teclado portátil se ha rediseñado por completo para hacerla más intuitiva y consistente. (#804)
* Actualizado el sintetizador de voz eSpeak a 1.47.11. (#2680, #3124, #3132, #3141, #3143, #3172)

### Corrección de Fallos

* Las teclas de navegación rápida para saltar al siguiente o anterior separador en modo exploración ahora funcionan en Internet Explorer y otros controles MSHTML. (#2781)
* Si NVDA se cambia a eSpeak debido a que el sintetizador de voz configurado falla cuando NVDA arranca, el sintetizador configurado ya no se deja automáticamente en la opción de eSpeak. Esto significa que ahora, el sintetizador original será probado de nuevo la próxima vez que NVDA arranque. (#2589)
* Si NVDA se cambia a sin braille debido a que la pantalla braille configurada  falla cuando NVDA arranca, la pantalla configurada ya no se deja automáticamente en la opción de sin braille. Esto significa que ahora, la pantalla original será probada de nuevo la próxima vez que NVDA arranque. (#2264)
* En modo exploración en aplicaciones de Mozilla, las actualizaciones de las tablas ahora se procesan correctamente. Por ejemplo, en actualización de celdas, las coordenadas de fila y columna se anuncian y la navegación de la tabla funciona como debería. (#2784)
* En modo exploración en navegadores web, ciertos gráficos cliqueables no etiquetados que no se procesaban anteriormente ahora se procesan correctamente. (#2838)
* Ahora se soportan las versiones anteriores y actuales de SecureCRT . (#2800)
* Ahora se anuncia correctamente la cadena de lectura para métodos de entrada tales como Easy Dots IME bajo XP.
* La lista de candidatos del método de entrada Chino Simplificado Microsoft Pinyin bajo Windows 7 ahora se lee correctamente cuando se cambian páginas con las flechas izquierda y derecha, y cuando se la abre primero con Inicio.
* Cuando se guarda la información de pronunciación personalizada de símbolos , el campo avanzado "preserve" ya no se elimina. (#2852)
* Cuando se desactive la detección automática de actualizaciones, NVDA ya no ha de reiniciarse para que todos los cambios tengan efecto.
* NVDA ya no falla al iniciarse si un complemento no se puede eliminar debido a que su directorio se esté utilizando actualmente por otra aplicación. (#2860)
* Las etiquetas de pestañas en el diálogo de preferencias de DropBox ahora pueden verse con la Revisión Plana.
* Si el idioma de entrada se cambia a algún otro que el predeterminado, NVDA ahora detecta las teclas correctamente para órdenes y el modo de ayuda de entrada.
* Para idiomas tales como el alemán donde el signo + (más) es una  tecla sola en el teclado, ahora es posible vincularle órdenes utilizando la palabra "plus". (#2898)
* En Internet Explorer y otros controles  MSHTML, las comillas ahora se anuncian donde proceda. (#2888)
* El controlador de las pantallas HumanWare Brailliant BI/Bbraille ahora puede  seleccionarse cuando las pantallas estén conectadas a través de Bluetooth pero nunca se hayan conectado a través de USB.
* El filtrado de elementos en la Lista de Elementos del modo exploración con el filtro de texto en mayúsculas ahora devuelve resultados no sensibles a las mayúsculas igual que en minúsculas en lugar de nada en absoluto. (#2951)
* En navegadores de Mozilla, el modo exploración puede utilizarse de nuevo cuando se enfoque contenido Flash. (#2546)
* Cuando se utilice una tabla de braille contraído y esté habilitada la opción expandir a braille computerizado para la palabra en el cursor , el cursor braille ahora se coloca correctamente cuando se encuentre después de  una palabra donde un carácter se  represente con varias celdas braille (ej.: signo de mayúsculas, signo de diálogo, signo de número, etc.). (#2947)
* La selección de texto ahora se muestra correctamente en una pantalla braille en aplicaciones tales como controles de edición de Microsoft word 2003 e Internet Explorer.
* Es posible de nuevo seleccionar texto en una dirección hacia atrás en Microsoft Word mientras esté habilitado el Braille.
* Cuando se esté en revisión,  eliminando caracteres con retroceso o suprimir en controles de edición de Scintilla, NVDA anuncia correctamente caracteres multibyte. (#2855)
* NVDA ya no fallará al instalar cuando la ruta del perfil de usuario contenga ciertos caracteres multibyte. (#2729)
* El anunciado de grupos para controles Vista de Lista (SysListview32) en aplicaciones de 64 bit ya no causa un error.
* En modo exploración en aplicaciones de Mozilla, el contenido de texto ya no se trata incorrectamente como editable en algunos casos extraños. (#2959)
* En IBM Lotus Symphony y OpenOffice, moviendo el cursor del sistema ahora se mueve  el cursor de revisión si procede.
* El contenido de Adobe Flash ahora es accesible en Internet Explorer en Windows 8. (#2454)
* Corregido el soporte Bluetooth para la Papenmeier Braillex Trio. (#2995)
* Corregida la incapacidad para utilizar ciertas voces de Microsoft Speech API versión 5 tales como las voces de Koba Speech 2. (#2629)
* En aplicaciones que utilicen el Java Access Bridge, ahora las pantallas braille se actualizan correctamente cuando el cursor se mueva en campos de texto editables . (#3107)
* Se soporta la región en formulario en modo exploración en documentos que soporten regiones. (#2997)
* El controlador del sintetizador de voz eSpeak ahora maneja la lectura por caracteres más apropiadamente (ej.: anuncia un nombre de letra extrangero o un valor en lugar de sólo su sonido o nombre genérico). (#3106)
* NVDA ya no falla al copiar las opciones del usuario para utilizarlas en la autentificación y en otras pantallas seguras cuando la ruta del perfil del usuario contiene caracteres no ASCII. (#3092)
* NVDA ya no se bloquea cuando se utiliza la entrada de caracteres asiáticos en algunas aplicaciones .NET. (#3005)
* ahora es posible utilizar el modo exploración para páginas en Internet Explorer 10 cuando se esté en modo estándar; ej.: [www.gmail.com](http://www.gmail.com) login page. (#3151)

### Cambios para Desarrolladores

* Los controladores de pantalla braille ahora pueden soportar la selección manual de puertos. (#426)
 * Esto es mayoritariamente útil para pantallas braille que soporten conexión a través de un puerto serie.
 * Esto se hace utilizando el método de la clase getPossiblePorts en la clase BrailleDisplayDriver.
* Ahora se soporta la entrada braille  desde teclados braille. (#808)
 * La entrada braille se abarca por la clase brailleInput.BrailleInputGesture o una subclase de la misma.
 * Las subclases de braille.BrailleDisplayGesture (según se implementaron en los controladores de las pantallas braille) también pueden heredar de brailleInput.BrailleInputGesture. Esto permite mostrar órdenes  y que la entrada braille se maneje por la misma clase gesture.
* Ahora puedes utilizar comHelper.getActiveObject para conseguir un objeto COM activo desde un proceso normal cuando NVDA esté ejecutándose con el privilegio UIAccess. (#2483)

## 2012.3

Lo subrayable de esta versión incluye el soporte para la entrada de caracteres asiáticos; soporte experimental para pantallas táctiles en Windows 8; anunciado de números de página y soporte mejorado para tablas en Adobe Reader; órdenes de navegación de tabla en filas de tabla enfocadas y controles de vista en lista de Windows; soporte para algunas pantallas braille más; y encabezados de columna en Microsoft Excel.

### Nuevas Características

* NVDA ahora puede soportar entrada de caracteres asiáticos utilizando IME y métodos de servicio de entrada de texto en todas las aplicaciones, incluyendo:
 * Anunciado y navegación de listas candidatas;
 * Anunciado y navegación de cadenas de composición; y
 * Anunciado de lectura de cadenas.
* La presencia de subrayados y tachados ahora se anuncia en documentos de Adobe Reader. (#2410)
* Cuando la función Windows Sticky Keys está activada, la tecla modificadora de NVDA ahora se comportará como las otras teclas modificadoras. Esto te permite utilizar la tecla modificadora de NVDA sin la necesidad de mantener pulsada mientras pulsas otras teclas. (#230)
* Ahora se soporta el anunciado automático de encabezados de columna y de fila en Microsoft Excel. Pulsa NVDA+shift+c para configurar la fila que contenga encabezados de columna y NVDA+shift+r para la columna que contenga encabezados de fila. Pulsa el script dos veces en sucesión rápida para limpiar la opción. (#1519)
* Soporte para las pantallas braille HIMS Braille Sense, Braille EDGE y SyncBraille. (#1266, #1267)
* Cuando las Notificaciones de Windows 8 aparezcan, NVDA las anunciará si el anunciado de globos de ayuda está habilitado. (#2143)
* Soporte experimental para pantallas Táctiles en Windows 8, incluyendo:
 * Lectura de texto directamente bajo tu dedo mientras lo mueves
 * Muchos gestos para llevar a cabo la navegación por objetos, revisión de texto, y otras órdenes de NVDA.
* Soporte para VIP Mud. (#1728)
* En Adobe Reader, si una tabla tiene un resumen, ahora se presenta. (#2465)
* En Adobe Reader, los encabezados de fila y columna de tabla ahora pueden anunciarse. (#2193 #2527 #2528)
* Nuevos idiomas: Amárico, Coreano, Nepalí, Esloveno.
* NVDA ahora puede leer sugerencias de autocompletado cuando se introduzcan direcciones de correo en Microsoft Outlook 2007. (#689)
* Nuevas variantes de voz de eSpeak: Gene, Gene2. (#2512)
* En Adobe Reader, ahora pueden anunciarse los números de página. (#2534)
 * En Reader XI, las etiquetas de página se anuncian donde estén presentes, reflejando cambios en la numeración de páginas en secciones diferentes, etc. en versiones anteriores, esto no es posible y sólo los números de páginas secuenciales se anunciaban.
* Ahora es posible reiniciar la configuración de NVDA a los valores predeterminados de fábrica pulsando NVDA+control+r tres veces rápidamente o eligiendo Reiniciar a los Valores Predeterminados de Fábrica desde el menú NVDA (#2086).
* Soporte para las pantallas braille Seika Versión 3, 4 y 5 y Seika80 de Nippon Telesoft. (#2452)
* El primer y el último de los sensores superiores de las pantallas braille Freedom Scientific Pacmate y Focus ahora pueden utilizarse para desplazar hacia atrás o adelante. (#2556).
* Se soportan muchas más características en las pantallas braille Freedom Scientific Focus tales como barras avanzadas, barras de balancines y ciertas combinaciones de puntos para acciones comunes. (#2516)
* En aplicaciones que utilicen IAccessible2 tales como aplicaciones de Mozilla, los encabezados de fila y columna de tabla ahora pueden anunciarse fuera del modo exploración. (#926)
* Soporte preliminar para el control de documento en Microsoft Word 2013. (#2543)
* La alineación de texto ahora puede anunciarse en aplicaciones que utilizan IAccessible2 tales como aplicaciones de Mozilla. (#2612)
* Cuando se enfoca una fila de tabla o un control estándar vista en lista de Windows con múltiples columnas, ahora puedes utilizar las órdenes de navegación por tablas para acceder a las celdas individuales. (#828)
* Nuevas tablas de transcripción braille: Estonio grado 0, braille computerizado Portugués de 8 puntos y braille italiano computerizado de 6 puntos. (#2319, #2662)
* Si NVDA se instala en el sistema, la apertura directa de un paquete de complemento de NVDA (es decir desde el explorador de Windows o después de descargarlo de un navegador web) lo instalará en NVDA. (#2306)
* Soporte para los modelos modernos de las pantallas de Papenmeier BRAILLEX. (#1265)
* La información de posición (ej.: 1 de 4) ahora se anuncia para los elementos de lista de Windows Explorer en Windows 7 y posterior. Esto también incluye cualquier control UIAutomation que soporte las propiedades personalizables itemIndex e itemCount. (#2643)

### Cambios

* En el diálogo Preferencias del Cursor de Revisión de NVDA, la opción Seguir foco del teclado ha sido renombrada a Seguir al foco del sistema para consistencia con la terminología utilizada en otras partes en NVDA.
* Cuando el braille esté siguiendo a la revisión y el cursor esté sobre un objeto que no sea un objeto de texto (ej.: un campo de texto editable), las teclas de los sensores del cursor ahora activarán el objeto. (#2386)
* La opción Guardar la Configuración al Salir ahora está activada de manera predeterminada para nuevas configuraciones.
* Cuando se actualiza una copia de NVDA instalada anteriormente, la tecla de atajo del escritorio ya no se fuerza a control+alt+n si fue cambiada manualmente a alguna otra diferente por el usuario. (#2572)
* La lista de complementos en el Administrador de Complementos ahora muestra el nombre del paquete antes de su estado. (#2548)
* Al instalar la misma u otra versión de un complemento instalado actualmente, NVDA te preguntará si deseas actualizar el complemento antiguo primero, en lugar de mostrar un error y abortar la instalación. (#2501)
* Las órdenes de navegación de objetos (excepto la orden anunciar objeto actual) ahora anuncian con menos verbosidad. Todavía puedes obtener la información extra utilizando la orden de anunciar objeto actual. (#2560)
* Actualizado el transcriptor braille liblouis a 2.5.1.
* El documento Referencia Rápida de Órdenes de teclado de NVDA ha sido renombrado a Referencia Rápida de Órdenes, así ahora incluye tanto órdenes táctiles como órdenes de teclado.
* La Lista de elementos en modo exploración ahora recordará el último tipo de elemento mostrado (ej.: enlaces, encabezados o regiones) cada vez que se muestre el diálogo dentro de la misma sesión de NVDA. (#365)
* La mayoría de las aplicaciones Metro en Windows 8 (ej.: Mail, Calendar) ya no activan el modo exploración para toda la aplicación.
* Actualizado el Handy Tech BrailleDriver COM-Server a 1.4.2.0.

### Corrección de Fallos

* En Windows Vista y posterior, NVDA ya no trata incorrectamente la tecla Windows como es al mantenerla pulsada cuando se desbloquea Windows después de bloquearla pulsando Windows+l. (#1856)
* En Adobe Reader, los encabezados de fila ahora se reconocen correctamente como celdas de tabla; es decir, las coordenadas se anuncian y se pueden acceder utilizando órdenes de navegación de tabla. (#2444)
* En Adobe Reader, las celdas de tabla que abarquen más de una columna y/o fila ahora se manejan correctamente. (#2437)
* El paquete de distribución de NVDA ahora verifica su integridad antes de ejecutarse. (#2475)
* Los ficheros descargados temporalmente ahora se eliminan si se descarga un fichero de actualización de NVDA. (#2477)
* NVDA ya no se colgará cuando se esté ejecutando como un administrador mientras se copia la configuración del usuario a la configuración del sistema (para utilizarla en la autentificación de Windows y en otras pantallas seguras). (#2485)
* Los mosaicos en la Pantalla de inicio de Windows 8 ahora se presentan mejor en voz y braille. El nombre ya no se repite, ya no se anuncia no seleccionado en todos los mosaicos, y la información de estado en directo se presenta según la descripción del mosaico (ej.: temperatura actual para el mosaico del Tiempo).
* Las contraseñas ya no se anuncian cuando se lean campos de contraseña en Microsoft Outlook y otros controles de edición estándar que estén marcados como protegidos. (#2021)
* En Adobe Reader, los cambios para campos de formulario ahora se reflejan correctamente en modo exploración. (#2529)
* Mejoras en el soporte para el corrector de ortografía de Microsoft Word, incluyendo la lectura más precisa del error ortográfico actual, y la capacidad de soportar el corrector de ortografía cuando se ejecute una copia instalada de NVDA en Windows Vista o superior.
* Los complementos que incluyan ficheros conteniendo caracteres que no estén en Inglés ahora pueden instalarse correctamente en la mayoría de los casos. (#2505)
* En Adobe Reader, el idioma del texto ya no se pierde cuando se actualiza o se desplaza. (#2544)
* Cuando se instala un complemento, el diálogo de confirmación ahora muestra correctamente el nombre traducido del complemento si está disponible. (#2422)
* En aplicaciones que utilizan UI Automation (tales como aplicaciones de .net y Silverlight), el cálculo de valores numéricos para controles tales como deslizadores se ha corregido. (#2417)
* La configuración para el anunciado de barras de progreso ahora se reconoce para barras de progreso indeterminadas mostradas por NVDA cuando se está instalando, creando una copia portable, etc. (#2574)
* Las órdenes de NVDA ya no pueden ejecutarse desde una pantalla braille mientras una pantalla segura de Windows (tal como la pantalla de desbloqueo) esté activa. (#2449)
* En modo exploración, el braille ahora se actualiza si el texto que está siendo desplazado cambia. (#2074)
* Cuando se está en pantallas seguras de  Windows tales como la pantalla de desbloqueo, los mensajes de las aplicaciones que están hablando o mostrando braille directamente a través de NVDA ahora se ignoran.
* En modo exploración, ya no es posible sobrepasar la parte inferior del documento con la tecla flecha derecha cuando se está en el carácter final, o saltando el fin de un contenedor cuando ese contenedor es el último elemento del documento. (#2463)
* Ya no se incluye incorrectamente contenido extraño cuando se anuncia el texto de diálogos en aplicaciones web (específicamente, diálogos ARIA sin el atributo aria-describedby). (#2390)
* NVDA ya no localiza o anuncia incorrectamente ciertos campos de edición en documentos MSHTML (ej.: Internet Explorer), específicamente donde se haya utilizado un rol ARIA explícito por el autor de la página web. (#2435)
* La tecla retroceso ahora se maneja correctamente cuando se verbalizan palabras al escribir en consolas de órdenes de Windows. (#2586)
* Las coordenadas de las celdas ahora se muestran de nuevo en Braille en Microsoft Excel.
* En Microsoft Word, NVDA ya no te deja enganchado en un párrafo con formato de lista cuando tratas de navegar por una viñeta o número con flecha izquierda o control + flecha izquierda. (#2402)
* En modo exploración en aplicaciones de Mozilla, los elementos en ciertos cuadros de lista (específicamente, cuadros de lista de ARIA) ya no se procesan incorrectamente.
* En modo exploración en aplicaciones de Mozilla, ciertos controles que fueron procesados con una etiqueta incorrecta o como espacio en blanco ahora se procesan con la etiqueta correcta.
* En modo exploración en aplicaciones de Mozilla, se han eliminado espacios en blanco extraños.
* En modo exploración en navegadores web, ciertos gráficos que se marcaron explícitamente como presentables (específicamente, con un atributo alt="") ahora se ignoran correctamente.
* En navegadores web, NVDA ahora oculta contenido que se marcó como oculto para lectores de pantalla (específicamente, utilizando el atributo aria-hidden). (#2117)
* Las cantidades negativas en moneda (ej.: -$123) ahora se verbalizan correctamente como negativos, independientemente del nivel de símbolos. (#2625)
* Durante leer todo, NVDA ya no regresará incorrectamente a al idioma predeterminado si una línea no finaliza una frase. (#2630)
* Ahora se detecta correctamente la información de fuente en Adobe Reader 10.1 y posteriores. (#2175)
* En Adobe Reader, si se proporciona texto alternativo, sólo se procesará ese texto. Anteriormente, algunas veces se incluía texto extraño. (#2174)
* Donde un documento contenga una aplicación, el contenido de la aplicación ya no se incluye en modo exploración. Esto previene de movimientos inesperados dentro de la aplicación cuando se navega. Puedes interactuar con la aplicación del mismo modo que para los objetos integrados. (#990)
* En aplicaciones de Mozilla, el valor de los botones de flecha ahora se anuncia correctamente cuando cambian. (#2653)
* Actualizado el soporte de Adobe Digital Editions para que funcione en la versión 2.0. (#2688)
* Pulsando NVDA+flecha arriba mientras se esté en un cuadro combinado en Internet Explorer y otros documentos MSHTML ya no se leerán incorrectamente todos los elementos. Por lo contrario, sólo se leerá el elemento activo. (#2337)
* Los diccionarios del habla ahora se guardarán apropiadamente cuando se utilice un signo de número (#) dentro de los campos de edición patrón o reemplazar. (#961)
* El modo exploración para documentos MSHTML (ej.: Internet Explorer) ahora muestra correctamente el contenido visible que hay dentro del contenido oculto. Específicamente: elementos con un estilo visibility:visible en un elemento con estilo visibility:hidden. (#2097)
* Los enlaces en el Centro de Seguridad de Windows XP ya no anuncian basura aleatoriamente después de sus nombres. (#1331)
* Los controles de texto UI Automation ej.:  el campo de búsqueda en el menú de inicio de Windows 7 ahora se anuncian correctamente cuando se mueva el ratón sobre ellos en lugar de permanecer en silencio.
* Los cambios de distribución del teclado ya no se anuncian durante leer todo, lo cual era especialmente problemático para documentos multilingües incluyendo texto árabe. (#1676)
* Todo el contenido de algunos controles de texto editable UI Automation (ej.: el cuadro de búsqueda en el menú de inicio de Windows 7/8) ya no se anuncia cada vez que cambie.
* Cuando te muevas entre grupos en la pantalla de inicio de Windows 8, los grupos no etiquetados ya no anunciarán su primer mosaico como el nombre del grupo. (#2658)
* Al abrir la pantalla de inicio de Windows 8, el foco se coloca correctamente sobre el primer mosaico en lugar de saltar a la raíz de la pantalla de inicio, lo cual puede confundir en la navegación. (#2720)
* NVDA ya no fallará al arrancar cuando la ruta de perfiles del usuario contenga ciertos caracteres multibyte. (#2729)
* En modo exploración en Google Chrome, el texto de las pestañas ahora se procesa correctamente.
* En modo exploración, los botones de menú ahora se anuncian correctamente.
* En Calc de OpenOffice.org/LibreOffice, la lectura de las celdas de las hojas de cálculo ahora funciona correctamente. (#2765)
* NVDA puede funcionar de nuevo en la lista de mensajes de Yahoo! Mail cuando se utiliza desde Internet Explorer. (#2780)

### Cambios para Desarrolladores

* El anterior fichero de registro ahora se copia en nvda-old.log en la inicialización de NVDA. Por lo tanto, si NVDA se bloquea o se reinicia, el registro de información  de esa sesión todavía es accesible para su inspección. (#916)
* La obtención de la propiedad de rol en chooseNVDAObjectOverlayClasses ya no causa que el rol sea incorrecto y por lo tanto no se anuncie en foco para ciertos objetos tales como consolas de órdenes de Windows y controles de Scintilla. (#2569)
* Los menús de NVDA Preferencias, Herramientas y Ayuda ahora son accesibles como atributos en gui.mainFrame.sysTrayIcon llamándose preferencesMenu, toolsMenu y helpMenu, respectivamente. Esto permite a los plugins añadir elementos mucho más fácilmente a estos menús.
* El script navigatorObject_doDefaultAction en globalCommands ha sido renombrado a review_activate.
* Ahora se soportan los mensajes contextuales de Gettext. Esto permite que sean definidas múltiples traducciones para un solo mensaje en Inglés dependiendo del contexto. (#1524)
 * Esto se hace utilizando la función pgettext(context, message).
 * Esto se soporta tanto para NVDA mismo como para los complementos.
 * deben utilizarse xgettext y msgfmt de GNU gettext para crear cualquier fichero PO y MO. Las herramientas de Python no soportan mensajes contextuales.
 * Para xgettext, pasa el argumento de línea de órdenes --keyword=pgettext:1c,2 para habilitar la inclusión de mensajes contextuales.
 * Mira https://www.gnu.org/software/gettext/manual/html_node/Contexts.html#Contexts para más información.
* Ahora es posible acceder a los módulos compilados de NVDA donde hayan sido sobreescritos por módulos de terceros. Mira el módulo nvdaBuiltin para detalles.
* Ahora puede utilizarse el soporte de traducción de complementos dentro del módulo installTasks del complemento. (#2715)

## 2012.2.1

Esta versión aborda varios problemas de seguridad potenciales (mediante la actualización de Python a 2.7.3).

## 2012.2

Lo reseñable de esta versión incluye una característica que integra el instalador y la creación del portable, un auto actualizador, administración fácil de los nuevos complementos de NVDA, anunciado de gráficos en Microsoft Word, soporte para el estilo de aplicaciones de Windows 8 Metro, y varias correcciones de fallos importantes.

### Nuevas Características

* NVDA ahora puede buscar automáticamente, descargar e instalar actualizaciones. (#73)
* Se ha hecho más sencilla la extensión de la funcionalidad de NVDA con la adición de un Administrador de Complementos (que se encuentra bajo Herramientas en el menú NVDA) permitiéndote instalar y desinstalar paquetes de complementos de NVDA (ficheros .nvda-addon) que contengan plugins y controladores. Ten en cuenta que el Administrador de Complementos no debería mostrar los antiguos plugins personales y controladores copiados manualmente en tu directorio de configuración. (#213)
* Ahora funcionan Muchas más características comunes de NVDA en el estilo de aplicaciones de Windows 8 Metro cuando se utiliza una versión instalada de NVDA, incluyendo la verbalización de caracteres al escribir y modo exploración para documentos web (se incluye soporte para la versión metro de Internet Explorer 10). Las copias portables de NVDA no pueden acceder al estilo de aplicaciones metro. (#1801)
* En documentos en modo exploración (Internet Explorer, Firefox etc) ahora puedes saltar al comienzo, o pasar al final, de ciertos elementos contenedores (incluyendo listas y tablas) con shift+, y , respectivamente. (#123)
* Nuevo idioma: Griego.
* Ahora se anuncian los gráficos y textos alternativos en documentos de Microsoft Word. (#2282, #1541)

### Cambios

* El anunciado de coordenadas de celda en Microsoft Excel ahora se hace después del contenido en lugar de antes, y ahora sólo se incluye si las opciones de anunciado de tablas y de anunciado de coordenadas de la celda de la tabla están activadas en las opciones del diálogo Formato de Documento. (#320)
* NVDA ahora se distribuye en un paquete. En lugar de una versión portable y una instalable, ahora sólo hay un fichero que cuando se ejecute, iniciará una copia temporal de NVDA, y te permitirá instalar, o generar una distribución portable. (#1715)
* NVDA ahora siempre se instala en Program Files en todos los sistemas. Al actualizar una instalación también se la moverá automáticamente si anteriormente no se instaló ahí.

### Corrección de Fallos

* Con el Cambio automático de idioma activado, el Contenido tal como el texto alternativo para gráficos y etiquetas para ciertos otros controles en Mozilla Gecko (ej.: Firefox) ahora se anuncian en el idioma correcto si se marcó apropiadamente.
* Leer todo en BibleSeeker (y otros controles TRxRichEdit) ya no se detiene en el medio de un pasaje.
* Las listas que se encuentran en las propiedades de fichero en Windows 8 Explorer (pestaña permisos) y en Windows 8 Windows Update ahora se leen correctamente.
* Corregidos posibles cuelgues en MS Word que podrían ocurrir cuando le tomó más de dos segundos extraer texto  desde un documento (líneas extremadamente largas o tablas de contenido). (#2191)
* La detección de partición de palabras ahora funciona correctamente donde un espacio en blanco sea seguido por cierta puntuación. (#1656)
* En modo exploración en Adobe Reader, ahora es posible navegar por encabezados fuera de un nivel utilizando navegación rápida y la Lista de Elementos. (#2181)
* En Winamp, el braille ahora se actualiza correctamente cuando te mueves a un elemento diferente en el Editor de listas de reproducción. (#1912)
* El árbol en los Elementos de Lista (disponible para documentos en modo exploración) ahora se dimensiona apropiadamente para mostrar el texto de cada elemento. (#2276)
* En aplicaciones que utilicen Java Access Bridge, los campos de texto editable ahora se presentan correctamente en braille. (#2284)
* En aplicaciones que utilicen Java Access Bridge, los campos de texto editable ya no informan de caracteres extraños en ciertas circumstancias. (#1892)
* En aplicaciones que utilicen Java Access Bridge, cuando se esté al final de un campo de texto editable, la línea actual  ahora se anuncia correctamente. (#1892)
* En modo exploración en aplicaciones que utilicen Mozilla Gecko 14 y posterior (ej.: Firefox 14), ahora la navegación rápida funciona en bloques de citas y objetos integrados. (#2287)
* En Internet Explorer 9 NVDA ya no lee contenido indeseado cuando el foco se mueve dentro de ciertas regiones o elementos enfocables (específicamente un elemento div que es enfocable o que tiene un rol de región ARIA).
* Los iconos para los atajos para NVDA en el Escritorio y en el Menú de Inicio ahora se muestran correctamente en ediciones de 64 bit de Windows. (#354)

### Cambios para Desarrolladores

* Debido a la sustitución del instalador anterior NSIS para NVDA por uno compilado en Python, ya no es necesario para los traductores mantener un fichero langstrings.txt para el instalador. Todas las cadenas de localización ahora se administran con ficheros po de gettext.

## 2012.1

Lo subrayable de esta versión incluye características para una lectura más fluída en braille; indicación de formato de documento en braille; acceso a mucha más información de formato y mejora del rendimiento en Microsoft Word; y soporte para la Store de iTunes.

### Nuevas Características

* NVDA puede anunciar el número de los tabuladores o espacios al inicio en la línea actual en el orden en que se introdujeron. Esto puede activarse seleccionando anunciar sangrado de línea en el diálogo Formateado de documento. (#373)
* NVDA ahora puede detectar la pulsación de teclas generadas desde la emulación de entrada de teclado tal como en programas de teclado en pantalla o de reconocimiento de voz.
* NVDA ahora puede detectar colores en ventanas órdenes de consola.
* Las negritas, cursivas y subrayados ahora se indican en braille utilizando signos apropiados a la tabla de transcripción configurada. (#538)
* Ahora se  anuncia mucha más información en documentos de Microsoft Word, incluyendo:
 * Información en línea tal como números de encabezados y notas al pie, niveles de encabezado, la existencia de comentarios, niveles de anidamiento de tabla, enlaces, y color de texto;
 * Se anuncia cuando se entra a las secciones del documento tales como al histórico de comentarios, al histórico de notas al pie y notas finales, y a los históricos de encabezados y pies.
* El braille ahora indica texto seleccionado utilizando los puntos 7 y 8. (#889)
* El braille ahora anuncia información acerca de controles dentro de documentos tales como enlaces, botones y encabezados. (#202)
* Soporte para pantallas braille hedo ProfiLine USB y MobilLine. (#1863, #1897)
* NVDA ahora evita la separación de palabras en braille cuando sea posible de forma predeterminada.  Esto puede desactivarse en el diálogo Opciones de Braille. (#1890, #1946)
* Ahora es posible mostrar braille por párrafos en lugar de líneas, lo cual podría permitir más fluidez al leer grandes cantidades de texto. Esto es configurable utilizando la opción Leer por párrafos en el diálogo de Opciones de Braille. (#1891)
* En modo exploración, puedes activar el objeto bajo el cursor utilizando una pantalla braille. Esto se hace pulsando la tecla de guiado de cursor donde se localice el cursor (lo cual significa pulsarlo dos veces si el cursor no está todavía allí). (#1893)
* Soporte básico para áreas web en iTunes tal como en la Store. Otras aplicaciones que utilicen WebKit 1 también podrían soportarse. (#734)
* En libros en Adobe Digital Editions 1.8.1 y posteriores, ahora las páginas se pasan automáticamente cuando se utiliza leer todo.  (#1978)
* Nuevas tablas de transcripción braille: Portugués grado 2, braille islandés computerizado de 8 puntos, tamil grado 1, Braille español computerizado de 8 puntos, persa grado 1. (#2014)
* Ahora puedes configurar si se anuncian los marcos en documentos desde el diálogo de preferencias de Formato de Documentos. (#1900)
* El modo durmiente se activa automáticamente cuando se utiliza OpenBook. (#1209)
* En Poedit, los traductores ahora pueden leer los comentarios añadidos y extraídos automáticamente para el traductor. Los mensajes que estén sin traducir o provisionales se marcan con un asterisco y se escucha un pitido cuando se navegue sobre ellos (#1811).
* Soporte para las pantallas braille de HumanWare Brailliant series BI y B. (#1990)
* Nuevo idioma: Noruego Bokmål.

### Cambios

* Las órdenes para describir el carácter actual o para deletrear la palabra o línea actual ahora deletrearán en el idioma apropiado de acuerdo con el texto, si el cambio automático de idioma está activado y la información de idioma adecuada está disponible.
* Actualizado el sintetizador de voz eSpeak a 1.46.02.
* Ahora NVDA filtrará los nombres extremadamente largos (30 caracteres o más) deducidos de URLs de gráfícos y enlaces dado que lo más probable es que sean basura que obstaculice la lectura.
* Se ha abreviado alguna información mostrada en braille. (#1955, #2043)
* Cuando los cursores de sistema o de revisión se mueven, ahora el braille se desplaza de igual modo como si se desplazase manualmente. Esto lo hace más apropiado cuando el braille se configuró para leer por párrafos y/o para evitar partición de palabras. (#1996)
* Actualizado a una nueva tabla de transcripción braille Española de grado 1.
* Actualizado el transcriptor braille liblouis a 2.4.1.

### Corrección de Fallos

* En Windows 8, el foco ya no se mueve incorrectamente del campo de Búsqueda de Windows Explorer, lo cual no permitía a NVDA interactuar con él.
* Mejoras en el rendimiento cuando se lee y se navega por documentos de Microsoft word mientras el anunciado automático del formato está activado, así ahora es un poco más confortable probar a leer el formato etc. El rendimiento también podría mejorarse sobre todo para algunos usuarios.
* El modo exploración ahora se utiliza para todo el contenido de pantalla de Adobe Flash.
* Corregida la mala calidad de audio en algunos casos cuando se utilizan voces de Microsoft Speech API version 5 con el dispositivo de salida de audio configurado a algún otro que el predeterminado (Microsoft Sound Mapper). (#749)
* Se permite de nuevo a NVDA utilizar el sintetizador "no speech", confiando únicamente en el braille o en elVisualizador de Voz. (#1963)
* Las órdenes de navegación de objetos ya no anuncian "Sin hijos" y "Sin padres", pero en cambio anuncian mensajes consistentes con la documentación.
* Cuando NVDA se configuró para utilizar otro idioma que el Inglés, el nombre de la tecla tab ahora se anuncia en el idioma adecuado.
* En Mozilla Gecko (ej.: Firefox), NVDA ya no cambia intermitentemente a modo exploración mientras se navega por menús en documentos. (#2025)
* En la Calculadora, la tecla retroceso ahora anuncia el resultado actualizado en lugar de no anunciar nada. (#2030)
* En modo exploración, la orden mover el ratón al navegador de objetos actual ahora se mueve al centro del objeto en el cursor de revisión en lugar de a la esquina izquierda superior, haciéndolo más preciso en algunos casos. (#2029)
* En modo exploración con el modo foco automático para cambios del foco activado, el enfocado de una barra de herramientas ahora cambiará a modo foco. (#1339)
* La orden anunciar título funciona correctamente de nuevo en Adobe Reader.
* Con el modo foco automático para cambios del foco activado, el modo foco ahora se utiliza correctamente para las celdas de tabla enfocadas; ej.: en regillas ARIA. (#1763
* En iTunes, la información de posición en ciertas listas ahora se anuncia correctamente.
* En Adobe Reader, algunos enlaces ya no se tratan como conteniendo campos de texto editable de sólo lectura.
* Las etiquetas de algunos campos de texto editable ya no se incluyen incorrectamente cuando se anuncia el texto de un diálogo. (#1960)
* La descripción de grupos se anuncia una vez de nuevo si el anunciado de descripciones de objeto está activado.
* Los tamaños legibles ahora se incluyen en el texto del diálogo de propiedades de la unidad en Windows Explorer.
* El anunciado doble de texto en páginas de propiedades ha sido suprimido en algunos casos. (#218)
* Mejorado el seguimiento del cursor del sistema en campos de texto editable que confían en texto escrito en la pantalla. En particular, esto mejora la edición en el editor de celdas de Microsoft Excel y el editor de mensajes de Eudora. (#1658)
* En Firefox 11, la orden mover a contenido de modo virtual (NVDA+control+espacio) ahora funciona como debería para salir de objetos integrados tales como contenido Flash.
* NVDA ahora se reinicia correctamente (ej.: después de cambiar el idioma configurado) cuando se localice en un directorio con contenidos de caracteres no ASCII. (#2079)
* El Braille respeta correctamente las opciones para el anunciado de teclas de atajo de los objetos, información de posición y descripciones.
* En aplicaciones Mozilla, el cambio entre modos navegación y foco ya no se enlentece con el braille activado. (#2095)
* Guiar el cursor al espacio en el final de la línea/párrafo utilizando los sensores del cursor braille en algunos campos de texto editable ahora funciona correctamente en lugar de llevar al comienzo del texto. (#2096)
* NVDA funciona de nuevo correctamente con el sintetizador Audiologic Tts3. (#2109)
* Los documentos de Microsoft Word se tratan correctamente como multi-línea. Esto causa que el braille se comporte de manera más adecuada cuando un documento se enfoque.
* En Microsoft Internet Explorer, ya no ocurren errores cuando se enfoca sobre ciertos controles raros. (#2121)
* Cambiar la puntuación y símbolos por el usuario ahora tendrá efecto inmediato, en lugar de requerir un reinicio de NVDA, o que se desactive el cambio automático de idioma.
* Cuando se utiliza eSpeak, la voz ya no queda en silencio en algunos casos en el diálogo Guardar Como... del Visualizador de Registro de NVDA. (#2145)

### Cambios para desarrolladores

* Ahora hay una Consola Python remota para situaciones donde la depuración remota es útil. Mira la Developer Guide para detalles.
* La ruta base del código de NVDA ahora se quitó de los tracebacks en el registro para mejorar legibilidad. (#1880)
* Los objetos TextInfo ahora tienen un método activate() para activar la posición representada por el TextInfo.
 * Esto se utiliza por el braille para activar la posición utilizando teclas de guiado del cursor en una pantalla braille. No obstante, podría haber otras llamadas en el futuro.
* Los treeInterceptors y los NVDAObjects que sólo exponen una página de texto a la vez pueden soportar el cambio automático de página durante leer todo utilizando el textInfos.DocumentWithPageTurns mezclado. (#1978)
* Se han movido o cambiado los nombres de varios controles y constantes de salida. (#228)
 * las constantes speech.REASON_* se han movido a controlTypes.
 * Se han renombrado controlTypes, speechRoleLabels y speechStateLabels sólo a roleLabels y stateLabels, respectivamente.
* Ahora la salida braille se registra en el nivel input/output. Primero, el texto sin transcribir de todas las regiones se registra, seguido por las celdas braille de la ventana que están siendo mostradas. (#2102)
* las subclasses del synthDriver sapi5  ahora pueden sobreescribirse _getVoiceTokens y extender init para soportar fichas de voces personalizadas tales como con sapi.spObjectTokenCategory para obtener fichas de un registro personalizado.

## 2011.3

Lo subrayable en esta versión incluye el cambio automático de idioma de la voz cuando se leen documentos con la información de idioma apropiada;  soporte para ambientes Java Runtime de 64 bit; anunciado de formato de texto en modo exploración en aplicaciones de Mozilla; mejor manejo de rupturas y cuelgues de aplicaciones; y correcciones iniciales para Windows 8.

### Nuevas Características

* NVDA ahora puede cambiar el idioma del sintetizador eSpeak al vuelo cuando lee ciertos documentos web/pdf con la información de idioma apropiada. El cambio automático de idioma/dialecto puede activarse o desactivarse desde el diálogo Opciones de Voz. (#845)
* En Mozilla Gecko (ej.: Firefox) los niveles de encabezado ahora se anuncian cuando se utiliza la navegación de objetos.
* El formato de texto ahora se puede anunciar cuando se utiliza el modo exploración en Mozilla Gecko (ej.: Firefox y Thunderbird). (#394)
* El texto con subrayado y/o tachado ahora puede detectarse y anunciarse en controles de texto estándar IAccessible2 tal como en aplicaciones de Mozilla.
* NVDA ahora se reiniciará si se cuelga.
* En modo exploración en Adobe Reader, ahora se informa de la cuenta de las filas y las columnas.
* Se añadió soporte para la Plataforma de Síntesis de Voz de Microsoft. (#1735)
* Los números de línea y de página ahora se anuncian para el cursor en IBM Lotus Symphony. (#1632)
* El porcentaje de cuánto cambia el tono cuando se verbalice una letra mayúscula ahora es configurable desde el diálogo Opciones de voz. Por lo tanto, esto reemplaza la antigua casilla de verificación elevar el tono para mayúsculas (por lo tanto para desactivar esta característica pon el porcentaje a 0). (#255)
* El color de texto y fondo ahora se incluyen en el anunciado de formato para celdas en Microsoft Excel. (#1655)
* En aplicaciones que utilizen el Java Access Bridge, la orden activar actual navegador de objetos ahora funciona en controles donde sea apropiado. (#1744)
* Nuevo idioma: Tamil.
* Soporte básico para Design Science MathPlayer.

### Cambios

* NVDA ahora se reiniciará si se cuelga.
* Alguna información mostrada en braille ha sido abreviada. (#1288)
* el script Leer Ventana activa (NVDA+b) ha sido mejorado para filtrar controles inútiles y ahora también es mucho más fácil de silenciar. (#1499)
* Leer Todo automáticamente cuando se carga un documento en modo exploración ahora es opcional a través de una opción en el diálogo Opciones de modo exploración. (#414)
* Cuando se tratan de leer barras de estado (Sobremesa NVDA+fin), si no se puede localizar un objeto de barra de estado real, NVDA recurrirá en su lugar a utilizar la línea final de texto escrita en la pantalla de la aplicación activa. (#649)
* Cuando se lee con leer todo en documentos en modo exploración, NVDA ahora hará una pausa en el final de encabezados y otros elementos de nivel de bloque, en lugar de verbalizar el texto junto con el siguiente bloque como si fuese una frase larga.
* En modo exploración, presionando intro o espacio en una pestaña ahora la activa en lugar de cambiar a modo foco. (#1760)
* Actualizado el sintetizador de voz eSpeak a 1.45.46.

### Corrección de Fallos

* NVDA ya no muestra viñetas o numeración para listas en Internet Explorer y otros controles MSHTML cuando el autor ha indicado que éstas no deberíam mostrarse (es decir, el estilo de lista es "none"). (#1671)
* Reiniciar NVDA cuando se ha colgado (ej.: presionando control+alt+n) ya no sale de la copia previa sin comenzar otra nueva.
* Pulsar retroceso o flechas en una consola de órdenes de Windows ya no causa resultados extraños en algunos casos. (#1612)
* El elemento seleccionado en cuadros combinados WPF (y posiblemente algunos otros cuadros combinados mostrados utilizando UI Automation) que no permiten edición de texto ahora se anuncia correctamente.
* En modo exploración en Adobe Reader, ahora siempre es posible moverte a la siguiente fila desde la fila de encabezado y viceversa utilizando las órdenes moverse a la siguiente fila y moverse a la fila anterior. También,  la fila de encabezado ya no se anuncia como fila 0. (#1731)
* En modo exploración en Adobe Reader, ahora es posible mover a (y por lo tanto pasar) celdas vacías en una tabla.
* Información de posición sin sentido  (ej.: 0 de 0 nivel 0) ya no se anuncia en braille.
* Cuando el braille siga a la revisión, ahora podrá mostrarse contenido en revisión planan. (#1711)
* Un texto del control de texto ya no se presenta dos veces en una pantalla braille en algunos casos, ej.: desplazándose atrás desde el comienzo de documentos de Wordpad.
* En modo exploración en Internet Explorer, pulsando intro sobre un botón de subir un fichero ahora se presenta correctamente el diálogo para elegir un fichero para subir en lugar de cambiar a modo foco.  (#1720)
* Los cambios de contenido dinámico tales como en consolas del Dos ya no se anuncian si  el modo durmiente para esa aplicación está actualmente activado. (#1662)
* En modo exploración, el comportamiento de alt+flecha arriba y alt+flecha abajo para contraer y expandir cuadros combinados ha sido mejorado. (#1630)
* NVDA ahora se recupera de muchas más situaciones tales como aplicaciones que dejan de responder en las que anteriormente causaba un cuelgue completo. (#1408)
* Para documentos en modo exploración de Mozilla Gecko (Firefox etc) NVDA ya no fallará al interpretar texto en una situación muy específica donde un elemento is styled as display:table. (#1373)
* NVDA ya no anunciará controles etiqueta cuando el foco se mueva por ellos. Detiene el anunciado doble de etiquetas para algunos campos de formulario en Firefox (Gecko) e Internet Explorer (MSHTML). (#1650)
* NVDA ya no falla al leer una celda en Microsoft Excel después de pegar con control+v. (#1781)
* En Adobe Reader, ya no se anuncia información extraña acerca del documento cuando se mueva a un control en una página diferente en modo foco. (#1659)
* En modo exploración en aplicaciones de Mozilla Gecko (ej.: Firefox), los botones de comnutación ahora se detectan y anuncian correctamente. (#1757)
* NVDA ahora puede leer correctamente la barra de direcciones del Explorador de Windows en Windows 8 developer preview.
* NVDA ya no bloquea aplicaciones tales como winver y wordpad en Windows 8 developer preview debido a malas traducciones de glyph.
* En modo exploración en aplicaciones que utilizan Mozilla Gecko 10 y posteriores (ej.: Firefox 10), el cursor se coloca correctamente más amenudo cuando se carga una página con un ancla. (#360)
* En modo exploración en aplicaciones Mozilla Gecko (ej.: Firefox), las etiquetas para mapas de imagen ahora se interpretan.
* Con el seguimiento del ratón activado, al mover el ratón sobre ciertos campos de texto editable (tal como en Synaptics Pointing Device Settings y SpeechLab SpeakText) ya no causa que la aplicación se cuelgue. (#672)
* NVDA ahora funciona correctamente en varios diálogos Acerca de... en aplicaciones distribuídas con Windows XP, incluyendo el diálogo de acerca de... en Notepad y el diálogo de acerca de  en Windows. (#1853, #1855)
* Corregida la revisión por palabras en controles de edición de Windows. (#1877)
* Moverse fuera de un campo de texto editable con flecha izquierda, flecha arriba o avpág mientras se está en modo foco ahora cambia correctamente a modo exploración cuando está habilitado el modo foco automático para movimientos del cursor. (#1733)

### Ccambios para Desarrolladores

* NVDA ahora puede instruir a los sintetizadores de voz para cambiar los idiomas para secciones en particular de voz.
 * Para soportar esto, los controladores deben manejar speech.LangChangeCommand en secuencias pasadas a SynthDriver.speak().
 * Los objetos SynthDriver también deberían proporcionar el argumento de idioma a objetos VoiceInfo (o sobreescribir el atributo de idioma para capturar el idioma actual). de otro modo, el idioma de la interfaz de usuario de NVDA será utilizado.

## 2011.2

Lo subrayable en esta revisión incluye mejoras mayores concernientes a la puntuación y símbolos, incluyendo niveles configurables, etiquetado y descripciones de caracteres personalizados; sin pausas al final de las líneas durante la lectura completa; soporte mejorado para ARIA en Internet Explorer; y mucho mejor soporte para documentos PDF XFA/LiveCycle en Adobe Reader; acceso a texto escrito en la pantalla en más aplicaciones; y acceso a formato e información de color para texto escrito en la pantalla.

### Nuevas Características

* Ahora es posible escuchar la descripción para cualquier carácter dado presionando el script revisar carácter actual dos veces en sucesión rápida.  Para caracteres en Inglés esto es el alfabeto fonético inglés estándar. Para idiomas pictográficos tales como el Chino Mandarín, se proporcionan una o más frases de ejemplo utilizando el símbolo dado. También presionando revisar palabra actual o revisar línea actual tres veces deletreará la palabra/línea utilizando la primera de estas descripciones. En español se utiliza el alfabeto de deletreo radioaficionado ligeramente modificado(#55)
* Puede verse más texto en revisión plana para aplicaciones tales como Mozilla Thunderbird que escriben su texto directamente a la pantalla como glyphs.
* Ahora es posible elegir varios niveles de anunciado de puntuación y símbolos. (#332)
* Cuando la puntuación u otros símbolos se repiten más de una vez, ahora se anuncia el número de repeticiones  en lugar de verbalizar los símbolos repetidamente. (#43)
* Una nueva tabla de transcripción braille: braille computerizado noruego de 8 puntos. (#1456)
* La voz ya no hace pausas antinaturales al final de cada línea cuando se utiliza la orden para leer todo. (#149)
* NVDA ahora anunciará si algo se ordena (de acuerdo con la propiedad aria-sort) en navegadores Web. (#1500)
* Los patrones Braille unicode ahora se muestran correctamente en las pantallas braille. (#1505)
* En Internet Explorer y otros controles MSHTML cuando el foco se mueve dentro de un grupo de controles (surrounded by a fieldset), NVDA ahora anunciará el nombre del grupo (the legend). (#535)
* En Internet Explorer y otros controles MSHTML, las propiedades aria-labelledBy y aria-describedBy are now honoured.
* en Internet Explorer y otros controles MSHTML, ha sido mejorado el soporte para controles ARIA list, gridcell, slider y progressbar.
* Los usuarios ahora pueden cambiar la pronunciación de puntuación y otros símbolos, así como el nivel en que se verbalicen. (#271, #1516)
* En Microsoft Excel, el nombre de la hoja activa ahora se anuncia cuando se cambie de página con control+rePág o control+avPág. (#760)
* Cuando se navega por una tabla en Microsoft Word con la tecla tab NVDA ahora anunciará la celda actual según te muevas. (#159)
* Ahora puedes configurar si las coordenadas de una celda de tabla se anuncian desde el diálogo de preferencias de formato de documento. (#719)
* NVDA ahora puede detectar formato y color para texto escrito en la pantalla.
* En la lista de mensajes de Outlook Express/Windows Mail/Windows Live Mail, NVDA ahora anunciará el hecho de que un mensaje esté no leído y también si está expandido o contraído en el caso de hilos de conversación. (#868)
* eSpeak ahora tiene una opción de tasa de aumento que triplica la velocidad de la voz.
* Soporte para el control calendario que se encuentra en el diálogo de Información de Fhecha y Hora accedido desde el reloj de Windows 7. (#1637)
* Se han añadido combinaciones de teclas adicionales para la pantalla braille MDV Lilli. (#241)
* Nuevos idiomas: Búlgaro, Albanés.

### Cambios

* Para mover el cursor del sistema al cursor de revisión, ahora presiona el script mover foco al navegador de objetos (Sobremesa NVDA+shift+menos teclado numérico, portátil NVDA+shift+retroceso) dos veces en sucesión rápida. Esto libera más teclas en el teclado. (#837)
* Para escuchar la representación decimal y hexadecimal del carácter bajo el cursor de revisión, ahora presiona revisar carácter actual tres veces en lugar de dos veces, ya que dos veces ahora verbaliza la descripción del carácter.
* Actualizado el sintetizador de voz eSpeak a 1.45.03. (#1465)
* Las tablas de  diseño ya no  se anuncian en aplicaciones de Mozilla Gecko mientras se mueve el foco cuando se está en modo foco o fuera de un documento.
* En Internet Explorer y otros controles  MSHTML, el modo exploración ahora funciona para los documentos dentro de aplicaciones ARIA. (#1452)
* Actualizado el transcriptor braille  liblouis a 2.3.0.
* Cuando se está en modo exploración y se salta a un control con quicknav o foco, la descripción del control ahora se anuncia si tiene uno.
* Las barras de progreso ahora se anuncian en modo exploración.
* Los nodos marcados  con un rol ARIA de presentación en Internet Explorer y otros controles MSHTML ahora se filtran fuera de la revisión simple y el ancestro del foco.
* La interfaz de usuario y la documentación de NVDA ahora se refieren a los modos virtuales como modo exploración , ya que el término "virtual buffer" es menos comprensible para la mayoría de los usuarios. (#1509)
* Cuando el usuario desee copiar sus opciones de usuario al perfil del sistema para utilizarlas en pantallas de autentificación, etc., y sus opciones contengan plugins personales, ahora serán advertidos de que esto podría suponer un riesgo de seguridad. (#1426)
* El servicio NVDA ya no inicia y detiene a NVDA en escritorios de entrada de usuario.
* En Windows XP y Windows Vista, NVDA ya no hace uso de UI Automation aún si está disponible a través de la actualización de la plataforma. Aunque utilizando UI Automation se puede mejorar la accesibilidad de algunas aplicaciones modernas, en XP y Vista había muchos cuelgues, rupturas y se perdía toda la buena funcionalidad utilizándolo. (#1437)
* En aplicaciones que utilizan Mozilla Gecko 2 y posterior (tales como Firefox 4 y posterior), ahora puede leerse un documento en modo exploración antes de que la carga finalice completamente.
* NVDA anuncia ahora el estado de un contenedor cuando el foco se mueva a un control dentro de él (ej.: si el foco se mueve dentro de un documento que todavía se esté cargando lo anunciará como ocupado).
* La interfaz de usuario y documentación de NVDA ya no utilizan los términos "primer hijo" y "padre" con respecto a navegación de objetos, pues estos términos son confusos para muchos usuarios.
* Ya no se anuncia contraído para algunos elementos de menú que tienen submenús.
* El script reportCurrentFormatting (NVDA+f) ahora anuncia el formato en la posición del cursor de revisión antes que el cursor del sistema / foco. Ya que de forma predeterminada el cursor de revisión sigue al del sistema, la mayor parte de la gente no debería notar la diferencia.  Sin embargo esto ahora posibilita al usuario mirar el formato cuando se mueva el cursor de revisión, tal como en la revisión plana.

### Corrección de fallos

* Contraer cuadros combinados en documentos en modo exploración cuando el modo foco ha sido forzado con NVDA+espacio ya no retorna automáticamente a modo exploración. (#1386)
* En documentos Gecko (ej.: Firefox) y MSHTML (ej.: Internet Explorer), NVDA ahora procesa correctamente  cierto texto en la misma línea que previamente fue procesado en líneas separadas. (#1378)
* Cuando el Braille sigue a la revisión y el navegador de objetos se mueve a un documento en modo exploración, o manualmente o debido a un cambio de foco, el braille mostrará adecuadamente el contenido del modo de navegación. (#1406, #1407)
* Cuando la verbalización de la puntuación esté desactivada, cierta puntuación ya no se verbaliza incorrectamente cuando se utilicen algunos sintetizadores. (#332)
* Ya no ocurren problemas cuando se carga la configuración para sintetizadores que no soportan la opción de voz tales como Audiologic Tts3. (#1347)
* El menú de Skype Extras ahora se lee correctamente. (#648)
* Marcando la casilla de verificación Brillo Controla el Volumen en el diálogo Opciones de Ratón ya no debería causar un retraso mayor para pitidos cuando se mueve el ratón a lo largo de la pantalla en Windows Vista/Windows 7 con Aero activado. (#1183)
* Cuando NVDA se configura para utilizar la distribución de teclado portátil, NVDA+suprimir ahora funciona como se documentó para anunciar las dimensiones del navegador de objetos actual. (#1498)
* NVDA ahora cumple apropiadamente con el atributo aria-selected en documentos de Internet Explorer.
* Cuando NVDA cambia automáticamente a modo foco en documentos de modo exploración, ahora anuncia información acerca del contexto del foco. Por ejemplo, si un elemento de un cuadro de lista recive el foco, el cuadro de lista se anunciará primero. (#1491)
* En Internet Explorer y otros controles MSHTML, los controles ARIA listbox ahora se tratan como listas, en lugar de como elementos de lista.
* Cuando un control editable de texto de solo lectura recibe el foco, NVDA ahora informa de que es de sólo lectura. (#1436)
* En modo exploración, NVDA ahora funciona correctamente con respecto a campos de texto editable de solo lectura.
* En documentos en modo exploración, NVDA ya no cambia incorrectamente de modo foco cuando aria-activedescendant está configurado; ej.: cuando la finalización de la lista aparece en algunos controles con autocompletado.
* En Adobe Reader, el nombre de controles ahora se anuncia cuando se mueve el foco o se utiliza navegación rápida en modo exploración.
* En documentos XFA PDF en Adobe Reader, botones, enlaces y gráficos ahora se procesan correctamente.
* En documentos XFA PDF en Adobe Reader, todos los elementos ahora se procesan en líneas por separado.  Este cambio se hizo porque las secciones grandes (a veces todo el documento) se procesaban sin saltos debido al retraso general de la estructura en estos documentos.
* Corregidos problemas cuando se mueve el foco desde campos de texto editable en documentos XFA PDF en Adobe Reader.
* En documentos XFA PDF en Adobe Reader, los cambios al valor de un cuadro combinado enfocado ahora se anunciarán.
* Los cuadros combinados Owner-drawn tales como los de elegir colores en Outlook Express ahora son accesibles con NVDA. (#1340)
* En idiomas que utilizan un espacio como separador de grupo de millar tales como francés y alemán, los números de grupos separados de texto ya no se pronuncian como un sólo número. Esto era particularmente problemático para celdas de tablas que contengan números. (#555)
* los nodos con un rol de descripción de ARIA en Internet Explorer y otros controles MSHTML ahora se clasifican como texto estático, no como campos de edición.
* Corregidos varios problemas cuando se presiona tab mientras el foco está en un documento en modo exploración (ej.: tab se mueve inapropiadamente a la barra de direcciones en Internet Explorer). (#720, #1367)
* Cuando se entra en listas mientras se lee texto, NVDA ahora dice, por ejemplo, "lista con 5 elementos" en lugar de "listacon 5 elementos". (#1515)
* En el modo de ayuda de entrada, los gestos están en el sistema aun si sus scripts dejan pasar la ayuda de entrada tales como las órdenes de desplazamiento de la pantalla braille hacia adelante y atrás.
* En el modo de ayuda de entrada, cuando una modificadora se mantiene pulsada en el teclado, NVDA ya no anuncia la modificadora como si se modificase a sí misma; ej.: NVDA+NVDA.
* En documentos de Adobe Reader, el presionado de c o shift+c para navegar a un cuadro combinado ahora funciona.
* El estado seleccionado de filas de tabla seleccionables ahora se anuncia del mismo modo que para los elementos de lista y árbol.
* Los controles en Firefox y otras aplicaciones Gecko ahora pueden activarse mientras se está en modo exploración aún si su contenido ha estado flotando fuera de pantalla. (#801)
* Ya no se puede mostrar un diálogo de opciones de NVDA mientras se está mostrando un mensaje de diálogo, ya que el diálogo de opciones se colgaba en este caso. (#1451)
* En Microsoft Excel, ya no hay un retraso cuando se mantenían pulsadas o se pulsaban teclas rápidamente para moverse entre celdas o seleccionarlas.
* Corregidas rupturas del servicio NVDA que significaban que NVDA paraba de ejecutarse en en ventanas seguras de Windows.
* Corregidos problemas que ocurrían a veces con pantallas braille cuando un cambio causaba que el texto que estaba mostrándose desapareciera.
* La ventana de descargas en Internet Explorer 9 ahora puede navegarse y leerse con NVDA. (#1280)
* Ya no es posible iniciar accidentalmente múltiples copias de NVDA al mismo tiempo. (#507)
* En sistemas lentos, NVDA ya no causa que su ventana principal se muestre inapropiadamente todo el tiempo mientras se ejecuta. (#726)
* NVDA ya no se rompe en Windows xP cuando se inicia una aplicación WPF. (#1437)
* Leer todo y leer todo con cursor de revisión ahora podrá funcionar en algunos controles de texto UI automation que soporten todos los métodos necesarios. (ej.: ahora puedes utilizar verbalizar toda la revisión en documentos de XPS Viewer).
* NVDA ya no clasifica inapropiadamente algunos elementos de lista en el aplique de reglas de mensajes en Outlook Express / Windows Live Mail ahora el diálogo es como casillas de verificación. (#576)
* Los cuadros combinados ya no se anuncian como teniendo un submenú.
* NVDA ahora podrá leer el recipiente en los campos para, CC y CCO en Microsoft Outlook. (#421)
* Corregido el fallo en el diálogo de Opciones de Voz de NVDA donde el valor de las barras de desplazamiento  a veces no se anunciaba cuando cambiaban. (#1411)
* NVDA ya no falla al anunciar la celda nueva cuando se mueve en una hoja Excel después de cortar y pegar. (#1567)
* NVDA ya no lo hace tan mal adivinando los nombres de los colores anunciando la mayoría de los mismos.
* En Internet Explorer y otros controles MSHTML, se corrigió la incapacidad para leer partes de páginas extrañas que contienen iframes marcados con un rol ARIA de presentación. (#1569)
* En Internet Explorer y otros controles MSHTML, se corrigió un problema extraño donde el foco permanecía rebotando infinitamente entre el documento y un campo editable de texto multilínea en modo foco. (#1566)
* En Microsoft Word 2010 NVDA ahora leerá automáticamente los diálogos de confirmación. (#1538)
* En campos editables multilínea de texto en Internet Explorer y otros controles MSHTML, la selección en líneas después del primero ahora se anuncia correctamente. (#1590)
* Mejorado el movimiento por palabras en muchos casos, incluyendo modo exploración y controles de edición de Windows. (#1580)
* El instalador de NVDA ya no muestra texto confuso para versiones para Hong Kong de Windows Vista y Windows 7. (#1596)
* NVDA ya no falla al cargar el sintetizador de Microsoft Speech API versión 5 si la configuración contiene opciones para ese sintetizador pero falta la opción de la voz. (#1599)
* En campos de texto editable en Internet Explorer y otros controles MSHTML, NVDA ya no se retrasa o se congela cuando el braille esté activado.
* En el modo exploración de firefox, NVDA ya no se niega a incluir contenido que esté dentro de un nodo enfocable con un rol ARIA de presentación.
* En Microsoft Word con el braille activado, las líneas en páginas después de la primera página ahora se anuncian correctamente. (#1603)
* En Microsoft Word 2003, las líneas de texto de derecha a izquierda pueden leerse una vez de nuevo con el braille activado. (#627)
* En Microsoft Word, leer todo ahora funciona correctamente cuando el documento no finaliza con un final de frase.
* Cuando se abre un mensaje de texto plano en Windows Live Mail 2011, NVDA enfocará correctamente el documento de mensaje permitiendo que se lea.
* NVDA ya no se bloquea o se niega a hablar temporalmente cuando está en los diálogos Mover a / Copiar a en Windows Live Mail. (#574)
* En Outlook 2010, NVDA ahora seguirá correctamente el foco en la lista de mensajes. (#1285)
* Se han resuelto algunos problemas de conexión de USB con la pantalla braille MDV Lilli. (#241)
* En Internet explorer y otros controles MSHTML, los espacios ya no se ignoran en modo exploración en ciertos casos (es decir después de un enlace).
* En Internet Explorer y otros controles MSHTML, han sido eliminados algunos extraños cambios de línea en modo exploración. Específicamente, elementos HTML con un estilo de pantalla None ya no fuerza un salto de línea. (#1685)
* Si NVDA no es capaz de iniciarse, el fracaso para reproducir el sonido de parada crítica de Windows ya no anula el mensaje de error crítico en el fichero de registro.

### Cambios para Desarrolladores

* La documentación de desarrolladores ahora puede generarse utilizando SCons. mira readme.txt en la raíz de la distribución fuente para detalles, incluyendo dependencias asociadas.
* Las Localizaciones ahora pueden proporcionar descripciones para caracteres. Mira la sección Character Descriptions de la Developer Guide para detalles. (#55)
* Las Localizaciones ahora pueden proporcionar información acerca de la pronunciación de puntuación específica y otros símbolos. Mira la sección Symbol Pronunciation de la Developer Guide para detalles. (#332)
* Ahora puedes compilar NVDAHelper con varias opciones de depuración utilizando la variable nvdaHelperDebugFlags SCons. Mira readme.txt en la raíz de la distribución de fuentes de para detalles. (#1390)
* Los controladores de síntesis ahora se pasan como una secuencia de texto y órdenes de voz a verbalizar, en lugar de sólo texto y un índice.
 * Esto permite índices integrados, cambios de parámetros, etc.
 * Los controladores deberían implementar SynthDriver.speak() en lugar de SynthDriver.speakText() y SynthDriver.speakCharacter().
 * Los métodos antiguos se utilizarán si SynthDriver.speak() no se implementó, pero han quedado en desuso y se eliminarán en una versión futura.
* se ha eliminado gui.execute(). Debería utilizarse wx.CallAfter() en su lugar.
* ha sido eliminado gui.scriptUI .
 * Para diálogos de mensaje, utiliza wx.CallAfter(gui.messageBox, ...).
 * Para todos los demás diálogos, deberían utilizarse los diálogos propios de wx en su lugar.
 * Una nueva función gui.runScriptModalDialog() simplifica la utilización de diálogos modales de scripts.
* Ahora los controladores de sintetizador pueden soportar opciones booleanas.  Mira SynthDriverHandler.BooleanSynthSetting.
* SCons ahora accepta una variable certTimestampServer especifycando la URL de un servidor timestamping para utilizar unas marcas timestamp authenticode. (#1644)

## 2011.1.1

Esta versión corrige varios problemas de seguridad y otros importantes encontrados en NVDA 2011.1.

### Corrección de Fallos

* El elemento Donar en el menú NVDA ahora se desactiva cuando se ejecuta en la autentificación, bloqueo, UAC y otras Ventanas de pantallas seguras, ya que esto es un riesgo de seguridad. (#1419)
* Ahora es imposible copiar o pegar dentro de la ventana de interfaz del usuario de NVDA mientras se está en escritorios seguros (Pantalla bloqueada, pantalla del UAC y autentificación de windows) ya que esto es un riesgo de seguridad. (#1421)
* En Firefox 4, la orden mover al contenido del modo virtual (NVDA+control+espacio) ahora funciona como debería escapar de objetos empotrados tales como contenido Flash. (#1429)
* Cuando verbalizar teclas de órdenes esté activado, los caracteres mayusculados ya no se verbalizan incorrectamente como teclas de órdenes. (#1422)
* Cuando verbalizar teclas de órdenes esté activado,, presionando espacio con otros modificadores que shift (tales como control y alt) ahora se anuncian como una tecla de órdenes. (#1424)
* El Logging ahora se desactiva completamente cuando se ejecute desde la autentificación, bloqueo, UAC y otras ventanas seguras, ya que esto es un riesgo de seguridad. (#1435)
* En el modo de ayuda de entrada, los gestos ahora se conectan aun si no están vinculados a un script (de acuerdo con la guía del usuario. (#1425)

## 2011.1

Lo subrayable en esta versión incluye el anunciado de colores para algunos controles; anunciado automático de la salida de texto nuevo en mIRC, PuTTY, Tera Term y SecureCRT; soporte para plugins globales; anunciado de viñetas  y numeración en Microsoft Word; combinaciones de teclas adicionales para pantallas braille, incluyendo teclas para moverse a la línea siguiente y anterior; y soporte para varias pantallas braille Baum, HumanWare y APH.

### Nuevas Características

* Ahora se pueden anunciar los colores para algunos controles. El anunciado automático se puede configurar en el diálogo de preferencias de formateado de documentos. También se pueden anunciar bajo demanda utilizando la orden de anunciado de formato de texto (NVDA+f).
 * Inicialmente, esto se soporta en controles de texto estándar IAccessible2 (tales como en aplicaciones de Mozilla), controles RichEdit (tales como en Wordpad) y controles de texto de IBM Lotus Symphony.
* En los modos virtuales, ahora puedes seleccionar por página (utilizando shift+AvPág y shift+RePág) y por párrafos(utilizando shift+control+Flecha Abajo y shift+control+Flecha Arriba). (#639)
* NVDA ahora anuncia la salida de texto nuevo en mIRC, PuTTY, Tera Term y SecureCRT. (#936)
* Los usuarios ahora pueden añadir nuevas combinaciones de teclas o o sobreescribir las existentes para cualquier script en NVDA proporcionando un sencillo mapa de movimientos de entrada del usuario. (#194)
* Soporte para plugins globales. Los plugins globales pueden añadir nueva funcionalidad a NVDA que funcione en todas las aplicaciones. (#281)
* Ahora se escucha un pequeño pitido cuando se teclean caracteres con la tecla shift mientras el BloqMayus esté activado. Esto se puede desactivar desmarcando la nueva opción relacionada en el diálogo de Opciones de Teclado . (#663)
* ahora se anuncian los saltos de página cuando nos movemos por líneas en Microsoft Word. (#758)
* Las viñetas y la numeración se verbalizan ahora en Microsoft Word cuando nos movemos por líneas. (#208)
* Ahora está disponible una orden para activar o desactivar el modo Durmiente para la aplicación actual (NVDA+shift+s). El Modo Durmiente (anteriormente conocido como modo de voz propia) desactiva toda la funcionalidad de lectura de la pantalla en NVDA para una aplicación en particular. Muy útil para aplicaciones que proporcionan su propia voz y o características de lectura de pantalla. Presiona esta orden de nuevo para desactivar el Modo Durmiente.
* Se añadieron algunas combinaciones de teclas adicionales para pantallas braille. Mira la sección pantallas braille Soportadas de la Guía del Usuario para detalles. (#209)
* Para conveniencia de desarrolladores de terceras partes, los app modules así como los plugins globales ahora se pueden recargar sin reinicializar NVDA. Utiliza Herramientas -> Recargar plugins en el menú de NVDA o NVDA+control+f3. (#544)
* NVDA ahora recuerda la posición donde estabas cuando regresas a una página anteriormente visitada. Esto se aplica hasta que o el navegador o NVDA sean cerrados. (#132)
* Las pantallas braille Handy Tech ahora pueden utilizarse sin instalar el controlador universal de Handy Tech. (#854)
* Soporte para varias pantallas braille Baum, HumanWare y APH. (#937)
* Ahora se reconoce la barra de estado en Media Player Classic Home Cinema.
* Ahora la pantalla braille Freedom Scientific Focus 40 Blue puede utilizarse cuando se conecte a través de bluetooth. (#1345)

### Cambios

* La información de posición ya no se anuncia de manera predeterminada en algunos casos dónde era normalmente incorrecto; ej.: la mayoría de los menús, la barra de aplicaciones en ejecución, el área de notificaciones, etc. No obstante, esto puede activarse de nuevo con una opción añadida en el diálogo de Opciones de presentación de objetos.
* Ayuda de Teclado se ha renombrado a Ayuda de entrada para reflejar que se maneja entrada desde otras fuentes que el teclado.
* La localización de un script en el código ya no se anuncia en la ayuda de entrada puesto que es irrelevante y críptica para el usuario.
* Cuando NVDA detecta que se ha colgado, continúa interceptando  las teclas modificadoras de NVDA, aunque deja pasar todas las demás teclas del sistema. Esto previene al usuario de conmutar inintencionalmente el BlogMayus, etc. Si presionan una tecla modificadora de NVDA sin realising NVDA has frozen. (#939)
* Si las teclas se mantienen pulsadas después de utilizar la orden de dejar pasar, todas las teclas (incluyendo repeticiones de teclas) ahora se pasan hasta que la última tecla  sea soltada.
* Si una tecla modificadora de NVDA se presiona dos veces en sucesión rápida para pasarla y la segunda presionada está pulsada, todas las teclas repetidas ahora se pasarán también.
* Las teclas subir, bajar volumen y silenciar ahora se anuncian  en la Ayuda de Entrada. Esto podría ser de utilidad si el usuario no sabe qué hacen esas teclas.
* La tecla rápida para el elemento Cursor de Revisión en el menú de Preferencias de NVDA ha sido cambiado de r a c para eliminar el conflicto con el elemento de Opciones de Braille.

### Corrección de Fallos

* Cuando se añade una nueva entrada del diccionario del habla, el título del diálogo ahora es "Añadir Entrada de Diccionario" en lugar de "Editar entrada de diccionario". (#924)
* En los diálogos del diccionario del habla, el contenido de las columnas de la Expresión Regular y sensible a las mayúsculas de la lista de entradas de diccionario  se presenta ahora en el idioma configurado en NVDA en lugar de siempre en Inglés.
* En AIM, la información de posición ahora se anuncia en árboles.
* En barras de deslizamiento en el diálogo Opciones de Voz, flecha arriba/rePág/inicio ahora incrementan la opción y flecha abajo/AvPág/fin la decrementan. Anteriormente, ocurría lo opuesto, lo cual no es lógico y es inconsistente con las opciones del grupo synth. (#221)
* En modos virtuales con la distribución de pantalla deshabilitada, ya no aparecen algunas extrañas líneas en blanco.
* Si una tecla modificadora de NVDA se presiona dos veces rápidamente pero hay una tecla presionada interviniendo, la tecla modificadora de NVDA ya no pasa en la segunda presión.
* Las teclas de puntuación ahora se verbalizan en la ayuda de entrada cuando la verbalización de la puntuación esté desactivada. (#977)
* En el diálogo Opciones de Teclado, los nombres de distribución de teclado ahora se presentan en el idioma configurado para NVDA en lugar de siempre en Inglés. (#558)
* Corregido un problema donde algunos elementos se renderizaban como vacíos en documentos de Adobe Reader; ej.: los enlaces en la tabla de contenido de la Guía del usuario del Apple iPhone IOS 4.1.
* El botón "Utilizar opciones actuales guardadas en el logon y otras pantallas seguras" en el diálogo de Opciones Generales de NVDA, funciona si se utilizó inmediatamente después de que NVDA sea instalado nuevamente pero antes de que una pantalla segura haya aparecido.  Anteriormente, NVDA anunciaba que el copiado tuvo éxito, pero actualmente no tenía efecto. (#1194)
* Ya no es posible tener dos diálogos de opciones de NVDA abiertos simultáneamente. Esto corrige errores donde un diálogo abierto depende de otro diálogo abierto; es decir, cambiar el sintetizador mientras el diálogo Opciones de Voz está abierto. (#603)
* En sistemas con UAC activado, el botón "Utilizar opciones actualmente guardadas en el logon y pnatallas seguras" en el diálogo de Opciones Generales del NVDA, ya no falla después del UAC si el nombre de la cuenta del usuario contiene un espacio. (#918)
* En Internet Explorer y otros controles MSHTML, NVDA utiliza ahora la URL como un último resorte para determinar el nombre de un enlace, más que presentar enlaces vacíos. (#633)
* NVDA ya no ignora el foco en los menús de AOL Instant Messenger 7. (#655)
* Anunciar la etiqueta correcta para errores en el diálogo del corrector de ortografía de Microsoft Word (ej.: No en diccionario, error gramatical, puntuación). Anteriormente todos se anunciaban como error gramatical. (#883)
* Tecleando en Microsoft Word mientras se utiliza una pantalla braille ya no debería causar que sea tecleado texto ilegible, y un extraño cuelgue cuando se presiona un sensor de seguimiento braille en documentos de Word ha sido corregido. (#1212) No osstante una limitación es que el texto en árabe puede no leerse ya en Word 2003 y superior, mientras se utiliza una pantalla braille. (#627)
* Cuando se presiona la tecla supr en un campo de edición, el texto/cursor en una pantalla braille ahora debería actualizarse siempre apropiadamente para reflejar el cambio. (#947)
* Los cambios en páginas en documentos Gecko2 (Ej.: Firefox 4) mientras se abren múltiples pestañas ahora se refleja adecuadamente por NVDA. Anteriormente sólo los cambios en la primera pestaña se reflejaban. (Mozilla bug 610985)
* NVDA ahora puede anunciar apropiadamente las sugerencias para errores gramaticales y de puntuación en el diálogo del corrector de ortografía de Microsoft Word. (#704)
* En Internet Explorer y otros controles MSHTML, NVDA ya no presenta anclas de destino como enlaces vacíos en su modo virtual. En su lugar, estas anclas se ocultan según debería ser. (#1326)
* La navegación de objetos sobre y dentro de brupos estándar de windows ya no rompe y asymmetrical.
* En Firefox y otros controles basados en Gecko, NVDA ya no se queda pegado en un submarco si finaliza cargando antes de otro documento.
* NVDA ahora anuncia apropiadamente el siguiente caracter cuando se elimina un caracter con suprimir del teclado numérico. (#286)
* En la pantalla de autentificación de Windows XP, el nombre de usuario se anuncia una vez de nuevo cuando el usuario seleccionado se cambió.
* Corregidos problemas cuando al leer texto en consolas de órdenes de Windows el anunciado de números de línea está activado.
* El diálogo de lista de elementos para modos virtuales ahora es utilizable por usuarios videntes.  Todos los controles son visibles en pantalla. (#1321)
* La lista de entradas en el diálogo Diccionarios del Habla, ahora es más legible por usuarios videntes.  La lista ahora es bastante grande para mostrar todas sus columnas en pantalla. (#90)
* En pantallas braille ALVA BC640/BC680 NVDA ya no hace caso omiso de las teclas de la pantalla que todavía están siendo pulsadas después que otra tecla se suelte.
* Adobe Reader X ya no se rompe cuando se cierra un documento sin opciones no etiquetadas antes de que aparezca el diálogo de procesamiento. (#1218)
* NVDA ahora cambia al controlador de pantalla braille apropiado cuando vuelvas a la configuración guardada. (#1346)
* El asistente de proyecto de Visual Studio 2008 se lee correctamente nuevamente. (#974)
* NVDA ya no falla completamente al trabajar en aplicaciones que contengan caracteres no ASCII en su nombre del ejecutable. (#1352)
* Cuando se lee por líneas en AkelPad con el salto de palabras activado, NVDA ya no lee el primer caracter de la línea siguiente en el final de la línea actual.
* En el editor de código de Visual Studio 2005/2008, NVDA ya no lee todo el texto después de cada caracter tecleado. (#975)
* Corregido el problema donde algunas pantallas braille no se limpiaban correctamente cuando NVDA se cerraba o se cambiaba la pantalla braille.
* El foco inicial ya no se verbaliza en algunas ocasiones dos veces cuando NVDA arranca. (#1359)

### Cambios para Desarrolladores

* SCons ahora se utiliza para preparar el árbol fuente y crear compilaciones binarias, archivos portables, instaladores, etc. Mira readme.txt en la raíz de la distribución fuente para detalles.
* Los nonbres de teclas utilizados por NVDA (incluyendo mapas de teclas) han sido hechos más amigables/lógicos; ej.: upArrow en lugar de extendedUp y numpadPageUp en lugar de prior. Mira el módulo vkCodes para una lista.
* Toda la salida del usuario ahora se representa por una instancia inputCore.InputGesture. (#601)
 * Cada fuente de la entrada es una subclase de la clase base InputGesture.
 * La pulsación de teclas en el teclado del sistema se incluye en la clase keyboardHandler.KeyboardInputGesture.
 * La pulsación de botones, ruedas y otros controles en una pantalla braille se incluye en las subclases de la clase braille.BrailleDisplayGesture . Estas subclases se proporcionan por cada controlador de pantalla braille.
* Los gestos de entrada se vinculan a ScriptableObjects utilizando el método ScriptableObject.bindGesture() en una instancia o un diccionario __gestures en la clase cuyos identificadores de mapas de gestos a nombres de scripts. Mira baseObject.ScriptableObject para detalles.
* Los módulos de aplicación ya no tienen fichero de mapa de teclas. Todos los vínculos de entrada de gestos deben hacerse en el appModule mismo.
* Todos los scripts ahora toman una sentencia InputGesture en lugar de una pulsación de tecla.
 * Pueden enviarse keyboardInputGestures al OS utilizando el método send() del gesto.
* Para enviar una pulsación de tecla arbitrariamente, ahora debes crear un KeyboardInputGesture utilizando KeyboardInputGesture.fromName() y luego utilizar su método send().
* Las localizaciones ahora podrán proporcionar un fichero de mapa de gesto de entrada para añadir nuevos vínculos o sobreescribir los vínculos existentes para los scripts en cualquier sitio de NVDA. (#810)
 * Los mapas de gestos de localización deben colocarse en locale\LANG\gestures.ini, donde LANG es el código de idioma.
 * Consulta inputCore.GlobalGestureMap para detalles del formato del fichero.
* Los nuevos comportamientos LiveText y Terminal NVDAObject facilitan la notificación automática de nuevo texto. Ver esas clases en NVDAObjects.behaviors para más detalles. (#936)
 * La clase de sobreimpresión NVDAObjects.window.DisplayModelLiveText se puede utilizar para objetos que deben recuperar texto escrito en la pantalla.
 * Consulta los appModules de mirc y de putty para ejemplos de uso.
* Ya no existe un appMolule _default. En su lugar, los appModules deben subclasificar appModuleHandler.AppModule (la clase AppModule base).
* Soporte para plugins blobales que puede vincular globalmente scripts, maneja eventos NVDAObject y elige clases NVDAObject. (#281) See globalPluginHandler.GlobalPlugin for details.
* En los objetos SynthDriver, los atributos available* de los ajustes de cadena (por ejemplo, availableVoices y availableVariants) son ahora OrderedDicts con clave ID en lugar de listas.
* synthDriverHandler.VoiceInfo ahora toma un argumento opcional de idioma que especifica el idioma de la voz.
* Los objetos SynthDriver ahora proporcionan un atributo de idioma que especifica el idioma de la voz actual.
 * La implementación base utiliza el idioma especificado en los objetos VoiceInfo en availableVoices. Esto es adecuado para la mayoría de los sintetizadores que admiten un idioma por voz.
* Se han mejorado los controladores de la pantalla Braille para permitir que los botones, las ruedas y otros controles se vinculen a los scripts de NVDA:
 * Los controladores pueden proporcionar un mapa de gestos de entrada global para añadir enlaces para scripts en cualquier parte de NVDA.
 * También pueden proporcionar sus propios scripts para realizar funciones específicas de visualización.
 * Consulta braille.BrailleDisplayDriver para detalles y controladores de pantallas braille existentes para ejemplos.
* La propiedad 'selfVoicing' de las clases AppModule ha sido renombrada a 'sleepMode'.
* Los eventos de appModule: event_appLoseFocus y event_appGainFocus ahora se han renombrado a event_appModule_loseFocus y event_appModule_gainFocus respectivamente, para mantener la sintaxis de nombrado igual que entre appModules y treeInterceptors etc.
* Todos los controladores de pantalla braille deben utilizar ahora braille.BrailleDisplayDriver en lugar de braille.BrailleDisplayDriverWithCursor.
 * El cursor se gestiona ahora fuera del controlador.
 * Los controladores existentes sólo tienen que cambiar su declaración de clase en consecuencia y cambiar el nombre de su método _display a display.

## 2010.2

Las características más notables de esta versión incluyen una gran simplificación de la navegación de objetos; modos virtuales para contenido de Adobe Flash; acceso a muchos controles anteriormente inaccesibles capturando texto escrito a la pantalla; revisión plana de texto en pantalla; soporte para documentos de IBM Lotus Symphony; anunciado de encabezados de fila y columna de tabla en Mozilla Firefox; una mejora significativa de la documentación del usuario.

### Nuevas Características

* La navegación por objetos con el cursor de revisión ha sido muy simplificada. El cursor de revisión ahora excluye objetos que no sean útiles para el usuario; es decir, objetos sólo utilizados para propósitos de diseño y objetos no disponibles.
* En aplicaciones que utilizan el Java Access Bridge (incluyendo OpenOffice.org), el formato ahora puede informarse en controles de texto. (#358, #463)
* Cuando se mueve el ratón sobre celdas en Microsoft Excel, NVDA las anunciará apropiadamente.
* En aplicaciones que utilizan el Java Access Bridge, el texto de un diálogo ahora se anuncia cuando el diálogo aparezca. (#554)
* Ahora se puede utilizar un modo virtual para navegar por el contenido de adobe Flash. Navegar por objetos e interactuar con los controles directamente (activando el modo foco) ya se soporta. (#453)
* Los controles de texto editable en el IDE Eclipse, incluyendo el editor de código, ahora son accesibles. Debes utilizar Eclipse 3.6 o superior. (#256, #641)
* NVDA ahora puede recuperar la mayoría de texto escrito en la pantalla. (#40, #643)
 * Esto permite la lectura de controles que no exponen información en formas más directas/fiables.
 * Los controles que se accesibilizan por esta característica incluyen: algunos elementos de menú que muestran iconos (ej.: el menú Abrir con en ficheros en Windows XP) (#151), campos de texto editables en aplicaciones Windows Live (#200), la lista de errores en Outlook Express (#582), el control de texto editable en TextPad (#605), listas en Eudora, muchos controles en Australian E-tax y la barra de fórmulas en Microsoft Excel.
* Soporte para el editor de código en Microsoft Visual Studio 2005 y 2008. Al menos se requiere Visual Studio Standard; esto no funciona en las ediciones Express. (#457)
* Soporte para documentos en IBM Lotus Symphony.
* Soporte primario y experimental paraGoogle Chrome. Por favor ten en cuenta que el soporte para lectores de pantalla de Chrome está lejos de completarse y requerirá trabajo adicional también en NVDA. Necesitarás una compilación de desarrollo reciente de Chrome para probar esto.
* El estado de las teclas conmutables (Bloq Mayus, bloq núm y bloqueo de desplazamiento) ahora se muestra en braille cuando son pulsadas. (#620)
* Los globos de ayuda ahora se muestran en braille cuando aparezcan. (#652)
* Añadido un controlador para la pantalla braille MDV Lilli. (#241)
* Cuando se selecciona una fila o una columna completa en MS Excel con las teclas de atajo shift+espacio y control+espacio, la nueva selección ahora se anuncia. (#759)
* Los encabezados de fila y columna ahora pueden anunciarse. Esto es configurable desde el diálogo de preferencias de formato de documento.
 * Actualmente, esto se soporta en documentos en aplicaciones de Mozilla tales como Firefox y Thunderbird. (#361)
* Introducidas órdenes para la revisión plana: (#58)
 * NVDA+7 teclado numérico cambia a revisión plana, colocando el cursor de revisión en la posición del objeto actual, permitiéndote revisar la pantalla (o un documento si se está dentro de uno) con las órdenes de revisión de texto.
 * NVDA+1 teclado numérico mueve el cursor de revisión al objeto representado por el texto en la posición del cursor de revisión, permitiéndote navegar por objetos desde ese punto.
* Las opciones de usuario actuales de NVDA pueden copiarse para utilizarse en las pantallas de autentificación/UAC, presionando un botón en el diálogo Opciones Generales.
* Soporte para Mozilla Firefox 4.
* Soporte para Microsoft Internet Explorer 9.

### Ccambios

* Leer todo en el navegador de objetos  (NVDA+más del teclado numérico), siguiente objeto en flujo del navegador de objetos (NVDA+shift+6 del teclado numérico) y anterior objeto en flujo en el navegtador de objetos (NVDA+shift+4 del teclado numérico) han sido eliminados de momento, debido a fallos y para liberar las teclas para otras posibles características.
* En el diálogo de sintetizadores de NVDA, ahora sólo se muestra el sintetizador listado. Anteriormente, se prefijaba con el nombre del controlador, que sólo es relevante internamente.
* Cuando se está en aplicaciones empotradas o modos virtuales dentro de otro modo virtual (ej.: Flash), ahora puedes presionar nvda+control+espacio para salir de la aplicación empotrada o modo virtual, al documento principal. Anteriormente, nvda+espacio  se utilizaba para esto. Ahora nvda+espacio es sólo específicamente para conmutar los modos revisión/foco en los modos virtuales.
* Si al visor de voz (activable en el menú Herramientas) se le dió el foco (ej.: it se hizo clic) el texto nuevo no aparecerá en el control hasta que el foco se mueva. Esto se permite para seleccionar el texto con mayor facilidad (ej.: para copiar).
* El visualizador de registro y la consola de Python se maximizan cuando se activen.
* Cuando se enfoca una hoja de cálculo en MS Excel, y hay más de una celda seleccionada, se anuncia el alcance de la selección, en lugar de sólo la celda activa. (#763)
* El guardado de la configuración, y el cambio de opciones sensibles en particular, ahora se desactiva cuando se ejecute en modo seguro (en las pantallas de autentificación/UAC).
* Actualizado el sintetizador de voz eSpeak a 1.44.01.
* Si NVDA ya está ejecutándose, activando el atajo de teclado de NVDA en el escritorio (que es el presionado de control+alt+n) reiniciará a NVDA.
* Se elimina la casilla de verificación anunciar texto bajo el ratón del diálogo Opciones de Ratón y se reenplaza con una casilla de verificación Activar seguimiento del Ratón, que mejora el emparejado del conmutado del script de seguimiento del ratón (NVDA+m).
* Se actualiza la distribución de teclado laptop tal que incluya todas las órdenes disponibles en la distribución desktop y funciona correctamente en teclados no ingleses. (#798, #800)
* Mejoras significativas y actualizaciones a la documentación del usuario, incluyendo documentación de las órdenes de teclado laptop y sincronización de la Referencia Rápida de Órdenes de Teclado con la Guía del Usuario. (#455)
* Actualizado el transcriptor braille liblouis a la versión 2.1.0. Notablemente, esto corrige algunos problemas relacionados con el Braille Chino

### Corrección de Fallos

* En µTorrent, el elemento enfocado en la lista de torrents ya no informa repetidamente o escamotea el foco cuando se abre un menú.
* En µTorrent, los nombres de los ficheros en la lista de contenidos de Torrent ahora se anuncian.
* En aplicaciones de Mozilla, ahora el foco se detecta correctamente cuando aterriza en una tabla vacía o árbol.
* En aplicaciones de Mozilla, "no verificado" ahora se informa correctamente para controles marcables tales como celdas de tabla marcables. (#571)
* En aplicaciones de Mozilla, el texto de diálogos aria correctamente implementados ya no se ignora y ahora se informará cuando el diálogo aparezca.
* en Internet Explorer y otros controles MSHTML, el atributo nivel de ARIA ahora se cumple correctamente.
* En Internet Explorer y otros controles MSHTML, el rol ARIA ahora se elige sobre otro tipo de información para dar una experiencia de ARIA mucho más correcta y predecible.
* Detenido un raro cuelgue en Internet Explorer cuando se navega por marcos o iFrames.
* En documentos de Microsoft Word, las líneas de derecha a izquierda (tales como en el texto árabe) pueden leerse de nuevo. (#627)
* Fuerte reducción de retraso cuando grandes cantidades de texto se mostraban en una consola de órdenes de Windows en sistemas de 64 bits. (#622)
* Si Skype ya está arrancado  cuando arranque NVDA, ya no es necesario reiniciar Skype para habilitar la accesibilidad. Esto también puede ser cierto para otras aplicaciones que comprueben la bandera del sistema para el lector de pantalla.
* En aplicaciones de Microsoft Office, NVDA ya no se bloquea cuando se presionó verbalizar primer plano (NVDA+b) o cuando se navegan algunos objetos en barras de herramientas. (#616)
* Corregida la verbalización incorrecta de números que contienen un 0 después de un separador; ej.: 1.023. (#593)
* Adobe Acrobat Pro y Reader 9 ya no se bloquean cuando se cierra un fichero o se llevan a cabo otras ciertas tareas. (#613)
* La selección se anuncia ahora cuando se presiona control+a para seleccionar todo el texto en algunos controles de texto editables tales como en Microsoft Word. (#761)
* En los controles de Scintilla (ej.: Notepad++), el texto ya no se selecciona incorrectamente cuando NVDA mueve el cursor del sistema tal como durante leer todo. (#746)
* Es posible de nuevo revisar el contenido de celdas en MS Excel con el cursor de revisión.
* NVDA puede leer de nuevo por líneas en ciertos campos de área de texto problemáticos en Internet Explorer 8. (#467)
* Windows Live Messenger 2009 ya no se cierra inmediatamente después de iniciarse mientras NVDA se ejecuta. (#677)
* En los navegadores web, ya no es necesario presionar tab para interactuar con un objeto empotrado (tal como contenido Flash) después de presionar intro en el objeto empotrado o volviendo desde otra aplicación. (#775)
* En controles de Scintilla (ej.: Notepad++), el comienzo de líneas largas ya no se corta cuando sobrepasan la pantalla. También, estas líneas largas se mostrarán correctamente en braille cuando se seleccionen.
* En Loudtalks, ahora es posible acceder a la lista de contactos.
* La URL del documento y "MSAAHTML Registered Handler" ya no se anuncia a veces falso en Internet Explorer y otros controles MSHTML. (#811)
* En árboles en en el IDE de Eclipse,  el elemento enfocado anteriormente ya no se anuncia incorrectamente cuando el foco se mueve a un nuevo elemento.
* NVDA ahora funciona correctamente en un sistema donde el actual directorio de trabajo se haya eliminado de la ruta de búsqueda de las DLL (configurando la entrada de registro CWDIllegalInDllSearch a 0xFFFFFFFF). Ten en cuenta que esto no es relevante para la mayoría de los usuarios. (#907)
* Cuando las órdenes de navegación de tablas se utilicen fuera de una en Microsoft Word, "borde de tabla" ya no hablan después de "no en tabla". (#921)
* Cuando las órdenes de navegación de tabla no puedan mover debido a estar en el borde de una tabla en Microsoft Word, "borde de tabla" ahora habla en el idioma configurado d NVDA en lugar de siempre en inglés. (#921)
* En Outlook Express, Windows Mail y Windows Live Mail, el estado de las casillas de verificación en listas de reglas de mensajes ahora se anuncia. (#576)
* La descripción de las reglas de mensajes ahora puede leerse en Windows Live Mail 2010.

## 2010.1

Esta revisión se enfoca principalmente en corrección de fallos y mejoras a la experiencia del usuario, incluyendo algunas correcciones significativas de estabilidad.

### Nuevas características

* NVDA ya no falla al arrancar en un sistema sin dispositivos de salida de audio. Obviamente, será necesario utilizar una pantalla braille o el Display synthesiser para la salida en este caso. (#425)
* Ha sido añadida una casilla de verificación Anunciar regiones al diálogo de Opciones de formato de Documento que te permite configurar si NVDA debería anunciar regiones en documentos web. Para compatibilidad con la versión anterior, la opción está activada de forma predeterminada.
* Si verbalizar teclas de órdenes está activada NVDA ahora anunciará los nombres de las teclas multimedia (ex.: reproducir, detener, página de inicio, etc.) cuando sean presionadas. (#472)
* NVDA ahora anuncia la palabra que esté siendo eliminada cuando se presiona control+retroceso en controles que lo soporten. (#491)
* Las flechas de cursor ahora pueden ser utilizadas en la ventana del formateador Web para navegar y leer el texto. (#452)
* La lista de entradas en la libreta de direcciones de Microsoft Office Outlook ahora está soportada.
* Mejor soporte de documentos empotrados editables de NVDA (modo de diseño) en Internet Explorer. (#402)
* un script nuevo (nvda+shift+menos del teclado numérico) te permite mover el foco del sistema al navegador de objetos actual.
* Nuevos scripts para bloquear y desbloquear los botones izquierdo y derecho del ratón. Útil para llevar a cabo operaciones de arrastrar y soltar. shift+dividir del teclado numérico para bloquear/desbloquear el izquierdo, shift+multiplicar del teclado numérico para bloquear/desbloquear el derecho.
* Nuevas tablas de transcripción braille: braille computerizado alemán de 8 puntos, Alemán grado 2, braille computerizado Finlandés de 8 puntos, Chino (Hong Kong, Cantonés), Chino (Taiwan, Mandarín). (#344, #369, #415, #450)
* Ahora es posible desactivar la creación del atajo del escritorio (y así la tecla de atajo) cuando se instala NVDA. (#518)
* NVDA ahora puede utilizar IAccessible2 cuando se presenta en aplicaciones de 64 bit. (#479)
* Mejorado el soporte para regiones vivas en aplicaciones de Mozilla. (#246)
* La API NVDA Controller Client ahora se proporciona para permitir a las aplicaciones controlar a NVDA; ej.: para verbalizar texto, silenciar la voz, mostrar un mensaje en Braille, etc.
* Los mensajes de información y error ahora se leen en la pantalla del logon en Windows Vista y Windows 7. (#506)
* En Adobe Reader, los formularios PDF interactivos desarrollados con Adobe LiveCycle ahora son soportados. (#475)
* En Miranda IM, NVDA ahora lee automáticamente los mensajes de entrada en ventanas de chat si el anunciado de cambios de contenido dinámico se activó. También, han sido añadidas las órdenes para anunciar los tres mensajes más recientes (NVDA+control+número). (#546)
* Ahora se soportan campos de entrada de texto en contenido de Adobe Flash. (#461)

### Cambios

* El mensaje de ayuda de teclado extremadamente verboso en el menú de Inicio de Windows 7 ya no se anuncia.
* El sintetizador Display ahora ha sido reemplazado con un nuevo Visualizador de Habla. Para activarlo, elige Visor de Habla desde el menú Herramientas. El Visualizador de Habla puede ser utilizado independientemente de con qué otro sintetizador de voz estés trabajando.
* Los mensajes en la pantalla braille serán rechazados automáticamente si el usuario presiona una tecla que signifique un cambio tal como el movimiento del foco. Anteriormente el mensaje siempre permanecería según su tiempo configurado.
* La Opción para ajustar el braille al foco o al cursor de revisión (NVDA+control+t) ahora puede ser también configurada desde el diálogo de opciones braille, y ahora también se guarda en la configuración del usuario.
* Actualizado el sintetizador de voz eSpeak a 1.42.04.
* Actualizado el transcriptor braille liblouis a 1.8.0.
* En los modos virtuales, el anunciado de elementos cuando se mueve por caracteres o palabras ha sido muy mejorado. Anteriormente, era anunciada una gran cantidad de información irrelevante y el anunciado era muy diferente a eso cuando se mueve por líneas. (#490)
* La tecla Control ahora simplemente detiene la voz como otras teclas, en lugar de pausar la voz. Para pausar/reanudar la voz, utiliza la tecla shift.
* Ya no se anuncia la cuenta de filas y columnas de tabla cuando se anuncian los cambios del foco, puesto que este anunciado es demasiado verboso y normalmente no es útil.

### Corrección de Fallos

* NVDA ya no falla al arrancar si el soporte UI Automation parece estár disponible pero falla al inicializarse por alguna razón. (#483)
* Todo el contenido de una fila de una tabla ya no es anunciado a veces cuando se mueve el foco entre celdas en aplicaciones de Mozilla. (#482)
* NVDA ya no se retrasa durante un tiempo largo cuando se expanden elementos de la vista en árbol que contengan una cantidad muy grande de sub-elementos.
* Cuando se listan voces SAPI 5, NVDA ahora intenta detectar voces defectuosas y excluirlas del diálogo de Opciones de Voz y del grupo de Opciones de Sintetizador. Anteriormente, cuando había una voz problemática, el controlador SAPI 5 de NVDA fallaba algunas veces al iniciarse.
* Los modos virtuales ahora anuncian las teclas de atajo del objeto opción que se encuentra en el diálogo Presentación de Objetos. (#486)
* En los modos virtuales, las coordenadas de fila/columna ya no se leen incorrectamente por encabezados de fila y columna cuando el anunciado de tablas está desactivado.
* En los modos virtuales, las coordenadas de fila/columna ahora son correctamente leídas cuando abandonas una tabla y luego vuelves a entrar en la misma celda de la tabla sin visitar otra celda primero; ej.: presionando flecha arriba y luego flecha abajo sobre la primera celda de una tabla. (#378)
* Las líneas en blanco en documentos de Microsoft Word y de controles de edición de Microsoft HTML ahora son mostradas apropiadamente en pantallas braille. Anteriormente NVDA mostraba la frase actual en la línea, no la línea actual para estas situaciones. (#420)
* Múltiples correcciones de seguridad cuando se ejecuta NVDA en el Logon de Windows y en otros Escritorios Seguros.
* La posición del cursor (cursor del sistema) ahora se actualiza correctamente cuando se lleva a cabo una Lectura Completa que se pase del final de la pantalla, en campos de edición estándar de Windows y documentos de Microsoft Word. (#418)
* En los modos virtuales, el texto ya no es incluído incorrectamente por imágenes dentro de enlaces y cliqueables que son marcados como irrelevantes para los lectores de pantalla. (#423)
* Correcciones para la distribución de teclado laptop. (#517)
* Cuando el braille está siguiendo a la revisión cuando enfocas en una ventana de consola del dos, el cursor de revisión ahora puede navegar apropiadamente por el texto en la consola.
* Mientras se trabaja con TeamTalk3 o TeamTalk4 Classic VU la barra de progreso contador en la ventana principal ya no se anuncia según se actualiza. También los caracteres especiales pueden leerse apropiadamente en la ventana de entrada de chat.
* Los elementos ya no son verbalizados dos veces en el menú de inicio de Windows 7. (#474)
* Activando enlaces a la misma página en Firefox 3.6 appropriately se mueve el cursor apropiadamente en el modo virtual al lugar correcto en la página.
* Corregido el problema donde algún texto no era proporcionado en Adobe Reader en ciertos documentos PDF.
* NVDA ya no verbaliza incorrectamente ciertos números separados por un guión; ej.: 500-1000. (#547)
* En Windows XP, NVDA ya no causa que Internet Explorer se cuelgue cuando se conmutan casillas de verificación en Windows Update. (#477)
* Cuando se utiliza en el sintetizador eSpeak incorporado, simultáneamente voz y pitidos ya no causa cuelgues intermitentes en algunos sistemas. Esto era más evidente, por ejemplo, cuando se copian cantidades grandes de datos en Windows Explorer.
* NVDA ya no anuncia que un documento de Firefox se ha llenado (ej.: debido a una actualización o refresco) cuando ese documento está en segundo plano. Esto también causaba que la barra de estado de la aplicación en primer plano sea anunciada falsamente.
* Cuando se cambian distribuciones de teclado de Windows (con control+shift o alt+shift), el nombre completo de la distribución se anuncia en voz y braille. Anteriormente sólo se anunciaba en voz, y distribuciones alternativas (ej.: Dvorak) no se anunciaban.
* Si el anunciado de tablas se desactivó, la información de tabla ya no se anuncia cuando el foco ccambie.
* Ciertos controles estándar de vista en árbol en aplicaciones de 64 bit (ej.: la vista en árbol de contenidos en Microsoft HTML Help) ahora son accesibles. (#473)
* Corregidos algunos problemas con mensajes de registro que contienen caracteres no ASCII. Esto podía provocar errores expúreos en algunos casos en sistemas que no estén en inglés. (#581)
* La información en el diálogo Acerca de en NVDA ahora aparece en el idioma configurado del usuario en lugar de aparecer siempre en inglés. (#586)
* Ya no se encuentran problemas al utilizar el anillo de opciones del sintetizador después de que la voz se cambie a una que tenga menos opciones que la voz anterior.
* En Skype 4.2, los nombres de contacto ya no se verbalizan dos veces en la lista de contactos.
* Corregidas algunas fugas de memoria potencialmente importantes en la interfaz gráfica de usuario y en los búferes virtuales. (#590, #591)
* Solucionado un eror desagradable en algunos sintetizadores SAPI 4 que estaba causando frecuentes fallos y bloqueos NVDA. (#597)

## 2009.1

Lo más resaltable de esta versión incluye el soporte para ediciones de 64 bit de Windows; soporte muy mejorado para los documentos de Microsoft Internet Explorer y de Adobe Reader; soporte para Windows 7; la lectura de las pantallas de  logon de Windows, control+alt+supr y el control de cuentas de usuario (UAC); y la capacidad para interactuar con contenidos de Adobe Flash y de Sun Java en páginas web. También hemos tenido varias correcciones significativas de estabilidad y mejoras a la experiencia de usuario general.

### Nuevas Características

* ¡Soporte oficial para ediciones de 64 bit de Windows! (#309)
* Añadido un controlador de sintetizador para el sintetizador Newfon. Nota que esto requiere una versión especial de Newfon. (#206)
* En los modos virtuales, el modo foco y el modo revisión ahora pueden anunciarse utilizando sonidos en lugar de la voz. Esto está activado predeterminadamente. Puede configurarse desde el diálogo de Modo Virtual. (#244)
* NVDA ya no cancela la voz cuando las teclas de control del volumen se presionan en el teclado, permitiendo al usuario cambiar el volumen y escuchar los resultados actuales inmediatamente. (#287)
* Reescrito Completamente el soporte para documentos de Microsoft Internet Explorer y Adobe Acrobat. Este soporte ha sido unificado con el soporte interno utilizado por Mozilla Gecko, así características tales como la interpretación más rápida de página, navegación extensa y rápida, lista de enlaces, selección de texto, modo foco automático y soporte de braille están ahora disponibles con estos documentos.
* Mejorado el soporte para el control de selección de fecha encontrado en el diálogo  de propiedades de Fecha / Hora en Windows Vista.
* mejorado el soporte para el menú de inicio Moderno XP/Vista (específicamente los menús Todos los programas y lugares). La información de nivel se anuncia ahora apropiadamente.
* La cantidad de texto que se anuncia con el movimiento del ratón, es ahora configurable desde el diálogo Opciones del Ratón. Puede hacerse una elección de párrafo, línea, palabra o caracter.
* se anuncian errores de ortografía bajo el cursor en Microsoft Word.
* soporte para la corrección ortográfica en Microsoft Word 2007. Soporte Parcial podría estar disponible para versiones anteriores de Microsoft Word.
* Soporte para Windows Live Mail (específicamente ahora los mensajes de texto plano pueden leerse).
* En Windows Vista, si el usuario se mueve al escritorio seguro (o porque un diálogo de control del UAC aparece, o porque fue presionado control+alt+supr), NVDA anunciará el hecho de que el usuario ahora está en el escritorio seguro.
* NVDA puede anunciar texto bajo el ratón dentro de ventanas de la consola del dos.
* Soporte para UI Automation a través de la API cliente UI Automation disponible en Windows 7, tanto como se mejora la experiencia de NVDA en Windows 7.
* NVDA puede configurarse para iniciarse automáticamente después de que te identifiques en Windows. la opción está en el diálogo Opciones Generales.
* NVDA puede leer pantallas seguras de Windows tales como la autentificación de Windows (logon), control+alt+suprimir y pantallas del UAC en Windows XP y posteriores. La lectura de las pantallas de autentificación de Windows (logon) puede ser configurada desde el diálogo de Opciones Generales. (#97)
* Añadido un controlador para las pantallas braille de la serie Optelec ALVA BC6.
* Cuando se navega por documentos web, ahora puedes presionar n y shift+n para saltar adelante y atrás pasando bloques de enlaces, respectivamente.
* Cuando se navega por documentos web, los marcadores de ARIA ahora se anuncian, y puedes moverte adelante y atrás a través de ellos utilizando d y shift+d, respectivamente. (#192)
* El diálogo de lista de enlaces disponible cuando se exploran documentos web se ha convertido ahora en un diálogo Lista de Elementos el cual puede listar enlaces, encabezados y marcadores. Los encabezados y marcadores se presentan jerárquicamente. (#363)
* El nuevo diálogo Lista de Elementos filtra la lista según escribas para contener sólo aquéllos elementos incluído el texto que fue tecleado. Puedes presionar retroceso para limpiar el filtro tal que todos los elementos se presenten nuevamente. (#173)
* Las versiones portátiles de NVDA ahora buscan en el directorio 'userConfig' dentro del directorio de NVDA, las configuraciones del usuario. Como la versión del instalador, esto mantiene la configuración del usuario separada de NVDA.
* Los módulos personales de apps, los controladores de pantallas braille y los controladores de sintetizadores ahora pueden ser almacenados en el directorio de la configuración del usuario. (#337)
* Los modos virtuales ahora son interpretados en segundo plano, permitiendo al usuario interactuar con el sistema hasta cierto punto durante el proceso de interpretado. El usuario será notificado de que el documento está siendo interpretado si le ocupará más de un segundo.
* Si NVDA detecta que se ha colgado por alguna razón, Pasará automáticamente por todas las pulsaciones para que el usuario tenga una mejor posibilidad de recuperación del sistema.
* Soporte para arrastrar y soltar en ARIA en Mozilla Gecko. (#239)
* La selección de título de documento y línea actual ahora se verbaliza cuando muevas el foco dentro de un modo virtual. Esto hace que el comportamiento cuando se mueve el foco en los modos virtuales sea consistente como en un documento normal. (#210)
* En los modos virtuales, ahora puedes interactuar con objetos empotrados (tales como contenidos Adobe Flash y Sun Java) presionando intro sobre el objeto. Si es accesible, puedes entonces tabular por él como cualquier otra aplicación. Para regresar el foco al documento, presiona NVDA+espacio. (#431)
* En los modos virtuales, o y shift+o mueven al siguiente y al anterior objeto empotrado, respectivamente.
* NVDA ahora puede acceder completamente a aplicaciones que se ejecuten como administrador en Windows Vista y posterior. Debes instalar una versión oficial de NVDA para que esto funcione. Esto no funciona para versiones portables y snapshots. (#397)

### Cambios

* NVDA ya no anuncia "NVDA activado" cuando arranca.
* Los sonidos de arranque y finalización ahora se reproducen utilizando el dispositivo de salida de audio configurado en NVDA en lugar del dispositivo de audio predeterminado de Windows. (#164)
* El anunciado de las barras de progreso ha sido mejorado. Lo más notable es que ahora puedes configurar a NVDA para anunciarlas a través de voz y pitidos al mismo tiempo.
* Algunos roles genéricos, tales como panel, aplicación y marco, ya no se anuncian en el foco a menos que el control no tenga nombre.
* La orden de copia de revisión (NVDA+f10) copia el texto desde encima de la marca de comienzo e incluye la posición actual de revisión, en lugar de excluir la posición actual. Esto permite que el último caracter de una línea sea copiado, lo cual no era posible anteriormente. (#430)
* el script  navigatorObject_where (ctrl+NVDA+numpad5) ha sido eliminado. Esta combinación de teclas no funcionaba en algunos teclados, ni el script era útil.
* el script navigatorObject_currentDimentions ha sido remapeado a NVDA+supr del teclado numérico. La antigua combinación de teclas no funcionaba en algunos teclados. Este script ahora también anuncia la anchura y la altura del objeto en lugar de las coordenadas derecha/inferior.
* Mejorado el rendimiento (especialmente en netbooks) cuando ocurren muchos pitidos en sucesión rápida; ej.: movimientos rápidos con el ratón con las coordenadas de audio activadas. (#396)
* Los sonidos de error de NVDA ya no se reproducen en versiones candidatas y finales. Ten een cuentan que los errores todavía se registran.

### Corrección de Fallos

* Cuando NVDA está ejecutándose desde una ruta de DOS 8.3, pero está instalado en la ruta larga relacionada (ej.: progra~1 versus program files) NVDA identificará correctamente que es una copia instalada y carga apropiadamente las opciones de usuario.
* la verbalización del título de la ventana actual en primer plano con nvda+t funciona ahora correctamente cuando se está en los menús.
* el braille ya no muestra información innecesaria en su contexto de foco tal como paneles no etiquetados.
* se detiene el anunciado de alguna información innecesaria cuando el foco cambia tal como paneles raíz, paneles solapados y paneles deslizables en aplicaciones Java o Lotus.
* Se hace que el campo de búsqueda de palabras clave en el visualizador de Ayuda de Windows (CHM) sea mucho más usable. Debido a la cantidad de fallos en ese control, la palabra clave actual no podría ser leída ya que estaría continuamente cambiando.
* se anuncian los números correctos de página en Microsoft Word si la numeración de página ha sido específicamente configurada en el documento.
* Mejor soporte para campos de edición encontrados en diálogos de Microsoft Word (ej.: el diálogo Fuentes). Ahora es posible navegar estos controles con las flechas.
* mejor soporte para consolas del Dos. específicamente: NVDA ahora puede leer el contenido de consolas particulares que Siempre se pensó que estaban en blanco. Presionando control+break ya no apagan a NVDA.
* En Windows Vista, el instalador de NVDA ahora arranca a NVDA con privilegios de un usuario normal cuando se requiera para ejecutar a NVDA en la pantalla final.
* El Retroceso ahora es manejado correctamente cuando se verbalizan palabras al escribir. (#306)
* No se anuncia incorrectamente "Menú inicio" para ciertos menús de contexto en Windows Explorer/Windows shell. (#257)
* NVDA ahora maneja correctamente etiquetas de ARIA en Mozilla Gecko cuando no hay otro contenido útil. (#156)
* NVDA ya no activa incorrectamente el modo foco automáticamente para campos de texto editable que actualizan su valor cuando el foco cambia; ej.: https://tigerdirect.com/. (#220)
* NVDA ahora intentará recuperarse de algunas situaciones que anteriormente causarían que secolgase completamente. Podrá tomar sobre 10 segundos para que NVDA detecte y se recupere de tales cuelgues.
* Cuando el idioma de NVDA está ajustado a "User default", utiliza el idioma del usuario de Windows configurado en lugar del local de windows.
* NVDA ahora reconoce la existencia de controles en AIM 7.
* La orden de dejar pasar la tecla ya no se queda atascada si una tecla se mantiene presionada. Anteriormente, NVDA detenía el aceptado de órdenes si esto ocurría y tenía que ser reiniciado. (#413)
* La barra de tareas ya no se ignora cuando recibe el foco, lo que amenudo ocurre cuando se sale de una aplicación. Anteriormente, NVDA se comportaba como si el foco no huviera cambiado.
* Cuando se leen campos de texto en aplicaciones que utilizan el Java Access Bridge (incluyendo OpenOffice.org), NVDA ahora funciona correctamente cuando el anunciado de números de línea está activado.
* La orden de copia en revisión (NVDA+f10) maneja elegantemente el caso donde sea utilizado en una posición antes del marcador de inicio. Anteriormente, esto podía causar problemas tales como cuelgues en Notepad++.
* Cierto caracter de control (0x1) ya no causa una extraña conducta en eSpeak (tal como cambios en el volumen tono) cuando se la encuentra en un texto. (#437)
* La orden anunciar selección de texto (NVDA+shift+flecha arriba) ahora informa con elegancia de que no hay selección en objetos que no soporten selección de texto.
* Corregido el fallo donde al pulsar la tecla intro en ciertos botones o enlaces de Miranda-IM causaba que NVDA se congelase. (#440)
* La línea actual o selección ahora se respeta correctamente al deletrear o copiar el navegador de objetos actual.
* Se ha solucionado un error de Windows que provocaba que se dijera basura después del nombre de los controles de enlace en los diálogos de Windows Explorer e Internet Explorer. (#451)
* Corregido un problema con el anunciado de la orden de hora y la fecha (NVDA+f12). anteriormente, anuncciado de fecha fue truncado en algunos sistemas. (#471)
* Corregido el problema donde el indicador del lector de pantalla del sistema a veces se borraba de forma inadecuada después de interactuar con pantallas seguras de Windows. Esto podía causar problemas en aplicaciones que comprueban el indicador del lector de pantalla como Skype, Adobe Reader y Jart. (#462)
* En un cuadro combinado de Internet Explorer 6, el elemento activo ahora se anuncia cuando cambia. (#342)

## 0.6p3

### Nuevas Características

* Como la barra de fórmulas de Microsoft Excel es inaccesible para NVDA, se proporciona un cuadro de diálogo específico de NVDA para editar cuando el usuario presione f2 sobre una celda.
* Soporte para formato en controles de texto de IAccessible2, incluyendo aplicaciones de Mozilla.
* Deletrear errores puede ser anunciado ahora donde sea posible. Esto es configurable desde el diálogo de preferencias Formato de Documentos.
* NVDA puede configurarse para pitar para todas o sólo para las barras de progreso visibles. Alternativamente, puede configurarse para verbalizar los valores de las barras de progreso cada 10%.
* Los enlaces pueden ahora identificarse en controles de edición multilínea.
* El ratón puede ahora moverse al caracter bajo el cursor de revisión en la mayoría de los controles de texto editables. Previamente, el ratón sólo podía ser movido al centro del control.
* En los modos virtuales, el cursor de revisión ahora revisa el texto del modo, antes que sólo el texto interno del navegador de objetos (lo cual amenudo no es útil para el usuario). Esto significa que puedes navegar el modo virtual jerárquicamente utilizando navegación de objetos y el cursor de revisión moverá a ese punto en el modo.
* Manejo de algunos estados adicionales en controles de Java.
* Si la orden de título (NVDA+t) se presiona dos veces rápidamente, deletrea el título. Si se presionó tres veces, se copia al portapapeles.
* La ayuda de teclado ahora lee los nombres de las teclas modificadoras cuando se presionaron solas.
* Los nombres de tecla anunciados por la ayuda de teclado están ahora traducidos.
* Añadido soporte para el texto reconocido en campos de SiRecognizer. (#198)
* ¡Soporte para pantallas braille!
* Añadida una orden (NVDA+c) para anunciar el texto en el portapapeles de Windows. (#193)
* Ahora puedes presionar escape cuando estás en modo foco para regresar a modo revisión.
* En los modos virtuales, cuando el foco cambia o el cursor se mueve, NVDA puede cambiar automáticamente amodo foco o modo revisión según proceda para el control bajo el cursor. Esto se configura desde el diálogo de Modo virtual. (#157)
* Reescrito el controlador de sintetizador SAPI4 el cual reemplaza a los controladores sapi4serotek y sapi4activeVoice y debería solucionar los problemas encontrados con estos controladores.
* La aplicación NVDA ahora incluye un manifiesto, lo cual significa que no se ejecutará más en modo de compatibilidad en Windows Vista.
* El fichero de configuración y los diccionarios del habla se guardan ahora en el directorio de datos del usuario si NVDA fue instalado utilizando el instalador. Esto es necesario para Windows Vista y también permite a múltiples usuarios tener configuraciones individuales para NVDA.
* Añadido soporte para información de posición para controles IAccessible2.
* Añadida la capacidad para copiar texto al portapapeles utilizando el cursor de revisión. NVDA+f9 ajusta la marca de inicio en la posición actual del cursor de revisión. NVDA+f10 recupera el texto entre la marca de inicio y la posición actual del cursor de revisión y lo copia al portapapeles. (#240)
* Añadido soporte para algunos controles de edición en el programa pinacle tv.
* Cuando se anuncian texto seleccionado para selecciones largas (512 caracteres o más), NVDA vervaliza ahora el número de caracteres seleccionados, en lugar de verbalizar toda la selección. (#249)

### Cambios

* Si el dispositivo de salida de audio se ajusta para utilizar el dispositivo predeterminado de Windows (Microsoft Sound Mapper), NVDA cambiará ahora al nuevo dispositivo predeterminado para eSpeak y tonos cuando el dispositivo predeterminado cambie. Por ejemplo, NVDA cambiará a un dispositivo de audio USB si se hace dispositivo predeterminado automáticamente cuando se conecte.
* Se mejora el rendimiento de eSpeak con algunos controladores de audio en Windows Vista.
* leer por frase en controles de texto enriquecido si es posible.
* El anunciado de enlaces, encabezados, listas y citas en documentos se configura ahora en el diálogo de 	* La velocidad es ahora la opción predeterminada en el grupo de las opciones de voz del sintetizador.
* Se mejora la carga y descarga de los appModules.
* La orden de título (NVDA+t) ahora sólo informa del título en lugar de todo el objeto. Si el objeto en primer plano no tiene nombre, se utiliza el nombre de proceso de la aplicación.
* En lugar de activar y desactivar el paso a través del modo virtual, NVDA ahora anuncia modo foco (paso por modo virtual activado) y modo revisión (paso por modo virtual desactivado).
* Las voces ahora se guardan en el fichero de configuración por ID en lugar de por index. Esto hace las opciones de voz más seguras a través de los cambios de los sistemas y las configuraciones. La opción de voz no se preservará en todas las configuraciones y un error podrá mostrarse en el registro la primera vez que un sintetizador sea utilizado. (#19)
* El nivel de un elemento de vista de árbol ahora es anunciado primero si ha cambiado desde el elemento enfocado anteriormente para todas las vistas en árbol. Anteriormente, esto sólo ocurría para vistas en árbol nativas de Windows (SysTreeView32).

### Corrección de Fallos

* El último trozo de audio no se corta ya cuando se utilice NVDA con eSpeak en un servidor de escritorio remoto.
* Se corrigen problemas con el guardado de diccionarios de voz para ciertas voces.
* Eliminación de retraso cuando se mueva por otras unidades que no sean caracter (palabra, línea, etc.) hacia el final de los documentos de texto plano largos en los modos virtuales de Mozilla Gecko. (#155)
* Si verbalizar palabras al escribir está habilitado, anuncia la palabra cuando se presione intro.
* Corregidos algunos grupos de sucesiones de caracteres en documentos enriquecidos. preferencias de Formato de Documentos. Esto incluye modos virtuales de Mozilla Gecko.
* El visualizador de registro de NVDA ahora utiliza cuadros multilínea en lugar de sólo editar para mostrar el registro. Esto mejora la lectura por palabras con NVDA y te permite leer el texto del registro más allá de los 65535 bytes.
* Corregidos algunos fallos relacionados con objetos empotrados en controles de edición multilínea.
* NVDA ahora lee los números de página en Microsoft Word. (#120)
* Se corrige el fallo cuando tabulando a una casilla de verificación verificada en un modo virtual de Mozilla Gecko y presionando espacio no anunciaba que la casilla de verificación estaba siendo desverificada.
* Informa correctamente las casillas de verificación parcialmente verificadas en aplicaciones Mozilla.
* Si la selección de texto se expande o se contrae en ambas direcciónes, lee la selección como un trozo en lugar de dos.
* Cuando se lee con el ratón, el texto en los campos de edición de Mozilla Gecko debería leerse ahora.
* Leer todo no debería causar que ciertos sintetizadores SAPI5 se cuelguen.
* Corregido un fallo el cual significaba que cambios en la selección de texto no estuviesen siendo leídos en controles estándares de edición de Windows antes del primer cambio del foco después que NVDA se iniciase.
* Corregido el seguimiento del ratón en objetos Java. (#185)
* NVDA ya no anuncia los elementos de los árboles Java sin hijos como si estuviesen contraídos.
* Anuncia el objeto con el foco cuando una ventana Java es traída a primer plano. Anteriormente, sólo se anunciaba el objeto de nivel superior Java.
* El controlador del sintetizador eSpeak no se detiene ya completamente mientras habla después de un simple error.
* Se corrige el fallo mediante el cual actualizar parámetros de voz (velocidad, tono, etc.) no se guardó cuando la voz fue cambiada desde el grupo de las opciones de sintetizador.
* Mejorada la verbalización de caracteres y palabras escritos.
* Algún texto nuevo que anteriormente no era verbalizado en aplicaciones de la consola de texto (tales como algún texto de juegos conversacionales) es ahora verbalizado.
* NVDA ahora ignora cambios del foco en ventanas en segundo plano. Anteriormente, un cambio del foco en segundo plano podía ser tratado como si el foco real cambiase.
* Mejorada la detección del foco cuando se abandonan los menús de contexto. Anteriormente, NVDA amenudo no reaccionaba del todo cuando se abandonaba un menú de contexto.
* NVDA ahora anuncia cuando el menú de contexto es activado en el menú de Inicio.
* El menú de Inicio clásico ahora es anunciado como Menú de Inicio en lugar de Menú Aplicación.
* Mejorada la lectura de alertas tales como aquéllas encontradas en Mozilla Firefox. El texto no debería ser leído ya múltiples veces y otra información extraña no será ya leída. (#248)
* El texto enfocable, campos de edición de solo lectura no serán ya incluídos cuando se recoja el texto de diálogos. Esto corrige, por ejemplo, la lectura automática de toda la aceptación de la licencia en los instaladores.
* NVDA ya no anuncia la deselección de texto cuando se abandonen algunos controles de edición (ejemplo: barra de dirección en Internet Explorer, campos de dirección en correo electrónico en Thunderbird 3 ).
* Cuando se abran correos en texto plano  en Outlook Express y Windows Mail, el foco está correctamente colocado en el mensaje listo para que el usuario lo lea. Anteriormente el usuario tenía que presionar tab o hacer clic sobre el mensaje en orden a utilizar las teclas del cursor para leerlo.
* Corregidos varios problemas mayores con la funcionalidad "Vervalizar Teclas de Órdenes".
* NVDA ahora puede leer texto que pase de 65535 caracteres en controles estándar de edición (ej.: un fichero grande en Notepad).
* Mejorada la lectura de líneas en campos de edición de MSHTML (mensajes editables de Outlook Express y campos de entrada de texto en Internet Explorer).
* NVDA ya no se cuelga a veces completamente cuando se edita texto en OpenOffice. (#148, #180)

## 0.6p2

* Mejorada la voz predeterminada de ESpeak en NVDA
* Añadida una disposición de teclado para ordenadores portátiles. Las disposiciones de teclado pueden ser configuradas desde el diálogo de Opciones de teclado de NVDA. (#60)
* Soporte para grupos de elementos en controles SysListView32, encontrados principalmente en Windows Vista. (#27)
* Informar del estado verificado de elementos de vista en árbol en controles SysTreeview32.
* Añadidas teclas de atajo para muchos de los diálogos de configuración de NVDA
* Soporte para IAccessible2 habilitado para aplicaciones tales como Mozilla Firefox cuando se ejecuta a NVDA desde un medio portátil, sin tener que registrar ningún fichero Dll en especial
* Corregido un cuelgue con la lista de enlaces del modo virtual en aplicaciones Gecko. (#48)
* NVDA no debería colgarse ya con aplicaciones Mozilla Gecko tales como Firefox y Thunderbird si NVDA está ejecutándose con privilegios más altos que los de la aplicación Mozilla Gecko. Ej. NVDA está ejecutándose como Administrador.
* Diccionarios del habla (anteriormente diccionarios de usuario) ahora pueden ser o sensibles a las mayúsculas o insensibles, y los patrones pueden ser opcionalmente expresiones regulares. (#39)
* Si o no NVDA utiliza un 'modo de disposición de pantalla' para los documentos del modo virtual puede ahora ser configurado desde un diálogo de opciones
* No se informa más sobre anclaje de etiquetas sin href en documentos Gecko como enlaces. (#47)
* La orden buscar de NVDA ahora recuerda qué es lo último que se buscó, a través de todas las aplicaciones. (#53)
* Corregidos problemas donde el estado verificado no era anunciado en algunas casillas de verificación y botones de opción en los modos virtuales
* El modo de paso a través del modo virtual es específico ahora para cada documento, en lugar de globalmente para NVDA. (#33)
* Corregidos alguna lentitud con los cambios del foco e interrupción incorrecta de la voz que algunas veces ocurría cuando se utiliza NVDA en un sistema que había estado en sobre aviso o estaba más bien lento
* Mejora el soporte para cuadros combinados en Mozilla Firefox. Específicamente cuando se navegando con las flechas por sus textos no es repetido, y cuando saltando fuera de ellos, los controles ancestros no son anunciados innecesariamente. Ahora también las órdenes del modo virtual funcionan cuando reciben el foco en uno cuando estás en un modo virtual.
* Mejora la precisión de la búsqueda de la barra de estado en muchas aplicaciones. (#8)
* Añadida la herramienta de la consola de python interactiva de NVDA, para habilitar a los desarrolladores para mirar y manipular cuestiones internas de NVDA según está ejecutándose
* los scripts DecirTodo, AnunciarSelección y anunciarLíneaActual funcionan ahora apropiadamente cuando se está en el modo pasar a través del modo virtual. (#52)
* Los scripts incrementar velocidad y decrementar velocidad han sido eliminados. Los usuarios deberían utilizar los scripts del grupo de las opciones de sintetizador (control+nvda+flechas) o el diálogo de opciones de Voz
* Se mejora el rango y la escala de los pitidos de la barra de progreso
* Añadidas más teclas rápidas al nuevo modo virtual:  l para lista, i para elemento de lista, e para campo de edición, b para botón, x para casilla de verificación, r para botón de opción, g para gráfico, q para citas, c para cuadro combinado, 1 a 6 para los respectivos niveles de encabezado, s para separador, m para marco. (#67, #102, #108)
* La cancelación de la carga de un nuevo documento en Mozilla Firefox permite ahora al usuario seguir utilizando el antiguo documento del  modo virtual si el viejo documento no ha sido realmente destruido aún. (#63)
* Navegar por palabras en los modos virtuales es ahora más exacto mientras las palabras no contengan accidentalmente texto de más de un campo. (#70)
* Mejorada la exactitud del seguimiento del foco y la actualización del foco cuando se navega en modos virtuales de Mozilla Gecko.
* Añadido un script encontrarAnterior (shift+NVDA+f3) para utilizar en el nuevo modo virtual
* Mejorada la lentitud en diálogos Mozilla Gecko (en Firefox y Thunderbird). (#66)
* Añadida la capacidad para ver el fichero registro actual para NVDA. Puede ser encontrado en el menú NVDA -> Herramientas
* Scripts tales como decir fecha y hora tienen en cuenta ahora el idioma actual; puntuación y ordenamiento de las palabras ahora reflejan el idioma
* El cuadro combinado de idioma en el diálogo de Opciones Generales de NVDA muestra ahora los nombres de idioma completo para facilidad de uso
* Cuando se revisa texto en el navegador de objetos actual, el texto está siempre actualizado si cambia dinámicamente. Ej.: revisando el texto de un elemento de lista en la Bandeja de Tareas. (#15)
* Cuando te mueves con el ratón, el párrafo actual de texto bajo el ratón ahora es anunciado, en lugar de todo el texto en ese objeto particular o sólo la palabra actual. También las coordenadas de audio, y el anunciado de los roles del objeto es opcional, son desactivados predeterminadamente
* Soporte para lectura de texto con el ratón en Microsoft Word
* Corregido un error donde al abandonar la barra de menú en aplicaciones tales como Wordpad podría causar que la selección de texto no sea anunciada nunca más
* En Winamp, el título  de la pista no es ya anunciado una y otra vez cuando se cambia de pistas, o al pausar/reanudar/detener la reproducción.
* En Winamp, añadida la capacidad de anunciar el estado de los controles Aleatorio y repetición según son activados. Funciona en la ventana principal y en el editor de listas de reproducción
* Mejorada la capacidad para activar campos particulares en los modos virtuales de Mozilla Gecko. Podrá incluir gráficos clicables, enlaces que contengan párrafos, y otras estructuras raras
* Corregido un retraso inicial cuando se abren diálogos de NVDA en algunos sistemas. (#65)
* Añadido soporte específico para la aplicación Total Commander
* Corregido un fallo en el controlador sapi4serotek donde el tono se bloqueaba en un valor particular, es decir, se quedaba alto después de leer una letra en mayúscula. (#89)
* Se anuncia texto cliqueable y otros campos como cliqueables en modos virtuales de Mozilla Gecko. ej.:  a campo que tenga un atributo onclick HTML. (#91)
* Cuando nos movemos por modos virtuales de Mozilla Gecko, se desplaza el campo actual para ver -- útil para que los pares videntes tengan una idea de dónde está el usuario en el documento (#57)
* Se añade soporte básico para ela área de regiones activas muestre eventos en aplicaciones habilitadas para IAccessible2 Útil en la aplicación de IRC Chatzilla, Los mensajes nuevos serán ahora leídos automáticamente
* Algunas mejoras pequeñas para ayudar a utilizar aplicaciones web con capacidad de ARIA,  ej.: Google Docs
* Se detiene la adición de líneas en blanco extra al texto cuando se copia desde un modo virtual
* Se detiene la tecla espacio de activar un enlace en la lista de enlaces.  Ahora puede ser utilizado como otras letras en orden a iniciar el tecleo del nombre de un enlace en particular al que desees ir
* El script moveMouseToNavigator (NVDA+barra del teclado numérico) ahora mueve el ratón al centro del navegador de objetos, en lugar  de la esquina superior izquierda
* Añadidos scripts para hacer clic en los botones izquierdo y derecho del ratón (barra y asterisco del teclado numérico respectivamente)
* Mejorado el acceso a la Bandeja del Sistema de Windows. Con esperanza de que el foco ya no debería parecer quedarse atrás en un elemento en particular. Recordatorio: para ir a la Bandeja del sistema utiliza la orden de Windows Tecla Windows+b. (#10)
* Se mejora el rendimiento y parada de anunciado de texto extra cuando se mantiene pulsado una tecla de cursor en un campo de edición y alcanza el final
* Se detiene la capacidad de NVDA para hacer que el usuario aguarde mientras mensajes en particular son hablados. Arregla algunos cuelgues con sintetizados de voz en particular. (#117)
* Añadido soporte para el sintetizador de voz Audiologic Tts3, contribución de Gianluca Casalino. (#105)
* Posiblemente mejora de rendimiento cuando se navega por los documentos en Microsoft Word
* Mejorada precisión cuando se lee texto de avisos en aplicaciones de Mozilla Gecko
* Se detienen posibles cuelgues cuando se trata de guardar la configuración en versiones no en inglés de Windows. (#114)
* Se añade un diálogo de bienvenida de NVDA. Este diálogo está diseñado para proporcionar información esencial para nuevos usuarios y permite al BloqMayus ser configurado como una tecla modificadora de NVDA. Este diálogo será mostrado cuando NVDA sea iniciado predeterminadamente hasta que se deshabilite.
* Corregido soporte básico para Adobe Reader tal que es posible leer documentos en  versiones 8 y 9
* Corregidos algunos errores que podrían haber ocurrido cuando se mantienen pulsadas teclas antes de que NVDA sea apropiadamente inicializado
* Si el usuario ha configurado NVDA para guardar la configuración al salir, se asegura de que la configuración es apropiadamente guardada cuando se apaga o se sale de Windows.
* Añadido un sonido de logo de NVDA al inicio del instalador, contribuído por Victor Tsaran
* NVDA, tanto al ejecutarse en el instalador como de otra manera, debería quitar apropiadamente su icono de la bandeja del sistema cuando salga
* Etiquetas para controles estándar en diálogos de NVDA (tales como botones Aceptar y cancelar) deberían mostrarse ahora en el idioma en que NVDA está ajustado, en lugar de sólo quedarse en Inglés.
* El icono de NVDA debería ser ahora utilizado por las teclas de atajo de NVDA en el menú de inicio y en el escritorio, en lugar de un icono de aplicación predeterminado.
* Leer celdas en MS Excel cuando te mueves con tab y shift+tab. (#146)
* Corregidas algunas verbalizaciones duplicadas en listas en particular en Skype.
* Mejorado el seguimiento del cursor en aplicaciones IAccessible2 y Java; ej.: en Open Office y Lotus Symphony, NVDA aguarda adecuadamente que el cursor se mueva en documentos en lugar de leer accidentalmente la palabra incorrecta o línea en el final de algunos párrafos. (#119)
* Soporte para controles AkelEdit encontrados en Akelpad 4.0
* NVDA ya no se bloquea en Lotus Synphony cuando te mueves desde el documento a la barra de menú.
* NVDA ya no se cuelga en los applets de programas Add/Remove en Windows XP cuando se lanza un desinstalador. (#30)
* NVDA ya no se cuelga cuando se abre Spybot Search and Destroy

## 0.6p1

### Acceso al contenido de la web con los nuevos modos virtuales en proceso (hasta aquí para aplicaciones Mozilla Gecko incluyendo Firefox3 y Thunderbird3)

* Los tiempos de carga han sido mejorados casi por un factor de trenta (ya no tienes que aguardar en toda la mayor parte de las páginas web para cargarse en el modo virtual)
* Añadida una lista de enlaces (NVDA+f7)
* Mejorado el diálogo buscar (control+nvda+f) así que lleva a cabo una búsqueda insensible a las mayúsculas, más arreglo de unos pocos problemas con el foco con ese cuadro de diálogo.
* Ahora es posible seleccionar y copiar texto en los nuevos modos virtuales
* De forma predeterminada los nuevos modos virtuales representan el documento en una disposición de pantalla (enlaces y controles no están en líneas separadas a menos que realmente sean visualmente así). Puedes conmutar esta característica con NVDA+v.
* Es posible moverse por párrafos con control+flecha arriba y control+flecha abajo.
* Mejorado el soporte para contenido dinámico
* Mejorada por encima  toda la precisión de la lectura de líneas y campos cuando se sube o se baja con las flechas.

### Internacionalización

* Ahora es posible teclear caracteres acentuados que  dependen de un "caracter justo", mientras NVDA está ejecutándose.
* NVDA anuncia ahora cuando la distribución de teclado es cambiada (cuando se presiona alt+shift).
* La característica de anunciado de fecha y hora toma ahora las opciones regional y de idioma actuales del sistema.
* añadida traducción al Checo (por Tomas Valusek con ayuda de Jaromir Vit)
* añadida traducción al vietnamita por Dang Hoai Phuc
* Añadida ttraducción al Africaans (af_ZA), por Willem van der Walt.
* Añadida traducción al ruso por Dmitry Kaslin
* Añadida traducción al polaco por DOROTA CZAJKA y amigos.
* Añadida traducción al japonés por Katsutoshi Tsuji.
* añadida tradución al tailandés por Amorn Kiattikhunrat
* añadida traducción al croata por Mario Percinic y Hrvoje Katic
* Añadida traducción al gallego por Juan C. buño
* añadida traducción al ucraniano por Aleksey Sadovoy

### Voz

* NVDA viene ahora con eSpeak 1.33 empaquetado que contiene muchas mejoras, entre las cuales están idiomas mejorados, variantes nombradas, capacidad para hablar más rápido.
* El diálogo de opciones de voz ahora te permite cambiar la variante de un sintetizador si lo soporta. La variante es normalmente una ligera variación de la voz actual. (eSpeak soporta variantes).
* Añadida la capacidad para cambiar la inflexión de una voz en el diálogo de Opciones de Voz si el sintetizador actual lo soporta. (eSpeak soporta inflexión).
* Añadida la capacidad para detener la verbalización de la información de posición del objeto (ej.:. 1 de 4). Esta opción puede ser encontrada en el diálogo de Opciones de Presentación de objetos.
* NVDA puede pitar ahora cuando verbalice una letra en mayúsculas. Esto puede ser activado y desactivado con una casilla de verificación en el diálogo de Opciones de Voz. También se añadió una casilla de verificación de elevación del tono para mayúsculas para configurar si NVDA actualmente debería tener su elevación de tono normal para las mayúsculas. Así ahora puedes tener o tono elevado, decir mayus, o pitar, para mayúsculas.
* Añadida la capacidad para pausar la voz en NVDA (como la encontrada en Voice Over para el Mac). Cuando NVDA está verbalizando algo, puedes presionar las teclas control o shift para silenciar la voz normalmente, pero si entonces pulsas la tecla shift de nuevo (tanto en cuanto no hayas presionado cualquier otra tecla) la voz continuará exactamente desde donde lo habíamos dejado.
* Añadido un controlador de sintetizador virtual el cual saca texto a una ventana en lugar de verbalizarla a través de un sintetizador de voz. Esto debería ser más agradable para los desarrolladores videntes que no son usuarios de síntesis de voz pero quieren saber qué está verbalizando NVDA. Todavía hay probablemente algunos fallos, así que la retroalimentación es más bienvenida si cabe.
* NVDA ya no verbaliza predeterminadamente la puntuación, puedes habilitar la verbalización de puntuación con NVDA+p.
* eSpeak predeterminadamente ahora habla un poco más despacio, lo cual debería hacerlo más fácil para gente que van a utilizar eSpeak por primera vez, cuando instalan o comienzan a utilizar NVDA.
* Añadidos diccionarios de usuario a NVDA. Éstos te permiten hacer que NVDA verbalice cierto texto de modo diferente. Hay tres diccionarios: predeterminado, voz, y temporal. Las entradas que añadas al diccionario predeterminado sucederán todo el tiempo en NVDA. Los diccionarios por voz son específicos al sintetizador actual y la voz que actualmente tengas ajustada. Y el diccionario temporal es para aquellas ocasiones que quieras fijar rápidamente una regla mientras vas a hacer una tarea en particular, pero no quieres que sea permanente (desaparecerá si cierras NVDA). Por ahora las reglas son expresiones regulares, no solo texto normal.
* Los sintetizadores pueden ahora utilizar cualquier dispositivo audio de salida en tu sistema, ajustando el cuadro combinado de dispositivo de salida en el diálogo Sintetizador antes de seleccionar el sintetizador que quieras.

### Rendimiento

* NVDA ya no toma una gran cantidad de memoria del sistema, cuando se editan mensajes en controles de edición mshtml
* Mejorado el rendimiento cuando se revisa texto dentro de muchos controles que no tienen actualmente un cursor real. Ej.: ventana de históricos de MSN Messenger, elementos de vistas en árbol, elementos de vista de lista etc.
* Mejorado el rendimiento en documentos enriquecidos.
* NVDA ya no debería enlentecerse consumiendo tamaño de memoria del sistema sin razón
* Corregidos fallos cuando se pone el foco en una ventana de consola del dos más de tres veces o así. NVDA tenía una tendencia a colgarse completamente.

### Teclas de órdenes

* NVDA+shift+numpad6 y NVDA+shift+numpad4 te permiten navegar al siguiente o anterior objeto en flujo respectivamente. Esto significa que puedes navegar en una aplicación sólo utilizando estas dos teclas sin preocuparse acerca de subir al padre, o bajar al primer hijo según te muevas a través de la jerarquía de objetos. Por ejemplo en un navegador web tal como firefox, podrías navegar el documento por objetos, sólo utilizando estas dos teclas. Si el siguiente en flujo o el anterior en flujo te acerca y te saca de un objeto, o down en un objeto, mandará pitidos indicando la dirección.
* Ahora puedes configurar opciones de voz sin abrir el diálogo opciones de voz, utilizando el grupo de opciones de sintetizador. El grupo de opciones del sintetizador es un grupo de opciones de voz que puedes conmutar a través de la pulsación de control+NVDA+derecha y control+NVDA+izquierda. Para cambiar una opción utiliza control+NVDA+arriba y control+NVDA+abajo.
* Añadida una orden para anunciar la selección actual en campos de edición (NVDA+shift+flecha arriba).
* Un buen número de órdenes de NVDA que verbalizan texto (tales como anunciar línea actual etc) ahora pueden deletrear el texto si se presionan dos veces rápidamente.
* el BloqMayus, insert del teclado numérico e insert del extendido pueden ser todos utilizados como la tecla modificadora de NVDA. También si una de estas teclas es utilizada, presionándola dos veces rápidamente sin presionar ninguna otra tecla enviará la tecla al sistema operativo, como si presionases la tecla sin NVDA ejecutándose. Para hacer que una de estas teclas sea la modificadora de NVDA, verifica su casilla de verificación en el diálogo de Opciones de Teclado (utilizado para ser llamado el diálogo de eco de teclado).

### Soporte de aplicaciones

* Mejorado el soporte para documentos de Firefox3 y Thunderbird3. Los tiempos de carga han sido mejorados casi por un factor de trenta, una distribución de pantalla es utilizada predeterminadamente (presiona nvda+v para activar o desactivar esta distribución de pantalla), Una lista de enlaces (nvda+f7 ha sido añadida), el diálogo buscar (control+nvda+f) es ahora insensible a las mayúsculas, mucho mejor soporte para contenido dinámico, la selección y copiado de texto es ahora posible.
* En las ventanas de los históricos del MSN Messenger y Windows Live Messenger, ahora es posible seleccionar y copiar texto.
* Mejorado el soporte para la aplicación audacity
* Añadido soporte para unos pocos controles edit/text en Skype
* Mejorado el soporte para la aplicación Miranda instant messenger
* Corregidos algunos problemas del foco cuando se abren mensajes html y de texto planno en Outlook Express.
* Los campos de mensajes de noticias de Outlook express son ahora etiquetados correctamente
* NVDA ahora puede leer las direcciones en los campos de mensajes de Outlook Express (para/de/cc etc)
* NVDA ahora debería estár más certero al anunciar el siguiente mensaje en out look express cuando se elimina un mensaje desde la lista de mensajes.

### APIs y toolkits

* Mejorada la navegación de objetos por los objetos de for MSAA. Si una ventana como un menú del sistema, barra de título, o barras de desplazamiento, ahora puedes navegar por ellas.
* Añadido soporte para la API de accesibilidad IAccessible2. Una parte de la capacidad para anunciar más tipos de controles, esto también permite a NVDA acceder al cursor en aplicaciones tales como Firefox 3 y Thunderbird 3, permitiéndote navegar, seleccionar o editar texto.
* Añadido soporte para controles de edición de Scintilla (tales controles pueden ser encontrados en Notepad++ o Tortoise SVN).
* Añadido soporte para aplicaciones Java (a través del Java Access Bridge). Esto puede proporcionar soporte básico para Open Office (si Java está activado), y cualquier otra aplicación autónoma Java. Nota que los Applets de java dentro de un navegador web no podrá funcionar aún.

### Ratón

* Mejorado el soporte para la lectura de lo que está bajo el puntero del ratón según se mueve. Ahora es mucho más rápido, y ahora también tiene la capacidad en algunos controles tales como campos de edición estándares, controles Java e IAccessible2, para leer la palabra actual, no sólo el objeto actual. Esto podrá ser de algún uso a personas con deficiencia visual que sólo quieran leer un pedazo específico de texto con el ratón.
* Añadida una nueva opción de configuración, encontrada en el diálogo Opciones de Ratón. Reproducir audio cuando el ratón se mueve, cuando está verificada, reproduce un pitido de 40 ms cada vez que el ratón se mueve, con su tono (entre 220 y 1760 hz) representando el eje y, y el volumen izquierda/derecha, representando el eje x. Esto capacita a una persona ciega alcanzar una idea aproximada de dónde está el ratón en la pantalla según está siendo movido. Esta característica también depende de que reportObjectUnderMouse también vaya a ser activado. Así esto significa que si necesitas deshabilitar rápidamente tanto el pitado como el anunciado de objetos, entonces sólo presiona NVDA+m. Los pitidos también son más altos o más bajos dependiendo de cómo brille la pantalla en ese punto.

### Presentación de objetos e interacción

* Mejorado el soporte para la mayoría de los controles comunes de vista en árbol. NVDA te dice ahora cuántos elementos están en la rama cuando la expandes. También anuncia el nivel cuando te mueves en y fuera de las ramas. Y, anuncia el número del elemento actual y el número de elementos, de acuerdo con la actual rama, no el árbol entero.
* Mejorado qué es anunciado cuando el foco cambia según te mueves por aplicaciones o el sistema Operativo. Ahora en lugar de sólo escuchar el control en el que aterrizas, escuchas información interna acerca de cualquier control sobre el que este control esté posicionado. Por ejemplo si tabulas y aterrizas sobre un botón dentro de un grupo, el grupo también será anunciado.
* NVDA ahora trata de verbalizar el mensaje interior de muchos cuadros de diálogo según aparecen. Esto es exacto la mayor parte de las ocasiones, aunque todavía hay muchos diálogos que no son tan buenos como deberían ser.
* Añadida una casilla de verificación anunciar descripciones del objeto al diálogo de Opciones de presentación de objetos. Los usuarios avanzados podrán en ocasiones desverificar esto para detener el anunciado de NVDA de un montón de descripciones extra en controles en particular, tales como en aplicaciones Java.
* NVDA anuncia automáticamente texto seleccionado en controles de edición cuando el foco se mueve a ellos. Si no hay ningún texto seleccionado, entonces sólo anuncia la línea actual como normalmente.
* NVDA es mucho más cuidadoso ahora cuando reproduce pitidos para indicar cambios en las barras de progreso en aplicaciones. Ya no se vuelve loco en aplicaciones de Eclipse tales como Lotus Notes/Symphony, y Accessibility Probe.

### Interfaz del Usuario

* Eliminada la ventana de interfaz de NVDA, y reemplazada con un simple menú de NVDA desplegable.
* El diálogo opciones de Interfaz de NVDA es ahora llamado Opciones Generales. También contiene una opción extra: un cuadro combinado para ajustar el nivel del registro, para que los mensajes puedan ir al fichero de registro de NVDA. Nota que el fichero de registro de NVDA es ahora llamado nvda.log no debug.log.
* Eliminada la casilla de verificación Anunciar nombres de grupos de objetos del diálogo Opciones de presentación de objetos, el anunciado de nombres de objetos es ahora manejado diferentemente.

## 0.5

* NVDA tiene ahora un sintetizador incorporado llammado eSpeak, desarrollado por Jonathan Duddington. Es muy ágil y ligero, y tiene soporte para muchos idiomas diferentes. Los sintetizadores Sapi todavía pueden ser utilizados, pero eSpeak será utilizado predeterminadamente. eSpeak no depende de ningún software especial para ser instalado, así que puede ser utilizado con NVDA en cualquier ordenador, en un lápiz de memoria USB, o cualquier otro. Para más información sobre eSpeak, o para encontrar otras versiones, ve a https://espeak.sourceforge.net/.
 * eSpeak no depende de ningún software especial para instalarse, así que puede utilizarse con NVDA en cualquier ordenador, en una memoria USB o en cualquier lugar.
 * Para más información sobre eSpeak, o para encontrar otras versiones, ve a http://espeak.sourceforge.net/.
* Corrección del fallo donde era anunciado el caracter incorrecto cuando se presionaba Suprimir en paneles editables de Internet Explorer / Outlook Express.
* Añadido soporte para más campos de edición en Skype.
* Los modos virtuales sólo se cargan cuando el foco está sobre la ventana que necesita ser cargada. Esto arregla algunos problemas cuando el panel anterior está activado en Outlook Express.
* Añadidos argumentos de línea de órdenes a NVDA:
 * -m, --minimal: no reproduce los sonidos de inicio/salir y no muestra la interfaz al arrancar si se ajustó a tal cosa.
 * -q, --quit: abandona cualquier otra instancia ya en ejecución de NVDA y luego sale
 * -s, --stderr-file nombreFichero: especifica dónde debería colocar NVDA los errores y excepciones
 * -d, --debug-file nombreFichero: especifica dónde debería colocar NVDA los mensajes de depuración
 * -c, --config-file: especifica un fichero de configuración alternativo
 * -h, -help: muestra un mensaje de ayuda listando los argumentos de línea de órdenes
* Corregido un fallo donde los símbolos de puntuación no deberían ser traducidos al idioma apropiado, cuando se utiliza otro idioma que el inglés, y cuando verbalizar caracteres al escribir estuviera activado.
* Añadidos ficheros del idioma Eslovaco gracias a Peter Vagner
* Añadido el diálogo de Opciones de Modo virtual y un diálogo de opciones de formato de documento, de Peter Vagner.
* Añadida traducción al francés gracias a Michel Such
* Añadido un script para activar y desactivar el pitido de las barras de progreso (insert+u). Colaboración de Peter Vagner.
* Se hace que más mensajes en NVDA sean traducibles para otros idiomas. Esto incluye descripciones de script cuando se está en la ayuda de teclado.
* Añadido un diálogo de búsqueda a los modos virtuales (internet Explorer y Firefox). Presionando control+f cuando se está en una página despliega un diálogo en el que puedes teclear algún texto a encontrar. Presionando intro después buscará este texto y colocará el cursor del modo virtual sobre esta línea. Presionando f3 también buscarás la siguiente ocurrencia del texto.
* Cuando Verbalizar caracteres al escribir está activado, más caracteres deberían ser verbalizados ahora. Técnicamente, ahora los caracteres ascii desde el 32 al 255 pueden ser verbalizados.
* Renombrados algunos tipos de controles para una mejor legibilidad. Texto editable es ahora edición, outline es ahora árbol y botón pulsable es ahora botón.
* Cuando se navega a lo largo de los elementos de una lista, o elementos de árbol en un árbol, el tipo de control (elemento de lista, elemento de árbol) ya no es verbalizado, para una navegación rápida.
* Tiene desplegable (para indicar que un menú tiene un submenú) es ahora verbalizado como submenú.
* Cuando algunos idiomas utilizan control y alt (o altGR) para introducir un caracter especial, NVDA verbalizará ahora estos caracteres cuando Verbalizar caracteres al escribir esté activado.
* Arreglados algunos problemas con la revisión de controles con texto estático.
* Añadida traducción al Chino Tradicional, gracias a Coscell Kao.
* Reestructurado una parte importante del código de NVDA, que debería corregir ahora muchos fallos con la interfaz de usuario de NVDA (incluyendo opciones de diálogos).
* Añadido soporte Sapi4 para NVDA. Actualmente hay dos controladores sapi4, uno basado en código escrito por Serotek Corporation, y otro utilizando la interfaz ActiveVoice.ActiveVoice com. Ambos controladores tienen problemas, mira cuál funciona mejor para ti.
* Ahora cuando se trata de ejecutar una nueva copia de NVDA mientras una copia anterior está todavía ejecutándose causará que la nueva copia salga. Esto arregla un problema mayor cuando se ejecutan múltiples copias de NVDA haciendo que tu sistema sea muy inusable.
* Renombrado el título de la interfaz de usuario de NVDA de Interfaz de NVDA a NVDA.
* Corregido un fallo en Outlook Express cuando al pulsar Retroceso en el inicio de un mensaje editable causaba un error.
* Añadido un parche de Rui Batista que añade un script para anunciar el actual estado de la batería en portátiles (insert+shift+b).
* Añadido un controlador de sintetizador llamado Silence. Este es un controlador de sintetizador que no verbaliza nada, permitiendo a NVDA permanecer completamente silencioso todo el rato. Eventualmente esto sería utilizado junto con el soporte Braille, cuando lo tengamos.
* Añadida opción capitalPitchChange para sintetizadores gracias a J.J. Meddaugh
* Añadido parche de J.J. Meddaugh que hace que el script conmutar anunciado de objetos bajo el ratón sea más parecido a otros scripts conmutables (diciendo activado/desactivado en lugar de cambiando el todo el estado).
* Añadida traducción al español (es) colaboración de Juan C. buño.
* Añadido fichero de idioma Húmgaro de Tamas Gczy.
* Añadido fichero de idioma portugués de Rui Batista.
* El cambio de voz en el diálogo Opciones de voz ajusta ahora los deslizadores de velocidad, tono y volumen a los nuevos de acuerdo con el sintetizador, en lugar de forzar al sintetizador a ser ajustado a los valores anteriores. Esto arregla fallos cuando un sintetizador como eloquence o viavoice parecen hablar a una velocidad mucho más rápida que todos los otros sintetizadores.
* Corregido un fallo donde el sintetizador de voz se detenía, o NVDA se colgaba completamente, cuando se estaba en una ventana de a consola del Dos.
* Si existe soporte para un idioma en particular, NVDA ahora puede mostrar automáticamente su interfaz y verbalizar sus mensajes en el idioma en que Windows esté ajustado. Un idioma particular puede todavía ser elegido manualmente desde el diálogo Opciones de Interfaz de Usuario como también.
* Añadido un script 'toggleReportDynamicContentChanges' (insert+5). Esto conmuta si el texto nuevo, u otros cambios dinámicos deberían ser anunciados automáticamente. Hasta aquí esto sólo funcionaba en ventanas de consola del Dos.
* Añadido el script 'toggleCaretMovesReviewCursor' (insert+6). Esto conmuta si el cusros de revisión debería ser reposicionado automáticamente cuando el cursor del sistema se mueve. Esto es útil en Ventanas de Consola del Dos cuando se trata de leer información cuando la pantalla se está actualizando.
* Añadido el script 'toggleFocusMovesNavigatorObject' (insert+7). Esto conmuta si el navegador de objetos es reposicionado sobre el objeto con el foco cuando cambia.
* Añadida alguna documentación traducida en varios idiomas. Hasta aquí hay Francés, Español y Finlandés.
* Eliminada alguna documentación de desarrolladores de la distribución binaria de NVDA, ahora solamente está en la versión de los fuentes.
* Corregido un posible fallo en Windows Live Messanger y MSN Messenger donde al navegar arriba y abajo por la lista de contactos causaba errores.
* Nuevos mensajes son ahora verbalizados automáticamente cuando se está en una conversación utilizando Windows Live Messenger. (sólo funciona para versiones en Inglés hasta ahora)
* La ventana de históricos en una conversación en Windows Live Messenger ahora puede ser leída utilizando las teclas de flechas. (Sólo funciona para versiones en Inglés hasta el momento)
* Añadido el script 'passNextKeyThrough' (insert+f2). Presiona esta tecla, y entonces la siguiente tecla presionada será pasada directamente a Windows. Esto es útil si has de presionar una tecla en una aplicación pero NVDA utiliza esa tecla para algo.
* NVDA ya no se conjela por más de un minuto cuando se habren documentos muy grandes en MS Word.
* Corregido un fallo cuando se mueve fuera de una tabla en MS Word, y luego se regresa a ella, causaba que los números de la actual fila/columna no sean verbalizados si regresas exactamente a la misma celda.
* Cuando se inicia NVDA con un sintetizador que no existe, o no está funcionando, el sintetizador sapi5 tratará de ser cargado en su lugar, o si sapi5 no está funcionando, entonces la voz será ajustada a silence.
* Los scripts de Incrementar y decrementar la velocidad ya no pueden tomar la velocidad por encima de 100 o por debajo de 0.
* Si hay un error con un idioma cuando se elija en el diálogo Opciones de Interfaz de Usuario, un cuadro de mensaje alertará al usuario del hecho.
* NVDA ahora pregunta si debería guardar la configuración y reiniciar si el usuario ha cambiado el idioma en el diálogo Opciones de Interfaz de Usuario. NVDA debe ser reiniciado para que el cambio de idioma tenga un efecto completo.
* Si un sintetizador no puede ser cargado, cuando se lo selecciona desde el diálogo Sintetizadores, Un cuadro de mensaje alerta al usuario del hecho.
* Cuando se carga un sintetizador por primera vez, NVDA permite al sintetizador elegir la voz más conveniente, los parámetros de velocidad y tono, en lugar de forzarlo a dejarlo como piense que está bien. Esto corrige un problema donde los sintetizadores sapi4 Eloquence y Viavoice comienzan a hablar de un modo bastante rápido para una primera vez.
