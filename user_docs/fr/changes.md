# Quoi de Neuf dans NVDA

## 2024.4

Cette version inclut un certain nombre d'améliorations dans Microsoft Office, au niveau du braille et du formatage des documents.

Dans Word ou Excel, un double appui sur le geste de commandes associé aux commentaires permet désormais de consulter le commentaire ou la note dans une boîte de dialogue.
Vous pouvez désormais utiliser la commande de sélection du curseur de revue pour sélectionner du texte dans PowerPoint.
Lors de l'utilisation du modèle objet dans Word, NVDA n'affiche plus de caractères braille indésirables lorsque le texte de l'en-tête de ligne ou de colonne dans les tableaux est affiché.

NVDA peut désormais être configuré pour annoncer séparément les attributs de police vocalement et en braille.

Un nouveau paramètre a été ajouté pour régler le délai d'attente lors de l'exécution d'un geste de commande nécessitant plusieurs appuis, comme par exemple la commande de rapport de l'heure ou de la date.

Vous pouvez désormais configurer la manière dont NVDA affiche la mise en forme du texte en braille et faire en sorte qu'il affiche le début des paragraphes en braille.
NVDA peut désormais annoncer le caractère à la position du curseur lors d'un appui sur un curseur routine.
La fiabilité du comportement destouches de curseurs routine a été améliorée et celles-ci sont désormais prise en charge dans PowerPoint.
Toutes les lignes de cellules sont désormais exploitées lors de l'utilisation d'un afficheur braille multi-lignes via HID braille.
NVDA n'est plus instable après un redémarrage de NVDA pendant la recherche automatique d'un afficheur braille Bluetooth.

La version minimale requise de Poedit pour fonctionner avec NVDA est désormais la version 3.5.

eSpeak NG a été mis à jour, ajoutant la prise en charge des langues féroïenne et xextane.

LibLouis has been updated, adding new Braille tables for Thai and Greek international braille with single-cell accented letters.

Il y a également eu un certain nombre de correctifs, notamment pour le suivi de la souris dans Firefox et le mode de synthèse vocale à la demande.

### Nouvelles fonctionnalités

* Nouvelles fonctionnalités braille :
  * Il est désormais possible de modifier la façon dont NVDA affiche certains attributs de mise en forme du texte en braille.
    Les options disponibles sont :
    * Liblouis (par défaut) : Utilise les marqueurs de mise en forme définis dans la table braille sélectionnée.
    * Balises : Utilise des balises de début et de fin pour indiquer où commencent et se terminent certains attributs de police. (#16864)
  * Lorsque l'option "Lire par paragraphe" est activée, NVDA peut désormais être configuré pour indiquer le début des paragraphes en braille. (#16895, @nvdaes)
  * Lors de l'appui sur un curseur routine braille, NVDA peut désormais annoncer automatiquement le caractère à la position du curseur. (#8072, @LeonarddeR)
    * Cette option est désactivée par défaut.
      Vous pouvez activer l'option "Annoncer le caractère lors du routage du curseur dans le texte" dans les paramètres braille de NVDA.
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

L'Add-on Store vous informera désormais si des mises à jour d'extensions sont disponibles au démarrage de NVDA.

Il existe désormais des options pour appliquer une normalisation Unicode à la sortie vocale et en braille.
Cela peut être utile lors de la lecture de certains caractères inconnus d'un synthétiseur ou d'une table braille spécifique et qui ont une alternative compatible, comme les caractères de mise en gras ou en italique couramment utilisés sur les réseaux sociaux.
Cela permet également la lecture des équations dans l'éditeur d'équations de Microsoft Word.

Les afficheurs braille Help Tech Activator Pro sont maintenant supportés.

Des commandes non assignées ont été ajoutées pour faire défiler avec la molette de la souris verticalement et horizontalement.

De nombreuses corrections de bogues sont présentes, en particulier pour le panneau d'emojis et l'historique du presse-papiers de Windows 11.
Pour les navigateurs Web, des correctifs sont présents pour l'annonce des messages d'erreur, figures, légendes, étiquettes de tableau et les éléments de menu boutons radio ou cases à cocher.

LibLouis a été mis à jour, ajoutant de nouvelles tables braille pour le cyrillique serbe, le yiddish, plusieurs langues anciennes, le turc et l'Alphabet Phonétique International.
eSpeak a été mis à jour, ajoutant la prise en charge de la langue Karakalpak.
Le CLDR Unicode a également été mis à jour.

### Nouvelles Fonctionnalités

* Nouveaux gestes de commandes :
  * Ajout de commandes non attribuées pour le défilement vertical et horizontal avec la molette de la souris, afin d'améliorer la navigation sur les pages Web et les applications au contenu dynamique, telles que Dism++. (#16462, @Cary-Rowen)
* Ajout de la prise en charge de la normalisation Unicode pour la sortie vocale et braille. (#11570, #16466 @LeonarddeR).
  * Cela peut être utile lors de la lecture de certains caractères inconnus d'un synthétiseur ou d'une table braille spécifique et qui ont une alternative compatible, comme les caractères de mise en gras ou en italique couramment utilisés sur les réseaux sociaux.
  * Cela permet également la lecture des équations dans l'éditeur d'équations de Microsoft Word. (#4631)
  * Vous pouvez activer cette fonctionnalité pour la parole et le braille dans leurs catégories de paramètres respectives dans le dialogue des Paramètres de NVDA.
* Par défaut, après le démarrage de NVDA, vous serez averti si des mises à jour d'extensions sont disponibles. (#15035)
  * Cela peut être désactivé dans la catégorie Add-on Store des paramètres.
  * NVDA vérifie quotidiennement les mises à jour d'extensions.
  * Seules les mises à jour sur le même canal seront vérifiées (par exemple une extension installée en béta n'avertira que des mises à jour sur le canal béta).
* Ajout du support des afficheurs braille Help Tech Activator Pro. (#16668)

### Changements

* Mises à jour de composants :
  * eSpeak NG a été mis à jour à la version 1.52-dev révision `54ee11a79`. (#16495)
    * Ajout de la langue Karakalpak.
  * Mise à jour du CLDR Unicode à la version 45.0. (#16507, @OzancanKaratas)
  * Mise à jour de Fast_diff_match_patch (utilisé pour détecter les changements de contenu dans les terminaux et autre contenus dynamiques) à la version 2.1.0. (#16508, @codeofdusk)
  * Mise à jour du transcripteur braille Liblouis à la version [3.30.0](https://github.com/liblouis/liblouis/releases/tag/v3.30.0). (#16652, @codeofdusk)
    * Nouvelles tables braille :
      * Cyrillique serbe.
      * Yiddish.
      * Plusieurs langues anciennes : Hébreu biblique, Akkadien, Syriaque, Ougaritique et texte cunéiforme translittéré.
      * Turc abrégé. (#16735)
      * Alphabet Phonétique International. (#16773)
  * Mise à jour de NSIS à la version 3.10 (#16674, @dpy013)
  * Mise à jour de markdown à la version 3.6 (#16725, @dpy013)
  * Mise à jour de nh3 à la version 0.2.17 (#16725, @dpy013)
* La table braille d'entrée de secours est désormais égale à la table de sortie de secours, qui est le code braille anglais unifié intégral. (#9863, @JulienCochuyt, @LeonarddeR)
* NVDA annoncera désormais les figures sans élément enfant accessible, mais avec une étiquette ou une description. (#14514)
* Lors de la lecture par ligne en mode navigation, "légende" n'est plus annoncé sur chaque ligne d'une longue légende de figure ou tableau. (#14874)
* Dans la console Python, la dernière commande non exécutée ne sera plus perdue lors du déplacement dans l'historique de saisie. (#16653, @CyrilleB79)
* Un identifiant anonyme unique est désormais envoyé dans le cadre de la collecte facultative de statistiques d'utilisation de NVDA. (#16266)
* Par défaut, un nouveau dossier sera créé lors de la création d'une copie portable.
Un message d'avertissement vous informera si vous tentez d'écrire dans un dossier qui n'est pas vide. (#16686)

### Corrections de Bogues

* Correctifs pour Windows 11 :
  * NVDA ne semblera plus être bloqué lors de la fermeture de l'historique du presse-papiers ou du panneau d'emojis. (#16346, #16347, @josephsl)
  * NVDA annoncera de nouveau les candidats visibles lors de l'ouverture de l'interface IME. (#14023, @josephsl)
  * NVDA n'annoncera plus deux fois "historique du presse-papiers" lors de la navigation dans les éléments du menu du panneau d'emojis. (#16532, @josephsl)
  * NVDA ne coupera plus la parole et le braille lors de la navigation dans les kaomojis et les symboles dans le panneau d'emojis. (#16533, @josephsl)
* Correctifs pour les navigateurs Web :
  * Les messages d'erreur référencés avec `aria-errormessage` sont maintenant annoncés dans Google Chrome et Mozilla Firefox. (#8318)
  * Si disponible, NVDA utilisera désormais `aria-labelledby` pour fournir un nom accessible pour les tableaux dans Mozilla Firefox. (#5183)
  * NVDA annoncera correctement les éléments de menu boutons radio et cases à cocher lors de la première entrée dans des sous-menus dans Google Chrome et Mozilla Firefox. (#14550)
  * La fonctionnalité de recherche du mode navigation de NVDA est désormais plus précise lorsque la page contient des emojis. (#16317, @LeonarddeR)
  * Dans Mozilla Firefox, NVDA annonce désormais correctement le caractère, le mot et la ligne actuels lorsque le curseur est au point d'insertion à la fin d'une ligne. (#3156, @jcsteh)
  * Ne cause plus le plantage de Google Chrome lors de la fermeture d'un document ou en quittant Chrome. (#16893)
* NVDA annoncera correctement les suggestions de saisie semi-automatique dans Eclipse et d'autres environnements basés sur Eclipse sous Windows 11. (#16416, @thgcode)
* Amélioration de la fiabilité de la lecture automatique de texte, en particulier dans les terminaux. (#15850, #16027, @Danstiv)
* Il est à nouveau possible de réinitialiser la configuration aux valeurs par défaut de manière fiable. (#16755, @Emil-18)
* NVDA annoncera correctement les changements de sélection lors de l'édition du texte d'une cellule dans Microsoft Excel. (#15843)
* Dans les applications utilisant Java Access Bridge, NVDA annoncera désormais correctement la dernière ligne vide d'un texte au lieu de répéter la ligne précédente. (#9376, @dmitrii-drobotov)
* Dans LibreOffice Writer (version 24.8 et au-delà), lors de la bascule du formatage du texte (gras, italique, souligné, indice/exposant, alignement) à l'aide du raccourci clavier correspondant, NVDA annoncera le nouvel attribut de formatage (par exemple « Gras activé », « Gras désactivé »). ). (#4248, @michaelweghorn)
* Lors de la navigation avec les touches de curseur dans les zones d'édition des applications utilisant UI Automation, NVDA n'annoncera plus parfois le mauvais caractère, mot, etc. (#16711, @jcsteh)
* Lors du collage dans la calculatrice de Windows 10/11, NVDA annoncera désormais correctement le nombre collé entièrement. (#16573, @TristanBurchett)
* La parole n'est plus silencieuse après la déconnexion et la reconnexion à une session de Bureau à distance. (#16722, @jcsteh)
* Ajout de la prise en charge des commandes de révision de texte pour le nom d'un objet dans Visual Studio Code. (#16248, @Cary-Rowen)
* La lecture des sons de NVDA n'échoue plus sur un périphérique audio mono. (#16770, @jcsteh)
* NVDA annoncera les adresses en parcourant les champs À/Copie à/Copie cachée à dans Outlook.com/Outlook Moderne. (#16856)
* NVDA gère désormais d'une meilleure manière les échecs d'installation d'extensions. (#16704)

### Changements pour les Développeurs

* NVDA utilise désormais Ruff à la place de flake8 pour le linting. (#14817)
* Correction du système de compilation de NVDA pour fonctionner correctement lors de l'utilisation de Visual Studio 2022 version 17.10 et au-delà. (#16480, @LeonarddeR)
* Une police à largeur fixe est désormais utilisée dans la visionneuse du journal et dans la console Python NVDA afin que le curseur reste dans la même colonne lors de la navigation verticale.
Cela est particulièrement utile pour lire l'emplacement des erreurs dans les tracebacks. (#16321, @CyrilleB79)
* Le support pour les tables braille personnalisées a été ajouté. (#3304, #16208, @JulienCochuyt, @LeonarddeR)
  * Les tables peuvent être fournies dans le dossier `brailleTables` d'une extension.
  * Les métadonnées des tables peuvent être ajoutées à une section facultative `brailleTables` dans le manifeste de l'extension ou à un fichier `.ini` avec le même format que celui trouvé dans le sous-dossier brailleTables du dossier scratchpad.
  * Veuillez consulter [la section Braille translation tables dans le guide du développeur](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#BrailleTables) pour plus de détails.
* Lorsqu'un événement `gainFocus` est mis en file d'attente avec un objet qui a une propriété `focusRedirect` valide, l'objet pointé par la propriété `focusRedirect` est désormais détenu par `eventHandler.lastQueuedFocusObject`, plutôt que par l'objet initialement mis en file d'attente. (#15843)
* NVDA journalisera son architecture d'exécution (x86) au démarrage. (#16432, @josephsl)
* `wx.CallAfter`, dont le wrapper se situe dans `monkeyPatches/wxMonkeyPatches.py`, inclut désormais l'indication `functools.wraps` appropriée. (#16520, @XLTechie)
* Il existe un nouveau module pour planifier les tâches `utils.schedule`, en utilisant le module pip `schedule`. (#16636)
  * Vous pouvez utiliser `scheduleThread.scheduleDailyJobAtStartUp` pour planifier automatiquement une tâche qui se produit après le démarrage de NVDA, et toutes les 24 heures par la suite.
  Les tâches sont planifiées avec un retard pour éviter les conflits.
  * `scheduleThread.scheduleDailyJob` et `scheduleJob` peuvent être utilisés pour planifier des tâches à des heures personnalisées, où une `JobClashError` sera déclenchée en cas de conflit de planification de tâches connu.
* Il est désormais possible de créer des modules applicatifs pour les applications hébergeant des contrôles Edge WebView2 (msedgewebview2.exe). (#16705, @josephsl)

## 2024.2

Il existe une nouvelle fonctionnalité nommée séparation du son.
Cela permet de séparer les sons de NVDA d'un côté (par exemple à gauche) tandis que les sons de toutes les autres applications arriveront de l'autre côté (par exemple à droite).

Il existe de nouvelles commandes pour modifier la boucle des paramètres synthétiseur, permettant aux utilisateurs de passer au premier ou au dernier paramètre et d'augmenter ou de diminuer le paramètre courant par pas plus importants.
Il existe également de nouvelles commandes de navigation rapide, permettant aux utilisateurs d'assigner des gestes pour naviguer rapidement entre : paragraphe, paragraphe aligné verticalement, texte de style identique, texte de style différent, élément de menu, bouton bascule, barre de progression, figure, et formule mathématique.

De nombreuses nouvelles fonctionnalités Braille et corrections sont présentes.
Un nouveau mode Braille appelé "afficher la parole" a été ajouté.
Lorsque ce mode est activé, l'affichage Braille affiche exactement ce que NVDA prononce.
Le support des afficheurs Braille BrailleEdgeS2 et BrailleEdgeS3 a également été ajouté.
LibLouis a été mis à jour, avec l'ajout des nouvelles tables Braille Biélorusse et Ukrainien détaillés (avec lettres majuscules indiquées), une table Laotien, et une table Espagnole pour lire le textes grecs.

eSpeak a été mis à jour, avec l'ajout du langage Tigrigna.

Sont présents de nombreux correctifs de bogues mineures pour des applications, telles que Thunderbird, Adobe Reader, les navigateurs Web, Nudi et Geekbench.

### Nouvelles Fonctionnalités

* Nouvelles commandes clavier :
  * Nouvelle commande de navigation rapide `p` pour sauter au paragraphe suivant/précédent en mode navigation. (#15998, @mltony)
  * Nouvelles commandes de navigation rapides non assignées, pouvant être utilisées pour sauter à ces types d'élément suivants/précédents :
    * figure (#10826)
    * paragraphe aligné verticalement (#15999, @mltony)
    * élément de menu (#16001, @mltony)
    * bouton bascule (#16001, @mltony)
    * barre de progression (#16001, @mltony)
    * formule mathématique (#16001, @mltony)
    * texte de style identique (#16000, @mltony)
    * texte de style différent (#16000, @mltony)
  * Ajout de commandes pour sauter au premier, au dernier, en avant et en arrière dans la boucle des paramètres synthétiseur. (#13768, #16095, @rmcpantoja)
    * Aller à la première/dernière valeur du paramètre courant dans la boucle des paramètres synthétiseur n'a pas de geste assigné. (#13768)
    * Diminuer et augmenter le paramètre courant de la boucle des paramètres synthétiseur d'un intervalle plus important (#13768) :
      * Ordinateur de Bureau : `NVDA+contrôle+pagePrec` et `NVDA+contrôle+pageSuiv`.
      * Ordinateur portable : `NVDA+contrôle+maj+pagePrec` et `NVDA+contrôle+maj+pageSuiv`.
  * Ajout d'un nouveau geste de commande non assigné pour basculer l'annonce des figures et légendes. (#10826, #14349)
* Braille :
  * Ajout du support des afficheurs BrailleEdgeS2 et BrailleEdgeS3. (#16033, #16279, @EdKweon)
  * Un nouveau mode Braille appelé "afficher la parole" a été ajouté. (#15898, @Emil-18)
    * Lorsque ce mode est activé, l'affichage Braille affiche exactement ce que NVDA prononce.
    * Il peut être activé/désactivé en appuyant sur `NVDA+alt+t`, ou depuis le dialogue des paramètres Braille.
* Séparation du son : (#12985, @mltony)
  * Permet de séparer les sons de NVDA d'un côté (par exemple à gauche) tandis que les sons de toutes les autres applications arriveront de l'autre côté (par exemple à droite).
  * Activé/désactivé par `NVDA+alt+s`.
* L'annonce des en-têtes de lignes et colonnes est maintenant supporté dans les éléments HTML au contenu éditable. (#14113)
* Ajout d'une option pour désactivé l'annonce des figures et légendes dans les paramètres de mise en forme des documents. (#10826, #14349)
* Sous Windows 11, NVDA annoncera les alertes de saisie vocale et les actions suggérées lors de la copie de données telles que des numéros de téléphone dans le presse-papiers (mise à jour Windows 11 2022 et versions ultérieures). (#16009, @josephsl)
* NVDA maintiendra le périphérique audio éveillé après l'arrêt de la parole, afin d'éviter que le début de la parole suivante ne soit tronqué avec certains périphériques audio tels que les casques Bluetooth. (#14386, @jcsteh, @mltony)
* HP Secure Browser est maintenant supporté. (#16377)

### Changements

* Add-on Store :
  * La version minimale et la dernière version testées d'une extension sont maintenant affichées dans la zone "autres détails". (#15776, @Nael-Sayegh)
  * L'action avis de la communauté sera disponible dans tous les onglets du store. (#16179, @nvdaes)
* Mises à jour de composants :
  * Mise à jour du transcripteur Braille LibLouis à la version [3.29.0](https://github.com/liblouis/liblouis/releases/tag/v3.29.0). (#16259, @codeofdusk)
    * Nouvelles tables Braille Biélorusse et Ukrainien détaillés (avec lettres majuscules indiquées).
    * Nouvelle table Espagnole pour le texte Grec.
    * Nouvelle table Laotien intégral. (#16470)
  * eSpeak NG a été mis à jour à la version 1.52-dev révision `cb62d93fd7`. (#15913)
    * Ajout du langage Tigrigna.
* Changements de plusieurs gestes pour les périphériques BrailleSense pour éviter des conflits avec les caractères de la table Braille française. (#15306)
  * `alt+flècheGauche` est maintenant assigné à `point2+point7+espace`
  * `alt+flècheDroite` est maintenant assigné à `point5+point7+espace`
  * `alt+flècheHaut` est maintenant assigné à `point2+point3+point7+espace`
  * `alt+flècheBas` est maintenant assigné à `point5+point6+point7+espace`
* Les points de remplissage couramment utilisés dans les tables des matières ne sont plus signalés aux faibles niveaux de ponctuation. (#15845, @CyrilleB79)

### Corrections de Bogues

* Correctifs pour Windows 11 :
  * NVDA annoncera de nouveau les suggestions de saisie pour le clavier physique. (#16283, @josephsl)
  * Dans la version 24H2 (mise à jour 2024 et Windows Server 2025), la souris et l'interaction tactile peuvent être utilisées dans les paramètres rapides. (#16348, @josephsl)
* Add-on Store :
  * Lors de l'appui sur `ctrl+tab`, le focus se déplace correctement vers le titre du nouvel onglet. (#14986, @ABuffEr)
  * Si les fichiers mis en cache sont incorrects, NVDA ne redémarrera plus. (#16362, @nvdaes)
* Correctifs pour les navigateurs basés sur Chromium lorsqu'ils sont utilisés avec UIA :
  * Correction de bugs provoquant le blocage de NVDA. (#16393, #16394)
  * Retour arrière fonctionne désormais correctement dans les champs de connexion de Gmail. (#16395)
* Retour arrière fonctionne désormais correctement lors de l'utilisation de Nudi 6.1 avec le paramètre "Exécuter les touches d'autres applications" de NVDA activé. (#15822, @jcsteh)
* Correction d'un bug où les coordonnées audio étaient joués alors que l'application était en veille lorsque "Sonoriser les coordonnées quand la souris se déplace" est activé. (#8059, @hwf1324)
* Dans Adobe Reader, NVDA n'ignore plus le texte alternatif défini dans les formulaires PDF. (#12715)
* Correction d'un bug causant l'échec de NVDA à lire les rubans et options dans Geekbench. (#16251, @mzanm)
* Correction d'un rare cas où l'enregistrement de la configuration pouvait échouer à enregistrer tous les profils. (#16343, @CyrilleB79)
* Dans Firefox et les navigateurs basés sur Chromium, NVDA entrera correctement en mode formulaire lors de l'appui sur entrée lorsque vous êtes positionné dans une liste de présentation (ul / ol) dans un contenu éditable. (#16325)
* Le changement d'état d'une colonne est maintenant correctement annoncé lors du choix des colonnes à afficher dans la liste de messages de Thunderbird. (#16323)
* Le paramètre de ligne de commande `-h`/`--help` fonctionne de nouveau correctement. (#16522, @XLTechie)
* Le support de NVDA pour le logiciel de traduction Poedit version 3.4 ou au-delà fonctionne correctement lors de la traduction de langues avec une ou plus de 2 formes pluriel (par exemple Chinois, Polonais). (#16318)

### Changements pour les Développeurs

Veuillez consulter le [guide du développeur](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur le processus de dépréciation et de suppression de l'API de NVDA.

* Instancier les objets `winVersion.WinVersion` avec des versions de Windows inconnues supérieures à 10.0.22000 tel que 10.0.25398 renvoi "Windows 11 unknown" au lieu de "Windows 10 unknown" comme nom de version. (#15992, @josephsl)
* Le processus de compilation AppVeyor est plus simple pour les forks de NVDA, grâce à l'ajout de variables configurables dans appveyor.yml pour désactiver ou modifier les portions des scripts de compilation propres à NV Access. (#16216, @XLTechie)
* Ajout d'un document how-to, expliquant le processus de compilation pour les forks de NVDA avec AppVeyor. (#16293, @XLTechie)

## 2024.1

Un nouveau mode de parole "à la demande" a été ajouté.
Lorsqu'il est activé, NVDA ne parle pas automatiquement (par exemple lors du déplacement du curseur) mais parle quand même lors de l'appel de commandes dont le but est explicitement d'annoncer quelque chose (par exemple l'annonce du titre de la fenêtre).
Dans la catégorie Parole des paramètres de NVDA, il est désormais possible d'exclure les modes de parole non souhaités de la commande de défilement entre les modes de parole (`NVDA+s`).

Un nouveau mode de sélection native (activé par `NVDA+maj+f10`) est désormais disponible dans le mode navigation de NVDA pour Mozilla Firefox.
Lorsqu'il est activé, la sélection de texte en mode navigation manipulera également la sélection native de Firefox.
Copier du texte avec `contrôle+c` sera transmis directement à Firefox, copiant ainsi le contenu riche, plutôt que la représentation en texte brut de NVDA.

L'Add-on Store prend désormais en charge les actions groupées (par exemple, l'installation, l'activation d'extensions) en sélectionnant plusieurs extensions.
Il existe une nouvelle action pour ouvrir une page Web de commentaires pour l'extension sélectionnée.

Les options périphérique de sortie audio et mode d'atténuation audio ont été supprimées de la boîte de dialogue "Choisir le synthétiseur".
Elles se trouvent dans le panneau des paramètres audio qu'on peut ouvrir avec `NVDA+contrôle+u`.

eSpeak-NG, LibLouis et le CLDR Unicode ont été mis à jour.
De nouvelles tables braille thaïlandaise, philippine et roumaine sont disponibles.

De nombreux correctifs sont présents, notamment pour l'Add-on Store, le braille, Libre Office, Microsoft Office et l'audio.

### Notes importantes

* Cette version rompt la compatibilité avec les extensions existantes.
* Windows 7 et Windows 8 ne sont plus pris en charge.
Windows 8.1 devient la version minimale de Windows prise en charge.

### Nouvelles Fonctionnalités

* Add-on Store :
  * L'Add-on Store prend désormais en charge les actions groupées (par exemple, l'installation, l'activation d'extensions) en sélectionnant plusieurs extensions. (#15350, #15623, @CyrilleB79)
  * Une nouvelle action a été ajoutée pour ouvrir une page Web dédiée afin de voir ou de fournir des commentaires sur l'extension sélectionnée. (#15576, @nvdaes)
* Ajout de la prise en charge des afficheurs Braille Bluetooth Low Energy HID. (#15470)
* Un nouveau mode de sélection native (activé par `NVDA+maj+f10`) est désormais disponible dans le mode navigation de NVDA pour Mozilla Firefox.
Lorsqu'il est activé, la sélection de texte en mode navigation manipulera également la sélection native de Firefox.
Copier du texte avec `contrôle+c` sera transmis directement à Firefox, copiant ainsi le contenu riche, plutôt que la représentation en texte brut de NVDA.
Notez cependant que comme Firefox gère la copie lui-même, NVDA n'annoncera pas de message "copié dans le presse-papiers" dans ce mode. (#15830)
* Lors de la copie de texte dans Microsoft Word avec le mode navigation de NVDA activé, le formatage est désormais également inclus.
En revanche, NVDA n'annoncera plus de message "copié dans le presse-papiers" lorsque vous appuyez sur `contrôle+c` en mode navigation dans Microsoft Word ou Outlook, car l'application gère désormais la copie à la place de NVDA. (#16129)
* Un nouveau mode de parole "à la demande" a été ajouté.
Lorsqu'il est activé, NVDA ne parle pas automatiquement (par exemple lors du déplacement du curseur) mais parle quand même lors de l'appel de commandes dont le but est explicitement d'annoncer quelque chose (par exemple l'annonce du titre de la fenêtre). (#481, @CyrilleB79)
* Dans la catégorie Parole des paramètres de NVDA, il est désormais possible d'exclure les modes de parole non souhaités de la commande de défilement entre les modes de parole (`NVDA+s`). (#15806, @lukaszgo1)
  * Si vous utilisez actuellement l'extension NoBeepsSpeechMode, pensez à la désinstaller et à désactiver les modes de parole "remplacée par des bips" et "à la demande" dans les paramètres.

### Changements

* NVDA ne prend plus en charge Windows 7 et Windows 8.
Windows 8.1 devient la version minimale de Windows prise en charge. (#15544)
* Mises à jour de composants :
  * Mise à jour du transcripteur Braille LibLouis à la version [3.28.0](https://github.com/liblouis/liblouis/releases/tag/v3.28.0). (#15435, #15876, @codeofdusk)
    * Ajout de nouvelles tables braille thaïlandaise, roumaine et philippine.
  * eSpeak NG a été mis à jour à la version 1.52-dev révision `530bf0abf`. (#15036)
  * Les annotations d'emoji et de symboles CLDR ont été mises à jour à la version 44.0. (#15712, @OzancanKaratas)
  * Mise à jour de Java Access Bridge à la version 17.0.9+8Zulu (17.46.19). (#15744)
* Commandes de base :
  * Les commandes suivantes prennent désormais en charge deux et trois appuis pour épeler l'information annoncée et épeler avec la description de caractères : annonce de la sélection, annonce du texte dans le presse-papiers et annonce de l'objet en focus. (#15449, @CyrilleB79)
  * La commande pour activer/désactiver le rideau d'écran a désormais un geste par défaut : `NVDA+contrôle+Échap`. (#10560, @CyrilleB79)
  * Avec 4 appuis, la commande d'annonce de la sélection affiche désormais la sélection dans un message navigable. (#15858, @Émile-18)
* Microsoft Office :
  * Lors de l'annonce des informations de formatage sur les cellules Excel, les bordures et l'arrière-plan ne seront signalés que s'il existe un tel formatage. (#15560, @CyrilleB79)
  * NVDA n'annoncera à nouveau plus les groupes sans label comme dans les menus des versions récentes de Microsoft Office 365. (#15638)
* Les options périphérique de sortie audio et mode d'atténuation audio ont été supprimées de la boîte de dialogue "Choisir le synthétiseur".
Elles se trouvent dans le panneau des paramètres audio qu'on peut ouvrir avec `NVDA+contrôle+u`. (#15512, @codeofdusk)
* L'option "Annoncer le rôle lorsque la souris entre dans un objet" dans la catégorie des paramètres de la souris de NVDA a été renommée en "Annoncer l'objet quand la souris y entre".
Cette option annonce désormais des informations supplémentaires pertinentes sur un objet lorsque la souris y entre, telles que les états (cochés/enfoncés) ou les coordonnées des cellules dans un tableau. (#15420, @LeonarddeR)
* De nouveaux éléments ont été ajoutés au menu Aide vers la page "Obtenir de l'aide" et vers la boutique de NV Access. (#14631)
* Le support de NVDA pour [Poedit](https://poedit.net) a été mis à jour pour Poedit version 3 et supérieure.
Les utilisateurs de Poedit 1 sont encouragés à mettre à jour vers Poedit 3 s'ils souhaitent bénéficier d'une accessibilité améliorée dans Poedit, comme des raccourcis pour lire les notes et les commentaires du traducteur. (#15313, #7303, @LeonarddeR)
* La visionneuse Braille et la visionneuse de parole sont désormais désactivées en mode sécurisé. (#15680)
* Lors de la navigation par objets, les objets désactivés (non disponibles) ne seront plus ignorés. (#15477, @CyrilleB79)
* Ajout d'une table des matières au document de résumé des commandes de base. (#16106)

### Corrections de Bogues

* Add-on Store :
  * Lorsque le statut d'une extension est modifié alors qu'elle a le focus, par ex. le passage de "téléchargement" à "téléchargé", l'élément mis à jour est désormais annoncé correctement. (#15859, @LeonarddeR)
  * Lors de l'installation d'extension, les confirmation d'installation ne sont plus masquées par la boîte de dialogue de redémarrage. (#15613, @lukaszgo1)
  * Lors de la réinstallation d'une extension incompatible, elle n'est plus désactivée de force. (#15584, @lukaszgo1)
  * Les extensions désactivées et incompatibles peuvent désormais être mises à jour. (#15568, #15029)
  * NVDA récupère désormais et affiche une erreur dans le cas où une extension ne parvient pas à se télécharger correctement. (#15796)
  * NVDA n'échoue plus à redémarrer par intermittence après l'ouverture et la fermeture de l'Add-on Store. (#16019, @lukaszgo1)
* Audio :
  * NVDA ne se fige plus brièvement lorsque plusieurs sons sont joués rapidement à la suite. (#15311, #15757, @jcsteh)
  * Si le périphérique de sortie audio est réglé sur autre chose que celui par défaut et que ce périphérique redevient disponible après avoir été indisponible, NVDA reviendra désormais au périphérique configuré au lieu de continuer à utiliser le périphérique par défaut. (#15759, @jcsteh)
  * NVDA reprend désormais l'audio si la configuration du périphérique de sortie change ou si une autre application libère le contrôle exclusif du périphérique. (#15758, #15775, @jcsteh)
* Braille :
  * Les afficheurs braille multilignes ne feront plus planter le pilote BRLTTY et sont traités comme un seul afficheur continu. (#15386)
  * Plus d'objets contenant du texte utile sont détectés et leur contenu est affiché en braille. (#15605)
  * La saisie en braille abrégé fonctionne à nouveau correctement. (#15773, @aaclause)
  * Le braille est désormais mis à jour lors du déplacement de l'objet navigateur entre les cellules d'un tableau dans plus de situations (#15755, @Emil-18)
  * Le résultat de l'annonce du focus courant, de l'objet navigateur courant et de la sélection courante est désormais affiché en braille. (#15844, @Émile-18)
  * Le pilote braille Albatross ne traite plus un microcontrôleur Esp32 comme afficheur Albatross. (#15671)
* LibreOffice :
  * Les mots supprimés à l'aide du raccourci clavier `contrôle+retour arrière` sont désormais également correctement annoncés lorsque le mot supprimé est suivi d'espaces (comme des espaces et des tabulations). (#15436, @michaelweghorn)
  * L'annonce de la barre d'état à l'aide du raccourci clavier `NVDA+fin` fonctionne désormais également pour les boîtes de dialogue dans LibreOffice version 24.2 et plus récente. (#15591, @michaelweghorn)
  * Tous les attributs de texte attendus sont désormais pris en charge dans les versions LibreOffice 24.2 et supérieures.
  Cela permet d'annoncer les fautes d'orthographe lors de l'annonce d'une ligne dans Writer. (#15648, @michaelweghorn)
  * L'annonce des niveaux de titre fonctionne désormais également pour les versions 24.2 et ultérieures de LibreOffice. (#15881, @michaelweghorn)
* Microsoft Office :
  * Dans Excel avec UIA désactivé, le braille est mis à jour et le contenu de la cellule active est annoncé lors de l'appui sur `contrôle+y`, `contrôle+z` ou `alt+retour arrière`. (#15547)
  * Dans Word avec UIA désactivé, le braille est mis à jour lors de l'appui sur `contrôle+v`, `contrôle+x`, `contrôle+y`, `contrôle+z`, `alt+retour arrière`, `retour arrière` ou `contrôle+retour arrière`.
  Il est également mis à jour avec UIA activé, lors de la saisie de texte quand le braille suit la revue et que le curseur de revue suit le curseur applicatif. (#3276)
  * Dans Word, la cellule d'arrivée sera désormais correctement annoncée lors de l'utilisation des commandes Word natives pour la navigation dans les tableaux `alt+début`, `alt+fin`, `alt+page précédente` et `alt+page suivante`. (#15805, @CyrilleB79)
* L'annonce des touches de raccourci des objets a été amélioré. (#10807, #15816, @CyrilleB79)
* Le synthétiseur SAPI4 prend désormais correctement en charge les changements de volume, de débit et de hauteur intégrés dans les paramètres de parole. (#15271, @LeonarddeR)
* L'état multiligne est désormais correctement signalé dans les applications utilisant Java Access Bridge. (#14609)
* NVDA annoncera le contenu des boîtes de dialogue pour davantage de boîtes de dialogue Windows 10 et 11. (#15729, @josephsl)
* NVDA n'échouera plus à lire une page nouvellement chargée dans Microsoft Edge lors de l'utilisation d'UI Automation. (#15736)
* Lors de l'utilisation du mode dire tout ou des commandes qui épellent du texte, les pauses entre les phrases ou les caractères ne diminuent plus progressivement au fil du temps. (#15739, @jcsteh)
* NVDA ne se bloque plus parfois lors de l'annonce d'une grande quantité de texte. (#15752, @jcsteh)
* Lors de l'accès à Microsoft Edge à l'aide d'UI Automation, NVDA est capable d'activer davantage de contrôles en mode navigation. (#14612)
* NVDA n'échouera plus à démarrer lorsque le fichier de configuration est corrompu, et restaurera la configuration par défaut, comme c'était le cas précédemment. (#15690, @CyrilleB79)
* Correction de la prise en charge des contrôles vue de liste système (`SysListView32`) dans les applications Windows Forms. (#15283, @LeonarddeR)
* Il n'est plus possible d'écraser l'historique de la console Python de NVDA. (#15792, @CyrilleB79)
* NVDA devrait rester réactif lors de la réception de nombreux événements UI Automation, par ex. lorsque de gros morceaux de texte apparaissent dans un terminal ou lors de l'écoute de messages vocaux dans WhatsApp Messenger. (#14888, #15169)
  * Ce nouveau comportement peut être désactivé à l'aide du nouveau paramètre "Utiliser le traitement amélioré des événements" dans les paramètres avancés de NVDA.
* NVDA est à nouveau capable de suivre le focus dans les applications exécutées dans Windows Defender Application Guard (WDAG). (#15164)
* Le texte annoncé n'est plus mis à jour lorsque la souris se déplace dans la visionneuse de parole. (#15952, @hwf1324)
* NVDA reviendra à nouveau en mode navigation lors de la fermeture des listes déroulantes avec `échap` ou `alt+flèche haut` dans Firefox ou Chrome. (#15653)
* Les flèches haut et bas dans les zones de liste déroulante dans iTunes ne reviendront plus de manière inappropriée en mode navigation. (#15653)

### Changements pour les développeurs

Veuillez consulter le [guide du développeur](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur le processus de dépréciation et de suppression de l'API de NVDA.

* Note: Cette version rompt la compatibilité avec les extensions existantes.
Les extensions devront être testées à nouveau et leur manifeste mis à jour.
* La compilation de NVDA nécessite désormais Visual Studio 2022.
Veuillez consulter les [documents NVDA](https://github.com/nvaccess/nvda/blob/release-2024.1/projectDocs/dev/createDevEnvironment.md) pour la liste spécifique des composants Visual Studio. (#14313)
* Ajout des points d'extension suivants :
  * `treeInterceptorHandler.post_browseModeStateChange`. (#14969, @nvdaes)
  * `speech.speechCanceled`. (#15700, @LeonarddeR)
  * `_onErrorSoundRequested` (doit être récupéré en appelant `logHandler.getOnErrorSoundRequested()`) (#15691, @CyrilleB79)
* Il est désormais possible d'utiliser des formes plurielles dans les traductions d'une extension. (#15661, @beqabeqa473)
* python3.dll est inclus dans la distribution binaire pour une utilisation par des extensions avec des bibliothèques externes utilisant l'[ABI stable](https://docs.python.org/3.11/c-api/stable.html). (#15674, @mzanm)
* La classe de base `BrailleDisplayDriver` possède désormais les propriétés `numRows` et `numCols` pour fournir des informations sur les afficheurs braille multilignes.
Il est toujours possible de définir `numCells` pour les afficheurs braille à une seule ligne et `numCells` renverra le nombre total de cellules pour les afficheurs braille à plusieurs lignes. (#15386)
* Mise à jour de BrlAPI pour BRLTTY vers la version 0.8.5 et de son module python correspondant vers une version compatible Python 3.11. (#15652, @LeonarddeR)
* Ajout de la fonction `speech.speakSsml`, qui vous permet d'écrire des séquences vocales NVDA en utilisant [SSML](https://www.w3.org/TR/speech-synthesis11/). (#15699, @LeonarddeR)
  * Les balises suivantes sont actuellement prises en charge et traduites en commandes vocales NVDA appropriées :
    * `Prosody` (`pitch`, `rate` et `volume`). Seules les multiplications (par exemple `200%` sont prises en charge.
    * `say-as` avec l'attribut `interpret` défini à `characters`
    * `voice` avec `xml:lang` défini sur à langage XML
    * `break` avec l'attribut `time` défini à une valeur en millisecondes, par ex. `200ms`
    * `mark` avec l'attribut `name` défini à un nom de marque, par ex. `mark1`, nécessite de fournir une fonction de rappel
  * Example : `speech.speakSsml('<speak><prosody pitch="200%">hello</prosody><break time="500ms" /><prosody rate="50%">John</prosody></speak>')`
  * Les capacités d'analyse SSML sont soutenues par la classe `SsmlParser` dans le module `speechXml`.
* Modifications apportées à la bibliothèque Client Contrôleur de NVDA :
  * Les noms de fichiers de la bibliothèque ne contiennent plus de suffixe désignant l'architecture, c'est-à-dire que `nvdaControllerClient32/64.dll` sont désormais appelés `nvdaControllerClient.dll`. (#15718, #15717, @LeonarddeR)
  * Ajout d'un exemple pour montrer l'utilisation de nvdaControllerClient.dll en Rust. (#15771, @LeonarddeR)
  * Ajout des fonctions suivantes au client contrôleur : (#15734, #11028, #5638, @LeonarddeR)
    * `nvdaController_getProcessId` : Pour obtenir l'identifiant de processus (PID) de l'instance actuelle de NVDA que le client contrôleur utilise.
    * `nvdaController_speakSsml` : Pour demander à NVDA de parler selon le SSML fourni. Cette fonction prend également en charge :
      * Fournir le niveau de symbole.
      * Fournir la priorité de la parole à prononcer.
      * Parler de manière synchrone (blocage) ou de manière asynchrone (retour instantané).
    * `nvdaController_setOnSsmlMarkReachedCallback` : pour enregistrer une fonction de rappel de type `onSsmlMarkReachedFuncType` qui est appelé en mode synchrone pour chaque balise `<mark />` rencontrée dans la séquence SSML fournie à `nvdaController_speakSsml`.
  * Remarque : les nouvelles fonctions du client contrôleur ne prennent en charge que NVDA 2024.1 et supérieur.
* Dépendances dans `include` mises à jour :
  * detours à `4b8c659f549b0ab21cf649377c7a84eb708f5e68`. (#15695)
  * ia2 à `3d8c7f0b833453f761ded6b12d8be431507bfe0b`. (#15695)
  * sonic à `8694c596378c24e340c09ff2cd47c065494233f1`. (#15695)
  * w3c-aria-practices à `9a5e55ccbeb0f1bf92b6127c9865da8426d1c864`. (#15695)
  * wil à `5e9be7b2d2fe3834a7107f430f7d4c0631f69833`. (#15695)
* Les informations sur le périphérique générées par `hwPortUtils.listUsbDevices` contiennent désormais la description rapportée par le bus du périphérique USB (clé `busReportedDeviceDescription`). (#15764, @LeonarddeR)
* Pour les périphériques série USB, `bdDetect.getConnectedUsbDevicesForDriver` et `bdDetect.getDriversForConnectedUsbDevices` génèrent désormais des correspondances de périphériques contenant un dictionnaire `deviceInfo` enrichi de données sur le périphérique USB, tel que `busReportedDeviceDescription`. (#15764, @LeonarddeR)
* Lorsque le fichier de configuration `nvda.ini` est corrompu, une copie de sauvegarde est enregistrée avant qu'il soit réinitialisé. (#15779, @CyrilleB79)
* Lors de la définition d'un script avec le décorateur de script, l'argument booléen `speakOnDemand` peut être spécifié pour contrôler si un script doit parler en mode de parole "à la demande". (#481, @CyrilleB79)
  * Les scripts qui fournissent une information (par exemple annoncer le titre de la fenêtre, annoncer l'heure/la date) doivent parler en mode "à la demande".
  * Les scripts qui effectuent une action (par exemple déplacer le curseur, modifier un paramètre) ne doivent pas parler en mode "à la demande".
* Correction d'un bug où la suppression des fichiers suivis par git lors de l'appel à `scons -c` entraînait des interfaces UIA COM manquantes lors de la recompilation. (#7070, #10833, @hwf1324)
* Correction d'un bug où certaines modifications de code n'étaient pas détectées lors de la compilation de `dist`, ce qui empêchait le déclenchement d'une nouvelle compilation.
Maintenant, `dist` est toujours recompilé. (#13372, @hwf1324)
* Un `gui.nvdaControls.MessageDialog` avec un type standard par défaut ne lève plus d'exception de conversion de None car aucun son n'est attribué. (#16223, @XLTechie)

#### Changements avec rupture de l'API

Ces changements modifient l'API des extensions.
Veuillez ouvrir un problème GitHub si votre extension a un problème avec la mise à jour vers la nouvelle API.

* NVDA est désormais compilé avec Python 3.11. (#12064)
* Dépendances pip mises à jour :
  * configobj à 5.1.0dev commit `e2ba4457c4651fa54f8d59d8dcdd3da950e956b8`. (#15544)
  * Comtypes à 1.2.0. (#15513, @codeofdusk)
  * Flake8 à 4.0.1. (#15636, @lukaszgo1)
  * py2exe à 0.13.0.1dev commit `4e7b2b2c60face592e67cb1bc935172a20fa371d`. (#15544)
  * robotframework à 6.1.1. (#15544)
  * SCons à 4.5.2. (#15529, @LeonarddeR)
  * sphinx à 7.2.6. (#15544)
  * wxPython à 4.2.2a commit `0205c7c1b9022a5de3e3543f9304cfe53a32b488`. (#12551, #16257)
* Dépendances pip supprimées :
  * typing_extensions, celles-ci devraient être prises en charge nativement dans Python 3.11 (#15544)
  * nose, à la place, unittest-xml-reporting est utilisé pour générer des rapports XML. (#15544)
* `IAccessibleHandler.SecureDesktopNVDAObject` a été supprimé.
Au lieu de cela, lorsque NVDA s'exécute sur le profil utilisateur, suivez la présence du bureau sécurisé avec le point d'extension : `winAPI.secureDesktop.post_secureDesktopStateChange`. (#14488)
* `braille.BrailleHandler.handlePendingCaretUpdate` a été supprimé sans remplacement public. (#15163, @LeonarddeR)
* `bdDetect.addUsbDevices et bdDetect.addBluetoothDevices` ont été supprimés.
Les pilotes d'afficheur braille doivent implémenter la méthode de classe `registerAutomaticDetection` à la place.
Cette méthode reçoit un objet `DriverRegistrar` sur lequel les méthodes `addUsbDevices` et `addBluetoothDevices` peuvent être utilisées. (#15200, @LeonarddeR)
* L'implémentation par défaut de la méthode de vérification sur un `BrailleDisplayDriver` nécessite désormais que les attributs `threadSafe` et `supportsAutomaticDetection` soient définis sur `True`. (#15200, @LeonarddeR)
* Passer des fonctions lambda à `hwIo.ioThread.IoThread.queueAsApc` n'est plus possible, car les fonctions doivent être faiblement référençables (weakref). (#14627, @LeonarddeR)
* `IoThread.autoDeleteApcReference` a été supprimé. (#14924, @LeonarddeR)
* Pour prendre en charge les changements de hauteur  pour les majuscules, les synthétiseurs doivent désormais déclarer explicitement qu'ils supportent les `PitchCommand` dans l'attribut `supportedCommands` du pilote. (#15433, @LeonarddeR)
* `speechDictHandler.speechDictVars` a été supprimé. Utilisez `NVDAState.WritePaths.speechDictsDir` au lieu de `speechDictHandler.speechDictVars.speechDictsPath`. (#15614, @lukaszgo1)
* `languageHandler.makeNpgettext` et `languageHandler.makePgettext` ont été supprimés.
`npgettext` et `pgettext` sont désormais supportés nativement. (#15546)
* Le module d'application pour [Poedit](https://poedit.net) a été considérablement modifié. La fonction `fetchObject` a été supprimée. (#15313, #7303, @LeonarddeR)
* Les types et constantes redondants suivants ont été supprimés de `hwPortUtils` : (#15764, @LeonarddeR)
  * `PCWSTR`
  * `HWND` (remplacé par `ctypes.wintypes.HWND`)
  * `ULONG_PTR`
  * `ULONGLONG`
  * `NULL`
  * `GUID` (remplacé par `comtypes.GUID`)
* `gui.addonGui.AddonsDialog` a été supprimé. (#15834)
* `touchHandler.TouchInputGesture.multiFingerActionLabel` a été supprimé sans remplacement. (#15864, @CyrilleB79)
* `NVDAObjects.IAccessible.winword.WordDocument.script_reportCurrentHeaders` a été supprimé sans remplacement. (#15904, @CyrilleB79)
* Les modules d'application suivants sont supprimés.
Si du code importait depuis ces modules, il doit maintenant importer depuis le module de remplacement. (#15618, @lukaszgo1)

| Nom du module supprimé |Module de remplacement|
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

#### Dépréciations

* L'utilisation de `watchdog.getFormattedStacksForAllThreads` est obsolète - veuillez utiliser `logHandler.getFormattedStacksForAllThreads` à la place. (#15616, @lukaszgo1)
* `easeOfAccess.canConfigTerminateOnDesktopSwitch` devient obsolète, puisque Windows 7 n'est plus pris en charge. (#15644, @LeonarddeR)
* `winVersion.isFullScreenMagnificationAvailable` est obsolète - utilisez `visionEnhancementProviders.screenCurtain.ScreenCurtainProvider.canStart` à la place. (#15664, @josephsl)
* Les constantes de version Windows suivantes sont obsolètes du module winVersion (#15647, @josephsl) :
  * `winVersion.WIN7`
  * `winVersion.WIN7_SP1`
  * `winVersion.WIN8`
* Les constantes `bdDetect.KEY_*` sont obsolètes.
Utilisez `bdDetect.DeviceType.*` à la place. (#15772, @LeonarddeR).
* Les constantes `bdDetect.DETECT_USB` et `bdDetect.DETECT_BLUETOOTH` sont obsolètes sans remplacement public. (#15772, @LeonarddeR).
* L'utilisation de `gui.ExecAndPump` est obsolète - veuillez utiliser `systemUtils.ExecAndPump` à la place. (#15852, @lukaszgo1)

## 2023.3.4

Version mineure corrigeant un problème de sécurité et un problème avec le programme d'installation.
Veuillez signaler de manière responsable les problèmes de sécurité conformément à la [politique de sécurité](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correctifs de sécurité

* Empêche le chargement d'une configuration alternative lorsque le mode sécurisé est forcé.
([GHSA-727q-h8j2-6p45](https://github.com/nvaccess/nvda/security/advisories/GHSA-727q-h8j2-6p45))

### Corrections de bogues

* Correction d'un bug qui empêchait le processus NVDA de se terminer correctement. (#16123)
* Correction d'un bug où si le processus NVDA précédent ne se terminait pas correctement, une installation de NVDA pouvait échouer et devenir irrécupérable. (#16122)

## 2023.3.3

Version mineure corrigeant un problème de sécurité.
Veuillez signaler de manière responsable les problèmes de sécurité conformément à la [politique de sécurité](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correctifs de sécurité

* Empêche une potentielle attaque XSS réfléchie provenant d'un contenu contrefait pour provoquer l'exécution de code arbitraire.
([GHSA-xg6w-23rw-39r8](https://github.com/nvaccess/nvda/security/advisories/GHSA-xg6w-23rw-39r8))

## 2023.3.2

Version mineure corrigeant un problème de sécurité.
Le correctif de sécurité de la version 2023.3.1 n'a pas été résolu correctement.
Veuillez signaler de manière responsable les problèmes de sécurité conformément à la [politique de sécurité](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correctifs de sécurité

* Le correctif de sécurité de la version 2023.3.1 n'a pas été résolu correctement.
Empêche un potentiel accès au système et l'exécution de code arbitraire avec des privilèges système pour les utilisateurs non authentifiés.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3.1

Version mineure corrigeant un problème de sécurité.
Veuillez signaler de manière responsable les problèmes de sécurité conformément à la [politique de sécurité](https://github.com/nvaccess/nvda/blob/master/security.md) de NVDA.

### Correctifs de sécurité

* Empêche un potentiel accès au système et l'exécution de code arbitraire avec des privilèges système pour les utilisateurs non authentifiés.
([GHSA-h7pp-6jqw-g3pj](https://github.com/nvaccess/nvda/security/advisories/GHSA-h7pp-6jqw-g3pj))

## 2023.3

Cette version inclue des améliorations pour les performances, la réactivité et la fiabilité de la sortie audio.
Des options ont été ajoutées pour contrôler le volume des sons et des bips de NVDA, ou pour qu'ils suivent le volume de la voix utilisée.

NVDA peut maintenant rafraîchir périodiquement le résultat de l'OCR, en annonçant le texte lorsqu'il apparaît.
Cela peut être configuré dans la catégorie Reconnaissance Optique de Caractères de Windows du dialogue de paramètres de NVDA.

Plusieurs corrections pour le Braille ont été apportées, améliorant la détection des appareils et le mouvement du curseur.
Il est maintenant possible d'exclure les pilotes non désirés de la détection automatique, pour en améliorer les performances.
De nouvelles commandes BRLTTY sont également présentes.

Sont également présents des correctifs pour l'Add-on Store, Microsoft Office, les menus contextuels de Microsoft Edge, et la calculatrice de Windows.

### Nouvelles Fonctionnalités

* Amélioration de la gestion du son :
  * Un nouveau dialogue Paramètres Audio :
    * Il peut être ouvert avec `NVDA+contrôle+u`. (#15497)
    * Une option dans les paramètres audio pour que le volume des sons et des bips NVDA suive le réglage du volume de la voix que vous utilisez. (#1409)
    * Une option dans les paramètres Audio pour configurer séparément le volume des sons NVDA. (#1409, #15038)
    * Les paramètres permettant de modifier le périphérique de sortie audio et d'activer l'atténuation audio ont été déplacés du dialogue Sélectionner un synthétiseur vers le nouveau dialogue de paramètres audio . (#8711)
    Ces options seront supprimées du dialogue "Sélectionner un synthétiseur" en 2024.1. (#15486, #8711)
  * NVDA sort désormais l'audio via l'API Windows Audio Session (WASAPI), ce qui peut améliorer la réactivité, les performances et la stabilité de la parole et des sons de NVDA. (#14697, #11169, #11615, #5096, #10185, #11061)
  * Note : WASAPI est incompatible avec certaines extensions.
  Des mises à jour compatibles sont disponibles pour ces extensions, veuillez les mettre à jour avant NVDA.
  Les versions incompatibles de ces extensions seront désactivées lors de la mise à jour de NVDA.
    * Tony's Enhancements version 1.15 ou plus ancien. (#15402)
    * Extension des commandes de base de NVDA 12.0.8 ou plus ancien. (#15443)
* NVDA est maintenant capable d'actualiser continuellement le résultat lors de l'exécution de la reconnaissance optique des caractères (OCR), en annonçant le texte lorsqu'il apparaît. (#2797)
  * Pour activer cette fonctionnalité, activez l'option "Actualiser périodiquement le contenu reconnu" dans la catégorie Reconnaissance Optique de Caractères de Windows du dialogue des paramètres de NVDA.
  * Une fois activé, vous pouvez basculer l'annonce du nouveau texte en basculant l'annonce des changements dynamiques de contenu (en pressant `NVDA+5`).
* Lors de l'utilisation de la détection automatique des afficheurs Braille, il est maintenant possible d'exclure des afficheurs de la détection automatique depuis le dialogue de sélection de l'afficheur Braille. (#15196)
* Nouvelle option dans les paramètres de mise en forme des documents, "Ignorer les lignes vides pour l'annonce d'indentation de ligne". (#13394)
* Ajout d'un geste non assigné pour naviguer par groupe d'onglets en mode navigation. (#15046)

### Changements

* Braille :
  * Lorsque le texte dans un terminal change sans rafraîchir le curseur, le texte sur l'afficheur Braille sera maintenant correctement mis à jour lorsque positionné sur une ligne modifiée.
  Cela inclut les situations où le Braille suit la revue. (#15115)
  * Plus de gestes de commandes BRLTTY sont désormais assignées à des commandes NVDA (#6483) :
    * `learn` : Bascule l'aide d'entrée NVDA
    * `prefmenu` : Ouvrir le menu NVDA
    * `prefload`/`prefsave` : Charger/sauvegarder la configuration NVDA
    * `time` : Afficher l'heure
    * `say_line` : Annoncer la ligne actuelle où est positionné le curseur de revue
    * `say_below` : Dire tout en utilisant le curseur de revue
  * Le pilote BRLTTY est uniquement disponible lorsqu'une instance de BRLTTY avec BrlAPI activé est en cours d'exécution. (#15335)
  * Le paramètre avancé pour activer le support du Braille HID a été remplacé en faveur d'une nouvelle option.
  Vous pouvez maintenant exclure certains pilotes de la détection automatique dans le dialogue de sélection de l'afficheur Braille. (#15196)
* Add-on Store : Les extensions installées apparaitront désormais dans l'onglet extensions disponibles si elles sont disponibles dans le store. (#15374)
* Certaines touches d'accès ont été modifiées dans le menu NVDA. (#15364)

### Corrections de Bogues

* Microsoft Office :
  * Correction d'un crash dans Microsoft Word quand les options de mise en forme des documents "annoncer les titres" et "annoncer les notes et commentaires" ne sont pas activées. (#15019)
  * Dans Word et Excel, l'alignement du texte sera correctement annoncé dans d'avantage de situations. (#15206, #15220)
  * Correction de l'annonce de quelques raccourcis de mise en forme dans Excel. (#15527)
* Microsoft Edge :
  * NVDA ne reviendra plus à la dernière position du mode navigation lors de l'ouverture du menu contextuel dans Microsoft Edge. (#15309)
  * NVDA peut à nouveau lire le menu contextuel des téléchargements dans Microsoft Edge. (#14916)
* Braille :
  * Le curseur et l'indicateur de sélection Braille seront désormais toujours correctement actualisés après avoir affiché ou masqué leurs indicateurs respectifs via un geste de commande. (#15115)
  * Correction d'un problème où les afficheurs Braille Albatross essayaient de s'initialiser alors qu'un autre afficheur Braille était connecté. (#15226)
* Add-on Store :
  * Correction d'un problème où décocher "inclure les extensions incompatibles" continuait malgré tout de lister les extensions incompatibles dans le store. (#15411)
  * Les extensions bloquées pour des raisons d'incompatibilité devraient maintenant être correctement filtrées lors de la bascule du filtre sur le statut activée/désactivée. (#15416)
  * Correction d'un problème empêchant la mise à jour ou le remplacement des extensions incompatibles installées et activées via l'outil d'installation externe. (#15417)
  * Correction d'un problème où NVDA ne parlait plus jusqu'à son redémarrage après l'installation d'une extension. (#14525)
  * Correction d'un problème où une extension ne pouvait pas être installée si un téléchargement précédent avait échoué ou était annulé. (#15469)
  * Correction de problèmes avec la gestion des extensions incompatibles lors de la mise à jour de NVDA. (#15414, #15412, #15437)
* NVDA annonce à nouveau les résultats des calculs dans la calculatrice 32 bits de Windows Server, versions de Windows LTSC et LTSB. (#15230)
* NVDA n'ignore plus les changements de focus lorsqu'une fenêtre imbriquée (fenêtre petit-enfant) obtient le focus. (#15432)
* Correction d'une cause de plantage potentielle au démarrage de NVDA. (#15517)

### Changements pour les Développeurs

Veuillez vous référer au [guide de développement](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur le processus de dépréciation et de suppression de l'API de NVDA.

* `braille.handler.handleUpdate` et `braille.handler.handleReviewMove` ont été modifiés afin de ne pas effectuer de mise à jour instantanée.
Avant ce changement, lorsque l’une ou l’autre de ces méthodes était appelée très souvent, cela consommait beaucoup de ressources.
Ces méthodes mettent désormais en file d’attente une mise à jour à la fin de chaque cycle principal.
Elles doivent également être thread-safe, ce qui permet de les appeler à partir de threads en arrière-plan. (#15163)
* Ajout d'un support officiel pour enregistrer les pilotes d'afficheur braille personnalisés dans le processus de détection automatique de l'afficheur braille.
Veuillez consulter la documentation de la classe `braille.BrailleDisplayDriver` pour plus de détails.
Plus particulièrement, l'attribut `supportsAutomaticDetection` doit être défini sur `True` et la `classmethod` `registerAutomaticDetection` doit être implémentée. (#15196)

#### Dépréciations

* `braille.BrailleHandler.handlePendingCaretUpdate` est désormais obsolète sans remplacement public.
Elle sera supprimé en 2024.1. (#15163)
* Importer les constantes `xlCenter`, `xlJustify`, `xlLeft`, `xlRight`, `xlDistributed`, `xlBottom`, `xlTop` depuis `NVDAObjects.window .excel` est obsolète.
Utilisez les énumérations `XlHAlign` ou `XlVAlign` à la place. (#15205)
* Le mapping `NVDAObjects.window.excel.alignmentLabels` est obsolète.
Utilisez les méthodes `displayString` des énumérations `XlHAlign` ou `XlVAlign` à la place. (#15205)
* `bdDetect.addUsbDevices` et `bdDetect.addBluetoothDevices` sont obsolètes.
Les pilotes d'afficheurs braille doivent implémenter la méthode de classe `registerAutomaticDetection` à la place.
Cette méthode reçoit un objet `DriverRegistrar` sur lequel les méthodes `addUsbDevices` et `addBluetoothDevices` peuvent être utilisées. (#15200)
* L'implémentation par défaut de la méthode check sur `BrailleDisplayDriver` utilise `bdDetect.driverHasPossibleDevices` pour les périphériques marqués comme thread-safe.
À partir de NVDA 2024.1, pour que la méthode de base utilise `bdDetect.driverHasPossibleDevices`, l'attribut `supportsAutomaticDetection` doit également être défini sur `True`. (#15200)

## 2023.2

Cette version introduit l'Add-on Store pour remplacer le gestionnaire d'extensions.
Dans l'Add-on Store vous pouvez parcourir, rechercher, installer et mettre à jour les extensions de la communauté.
Vous pouvez maintenant manuellement passer outre les incompatibilités des extensions obsolètes à vos propres risques et périls.

Sont présents de nouvelles fonctionnalités Braille, commandes et supports d'afficheurs.
Il existe également de nouveaux gestes de commandes pour l'OCR et la navigation par objets à plat.
La navigation et l'annonce du formatage dans Microsoft Office sont améliorés.

Sont présents de nombreux correctifs, essentiellement pour le Braille, Microsoft Office, les navigateurs Web et Windows 11.

eSpeak-NG, le transcripteur Braille LibLouis, et le référentiel Unicode CLDR ont été mis à jour.

### Nouvelles Fonctionnalités

* L'Add-on Store a été ajouté à NVDA. (#13985)
  * Parcourez, recherchez, téléchargez et installez les extensions de la communauté.
  * Contournez manuellement les problèmes de compatibilité avec les extensions obsolètes.
  * Le gestionnaire d'extensions a été supprimé et remplacé par l'add-on store.
  * Pour plus d'informations veuillez lire le guide de l'utilisateur mis à jour.
* Nouveaux gestes de commande :
  * Un geste non assigné pour parcourir les langues disponibles pour l'OCR de Windows. (#13036)
  * Un geste non assigné pour parcourir les modes d'affichage des messages en Braille. (#14864)
  * Un geste non assigné pour basculer l'affichage de l'indicateur de sélection en Braille. (#14948)
  * Ajout de gestes clavier par défaut pour aller à l'objet suivant ou précédent dans une vue à plat de la hierarchie des objets. (#15053)
    * Bureau : `NVDA+pavNum9` et `NVDA+pavNum3` pour se déplacer vers l'objet précédent ou suivant respectivement.
    * Portable : `NVDA+maj+ù` et `NVDA+maj+*` pour se déplacer vers l'objet précédent ou suivant respectivement.
* Nouvelles fonctionnalités Braille :
  * Ajout du support pour l'afficheur Braille Help Tech Activator. (#14917)
  * Nouvelle option pour basculer l'affichage de l'indicateur de sélection (points 7 et 8). (#14948)
  * Nouvelle option pour optionnellement déplacer le curseur système ou le focus lors de la modification de la position du curseur de revue avec les touches routings. (#14885, #3166)
  * Lors de l'appui sur `PavNum2` trois fois pour annoncer la valeur numérique du caractère à la position du curseur de revue, l'information est désormais également indiquée en Braille. (#14826)
  * Ajout du support pour l'attribut ARIA 1.3 `aria-brailleroledescription`, permettant aux développeurs Web de modifier le type d'un élément affiché sur les afficheurs Braille. (#14748)
  * Pilote Baum Braille : ajout de plusieurs gestes de commande Braille pour effectuer des commandes clavier courantes telles que `windows+d` et `alt+tab`.
  Veuillez vous référer au guide de l'utilisateur NVDA pour une liste complète. (#14714)
* Ajout de la prononciation de symboles Unicode :
  * symboles Braille tels que `⠐⠣⠃⠗⠇⠐⠜`. (#13778)
  * symbole de la touche Option Mac `⌥`. (#14682)
* Ajout de gestes pour les afficheurs Braille Tivomatic Caiku Albatross. (#14844, #15002)
  * afficher le dialogue des paramètres Braille
  * accéder à la barre d'état
  * parcourir les formes du curseur Braille
  * parcourir les modes d'affichage des messages Braille
  * activer/désactiver le curseur Braille
  * basculer l'état de l'option "affichage de la sélection en Braille"
  * parcourir les modes pour l'option "le braille déplace le curseur système lors du déplacement du curseur de revue". (#15122)
* Fonctionnalités pour Microsoft Office :
  * Lorsque l'annonce du texte en surbrillance est activé dans les paramètres de mise en forme des documents, les couleurs de surbrillance sont désormais annoncées dans Microsoft Word. (#7396, #12101, #5866)
  * Lorsque l'annonce des couleurs est activée dans les paramètres de mise en forme des documents, les couleurs d'arrière-plan sont maintenant annoncées dans Microsoft Word. (#5866)
  * Lors de l'utilisation des raccourcis clavier Excel pour basculer du formatage tel que gras, italique, souligné et barré d'une cellule dans Excel, le résultat est désormais annoncé. (#14923)
* Amélioration expérimentale de la gestion du son :
  * NVDA peut désormais sortir l'audio via l'API Windows Audio Session (WASAPI), ce qui peut améliorer la réactivité, les performances et la stabilité de la parole et des sons de NVDA. (#14697)
  * L'utilisation de WASAPI peut être activé dans les paramètres avancés.
  De plus, si WASAPI est activé, les paramètres avancés suivants peuvent également être configurés.
    * Une option pour que le volume des sons de NVDA suive le volume de la voix que vous utilisez. (#1409)
    * Une option pour séparément configurer le volume des sons de NVDA. (#1409, #15038)
  * Il existe un problème connu de crashs intermitants lorsque WASAPI est activé. (#15150)
* Sous Mozilla Firefox et Google Chrome, NVDA annonce maintenant quand un contrôle ouvre un dialogue, un tableau, une liste ou une arborescence si l'auteur l'a spécifié en utilisant `aria-haspopup`. (#8235)
* Il est désormais possible d'utiliser des variables systèmes (comme `%temp%` ou `%homepath%`) dans le chemin de création des copies portables de NVDA. (#14680)
* Sous Windows 10 mise à jour de May 2019 et supérieur, NVDA peut maintenant annoncer le nom des bureaux virtuels lors de leur ouverture, changement et fermeture. (#5641)
* Un paramètre système a été ajouté pour permettre aux utilisateurs et administrateurs système de forcer NVDA à démarrer en mode sécurisé. (#10018)

### Changements

* Mises à jour de composants :
  * eSpeak NG a été mis à jour à la version 1.52-dev révision `ed9a7bcf`. (#15036)
  * Mise à jour du transcripteur Braille Liblouis à la version [3.26.0](https://github.com/liblouis/liblouis/releases/tag/v3.26.0). (#14970)
  * Le référentiel Unicode CLDR a été mis à jour à la version 43.0. (#14918)
* Changements pour LibreOffice :
  * Lors de l'annonce de la position du curseur de revue, la position actuelle du focus/curseur est maintenant reportée relativement à la position de la page actuelle sous LibreOffice 7.6 et supérieur, similairement à ce qui est fait pour Microsoft Word. (#11696)
  * L'annonce de la barre d'état, par exemple déclenché par `NVDA+fin`, fonctionne désormais pour LibreOffice. (#11698)
  * Lors du déplacement vers une cellule différente dans LibreOffice Calc, NVDA n'annonce plus incorrectement les coordonnées de la cellule précédente si l'annonce des coordonnées est désactivé dans les paramètres de NVDA. (#15098)
* Changements Braille :
  * Lors de l'utilisation d'un afficheur Braille via le pilote Braille HID standard, le pavé directionnel peut être utilisé pour émuler les touches fléchées et entrée.
  `espace+point1` et `espace+point4` sont également désormais assignées à flèche haut et bas respectivement. (#14713)
  * Les mises à jour des contenus Web dynamiques (ARIA live regions) sont maintenant affichées en Braille.
  Cela peut être désactivé dans le panneau des paramètres avancés. (#7756)
* Les symboles tiret et tiret cadratin seront toujours envoyés au synthétiseur. (#13830)
* L'annonce de la distance dans Microsoft Word respectera maintenant l'unité définie dans les options avancées de Word même lors de l'utilisation de UIA pour l'accès aux documents Word. (#14542)
* NVDA répond plus rapidement lors du déplacement du focus dans un champ d'édition. (#14708)
* Le script pour annoncer la destination d'un lien se base désormais sur la position du curseur / focus plutôt que sur la position de l'objet navigateur. (#14659)
* La création d'une copie portable ne nécessite plus qu'une lettre de lecteur soit entrée comme partie d'un chemin absolu. (#14680)
* Si Windows est configuré pour afficher les secondes dans l'horloge de la barre d'état système, l'annonce de l'heure par `NVDA+f12` respecte maintenant ce paramètre. (#14742)
* NVDA annoncera désormais les groupes non labellisés qui ont des informations de position utiles, comme dans les menus des versions récentes de Microsoft Office 365. (#14878)

### Corrections de Bogues

* Braille :
  * Nombreux correctifs de stabilité pour les entrées/sorties des afficheurs Braille, résultant en moins d'erreurs et crashs fréquents de NVDA. (#14627)
  * NVDA ne basculera plus de nombreuses fois sur Pas de Braille durant la détection automatique, résultant en un journal plus propre et moins de temps perdu. (#14524)
  * NVDA basculera désormais sur USB si un périphérique Bluetooth HID (comme l'HumanWare Brailliant ou l'APH Mantis) est automatiquement détecté et qu'une ocnnexion USB devient disponnible.
  Cela fonctionnait seulement avec les ports série Bluetooth auparavant. (#14524)
  * Lorsqu'aucun afficheur Braille n'est connecté et que la visionneuse Braille est fermée par `alt+f4` ou par un clic sur le bouton Fermer, la taille de l'afficheur du sous système Braille sera rétablie à pas de cellule. (#15214)
* Navigateurs Web :
  * NVDA ne provoque plus occasionnellement le crash ou l'absence de réponse de Mozilla Firefox. (#14647)
  * Sous Mozilla Firefox et Google Chrome, les caractères entrés dans certains champs d'édition ne sont plus annoncés même si l'annonce des caractères saisis est désactivée. (#8442)
  * Vous pouvez maintenant utiliser le mode navigation dans les contrôles Chromium embarqués où cela n'était pas possible auparavant. (#13493, #8553)
  * Sous Mozilla Firefox, déplacer la souris au-dessus d'un texte après un lien annonce désormais correctement le texte. (#9235)
  * La destination des liens graphiques est maintenant annoncée correctement dans de plus nombreux cas sous Chrome et Edge. (#14783)
  * NVDA n'est plus silencieux lors d'une tentative d'annonce de la destination d'un lien sans attribut href.
  À la place, NVDA annonce que le lien n'a pas de destination. (#14723)
  * En mode navigation, NVDA n'ignorera plus incorrectement le passage d'un contrôle à son élément parent ou enfant, par exemple le passage d'un élément à sa liste ou cellule de tableau parente. (#14611)
    * Notez cependant que ce correctif fonctionne uniquement si l'option "Positionnement automatique du focus système sur les éléments susceptibles d'être mis en focus" est désactivée (ce qui est le comportement par défaut)
* Correctifs pour Windows 11 :
  * NVDA peut de nouveau annoncer le contenu de la barre d'état du bloc-notes. (#14573)
  * Basculer entre les onglets annoncera le nom et la position de l'onglet pour le bloc-notes et l'explorateur de fichiers. (#14587, #14388)
  * NVDA annoncera à nouveau les éléments candidats lors de la saisie de texte dans des langues telles que le chinois et le japonais. (#14509)
  * Il est à nouveau possible d'ouvrir les éléments contributeurs et licence dans le menu aide de NVDA. (#14725)
* Correctifs pour Microsoft Office :
  * Lors du passage rapide entre plusieurs cellules dans Excel, NVDA est moins susceptible d'annoncer la mauvaise cellule ou sélection. (#14983, #12200, #12108)
  * Lorsque vous arrivez sur une cellule Excel depuis l'extérieur d'une feuille de calcul, le Braille et le curseur mis en évidence ne sont plus mis à jour inutilement sur l'objet qui avait le focus auparavant. (#15136)
  * NVDA n'échoue plus à annoncer les champs de mot de passe mis en focus dans Microsoft Excel et Outlook. (#14839)
* Pour les symboles qui n'ont pas de description de symbole dans la langue actuelle, le niveau par défaut du symbole en anglais sera utilisé. (#14558, #14417)
* Il est maintenant possible d'utiliser le caractère barre oblique inversée dans le champ de remplacement d'une entrée de dictionnaire, lorsque le type n'est pas défini sur expression régulière. (#14556)
* Dans la calculatrice de Windows 10 et 11, une copie portable de NVDA ne sera plus silencieuse ou ne jouera plus de son d'erreur lors de la saisie d'expression dans le mode de calculatrice standard en mode d'affichage compact. (#14679)
* NVDA fonctionne à nouveau après des situations telles que des plantages d'applications, ce qui le gelait auparavant totalement. (#14759)
* Lorsque le support d'UIA est forcé avec certains terminaux et consoles, un bug qui causait un gel et le remplissage du fichier de log a été corrigé. (#14689)
* NVDA ne refusera maintenant plus de sauvegarder la configuration après une réinitialisation de la configuration. (#13187)
* Lors de l'exécution d'une version temporaire depuis le lanceur, NVDA n'induira plus les utilisateurs en erreur en leur faisant croire qu'ils peuvent enregistrer la configuration. (#14914)
* NVDA répond maintenant globalement plus rapidement aux commandes et changements de focus. (#14928)
* L'affichage des paramètres de la Reconnaissance Optique de Caractères n'échouera plus sur certains systèmes. (#15017)
* Correction d'un bogue sur la sauvegarde et le chargement de la configuration de NVDA, incluant le changement de synthétiseur. (#14760)
* Correction d'un bogue entraînant le geste tactile de revue du texte "glisser vers le haut" à se déplacer par page plutôt qu'aller à la ligne précédente.. (#15127)

### Changements pour les Développeurs

Veuillez vous référer au [guide de développement](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur le processus de dépréciation et de suppression de l'API de NVDA.

* Des conventions suggérées ont été ajoutées à la spécification du manifeste des extensions.
Celles-ci sont facultatives pour la compatibilité avec NVDA, mais sont recommandées ou requises pour la soumission à l'add-on store. (#14754)
  * Utilisation de la `lowerCamelCase` pour le champ name.
  * Utilisation du format `<majeure>.<mineure>.<patch>` pour le champ version (requis pour le add-on datastore).
  * Utilisation de `https://` comme schéma pour le champ URL (requis pour le add-on datastore).
* Ajout d'un nouveau type de point d'extension appelé `Chain`, qui peut être utilisé pour parcourir les itérables renvoyés par les gestionnaires enregistrés. (#14531)
* Ajout du point d'extension `bdDetect.scanForDevices`.
Des gestionnaires peuvent être enregistrés qui produisent des paires `BrailleDisplayDriver/DeviceMatch` qui ne rentrent pas dans les catégories existantes, comme USB ou Bluetooth. (#14531)
* Ajout d'un point d'extension : `synthDriverHandler.synthChanged`. (#14618)
* La boucle des paramètres synthétiseur NVDA met désormais en cache les valeurs de paramètres disponibles la première fois qu'elles sont nécessaires, plutôt que lors du chargement du synthétiseur. (#14704)
* Vous pouvez maintenant appeler la méthode d'exportation sur un mapping de gestes pour l'exporter vers un dictionnaire.
Ce dictionnaire peut être importé dans un autre mapping de gestes en le passant soit au constructeur de `GlobalGestureMap` soit à la méthode update sur un mapping existant. (#14582)
* `hwIo.base.IoBase` et ses dérivés ont maintenant un nouveau paramètre constructeur pour prendre un `hwIo.ioThread.IoThread`.
Si ce paramètre n'est pas fourni, le thread par défaut est utilisé. (#14627)
* `hwIo.ioThread.IoThread` a maintenant une méthode `setWaitableTimer` pour définir un timer d'attente à l'aide d'une fonction python.
De même, la nouvelle méthode `getCompletionRoutine` vous permet de convertir une méthode python en une routine de complétion en toute sécurité. (#14627)
* `offsets.OffsetsTextInfo._get_boundingRects` devrait maintenant toujours retourner une `List[locationHelper.rectLTWH]` comme prévu pour une sous-classe de `textInfos.TextInfo`. (#12424)
* `highlight-color` est maintenant un attribut de champ format. (#14610)
* NVDA devrait déterminer plus précisément si un message enregistré provient du noyau NVDA. (#14812)
* NVDA n'enregistrera plus d'avertissements ou d'erreurs inexacts concernant les appModules obsolètes. (#14806)
* Tous les points d'extension de NVDA sont maintenant brièvement décrits dans un nouveau chapitre dédié dans le Guide du développeur. (#14648)
* `scons checkpot` ne vérifiera plus le sous-dossier `userConfig`. (#14820)
* Les chaînes traduisibles peuvent désormais être définies au singulier et au pluriel en utilisant `ngettext` et `npgettext`. (#12445)

#### Dépréciations

* Le passage de fonctions lambda à `hwIo.ioThread.IoThread.queueAsApc` est obsolète.
Au lieu de cela, les fonctions doivent être des weakrefs. (#14627)
* L'importation de `LPOVERLAPPED_COMPLETION_ROUTINE` depuis `hwIo.base` est obsolète.
A la place, importer depuis `hwIo.ioThread`. (#14627)
* `IoThread.autoDeleteApcReference` est obsolète.
Il a été introduit dans NVDA 2023.1 et n'a jamais été destiné à faire partie de l'API publique.
Jusqu'à ce qu'il soit supprimé, il se comportera comme un no-op, c'est-à-dire un gestionnaire de contexte ne donnant rien. (#14924)
* `gui.MainFrame.onAddonsManagerCommand` est obsolète, utilisez `gui.MainFrame.onAddonStoreCommand` à la place. (#13985)
* `speechDictHandler.speechDictVars.speechDictsPath` est obsolète, utilisez `NVDAState.WritePaths.speechDictsDir` à la place. (#15021)
* L'importation de `voiceDictsPath` et `voiceDictsBackupPath` à partir de `speechDictHandler.dictFormatUpgrade` est obsolète.
Utilisez `WritePaths.voiceDictsDir` et `WritePaths.voiceDictsBackupDir` de `NVDAState` à la place. (#15048)
* `config.CONFIG_IN_LOCAL_APPDATA_SUBKEY` est obsolète.
Utilisez `config.RegistryKey.CONFIG_IN_LOCAL_APPDATA_SUBKEY` à la place. (#15049)

## 2023.1

Une nouvelle option a été ajoutée, "Style de paragraphe" dans "Navigation dans les documents".
Cela peut être utilisé avec les éditeurs de texte ne supportant pas nativement les paragraphes, comme le Bloc-Notes ou Notepad++.

Il existe une nouvelle commande globale pour connaître la destination d'un lien, assignée à `NVDA+k`.

Le support des contenus web annotés (tels que les commentaires et les notes de bas de page) a été amélioré.
Appuyez sur `NVDA+d` pour naviguer entre les résumés lorsque les annotations sont reportées (par exemple "contient un commentaire, contient une note de bas de page").

Les afficheurs Braille Tivomatic Caiku Albatross 46/80 sont désormais supportés.

Le support des versions ARM64 et AMD64 de Windows a été amélioré.

Beaucoup de correctifs sont inclus, notamment pour Windows 11.

eSpeak, LibLouis, Sonic rate boost et le CLDR Unicode ont été mis à jour.
De nouvelles tables Braille Géorgiennes, Swahili (Kenya) et Chichewa (Malawi) sont présentes.

Note :

* Cette version rompt la compatibilité avec les extensions existantes.

### Nouvelles Fonctionnalités

* Microsoft Excel via UI Automation : annonce automatique des en-têtes de lignes et colonnes dans les tableaux. (#14228)
  * Note : Ceci fait référence aux tableaux formatés via le bouton "Tableau" dans l'onglet Insertion du ruban.
  "Première colonne" et "En-tête de ligne" dans "Options de style du tableau" correspondent respectivement aux en-têtes de colonne et ligne.
  * Cela ne fait pas référence aux en-têtes spécifiques au lecteur d'écran via des plages nommés, qui ne sont actuellement pas pris en charge via UI Automation.
* Un script non assigné a été ajouté pour basculer l'annonce de la description différée des caractères. (#14267)
* Ajout d'une option expérimentale pour prendre en charge des notifications UIA dans le terminal Windows pour signaler du texte ajouté ou modifié dans le terminal, ce qui améliore la stabilité et la réactivité. (#13781)
  * Consultez le guide utilisateur pour connaître les limitations de cette nouvelle option.
* Sous Windows 11 ARM64, le mode navigation est maintenant disponible dans les applications AMD64 comme Firefox, Google Chrome et 1Password. (#14397)
* Une nouvelle option a été ajoutée, "Style de paragraphe" dans "Navigation dans les documents".
Ceci ajoute la prise en charge de la navigation par paragraphes via un saut de ligne (normal) et le saut de plusieurs lignes (bloc).
Cela peut être utilisé dans les éditeurs de texte ne supportant pas nativement la navigation par paragraphe, tels que le Bloc-Notes ou Notepad++. (#13797)
* La présence de plusieurs annotations est maintenant annoncée.
`NVDA+d` navigue maintenant entre le résumé de chaque cible d'annotation pour les origines avec plusieurs cibles d'annotation.
Par exemple, lorsqu'un texte a un commentaire et une note de bas de page associés avec lui. (#14507, #14480)
* Ajout du support des afficheurs Braille Tivomatic Caiku Albatross 46/80. (#13045)
* Nouvelle commande globale : annoncer la destination d'un lien (`NVDA+k`).
Appuyer une fois annoncera et affichera en Braille la destination du lien sous l'objet navigateur courant.
Appuyer 2 fois l'affichera dans une fenêtre, pour une revue plus détaillée. (#14583)
* Nouvelle commande globale non assignée (catégorie Outils) : Indiquer l'URL du lien dans une fenêtre.
Revient à appuyer sur `NVDA+K` deux fois, mais pourrait être plus utile pour les utilisateurs Braille. (#14583)

### Changements

* Mise à jour du transcripteur Braille LibLouis à la version [3.24.0](https://github.com/liblouis/liblouis/releases/tag/v3.24.0). (#14436)
  * Mise à jour majeure pour les tables Hongroises, UEB, et Chinois bopomofo.
  * Prise en charge du Braille Danois standard 2022.
  * Nouvelles table Braille Géorgien Braille littéraire, Swahili (Kenya) et Chichewa (Malawi).
* Mise à jour de la librairie Sonic rate boost à la révision `1d70513`. (#14180)
* Le CLDR a été mis à jour à la version 42.0. (#14273)
* eSpeak NG a été mis à jour à la version 1.52-dev révision `f520fecb`. (#14281, #14675)
  * Correction de l'annonce des grands nombres. (#14241)
* Les applications Java avec des contrôles utilisant l'état sélectionnable annonceront désormais lorsqu'un élément n'est pas sélectionné plutôt que lorsque l'élément est sélectionné. (#14336)

### Corrections de bogues

* Correctifs pour Windows 11 :
  * NVDA annoncera les suggestions de recherche à l'ouverture du menu démarrer. (#13841)
  * Sous ARM, les applications x64 ne sont plus identifiées comme applications ARM64. (#14403)
  * Les éléments de menu de l'historique du presse-papiers tels que les éléments épinglés sont maintenant accessibles. (#14508)
  * Sous Windows 11 22H2 et plus récent, il est à nouveau possible d'utiliser la souris et l'interaction tactile pour interagir avec certaines zones telles que la zone de dépassement de la barre d'état système ou le dialogue "Ouvrir avec". (#14538, #14539)
* Les suggestions sont annoncées lors de la saisie d'une @mention dans les commentaires de Microsoft Excel. (#13764)
* Dans la barre d'adresse de Google Chrome, les contrôles des suggestions (basculer vers l'onglet, supprimer la suggestion, etc.) sont maintenant annoncés lorsque sélectionnés. (#13522)
* Lors de l'annonce des informations de mise en forme, les couleurs sont désormais explicitement rapportées dans WordPad ou la visionneuse du journal, au lieu de simplement "Couleur par défaut". (#13959)
* Dans Firefox, l'activation du bouton "Show options" dans les pages d'issues sur GitHub fonctionne maintenant correctement. (#14269)
* Les sélecteurs de date dans le dialogue de recherche avancée de Outlook 2016 / 365 indiquent désormais leur nom et valeur. (#12726)
* Les contrôles ARIA à bascule sont maintenant réellement annoncés comme des bascules dans Firefox, Chrome et Edge, au lieu de cases à cocher. (#11310)
* NVDA annoncera automatiquement l'état du tri sur un en-tête de colonne de tableau HTML lorsqu'il est modifié par l'appui sur un bouton interne. (#10890)
* Le nom d'une région ou d'une région labélisée est toujours prononcé automatiquement lors de l'entrée à l'intérieur en utilisant la navigation rapide ou le focus en mode navigation. (#13307)
* Lorsque les bips ou l'annonce de "majuscule" pour les caractères est activé avec la description différée des caractères, NVDA ne bip ou n'annonce plus "majuscule" deux fois. (#14239)
* Les contrôles dans les tableaux des applications Java seront désormais annoncés plus fréquemment par NVDA. (#14347)
* Certains paramètres ne seront plus anormalement différents lorsqu'utilisés avec plusieurs profils. (#14170)
  * Les paramètres suivants ont été corrigés :
    * Mise en retrait des lignes dans les paramètres de mise en forme des documents.
    * Bordures de cellules dans les paramètres de mise en forme des documents
    * Affichage des messages dans les paramètres Braille
    * Suivi du Braille dans les paramètres Braille
  * Dans certains cas rares, ces paramètres utilisés dans des profils pourraient être inopinément modifiés lors de l'installation de cette version de NVDA.
  * Veuillez vérifier ces options dans vos profils après la mise à jour de NVDA vers cette version.
* Les emojis devraient maintenant être annoncés dans d'avantage de langues. (#14433)
* La présence d'une annotation n'est plus manquante en Braille pour certains éléments. (#13815)
* Correction d'un problème ou la configuration n'était pas correctement sauvegardée lors du changement d'une option de l'état "Par défaut" à la valeur de l'état "Par défaut". (#14133)
* Lors de la configuration de NVDA, il y aura désormais toujours au moins une touche configurée comme touche NVDA. (#14527)
* Lors de l'accès au menu NVDA depuis la zone de notifications, NVDA n'informera plus d'une mise à jour en attente lorsqu'aucune mise à jour n'est disponible. (#14523)
* Le temps écoulé, restant et total est maintenant correctement rapporté dans les fichiers audio plus longs qu'un jour dans Foobar2000. (#14127)
* Dans les navigateurs Web tels que Chrome et Firefox, les alertes comme les téléchargements de fichier sont maintenant affichées en Braille en plus d'être annoncées vocalement. (#14562)
* Correctif lors de la navigation vers la première et dernière colonne d'un tableau dans Firefox (#14554)
* Lorsque NVDA est démarré avec le paramètre `--lang=Windows`, il est à nouveau possible d'ouvrir le dialogue des paramètres généraux de NVDA. (#14407)
* NVDA n'échoue plus à poursuivre la lecture dans Kindle pour PC après avoir tourné la page. (#14390)

### Changements pour les Développeurs

Note : il s'agit d'une version de rupture de compatibilité de l'API des extensions.
Les extensions devront être testées à nouveau et leur manifeste mis à jour.
Veuillez vous référer au [guide de développement](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur le processus de dépréciation et de suppression de l'API de NVDA.

* Les tests système devrait maintenant réussir lorsqu'ils sont exécuté localement sur des systèmes non anglais. (#13362)
* Dans Windows 11 sur ARM, les applications x64 ne sont plus identifiées comme des applications ARM64. (#14403)
* Il n'est plus nécessaire d'utiliser les `NVDAObjects` `UIA` `SearchField` et `NVDAObjects.UIA.SuggestionListItem` dans les nouveaux scénarios UI Automation où l'annonce automatique des suggestions de recherche et où le type a été exposé via UI Automation avec le motif `controllerFor`.
Cette fonctionnalité est désormais disponible de manière générique via `behaviours.EditableText` et le `NVDAObject` de base respectivement. (#14222)
* La catégorie de journalisation de débogage UIA, lorsqu'elle est activée, produit désormais beaucoup plus de journalisation pour les gestionnaires d'événements et les utilitaires UIA. (#14256)
* Mise à jour des normes de construction de NVDAHelper. (#13072)
  * Utilise maintenant la norme C++20, au lieu de C++17.
  * Utilise maintenant le drapeau de compilateur `/permissive-` qui désactive les comportements permissifs et définit les options de compilateur `/Zc` pour une conformité stricte.
* Certains objets plugin (par exemple, les pilotes et les extensions) ont maintenant une description plus informative dans la console python NVDA. (#14463)
* NVDA peut maintenant être entièrement compilé avec Visual Studio 2022, ne nécessitant plus les outils de construction de Visual Studio 2019. (#14326)
* Une journalisation plus détaillée lorsque NVDA se fige pour faciliter le débogage. (#14309)
* La classe singleton `braille._BgThread` a été remplacée par `hwIo.ioThread.IoThread`. (#14130)
  * Une seule instance `hwIo.bgThread` (dans le noyau NVDA) de cette classe fournit des entrées/sorties en arrière-plan pour les pilotes d'affichage braille thread-safe.
  * Cette nouvelle classe n'est pas un singleton de par sa conception, les auteurs d'extensions sont encouragés à utiliser leur propre instance lors des E/S matérielles.
* L'architecture du processeur de l'ordinateur peut être interrogée à partir de l'attribut `winVersion.WinVersion.processorArchitecture.` (#14439)
* De nouveaux points d'extension ont été ajoutés. (#14503)
  * `inputCore.decide_executeGesture`
  * `tones.decide_beep`
  * `nvwave.decide_playWaveFile`
  * `braille.pre_writeCells`
  * `braille.filter_displaySize`
  * `braille.decide_enabled`
  * `braille.displayChanged`
  * `braille.displaySizeChanged`
* Il est possible de définir useConfig sur False sur les paramètres pris en charge pour un pilote de synthétiseur. (#14601)

#### Changements avec rupture de l'API

Ces changements modifient l'API des extensions.
Veuillez ouvrir un problème GitHub si votre extension a un problème avec la mise à jour vers la nouvelle API.

* La spécification de configuration a été altérée, des clés ont été supprimées ou modifiées :
  * Dans la section `[documentFormatting]` (#14233):
    * `reportLineIndentation` stocke une valeur int (0 à 3) au lieu d'un booléen
    * `reportLineIndentationWithTones` a été supprimé.
    * `reportBorderStyle` et `reportBorderColor` ont été supprimés et sont remplacés par `reportCellBorders`.
  * Dans la section `[braille]` (#14233):
    * `noMessageTimeout` a été supprimé, remplacé par une valeur pour `showMessages`.
    * `messageTimeout` ne peut plus prendre la valeur 0, remplacée par une valeur pour `showMessages`.
    * `autoTether` a été supprimé ; `tetherTo` peut maintenant prendre la valeur "auto" à la place.
  * Dans la section `[clavier]` (#14528):
    * `useCapsLockAsNVDAModifierKey`, `useNumpadInsertAsNVDAModifierKey`, `useExtendedInsertAsNVDAModifierKey` ont été supprimés.
    Ils sont remplacés par `NVDAModifierKeys`.
* La classe `NVDAHelper.RemoteLoader64` a été supprimée sans remplacement. (#14449)
* Les fonctions suivantes dans `winAPI.sessionTracking` sont supprimées sans remplacement. (#14416, #14490)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`
* Il n'est plus possible d'activer/désactiver le gestionnaire de braille en définissant `braille.handler.enabled`.
Pour désactiver le gestionnaire de braille par programmation, enregistrez un gestionnaire sur `braille.handler.decide_enabled`. (#14503)
* Il n'est plus possible de mettre à jour la taille d'affichage du gestionnaire en définissant `braille.handler.displaySize`.
Pour mettre à jour displaySize par programme, enregistrez un gestionnaire sur `braille.handler.filter_displaySize`.
Reportez-vous à `brailleViewer` pour un exemple sur la façon de procéder. (#14503)
* Il y a eu des changements dans l'utilisation de `addonHandler.Addon.loadModule`. (#14481)
  * `loadModule` attend maintenant un point comme séparateur, plutôt qu'une barre oblique inverse.
  Par exemple "lib.example" au lieu de "lib\example".
  * `loadModule` renvoie maintenant une exception lorsqu'un module ne peut pas être chargé ou a des erreurs, au lieu de retourner silencieusement `None` sans donner d'informations sur la cause.
* Les symboles suivants ont été supprimés de `appModules.foobar2000` sans remplacement direct. (#14570)
  * `statusBarTimes`
  * `parseIntervalToTimestamp`
  * `getOutputFormat`
  * `getParsingFormat`
* Les éléments suivants ne sont plus des singletons - leur méthode get a été supprimée.
L'utilisation de `Example.get()` est maintenant `Example()`. (#14248)
  * `UIAHandler.customAnnotations.CustomAnnotationTypesCommon`
  * `UIAHandler.customProps.CustomPropertiesCommon`
  * `NVDAObjects.UIA.excel.ExcelCustomProperties`
  * `NVDAObjects.UIA.excel.ExcelCustomAnnotationTypes`

#### Dépréciations

* `NVDAObjects.UIA.winConsoleUIA.WinTerminalUIA` est obsolète et son utilisation est déconseillée. (#14047)
* `config.addConfigDirsToPythonPackagePath` a été déplacé.
Utilisez `addonHandler.packaging.addDirsToPythonPackagePath` en remplacement. (#14350)
* `braille.BrailleHandler.TETHER_*` sont obsolètes.
Utilisez `configFlags.TetherTo.*.value` en remplacement. (#14233)
* `utils.security.postSessionLockStateChanged` est obsolète.
Utilisez `utils.security.post_sessionLockStateChanged` en remplacement. (#14486)
* `NVDAObject.hasDetails`, `NVDAObject.detailsSummary`, `NVDAObject.detailsRole` sont obsolètes.
Utilisez `NVDAObject.annotations` en remplacement. (#14507)
* `keyboardHandler.SUPPORTED_NVDA_MODIFIER_KEYS` est obsolète sans remplacement direct.
Pensez à utiliser la classe `config.configFlags.NVDAKey` en remplacement. (#14528)
* `gui.MainFrame.evaluateUpdatePendingUpdateMenuItemCommand` est obsolète.
Utilisez `gui.MainFrame.SysTrayIcon.evaluateUpdatePendingUpdateMenuItemCommand` en remplacement. (#14523)

## 2022.4

Cette version intègre beaucoup de nouvelles touches de commandes, incluant des commandes "Dire tout" dans les tableaux.
Une section "Guide de Démarrage Rapide" a été ajoutée au guide utilisateur.
Sont également présents un bon nombre de correctifs.

eSpeak et Liblouis ont été mis à jour.
De nouvelles tables Braille Chinoises, Suédoises, Luganda et Kinyarwanda sont incluses.

### Nouvelles Fonctionnalités

* Ajout d'une section "Guide de Démarrage Rapide" au guide de l'utilisateur. (#13934)
* Ajout d'une nouvelle commande pour connaître le raccourci clavier de l'élément actuellement en focus. (#13960)
  * Ordinateur de bureau : `shift+pavnum2`.
  * Ordinateur portable : `NVDA+contrôle+maj+.`.
* Ajout de nouvelles commandes pour déplacer le curseur par page lorsque supporté par l'application. (#14021)
  * Aller à la page précédente :
    * Ordinateur de bureau : `NVDA+page précédente`.
    * Ordinateur portable : `NVDA+maj+page précédente`.
  * Aller à la page suivante :
    * Ordinateur de bureau : `NVDA+page suivante`.
    * Ordinateur portable : `NVDA+maj+page suivante`.
* Ajout des commandes de tableau suivantes. (#14070)
  * Dire tout dans la colonne : `NVDA+contrôle+alt+flèche bas`
  * Dire tout dans la ligne : `NVDA+contrôle+alt+flèche droite`
  * Lire la colonne entière : `NVDA+contrôle+alt+flèche haut`
  * Lire la ligne entière : `NVDA+contrôle+alt+flèche gauche`
* Microsoft Excel via UI Automation : NVDA annonce désormais lorsqu'on quitte un tableau dans une feuille de calcul. (#14165)
* L'annonce des en-têtes de tableau peut maintenant être configurée séparément pour les lignes et colonnes. (#14075)

### Changements

* eSpeak NG a été mis à jour à la version 1.52-dev révision `735ecdb8`. (#14060, #14079, #14118, #14203)
  * Correction de l'annonce des caractères latins lors de l'utilisation du Mandarin. (#12952, #13572, #14197)
* Mise à jour du transcripteur Braille Liblouis à la version [3.23.0](https://github.com/liblouis/liblouis/releases/tag/v3.23.0). (#14112)
  * Ajout de tables Braille :
    * Braille commun Chinois (caractères Chinois simplifié)
    * Kinyarwanda Braille littéraire
    * Luganda Braille littéraire
    * Suédois Braille intégral
    * Suédois Braille partiellement abrégé
    * Suédois Braille abrégé
    * Chinois (Chine, Mandarin) système braille actuel (pas de tons) (#14138)
* NVDA inclut désormais l'architecture du système d'exploitation dans l'envoi des statistiques utilisateur. (#14019)

### Corrections de bogues

* Lors de la mise à jour de NVDA en utilisant le gestionnaire de paquets en ligne de commande (alias winget), une version stable de NVDA n'est plus toujours considérée comme nouvelle lorsqu'une version alpha est installée. (#12469)
* NVDA annoncera désormais correctement les groupes dans les applications Java. (#13962)
* Le curseur suit correctement le texte lu en mode "dire tout" dans les applications telles que Bookworm, WordPad, ou la visionneuse du journal de NVDA. (#13420, #9179)
* Dans les programmes utilisant UI Automation, les cases à cocher partiellement cochées seront annoncées correctement. (#13975)
* Amélioration des performances et de la stabilité dans Microsoft Visual Studio, Windows Terminal, et d'autres applications basées sur UI Automation. (#11077, #11209)
  * Ce correctif s'applique à Windows 11 Sun Valley 2 (version 22H2) et supérieur.
  * Enregistrement sélectif pour les évènements UIA et les changements de propriété maintenant actif par défaut.
* L'annonce du texte, la sortie Braille, et la suppression de mot de passe fonctionne désormais comme attendu dans la console de Terminal Windows intégrée dans Visual Studio 2022. (#14194)
* NVDA a désormais connaissance du DPI lors de l'utilisation de plusieurs écrans.
Cela inclut de nombreux correctifs pour l'utilisation d'un DPI plus élevé que 100% ou de l'utilisation avec plusieurs écrans.
Des problèmes peuvent toujours exister sur les versions de Windows inférieures à Windows 10 1809.
Pour que ces correctifs fonctionnent, les applications avec lesquelles NVDA interagit doivent également avoir connaissance du DPI.
Notez qu'il subsiste des problèmes connus avec Chrome et Edge. (#13254)
  * Le cadre de mise en évidence visuelle devrait maintenant être correctement placé dans plus d'applications. (#13370, #3875, #12070)
  * L'interaction tactile devrait maintenant être opérationnelle dans plus d'applications. (#7083)
  * Le suivi de la souris devrait maintenant fonctionner dans plus d'applications. (#6722)
* Les changements d'état d'orientation (paysage/portrait) sont maintenant correctement ignorés lorsqu'inexistants, par exemple en cas de changement d'écran. (#14035)
* NVDA annoncera les éléments glissés/déposés sur l'écran tels que lors du réarrangement des vignettes du menu démarrer de Windows 10 ou des bureaux virtuels sous Windows 11. (#12271, #14081)
* Dans les paramètres avancés, l'option "Jouer un son pour les erreurs journalisées" est maintenant correctement rétablie à sa valeur d'origine lors de l'appui sur le bouton "Rétablir les paramètres par défaut". (#14149)
* NVDA peut désormais sélectionner du texte en utilisant le raccourcis clavier `NVDA+f10` dans les applications Java. (#14163)
* NVDA ne sera plus bloqué dans un menu lors de l'utilisation des flèches haut et bas dans le filtre des conversations de Microsoft Teams. (#14355)

### Changements pour les Développeurs

Veuillez vous référer au [guide du développeur](https://www.nvaccess.org/files/nvda/documentation/developerGuide.html#API) pour plus d'informations sur la dépréciation et le processus de suppression de l'API de NVDA.

* La [liste de diffusion d'annonce de l'API NVDA](https://groups.google.com/a/nvaccess.org/g/nvda-api/about) a été créée. (#13999)
* NVDA ne traite plus les événements `textChange` pour la plupart des applications UI Automation en raison de leur impact extrêmement négatif sur les performances. (#11002, #14067)

#### Dépréciations

* `core.post_windowMessageReceipt` est obsolète, utilisez `winAPI.messageWindow.pre_handleWindowMessage` à la place.
* `winKernel.SYSTEM_POWER_STATUS` est obsolète et son utilisation est déconseillée, cela a été déplacé vers `winAPI._powerTracking.SystemPowerStatus`.
* Les constantes `winUser.SM_*` sont obsolètes, utilisez `winAPI.winUser.constants.SystemMetrics` à la place.

## 2022.3.3

Il s'agit d'une version mineure pour résoudre des problèmes dans les versions 2022.3.2, 2022.3.1 et 2022.3.
Elle corrige également un problème de sécurité.

### Corrections de Sécurité

* Empêche un éventuel accès au système (par exemple, la console NVDA Python) pour les utilisateurs non authentifiés.
([GHSA-fpwc-2gxx-j9v7](https://github.com/nvaccess/nvda/security/advisories/GHSA-fpwc-2gxx-j9v7))

### Corrections de Bogues

* Correction d'un bug où quand NVDA se fige lors du verrouillage, NVDA autorise l'accès au bureau de l'utilisateur sur l'écran de verrouillage Windows. (#14416)
* Correction d'un bug où quand NVDA se fige lors du verrouillage, NVDA ne se comporte pas correctement, comme si l'appareil était toujours verrouillé. (#14416)
* Correction des problèmes d'accessibilité avec le processus Windows "J'ai oublié mon code PIN" et l'expérience de mise à jour/installation de Windows. (#14368)
* Correction d'un bug lors de la tentative d'installation de NVDA dans certains environnements Windows, par ex. Serveur Windows. (#14379)

### Changements pour les Développeurs

#### Dépréciations

* `utils.security.isObjectAboveLockScreen(obj)` est obsolète, utilisez plutôt `obj.isBelowLockScreen`. (#14416)
* Les fonctions suivantes dans `winAPI.sessionTracking` sont obsolètes pour suppression dans 2023.1. (#14416)
  * `isWindowsLocked`
  * `handleSessionChange`
  * `unregister`
  * `register`
  * `isLockStateSuccessfullyTracked`

## 2022.3.2

Ceci est une version mineure pour corriger des régressions introduites dans la 2022.3.1 et corriger une faille de sécurité.

### Corrections de sécurité

* Évite un potentiel accès privilégié pour des utilisateurs non authentifiés.
([GHSA-3jj9-295f-h69w](https://github.com/nvaccess/nvda/security/advisories/GHSA-3jj9-295f-h69w))

### Corrections de bogues

* Correction d'une régression en 2022.3.1 où certaines fonctionnalités étaient indisponibles sur les écrans sécurisés. (#14286)
* Correction d'une régression en 2022.3.1 où certaines fonctionnalités étaient désactivées après la connexion, si NVDA démarre sur l'écran de connexion. (#14301)

## 2022.3.1

Ceci est une version mineure pour corriger plusieurs failles de sécurité.
Veuillez signaler de manière responsable les problèmes de sécurité à <info@nvaccess.org>.

### Corrections de sécurité

* Correction d'un exploit où il été possible de passer des privilèges utilisateur aux privilèges système.
([GHSA-q7c2-pgqm-vvw5](https://github.com/nvaccess/nvda/security/advisories/GHSA-q7c2-pgqm-vvw5))
* Correction d'une faille où il été possible d'accéder à la console Python sur l'écran de connexion via une condition dans le démarrage de NVDA.
([GHSA-72mj-mqhj-qh4w](https://github.com/nvaccess/nvda/security/advisories/GHSA-72mj-mqhj-qh4w))
* Correction d'un problème où le texte de la visionneuse de parole est disponible lors du verrouillage de Windows.
([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

### Corrections de bogues

* Empêche un utilisateur non authentifié de modifier des paramètres pour la visionneuse Braille ou visionneuse de paroles depuis l'écran de verrouillage. ([GHSA-grvr-j2h8-3qm4](https://github.com/nvaccess/nvda/security/advisories/GHSA-grvr-j2h8-3qm4))

## 2022.3

Une grande partie des améliorations de cette version a été réalisée par la communauté de NVDA.
Cela inclut la description différée des caractères et la prise en charge améliorée de la console Windows.

Cette version intègre également de nombreux correctifs.
Notamment, les versions récentes d'Adobe Acrobat ne plantent plus lors de la lecture de documents PDF.

eSpeak a été mis à jour, ce qui introduit 3 nouvelles langues : Bélarusse, Luxembourgeois et Totontepec Mixe.

### Nouvelles fonctionnalités

* Dans l'hôte de console Windows utilisé par l'invite de commande, PowerShell, et le sous-système Windows pour Linux sous Windows 11 version 22H2 (Sun Valley 2) et supérieur :
  * Considérables améliorations de performance et de stabilité. (#10964)
  * Lors de l'appui sur `contrôle+f` pour effectuer une recherche, la position du curseur de revue est mise à jour à la position du résultat trouvé. (#11172)
  * L'annonce du texte tapé n'apparaissant pas à l'écran (comme les mots de passe) est désactivée par défaut.
Elle peut être réactivée dans le panneau des paramètres avancés de NVDA. (#11554)
  * Le texte ayant défilé hors de l'écran peut être revu sans devoir faire défiler la fenêtre de la console. (#12669)
  * Plus de détails sur le formatage du texte sont disponibles. ([microsoft/terminal PR 10336](https://github.com/microsoft/terminal/pull/10336))
* Une nouvelle option de parole a été ajoutée pour lire la description des caractères après un délai. (#13509)
* Une nouvelle option Braille a été ajoutée pour choisir si le défilement avant/arrière de l'afficheur Braille doit interrompre la voix. (#2124)

### Changements

* eSpeak NG a été mis à jour à la version 1.52-dev révision `9de65fcb`. (#13295)
  * Langues ajoutées :
    * Bélarusse
    * Luxembourgeois
    * Totontepec Mixe
* Lors de l'utilisation de UIAutomation pour accéder aux feuilles de calcul Microsoft Excel, NVDA peut maintenant annoncer si une cellule est fusionnée. (#12843)
* Au lieu d'indiquer "contient des détails" le type de détail est inclus si possible, par exemple "contient un commentaire". (#13649)
* La taille d'installation de NVDA est maintenant affichée dans la section programmes et fonctionnalités de Windows. (#13909)

### Corrections de bogues

* Adobe Acrobat / Reader 64 bit ne plantera plus lors de la lecture d'un document PDF.. (#12920)
  * Notez que la version la plus récente d'Adobe Acrobat / Reader est également nécessaire pour éviter le plantage.
* Les mesures de tailles de police sont maintenant traduisibles dans NVDA. (#13573)
* Les évènements Java Access Bridge sont ignorés lorsqu'aucune fenêtre ne peut être trouvée pour une application Java.
Cela améliorera les performances pour certaines applications Java incluant IntelliJ IDEA. (#13039)
* L'annonce des cellules sélectionnées dans LibreOffice Calc est plus efficace et évitera désormais le gel de Calc lorsque beaucoup de cellules sont sélectionnées. (#13232)
* Exécuté sous un compte utilisateur différent, Microsoft Edge n'est plus inaccessible. (#13032)
* Lorsque la voix turbo est désactivée, le débit de eSpeak ne vari plus anormalement entre 99 et 100%. (#13876)
* Correction d'un bogue qui permettait à 2 dialogues "Gestes de commandes" d'être ouverts. (#13854)

### Changements pour les développeurs

* Mise à jour de Comtypes à la version 1.1.11. (#12953)
* Dans les versions de la console Windows (`conhost.exe`) avec un niveau d'API NVDA de 2 (`FORMATTED`) ou supérieur, telles que celles incluses avec Windows 11 version 22H2 (Sun Valley 2), UI Automation est désormais utilisé par défaut. (#10964)
  * Cela peut être annulé en modifiant le paramètre "Prise en charge de la console Windows" dans le panneau des paramètres avancés de NVDA.
  * Pour trouver le niveau d'API NVDA de votre console Windows, définissez "Prise en charge de la console Windows" sur "UIA si disponible", puis vérifiez le journal NVDA+F1 ouvert à partir d'une instance de la console Windows en cours d'exécution.
* Le tampon virtuel Chromium est maintenant chargé même lorsque l'objet document a l'état MSAA `STATE_SYSTEM_BUSY` exposé via IA2. (#13306)
* Un type de spécification de configuration `featureFlag` a été créé pour être utilisé avec des fonctionnalités expérimentales dans NVDA. Voir `devDocs/featureFlag.md` pour plus d'informations. (#13859)

#### Dépréciations

Aucune dépréciation n'est proposée pour la version 2022.3.

## 2022.2.4

Version mineure corrigeant un problème de sécurité.

### Corrections de Bogues

* Correction d'un exploit rendant possible d'ouvrir la console python NVDA via la visionneuse de journal sur l'écran de verrouillage.
([GHSA-585m-rpvv-93qg](https://github.com/nvaccess/nvda/security/advisories/GHSA-585m-rpvv-93qg))

## 2022.2.3

Cette version corrige une rupture accidentelle d'API introduite dans la version 2022.2.1.

### Corrections de Bogues

* Correction d'un bogue faisant que NVDA n'annonçait pas "Bureau Sécurisé" quand on entrait dans un bureau sécurisé.
Cela faisait que NVDA Remote ne reconnaissait pas les bureaux sécurisés. (#14094)

## 2022.2.2

Ceci est une version corrigeant un problème introduit en 2022.2.1 concernant les gestes de commandes.

### Corrections de bogues

* Correction d'un problème faisant que les gestes de commandes ne fonctionnaient pas toujours (#14065)

## 2022.2.1

Version mineure corrigeant un problème de sécurité.
Veuillez signaler de manière responsable les problèmes de sécurité à <info@nvaccess.org>.

### Correctifs de sécurité

* Correction d'une faille rendant possible d'exécuter une console Python depuis l'écran de verrouillage. (GHSA-rmq3-vvhq-gp32)
* Correction d'une faille rendant possible de sortir de l'écran de verrouillage en utilisant la navigation par objet. (GHSA-rmq3-vvhq-gp32)

### Changements pour les développeurs

#### Dépréciations

Ces dépréciations ne sont actuellement pas prévues pour être supprimées.
Les alias dépréciés resteront disponibles jusqu'à nouvel ordre.
Veuillez tester la nouvelle API et fournir des commentaires.
Pour les auteurs d'extensions, veuillez ouvrir un problème GitHub si ces modifications empêchent l'API de répondre à vos besoins.

* `appModules.lockapp.LockAppObject` doit être remplacé par `NVDAObjects.lockscreen.LockScreenObject`. (GHSA-rmq3-vvhq-gp32)
* `appModules.lockapp.AppModule.SAFE_SCRIPTS` doit être remplacé par `utils.security.getSafeScripts()`. (GHSA-rmq3-vvhq-gp32)

## 2022.2

Cette version inclut beaucoup de correctifs.
Notamment, il y a des améliorations significatives pour les applications Java, le Braille, et les fonctionnalités Windows.

De nouvelles commandes de navigation pour les tableaux ont été introduites.
Le CLDR Unicode a été mis à jour.
LibLouis a été mis à jour, ce qui inclut une nouvelle table Braille allemande.

### Nouvelles Fonctionnalités

* Support de l'interaction avec les composants Microsoft Loop dans les produits Microsoft Office. (#13617)
* De nouvelles commandes de navigation de tableau ont été ajoutées. (#957)
 * `Contrôle+Alt+Début/Fin` pour sauter à la première/dernière colonne.
 * `Contrôle+Alt+Page précédente/Page suivante` pour sauter à la première/dernière ligne.
* Un script non assigné pour basculer entre les modes de changement de langue et dialecte a été ajouté. (#10253)

### Changements

* NSIS a été mis à jour à la version 3.08. (#9134)
* Le CLDR a été mis à jour à la version 41.0. (#13582)
* Mise à jour du transcripteur Braille Liblouis à la version [3.22.0](https://github.com/liblouis/liblouis/releases/tag/v3.22.0). (#13775)
  * Nouvelle table Braille : Allemand abrégé (détaillé)
* Ajout d'un nouveau rôle de contrôles "indicateur d'occupation". (#10644)
* NVDA annonce maintenant quand une action NVDA ne peut être réalisée. (#13500)
  * Cela peut se produire :
    * Lors de l'utilisation de la version Windows Store
    * Lors de l'utilisation dans un contexte sécurisé.
    * Lors de l'attente d'une réponse à une boîte de dialogue modale.

### Corrections de bogues

* Correctifs pour les applications basées sur Java :
  * NVDA annoncera maintenant l'état lecture seule. (#13692)
  * NVDA annoncera maintenant correctement l'état activé/désactivé. (#10993)
  * NVDA annoncera maintenant les raccourcis des touches de fonction. (#13643)
  * NVDA peut maintenant bipper ou parler sur des barres de progression. (#13594)
  * NVDA ne retirera plus incorrectement du texte des widgets lors de leur présentation à l'utilisateur. (#13102)
  * NVDA annoncera maintenant l'état des boutons bascule. (#9728)
  * NVDA identifiera maintenant la fenêtre dans une application Java avec plusieurs fenêtres. (#9184)
  * NVDA annoncera maintenant la position pour les contrôles d'onglet. (#13744)
* Correctifs Braille :
  * Correction de l'affichage Braille lors de la navigation de texte dans des contrôle d'édition Mozilla, comme l'édition d'un message brouillon dans Thunderbird. (#12542)
  * Lorsque le Braille est détecté automatiquement et que la souris est déplacée avec le suivi de la souris actif,
   les commandes de déplacement du curseur de revue mettent maintenant à jour l'afficheur Braille avec le texte parlé. (#11519)
  * Il est maintenant possible de faire défiler l'affichage Braille à travers le contenu après l'utilisation des commandes de révision de texte. (#8682)
* L'installeur NVDA peut maintenant s'exécuter depuis des dossiers contenant des caractères spéciaux (#13270)
* Dans Firefox, NVDA n'échoue plus à annoncer les éléments lorsque les attributs aria-rowindex, aria-colindex, aria-rowcount ou aria-colcount sont invalides. (#13405)
* Le curseur ne change plus de ligne ou de colonne lors de l'utilisation de la navigation de tableau pour naviguer dans des cellules fusionnées. (#7278)
* Lors de la lecture de PDFs non interactifs dans Adobe Reader, le type et l'état des champs de formulaire (comme les cases à cocher ou boutons radio) est maintenant annoncé. (#13285)
* "Réinitialiser la configuration aux valeurs par défaut" est maintenant accessible dans le menu NVDA en mode sécurisé. (#13547)
* Tout bouton de la souris verrouillé sera déverrouillé à la fermeture de NVDA, précédemment les boutons de la souris restaient verrouillés. (#13410)
* Visual Studio reporte maintenant les numéros de ligne. (#13604)
  * Notez que pour le report des numéros de ligne, l'affichage des numéros de ligne doit être activé dans Visual Studio et NVDA.
* Visual Studio reporte maintenant correctement l'indentation des lignes. (#13574)
* NVDA annoncera à nouveau le détail des résultats de recherche dans le menu démarrer des versions récentes de Windows 10 et 11. (#13544)
* Dans la calculatrice de Windows 10 et 11 version 10.1908 et supérieur,
NVDA annoncera les résultats lorsque davantage de commandes seront pressées, telles que des commandes en mode scientifique. (#13383)
* Sous Windows 11, il est à nouveau possible de naviguer et d'interagir avec certains éléments de l'interface utilisateur
comme la barre des tâches en utilisant la souris ou l'interaction tactile. (#13506)
* NVDA annoncera le contenu de la barre d'état dans le bloc-notes de Windows 11. (#13688)
* La mise en évidence de l'objet navigateur s'affiche maintenant tout de suite après l'activation de la fonctionnalité. (#13641)
* Correction de la lecture des éléments de liste avec une seule colonne. (#13659, #13735)
* Correction du changement automatique de langue d'eSpeak pour l'anglais et le français revenus à Anglais britannique et Français (France). (#13727)
* Correction du changement automatique de langue de OneCore lors d'une tentative de passage vers une langue anciennement installée. (#13732)

### Changements pour les développeurs

* La compilation des dépendances de NVDA avec Visual Studio 2022 (17.0) est maintenant supportée.
Pour le développement et les versions de production, Visual Studio 2019 est toujours utilisé. (#13033)
* Lors de la récupération du nombre d'enfants sélectionnés via accSelection,
le cas où un ID d'enfant négatif ou un IDispatch est renvoyé par `IAccessible::get_accSelection` est désormais correctement géré. (#13277)
* De nouvelles fonctions pratiques `registerExecutableWithAppModule` et `unregisterExecutable` ont été ajoutées au module `appModuleHandler`.
Elles peuvent être utilisées pour utiliser un seul module d'application avec plusieurs exécutables. (#13366)

#### Dépréciations

Voici des propositions de changements de rupture d'API.
La partie obsolète de l'API restera disponible jusqu'à la version spécifiée.
Si aucune version n'est spécifiée, le plan de suppression n'a pas été déterminé.
Notez que la feuille de route pour les suppressions est « au mieux » et peut être sujette à modification.
Veuillez tester la nouvelle API et fournir des commentaires.
Pour les auteurs d'extensions, veuillez ouvrir un problème GitHub si ces modifications empêchent l'API de répondre à vos besoins.

* `appModuleHandler.NVDAProcessID` est obsolète, utilisez `globalVars.appPid` à la place. (#13646)
* `gui.quit` est obsolète, utilisez `wx.CallAfter(mainFrame.onExitCommand, None)` directement à la place. (#13498)
  -
* Certains alias appModules sont marqués comme obsolètes.
Si votre code importe de l'un d'eux, il devra plutôt importer du module de remplacement. (#13366)

| Nom du module supprimé |Module de remplacement|
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

Cette version inclus de nombreuses améliorations du support de UIA dans Microsoft Office.
Pour Microsoft Office 16.0.15000 et supérieur sous Windows 11, NVDA utilisera UI Automation par défaut pour accéder aux documents Microsoft Word.
Cela permet un considérable gain de performances pour l'accès à tout les objets.

Sont présentes des améliorations pour certains pilotes Braille incluant Seika Notetaker, Papenmeier et HID Braille.
Il y a également de nombreuses corrections pour Windows 11, pour les applications telles que la Calculatrice, la Console, le Terminal, Courrier et le panneau d'emojis.

eSpeak-NG et LibLouis ont été mis à jour, ajoutant de nouvelles tables Japonaises, Allemandes et Catalanes.

Note :

 * Cette version rompt la compatibilité avec les extensions existantes.

### Nouvelles fonctionnalités

* Support de l'annonce des annotations dans MS Excel avec UI Automation sous Windows 11. (#12861)
* Dans les versions récentes de Word avec UI Automation activé sous Windows 11, l'existence de signets, de commentaires brouillons et de commentaires résolus est maintenant reportée vocalement et en Braille. (#12861)
* Le nouveau paramètre de ligne de commande `--lang` permet de remplacer la langue configurée dans NVDA. (#10044)
* NVDA alerte maintenant sur l'utilisation de paramètres de ligne de commande inconnus et utilisés par aucune extension. (#12795)
* Dans Microsoft Word avec UI Automation, NVDA utilisera maintenant mathPlayer pour lire et naviguer dans les équations Office Math. (#12946)
  * Pour que cela fonctionne, vous devrez utiliser Microsoft Word 365/2016 version 14326 ou supérieur.
  * Les équations MathType devront également être manuellement converties en équations Office Math en les sélectionnant une à une, en ouvrant le menu contextuel et en choisissant Options d'équation, Convertir en Office Math.
* L'annonce de "Possède des détails" et la commande associée pour résumer les détails a été mise à jour pour fonctionner en mode formulaire. (#13106)
* Seika Notetaker peut maintenant être autodétecté lorsque connecté en USB ou Bluetooth, #13142)
  * Cela concerne les périphériques suivants : MiniSeika (16, 24 cellules), V6, et V6Pro (40 cellules)
  * La sélection manuelle du port COM est également maintenant supportée.
* Ajout d'une commande pour activer/désactiver la visionneuse Braille, sans geste par défaut. (#13258)
* Ajout de commandes pour émuler plusieurs modificateurs simultanément avec un afficheur Braille (#13152)
* Le dialogue dictionnaire de prononciation a maintenant un bouton "Supprimer tout" pour vider tout un dictionnaire. (#11802)
* Ajout du support de la calculatrice de Windows 11. (#13212)
* Dans Microsoft Word avec UIA activé sous Windows 11, les numéros de ligne et numéros de section peuvent maintenant être annoncés. (#13283, #13515)
* Pour Microsoft Office 16.0.15000 et supérieur sous Windows 11, NVDA utilisera UI Automation par défaut pour accéder aux documents Microsoft Word, offrant un considérable gain de performances pour l'accès à tout les objets. (#13437)
 * Cela inclut les documents dans Microsoft Word lui-même, ainsi que le lecteur et le composeur de messages dans Outlook

### Changements

* Espeak-ng a été mis à jour à la version 1.51-dev révision `7e5457f91e10`. (#12950)
* Mise à jour du transcripteur Braille Liblouis à la version [3.21.0](https://github.com/liblouis/liblouis/releases/tag/v3.21.0). (#13141, #13438)
  * Ajout de nouvelles tables Braille : Japonais (Kantenji) braille littéraire
  * Ajout de la nouvelle table Braille Allemand Braille informatique 6 points
  * Ajout de la table Braille Catalan intégral (#13408)
* NVDA annoncera la sélection et la fusion de cellules dans LibreOffice 7.3 et supérieur. (#9310, #6897)
* Mise à jour du référentiel commun de données Unicode (CLDR) à la version 40.0. (#12999)
* `NVDA+pavNum effacement` reporte la position du curseur ou de l'objet mis en évidence par défaut. (#13060)
* `NVDA+Maj+pavNum effacement` reporte la position du curseur de revue. (#13060)
* Ajout de gestes par défaut pour basculer les touches de modification sur les afficheurs Freedom Scientific (#13152)
* "Ligne de base" n'est plus annoncé par la commande d'annonce de formatage (`NVDA+f`). (#11815)
* L'annonce de la description longue n'a plus de geste assigné par défaut. (#13380)
* Le report des détails d'un résumé a maintenant un geste par défaut (`NVDA+d`). (#13380)
* NVDA doit être redémarré après l'installation de MathPlayer. (#13486)

### Corrections de bogues

* Le panneau de gestion du presse-papiers ne devrait plus garder incorrectement le focus lors de l'ouverture de certains programmes Office. (#12736)
* Sur les systèmes où l'utilisateur a choisi d'inverser le bouton principal de la souris du gauche au droit, NVDA n'ouvrira plus accidentellement le menu contextuel au lieu d'activer un élément, dans les applications telles que les navigateurs Web. (#12642)
* Lorsque le curseur de revue est déplacé en dehors des contrôles de texte, comme dans Microsoft Word avec UI Automation, "Bas" est maintenant correctement reporté dans plus de situations. (#12808)
* NVDA peut annoncer le nom et la version des exécutables placés dans System32 lorsqu'il est exécuté sur des versions 64 bits de Windows. (#12943)
* Amélioration de la cohérence de la sortie dans les programmes de terminaux. (#12974)
  * Notez que dans certaines situations, lors de l'insertion ou de la suppression de caractères au milieu d'une ligne, le caractère après le curseur pourrait à nouveau être lu.
* MS Word avec UIA : naviguer de titre en titre en mode navigation ne se bloque plus sur le dernier titre du document, et celui-ci n'est plus affiché 2 fois dans la liste des éléments de NVDA. (#9540)
* Sous Windows 8 et supérieur, la barre d'état de l'explorateur de fichiers peut maintenant être lue en utilisant le geste de commande standard NVDA+Fin (ordinateur de bureau) / NVDA+maj+Fin (ordinateur portable). (#12845)
* Les messages entrants dans le chat de Skype for Business sont à nouveau lus. (#9295)
* NVDA peut à nouveau atténuer l'audio lors de l'utilisation du synthétiseur SAPI5 sous Windows 11. (#12913)
* Dans la calculatrice de Windows 10, NVDA annoncera les labels pour l'historique et la liste des éléments de mémoire. (#11858)
* Les gestes tels que le défilement ou le routage fonctionnent à nouveau avec les afficheurs Braille HID. (#13228)
* Courrier pour Windows 11 : Lors de la bascule entre plusieurs applications, pendant la lecture d'un long message, NVDA ne se bloque plus sur une ligne du message. (#13050)
* HID braille : Les gestes multitouches (par exemple `espace+point4`) peuvent maintenant être correctement réalisés sur les afficheurs Braille. (#13326)
* Correction d'un problème où plusieurs dialogues de paramétrage pouvaient être ouverts en même temps. (#12818)
* Correction d'un problème où certains afficheurs Braille Focus Blue pouvaient ne plus fonctionner lorsque l'ordinateur sortait de veille. (#9830)
* "Ligne de base" n'est plus incorrectement reporté lorsque l'annonce des exposants et indices est activée. (#11078)
* Sous Windows 11, NVDA n'empêchera plus la navigation dans le panneau d'emojis lors de la sélection d'emojis. (#13104)
* Correction d'un problème causant une double annonce dans la console et le terminal Windows. (#13261)
* Correction de nombreux problèmes où les éléments de liste n'étaient pas reportés dans les applications 64 bits, comme Reaper. (#8175)
* Dans le gestionnaire de téléchargements de Microsoft Edge, NVDA basculera automatiquement en mode formulaire lorsque la liste avec les téléchargements récents prendra le focus. (#13221)
* NVDA n'entraîne plus le plantage des versions 64 bits de Notepad++ 8.3 et supérieur. (#13311)
* Adobe Reader ne plante plus au démarrage si le mode protégé d'Adobe Reader est activé. (#11568)
* Correction d'un problème où la sélection du pilote Braille Papenmeier faisait planter NVDA. (#13348)
* Dans Microsoft Word avec UIA : le numéro de pages ou d'autres informations de formatage ne sont plus annoncées inutilement lors de la navigation d'une cellule de tableau vide à une cellule avec du contenu, ou de la fin du document vers du contenu. (#13458, #13459)
* NVDA n'échoue plus à signaler le titre de la page et commence à lire automatiquement, lorsqu'une page se charge dans Google chrome 100. (#13571)
* NVDA ne plante plus lors de la réinitialisation des paramètres aux valeurs par défaut avec l'annonce des touches de commande activée. (#13634)

### Changements pour les développeurs

* Remarque : Cette version rompt la compatibilité de l'API des extensions. Les extensions devront être retestées et leur manifeste mis à jour.
* Bien que NVDA nécessite toujours Visual Studio 2019, les builds ne devraient plus échouer si une version plus récente de Visual Studio (par exemple 2022) est installée parallèlement à 2019. (#13033, #13387)
* SCons a été mis à jour à la version 4.3.0. (#13033)
* Mise à jour de py2exe à la version 0.11.1.0. (#12357, #13066)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` a été supprimé. Utilisez `apiLevel` à la place. (#12955, #12660)
* `TVItemStruct` a été supprimé de `sysTreeView32`. (#12935)
* `MessageItem` a été supprimé de l'appModule Outlook. (#12935)
* Les constantes `audioDucking.AUDIODUCKINGMODE_*` sont maintenant une `DisplayStringIntEnum`. (#12926)
  * les utilisations doivent être remplacées par `AudioDuckingMode.*`
  * les utilisations de `audioDucking.audioDuckingModes` doivent être remplacées par `AudioDuckingMode.*.displayString`
* Les utilisations des constantes `audioDucking.ANRUS_ducking_*` doivent être remplacées par `ANRUSDucking.*`. (#12926)
* Changements de `synthDrivers.sapi5` (#12927):
  * Les utilisations de `SPAS_*` doivent être remplacées par `SPAudioState.*`
  * Les utilisations de `constants.SVSF*` doivent être remplacées par `SpeechVoiceSpeakFlags.*`
    * Remarque : `SVSFlagsAsync` doit être remplacé par `SpeechVoiceSpeakFlags.Async` et non `SpeechVoiceSpeakFlags.lagsAsync`
  * Les utilisations de `constants.SVE*` doivent être remplacées par `SpeechVoiceEvents.*`
* Les classes et fonctions suivantes de l'appModule `soffice` sont supprimées : `JAB_OOTableCell`, `JAB_OOTable`, `gridCoordStringToNumbers`. (#12849)
* `core.CallCancelled` devient `exceptions.CallCancelled`. (#12940)
* Toutes les constantes commençant par RPC de `core` et `logHandler` sont déplacées dans l'énumération `RPCConstants.RPC`. (#12940)
* Il est recommandé d'utiliser les fonctions `mouseHandler.doPrimaryClick` et `mouseHandler.doSecondaryClick` pour cliquer sur la souris pour effectuer une action logique telle que l'activation (principale) ou secondaire (afficher le menu contextuel),
plutôt que d'utiliser `executeMouseEvent` et en spécifiant spécifiquement le bouton gauche ou droit de la souris.
Cela garantit que le code respectera le paramètre utilisateur Windows pour intervertir le bouton principal de la souris. (#12642)
* `config.getSystemConfigPath` a été supprimé - il n'y a pas de remplacement. (#12943)
* `shlobj.SHGetFolderPath` a été supprimé - veuillez utiliser `shlobj.SHGetKnownFolderPath` à la place. (#12943)
* Les constantes `shlobj` ont été supprimées. Une nouvelle énumération a été créée, `shlobj.FolderId` à utiliser avec `SHGetKnownFolderPath`. (#12943)
* `diffHandler.get_dmp_algo` et `diffHandler.get_difflib_algo` ont été remplacés par `diffHandler.prefer_dmp` et `diffHandler.prefer_difflib` respectivement. (#12974)
* `languageHandler.curLang` a été supprimé - pour obtenir la langue courante de NVDA, utilisez `languageHandler.getLanguage()`. (#13082)
* Une méthode `getStatusBarText` peut être implémentée dans un appModule pour personnaliser la façon dont NVDA récupère le texte de la barre d'état. (#12845)
* `globalVars.appArgsExtra` a été supprimé. (#13087)
  * Si votre extension a besoin de traiter des arguments de ligne de commande supplémentaires, consultez la documentation de `addonHandler.isCLIParamKnown` et le guide du développeur pour plus de détails.
* Le module UIA handler et d'autres modules de support UIA font désormais partie du package UIAHandler. (#10916)
  * `UIAUtils` devient `UIAHandler.utils`
  * `UIABrowseMode` devient `UIAHandler.browseMode`
  * `_UIAConstants` devient `UIAHandler.constants`
  * `_UIACustomProps` devient `UIAHandler.customProps`
  * `_UIACustomAnnotations` devient `UIAHandler.customAnnotations`
* Les constantes `IA2_RELATION_*` de `IAccessibleHandler` ont été remplacées par l'énumération `IAccessibleHandler.RelationType`. (#13096)
  * Suppression de `IA2_RELATION_FLOWS_FROM`
  * Suppression de  `IA2_RELATION_FLOWS_TO`
  * Suppression de  `IA2_RELATION_CONTAINING_DOCUMENT`
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` et `LOCALE_SLANGDISPLAYNAME` sont supprimés de `languageHandler` - utilisez les membres de `languageHandler.LOCALE` à la place. (#12753)
* Remplacement de Minhook par Microsoft Detours comme bibliothèque de hooking pour NVDA. Le hooking avec cette bibliothèque est principalement utilisé pour le display model. (#12964)
* `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` est supprimé. (#13211)
* SCons avertit désormais de construire avec un nombre de tâches égal au nombre de processeurs logiques du système.
Cela peut réduire considérablement les temps de construction sur les systèmes multicœurs. (#13226, #13371)
* Les constantes `characterProcessing.SYMLVL_*` sont supprimées - veuillez utiliser `characterProcessing.SymbolLevel.*` à la place. (#13248)
* Les fonctions `loadState` et `saveState` sont supprimées de addonHandler - veuillez utiliser `addonHandler.state.load` et `addonHandler.state.save` à la place. (#13245)
* Déplacement de la couche d'interaction UWP/OneCore de NVDAHelper [de C++/CX vers C++/Winrt https://docs.microsoft.com/en-us/windows/uwp/cpp-and-winrt-apis/move-to-winrt](-de-cx). (#10662)
* Il est maintenant obligatoire de créer une sous-classe de `DictionaryDialog` pour l'utiliser. (#13268)
* `config.RUN_REGKEY`, `config.NVDA_REGKEY` sont obsolètes, veuillez utiliser `config.RegistryKey.RUN`, `config.RegistryKey.NVDA` à la place. Ceux-ci seront supprimés en 2023. (#13242)
* `easeOfAccess.ROOT_KEY`, `easeOfAccess.APP_KEY_PATH` sont obsolètes, veuillez utiliser `easeOfAccess.RegistryKey.ROOT`, `easeOfAccess.RegistryKey.APP` à la place. Ceux-ci seront supprimés en 2023. (#13242)
* `easeOfAccess.APP_KEY_NAME` est obsolète et sera supprimé en 2023. (#13242)
* `DictionaryDialog` et `DictionaryEntryDialog` sont déplacés de `gui.settingsDialogs` vers `gui.speechDict`. (#13294)
* Les relations IAccessible2 sont maintenant affichées dans les informations du développeur pour les objets IAccessible2. (#13315)
* `languageHandler.windowsPrimaryLCIDsToLocaleNames` a été supprimé, utilisez `languageHandler.windowsLCIDToLocaleName` ou `winKernel.LCIDToLocaleName` à la place. (#13342)
* L'utilisation de la propriété `UIAAutomationId` pour les objets UIA doit être préférée à `cachedAutomationId`. (#13125, #11447)
  * `cachedAutomationId` peut être utilisé s'il est obtenu directement à partir de l'élément.
* `NVDAObjects.window.scintilla.CharacterRangeStruct` a été déplacé vers `NVDAObjects.window.scintilla.Scintilla.CharacterRangeStruct`. (#13364)
* Le booléen `gui.isInMessageBox` est supprimé, veuillez utiliser la fonction `gui.message.isModalMessageBoxActive` à la place. (#12984, #13376)
* `controlTypes` a été divisé en plusieurs sous-modules. (#12510 #13588)
  * `ROLE_*` et `STATE_*` ont été remplacés par `Role.*` et `State.*`.
  * Bien que toujours disponibles, les éléments suivants doivent être considérés comme obsolètes :
    * `ROLE_*` et `STATE_*`, remplacés par `Role.*` et `State.*`.
    * `roleLabels`, `stateLabels` et `negativeStateLabels`, les utilisations telles que `roleLabels[ROLE_*]` doivent être remplacées par leur équivalent `Role.*.displayString` ou `State. *.negativeDisplayString`.
    * `processPositiveStates` et `processNegativeStates` remplacés par `processAndLabelStates`.
* Les constantes d'état des cellules Excel (`NVSTATE_*`) sont maintenant des valeurs dans l'énumération `NvCellState`, reflétées dans l'énumération `NvCellState` dans `NVDAObjects/window/excel.py` et mappées à `controlTypes.State` via _nvCellStatesToStates. (#13465)
* `EXCEL_CELLINFO` struct membre `state` est maintenant `nvCellStates`.
* `mathPres.ensureInit` a été supprimé, MathPlayer est maintenant initialisé au démarrage de NVDA. (#13486)

## 2021.3.5

Cela est une version mineure pour corriger plusieurs problèmes de sécurité découverts.
Veuillez signaler de manière responsable les problèmes de sécurité à <info@nvaccess.org>.

### Corrections de sécurité

* Correction pour l'avis de sécurité `GHSA-xc5m-v23f-pgr7`.
  * Le dialogue prononciation des symboles est maintenant désactivé en mode sécurisé.

## 2021.3.4

Cela est une version mineure pour corriger plusieurs problèmes de sécurité découverts.
Veuillez signaler de manière responsable les problèmes de sécurité à <info@nvaccess.org>.

### Corrections de sécurité

* Correction pour l'avis de sécurité `GHSA-354r-wr4v-cx28`. (#13488)
  * Suppression de la possibilité de démarrer NVDA avec le mode débodage actif lors de l'utilisation de NVDA en mode sécurisé.
  * Suppression de la possibilité de mettre à jour NVDA lorsqu'il s'exécute en mode sécurisé.
* Correction pour l'avis de sécurité `GHSA-wg65-7r23-h6p9`. (#13489)
  * Suppression de la possibilité d'ouvrir le gestionnaire de commandes en mode sécurisé.
  * Suppression de la possibilité d'ouvrir les dialogues de dictionnaires par défaut, temporaires et de la voix en mode sécurisé.
* Correction pour l'avis de sécurité `GHSA-mvc8-5rv9-w3hx`. (#13487)
  * L'outil wx GUI inspection est maintenant désactivé en mode sécurisé.

## 2021.3.3

Cette version est identique à la 2021.3.2.
Un problème était présent dans NVDA 2021.3.2, causant cette version à s'identifier elle-même comme version 2021.3.1.
Cette version s'identifie correctement comme 201.3.3.

## 2021.3.2

Cela est une version mineure pour corriger plusieurs problèmes de sécurité découverts.
Veuillez signaler de manière responsable les problèmes de sécurité à <info@nvaccess.org>.

### Corrections de bogues

* Correction de sécurité : Empêche la navigation par objets hors de l'écran de verrouillage sous Windows 10 et 11. (#13328)
* Correction de sécurité : Le dialogue gestion des extensions est maintenant désactivé sur les écrans sécurisés. (#13059)
* Correction de sécurité : L'aide contextuelle de NVDA n'est plus disponible sur les écrans sécurisés. (#13353)

## 2021.3.1

Version mineure pour résoudre plusieurs problèmes dans la version 2021.3.

### Changements

* Le nouveau protocole HID Braille n'est plus privilégié lorsqu'un autre pilote d'afficheur braille peut être utilisé. (#13153)
* Le nouveau protocole HID Braille peut être désactivé via un paramètre dans le panneau des paramètres avancés. (#13180)

### Corrections de Bogues

* Région est à nouveau abrégé en braille. #13158
* Correction de la détection automatique de l'afficheur braille instable pour les afficheurs braille Humanware Brailliant et APH Mantis Q40 lors de l'utilisation de Bluetooth. (#13153)

## 2021.3

Cette version introduit le support de la nouvelle spécification Braille HID.
Cette spécification entend standardiser le support des afficheurs Braille sans nécessiter de pilotes individuels.
eSpeak et Liblouis ont été mis à jour, incluant de nouvelles tables Braille Russe et Tshivenda.
Le son d'erreur peut être activé dans les versions stables de NVDA via un nouveau paramètre avancé.
Dire tout dans Word fait maintenant défiler le document afin de garder la position actuelle visible.
Sont également présentes de nombreuses améliorations lors de l'utilisation d'Office avec UIA.
Un des correctifs UIA est qu'Outlook ignore maintenant plus de tableaux de disposition dans les messages.

Notes importantes :

En raison d'une mise à jour de notre certificat de sécurité, un petit nombre d'utilisateurs rencontre une erreur lorsque NVDA 2021.2 vérifie les mises à jour.
NVDA demande maintenant à Windows de mettre à jour les certificats de sécurité, ce qui évitera ce type d'erreurs dans le futur.
Les utilisateurs affectés devront télécharger cette mise à jour manuellement.

### Nouvelles fonctionnalités

* Ajout d'un geste de commande pour basculer le paramètre d'annonce du style des bordures de cellules. (#10408)
* Support de la nouvelle spécification Braille HID qui a pour but de standardiser le support des afficheurs Braille. (#12523)
  * Les terminaux qui supportent cette spécification seront détectés automatiquement par NVDA.
  * Pour les détails techniques sur l'implémentation de cette spécification dans NVDA, voir https://github.com/nvaccess/nvda/blob/master/devDocs/hidBrailleTechnicalNotes.md
* Ajout du support du terminal Braille VisioBraille Vario 4. (#12607)
* Les notifications d'erreur peuvent être activées (paramètres avancés) lors de l'utilisation de toutes les versions de NVDA. (#12672)
* Sous Windows 10 et supérieur, NVDA annoncera le nombre de suggestions lors de la saisie de termes de recherche dans des applications telles que les paramètres ou le Microsoft Store. (#7330, #12758, #12790)
* La navigation dans les tableaux est désormais prise en charge dans les contrôles de grille créés à l'aide de l'applet de commande Out-GridView dans PowerShell. (#12928)

### Changements

* Espeak-ng a été mis à jour en version 1.51-dev révision `74068b91bcd578bd7030a7a6cde2085114b79b44`. (#12665)
* NVDA basculera sur eSpeak si aucune voix OneCore installée ne supporte la langue sélectionnée dans NVDA. (#10451)
* Si les voix OneCore échouent constamment à parler, NVDA basculera sur le synthétiseur eSpeak. (#11544)
* Lors de la lecture de la barre d'état par `NVDA+Fin`, le curseur de revue n'est plus déplacé vers son emplacement.
Si vous souhaitez cette fonctionnalité, veuillez assigner un geste au script approprié dans la rubrique "Navigation par objet" du dialogue "Gestes de commandes". (#8600)
* Lors de l'ouverture d'un dialogue de paramétrage déjà ouvert, NVDA donne le focus au dialogue ouvert au lieu de retourner une erreur. (#5383)
* Mise à jour du transcripteur Braille Liblouis en version [3.19.0](https://github.com/liblouis/liblouis/releases/tag/v3.19.0). (#12810)
  * Nouvelles tables Braille : Russe intégral, Tshivenda intégral, Tshivenda abrégé
* Au lieu de "contenu marqué" ou "mrq", "surligné" ou "mrq" sera annoncé vocalement et en Braille respectivement. (#12892)
* NVDA n'essaiera plus de se fermer lorsqu'une boîte de dialogue requière une action (par exemple Confirmer ou Annuler). (#12984)

### Corrections de bogues

* Le suivi des modificateurs clavier (tels que CTRL, ou Insert) est plus robuste lors de la récupération par le superviseur. (#12609)
* Il est à nouveau possible de vérifier les mises à jour de NVDA sur certains systèmes. Par exemple les nouvelles installations de Windows. (#12729)
* NVDA annonce correctement les cellules de tableau vides lors de l'utilisation de UI Automation dans Microsoft Word. (#11043)
* Dans les cellules de grille de données ARIA sur le web, la touche échap sera maintenant transmise à la grille et ne désactivera plus le mode formulaire inconditionnellement. (#12413)
* Lors de la lecture d'une cellule d'en-tête d'un tableau sous Chrome, correction du nombre de colonnes annoncé deux fois. (#10840)
* NVDA ne reporte plus une valeur numérique pour les potentiomètres UIA qui ont une représentation textuelle de leur valeur définie (UIA ValuePattern est maintenant préféré à RangeValuePattern). (#12724)
* NVDA ne traite plus la valeur des potentiomètres UIA comme étant toujours basée sur un pourcentage.
* Le report de la position d'une cellule dans Microsoft Excel lors de l'utilisation avec UI Automation fonctionne à nouveau correctement sous Windows 11. (#12782)
* NVDA ne définit plus incorrectement la langue dans Python. (#12753)
* Si une extension désactivée est désinstallée puis réinstallée, elle est réactivée. (#12792)
* Correction de bugs lors de la mise à jour ou de la suppression d'une extension si le dossier de l'extension a été renommé ou contient des fichiers ouverts. (#12792, #12629)
* Lors de l'utilisation de UI Automation pour accéder aux feuilles de calcul Microsoft Excel, NVDA n'annonce plus de manière redondante si une seule cellule est sélectionnée. (#12530)
* Le texte de plus de dialogues est automatiquement lu dans LibreOffice Writer, comme dans les dialogues de confirmation. (#11687)
* Lire/naviguer en mode navigation dans Microsoft Word via UI automation s'assure maintenant toujours du défilement du document, que la position actuelle du mode navigation soit visible, et que la position du mode en mode formulaire reflète la position du mode navigation. (#9611)
* Lors de l'utilisation du mode dire tout dans Microsoft Word via UI automation, le document défile maintenant automatiquement, et la position du curseur est correctement mise à jour. (#9611)
* Lors de la lecture d'e-mails dans Outlook quand NVDA accède aux message en utilisant UI Automation, certains tableaux sont maintenant marqués comme tableau de disposition, et ne seront donc plus annoncés par défaut. (#11430)
* Une erreur rare lors du changement de périphérique audio a été résolue. (#12620)
* La saisie avec des tables Braille littéraires devrait être plus fiable dans les champs d'édition. (#12667)
* Lors de la navigation dans le calendrier de la zone de notifications Windows, NVDA annonce maintenant le jour de la semaine en intégralité. (#12757)
* Lors de l'utilisation d'une méthode de saisie chinoise telle que Taïwan - Microsoft Quick dans Microsoft Word, le défilement du Braille vers l'avant et l'arrière ne revient plus à la position initiale du curseur. (# 12855)
* Lors de l'accès aux documents Microsoft Word via UIA, naviguer par phrase (alt+flèche bas / alt+flèche haut) est à nouveau possible. (#9254)
* Lors de l'accès à MS Word avec UIA, l'indentation des paragraphes est maintenant annoncée. (#12899)
* Lors de l'accès à MS Word avec UIA, la commande de suivi des modifications et d'autres commandes localisées sont maintenant reportées dans Word. (#12904)
* Correction d'un doublon en Braille et vocal quand 'description' est identique 'content' ou 'name'. (#12888)
* Dans MS Word avec UIA activé, la génération du son d'erreur d'orthographe lors de la frappe est plus fiable. (#12161)
* Sous Windows 11, NVDA n'annoncera plus "volet" lors de l'appui sur Alt+Tab pour circuler entre les programmes. (#12648)
* Le nouveau volet latéral des commentaires modernes est désormais pris en charge dans MS Word lorsque vous n'accédez pas au document via UIA. Appuyez sur Alt+F12 pour naviguer entre le volet latéral et le document. (#12982)

### Changements pour les Développeurs

* La compilation de NVDA requiert maintenant Visual Studio 2019 16.10.4 ou supérieur.
Pour correspondre à l'environnement de compilation de production, mettez à jour Visual Studio pour rester synchronisé avec la [version actuellement utilisée par AppVeyor](https://www.appveyor.com/docs/windows-images-software/#visual-studio-2019). (#12728)
* `NVDAObjects.UIA.winConsoleUIA.WinConsoleUIA.isImprovedTextRangeAvailable` a été rendu obsolète pour suppression dans NVDA 2022.1. (#12660)
  * Utiliser `apiLevel` à la place (voir les commentaires dans `_UIAConstants.WinConsoleAPILevel` pour les détails).
* La transparence de la couleur d'arrière-plan du texte provenant des applications GDI (via le modèle d'affichage) est désormais exposée pour les extensions ou les appModules. (#12658)
* `LOCALE_SLANGUAGE`, `LOCALE_SLIST` et `LOCALE_SLANGDISPLAYNAME` ont été déplacés vers l'enum `LOCALE` dans languageHandler.
Ils sont toujours disponibles au niveau du module mais sont obsolètes et seront supprimés dans NVDA 2022.1. (#12753)
* L'utilisation des fonctions `addonHandler.loadState` et `addonHandler.saveState` doit être remplacée par leurs équivalents `addonHandler.state.save` et `addonHandler.state.load` avant NVDA 2022.1. (#12792)
* La sortie Braille peut maintenant être vérifiée dans les tests système. (#12917)

## 2021.2

Cette version intègre un support préliminaire de Windows 11.
Comme Windows 11 n'est pas encore publié, cette version a été testée sur des versions béta de Windows 11.
Cela inclut un correctif important pour le rideau d'écran (voir notes importantes).
L'outil de correction des inscriptions COM peut maintenant résoudre plus de problèmes lors de l'exécution de NVDA.
Des mises à jour du synthétiseur eSpeak et du transcripteur Braille Liblouis sont présentes.
Il y a également beaucoup de correctifs et améliorations, notamment pour le support du Braille, le terminal Windows, la calculatrice, le panneau d'emojis et l'historique du presse-papiers.

### Notes importantes

En raison d'un changement dans l'API d'agrandissement de Windows, le rideau d'écran a dû être mis à jour pour supporter les nouvelles versions de Windows.
Utilisez NVDA 2021.2 pour activer le rideau d'écran sous Windows 10 21H2 (10.0.19044) ou supérieur.
Cela inclut Windows 10 Insiders et Windows 11.
Pour des raisons de sécurité, lors de l'utilisation d'une nouvelle version de Windows, veuillez obtenir une confirmation visuelle que le rideau d'écran rend l'écran entièrement noir.

### Nouvelles fonctionnalités

* Support expérimental des annotations ARIA :
  * ajout d'une commande pour lire le résumé d'un objet comportant des détails avec aria-details. (#12364)
  * ajout d'une option dans les paramètres avancés pour annoncer si un objet contient des détails en mode navigation. (#12439)
* Sous Windows 10 version 1909 et supérieures (Windows 11 y compris), NVDA annoncera le nombre de suggestions lors d'une recherche dans l'explorateur de fichiers. (#10341, #12628)
* Sous Microsoft Word, NVDA annonce maintenant le résultat des raccourcis clavier de retrait et de retrait négatif lors de leur exécution. (#6269)

### Changements

* Espeak-ng a été mis à jour à la version 1.51-dev révision `ab11439b18238b7a08b965d1d5a6ef31cbb05cbb`. (#12449, #12202, #12280, #12568)
* Si "Article" est activé dans le dialogue de "Mise en forme des documents", NVDA annonce maintenant "Article" après le contenu. (#11103)
* Mise à jour du transcripteur Braille Liblouis à la version [3.18.0](https://github.com/liblouis/liblouis/releases/tag/v3.18.0). (#12526)
  * Nouvelles tables Braille : Bulgare intégral, Birman intégral, Birman abrégé, kazakhe intégral, khmer intégral, Kurde du Nord grade 0, Sepedi intégral, Sepedi abrégé, Sésotho intégral, Sésotho abrégé, Setswana intégral, Setswana abrégé, Tatare intégral, Vietnamien grade 0, Vietnamien abrégé, Vietnamien du sud intégral, Xhosa intégral, Xhosa abrégé, Yakoute intégral, Zoulou intégral, Zoulou abrégé
* "Reconnaissances optique de caractères de Windows 10" a été renommé en "Reconnaissance optique de caractères de Windows". (#12690)

### Corrections de bogues

* Dans la calculatrice de Windows 10, NVDA affichera l'expression d'un calcul sur les afficheurs Braille. (#12268)
* Dans les programmes de terminal sous Windows 10 version 1607 et au-delà, lors de l'insertion ou de la suppression d'un caractère au milieu d'une ligne, le caractère à droite du curseur n'est plus lu. (#3200)
  * Diff Match Patch est maintenant activé par défaut. (#12485)
* La saisie Braille fonctionne correctement avec les tables abrégées suivantes : Arabe abrégé, Espagnol abrégé, Urdu abrégé, Chinois (Chine, Mandarin) abrégé. (#12541)
* L'outil de correction des enregistrements COM résout maintenant davantage de problèmes, particulièrement sous les versions 64 bits de Windows. (#12560)
* Amélioration de la gestion des boutons pour l'afficheur Braille Seika Notetaker de Nippon Telesoft. (#12598)
* Améliorations dans l'annonce du panneau d'emojis Windows et l'historique du presse-papiers. (#11485)
* Mise à jour de la description des caractères pour l'alphabet Bengali. (#12502)
* NVDA se ferme proprement lorsqu'un nouveau processus est démarré. (#12605)
* Resélectionner le pilote d'afficheur Braille Handy Tech depuis le dialogue "Sélectionner un afficheur Braille" ne cause plus d'erreur. (#12618)
* Windows version 10.0.22000 ou supérieur est reconnu comme Windows 11, et non Windows 10. (#12626)
* Le support du rideau d'écran a été corrigé et testé pour les versions de Windows jusqu'à 10.0.22000. (#12684)
* Si aucun résultat n'est affiché lors du filtrage dans les gestes de commandes, le dialogue de configuration des gestes de commandes continu de fonctionner correctement. (#12673)
* Correction d'un bogue où le premier élément de menu d'un sous-menu n'était pas annoncé dans certains cas. (#12624)

### Changements pour les Développeurs

* L'utilisation des constantes `characterProcessing.SYMLVL_*` devra être remplacée par leur équivalent `SymbolLevel.*` avant 2022.1. (#11856, #12636)
* `controlTypes` a été séparé en plusieurs sous-modules, les symboles marqués comme dépréciés devront être remplacés avant 2022.1. (#12510)
  * Les constantes `ROLE_*` et `STATE_*` devront être remplacées par leurs équivalents `Role.*` et `State.*`.
  * `roleLabels`, `stateLabels` et `negativeStateLabels` ont été dépréciés, des usages tel que `roleLabels[ROLE_*]` devront être remplacés par leurs équivalents `Role.*.displayString` ou `State.*.negativeDisplayString`.
  * `processPositiveStates` et `processNegativeStates` ont été dépréciés pour suppression.
* Sous Windows 10 version 1511 et au-delà (builds insider y compris), le nom de la mise à jour de fonctionnalités actuelle est obtenu depuis le registre. (#12509)
* Déprécié : `winVersion.WIN10_RELEASE_NAME_TO_BUILDS` sera supprimé dans 2022.1, sans remplaçant direct. (#12544)

## 2021.1

Cette version inclut un support expérimental d'UIA dans Microsoft Excel et les navigateurs basés sur Chromium.
Elle contient également des correctifs pour de nombreuses langues, et pour l'accès aux liens en Braille.
Des mises à jour de la base CLDR, des symboles mathématiques, et de Liblouis.
Comme toujours de nombreux correctifs et améliorations, y compris pour Office, Visual Studio, et pour de nombreuses langues.

Note :

 * Cette version rompt la compatibilité avec les extensions existantes.
 * Cette version interrompt également le support d'Adobe Flash.

### Nouvelles fonctionnalités

* Support initial d'UIA dans les navigateurs basés sur Chromium (tel que Edge). (#12025)
* Support expérimental optionnel de Microsoft Excel via UIAutomation. Recommandé uniquement pour Microsoft Excel version 16.0.13522.10000 ou supérieur. (#12210)
* Facilité de navigation dans l'affichage de la console Python de NVDA. (#9784)
  * alt+haut/bas amène au résultat précédent/suivant (ajouter maj pour sélectionner).
  * CTRL+L vide le volet d'affichage.
* NVDA reporte maintenant les catégories auxquelles un rendez-vous est assigné dans Microsoft Outlook, s'il y en a. (#11598)
* Prise en charge de l'afficheur braille Seika Notetaker de Nippon Telesoft. (#11514)

### Changements

* En mode navigation, les contrôles peuvent maintenant être activés sur leurs descripteurs en utilisant les curseurs éclair d'un afficheur Braille (par exemple ln pour un lien). Ceci est particulièrement utile sur les cases à cocher sans label par exemple. (#7447)
* NVDA empêche maintenant l'utilisateur d'exécuter la reconnaissance optique de caractères de Windows 10 quand le rideau d'écran est actif. (#11911)
* Mise à jour du référentiel commun de données Unicode (CLDR) à la version 39.0. (#11943, #12314)
* Ajout de plusieurs symboles mathématiques au dictionnaire de symboles. (#11467)
* Le guide utilisateur, la liste de changements et le résumé des commandes ont maintenant une apparence révisée. (#12027)
* "Non supporté" est maintenant annoncé lorsque vous essayez de changer la disposition de l'écran dans des applications ne le supportant pas, comme Microsoft Word. (#7297)
* Dans les paramètres avancés, l'option "Essayer de couper la parole pour les événements de focus expirés" est maintenant activée par défaut. (#10885)
  * Ce comportement peut être désactivé en définissant cette option sur "Non".
  * Les applications Web, comme GMail, n'annoncent plus d'informations erronées lors du déplacement rapide du focus.
* Mise à jour du transcripteur Braille Liblouis à la version [3.17.0](https://github.com/liblouis/liblouis/releases/tag/v3.17.0). (#12137)
  * Nouvelles tables Braille: Bélarusse Braille littéraire, Bélarusse Braille informatique, Urdu intégral, Urdu abrégé.
* Le support des contenus flash a été supprimé de NVDA en raison de l'utilisation de flash déconseillée par Adobe. (#11131)
* On pourra maintenant quitter NVDA même avec des fenêtres ouvertes, le processus de fermeture ferme maintenant toutes les fenêtres et dialogues de NVDA. (#1740)
* La visionneuse de parole peut maintenant être fermée par `alt+F4` et contient un bouton de fermeture standard pour les utilisateurs de périphériques de pointage. (#12330)
* La visionneuse Braille a maintenant un bouton de fermeture standard pour les utilisateurs de périphériques de pointage. (#12328)
* Dans la liste d'éléments, la touche accélératrice du bouton "Activer" a été retirée dans certaines langues afin d'éviter un conflit avec le type d'élément "Bouton radio". Quand il est disponible, le bouton est toujours celui par défaut pour le dialogue et peut donc être activé simplement en appuyant sur entrée dans la liste d'éléments elle-même. (#6167)

### Corrections de bogues

* La liste de messages dans Outlook 2010 est à nouveau lisible. (#12241)
* Dans les programmes de terminal sous Windows 1607 et supérieur, lors de l'insertion ou de la suppression d'un caractère au milieu d'une ligne, le caractère à droite du curseur n'est plus annoncé. (#3200)
  * Ce correctif expérimental doit être manuellement activé dans les paramètres avancés de NVDA en changeant l'algorithme de diff pour "Autoriser diff Match Patch".
* Dans Microsoft Outlook, une distance n'est plus annoncée de manière inappropriée lors de la navigation entre le corps et le sujet d'un mail avec maj+tab. (#10254)
* Dans la console Python, insérer une tabulation pour l'indentation en début d'une ligne non vide et utiliser l'autocomplétion en milieu de ligne est maintenant supporté. (#11532)
* Les informations de mise en forme et les autres messages navigables ne comportent plus de ligne vide non souhaitée à leur fin lorsque la disposition de l'écran est désactivée. (#12004)
* Il est maintenant possible de lire les commentaires dans Microsoft Word avec UIA activé. (#9285)
* Les performances lors de l'interaction avec Visual Studio ont été améliorées. (#12171)
* Corrections de problèmes graphiques comme l'absence d'un élément lors de l'utilisation de NVDA avec une disposition de droite à gauche. (#8859)
* Respect de la disposition de l'interface graphique en se basant sur la langue de NVDA plutôt que celle du système. (#638)
  * problème connu pour les langues de droite à gauche : la bordure droite des groupes d'éléments masque une partie des labels des contrôles. (#12181)
* La langue de Python est définie pour toujours respecter la langue des préférences et devrait maintenant utiliser la langue par défaut. (#12214)
* TextInfo.getTextInChunks ne plante plus lorsqu'appelé dans des contrôles d'édition riches comme la visionneuse du journal. (#11613)
* Il est à nouveau possible d'utiliser NVDA avec des langues contenant des soulignements dans leur nom comme de_CH sous Windows 10 1803 et 1809. (#12250)
* Dans WordPad, la configuration de l'annonce des exposants et indices fonctionne maintenant comme attendu. (#12262)
* NVDA n'échoue plus à lire le nouveau contenu sous le curseur sur une page Web si l'ancien contenu disparaît et est remplacé par le nouveau à la même place. (#12147)
* Le formatage barré, exposant et indice est maintenant correctement renvoyé pour des cellules Excel entières si les options correspondantes sont activées. (#12264)
* Correction de la copie de la configuration pendant l'installation depuis une version portable si le dossier de configuration par défaut est vide. (#12071, #12205)
* Correction de l'annonce de certaines lettres avec accent ou diacritique quand l'option "Dire majuscule avant les majuscules" est cochée. (#11948)
* Correction du changement de hauteur pour les majuscules avec le synthétiseur SAPI4. (#12311)
* Le programme d'installation de NVDA respecte maintenant l'argument de ligne de commande `--minimal` et ne joue plus le son de démarrage, suivant le même comportement que celui documenté pour l'exécutable d'une version portable ou installée de NVDA. (#12289)
* Dans Microsoft Word ou Outlook, les commandes de navigation de tableau permettent maintenant d'amener à la table de visualisation suivante ou précédente si l'option "Inclure les tables de visualisation" est cochée dans les paramètres du mode navigation. (#11899)
* NVDA n'annoncera plus "↑↑↑" pour les emojis dans certaines langues. (#11963)
* Espeak supporte à nouveau le Cantonais et le Mandarin. (#10418)
* Dans le nouveau Microsoft Edge basé sur Chromium, les zones de texte comme la barre d'adresse sont maintenant annoncées lorsqu'elles sont vides. (#12474)
* Correction du pilote Braille Seika. (#10787)

### Changements pour les développeurs

* Remarque : Cette version rompt la compatibilité de l'API des extensions. Les extensions devront être retestées et leur manifeste mis à jour.
* Le système de construction de NVDA récupère désormais toutes les dépendances Python avec pip et les stocke dans un environnement virtuel Python. Tout cela est fait de manière transparente.
  * Pour construire NVDA, SCons doit continuer à être utilisés de la manière habituelle. Par exemple. exécuter scons.bat à la racine du dépôt. L'exécution de `py -m SCons` n'est plus prise en charge, et `scons.py` a également été supprimé.
  * Pour exécuter NVDA à partir des sources, plutôt que d'exécuter directement `source/nvda.pyw`, le développeur doit maintenant utiliser `runnvda.bat` à la racine du dépôt. Si vous essayez d'exécuter `source/nvda.pyw`, une boîte de message vous avertira que ce n'est plus supporté.
  * Pour effectuer des tests unitaires, exécutez `rununittests.bat [<options de découverte unittest additionnelles>]`
  * Pour effectuer des tests système : exécutez `runsystemtests.bat [<options robot additionnelles>]`
  * Pour effectuer le linting, exécutez `runlint.bat <branche de base>`
  * Veuillez consulter readme.md pour plus de détails.
* Les dépendances Python suivantes ont également été mises à niveau :
  * comtypes mis à jour à la version 1.1.8.
  * pySerial mis à jour à la version 3.5.
  * wxPython mis à jour vers la version 4.1.1.
  * Py2exe mis à jour à la version 0.10.1.0.
* `LiveText._getTextLines` a été supprimé. (#11639)
  * Au lieu de cela, remplacez `_getText` qui renvoie une chaîne contenant tout le texte de l'objet.
* Les objets `LiveText` peuvent désormais calculer les différences par caractère. (#11639)
  * Pour modifier le comportement de diff pour certains objets, remplacez la propriété `diffAlgo` (voir la docstring pour plus de détails).
* Lors de la définition d'un script avec le décorateur de script, l'argument booléen 'allowInSleepMode' peut être spécifié pour contrôler si un script est disponible en mode veille ou non. (#11979)
* Les fonctions suivantes sont supprimées du module config. (#11935)
  * canStartOnSecureScreens - utilisez config.isInstalledCopy à la place.
  * hasUiAccess et execElevated - utilisez-les depuis le module systemUtils.
  * getConfigDirs - utilisez globalVars.appArgs.configPath à la place.
* Les constantes REASON_ * définies au niveau du module sont supprimées de controlTypes - veuillez utiliser controlTypes.OutputReason à la place. (#11969)
* REASON_QUICKNAV a été supprimé de BrowseMode - utilisez controlTypes.OutputReason.QUICKNAV à la place . (#11969)
* La propriété `isCurrent` de `NVDAObject` (et ses dérivés) renvoie désormais strictement la classe d'énumération `controlTypes.IsCurrent`. (#11782)
  * `isCurrent` n'est plus optionnel et ne retournera donc pas None.
    * Lorsqu'un objet n'est pas le courant, `controlTypes.IsCurrent.NO` est renvoyé.
* Le dictionnaire `controlTypes.isCurrentLabels` a été supprimé. (#11782)
  * A la place, utilisez la propriété `displayString` sur une valeur d'énumération `controlTypes.IsCurrent`.
    * Par exemple `controlTypes.IsCurrent.YES.displayString`
* `winKernel.GetTimeFormat` a été supprimé - utilisez `winKernel.GetTimeFormatEx` à la place. (#12139)
* `winKernel.GetDateFormat` a été supprimé - utilisez `winKernel.GetDateFormatEx` à la place. (#12139)
* `gui.DriverSettingsMixin` a été supprimé - utilisez `gui.AutoSettingsMixin`. (#12144)
* `speech.getSpeechForSpelling` a été supprimé - utilisez `speech.getSpellingSpeech`. (#12145)
* Les commandes ne peuvent pas être directement importées depuis speech de la façon suivante: `import speech; speech.ExampleCommand ()` ou `import speech.manager; speech.manager.ExampleCommand()` - utilisez `from speech.commands import ExampleCommand` à la place. (#12126)
* `speakTextInfo` n'enverra plus de parole via `speakWithoutPauses` si la raison est `SAYALL`, vu que `SayAllHandler` le fait maintenant manuellement. (#12150)
* Le contenu du module `synthDriverHandler` n'est plus importée globalement dans `globalCommands` et `gui.settingsDialogs` - utilisez `from synthDriverHandler import synthFunctionExample` à la place. (#12172)
* `ROLE_EQUATION` a été supprimé de controlTypes - utilisez `ROLE_MATH` à la place. (#12164)
* Les classes `autoSettingsUtils.driverSetting` sont supprimées de `driverHandler` - veuillez les utiliser depuis `autoSettingsUtils.driverSetting`. (#12168)
* Les classes `autoSettingsUtils.utils` sont supprimées de `driverHandler` - veuillez les utiliser depuis `autoSettingsUtils.utils`. (#12168)
* La prise en charge des `TextInfo` qui n'héritent pas de `contentRecog.BaseContentRecogTextInfo` est supprimée. (#12157)
* `speech.speakWithoutPauses` a été supprimé - veuillez utiliser `speech.speechWithoutPauses.SpeechWithoutPauses(speakFunc=speech.speak).speakWithoutPauses` à la place. (#12195, #12251)
* `speech.re_last_pause` a été supprimé - veuillez utiliser `speech.speechWithoutPauses.SpeechWithoutPauses.re_last_pause` à la place. (#12195, #12251)
* `WelcomeDialog`, `LauncherDialog` et `AskAllowUsageStatsDialog` sont déplacés vers le module `gui.startupDialogs`. (#12105)
* `getDocFilePath` a été déplacé de `gui` vers le module `documentationUtils`. (#12105)
* Le module gui.accPropServer ainsi que les classes AccPropertyOverride et ListCtrlAccPropServer du module gui.nvdaControls ont été supprimés au profit de la prise en charge native de WX pour le remplacement des propriétés d'accessibilité. Si vous voulez améliorer l'accessibilité des contrôles WX, implémentez wx.Accessible à la place. (#12215)
* Les fichiers dans `source/comInterfaces/` sont désormais plus facilement consommables par les outils de développement tels que les IDE. (#12201)
* Des méthodes et des types ont été ajoutés au module winVersion pour faciliter l'obtention et la comparaison des versions de Windows. (#11909)
  * La fonction isWin10 située dans le module winVersion a été supprimée.
  * la classe winVersion.WinVersion est un type comparable et pouvant être classé encapsulant les informations de version de Windows.
  * La fonction winVersion.getWinVer a été ajoutée pour obtenir une winVersion.WinVersion représentant le système d'exploitation en cours d'exécution.
  * Des constantes ont été ajoutées pour les versions Windows connues, voir les constantes winVersion.WIN*.
* IAccessibleHandler n'importe plus tout depuis les interfaces IAccessible et IA2 COM - veuillez les utiliser directement. (#12232)
* Les objets TextInfo ont maintenant des propriétés de début et de fin qui peuvent être comparées mathématiquement avec des opérateurs tels que < <= == != >= >. (#11613)
  * Par exemple ti1.start <= ti2.end
  * Cette utilisation est désormais préférée à ti1.compareEndPoints(ti2, "startToEnd") <= 0
* Les propriétés start et end de TextInfo peuvent également être définies l'une à partir de l'autre. (#11613)
  * Par exemple ti1.start = ti2.end
  * Cette utilisation est préférée à ti1.SetEndPoint(ti2, "startToEnd")
* `wx.CENTRE_ON_SCREEN` et `wx.CENTRE_ON_SCREEN` sont supprimés, utilisez `self.CentreOnScreen()` à la place. (#12309)
* `easeOfAccess.isSupported` a été supprimé, NVDA ne prend en charge que les versions de Windows où cette valeur est évaluée à `True`. (#12222)
* `sayAllHandler` a été déplacé vers `speech.sayAll`. (#12251)
  * `speech.sayAll.SayAllHandler` expose les fonctions `stop`, `isRunning`, `readObjects`, `readText`, `lastSayAllMode`.
  * `SayAllHandler.stop` réinitialise également l'instance `SpeechWithoutPauses` de `SayAllHandler`.
  * `CURSOR_REVIEW` et `CURSOR_CARET` ont été remplacés par `CURSOR.REVIEW` et `CURSOR.CARET`.
* `speech.SpeechWithoutPauses` a été déplacé vers `speech.speechWithoutPauses.SpeechWithoutPauses`. (#12251)
* `speech.curWordChars` a été renommé `speech._curWordChars`. (#12395)
* les éléments suivants ont été supprimés de `speech` et sont accessibles via `speech.getState()`. Ce sont maintenant des valeurs en lecture seule. (#12395)
  * speechMode
  * speechMode_beeps_ms
  * beenCanceled
  * isPaused
* pour mettre à jour `speech.speechMode`, utilisez `speech.setSpeechMode`. (#12395)
* les éléments suivants ont été déplacés vers `speech.SpeechMode`. (#12395)
  * `speech.speechMode_off` devient `speech.SpeechMode.off`
  * `speech.speechMode_beeps` devient `speech.SpeechMode.beeps`
  * `speech.speechMode_talk` devient `speech.SpeechMode.talk`
* `IAccessibleHandler.IAccessibleObjectIdentifierType` devient désormais `IAccessibleHandler.types.IAccessibleObjectIdentifierType`. (#12367)
* Les éléments suivants dans `NVDAObjects.UIA.WinConsoleUIA` ont été modifiés (#12094)
  * `NVDAObjects.UIA.winConsoleUIA.is21H1Plus` renommé `NVDAObjects.UIA.winConsoleUIA.isImprovedTextRangeAvailable`.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfo` renommé pour que le nom de classe commence par une majuscule.
  * `NVDAObjects.UIA.winConsoleUIA.consoleUIATextInfoPre21H1` renommé `NVDAObjects.UIA.winConsoleUIA.ConsoleUIATextInfoWorkaroundEndInclusive`
    * L'implementation définit une solution alternative au fait que les deux extrémités sont incluses (dans les plages de texte) avant [microsoft/terminal PR 4018](https://github.com/microsoft/terminal/pull/4018)
    * Solutions alternatives pour `expand`, `collapse`, `compareEndPoints`, `setEndPoint`, etc

## 2020.4

Cette version inclut le support de nouvelles méthodes d'entrée chinoises, une mise à jour de Liblouis, et la liste d'éléments (NVDA+F7) fonctionne maintenant en mode formulaire.
Une aide contextuelle est maintenant disponible lors de l'appui sur F1 dans les dialogue NVDA.
Améliorations pour les règles de prononciation, les dictionnaires de parole, les messages Braille et la lecture continue.
Correctifs et améliorations pour Courrier, Outlook, Teams, Visual Studio, Azure Data Studio et Foobar2000.
Sur le Web, améliorations pour Google Docs, et meilleur support d'ARIA.
Plus beaucoup d'autres correctifs et améliorations.

### Nouvelles fonctionnalités

* Appuyer sur F1 à l'intérieur d'un dialogue NVDA ouvrira maintenant le guide utilisateur à la section la plus appropriée. (#7757)
* Support des suggestions d'autocomplétion (IntelliSense) dans Microsoft SQL Server Management console et Visual Studio 2017 et supérieur. (#7504)
* Prononciation des symboles, prise en charge des regroupements de symboles dans une règle complexe et prise en charge des références à un groupe dans une règle de remplacement. Cela les rend plus simples, et plus puissantes. (#11107)
* Les utilisateurs sont maintenant avertis lorsqu'ils tentent de créer une entrée dans le dictionnaire de prononciation avec une expression régulière de remplacement invalide. (#11407)
  * Plus particulièrement, les erreurs de groupe sont maintenant détectées.
* Ajout du support des nouvelles méthodes de saisie rapide et pinyin pour le Chinois Traditionnel dans Windows 10. (#11562)
* Les en-têtes d'onglet sont maintenant considérés comme des champs de formulaire avec la touche de navigation rapide f. (#10432)
* Ajout d'une commande pour basculer l'annonce du texte marqué, surligné, sans geste de commande par défaut. (#11807)
* Ajout du paramètre de ligne de commande --copy-portable-config qui vous permet de copier la configuration utilisateur lors de l'installation silencieuse de NVDA. (#9676)
* Les routines Braille sont maintenant supportées dans la visionneuse Braille pour les utilisateurs de la souris, survoler pour se déplacer directement à une cellule Braille. (#11804)
* NVDA détectera maintenant les afficheurs Braille HumanWare Brailliant BI 40X et 20X via USB et Bluetooth. (#11819)

### Changements

* Mise à jour du transcripteur Braille Liblouis à la version 3.16.1.
 * Correction de beaucoup de plantages
 * Ajout de la table Braille Bachkir grade 1
 * Ajout de la table Braille Copte informatique 8 points
 * Ajout des tables Braille Russe braille littéraire et Russe braille littéraire (détaillé).
 * Ajout de la table Afrikaans abrégé
 * Suppression de la table Braille Russe grade 1
* Lors de la lecture en mode "Dire tout" en mode navigation, les commandes "Rechercher suivant" et "Rechercher précédent" n'arrêtent plus la lecture si l'option "Autoriser le survol en mode dire tout" est activée. À la place, la lecture reprend après le résultat précédent ou suivant trouvé. (#11563)
* Pour les afficheurs Braille HIMS, F3 a été réassigné à espace + points 148. (#11710)
* Améliorations des options du temps d'affichage et de l'affichage permanent des messages en Braille. (#11602)
* Dans les navigateurs Web et autres applications supportant le mode navigation, la liste d'éléments (NVDA+F7) peut maintenant être invoquée en mode formulaire. (#10453)
* Les mises à jour des régions ARIA-Live ne sont plus annoncées quand l'annonce du changement dynamique de contenu est désactivée. (#9077)
* NVDA annoncera maintenant "Copier dans le presse-papiers" avant le texte copié. (#6757)
* La présentation du mode tableau graphique dans le gestionnaire de disques a été améliorée. (#10048)
* Les labels des contrôles sont maintenant désactivés (grisés) lorsque le contrôle est désactivé. (#11809)
* Mise à jour de la base d'annotations emojis CLDR à la version 38. (#11817)
* La fonction interne "Mise en Évidence du Focus" a été renommée "Mise en Évidence Visuelle". (#11700)

### Corrections de bogues

* NVDA fonctionne à nouveau correctement avec les champs d'édition de l'application Fast Log Entry. (#8996)
* Report du temps écoulé dans Foobar2000 lorsque le temps total n'est pas disponible, par exemple lors de la lecture d'une diffusion en direct. (#11337)
* NVDA interprète maintenant correctement l'attribut aria-roledescription sur les éléments éditables dans les pages Web. (#11607)
* "Liste" n'est plus annoncé à toutes les lignes d'une liste dans Google Docs ou tout autre contenu éditable dans Google Chrome. (#7562)
* Lors de la navigation par caractères ou mots avec les flèches entre plusieurs éléments de liste en mode navigation, l'arrivée sur un nouvel élément de liste est maintenant annoncée. (#11569)
* NVDA lit désormais la ligne correcte lorsque le curseur est placé à la fin d'un lien à la fin d'un élément de liste dans Google Docs ou tout autre contenu éditable sur le Web. (#11606)
* Sous Windows 7, ouvrir et refermer le menu démarrer depuis le bureau replace maintenant correctement le focus. (#10567)
* Lorsque "Essayer de couper la parole pour les événements de focus expirés" est activé, les titres des tableaux sont maintenant à nouveau correctement annoncés dans Firefox. (#11397)
* NVDA n'échoue plus à lire un élément de liste après qu'un caractère a été saisi dans une liste avec les voix SAPI5 de Ivona. (#11651)
* Il est à nouveau possible d'utiliser le mode navigation pour lire un mail dans l'application Mail version 16005.13110 ou supérieure de Windows 10. (#11439)
* Lors de l'utilisation des voix Ivona SAPI5 de harposoftware.com, NVDA est maintenant capable d'enregistrer sa configuration (changement de synthétiseur) et ne reste plus silencieux après redémarrage. (#11650)
* Il est maintenant possible de saisir le chiffre 6 depuis le clavier Braille des afficheurs Braille Hims. (#11710)
* Améliorations majeures de performances dans Azure Data Studio. (#11533, #11715)
* Avec l'option "Essayer de couper la parole pour les événements de focus expirés" activée, le titre du dialogue de recherche de NVDA est à nouveau annoncé. (#11632)
* NVDA ne devrait plus se figer lorsque l'ordinateur sort de veille et que le focus se trouve dans un document Microsoft Edge. (#11576)
* Il n'est plus nécessaire d'appuyer sur tab ou de déplacer le curseur après la fermeture du menu contextuel dans Microsoft Edge pour que le mode navigation fonctionne de nouveau. (#11202)
* NVDA n'échoue plus à lire les éléments des listes dans les applications 64 bits comme Tortoise SVN. (#8175)
* ARIA treegrids apparaît maintenant comme un tableau normal dans Chrome et Firefox. (#9715)
* Une recherche en sens inverse peut maintenant être invoquée avec "Recherche précédent" et le raccourci NVDA+Maj+F3. (#11770)
* Un script NVDA n'est plus traité comme répété si une touche sans rapport est pressée entre les deux exécutions du script. (#11388)
* Les attributs gras et emphase peuvent à nouveau être ignorés dans Internet Explorer en désactivant l'option "Emphase" dans les paramètres de mise en forme des documents. (#11808)
* Un plantage de quelques secondes rencontré par quelques utilisateurs lors de la navigation entre les cellules dans Excel ne devrait plus se produire. (#11818)
* Dans Microsoft Teams avec des numéros de version tels que 1.3.00.28xxx, NVDA n'échouera plus à lire les messages dans le chat ou les canaux d'équipe à cause d'un élément de menu focalisé par erreur. (#11821)
* Le texte marqué à la fois comme contenant des erreurs d'orthographe et de grammaire dans Google Chrome sera correctement annoncé comme tel par NVDA. (#11787)
* Lors de l'utilisation d'Outlook (en français) le raccourci pour "Répondre à tous" (CTRL+Maj+R) fonctionne à nouveau. (#11196)
* Dans Visual Studio, les infobulles IntelliSense donnant des informations sur l'élément IntelliSense actuellement sélectionné sont maintenant à nouveau correctement annoncées. (#11611)
* Dans la calculatrice de Windows 10, NVDA n'annoncera plus la progression du calcul si l'annonce des caractères saisis est désactivée. (#9428)
* NVDA ne plante plus lors de l'utilisation de la table Anglais (États-Unis) abrégé, option "Afficher le mot sous le curseur en braille informatique" activée, lorsqu'un contenu tel qu'une URL est affiché. (#11754)
* Il est à nouveau possible d'annoncer le formatage de la cellule sélectionnée dans Excel en utilisant NVDA+F. (#11914)
* La saisie Qwerty sur les afficheurs Braille Papenmeier est à nouveau supportée et ne cause plus le plantage aléatoire de NVDA. (#11944)
* Dans les navigateurs basés sur Chromium, plusieurs cas ont été résolus où la navigation dans les tableaux ne fonctionnait pas et NVDA n'annonçait pas le nombre de lignes/colonnes du tableau. (#12359)

### Changements pour les développeurs

* Les tests système peuvent désormais envoyer des touches à l'aide de spy.emulateKeyPress, qui prend un identifiant de touche conforme aux propres noms de touche de NVDA, et bloque également par défaut jusqu'à ce que l'action soit exécutée. (#11581)
* NVDA ne requiert plus que le répertoire courant soit le répertoire d'application NVDA pour fonctionner. (#6491)
* Le paramètre aria live politeness pour les régions dynamiques peut désormais être trouvé sur les objets NVDA à l'aide de la propriété liveRegionPoliteness. (#11596)
* Il est maintenant possible de définir des gestes séparément pour Outlook et Word. (#11196)

## 2020.3

Cette version contient beaucoup d'améliorations de performance et de stabilité, particulièrement dans les applications Microsoft Office. Il existe de nouveaux paramètres pour basculer l'annonce des graphiques et le support des écrans tactiles.
L'existence de contenus marqués (soulignés) peut être reportée dans les navigateurs, et il existe de nouvelles tables Braille allemandes.

### Nouvelles Fonctionnalités

* Vous pouvez maintenant basculer l'annonce des graphiques dans les paramètres de mise en forme des documents de NVDA. Notez que désactiver cette option annoncera toujours les textes alternatifs des graphiques. (#4837)
* Vous pouvez maintenant basculer le support des écrans tactiles de NVDA. Une option a été ajoutée aux paramètres d'écrans tactiles, le raccourci par défaut est NVDA+CTRL+Alt+T. (#9682)
* Ajout de nouvelles tables braille allemandes. (#11268)
* NVDA détecte maintenant les contrôles de texte UIA en lecture seule. (#10494)
* Le texte marqué (surligné) est maintenant signalé en Braille et vocalement dans tous les navigateurs Web. (#11436)
 * Ceci peut être basculé via une nouvelle option dans les paramètres de mise en forme des documents pour le surlignage.
* De nouvelles touches d'émulation du clavier du système peuvent être ajoutées via le dialogue Gestes de Commandes. (#6060)
  * Pour faire cela, appuyez sur le bouton "Ajouter" après avoir sélectionné la catégorie "Touches émulées du clavier du système".
* Handy Tech Active Braille avec manette est maintenant supporté. (#11655)
* Le paramètre "Mode formulaire automatique lors du déplacement du curseur" est maintenant compatible avec "Positionnement automatique du focus système aux éléments susceptibles d'être mis en focus" désactivé. (#11663)

### Changements

* Le script d'annonce de la mise en forme (NVDA+F) a été modifié pour reporter la mise en forme à la position du curseur système et non plus du curseur de revue. Pour connaître la mise en forme à la position du curseur de revue utilisez maintenant NVDA+Maj+F. (#9505)
* NVDA ne place plus automatiquement le focus système sur les éléments pouvant être mis en focus en mode navigation, cela améliore les performances et la stabilité. (#11190)
* Base CLDR mise à jour de la version 36.1 à la version 37. (#11303)
* Mise à jour de eSpeak-NG à la version 1.51-dev, niveau 1fb68ffffea4
* Vous pouvez maintenant utiliser les commandes de navigation de tableau dans les listes avec des éléments cochables comportant plusieurs colonnes. (#8857)
* Dans le dialogue de confirmation de suppression d'une extension du gestionaire d'extensions, le bouton "Non" est maintenant celui par défaut. (#10015)
* Dans la liste d'éléments de Microsoft Excel, les formules sont maintenant présentées sous leur forme traduite. (#9144)
* NVDA indique maintenant correctement la terminologie des notes dans Excel. (#11311)
* Lors de l'utilisation de la commande de déplacement du curseur de revue vers le focus en mode navigation, le curseur de revue est maintenant déplacé à la position du curseur virtuel. (#9622)
* Les informations reportées en mode navigation, comme les informations de mise en forme avec NVDA+F sont maintenant affichées dans une fenêtre légèrement plus grande et centrée à l'écran. (#9910)

### Corrections de Bogues

* NVDA annonce maintenant toujours l'arrivée sur un symbole suivi d'un espace lors de la navigation par mot, peu importe le niveau de ponctuations. (#5133)
* Dans les applications utilisant QT 5.11 et supérieur, les descriptions d'objets sont à nouveau annoncées. (#8604)
* Lors de la suppression d'un mot par CTRL+Suppr, NVDA n'est plus silencieux. (#3298, #11029)
  * Le mot à droite du mot supprimé est maintenant annoncé.
* Dans les paramètres généraux, la liste des langues est maintenant triée correctement. (#10348)
* Améliorations notables de performances lors du filtrage dans le dialogue des gestes de commandes. (#10307)(
* Vous pouvez maintenant envoyer un symbole Unicode au-delà de u+FFFF depuis un afficheur Braille. (#10796)
* NVDA annoncera le contenu du dialogue "Ouvrir avec" sous Windows 10 May 2020 Update. (#11335)
* Une nouvelle option expérimentale dans les paramètres avancés (Activer l'enregistrement sélectif des évènements UI Automation et les changements de propriétés) peut apporter des améliorations majeures de performances dans Visual Studio et les autres applications basées sur UIA si activée. (#11077, #11209)
* Dans les listes avec éléments cochables, l'état "sélectionné" n'est plus annoncé systématiquement, et, le cas échéant, l'état "non sélectionné" est annoncé à la place. (#8554)
* Sous Windows 10 May 2020 Update, NVDA affiche maintenant le mapeur de sons Microsoft lors de l'affichage des périphériques de sortie audio du dialogue Synthétiseurs. (#11349)
* Sous Internet Explorer, les nombres sont maintenant annoncés correctement pour les listes ordonnées si la liste ne commence pas par 1. (#8438)
* Sous Google Chrome, NVDA reporte maintenant l'état "non coché" pour tous les contrôles, pas seulement les cases à cocher, qui ne sont actuellement pas cochés. (#11377)
* Il est à nouveau possible de naviguer dans différents contrôles si la langue de NVDA est définie sur l'aragonais. (#11384)
* NVDA ne se figera plus par moment dans Microsoft Word lors du défilement rapide avec flèche haut/bas ou lors de la saisie de caractères avec le Braille activé. (#11431, #11425, #11414)
* NVDA n'ajoute plus d'espace final inexistant lors de la copie de l'objet navigateur actuel vers le presse-papiers. (#11438)
* NVDA n'active plus le profil dire tout s'il n'y a rien à lire. (#10899, #9947)
* NVDA n'est plus incapable de lire la liste des fonctionnalités Internet dans IIS (Internet informations service). (#11468)
* NVDA garde maintenant le périphérique audio actif, améliorations des performances sur certaines cartes son. (#5172, #10721)
* NVDA ne se fige ou ne se quitte plus lors d'un appui prolongé de CTRL+Maj+Flèche basse dans Microsoft Word. (#9463)
* L'état "développé"/"Réduit" des arborressances sur drive.google.com est maintenant tout le temps reporté par NVDA. (#11520)
* NVDA détectera maintenant automatiquement l'afficheur Braille HumanWare NLSE en Bluetooth, son nom Bluetooth étant maintenant "NLS eReader Humanware". (#11561)
* Améliorations majeures de performances sous Visual Studio Code. (#11533)

### Changements pourr les Développeurs

* Dans les fonctions auxiliaires de création d'interface (GUI Helper), BoxSizerHelper.addDialogDismissButtons supporte un nouveau mot clé "separated", pour ajouter un séparateur horizontal standard aux dialogues (autre que les messages et simple dialogues d'entrée). (#6468)
* Ajouts de propriétés aux modules applicatifs incluant le chemin de l'exécutable (appPath), est une application du Store (isWindowsStoreApp), et l'architecture de la machine pour l'application (appArchitecture). (#7894)
* Il est maintenant possible de créer des modules pour les applications appartenant à wwahost.exe sous Windows 8 et suppérieur. (#4569)
* Un fragment du log peut maintenant être délimité et copié vers le presse-papiers en utilisant NVDA+CTRL+Maj+F1. (#9280)
* Les objets spécifiques à NVDA trouvés par le ramasse miettes cyclique de Python sont maintenant conservés lorsqu'ils permettent de supprimer les références cycliques de NVDA. (#11499)
 * La majorité des classes sont suivies notamment NVDAObjects, appModules, GlobalPlugins, SynthDrivers, et TreeInterceptors.
 * Une classe devant être suivie doit hériter de garbageHandler.TrackedObject.
* Des évènements de débogage significatifs pour les évènements MSAA peuvent maintenant être activés dans les paramètres avancés de NVDA. (#11521)
* Les événements MSAA winEvents pour l'objet ayant le focus ne sont plus filtrés comme d'autres événements si le nombre d'événements pour un thread donné est dépassé. (# 11520)

## 2020.2

Les points forts de cette version incluent le support d'un nouvel afficheur Braille de Natiq nBraille, un meilleur support de l'antivirus Eset et de Windows Terminal, une amélioration des performances pour 1Password et le synthétiseur Windows OneCore, ainsi que beaucoup d'autres correctifs.

### Nouvelles fonctionnalités

* Support de nouveaux afficheurs Braille :
  * Nattiq nBraille (#10778)
* Ajout d'un script pour ouvrir le dossier de configuration de NVDA (aucun geste par défaut). (#2214)
* Meilleur support pour l'interface de l'antivirus Eset. (#10894)
* Ajout du support de Windows Terminal. (#10305)
* Ajout d'une commande pour annoncer le profil de configuration actif (pas de geste par défaut). (#9325)
* Ajout d'une commande pour basculer l'annonce des exposants et indices (pas de geste par défaut). (#10985)
* Les applications Web (par exemple GMail) n'annonceront plus d'anciennes informations lors du déplacement rapide du curseur. (#10885)
  * Ce correctif expérimental doit être activé manuellement via l'option "Essayer de couper la parole pour les évènements focus expirés" dans les paramètres avancés.
* Beaucoup de symboles ont été ajoutés au dictionnaire de symboles par défaut. (#11105)

### Changements

* Mise à jour du transcripteur Braille Liblouis de la version 3.12.0 vers la version [3.14.0](https://github.com/liblouis/liblouis/releases/tag/v3.14.0). (#10832)
* L'annonce des exposants et indices est maintenant contrôlée séparément de l'annonce des attributs de la police. (#10919)
* En raison de changements dans VS Code, NVDA ne désactivera plus le mode navigation dans Code par défaut. (#10888)
* NVDA n'annonce plus "haut" et "bas" lors du déplacement du curseur de revue à la première ou dernière ligne de l'objet navigateur actuel. (#9551)
* NVDA n'annonce plus "gauche" et "droite" lors du déplacement du curseur de revue au premier ou dernier caractère de la ligne actuelle de l'objet navigateur actuel. (#9551)

### Corrections de bogues

* NVDA démarre maintenant correctement quand le fichier journal ne peut être créé (#6330)
* Dans les versions récentes de Microsoft Word 365, NVDA n'annoncera plus "mot précédent supprimé" quand CTRL+retour arrière est pressé pendant l'édition d'un document. (#10851)
* Dans Winamp, NVDA annoncera à nouveau le changement de statut des fonctions répétition et aléatoire. (#10945)
* NVDA n'est plus extrêmement lent lors du déplacement dans la liste des éléments de 1Password. (#10508)
* Le synthétiseur Windows OneCore ne ralentira plus entre les différents blocs de paroles. (#10721)
* NVDA ne se figera plus lors de l'ouverture du menu contextuel de 1Password depuis la zone de notifications système. (#11017)
* Dans Office 2013 et plus ancien :
  * Les rubans sont annoncés lorsque le curseur s'y déplace pour la première fois. (#4207)
  * Les éléments du menu contextuel sont à nouveau annoncés correctement. (#9252)
  * Les sections des rubans sont annoncées constamment lors du déplacement avec CTRL+flèche. (#7067)
* En mode navigation dans Mozilla Firefox et Google Chrome, le texte n'est plus incorrectement affiché sur une ligne séparée lorsque le contenu Web utilise l'affichage CSS : inline-flex. (#11075)
* En mode navigation avec le positionnement automatique sur les éléments susceptibles d'être mis en focus désactivé, il est maintenant possible d'activer les éléments impossible à mettre en focus.
* En mode navigation avec le positionnement automatique sur les éléments susceptibles d'être mis en focus désactivé, il est maintenant possible d'activer les éléments riches via la touche tab. (#8528)
* En mode navigation avec le positionnement automatique sur les éléments susceptibles d'être mis en focus désactivé, activer certains éléments ne cliquera plus à la mauvaise position. (#9886)
* Le son d'erreur de NVDA n'est plus joué lors de l'accès à un contrôle de texte DevExpress. (#10918)
* Les infobulles des icônes de la zone de notifications ne sont plus annoncées lors de la navigation au clavier si elles sont identiques au texte de l'icône, pour éviter une double annonce. (#6656)
* En mode navigation avec le positionnement automatique sur les éléments susceptibles d'être mis en focus désactivé, basculer en mode formulaire avec NVDA+espace met maintenant en focus l'élément sous le curseur. (#11206)
* Il est à nouveau possible de vérifier les mises à jour de NVDA sur certains systèmes, par exemple les installations propres de Windows. (#11253)
* Dans les applications Java, le focus n'est plus déplacé lors d'un changement de sélection dans une liste, un onglet ou une arborressence ne pouvant avoir le focus. (#5989)

### Changements pour les développeurs

* execElevated et hasUiAccess ont été déplacés du module config au module systemUtils. L'usage via le module config est déprécié. (#10493)
* Mise à jour de configobj à la version 5.1.0dev niveau f9a265c4. (#10939)
* Les tests automatiques de NVDA avec Chrome et un exemple HTML sont maintenant possibles. (#10553)
* IAccessibleHandler a été converti en un paquet, OrderedWinEventLimiter a été extrait en un module et ajouté à unit tests. (#10934)
* Mise à jour de BrlApi en version 0.8 (BRLTTY 6.1). (#11065)
* Le retour des barres d'état peut maintenant être personnalisé par un AppModule. (#2125, #4640)
* NVDA ne suit plus IAccessible EVENT_OBJECT_REORDER. (#11076)
* Un ScriptableObject bloqué (par exemple un globalplugin dont l'appel à la classe basique INIT est manquant) ne bloquera plus le rendu des scripts de NVDA. (#5446)

## 2020.1

Les points forts de cette version incluent la prise en charge de nombreux nouveaux afficheurs Braille de HumanWare et APH, et beaucoup d'autres corrections de bogues comme la possibilité de lire à nouveau du contenu mathématiques dans Microsoft Word en utilisant MathPlayer/MathType.

### Nouvelles Fonctionnalités

* L'élément actuellement sélectionné dans une zone de liste est à nouveau annoncé en mode navigation dans Chrome, comme c'était le cas pour NVDA 2019.1. (#10713)
* Vous pouvez maintenant effectuer des clics droit souris sur les appareils tactiles en maintenant un doigt appuyé. (#3886)
* Support de nouveaux afficheurs Braille : APH Chameleon 20, APH Mantis Q40, HumanWare BrailleOne, BrailleNote Touch v2, et NLS eReader. (#10830)

### Changements

* NVDA empêchera le système de se verrouiller ou de passer en veille pendant Dire Tout. (#10643)
* Support des cadres IFrames hors-processus dans Mozilla Firefox. (#10707)
* Mise à jour du transcripteur Braille Liblouis à la version 3.12. (#10161)

### Corrections de Bogues

* Correction de la non annonce par NVDA du symbole Unicode moins (U+2212) (#10633)
* Quand on installe une extension à partir du gestionnaire d'extensions, les noms des fichiers et des dossiers dans le dialogue parcourir ne sont plus annoncés deux fois. (#10620, #2395)
* Dans Firefox, lors du chargement de Mastodon avec l'interface Web avancée activée, toutes les chronologies sont désormais correctement rendues en mode navigation. (#10776)
* En mode navigation, NVDA annonce désormais " non coché " pour les cases à cocher décochées alors qu'il ne le faisait pas toujours avant. (#10781)
* Les contrôles de bascule ARIA ne provoquent plus l'annonce d'informations confuses telles que " non enfoncé coché " ou " enfoncé coché ". (#9187)
* Les voix SAPI4 ne devraient plus refuser de lire certains textes. (#10792)
* NVDA peut à nouveau lire et interagir avec des équations mathématiques dans Microsoft Word. (#10803)
* NVDA annoncera de nouveau correctement le texte désélectionné lorsque vous pressez une touche fléchée en mode navigation quand du texte est sélectionné. (#10731).
* NVDA ne se fermera plus en cas d'erreur à l'initialisation d'eSpeak. (#10607)
* Les erreurs dues aux caractères unicode dans la traduction d'un raccourci n'arrêteront plus l'installeur, provocant leur correction par retour au texte anglais. (#5166, #6326)
* Le mouvement par flèches en mode dire tout vers la sortie ou loin des listes et des tableaux n'annoncera plus constamment la sortie de ces derniers si le survol est activé. (#10706)
* Correction du suivi de la souris pour certains éléments MSHTML dans Internet Explorer. (#10736)

### Changements pour les développeurs

* La documentation développeur est maintenant compilée avec Sphinx. (#9840)
* Plusieurs fonctions vocales ont été divisées en deux. (#10593)
  La version speakX reste, mais elle dépend maintenant d'une fonction getXSpeech qui retourne une séquence de parole.
  * speakObjectProperties s'appuie maintenant sur getObjectPropertiesSpeech
  * speakObject s'appuie maintenant sur getObjectSpeech
  * speakTextInfo s'appuie maintenant sur getTextInfoSpeech
  * speakWithoutPauses a été converti en une classe et réécrite, mais cela ne rompt pas la compatibilité.
  * getSpeechForSpelling est maintenant déprécié, utilisez getSpellingSpeech à la place.
  Changements internes qui n'affectent pas le développement d'extensions :
  * _speakPlaceholderIfEmpty est devenu _getPlaceholderSpeechIfTextEmpty
  * _speakTextInfo_addMath est devenu _extendSpeechSequence_addMathForTextInfo
* La parole 'reason' a été converti en une énumération, consultez la classe controlTypes.OutputReason. (#10703)
  * Les constantes de niveau de module 'REASON_*' sont dépréciées.
* La compilation des dépendances de NVDA nécessitent maintenant Visual Studio 2019 (16.2 ou supérieur). (#10169)
* Mise à jour de SCons à la version 3.1.1. (#10169)
* Réautorisation de n'avoir aucun emplacement défini pour behaviors._FakeTableCell (#10864)

## 2019.3

NVDA 2019.3 est une version très importante contenant de nombreux changements structurels incluant la mise à jour de Python 2 à Python 3, et une réécriture majeure du sous-système de parole de NVDA.
Bien que ces changements rendent incompatibles certaines extensions anciennes, la mise à jour vers Python 3 est nécessaire pour la sécurité, et les changements dans la parole permettront d'intéressantes innovations dans un futur proche.
 Autres points forts de cette version :  Support du 64 bit pour les VMS Java, des fonctionnalités de Rideau d'écran et de surlignage du focus, le support de davantage d'afficheurs braille et une nouvelle visionneuse braille, ainsi que beaucoup de corrections de bogues.

### Nouvelles Fonctionnalités

* La précision de la commande pour déplacer la souris à l'objet navigateur a été améliorée dans les zones de texte des applications Java. (#10157)
* Ajout du support des afficheurs Braille Handy Tech suivants (#8955) :
 * Basic Braille Plus 40
 * Basic Braille Plus 32
 * Connect Braille
* Tous les gestes personnalisés peuvent maintenant être supprimés via un nouveau bouton "Réinitialiser aux valeurs par défaut" dans le dialogue "Gestes de commandes". (#10293)
* L'annonce de la police dans Microsoft Word indiquera maintenant si un texte est marqué comme masqué. (#8713)
* Ajout d'une commande pour déplacer le curseur de revue vers la position précédemment définie comme marqueur de début pour la sélection ou la copie : NVDA+Maj+F9. (#1969)
* Dans Internet Explorer, Microsoft Edge et les versions récentes de Firefox et Chrome, les régions sont maintenant annoncées en mode formulaire et en navigation par objet. (#10101)
* Dans Internet Explorer, Google Chrome et Firefox, vous pouvez maintenant naviguer par article et groupe en utilisant des scripts de navigation rapide. Ces scripts ne sont pas assignés par défaut et peuvent l'être via le dialogue "Gestes de commande" lorsque celui-ci est ouvert à partir d'un document en mode navigation. (#9485, #9227)
 * Les figures sont également reportées, elles sont considérées comme des objets et vous pouvez y naviguer en utilisant la touche de navigation rapide o.
* Dans Internet Explorer, Google Chrome et Mozilla Firefox, les articles sont désormais annoncés lors de la navigation par objet et éventuellement, en mode navigation, si ceci est activé dans les paramètres de mise en forme du document. (#10424)
* Ajout du rideau d'écran qui, quand il est activé, rend l'écran totalement noir sous Windows 8 et supérieur (#7857)
 * Ajout d'un script pour activer le rideau d'écran (jusqu'au prochain redémarrage avec un seul appui, ou toujours tant que NVDA est exécuté avec deux appuis). Aucun geste n'est assigné par défaut.
 * Ceci peut être configuré et activé via la catégorie "Vision" du dialogue de paramètres NVDA.
* Ajout de la fonctionnalité surlignage d'écran à NVDA. (#971, #9064)
 * Le surlignage du focus, de l'objet navigateur et du curseur en mode navigation peuvent être activés et configurés dans la catégorie "Vision" des paramètres NVDA.
 * Note : cette fonction est incompatible avec l'extension Focus Highlight, cette dernière pourra être utilisée si la fonction native est désactivée.
* Ajout de l'outil Visionneuse Braille, permettant de visualiser la sortie braille via une fenêtre à l'écran. (#7788)

### Changements

* Le guide de l'utilisateur décrit maintenant comment utiliser NVDA dans les consoles Windows. (#9957)
* Lancer nvda.exe remplace désormais automatiquement toute copie de NVDA en cours d'exécution. Le paramètre de ligne de commande -r|--replace est toujours accepté mais ignoré. (#8320)
* Sous Windows 8 et supérieur, NVDA indiquera désormais le nom et la version des applications hébergées telles que les applications téléchargées depuis le Microsoft Store en utilisant les informations transmises par l'application.) (#4259, #10108)
* Quand on active ou désactive le suivi des modifications dans Microsoft Word, NVDA annoncera désormais l'état de ce paramètre. (#942)
* La version de NVDA est désormais indiquée dans le premier message du journal. Cela se produit même si la journalisation a été désactivée via l'interface graphique. (#9803)
* Le dialogue des paramètres ne permet plus de changer le niveau de journalisation si ce dernier a déjà été configuré via la ligne de commande. (#10209)
* Dans Microsoft Word, NVDA annonce désormais l'état d'affichage des caractères non imprimables lorsqu'on fait le raccourci clavier Ctrl+Maj+8. (#10241)
* Mise à jour du transcripteur Braille Liblouis vers la révision 58d67e63. (#10094)
* Quand l'annonce des caractères CLDR (y compris les emojis) est activée, ceux-ci sont annoncés à tous les niveaux de ponctuation. (#8826)
* Les paquets Python tiers, tel que Comtypes, incluent maintenant leurs avertissements et erreurs dans le journal de NVDA. (#10393)
* Mise à jour des annotations d'emoji du référentiel commun de l'Unicode vers la version 36.0. (#10426)
* Quand le focus est sur un groupe en mode navigation, la description est désormais lue également. (#10095)
* Java Access Bridge est désormais inclu dans  NVDA pour permettre l'accès aux applications Java, y compris les machines virtuelles Java 64 bits. (#7724)
* Si Java Access Bridge n'est pas activé pour l'utilisateur, NVDA l'activera automatiquement à son lancement. (#7952)
* Mise à jour de eSpeak-NG à la version 1.51-dev, révision ca65812ac6019926f2fbd7f12c92d7edd3701e0c. (#10581)

### Corrections de Bogues

* Les emojis ainsi que les autres caractères Unicode 32 bits prennent maintenant moins de place sur un afficheur Braille lorsqu'ils sont affichés sous forme de valeurs hexadécimal. (#6695)
* Sous Windows 10, NVDA annonce maintenant les infos bulle dans les applications universelles s'il est configuré pour annoncer les infos bulle dans le dialogue de paramétrage "Présentation des objets". (#8118)
* Sous Windows 10 version anniversaire et plus récente, le texte tapé est maintenant annoncé dans MinTTY. (#1348)
* Sous Windows 10 version anniversaire et ultérieure, le texte qui apparaît près du curseur dans les consoles Windows n'est plus épelé. (#513)
* Les commandes dans le dialogue compresseur d'Audacity sont maintenant annoncées lors de la navigation dans ce dialogue. (#10103)
* NVDA ne considère plus les espaces comme des mots lors de la navigation par objet dans les éditeurs de texte basés sur Scintilla tel que Notepad++. (#8295)
* NVDA empêchera le système de passer en veille lors de la lecture d'un long texte avec les commandes de navigation d'un afficheur Braille. (#9175)
* Sous Windows 10, le Braille suit maintenant correctement lors de l'édition d'une cellule dans Microsoft Excel ainsi que dans d'autres contrôles de texte UIA où il ne suivait pas. (#9749)
* NVDA annonce à nouveau les suggestions dans la barre d'adresse de Microsoft Edge. (#7554)
* NVDA ne sera plus silencieux quand le focus est sur un en-tête de contrôle d'onglet HTML dans Internet Explorer. (#8898)
* Dans Microsoft Edge basé sur EdgeHTML, NVDA n'émettra plus le son de suggestions de recherche quand la fenêtre est agrandie. (#9110, #10002)
* Les listes déroulantes ARIA 1.1 sont maintenant supportées sous Firefox et Chrome. (#9616)
* NVDA n'annoncera plus le contenu des colonnes masquées visuellement pour les éléments de liste des contrôles SysListView32. (#8268)
* Le dialogue de paramètres n'affiche plus le niveau de journalisation sur les écrans sécurisés. (#10209)
* Dans le menu Démarrer de Windows 10 version anniversaire et supérieur, NVDA annonce maintenant le détail des résultats de recherche. (#10340)
* En mode navigation, si le déplacement du curseur ou l'utilisation de la navigation rapide entraîne la modification du document, NVDA n'indiquera plus un contenu incorrect dans certains cas. (#8831, #10343)
* Certains noms de puces dans Microsoft Word ont été corrigés. (#10399)
* Dans la mise à jour de Mai de Windows 10 et supérieur, NVDA annonce maintenant correctement le premier emoji ou le premier élément dans l'historique du presse-papiers lorsque le panneau d'emoji et le dialogue d'historique du presse-papiers sont ouverts, respectivement. (#9204)
* Dans Poedit, il est à nouveau possible de voir les traductions pour les langues se lisant de droite à gauche. (#9931)
* Dans l'application Paramètres de la mise à jour de Windows 10 avril 2018 et ultérieure, NVDA n'annoncera plus les informations de la barre de progression de volume qui se trouve dans ll'onglet Système / Son. (#10412)
* Des expressions régulières invalides dans les dictionnaires de parole n'entraînent plus l'arrêt complet de la parole. (#10334)
* Quand on parcourt des éléments à puces dans Microsoft Word avec UIA activé, la puce de l'élément de liste suivant n'est plus indûment annoncée. (#9613)
* Quelques rares erreurs de traduction Braille et erreurs avec Liblouis ont été résolues. (#9982)
* Les applications Java démarrées avant le lancement de NVDA sont maintenant accessibles sans avoir à redémarrer l'application Java. (#10296)
* Dans Firefox, lorsque l'élément sélectionné est marqué comme courant (aria-current), NVDA ne le répète plus plusieurs fois. (#8960)
* NVDA traitera désormais certains caractères unicode composés tels que le e accent aigu comme un seul caractère lors du déplacement dans le texte. (#10550)
* Spring Tool Suite Version 4 est maintenant supporté. (#10001)
* NVDA n'annoncera plus deux fois l'étiquette quand un élément aria-labeledby est un élément interne. (#10552)
* Sous Windows 10 version 1607 et au-delà, les caractères saisis depuis un clavier Braille sont maintenant vocalisés dans plus de situations. (#10569)
* Lors du changement du périphérique audio, les sons émis par NVDA seront désormais lus directement sur le nouveau périphérique sélectionné. (#2167)
* Dans Mozilla Firefox, déplacer le focus en mode navigation est maintenant plus rapide. Cela rend le déplacement du curseur en mode navigation plus réactif dans certains cas. (#10584)

### Changements pour les développeurs

* Mise à jour de Python à la version 3.7. (#7105)
* Mise à jour de pySerial à la version 3.4. (#8815)
* Mise à jour de wxPython à la version 4.0.3 pour supporter Python 3.5 et supérieur. (#9630)
* Mise à jour de six à la version 1.12.0. (#9630)
* Mise à jour de py2exe à la version 0.9.3.2 (en développement, niveau b372a8e dans le dépôt albertosottile/py2exe#13). (#9856)
* Mise à jour du module comtype de UIAutomationCore.dll à la version 10.0.18362. (#9829)
* La complétion via la tabulation dans la console Python suggère des éléments commençant par un souligné uniquement si le souligné est le premier caractère saisi. (#9918)
* L'outil Flake8 a été intégré en plus de SCons dans les tests de code que doit passer une pull request. (#5918)
* Comme NVDA ne dépend plus de pywin32, les modules tels que win32api et win32con ne sont plus disponibles pour les extensions. (#9639)
 * l'appel à win32api peut être remplacé par l'appel direct à la dll de win32api via ctypes.
 * les constantes win32con peuvent être définies dans vos fichiers.
* L'argument "async" dans nvwave.playWaveFile a été renommé en "asynchronous". (#8607)
* speakText et speakCharacter ne sont plus supportés dans synthDriver.
 * Cette fonction est remplacée par synthDriver.speak.
* La classe SynthSetting dans synthDriverHandler a été supprimée. Utilisez maintenant la classe driverHandler.DriverSetting à la place.
* La classe SynthDriver ne peut plus renvoyer d'index via la propriété lastIndex.
 * À la place, elle peut notifier l'action synthDriverHandler.synthIndexReached avec l'index, une fois que tous les autres audio ont finis d'être joués avant cet index.
* La classe SynthDriver doit maintenant notifier l'action synthDriverHandler.synthDoneSpeaking, une fois que tous les audio de SynthDriver.speak appelés ont été entièrement joués.
* La classe SynthDriver doit supportée speech.PitchCommand dans sa méthode de parole, les changements de hauteur ou encore l'épellation dépendent maintenant de cette méthode.
* La fonction de parole getSpeechTextForProperties a été renommée en getPropertiesSpeech. (#10098)
* La fonction Braille getBrailleTextForProperties a été renommée en getPropertiesBraille. (#10469)
* Plusieurs fonctions de parole ont été modifiées pour retourner des séquences de parole (#10098)
 * getControlFieldSpeech
 * getFormatFieldSpeech
 * getSpeechTextForProperties s'appelle maintenant getPropertiesSpeech
 * getIndentationSpeech
 * getTableInfoSpeech
* Ajout d'un module textUtils pour faciliter la différenciation entre les chaînes python 3 et les chaînes Windows unicode. (#9545)
 * Voir la documentation du module ainsi que le module textInfos.offsets pour des exemples d'implémentation.
* Fonctionnalités obsolètes supprimées (#9548)
 * AppModules supprimé:
  * Windows XP sound recorder.
  * Klango Player, qui est un logiciel abandonné.
 * configobj.validate supprimé
  * Nouveau code devant être utilisé depuis configobj import validate à la place de import validate
 * textInfos.Point et textInfos.Rect remplacés par locationHelper.Point et locationHelper.RectLTRB respectivement.
 * braille.BrailleHandler._get_tether et braille.BrailleHandler.set_tether ont été supprimés.
 * config.getConfigDirs a été supprimé.
 * config.ConfigManager.getConfigValidationParameter a été remplacé par getConfigValidation
 * La propriété inputCore.InputGesture.logIdentifier a été supprimée.
   * Utilisez _get_identifiers dans inputCore.InputGesture à la place.
 * synthDriverHandler.SynthDriver.speakText/speakCharacter ont été supprimés.
 * Suppression de plusieurs classes synthDriverHandler.SynthSetting.
   * Précédemment conservées pour compatibilité (#8214), maintenant considéré comme obsolète.
   * Les pilotes utilisant la classe SynthSetting doivent être mis à jour pour utiliser la classe DriverSetting.
 * Du vieux code a été supprimé, principalement:
  * Support pour la liste de messages dans les versions antérieures à Outlook 2003.
  * Une casse pour le menu démarrer classique, uniquement trouvée sous Windows Vista et antérieur.
  * Fin du support pour Skype 7, qui ne fonctionne définitivement plus.
* Ajout d'un cadre pour créer des fournisseurs d'amélioration de la vision; modules pouvant modifier le contenu de l'écran, éventuellement en fonction des informations fournies par NVDA concernant l'emplacement des objets. (#9064)
 * Ces extensions peuvent trouver leur propre place dans le dossier visionEnhancementProviders.
 * Voir les modules vision et visionEnhancementProviders pour l'implémentation du framework et des exemples, respectivement.
 * Les fournisseurs d'amélioration de la vision sont activés et configurés via la catégorie «vision» dans le dialogue des paramètres de NVDA.
* Les propriétés de classes abstraites sont maintenant supportées sur les objets qui héritent de baseObject.AutoPropertyObject (e.g. NVDAObjects et TextInfos). (#10102)
* Introduction de displayModel.UNIT_DISPLAYCHUNK comme une unité constante spécifique de textInfos DisplayModelTextInfo. (#10165)
 * Cette nouvelle constante permet de parcourir le texte dans un DisplayModelTextInfo d'une manière plus proche de la façon dont les fragments de texte sont enregistrés dans le modèle sous-jacent.
* displayModel.getCaretRect renvoie maintenant une instance de locationHelper.RectLTRB. (#10233)
* Les constantes UNIT_CONTROLFIELD et UNIT_FORMATFIELD ont été déplacées de virtualBuffers.VirtualBufferTextInfo vers le package textInfos. (#10396)
* Pour chaque entrée du journal NVDA, des informations sur le thread d'origine sont maintenant incluses. (#10259)
* Les objets UIA TextInfo peuvent maintenant être déplacés / développés avec les unités de texte page, story et formatField. (#10396)
* Les modules externes (appModules et globalPlugins) ont désormais moins de chances d’interrompre la création de NVDAObjects.
 * Les exceptions causées par les méthodes "ChooseNVDAObjectOverlayClasses" et "event_NVDAObject_init" sont maintenant correctement capturées et consignées.
* Le dictionnaire aria.htmlNodeNameToAriaLandmarkRoles a été renommé en aria.htmlNodeNameToAriaRoles. Il contient également des rôles qui ne sont pas des points de repère.
* scriptHandler.isCurrentScript a été supprimé en raison d'une utilisation insuffisante. Il n'y a pas de remplacement. (#8677)

## 2019.2.1

Ceci est une version mineure qui corrige plusieurs plantages présents dans la version 2019.2. Les correctifs incluent :

* Résolution de plusieurs blocages dans Gmail observés dans Firefox et Chrome lors de l'interaction avec des menus contextuels spécifiques, tels que la création de filtres ou la modification de certains paramètres Gmail. (#10175, #9402, #8924)
* Sous Windows 7, NVDA ne provoque plus le blocage de l'explorateur Windows quand la souris est utilisée dans le menu Démarrer. (#9435)
* L'explorateur Windows sous Windows 7 ne plante plus lors de l'accès aux champs d'édition des métadonnées. (#5337)
* NVDA ne gèle plus quand on interagit avec des images contenant un URI en base64 sous Mozilla Firefox ou Google Chrome. (#10227)

## 2019.2

Les améliorations principales de cette version consistent en l'ajout de l'auto-détection des afficheurs Braille Freedom Scientific, de l'ajout d'un réglage expérimental aux paramètres avancés pour empêcher le mode navigation de se déplacer automatiquement vers le curseur (ce qui peut améliorer les performances), une option pour trippler le débit du synthétiseur Windows OneCore, et plein d'autres correctifs.

### Nouvelles Fonctionnalités

* Le support NVDA pour Miranda NG fonctionne avec les versions les plus récentes du client. (#9053)
* Vous pouvez maintenant désactiver le mode navigation par défaut en désactivant la nouvelle option " Activer le mode navigation au chargement de la page " dans les paramètres du mode navigation de NVDA. (#8716)
 * Notez que lorsque cette option est désactivée, vous pouvez toujours activer le mode navigation manuellement en appuyant sur NVDA + Espace.
* Vous pouvez maintenant filtrer les symboles dans le dialogue de prononciation des symboles et ponctuations du même mode que pour le filtrage dans la liste des éléments et dans le dialogue des gestes de commandes. (#5761)
* Une commande a été ajoutée pour modifier la résolution de l'unité de texte de la souris (la quantité de texte qui sera prononcé lorsque la souris se déplace), mais aucun geste par défaut n'a été attribué à cette commande. (#9056)
* Le synthétiseur Windows OneCore dispose désormais d'une option d'augmentation du débit qui permet une parole beaucoup plus rapide. (#7498)
* L'option Tripler le Débit est maintenant configurable à partir de la boucle Paramètres Synthétiseur pour les synthétiseurs vocaux pris en charge. (Présentement, eSpeak-NG et Windows OneCore). (#8934)
* Les profils de configuration peuvent maintenant être activés manuellement avec des gestes. (#4209)
 * Les gestes doivent être configurés à l'aide du dialogue " Gestes de commandes ".
* Dans Eclipse, ajout du support pour l'auto-complétion dans l'éditeur de code. (#5667)
 * De plus, les informations Javadoc peuvent être lues à partir de l'éditeur quand il est présent à l'aide de NVDA + d.
* Ajout d'une option expérimentale au panneau Paramètres Avancés permettant d'empêcher le focus système de suivre le curseur du mode navigation (Mettre automatiquement le focus système sur les éléments pouvant être focalisés). (#2039) Bien que cette option ne puisse pas être désactivée pour tous les sites Web, cela peut également résoudre :
 * Effet d'élastique : NVDA annule sporadiquement la dernière frappe en mode navigation en sautant vers l'emplacement précédent.
 * Les zones d'édition volent le focus système lorsque vous les parcourez aux flèches sur certains sites Web.
 * Les touches du mode Navigation sont lentes à réagir.
* Pour les pilotes d'afficheurs braille qui le supportent, les paramètres du pilote peuvent maintenant être modifiés à partir de la catégorie paramètres braille dans le dialogue des paramètres de NVDA. (#7452)
* Les afficheurs Braille de Freedom Scientific sont maintenant supportés par l'auto-détection des afficheurs Braille. (#7727)
* Ajout d'une commande pour afficher le remplacement du symbole sous le curseur de revue. (#9286)
* Ajout d'une option dans les paramètres avancés vous permettant d'utiliser une fonction en cours de développement, la réécriture du support de la console Windows par NVDA en utilisant l'API UI Automation de Microsoft. (#9614)
* Dans la console Python, le champ de saisie prend désormais en charge le collage de plusieurs lignes à partir du presse-papiers. (#9776)

### Changements

* Le volume des synthèses est maintenant augmenté et diminué de 5 incréments au lieu de 10 dans la boucle paramètres du synthétiseur. (#6754)
* Clarification du texte dans le gestionnaire des extensions lors du lancement de NVDA avec l'argument --disable-addons. (#9473)
* Mise à jour des annotations emoji du référentiel de données locales communes Unicode vers la version 35.0. (#9445)
* Le raccourci clavier du champ de filtrage dans la liste des éléments en mode navigation a été remplacé par alt + y. (#8728)
* Lorsqu'un afficheur braille auto-détecté est connecté via Bluetooth, NVDA continuera à rechercher les afficheurs USB pris en charge par le même pilote et passera à une connexion USB si elle devient disponible. (#8853)
* Mise à jour de eSpeak-NG à la révision 67324cc.
* Mise à jour du traducteur braille liblouis à la version 3.10.0. (#9439, #9678)
* NVDA dira maintenant le mot " sélectionné " après avoir annoncé le texte qu'un utilisateur vient de sélectionner (#9028, #9909).
* Dans Microsoft Visual Studio Code, NVDA est maintenant en mode formulaire automatiquement. (#9828)

### Corrections de Bogues

* NVDA ne plante plus lorsqu'un répertoire d'extensions est vide. (#7686)
* Les marques LTR et RTL ne sont signalées ni en braille ni par épellation lors de l'accès à la fenêtre des propriétés. (#8361)
* Lorsqu'on se déplace entre les formulaires avec la navigation rapide en mode Navigation, le formulaire entier est maintenant annoncé plutôt que la première ligne seulement. (#9388)
* NVDA ne restera plus silencieux quand on quitte l'application Windows 10 Mail. (#9341)
* NVDA n'échoue plus au démarrage lorsque les paramètres régionaux utilisateur sont définis sur une langue inconnue de NVDA, telle que l'anglais (Pays-Bas). (#8726)
* Quand le mode navigation est activé dans Microsoft Excel et que l'on passe en mode formulaire ou inversement, l'état du mode navigation est désormais correctement signalé. (#8846)
* NVDA rend maintenant correctement la ligne située au curseur souris dans Notepad ++ et d'autres éditeurs basés sur Scintilla. (#5450)
* Dans Google Docs (et d'autres éditeurs basés sur le Web), le braille n'indique plus parfois incorrectement " fin de lst " avant le curseur situé au milieu d'un élément de liste. (#9477)
* Dans la mise à jour Windows 10 mai 2019, NVDA n'annonce plus beaucoup de notifications de volume si le volume est modifié à l'aide de boutons matériels quand l'explorateur de fichiers a le focus. (#9466)
* Le chargement du dialogue de prononciation des symboles et ponctuations est désormais beaucoup plus rapide lorsque vous utilisez des dictionnaires de symboles contenant plus de 1 000 entrées. (#8790)
* Dans les contrôles Scintilla tels que Notepad ++, NVDA peut lire la ligne correcte lorsque le retour à la ligne est activé. (#9424)
* Dans Microsoft Excel, l'emplacement de la cellule est annoncé quand il change à cause des gestes Maj Entrée ou Maj PavNum Entrée. (#9499)
* Dans Visual Studio 2017 et versions ultérieures, dans la fenêtre Explorateur d'objets, l'élément sélectionné dans l'arborescence des objets ou dans l'arborescence des membres avec des catégories est désormais correctement annoncé. (#9311)
* Les extensions dont les noms diffèrent seulement par leur majuscule ne sont plus traités comme des extensions séparées. (#9334)
* Pour les voix Windows OneCore, le débit défini dans NVDA n'est plus affecté par celui défini dans les paramètres vocaux de Windows 10. (#7498)
* Le journal peut maintenant être ouvert avec NVDA + F1 en l'absence d'informations développeur pour l'objet navigateur courant. (#8613)
* Il est à nouveau possible d'utiliser les commandes de navigation des tableaux de NVDA dans Google Docs, dans Firefox et Google Chrome. (#9494)
* Les touches " bumper " fonctionnent maintenant correctement sur les afficheurs Braille Freedom Scientific. (#8849)
* Lors de la lecture du premier caractère d'un document dans Notepad++ 7.7 X64, NVDA ne se bloque plus pendant 10 secondes. (#9609)
* HTCom peut maintenant être utilisé avec un afficheur Braille Handy Tech en association avec NVDA. (#9691)
* Dans Mozilla Firefox, les mises à jour d'une région active ne sont plus signalées si la région active est dans un onglet en arrière-plan. (#1318)
* Le dialogue de recherche du mode navigation de NVDA n'échoue plus si le dialogue À propos de NVDA est ouvert au même moment en arrière-plan. (#8566)

### Changements pour les développeurs

* Vous pouvez maintenant définir la propriété "disableBrowseModeByDefault" sur les modules d'application pour que le mode navigation soit désactivé par défaut. (#8846)
* Le style de fenêtre étendu d'une fenêtre est maintenant exposé à l'aide de la propriété `extendedWindowStyle` sur les objets Window et leurs dérivés. (#9136)
* Mise à jour du paquet comtypes vers 1.1.7. (#9440, #8522)
* Lors de l'utilisation de la commande report module info, l'ordre des informations a été modifié pour présenter d'abord le module. (#7338)
* Ajout d'un exemple d'utilisation de nvdaControllerClient.dll avec C#. (#9600)
* Ajout d'une nouvelle fonction isWin10 au module winVersion qui indique si cette copie de NVDA s'exécute ou non sur (au moins) la version passée en paramètre de Windows 10 (telle que 1903). (#9761)
* La console NVDA Python contient désormais des modules plus utiles dans son espace de noms (tels que appModules, globalPlugins, config et textInfos). (#9789)
* Le résultat de la dernière commande exécutée dans la console NVDA Python est désormais accessible depuis la variable _ (souligné). (#9782)
 * Veuillez noter que cela masque la fonction de traduction gettext également appelée "_". Pour accéder à la fonction de traduction : del _

## 2019.1.1

Cette version ponctuelle corrige les bogues suivants :

* NVDA ne provoque plus le blocage d'Excel 2007 ou le refus de signaler qu'une cellule contient une formule. (#9431)
* Google Chrome ne se bloque plus lors de l'interaction avec certaines listes de sélection. (#9364)
* Un problème empêchant la copie d'une configuration utilisateur dans le profil de configuration système a été corrigé. (#9448)
* Dans Microsoft Excel, NVDA utilise à nouveau le message traduit pour signaler l'emplacement des cellules fusionnées. (#9471)

## 2019.1

Les points forts de cette version incluent des améliorations de performances lors de l'accès à Microsoft Word et Excel, des améliorations en matière de stabilité et de sécurité, comme la prise en charge des extensions comportant des informations de compatibilité de version, ainsi que de nombreuses corrections de bogues.

Veuillez noter qu'à partir de cette version de NVDA, les modules applicatifs personnalisés, les globalPlugins, les pilotes d'afficheurs braille et les pilotes de synthèses vocales ne seront plus chargés automatiquement à partir de votre répertoire de configuration utilisateur NVDA.
Ceux-ci devront plutôt être installées en tant qu'extensions de NVDA. Pour ceux qui développent du code pour une extension, le code pour les tests peut être placé dans un nouveau répertoire bloc-notes du développeur, dans le répertoire de configuration de l'utilisateur NVDA, si l'option du bloc-notes du développeur est activée dans le nouveau panneau des paramètres avancés de NVDA.
Ces modifications sont nécessaires pour mieux assurer la compatibilité du code personnalisé, afin que NVDA ne soit pas endommagé lorsque ce code devient incompatible avec les nouvelles versions.
Veuillez vous reporter à la liste des modifications plus bas pour plus de détails à ce sujet et pour savoir comment les extensions sont désormais mieux versionnées.

### Nouvelles Fonctionnalités

* Nouvelles tables braille : Afrikaans, Arabe braille informatique 8 points, Arabe abrégé, Espagnol abrégé. (#4435, #9186)
* Ajout d'une option dans les paramètres de la souris de NVDA pour que NVDA supporte les situations où la souris est contrôlée par une autre application. (#8452)
 * Cela permet à NVDA de suivre la souris quand un système est contrôlé à distance en utilisant TeamViewer ou un autre logiciel de contrôle à distance.
* Ajout du paramètre de ligne de commande `--enable-start-on-logon` pour configurer si les installations silencieuses de NVDA le définissent pour démarrer à l'ouverture de session Windows ou non. Spécifiez true pour démarrer à l'ouverture de session ou false pour ne pas démarrer à l'ouverture de session. Si l'argument --enable-start-on-logon n'est pas spécifié, NVDA démarrera par défaut à l'ouverture de session, à moins qu'il n'ait déjà été configuré par une installation précédente. (#8574)
* Il est possible de désactiver la journalisation de NVDA en mettant le niveau de journalisation sur "désactivé" dans le panneau de paramètres généraux. (#8516)
* La présence de formules dans les tableaux sous LibreOffice et Apache OpenOffice est maintenant annoncée. (#860)
* Sous Mozilla Firefox et Google Chrome, le mode navigation annonce maintenant l'élément sélectionné dans les listes déroulantes et les arborescences.
 * Ceci fonctionne sous Firefox 66 et au-delà.
 * Ceci ne fonctionne pas pour certaines listes déroulantes (contrôles de sélection HTML) sous Chrome.
* Début de support d'applications telles que Mozilla Firefox sur les ordinateurs avec processeur ARM64 (ex : Qualcomm Snapdragon). (#9216)
* Une nouvelle catégorie Paramètres Avancés a été ajoutée au dialogue Paramètres de NVDA, incluant une option pour tester le nouveau support de NVDA pour Microsoft Word via l'API Microsoft UI Automation. (#9200)
* Ajout du support de la vue graphique dans le Gestionnaire de Disques de Windows. (#1486)
* Ajout du support des terminaux Handy Tech Connect Braille et Basic Braille 84. (#9249)

### Changements

* Mise à jour du traducteur braille liblouis à la version 3.8.0. (#9013)
* Les auteurs d'extensions peuvent désormais appliquer une version NVDA minimale requise à leurs extensions. NVDA refusera d'installer ou de charger une extension dont la version minimale requise de NVDA est supérieure à la version actuelle de NVDA. (#6275)
* Les auteurs d'extensions peuvent désormais spécifier la dernière version de NVDA pour laquelle l'extension a été testée. Si une extension a uniquement été testée sur une version de NVDA inférieure à la version actuelle, NVDA refusera alors d'installer ou de charger l'extension. (#6275)
* Cette version de NVDA autorisera l'installation et le chargement des extensions qui ne contiennent pas encore d'informations sur les versions de NVDA minimales et testées en dernier, mais la mise à niveau vers des versions ultérieures de NVDA (par exemple, 2019.2) désactivera automatiquement ces extensions plus anciennes.
* La commande de déplacement de la souris vers l'objet navigateur est maintenant disponible sous Microsoft Word ainsi que pour les contrôles UIA, en particulier pour Microsoft Edge. (#7916, #8371)
* L'annonce du texte sous la souris a été améliorée sous Microsoft Edge et autres applications UIA. (#8370)
* Quand NVDA est démarré avec le paramètre de ligne de commande `--portable-path`, le chemin fourni est automatiquement rempli quand on essaie de créer une copie portable de NVDA en utilisant le menu NVDA. (#8623)
* Mise à jour du chemin de la table braille Norvégienne pour refléter le standard de l'année 2015. (#9170)
* Durant la navigation par paragraphes, (contrôle + flèches haut ou bas) ou par cellules de tableau (contrôle + alt + flèches), la présence de fautes d'orthographe n'est plus signalée, même si NVDA est configuré pour les annoncer automatiquement. En effet, les paragraphes et les cellules de tableau peuvent être très volumineux et la détection des fautes d'orthographe dans certaines applications peut s'avérer très coûteuse. (#9217)
* NVDA ne charge plus automatiquement les appModules personnalisés, les modules globaux et les pilotes braille ou de synthétiseur depuis le répertoire de configuration utilisateur de NVDA. Ce code devrait plutôt être packagé comme une extension avec une information de version correcte, pour être sûr que du code incompatible n'est pas exécuté avec la version courante de NVDA. (#9238)
 * Pour les développeurs qui ont besoin de tester du code en cours de développment, activez le répertoire du bloc-notes du développeur NVDA dans la catégorie Avancé des paramètres NVDA, et placez votre code dans le répertoire 'scratchpad' qui se trouve dans le répertoire de configuration utilisateur de NVDA quand cette option est activée.

### Corrections de Bogues

* Lors de l''utilisation de la synthèse vocale OneCore sous Windows 10 April 2018 et au-delà, de longs silences ne sont plus insérés entre des segments de parole. (#8985)
* Durant le déplacement par caractère dans les contrôles texte plein (comme le Bloc-Notes) ou en mode navigation, les caractères emoji 32 bits consistant en deux points en code UTF-16 (comme ðŸ¤¦) sont maintenant lus correctement. (#8782)
* Amélioration du dialogue de confirmation de redémarrage après changement de la langue d'interface de NVDA. Le texte et les étiquettes de boutons sont maintenant plus concis et prêtent moins à confusion. (#6416)
* Si le chargement d'une synthèse vocale tierce échoue, NVDA se rabattra sur la synthèse vocale Windows OneCore sous Windows 10, et non sur ESpeak. (#9025)
* Suppression de l'entrée "Dialogue de Bienvenue" dans le menu NVDA quand on est sur un écran sécurisé. (#8520)
* Quand on tabule ou qu'on utilise la navigation rapide en mode navigation, les légendes sur les panneaux d'onglets sont maintenant annoncées de manière plus claire. (#709)
* NVDA annonce maintenant les changements de sélection pour certains sélecteurs d'heure comme sous l'application Horloge et Alarmes sous Windows 10. (#5231)
* Dans le Centre de Notifications de Windows 10, NVDA annonce les messages d'état pour la bascule d'actions rapides telles que la brillance et le mode "ne pas déranger". (#8954)
* Dans le Centre de Notifications de Windows 10 October 2018 Update et précédentes, NVDA reconnaît le contrôle d'action rapide de brillance comme un bouton au lieu d'un bouton bascule. (#8845)
* NVDA suit de nouveau le curseur et annonce les caractères effacés dans les champs d'édition Aller à et Rechercher de Microsoft Excel. (#9042)
* Correction d'un plantage rare du mode navigation sous Firefox. (#9152)
* NVDA n'échoue plus à annoncer le focus pour certains contrôles dans le ruban de Microsoft Office 2016 quand il est réduit.
* NVDA n'échoue plus à annoncer le contact suggéré quand on entre des adresses dans les nouveaux messages sous Outlook 2016. (#8502)
* Les dernières touches de routage curseur sur les afficheurs Eurobraille 80 cellules ne routent plus le curseur vers une position près du début de la ligne braille. (#9160)
* Correction de la navigation de tableau dans la vue en arborescence sous Mozilla Thunderbird. (#8396)
* Sous Mozilla Firefox et Google Chrome, le passage en mode formulaire fonctionne maintenant correctement pour certaines listes déroulantes et arborescences (quand la liste ou arborescence n'est pas elle-même focussable mais que ses éléments le sont) . (#3573, #9157)
* Le mode navigation est maintenant correctement activé par défaut quand on lit des messages sous Outlook 2016/365 si on utilise le support expérimental UI Automation pour les Documents Word. (#9188)
* NVDA est maintenant moins sujet à se bloquer de telle façon que le seul moyen d'y échapper est de se déconnecter de sa session Windows en cours. (#6291)
* Sous Windows 10 October 2018 Update et au-delà, lors de l'ouverture de l'historique du Presse-papiers dans le cloud avec le Presse-papiers vide, NVDA annoncera l'état du Presse-papiers. (#9103)
* Sous Windows 10 October 2018 Update et au-delà, quand on cherche un emoji dans le panneau d'emojis, NVDA annonce le premier emoji trouvé. (#9105)
* NVDA ne se bloque plus dans la fenêtre principale d'Oracle VirtualBox 5.2 ou au-delà. (#9202)
* La réactivité sous Microsoft Word quand on navigue par ligne, paragraphe ou cellule de tableau peut être significativement améliorée dans certains documents. Un rappel, pour de meilleures performances, mettez Microsoft Word en affichage Brouillon avec alt+w,e après l'ouverture d'un document. (#9217)
* Sous Mozilla Firefox et Google Chrome, les alertes vides ne sont plus annoncées. (#5657)
* Améliorations significatives de performance quand on navigue par cellule sous Microsoft Excel, en particulier quand la feuille de calcul contient des commentaires et ou des listes déroulantes de validation. (#7348)
* Il ne devrait plus être nécessaire de désactiver l'édition directe de cellule dans les options de Microsoft Excel pour accéder au contrôle d'édition de cellule avec NVDA sous Excel 2016/365. (#8146).
* Correction d'un blocage dans Firefox observé parfois lors de la navigation rapide par région, quand l'extension Enhanced Aria est utilisée. (#8980)

### Changements pour les Développeurs

* NVDA peut maintenant être construit avec toutes les éditions de Microsoft Visual Studio 2017 (pas seulement l'édition Community). (#8939)
* Vous pouvez maintenant inclure le journal de liblouis dans le journal NVDA en déclarant l'indicateur booléen louis dans la section debugLogging de la configuration de NVDA. (#4554)
* Les auteurs d'extensions peuvent maintenant fournir des informations de compatibilité de version de NVDA dans le manifests de l'extension. (#6275, #9055)
 * minimumNVDAVersion : La version minimum de NVDA requise pour que l'extension fonctionne correctement.
 * lastTestedNVDAVersion : La dernière version de NVDA sur laquelle l'extension a été testée.
* Les objets OffsetsTextInfo peuvent maintenant implémenter la méthode _getBoundingRectFromOffset pour permettre de récupérer un rectangle frontière par caractère au lieu de points. (#8572)
* Ajout d'une propriété boundingRect aux objets TextInfo pour récupérer le rectangle frontière d'un bloc de texte. (#8371)
* Les propriétés et les méthodes dans les classes peuvent maintenant être marquées comme abstract dans NVDA. Ces classes signaleront une erreur si instanciées. (#8294, #8652, #8658)
* NVDA peut journaliser le temps entre une action et la survenue de la parole, ce qui permet de mesurer la réactivité perçue. Ceci peut être activé en définissant le paramètre timeSinceInput à True dans la section debugLog de la configuration de NVDA. (#9167)

## 2018.4.1

Cette version corrige un plantage au démarrage si la langue d'interface de NVDA est réglée sur Aragonais. (#9089)

## 2018.4

Les points forts de cette version incluent des améliorations de performances dans les versions récentes de Mozilla Firefox, l'annonce des emojis avec tous les synthétiseurs, l'annonce des statuts répondu/transféré sous Outlook, l'annonce de la distance du curseur au bord de la page sous Microsoft Word, et beaucoup de corrections de bogues.

### Nouvelles Fonctionnalités

* Nouvelles tables braille : Chinois (Chine, Mandarin) intégral et abrégé. (#5553)
* Les statuts Répondu / Transféré sont maintenant annoncés dans la liste de messages de Microsoft Outlook. (#6911)
* NVDA est maintenant capable de lire les descriptions des emoji ainsi que d'autres caractères faisant partie du référentiel Unicode Common Locale Data. (#6523)
* Sous Microsoft Word, la distance du curseurs aux bords haut et gauche de la page peut être annoncée en pressant NVDA+pavnumEffacement. (#1939)
* Sous Google Sheets avec le mode braille activé, NVDA n'annonce plus 'sélectionné' pour chaque cellule quand on déplace le focus de cellule en cellule. (#8879)
* Ajout du support de Foxit Reader et Foxit Phantom PDF (#8944)
* Ajout du support de l'outil pour bases de données DBeaver. (#8905)

### Changements

* " Annoncer les bulles d'aide " dans le dialogue de Présentation des Objets a été renommé en "Annoncer les notifications" pour inclure l'annonce notifications toast sous Windows 8 et au-delà. (#5789)
* Dans les paramètres clavier de NVDA, les cases à cocher permettant d'activer ou désactiver les touches NVDA sont maintenant affichées dans une liste plutôt que comme des cases à cocher séparées.
* NVDA n'annoncera plus d'informations redondantes à la lecture de l'horloge de la barre des tâches système sous certaines versions de Windows. (#4364)
* Mise à jour du traducteur braille liblouis à la version 3.7.0. (#8697)
* Mise à jour de eSpeak-NG à la révision 919f3240cbb

### Corrections de bogues

* Sous Outlook 2016/365, la catégorie et l'indicateur d'état sont annoncés pour les messages. (#8603)
* Quand NVDA est configuré pour des langues telles que le Kirghize, le Mongol ou le Macédonien, il n'affiche plus au démarrage un dialogue avertissant que la langue n'est pas supportée par le système d'exploitation. (#8064)
* Sous Mozilla Firefox, Google Chrome et Acrobat Reader DC, amener la souris à l'objet de navigation amènera maintenant la souris à la position en mode navigation. (#6460)
* L'interaction avec les listes déroulantes sous Firefox, Chrome et Internet Explorer a été améliorée. (#8664)
* Sous la version Japonaise de Windows XP ou Vista, NVDA affiche maintenant l'avertissement de version d'OS requise comme prévu. (#8771)
* Améliorations de performances sous Mozilla Firefox quand on navigue dans de grandes pages avec beaucoup de changements dynamiques. (#8678)
* Le braille n'affiche plus les attributs de police s'ils ont été désactivés dans les paramètres de Mise en Forme des Document. (#7615)
* NVDA n'échoue plus à suivre le focus dans l'Explorateur de Fichiers et autres applications utilisant UI Automation quand une autre application est occupée (comme traitement audio par lot). (#7345)
* Dans les menus ARIA sur le web, la touche échap sera maintenant transmise au menu et n'interrompra plus le mode focus inconditionnellement. (#3215)
* Sous le nouveau GMail, quand on utilise la navigation rapide à l'intérieur d'un message durant la lecture, le corps entier du message n'est plus lu après l'élément vers lequel vous venez de naviguer. (#8887)
* Après mise à jour de NVDA, les navigateurs tels que Firefox et Google Chrome ne devraient plus se planter, et le mode navigation devrait continuer à refléter correctement les mises à jour de tout document chargé. (#7641)
* NVDA n'annonce plus " cliquable " plusieurs fois dans une ligne quand on navigue dans du contenu cliquable en Mode Navigation. (#7430)
* Les gestes effectués sur l'afficheur braille baum Vario 40 n'échoueront plus à s'exécuter. (#8894)
* Sous Google Slides avec Mozilla Firefox, NVDA n'annonce plus texte sélectionné sur chaque contrôle ayant le focus. (#8964)

### Changements pour les Développeurs

* gui.nvdaControls contient maintenant deux classes pour créer des listes accessibles avec des cases à cocher. (#7325)
 * CustomCheckListBox est une sous-classe accessible de wx.CheckListBox.
 * AutoWidthColumnCheckListCtrl ajoute des cases à cocher accessibles à un contrôle AutoWidthColumnListCtrl, qui est lui-même basé sur wx.ListCtrl.
* Si vous avez besoin de rendre accessible un widget wx qui ne l'est pas déjà, il est possible de le faire en utilisant une instance de gui.accPropServer.IAccPropServer_impl. (#7491)
 * Consultez l'implémentation de gui.nvdaControls.ListCtrlAccPropServer pour plus d'informations.
* configobj mis à jour à la version 5.1.0dev commit 5b5de48a. (#4470)
* L'action config.post_configProfileSwitch prend maintenant l'argument optionnel mot clé prevConf, permettant aux gestionnaires de prendre des actions basées sur les différences entre les configurations avant et après le changement de profil. (#8758)

## 2018.3.2

Ceci est une version mineure pour corriger un plantage sous Google Chrome quand on parcourt les tweets sur [www.twitter.com](http://www.twitter.com). (#8777)

## 2018.3.1

Ceci est une version mineure pour corriger un bogue critique de NVDA qui provoquait le plantage de la version 32 bits de Mozilla Firefox. (#8759)

## 2018.3

Les points forts de cette version incluent la détection automatique de beaucoup de terminaux Braille, le support de nouvelles fonctionnalités de Windows 10 incluant le panneau de saisie des Emoji, et beaucoup de corrections de bogues.

### Nouvelles Fonctionnalités

* NVDA Annoncera les erreurs grammaticales correctement exposées dans les pages web sous Mozilla Firefox et Google Chrome. (#8280)
* Le contenu marqué comme inséré ou supprimé dans les pages web est maintenant signalé sous Google Chrome. (#8558)
* Ajout du support de la roue de défilement du BrailleNote QT et de l'Apex BT quand le BrailleNote est utilisé comme afficheur braille par NVDA. (#6316)
* Ajout de scripts pour annoncer le temps écoulé et le temps total de la piste en cours sous Foobar2000. (#6596)
* Le symbole touche de commande Mac (⌘) est maintenant annoncé par tous les synthétiseurs durant la lecture de texte. (#8366)
* Les rôles personnalisés via l'attribut aria-roledescription sont maintenant supportés dans tous les navigateurs web.
* Nouvelles tables braille : Tchèque 8 points, Kurde Central, Espéranto, Hongrois, Suédois informatique 8 points. (#8226, #8437)
* Ajout de la détection automatique des terminaux braille en arrière-plan. (#1271)
 * Les terminaux ALVA, Baum/HumanWare/APH/Orbit, Eurobraille, Handy Tech, Hims, SuperBraille et HumanWare BrailleNote et Brailliant BI/B sont actuellement supportés.
 * Vous pouvez activer cette fonction en sélectionnant l'option "automatique" dans la liste de terminaux braille du dialogue de sélection du terminal braille de NVDA.
 * Veuillez consulter la documentation pour plus de détails.
* Ajout du support de divers moyens de saisie modernes introduits dans les versions récentes de Windows 10. Cela inclut le panneau d'hemojis (Fall Creators Update), la dictée (Fall Creators Update), les suggestions de saisie au clavier système (April 2018 Update), et le collage depuis le presse-papier dans le cloud (October 2018 Update). (#7273)
* Le contenu marqué comme citation en utilisant ARIA (rôle blockquote) est maintenant supporté sous Mozilla Firefox 63. (#8577)

### Changements

* La liste des langues disponibles dans le dialogue Paramètres/Général est maintenant triée dans l'ordre alphabétique des noms des langues au lieu du code ISO 639. (#7284)
* Ajout d'un geste par défaut pour alt+maj+tab et windows+tab pour les terminaux braille Freedom Scientific supportés. (#7387)
* Pour les terminaux ALVA BC680 et protocol converter, il est maintenant possible d'assigner différentes fonctions au smart pad gauche et droit, et aux touches pouce et etouch. (#8230)
* Pour les terminaux ALVA BC6, la combinaison de touches sp2+sp3 annonce maintenant la date et l'heure courante, et sp1+sp2 émule la touche Windows. (#8230)
* Au premier démarrage de NVDA, il est maintenant demandé à l'utilisateur s'il souhaite envoyer des statistiques d'utilisation à NV Access lors de la vérification automatique de mises à jour. (#8217)
* Lors de la vérification de mises à jour, si l'utilisateur a accepté d'envoyer des données statistiques à NV Access, NVDA enverra maintenant le nom du synthétiseur et le terminal braille en cours, pour permettre une meilleure priorisation du travail futur sur ces pilotes. (#8217)
* Mise à jour du convertisseur braille liblouis à la version 3.6.0. (#8365)
* Mise à jour du chemin vers la bonne table braille russe 8 points. (#8446)
* Mise à jour de eSpeak-ng au niveau 1.49.3dev commit 910f4c2 (#8561)

### Corrections de Bogues

* Sous Google Chrome, les étiquettes accessibles des contrôles sont maintenant plus facilement annoncées en mode navigation quand l'étiquette n'apparaît pas elle-même comme un contenu. (#4773)
* Les notifications sont maintenant supportées dans Zoom. Par exemple, cela inclut le statut muet/non muet, et les messages entrants. (#7754)
* En mode navigation, changer de présentation contextuelle du braille ne provoque plus un arrêt du suivi ddu curseur de navigation. (#7741)
* Les terminaux braille ALVA BC680 n'échouent plus à s'initialiser de manière intermittente. (#8106)
* Par défaut, les terminaux ALVA BC6 n'exécuteront plus d'émulations du clavier système à l'appui de combinaisons contenant sp2+sp3 pour activer des fonctionnalités internes. (#8230)
* L'appui sur sp2 sur un terminal ALVA BC6 pour émuler la touche alt fonctionne maintenant comme annoncé. (#8360)
* NVDA n'annonce plus de changements de configuration clavier redondants. (#7383, #8419)
* Le suivi de la souris est maintenant beaucoup plus précis sous Notepad et autres contrôles d'édition en texte clair dans les documents de plus de 65535 caractères. (#8397)
* NVDA reconnaît plus de dialogues sous Windows 10 et autres applications modernes. (#8405)
* Sous Windows 10 October 2018 Update, Server 2019 et au-delà, NVDA n'échoue plus à suivre le focus système quand une application se gèle ou surcharge le système en évènements. (#7345, #8535)
* L'utilisateur est maintenant informé quand il essaie de lire ou copier une barre d'état vide. (#7789)
* Correction d'un problème où l'état "non coché" des contrôles n'est pas annoncé quand l'état précédent était "semi-coché". (#6946)
* Dans la liste des langues du dialogue Paramètres/Général, le nom de la langue birmane s'affiche correctement sous Windows 7. (#8544)
* Sous Microsoft Edge, NVDA annoncera les notifications telles que la disponibilité de la page en lecture et la progression du chargement de la page. (#8423)
* Quand on entre dans une liste sur le web, NVDA annonce maintenant son étiquette si l'auteur en a fourni une. (#7652)
* Quand on assigne manuellement une fonction à un geste pour un terminal braille particulier, ce geste apparaît maintenant toujours comme assigné à ce terminal. Avant, il apparaissait comme assigné au terminal en cours. (#8108)
* La version 64-bit de Media Player Classic est maintenant supportée. (#6066)
* Plusieurs améliorations du support braille sous Microsoft Word avec UI Automation activé:
 * Comme dans les autres champs de texte multilignes, quand on se positionne au début d'un document en Braille, l'affichage est maintenant aligné pour que le premier caractère du document soit au début de l'affichage. (#8406)
 * Réduction de la présentation de focus trop verbeuse en vocal et en braille à la mise en focus d'un document Word. (#8407)
 * Le routage de curseur en braille fonctionne maintenant correctement quand on se trouve dans une liste dans un document Word. (#7971)
 * Les puces ou numérotations nouvellement insérées dans un document Word sont correctement signalées vocalement et en braille. (#7970)
* Sous Windows 10 1803 et au-delà, il est maintenant possible d'installer des extensions si la fonctionnalité "Utiliser Unicode UTF-8 pour le support mondial des langues" est activé. (#8599)
* Il n'est plus impossible d'interagir avec iTunes 12.9 et au-delà avec NVDA. (#8744)

### Changements pour les Développeurs

* Ajout de scriptHandler.script, qui peut fonctionner comme un décorateur pour les scripts sur les objets scriptables. (#6266)
* Un environnement de test système a été introduit pour NVDA. (#708)
* Quelques changements ont été apportés au module hwPortUtils : (#1271)
 * listUsbDevices fournit maintenant des dictionnaires avec des informations sur le périphérique incluant hardwareID et devicePath.
 * les dictionnaires fournis par listComPorts contiennent maintenant aussi une entrée usbID pour les ports COM par USB information VID/PID dans leur hardware ID.
* Mise à jour de wxPython à la version 4.0.3. (#7077)
* Comme NVDA ne supporte plus que Windows 7 SP1 et au-delà, la clé "minWindowsVersion" utilisée pour vérifier si UIA devrait être activé pour une version donnée de Windows a été supprimée. (#8422)
* Vous pouvez maintenant demander à être notifié des actions de sauvegardes/réinitialisations de configuration via les nouvelles actions config.pre_configSave, config.post_configSave, config.pre_configReset, et config.post_configReset. (#7598)
 * config.pre_configSave est utilisé pour être notifié quand la configuration de NVDA est sur le point d'être sauvegardée, et config.post_configSave est appelé après que la configuration ait été sauvegardée.
 * config.pre_configReset et config.post_configReset incluent un drapeau de paramètres par défaut pour spécifier si les paramètres sont rechargés depuis le disque (false) ou réinitialisés aux paramètres par défaut (true).
* config.configProfileSwitch a été renommé en config.post_configProfileSwitch pour refléter le fait que cette action est appelée après qu'un changement de profil ait pris effet. (#7598)
* Les interfaces UI Automation ont été mises à jour vers Windows 10 October 2018 Update et Server 2019 (IUIAutomation6 / IUIAutomationElement9). (#8473)

## 2018.2.1

Cette version comprend des changements de traduction dus au retrait de dernière minute d'une fonctionnalité qui posait problème.

## 2018.2

Les points forts de cette version incluent la prise en charge des tableaux dans Kindle pour PC, le support des terminaux Braille Humanware BrailleNote Touch et BI14, des améliorations apportées aux synthétiseurs vocaux OneCore et Sapi5, des améliorations dans Microsoft Outlook et bien plus encore.

### Nouvelles Fonctionnalités

* La taille des lignes et colonnes des cellules de tableau est maintenant signalée vocalement et en braille. (#2642)
* Les commandes NVDA de navigation dans les tableaux sont maintenant supportées sous Google Docs (avec le mode Braille activé). (#7946)
* Ajout de la possibilité de lire les tableau et d'y naviguer sous Kindle for PC. (#7977)
* Support des terminaux Braille BrailleNote Touch et Brailliant BI 14 de HumanWare via USB et Bluetooth. (#6524)
* Sous Windows 10 Fall Creators Update et au-delà, NVDA peut annoncer les notifications des applications telles que la Calculatrice et le Windows Store. (#7984)
* Nouvelles tables de conversion braille : Lithuanien 8 points, Ukrainien, Mongol abrégé. (#7839)
* Ajout d'un script pour annoncer l'information de mise en forme pour le texte sous une cellule braille spécifique. (#7106)
* Lors d'une mise à jour de NVDA, il est désormais possible de reporter l'installation de la mise à jour à un moment ultérieur. (#4263)
* Nouvelles langues : mongol, suisse allemand.
* Vous pouvez maintenant utiliser contrôle, majuscule, alt, windows et NVDA depuis votre clavier braille et combiner ces modifieurs avec la saisie braille (ex : presser contrôle+s). (#7306)
 * Vous pouvez assigner ces nouveaux modificateurs en utilisant les commandes qui se trouvent dans Touches émulées du clavier du système dans le dialogue Gestes de commandes.
* Retour du support des terminaux braille Handy Tech Braillino et Modular (ceux équipés de l'ancien micrologiciel). (#8016)
* La date et l'heure pour les terminaux Handy Tech supportés (comme Active Braille et Active Star) seront automatiquement synchronisés par NVDA en cas de désynchronisation de plus de 5 secondes. (#8016)
* Un geste de commande peut être assigné pour désactiver temporairement tous les déclencheurs des profils de configuration. (#4935)

### Changements

* Dans le gestionnaire des extensions, la colonne état a été modifiée pour indiquer que l'extension est activée ou désactivée plutôt que en cours d'exécution ou suspendu. (#7929)
* Mise à jour du convertisseur braille liblouis à la version 3.5.0. (#7839)
* La table braille lithuanienne a été renommée en Lithuanien 6 points pour éviter la confusion avec la nouvelle table 8 points. (#7839)
* Les tables Français (Canada) intégral et abrégé ont été supprimées. Elles sont remplacées par Français (unifié) braille littéraire 6 points et Français (unifié) abrégé respectivement. (#7839)
* Les boutons secondaires de routage sur les terminaux braille Alva BC6, EuroBraille et Papenmeier annoncent maintenant l'information de mise en forme pour le texte sous la cellule braille correspondant au bouton. (#7106)
* Les tables de saisie braille abrégé retourneront automatiquement en mode intégral dans les champs non-éditables (ex : Les contrôles où il n'y a pas de curseur ou en mode navigation). (#7306)
* NVDA est maintenant moins verbeux lorsqu'un rendez-vous ou un créneau horaire dans le calendrier Outlook couvre un jour entier. (#7949)
* Toutes les préférences de NVDA se trouvent maintenant dans un dialogue de configuration sous le Menu NVDA -> Préférences -> Paramètres, plutôt que dispersées dans de nombreux dialogues. (#577)
* La synthèse vocale par défaut sous Windows 10 est maintenant oneCore Speech plutôt qu'eSpeak. (#8176)

### Corrections de Bogues

* NVDA n'échoue plus à lire les contrôles en focus sur l'écran de connexion au compte Microsoft dans les paramètres après la saisie de l'adresse courriel. (#7997)
* NVDA n'échoue plus à lire la page après le retour à la page précédente sous Microsoft Edge. (#7997)
* Au déverrouillage de la machine, NVDA n'annonce plus incorrectement le dernier caractère du code PIN de connexion sous windows 10 . (#7908)
* Sous Chrome ou firefox, l'étiquette des cases à cocher et des boutons radio n'est plus annoncée deux fois quand on tabule où qu'on utilise les touches de navigation rapide en mode navigation. (#7960)
* Un aria-current avec une valeur false sera annoncé comme false au lieu de true (#7892).
* Le pilote du synthétiseur Windows OneCore Voices n'échoue plus au chargement si la voix configurée a été désinstallée. (#7553)
* Le changement de voix du pilote du synthétiseur Windows OneCore Voices est maintenant beaucoup plus rapide. ()#7999)
* Correction de caractères braille mal formés pour plusieurs tables braille, incluant les majuscules pour le danois abrégé 8 points. (#7526, #7693)
* NVDA peut maintenant annoncer plus de types de puces sous Microsoft Word. (#6778)
* Le déclenchement du script d'annonce de l'information de mise en forme ne modifie plus par erreur la position de revue, ainsi plusieurs activations successives ne donne plus des résultats différents. (#7869)
* La saisie braille ne permet plus d'utiliser l'abrégé dans les cas où il n'est pas supporté (ex : des mots entiers ne seront plus envoyés au système hors des zones éditables ou en mode navigation). (#7306)
* Correction des problèmes de stabilité de connexion pour les terminaux Handy Tech Easy Braille et Braille Wave . (#8016)
* Sous Windows 8 et au-delà, NVDA n'annoncera plus "inconnu" à l'ouverture du menu de liens rapides (Windows+X) et à la sélection d'un élément de ce menu. (#8137)
* Sur les terminaux Hims, les boutons de commandes spécifiques à chaque modèle fonctionnent maintenant comme indiqué dans le manuel. (#8096)
* NVDA essaiera maintenant de coriger les problèmes d'Inscription COM du système qui font que certains programmes comme Firefox et Internet Explorer deviennent inaccessibles par NVDA et annoncent "Inconnu". (#2807)
* Contournement d'un bogue dans le gestionnaire des tâches empêchant NVDA de permettre aux utilisateurs d'accéder au contenu des détails spécifiques aux processus. (#8147)
* Les nouvelles voix Microsoft SAPI5 n'accusent plus de retard en fin d'énoncé, ce qui rend beaucoup plus efficace la navigation avec ces voix. (#8174)
* NVDA ne signale plus (marques LTR et RTL) ni en Braille ni quand on se déplace vocalement par caractère, lors de l'accès à l'horloge dans les versions récentes de Windows. (#5729)
* La détection des touches de défilement sur les afficheurs Hims Smart Beetle est à nouveau plus fiable. (#6086)
* Dans certains contrôles de texte, surtout dans les applications Delphi, les informations fournies lors de l'édition et la navigation sont maintenant beaucoup plus fiables. (#636, #8102)
* Sous Windows 10 RS5, NVDA n'annonce plus d'informations redondantes quand on change de tâche avec alt+tab. (#8258)

### Changements pour les développeurs

* L'information pour le dévelopeur des objets UIA contient maintenant une liste des modèles UIA disponibles. (#5712)
* Les App modules peuvent maintenant forcer certaines fenêtres à toujours utiliser UIA en implémentant la méthode isGoodUIAWindow. (#7961)
* Le booléen caché "outputPass1Only" dans la section braille de la configuration a de nouveau été retiré. liblouis ne supporte plus l'affichage en une seule passe. (#7839)

## 2018.1.1

Ceci est une version spéciale de NVDA qui pallie à un bogue dans le pilote du synthétiseur vocal Windows OneCore, qui le faisait parler plus aigu et plus vite sous Windows 10 Redstone 4 (1803). (#8082)

## 2018.1

Points forts de cette version : support des graphiques sous Microsoft word et Powerpoint, le support de nouveaux terminaux braille : Eurobraille et le convertisseur de protocole Optelec, support amélioré des terminaux braille Hims et Optelec, améliorations de performances pour Mozilla Firefox 58 et au-delà, et bien d'autres choses.

### Nouvelles Fonctionnalités

* Il est maintenant possible d'interagir avec les diagrammes sous Microsoft Word et Microsoft Powerpoint, de la même manière que sous Microsoft Excel. (#7046)
 * sous Microsoft Word : En mode navigation, amener le curseur à un diagramme inclus et presser Entrer pour interagir avec lui.
 * Sous Microsoft Powerpoint en édition d'une diapositive : Tabuler jusqu'à un objet diagramme, et presser Entrer ou Espace pour interagir avec lui.
 * Pour cesser d'interagir avec un diagramme, presser échap.
* Nouvelle langue : Kirghize.
* Ajout du support de VitalSource Bookshelf. (#7155)
* Ajout du support du convertisseur de protocole Optelec, un mécanisme permettant d'utiliser les terminaux Braille Voyager et Satellite avec le protocole de communication ALVA BC6. (#6731)
* Il est maintenant possible d'utiliser la saisie braille avec un terminal ALVA 640 Comfort braille. (#7733)
 * Les fonctionnalités de saisie braille de NVDA peuvent être utilisées avec ceux-ci ainsi qu'avec les autres terminaux BC6 possédant le firmware 3.0.0 et au-delà.
* Support initial de Google Sheets avec le mode Braille activé. (#7935)
* Support des terminaux braille Eurobraille Esys, Esytime et Iris . (#7488)

### Changements

* Les pilotes pour les terminaux HIMS Braille Sense/Braille EDGE/Smart Beetle et Hims Sync Braille ont été remplacés par un pilote unique. Le nouveau pilote sera automatiquement activé pour les utilisateurs des anciens pilotes. (#7459)
 * Certaines touches, en particulier les touches de défilement, ont été réassignées pour respecter les conventions utilisées par les produits Hims. Veuillez consulter le guide de l'utilisateur pour plus de détails.
* Quand vous tapez sur le clavier à l'écran via l'interaction tactile, par défaut vous devez maintenant toucher deux fois chaque touche comme vous le feriez pour activer tout autre contrôle.
 * Pour utiliser le mode "frappe au toucher" où simplement lever son doigt de la touche suffit pour l'activer, activer cette option dans le nouveau dialogue Interaction Tactile du menu Préférences. (#7309)
* Il n'est plus nécessaire de joindre le braille au focus ou au curseur de revue explicitement car cela se fera automatiquement par défaut. (#2385)
 * Notez que le suivi automatique du curseur de revue ne se produira que si vous utilisez le curseur de revue ou la commande de navigation par objet. Le défilement n'activera pas ce nouveau comportement.

### Corrections de Bogues

* Les messages navigables tels que ceux affichant le formatage en cours, lors de l'appui sur NVDA+f deux fois rapidement, ne dysfonctionnent plus si NVDA est installé sur un chemin comprenant des caractères non-ASCII. (#7474)
* Le focus est maintenant restauré correctement lors du retour à Spotify à partir d'une autre application. (#7689)
* Sous Windows 10 Fall Creators Update, NVDA ne manque plus de se mettre à jour lorsque l'accès aux dossiers contrôlés est activé à partir du Centre de Sécurité de Windows Defender. (#7696)
* La détection des touches de défilement de l'afficheur Hims Smart Beetle n'est plus aléatoire. (#6086)
* Une légère amélioration de performances à l'affichage d'un contenu important sous Mozilla Firefox 58 et au-delà. (#7719)
* Sous Microsoft Outlook, la lecture de courriels contenant des tableaux ne provoque plus d'erreurs. (#6827)
* Les gestes de commandes de terminaux braille qui émulent les modificateurs de touches système peuvent maintenant être combinés avec d'autres touches émulées si un ou plusieurs des gestes émulés sont spécifiques au modèle de terminal. (#7783)
* Sous Mozilla Firefox, le mode navigation fonctionne maintenant correctement dans les fenêtres contextuelles Créées par des extensions telles que LastPass et bitwarden. (#7809)
* NVDA ne se bloque plus de temps en temps à chaque changement de focus si Firefox ou Chrome ne répondent plus en raison d'un bloquage ou d'un plantage. (#7818)
* Dans les clients Twitter tels que Chicken Nugget, NVDA n'ignorera plus les 20 derniers caractères des tweets de 280 caractères lors de la lecture. (#7828)
* NVDA utilise maintenant la langue appropriée pour l'annonce des symboles quand du texte est sélectionné. (#7687)
* Dans les versions récentes d'Office 365, il est de nouveau possible de naviguer dans les diagrammes Excel en utilisant les flèches. (#7046)
* En sortie vocale et braille, l'état des contrôles sera maintenant toujours indiqués dans le même ordre, qu'il soit positif ou négatif. #7076
* Dans les applications telles que Windows 10 Mail, NVDA ne manquera plus d'annoncer les caractères effacés lors de l'appui sur retour-arrière. (#7456)
* Toutes les touches du terminal braille Hims Braille Sense Polaris fonctionnent maintenant comme prévu. (#7865)
* NVDA n'échoue plus au démarrage sous Windows 7 à cause d'une api-ms dll interne, quand une version particulière des redistribuables de Visual Studio 2017 ont été installés par une autre application. (#7975)

### Changements pour les Développeurs

* Ajout d'un indicateur booléen caché à la section braille dans la configuration : "outputPass1Only". (#7301, #7693, #7702)
 * Cet indicateur est sur true par défaut. S'il est sur false, les règles de passage multiple de liblouis seront utilisées pour la sortie braille.
* Un nouveau dictionnaire (braille.RENAMED_DRIVERS) a été ajouté pour permettre une transition en douceur aux utilisateurs utilisant des pilotes remplacés par d'autres. (#7459)
* Le package comtypes a été mis à jour à la version 1.1.3. (#7831)
* Implémentation d'un système générique dans braille.BrailleDisplayDriver pour communiquer avec les terminaux qui envoient des paquets de confirmation. Consultez le pilote braille handyTech comme exemple. (#7590, #7721)
* Une nouvelle variable "isAppX" dans le module config peut être utilisée pour détecter si NVDA s'exécute comme une application Windows Desktop Bridge Store. (#7851)
* Pour les implémentations de document telles que NVDAObjects ou browseMode qui ont un textInfo, il existe maintenant une nouvelle classe documentBase.documentWithTableNavigation dont on peut hériter pour obtenir des scripts de navigation dans les tableaux standard. Veuillez vous référer à cette classe pour voir quelles méthodes helper doivent être fournies par votre implémentation pour que la navigation dans les tableaux fonctionne. (#7849)
* Le fichier batch scons prend maintenant mieux en compte la présence de Python 3, en utilisant le launcher pour lancer spécifiquement python 2.7 32 bit. (#7541)
* hwIo.Hid prend maintenant un paramètre additionnel exclusive, dont la valeur par défaut est True. Si initialisé à False, les autres applications peuvent accéder au périphérique quand il est connecté à NVDA. (#7859)

## 2017.4

Points forts de cette version : beaucoup de corrections et d'améliorations dans le support du web incluant le mode navigation pour les dialogues web par défaut, Meilleure annonce des étiquettes de groupes de champs en mode navigation, support de nouvelles technologies Windows 10 telles que Windows Defender Application Guard et Windows 10 sur ARM64, et l'annonce automatique de l'orientation écran et de l'état de la batterie.
Veuillez noter que cette version de NVDA ne supporte plus Windows XP et Windows Vista. Le minimum requis pour NVDA est maintenant windows 7 avec Service Pack 1.

### Nouvelles Fonctionnalités

* En mode navigation, il est maintenant possible d'aller à la fin ou au début d'une région en utilisant les commandes de saut à la fin ou au début d'un conteneur (virgule/maj+virgule). (#5482)
* Sous Firefox, Chrome et Internet Explorer, la navigation rapide vers les zones de saisie et les champs de formulaire inclut maintenant les champs texte riche (ex : contentEditable). (#5534)
* Dans les navigateurs web, La Liste d'Éléments peut maintenant lister les champs de formulaire et les boutons. (#588)
* Support initial de Windows 10 sur ARM64. (#7508)
* Support initial de la lecture et de la navigation interactive dans du contenu mathématique pour les livres Kindle avec mathématique accessible. (#7536)
* Ajout du support du lecteur de livres électroniques Azardi. (#5848)
* L'information de version des extensions est maintenant annoncée quand celles-ci sont mises à jour. (#5324)
* Ajout de nouveaux paramètres de ligne de commande pour créer une copie portable de NVDA. (#6329)
* Support de Microsoft Edge s'exécutant dans Windows Defender Application Guard sous Windows 10 Fall Creators Update. (#7600)
* S'il s'exécute sur un PC portable ou une tablette, NVDA annonce maintenant si le chargeur est connecté ou déconnecté, et quand l'orientation de l'écran change. (#4574, #4612)
* Nouvelle langue : Macédonien.
* Nouvelles tables d'affichage braille : Croate intégral, Vietnamien intégral. (#7518, #7565)
* Le support de l'afficheur braille Actilino de Handy Tech a été ajouté. (#7590)
* La saisie braille pour les afficheurs Handy Tech est maintenant supportée. (#7590)

### Changements

* Le système d'exploitation minimum supporté par NVDA est désormais Windows 7 avec Service Pack 1, ou Windows Server 2008 R2 avec Service Pack 1. (#7546)
* Les dialogues web dans les navigateurs Firefox et Chrome utilisent maintenant automatiquement le mode navigation, sauf à l'intérieur d'une application web. (#4493)
* En mode navigation, tabuler ou naviguer avec les touches de navigation rapide n'annonce plus la sortie de conteneurs tels que les listes et les tableaux, ce qui rend la navigation plus efficace. (#2591)
* En mode navigation sous Firefox ou Chrome, le nom des groupes de champs de formulaires est maintenant annoncés quand on y accède par navigation rapide ou en tabulant. (#3321)
* En mode navigation, les commandes de navigation rapide pour les objets embarqués (o et maj+o) incluent maintenant les éléments audio et vidéo ainsi que les éléments avec un rôle aria application et dialogue. (#7239)
* Espeak-ng a été mis à jour (à la version 1.49.2), Cela résout quelques problèmes dans la productions des builds. (#7385)
* À la troisième activation de la commande de lecture de la barre d'état, le contenu de celle-ci est copié dans le presse-papiers. (#1785)
* Sur un terminal Baum, l'assignation d'un geste de commande à une touche peut être limitée au modèle de terminal en cours d'utilisation (ex : VarioUltra ou Pronto). (#7517)
* Le raccourci clavier du champ de filtre de la liste d'éléments en mode navigation est passé de alt+f à alt+e. (#7569)
* Une commande non assignée a été ajoutée pour activer/désactiver l'inclusion des tables de disposition à la volée en mode navigation. Vous trouverez cette commande dans la catégorie Mode Navigation du dialogue Gestes de commandes. (#7634)
* Mise à jour du traducteur braille liblouis à la version 3.3.0. (#7565)
* Le raccourci clavier du bouton radio d'expression régulière dans la boîte de dialogue du dictionnaire est passé de alt+r à alt+e (interface en anglais). (#6782)
* Les fichiers de dictionnaires vocaux sont maintenant versionnés et ont été déplacés vers le répertoire 'speechDicts/voiceDicts.v1'. (#7592)
* Les modifications des fichiers versionnés (configuration utilisateur, dictionnaires vocaux) ne sont plus sauvegardés quand NVDA est exécuté depuis le lanceur. (#7688)
* Les afficheurs braille Handy Tech Braillino, Bookworm et Modular (avec un ancien microprogramme) ne sont plus supportés nativement. Veuillez installer le pilote universel Handy Tech et l'extension NVDA pour utiliser ces afficheurs. (#7590)

### Corrections de Bogues

* Les liens sont maintenant indiqués en braille dans les applications telles que Microsoft Word. (#6780)
* NVDA ne ralentit plus notablement quand beaucoup d'onglets sont ouverts dans les navigateurs Firefox ou Chrome. (#3138)
* Le routage curseur pour l'afficheur braille MDV Lilli ne se positionne plus incorrectement une cellule plus loin que la position prévue. (#7469)
* Sous Internet Explorer et autres documents MSHTML, l'attribut HTML5 requis pour indiquer l'état d'un champ de formulaire est maintenant supporté. (#7321)
* Les afficheurs braille sont maintenant mis à jour quand on tape des caractères Arabes dans un document WordPad aligné à gauche (#511).
* Sous Mozilla Firefox, les étiquettes Accessibles des contrôles sont maintenant annoncées plus facilement en mode navigation quand l'étiquette n'apparaît pas elle-même comme un contenu. (#4773)
* Sous windows 10 Creators Update, NVDA peut de nouveau accéder à Firefox après un redémarrage de NVDA. (#7269)
* Quand on redémarre NVDA avec Mozilla Firefox en focus, le mode navigation reste disponible, bien que vous puissiez avoir besoin de quitter la fenêtre et d'y revenir. (#5758)
* Il est maintenant possible d'accéder à du contenu mathématique sous Google Chrome sur un système où Mozilla Firefox n'est pas installé. (#7308)
* Le système d'exploitation et les autres applications devraient être plus stables juste après l'installation de NVDA avant de redémarrer le système, comparativement aux versions précédentes de NVDA. (#7563)
* Quand on utilise une commande de reconnaissance de contenu (ex : NVDA+r), NVDA annonce maintenant un message d'erreur si l'objet navigateur a disparu. (#7567)
* La fonction de défilement arrière a été corrigée pour les afficheurs Freedom Scientific comportant une barre de stickers gauche. (#7713)

### Changements pour les Développeurs

* "scons tests" vérifie maintenant que les chaînes traduisibles ont des commentaires pour les traducteurs. Vous pouvez exécuter seulement cette vérification par "scons checkPot". (#7492)
* Il y a maintenant un nouveau module extensionPoints qui fournit une infrastructure générique pour permettre des extensions de code à certains points spécifique dans le code. Cela permet aux parties intéressées de s'enregistrer pour être notifiées quand une action se produit (extensionPoints.Action), pour modifier un type particulier de données (extensionPoints.Filter) ou pour participer à la décision pour savoir si quelque chose doit être fait (extensionPoints.Decider). (#3393)
* Vous pouvez maintenant vous enregistrer pour être averti lors d'un changement de profil de configuration via l'Action config.configProfileSwitched. (#3393)
* Les gestes pour afficheur braille qui émulent des modificateurs de touches du clavier du système (comme contrôle et alt) peuvent maintenant être combinées avec d'autres touches émulées sans définition explicite. (#6213)
 * Par exemple : si vous avez sur votre afficheur une touche affectée à la touche alt et une autre à flècheBas, la combinaison de ces touches résultera en émulation de alt+flècheBas.
* La classe braille.BrailleDisplayGesture possède maintenant une propriété model. si elle est fournie, l'appui d'une touche générera un identificateur additionnel de geste spécifique au modèle de terminal. Cela permet à l'utilisateur d'affecter des gestes commande spécifiques limités à un modèle de terminal.
 * Pour un exemple de cette nouvelle fonctionnalité, regardez le pilote Baum.
* NVDA est maintenant compilé avec Visual Studio 2017 et le SDK Windows 10. (#7568)

## 2017.3

Les points forts de cette version incluent la saisie en braille abrégé, le support des nouvelles voix OneCore Voices disponibles sous Windows 10, le support de la reconnaissance de caractères intégrée à Windows 10, et beaucoup d'améliorations significatives touchant le braille et le web.

### Nouvelles Fonctionnalités

* Un paramètre Braille a été ajouté pour "afficher les messages indéfiniment". (#6669)
* Dans les listes de messages sous Microsoft Outlook, NVDA signale maintenant si un message est marqué. (#6374)
* Sous Microsoft Powerpoint, le type exact d'une forme est maintenant annoncé quand on édite une diapositive (Exemples : triangle, cercle, vidéo, flèche), plutôt que juste "forme". (#7111)
* Le contenu mathématique (fourni par MathML) est maintenant supporté sous Google Chrome. (#7184)
* NVDA peut maintenant parler en utilisant les nouvelles voix Windows OneCore (aussi connues sous le nom mobile voices) incluses dans Windows 10. Vous y avez accès en sélectionnant voix Windows OneCore dans le dialogue Synthétiseurs de NVDA. (#6159)
* Les fichiers de configuration utilisateur de NVDA peuvent maintenant être enregistrés dans le dossier local application data de l'utilisateur. Ceci est activé via un paramètre dans le registre. Veuillez consulter 'paramètres système' dans le guide de l'utilisateur pour plus de détails. (#6812)
* Dans les navigateurs internet, NVDA signale maintenant les valeurs d'espaces réservés pour les champs (en particulier, aria-placeholder est maintenant supporté). (#7004)
* En mode navigation sous Microsoft Word, il est maintenant possible d'atteindre les fautes d'orthographe en utilisant les touches de navigation rapide (w et maj+w) (#6942)
* Ajout du support du contrôle de sélection de date qu'on trouve dans les dialogues de rendez-vous de Microsoft Outlook. (#7217)
* Dans l'application Courrier de Windows 10, la suggestion sélectionnée est maintenant annoncée pour les champs à/cc, et il en va de même pour le champ de recherche des paramètres de Windows 10. (#6241)
* Un son est maintenant émis pour indiquer l'apparition d'une suggestion dans certains champs de recherche de Windows 10 (ex : écran de démarrage, recherche de paramètres, champs à/cc de Windows 10 courrier). (#6241)
* Annonce automatique des notifications sous Skype for Business Desktop, par exemple quand quelqu'un démarre une conversation avec vous. (#7281)
* Annonce automatique des messages de discussion instantannée dans une conversation sous Skype for Business. (#7286)
* Annonce automatique des notifications sous Microsoft Edge, par exemple lorsqu'un téléchargement démarre. (#7281)
* Vous pouvez maintenant taper en braille intégral ou abrégé depuis un terminal braille avec un clavier braille. Veuillez consulter la section Saisie en Braille du Guide de l'Utilisateur pour les détails. (#2439)
* Vous pouvez maintenant entrer des caractères braille unicode depuis le clavier braille d'un terminal braille en sélectionnant Braille Unicode comme table de saisie dans les Paramètres Braille. (#6449)
* Ajout du support du terminal braille SuperBraille utilisé à Taiwan. (#7352)
* Nouvelles tables de traduction braille : Danois braille informatique 8 points, Lithuanien, Perse braille informatique 8 points, Perse intégral, Slovène braille informatique 8 points. (#6188, #6550, #6773, #7367)
* Amélioration de la table Anglaise (U.S.) braille informatique 8 points , incluant le support des puces, du signe euro et des lettres accentuées. (#6836)
* NVDA peut maintenant utiliser la fonctionnalité de reconnaissance de caractères incluse dans Windows 10 pour reconnaître le texte d'images ou d'applications inaccessibles. (#7361)
 * La langue peut être définie dans le nouveau dialogue Reconnaissance de Caractères de Windows 10 dans les Préférences de NVDA.
 * Pour reconnaître le contenu de l'objet navigateur courant, pressez NVDA+r.
 * Veuillez consulter la section Reconnaissance de Contenu du Guide de l'Utilisateur pour plus de détails.
* Vous pouvez maintenant choisir les informations contextuelles affichées sur un terminal braille quand un objet prend le focus en utilisant le nouveau paramètre "Présentation contextuelle du focus" dans le dialogue Paramètres Braille. (#217)
 * Par exemple, les options "Afficher lors des changements contextuels" ou "Seulement lors d'un défilement arrière" peuvent rendre le travail avec les menus et les listes plus efficace, puisque les éléments ne changeront pas continuellement de position sur l'afficheur.
 * Veuillez consulter la section concernant le paramètre de "présentation contextuelle du focus" du Guide de l'Utilisateur pour plus de détails et des exemples.
* Sous Firefox et Chrome, NVDA supporte maintenant les tableaux dynamiques complexes tels que les feuilles de calcul quand seule une partie du contenu est chargée ou affichée (spécifiquement, les attributs aria-rowcount, aria-colcount, aria-rowindex et aria-colindex introduits avec ARIA 1.1). (#7410)

### Changements

* Une commande non affecté a été ajoutée pour redémarrer NVDA à la demande. Vous la trouverez dans la catégorie Divers du dialogue Gestes de commandes. (#6396)
* La configuration clavier peut maintenant être choisie dans le dialogue de bienvenue à NVDA. (#6863)
* Beaucou plus de contrôles et d'états ont été abrégés pour le braille. Les rpères ont aussi été abrégés. Veuillez consulter "Abbréviations de Contrôles, États et Repères" sous Braille dans le Guide de l'Utilisateur pour une liste complète. (#7188)
* Mise à jour de Espeak-ng à la version 1.49.1 (#7280).
* Les tables d'affichage et de saisie sont maintenant triées dans l'ordre alphabétique dans le dialogue Paramètres Braille. (#6113)
* Mise à jour du convertisseur braille liblouis à la version 3.2.0. (#6935)
* La table braille par défaut est maintenant le code Anglais unifié intégral. (#6952)
* Par défaut, NVDA n'affiche maintenant que la partie de l'information contextuelle qui a changé quand un objet prend le focus. (#217)
 * Précédemment, il affichait toujours autant d'information que possible, sans se préoccuper de savoir si vous aviez déjà vu ces mêmes informations avant.
 * Vous pouvez retrouver l'ancien comportement en modifiant le nouveau paramètre "Présentation contextuelle du focus" dans le dialogue Paramètres Braille à "Toujours afficher".
* En Braille, le curseur peut être configuré pour avoir une forme différente quand on suit le focus ou la revue. (#7112)
* Le logo de NVDA a été modernisé. Le nouveau logo DE NVDA est un mélange stylisé des lettres NVDA en blanc, sur un fond violet unié. Cela assure qu'il sera visible sur n'importe quelle couleur de fond, et il utilise le violet du logo NVAccess. (#7446)

### Corrections de Bogues

* Les éléments div éditables sous Chrome n'ont plus leur étiquette annoncée comme leur valeur en mode navigation. (#7153)
* L'appui sur fin en mode navigation dans un document Microsoft Word vide ne provoque plus une erreur d'exécution. (#7009)
* Le mode navigation est maintenant correctement supporté sous Microsoft Edge dans le cas où un document a reçu un rôle ARIA spécifique de Document. (#6998)
* En mode navigation, vous pouvez maintenant sélectionner ou désélectionner jusqu'à la fin de la ligne en utilisant maj+fin même si le curseur est sur le dernier caractère de la ligne. (#7157)
* Si un dialogue contient une barre de progression, le texte du dialogue est maintenant mis à jour quand la barre de progression évolue. Cela signifie, par exemple, que le temps restant peut maintenant être lu dans le dialogue de téléchargement de mise à jour de NVDA. (#6862)
* NVDA annonce maintenant les changements de sélection pour certaines listes déroulantes de Windows 10 telles que Lecture automatique dans les Paramètres. (#6337).
* Les informations sans objet ne sont plus annoncées quand on entre dans les dialogues de création de réunions ou rendez-vous de Microsoft Outlook. (#7216)
* Les bips indiquant les barres de progression indéterminées (ex : dialogue de vérification des mises à jour) ne sont émis que si le suivi des barres de progression est configuré pour émettre des bips. (#6759)
* Sous Microsoft Excel 2003 et 2007, les cellules sont de nouveau annoncées quand on se déplace avec les flèches dans une feuille de calcul. (#8243)
* Sous Windows 10 Creators update et au-delà, on s'assure que le mode navigation est activé automatiquement quand on lit des courriels sous l'application Courrier de Windows 10. (#7289)
* Sur la plupart des afficheurs braille possédant un clavier braille, le point 7 efface maintenant le dernier caractère entré, et le point 8 presse la touche entrer. (#6054)
* Dans un texte éditable, quand on déplace le curseur (ex : avec les touches de manipulation du curseur ou avec retour-arrière), le retour parlé de NVDA est maintenant plus précis dans beaucoup de cas, en particulier sous Chrome et les applications en mode terminal. (#6424)
* Le contenu de l'Éditeur de Signature sous Microsoft Outlook 2016 peut maintenant être lu. (#7253)
* Dans les applications Java Swing, NVDA ne provoque plus de plantages quand on navigue dans les tableaux. (#6992)
* Sous Windows 10 Creators Update, NVDA n'annonce plus les notifications plusieurs fois. (#7128)
* Dans le menu Démarrer sous Windows 10, l'appui sur Entrer pour fermer le menu après une recherche ne provoque plus l'annonce du texte recherché par NVDA. (#7370)
* La recherche des titres en navigation rapide sous Microsoft Edge est maintenant nettement plus rapide. (#7343)
* Sous Microsoft Edge, la navigation en mode navigation ne saute plus de grandes parties de certaines pages telles que le thème Wordpress 2015. (#7143)
* Sous Microsoft Edge, les régions sont correctement nommées dans les langues autres que l'Anglais. (#7328)
* Le braille suit maintenant correctement la sélection quand on sélectionne du texte au-delà de la largeur de l'écran. Par exemple, si vous sélectionnez plusieurs lignes avec maj+flècheBas, le braille montre maintenant la dernière ligne que vous avez sélectionnée. (#5770)
* Sous Firefox, NVDA n'annonce plus par erreur " section " plusieurs fois quand on ouvre les détails d'un tweet sur twitter.com. (#5741)
* En Mode Navigation, les commandes de navigation de tableaux ne sont plus disponibles pour les tables de visualisation sauf si l'annonce des tables de visualisation est activée. (#7382)
* Sous Firefox et Chrome, les commandes de navigation de tableaux sautent maintenant les cellules cachées. (#6652, #5655)

### Changement pour les Développeurs

* Dans le journal, les timestamps incluent maintenant les millisecondes. (#7163)
* NVDA doit maintenant être construit avec Visual Studio Community 2015. Visual Studio Express n'est plus supporté. (#7110)
 * Windows 10 Tools et SDK sont aussi requis, ce qui peut être activé à l'installation de Visual Studio.
 * Consultez la section Dépendances Installées du fichier readme pour plus de détails.
* Le support de reconnaisseurs de contenu tels que les OCR et les descripteurs d'image peuvent être facilement implémentés en utilisant le nouveau package contentRecog. (#7361)
* Le package Python json est maintenant inclus dans les constructions binaires de NVDAs. (#3050)

## 2017.2

Les points forts de cette versions incluent le support intégral de l'atténuation audio sous Windows 10 Creators Update; la correction de plusieurs problèmes de sélection en mode navigation, incluant les problèmes pour sélectionner tout; des améliorations significatives dans le support de Microsoft Edge; et des améliorations sur le web tels que l'indication des éléments marqués comme en cours (en utilisant aria-current).

### Nouvelles Fonctionnalités

* Sous Microsoft Excel, l'information de bordure de cellule peut maintenant être annoncée en utilisant NVDA+f. (#3044)
* Dans les navigateurs web, NVDA indique maintenant quand un élément a été marqué comme courant (spécifiquement, en utilisant l'attribut aria-current). (#6358)
* Le changement de langue automatique est maintenant supporté sous Microsoft Edge. (#6852)
* Ajout du support de la Calculatrice Windows sous Windows 10 Enterprise LTSB (Long-Term Servicing Branch) et Server. (#6914)
* Effectuer la commande de lecture de la ligne courante trois fois rapidement épelle la ligne en code international. (#6893)
* Nouvelle langue : Birman.
* Les flèches haute et basse et les symboles de fractions unicodes sont maintenant annoncés correctement. (#3805)

### Changements

* Quand on navigue en revue simple dans les applications utilisant UI Automation, davantage d'objets irrelevants sont ignorés rendant la navigation plus facile. (#6948, #6950)

### Corrections de Bogues

* Les éléments de menu dans les pages web peuvent maintenant être activés en mode navigation. (#6735)
* L'appui sur échap quand le dialogue de confirmation d'effacement de profil est actif ferme maintenant le dialogue. (#6851)
* Correction de quelques plantages sous Mozilla Firefox et autres applications Gecko quand le multi-process est activé. (#6885)
* L'annonce de la couleur d'arrière-plan en revue d'écran est maintenant plus fiable quand le texte est affiché avec un arrière-plan transparent. (#6467)
* Amélioration du support de aria-describedby sous Internet Explorer 11, incluant son support dans les cadres et quand de multiples IDs sont fournis. (#5784)
* Sous Windows 10 Creators Update, l'atténuation audio de NVDA fonctionne de nouveau comme sous les versions précédentes de Windows (Tous les modes sont de nouveau disponibles). (#6933)
* NVDA n'échouera plus à annoncer ou naviguer vers certains contrôles (UIA) pour lesquels un raccourci clavier n'est pas défini. (#6779)
* Deux espaces ne sont plus ajoutés dans les informations de raccourcis clavier pour certains contrôles (UIA). (#6790)
* Certaines combinaisons de touches sur les afficheurs HIMS (ex: espace+point4) n'échouent plus de façon intermittente. (#3157)
* Correction d'un problème à l'ouverture d'un port série sur des systèmes utilisant certaines langues autres que l'Anglais qui rendait la connexion à un terminal braille impossible dans certains cas. (#6845)
* Réduction des chances que le fichier de configuration soit corrompu à la fermeture de Windows. Les fichiers de configuration sont maintenant écrits dans un fichier temporaire avant de remplacer le fichier de configuration réel. (#3165)
* Quand on effectue la commande de lecture de la ligne courante deux fois rapidement pour épeler la ligne, la langue appropriée est maintenant utilisée pour épeler les caractères. (#6726)
* Naviguer par ligne sous Microsoft Edge est maintenant jusqu'à trois fois plus rapide sous Windows 10 Creators Update. (#6994)
* NVDA n'annonce plus "Web Runtime grouping" quand on met le focus sur un document Microsoft Edge sous Windows 10 Creators Update (#6948)
* Toutes les versions existantes de SecureCRT sont maintenant supportées. (#6302)
* Adobe Acrobat Reader ne se plante plus dans certains documents PDF (en particulier, ceux qui contiennent des attributs ActualText vides). (#7021, #7034)
* En mode navigation sous Microsoft Edge, les tableaux interactifs (ARIA grids) ne sont plus ignorés quand on navigue entre les tableaux par t et maj+t. (#6977)
* En mode navigation, l'appui sur maj+début après une sélection avant désélectionne maintenant jusqu'au début de la ligne comme prévu. (#5746)
* En mode navigation, sélectionner tout (contrôle+a) n'échoue plus à sélectionner tout le texte si le curseur n'est pas au début du texte. (#6909)
* Correction de quelques autres problèmes rares de sélection en mode navigation. (#7131)

### Changements pour les Développeurs

* Les arguments de ligne de commande sont maintenant traités par le module Python argparser, au lieu de optparse. Cela permet de traiter certaines options telles que -r et -q de manière exclusive. (#6865)
* core.callLater ajoute maintenant le callback à la queue principale de NVDA après le délai donné, plutôt que de réveiller le noyau et de l'exécuter directement. Ceci empêche de possibles bloquages dus au fait que le noyau se mette accidentellement en veille après le traitement d'un callback, au milieu d'un appel modal tel que l'affichage d'une boîte de message. (#6797)
* La propriété InputGesture.identifiers a été modifiée de manière à ne plus être normalisée. (#6945)
 * Les sous-classes n'ont plus besoin de normaliser les identifiants avant de les retourner de cette propriété.
 * Si vous voulez des identifiants normalisés, il y a maintenant une propriété InputGesture.normalizedIdentifiers qui normalise les identifiants retournés par la propriété des identifiants.
* La propriété InputGesture.logIdentifier est maintenant obsolète. Les appels devraient maintenant utiliser InputGesture.identifiers[0] en remplacement. (#6945)
* Du code obsolète a été supprimé :
 * Les constantes `speech.REASON_*`, remplacées par `controlTypes.REASON_*`. (#6846)
 * `i18nName` pour les paramètres synthétiseur, remplacées par `displayName` et `displayNameWithAccelerator`. (#6846, #5185)
 * `config.validateConfig`. (#6846, #667)
 * `config.save`: remplacé par `config.conf.save`. (#6846, #667)
* La liste des complétions dans le menu contextuel d'autocomplétion de la Console Python ne montre plus aucun chemin menant au symbole final à compléter. (#7023)
* Il y a maintenant une architecture de test unitaire pour NVDA. (#7026)
 * Les tests unitaires et l'infrastructure sont situés dans le répertoire tests/unit. veuillez consulter le docstring dans le fichier tests\unit\init.py pour plus de détails.
 * Vous pouvez exécuter les tests en utilisant "scons tests". Veuillez consulter la section "Running Tests" de readme.md pour plus de détails.
 * Si vous soumettez une pull request pour NVDA, vous devriez d'abord exécuter les tests et vous assurer qu'ils passent.

## 2017.1

Les points forts de cette version incluent l'annonce des sections et des colonnes de texte sous Microsoft Word; Le support de la lecture, navigation et annotation des livres sous Kindle pour PC; et un support amélioré de Microsoft Edge.

### Nouvelles Fonctionnalités

* Dans Microsoft Word le type de saut de section, et le numéro de section peuvent maintenant être signalés. Ceci s'active grâce à l'option "annoncer les numéros de page" dans le dialogue Mise en Forme des Documents. (#5946)
* Sous Microsoft Word les colonnes de texte peuvent maintenant être signalées. Ceci s'active grâce à l'option "Annoncer les numéros de page" dans le dialogue Mise en forme des documents. (#5946)
* Le changement automatique de langue est maintenant supporté sous Wordpad. (#6555)
* La commande de recherche de NVDA (NVDA+control+f) est maintenant supportée en mode navigation sous Microsoft Edge. (#6580)
* La navigation rapide vers les boutons en mode navigation (b et maj+b) est maintenant supportée sous Microsoft Edge. (#6577)
* Quand on copie une feuille sous Microsoft Excel, les titres de lignes et colonnes définis sont conservés. (#6628)
* Support de la lecture et de la navigation pour les livres sous Kindle pour PC version 1.19, incluant l'accès aux liens, notes de bas de page, graphiques, texte surligné et notes de l'utilisateur. Veuillez consulter la section Kindle pour PC du guide de l'utilisateur NVDA pour plus d'information. (#6247, #6638)
* La navigation dans les tableaux en mode navigation est maintenant supportée sous Microsoft Edge. (#6594)
* Sous Microsoft Excel, la commande d'annonce de position du curseur de revue (ordinateur de bureau : NVDA+pavnumEffacement, ordinateur portable : NVDA+effacement) annonce maintenant le nom de la feuille de calcul et la position de la cellule. (#6613)
* Ajout d'une option au dialogue de sortie permettant de redémarrer avec le journal en mode débogage. (#6689)

### Changements

* La vitesse minimale de clignotement du curseur braille est maintenant de 200ms. Si une valeur inférieure a été définie, elle sera augmentée à 200ms. (#6470)
* Une case à cocher a été ajoutée au dialogue paramètres braille pour permettre l'activation ou la désactivation du clignotement du curseur braille. Précédemment, une valeur de 0 était utilisée pour réaliser cela. (#6470)
* Mise à jour de eSpeak NG (commit e095f008, 10 Janvier 2017). (#6717)
* En raison de changements dans la mise à jour Creators Update de Windows 10, le mode "toujours atténué' a été retiré des paramètres d'atténuation audio de NVDA. Il est toujours disponible dans les versions plus anciennes de Windows 10. (#6684)
* En raison de changements dans la mise à jour Creators Update de Windows 10, le mode 'Atténuer les autres sources quand NVDA parle' ne peut plus s'assurer que les autres sources ont été complètement atténuées avant le début de la parole et ne pourra pas non plus conserver l'atténuation assez longtemps après la fin de la parole. Ceci n'affecte pas les versions plus anciennes de Windows 10. (#6684)

### Corrections de Bogues

* Correction du bloquage sous Microsoft Word quand on se déplace par paragraphe dans un gros document en mode navigation. (#6368)
* Sous Microsoft Word, les tableaux copiés depuis Microsoft Excel ne sont plus traités comme des tableaux de disposition, et ainsi ne sont plus ignorés. (#5927)
* Quand on essaie d'entrer des caractères sous Microsoft Excel dans une vue protégée, NVDA produit maintenant un son plutôt que de dire les caractères qui ne sont pas acceptés. (#6570)
* Sous Microsoft Excel, l'appui sur échap ne fait plus passer en mode navigation, à moins que l'utilisateur ne soit passé explicitement en mode navigation par NVDA+espace puis soit entré en mode formulaire en pressant entrer sur un champ de formulaire. (#6569)
* NVDA ne se bloque plus dans les feuilles de calcul Microsoft Excel quand une ligne ou une colonne entière est fusionnée. (#6216)
* L'annonce de texte détouré ou trop large dans les cellules sous Microsoft Excel devrait maintenant être plus fiable (#6472)
* NVDA signale maintenant quand une case à cocher est en lecture seule. (#6563)
* Le lanceur de NVDA n'affichera plus un dialogue d'avertissement quand il ne peut jouer le son de démarrage en raison de l'indisponibilité d'un dispositif audio. (#6289)
* Dans le ruban de Microsoft Excel, les contrôles indisponibles sont maintenant annoncés comme tel. (#6430)
* NVDA m'annoncera plus "Fenêtre" quand on minimise les fenêtres. (#6671)
* Support de l'écho clavier par caractères dans les applications Universal Windows Platform (incluant Microsoft Edge) sous Windows 10 Creators Update. (#6017)
* Le suivi de la souris fonctionne maintenant pour tous les écrans sur les ordinateurs avec plusieurs moniteurs. (#6598)
* NVDA ne devient plus inutilisable après avoir quitté Windows Media Player alors que le focus était sur un potentiomètre. (#5467)

### Changements pour les Développeurs

* Les fichiers de profils et de configurations sont maintenant automatiquement mis à jour pour satisfaire aux changements de schéma. En cas d'erreur durant la mise à jour, une notification est affichée, la configuration est réinitialisée, et l'ancien fichier de configuration est disponible dans le journal de NVDA au niveau 'Info'. (#6470)

## 2016.4

Les points fort de cette version incluent un support amélioré de Microsoft Edge; le mode navigation dans l'application Courrier de Windows 10; et des améliorations significatives dans les dialogues de NVDA.

### Nouvelles Fonctionnalités

* NVDA peut maintenant indiquer le retrait des lignes par des sons. Ceci peut être configuré en utilisant la liste déroulante "annoncer les retraits de ligne par" dans le dialogue Mise en Forme des Documents de NVDA. (#5906)
* Support de l'afficheur braille Orbit Reader 20. (#6007)
* Une option permettant d'ouvrir la visionneuse de parole au démarrage a été ajoutée. Elle peut être activée via une case à cocher dans la fenêtre de la visionneuse de parole. (#5050)
* Quand on rouvre la fenêtre de la visionneuse de parole, sa position et ses dimensions sont maintenant restaurées. (#5050)
* Les champs de Renvoi sous Microsoft Word sont maintenant traités comme des liens hypertexte. Ils sont annoncés comme des liens et peuvent être activés. (#6102)
* Support des afficheurs braille Baum SuperVario2, Baum Vario 340 et HumanWare Brailliant2. (#6116)
* Support initial de la mise à jour anniversaire de Microsoft Edge. (#6271)
* Le mode navigation est maintenant utilisé pour la lecture des courriels dans l'application mail de Windows 10. (#6271)
* Nouvelle langue : Lithuanien.

### Changements

* Convertisseur braille liblouis mis à jour à la version 3.0.0. Cela inclut des améliorations significatives du Braille Anglais Unifié. (#6109, #4194, #6220, #6140)
* Dans le Gestionnaire de Modules Complémentaires, les boutons Activer le module et Désactiver le module ont maintenant des raccourcis clavier (alt+d et alt+d, respectivement). (#6388)
* Dans les dialogues de NVDA, divers problèmes de remplissage et d'alignement ont été résolus. (#6317, #5548, #6342, #6343, #6349)
* Le dialogue de mise en forme des documents a été ajusté pour que le contenu puisse défiler. (#6348)
* Ajustement de la disposition du dialogue Prononciation des symboles pour que toute la largeur du dialogue soit utilisée pour la liste des symboles. (#6101)
* En mode navigation dans les navigateurs internet, les commandes de navigation vers les zones d'édition (e et maj+e) et les champs de formulaire (f et maj+f) peuvent maintenant atteindre les champs en lecture seule. (#4164)
* Dans le dialogue Mise en Forme des Documents de NVDA, "Annoncer les changements de mise en forme après le curseur" a été renommé en "Signaler les changements de mise en forme après le curseur", puisque cela affecte le braille autant que la voix. (#6336)
* Amélioration de l'apparence du dialogue de bienvenue de NVDA. (#6350)
* Dans les dialogues de NVDA, les boutons "Ok" et "Annuler" sont maintenant alignés à droite du dialogue. (#6333)
* Des contrôles rotatifs sont maintenant utilisés pour les champs de saisie numériques tels que le changement de la hauteur pour indiquer les majuscules dans le dialogue Paramètres Vocaux. Vous pouvez entrer une valeur ou utiliser les flèches haut et bas pour ajuster la valeur. (#6099)
* La manière dont les IFrames (documents inclus dans des documents) sont signalés a été rendue plus cohérente entre les différents navigateurs. Les IFrames sont maintenant signalés comme "cadre" sous Firefox. (#6047)

### Corrections de Bogues

* Correction d'une erreur rare quand on ferme NVDA avec la visionneuse de parole ouverte. (#5050)
* Les images interactives sont maintenant rendues comme prévu en mode navigation sous Mozilla Firefox. (#6051)
* Dans le dialogue des dictionnaires, l'appui sur la touche entrée sauvegarde maintenant les changements et ferme le dialogue. Précédemment, l'appui sur entrée n'avait aucun effet. (#6206)
* Les messages sont maintenant affichés en braille quand on change de mode de saisie pour une méthode de saisie (saisie native/alphanumérique, mode plein/mode demi, etc.). (#5892, #5893)
* Quand on désactive et réactive immédiatement un module complémentaire ou vice versa, l'état du module retourne maintenant correctement à sa valeur précédente. (#6299)
* Sous Microsoft Word, les numéros de page dans les titres peuvent maintenant être lus. (#6004)
* La souris peut maintenant être utilisée pour déplacer le focus entre la liste des symboles et les champs de saisie dans le dialogue prononciation des symboles. (#6312)
* Sous Microsoft Word en mode navigation, Correction d'un problème qui empêche la liste d'éléments d'apparaître quand le document contient un lien hypertexte invalide. (#5886)
* Après sa fermeture via la barre des tâches ou le raccourci alt+F4, l'état de la case à cocher de la visionneuse de parole dans le menu NVDA reflètera maintenant la visibilité réel de la fenêtre. (#6340)
* La commande de rechargement des modules complémentaires ne causse plus de problèmes aux profils de configuration déclenchés, aux nouveaux documents dans les navigateurs web et à la revue d'écran. (#2892, #5380)
* Dans la liste de langues du dialogue Paramètres Généraux de NVDA, les langues tel que l'Aragonais sont maintenant correctement affichées sous Windows 10. (#6259)
* Les touches système émulées (ex : Un bouton sur un afficheur braille émulant la touche tab) sont maintenant présentées dans la langue configurée pour NVDA dans l'aide à la saisie et le dialogue Gestes de Commandes. Avant, elles étaient toujours présentées en Anglais. (#6212)
* Changer la langue de NVDA (depuis le dialogue Paramètres Généraux) n'a maintenant plus d'effet avant le redémarrage de NVDA. (#4561)
* Le champ "modèle" d'une nouvelle entrée de dictionnaire ne peut plus être laissé à blanc. (#6412)
* Correction d'un problème rare durant la recherche des ports série sur certains systèmes qui rendait certains pilotes d'afficheurs braille inutilisables. (#6462)
* Sous Microsoft Word, les puces numérotées sont maintenant annoncées dans les tableaux quand on se déplace par cellule. (#6446)
* Il est maintenant possible d'assigner des gestes de commandes pour le pilote d'afficheurs braille Handy Tech dans le dialogue Gestes de Commandes de NVDA. (#6461)
* Sous Microsoft Excel, l'appui sur entrée ou sur entrée du pavé numérique quand on navigue dans une feuille de calcul annonce maintenant navigation à la ligne suivante. (#6500)
* iTunes ne se bloque plus de façon intermittente quand on utilise le mode navigation pour l'iTunes Store, Apple Music, etc. (#6502)
* Correction des plantages dans les applications Mozilla 64 bits et les applications basées sur Chrome. (#6497)
* Sous Firefox avec multi-processus activé, le mode navigation et les champs d'édition fonctionnent maintenant correctement. (#6380)

### Changements pour les Développeurs

* Il est maintenant possible de fournir des modules applicatifs pour les exécutables contenant un point (.) dans leur nom. Les points sont remplacés par des soulignés (_). (#5323)
* Le nouveau module gui.guiHelper inclut des utilitaires pour simplifier la création d'interfaces utilisateur graphiques wxPython, incluant la gestion automatique de l'espacement. Cela apporte une meilleure cohérence et apparence visuelle, ainsi que la simplification dans la création d'interfaces graphiques pour les développeurs non-voyants. (#6287)

## 2016.3

Les points forts de cette version incluent la possibilité de désactiver individuellement les modules complémentaires; le support des champs de formulaire sous Microsoft Excel; des améliorations significatives de l'annonce des couleurs; des corrections et améliorations concernant plusieurs afficheurs braille; et des corrections et améliorations du support de Microsoft Word.

### Nouvelles Fonctionnalités

* Le mode navigation peut maintenant être utilisé pour lire les documents PDF sous Microsoft Edge dans la mise à jour anniversaire de Windows 10. (#5740)
* Les biffures et doubles-biffures sont maintenant annoncées si approprié sous Microsoft Word. (#5800)
* Sous Microsoft Word, le titre d'un tableau est maintenant annoncé si un titre a été donné. Si description il y a, elle sera accessible à l'aide de la commande d'ouverture de description longue, (NVDA+d) en mode navigation. (#5943)
* Sous Microsoft Word, NVDA annonce maintenant l'information de position quand on déplace des paragraphes (alt+maj+flècheBasse et alt+maj+flècheHaute). (#5945)
* Sous Microsoft Word, l'interligne est maintenant annoncé via la commande d'annonce de formatage de NVDA, quand on le change par divers raccourcis clavier de Microsoft word, et quand on se déplace dans un texte avec différents interlignes si l'annonce des interlignes est activée dans le dialogue Mise en Forme des Documents de NVDA. (#2961)
* Sous Internet Explorer, les éléments structurants HTML 5 sont maintenant reconnus. (#6044)
* L'annonce des commentaires (comme sous Microsoft Word) peut maintenant être désactivée via une case à cocher Annoncer les Commentaires dans le dialogue Mise en Forme des Documents de NVDA. (#5108)
* Il est maintenant possible de désactiver un module individuellement dans le gestionnaire de modules complémentaires. (#3090)
* Des assignations de touches supplémentaires ont été ajoutées pour les afficheurs braille ALVA BC640/680 series. (#5206)
* Il y a maintenant une commande pour amener l'afficheur braille au focus courant. Actuellement, seul les terminaux ALVA BC640/680 ont une touche assignée à cette commande, mais elle peut être assignée manuellement pour les autres afficheurs dans le Dialogue Gestes de Commandes si besoin. (#5250)
* Sous Microsoft Excel, vous pouvez maintenant interagir avec les champs de formulaires. Allez aux champs de formulaires en utilisant la liste d'éléments ou la navigation par lettre en mode navigation. (#4953)
* Vous pouvez maintenant assigner un geste de commande pour activer ou désactiver le mode de revue simple en utilisant le dialogue Gestes de Commandes. (#6173)

### Changements

* NVDA annonce maintenant les couleurs en utilisant un jeu basique clair de 9 teintes et 3 tons, avec des variations de brillance et paleur, ceci pour ne pas utiliser des noms de couleurs plus subjectifs et moins clairs. (#6029)
* Le comportement de NVDA+F9 suivi de NVDA+F10 a été modifié pour sélectionner le texte au premier appui sur F10. Quand f10 est pressé deux fois rapidement, le texte est copié dans le presse-papiers. (#4636)
* ESpeakNG mis à jour à la version Master 11b1a7b (22 Juin 2016). (#6037)

### Corrections de Bogues

* En mode navigation sous Microsoft Word, la copie dans le presse-papiers préserve maintenant le formatage. (#5956)
* Sous Microsoft Word, NVDA annonce maintenant correctement quand on utilise les commandes de navigation dans les tableaux propres à Word (alt+début, alt+fin, alt+pagePrec et alt+pageSuiv) et les commandes de sélection dans les tableaux (maj ajouté aux commandes de navigation). (#5961)
* Dans les dialogues de Microsoft Word, la navigation par objet de NVDA a été grandement améliorée. (#6036)
* Dans certaines applications comme Visual Studio 2015, les raccourcis clavier (ex : contrôle+c pour Copier) sont maintenant annoncés comme prévu. (#6021)
* Correction d'un problème rare dans la recherche des ports série sur certains systèmes qui rendait les pilotes de certains afficheurs braille inutilisables. (#6015)
* L'annonce des couleurs sous Microsoft Word est maintenant plus fiable car les changements de thème dans Microsoft Office sont maintenant pris en compte. (#5997)
* Le mode navigation sous Microsoft Edge et le support des suggestions de recherche dans l'écran de démarrage, sont de nouveau disponibles pour les versions de Windows 10 postérieures à Avril 2016. (#5955)
* Sous Microsoft Word, la lecture automatique des titres de tableaux fonctionne mieux quand on rencontre des cellules fusionnées. (#5926)
* Dans l'application Courrier de Windows 10, NVDA n'échoue plus à lire le contenu des messages. (#5635)
* Plus d'annonce en double des touches de verrouillage quand l'annonce des touches de commande est activée. (#5490)
* Les dialogues Contrôle de Compte Utilisateur de Windows sont de nouveau lus correctement dans la mise à jour Anniversaire de Windows 10. (#5942)
* Dans le plug-in Web Conference (comme utilisé sous out-of-sight.net) NVDA n'annonce plus par des bips et vocalement les mises à jour de la barre de progression concernant l'entrée microphone. (#5888)
* Effectuer une commande Recherche Suivant ou Recherche Précédent en mode navigation fera maintenant une recherche sensible à la casse si la recherche originale est sensible à la casse. (#5522)
* Quand on édite les entrées de dictionnaire, un avertissement est maintenant donné pour les expressions régulières incorrectes. NVDA ne se plante plus si un dictionnaire contient une expression régulière invalide. (#4834)
* Si NVDA est incapable de communiquer avec un afficheur braille (ex : parce qu'il a été déconnecté), il désactivera automatiquement l'utilisation de l'afficheur. (#1555)
* Légère amélioration de performance du filtrage dans la liste d'éléments du mode navigation dans certains cas. (#6126)
* Sous Microsoft Excel, les noms de modèles d'arrière-plan annoncés par NVDA correspondent maintenant à ceux utilisés par Excel. (#6092)
* Support amélioré de l'écran de connexion à Windows 10, incluant l'annonce des alertes et l'activation du champ mot de passe au toucher. (#6010)
* NVDA détecte maintenant correctement les boutons de routage secondaires sur les afficheurs braille ALVA BC640/680 series. (#5206)
* NVDA peut de nouveau annoncer les notifications Toast de Windows dans les versions récentes de Windows 10. (#6096)
* NVDA n'arrête plus de temps en temps de reconnaître l'appui des touches sur les terminaux braille Compatibles Baum et HumanWare Brailliant B. (#6035)
* Si l'annonce des numéros de lignes est activée dans le dialogue Mise en Forme des Documents de NVDA, les numéros de lignes sont maintenant affichés sur l'afficheur braille. (#5941)
* Quand la parole est désactivée, l'annonce des objets (comme quand on presse NVDA+tab pour annoncer le focus) apparaît maintenant dans la visionneuse de parole comme prévu. (#6049)
* Dans la liste de messages d'Outlook 2016, l'information de brouillon associée n'est plus annoncée. (#6219)
* Sous Google Chrome et les navigateurs basés sur Chrome dans une langue autre que l'Anglais, le mode navigation ne refuse plus de fonctionner pour certains documents. (#6249)

### Changements pour les Développeurs

* La journalisation des informations directement depuis une propriété ne provoque plus l'appel récursif de la propriété indéfiniment. (#6122)

## 2016.2.1

Cette version corrige des plantages sous Microsoft Word :

* NVDA ne cause plus le plantage de Microsoft Word immédiatement après son démarrage sous Windows XP. (#6033)
* Suppression de l'annonce des erreurs grammaticales, car ceci cause des plantages sous Microsoft Word. (#5954, #5877)

## 2016.2

Les points forts de cette version incluent la possibilité d'indiquer les fautes d'orthographe durant la frappe; le support de l'annonce des erreurs grammaticales sous Microsoft Word; et des améliorations et corrections dans le support de Microsoft Office.

### Nouvelles Fonctionnalités

* en mode navigation sous Internet Explorer et autres contrôles MSHTML, utiliser la navigation par lettre pour se déplacer entre annotations (a et maj+a) ateint maintenant le texte inséré et effacé. (#5691)
* Sous Microsoft Excel, NVDA annonce maintenant le niveau d'un groupe de cellules, ainsi que s'il est réduit ou développé. (#5690)
* Un double appui sur la commande d'annonce de la mise en forme du texte (NVDA+f) présente l'information en mode navigation pour qu'elle puisse être parcourue. (#4908)
* Sous Microsoft Excel 2010 et au-delà, la trame et le dégradé d'une cellule est maintenant annoncé. L'annonce automatique est contrôlée par l'option d'annonce des couleurs dans les préférences de formatage de document de NVDA. (#3683)
* Nouvelle table de conversion braille : Grec Alexandrin. (#5393)
* Dans la visionneuse du Journal, vous pouvez maintenant sauvegarder le journal en utilisant le raccourci Contrôle+s. (#4532)
* Si l'annonce des fautes d'orthographe est activée et supportée par le contrôle en focus,, NVDA émettra un son pour vous avertir d'une faute d'orthographe commise durant la frappe. Ceci peut être désactivé en utilisant la nouvelle option "Jouer un son pour les fautes d'orthographe durant la frappe" dans le dialogue Paramètres Clavier de NVDA. (#2024)
* Les erreurs grammaticales sont maintenant annoncées sous Microsoft Word. Ceci peut être désactivé en utilisant la nouvelle option "Annoncer les erreurs grammaticales" dans le dialogue "Mise en forme des documents" de NVDA. (#5877)

### Changements

* En mode navigation et dans les champs de saisie, NVDA traite maintenant la touche Entrer du pavé numérique de la même manière que la touche Entrer principale. (#5385)
* NVDA est passé au synthétiseur de parole eSpeak NG. (#5651)
* Sous Microsoft Excel, NVDA n'ignore plus l'en-tête de colonne pour une cellule quand il y a une ligne blanche entre la cellule et le titre. (#5396)
* Sous Microsoft Excel, les coordonnées sont maintenant annoncées avant les en-têtes pour éliminer les ambiguïtés entre les en-têtes et le contenu. (#5396)

### Corrections de Bogues

* En mode navigation, quand on essaie d'utiliser la navigation par lettre pour atteindre un élément qui n'est pas suporté dans ce document, NVDA annonce que ceci n'est pas supporté plutôt que d'annoncer qu'il n'y a pas d'élément dans cette direction. (#5691)
* Quand on liste les feuilles dans la liste d'éléments sous Microsoft Excel, les feuilles ne contenant que des graphiques sont maintenant incluses. (#5698)
* NVDA n'annonce plus d'informations irrelevantes quand on change de fenêtre dans une application Java avec de multiples fenêtres comme IntelliJ oo Android Studio. (#5732)
* dans les éditeurs basés sur Scintilla comme Notepad++, le braille est maintenant mis à jour correctement quand on déplace le curseur en utilisant un afficheur braille. (#5678)
* NVDA ne se plante plus parfois quand on active l'affichage braille. (#4457)
* Sous Microsoft Word, le retrait des paragraphes est maintenant toujours annoncé dans l'unité de mesure choisie par l'utilisateur (ex : centimètres ou pouces). (#5804)
* Quand on utilise un afficheur braille, Beaucoup de messages de NVDA qui jusque là n'étaient que parlés sont maintenant également affichés en Braille. (#5557)
* Dans les applications Java accessibles, le niveau des éléments d'arborescence est maintenant annoncé. (#5766)
* Correction de plantages d'Adobe Flash sous Mozilla Firefox dans certains cas. (#5367)
* Sous Google Chrome et les navigateurs basés sur Chrome, les documents dans les dialogues ou les applications peuvent maintenant être lus en mode navigation. (#5818)
* Sous Google Chrome et les navigateurs basés sur Chrome, vous pouvez maintenant forcer NVDA à passer en mode navigation dans les dialogues ou applications web. (#5818)
* Sous Internet Explorer et autres contrôles MSHTML, amener le focus à certains contrôles (spécifiquement, quand aria-activedescendant est utilisé) ne passe plus incorrectement en mode navigation. Ceci arrivait, par exemple, quand on allait aux suggestions dans les champs d'adresse en composant un message sous Gmail. (#5676)
* Sous Microsoft Word, NVDA ne se bloque plus dans les grands tableaux quand l'annonce des en-têtes de lignes et collones de tableau est activée. (#5878)
* Sous Microsoft word, NVDA n'annonce plus incorrectement un texte avec un niveau hiérarchique (mais sans style d'en-tête défini) comme un titre. (#5186)
* En mode navigation sous Microsoft Word, les commandes aller après la fin ou avant le début d'un conteneur (virgule et maj+virgule) fonctionnent maintenant pour les tableaux. (#5883)

### Changements pour les Développeurs

* Les composants C++ de NVDA sont maintenant construits avec Microsoft Visual Studio 2015. (#5592)
* Vous pouvez maintenant présenter un texte ou un message HTML à l'utilisateur en mode navigation en utilisant ui.browseableMessage. (#4908)
* Dans le Guide de l'Utilisateur, quand une commande <!-- KC:setting est utilisée pour un paramètre ayant un raccourci commun à toutes les configurations clavier, le raccourci peut maintenant être placé après un deux-points pleine largeur (：) aussi bien qu'après un deux-points normal (:). (#5739) -->

## 2016.1

Les points forts de cette version incluent la possibilité de baisser optionnellement le volume des autres sources audio ; des amélioration de l'affichage braille et du support des terminaux braille ; plusieurs corrections significatives dans le support de Microsoft Office; et des corrections pour le mode navigation sous iTunes.

### Nouvelles Fonctionnalités

* Nouvelle table de conversion braille : Polonais braille informatique 8 points, Mongol. (#5537, #5574)
* Vous pouvez désactiver le curseur braille et en changer la forme en utilisant les nouvelles options Montrer le curseur et Forme du curseur dans le dialogue Paramètres Braille. (#5198)
* NVDA peut maintenant se connecter à un afficheur braille HIMS Smart Beetle via Bluetooth. (#5607)
* NVDA peut optionnellement baisser le volume des autres sons quand il est installé sous Windows 8 et au-delà. Ceci peut être configuré en utilisant l'option Mode d'Atténuation Audio dans le dialogue Synthétiseur de NVDA ou en pressant NVDA+maj+d. (#3830, #5575)
* Support de l'APH Refreshabraille en mode HID et des Baum VarioUltra et Pronto! connectés via USB. (#5609)
* Support des afficheurs braille HumanWare Brailliant BI/B quand le protocole est réglé sur OpenBraille. (#5612)

### Changements

* L'annonce de l'emphase est maintenant désactivée par défaut. (#4920)
* Dans la liste d'éléments sous Microsoft Excel, le raccourci pour les formule a été changé en alt+r pour qu'il soit différent du raccourci pour le champ de filtre. (#5527)
* Le traducteur braille liblouis a été mis à jour à la version 2.6.5. (#5574)
* Le mot "texte" n'est plus prononcé quand on amène le focus ou le curseur de revue sur des objets texte. (#5452)

### Corrections de Bogues

* Sous iTunes 12, le mode navigation se met maintenant à jour correctement quand une nouvelle page est chargée dans l'iTunes Store. (#5191)
* Sous Internet Explorer et autres contrôles MSHTML, aller à des titres de niveau spécifique en navigation par lettre fonctionne maintenant comme prévu quand le niveau d'un titre est masqué pour des raisons d'accessibilité (en particulier, quand aria-level masque le niveau d'un h tag). (#5434)
* Sous Spotify, Le focus ne se positionne plus fréquemment sur des objets inconnus. (#5439)
* Le focus est maintenant restauré correctement quand on revient dans Spotify depuis une autre application. (#5439)
* Quand on bascule entre mode navigation et mode formulaire, le mode est indiqué en Braille aussi bien qu'en parole. (#5239)
* Le bouton Démarrer sur la barre des tâches n'est plus annoncé comme une liste et/ou comme sélectionné dans certaines versions de Windows. (#5178)
* Des messages tels que "inséré" ne sont plus annoncés quand on compose des messages sous Microsoft Outlook. (#5486)
* Quand on utilise un afficheur braille et que du texte est sélectionné sur la ligne courante (ex : quand on recherche dans un éditeur de texte un texte apparaissant sur la même ligne), l'afficheur braille défilera si nécessaire. (#5410)
* NVDA ne s'arrête plus silencieusement quand on ferme une console de commandes Windows par alt+f4 sous Windows 10. (#5343)
* Dans la liste d'éléments en mode navigation, quand on change de type d'élément, le champ de filtrage est maintenant remis à blanc. (#5511)
* Dans le texte éditable des applications Mozilla, déplacer la souris lit à nouveau la ligne appropriée, le mot, etc. comme prévu au lieu de tout le contenu. (#5535)
* Quand on déplace la souris dans un texte éditable d'une application Mozilla, la lecture ne s'arrête plus sur les éléments tels que les liens dans le mot ou la ligne en cours de lecture. (#2160, #5535)
* Sous Internet Explorer, le site shoprite.com peut maintenant être lu en mode navigation et n'est plus annoncé comme vide. (Spécifiquement, les attributs lang malformés sont maintenant élégamment gérés.) (#5569)
* Sous Microsoft Word, les demandes de modification telles que "inséré" ne sont plus annoncées quand l'indicateur de demandes de modification n'est pas affiché. (#5566)
* Quand un bouton bascule est en focus, NVDA annonce maintenant quand il passe de enfoncé à non enfoncé. (#5441)
* L'annonce des changements de forme de la souris fonctionne de nouveau comme prévu. (#5595)
* Durant l'annonce du retrait des lignes, les espaces insécables sont maintenant traités comme des espaces normaux. Avant, cela pouvait causer des annonces telles que "espace espace espace" au lieu de "3 espace". (#5610)
* À la fermeture de la liste de candidats d'une méthode moderne de saisie Microsoft, le focus est rétabli correctement soit à la composition de saisie soit au document sous-jacent. (#4145)
* Sous Microsoft Office 2013 et au-delà, quand le ruban est paramétré pour ne montrer que des onglets, les items dans le ruban sont de nouveau annoncés comme prévu quand un onglet est activé. (#5504)
* Corections et améliorations dans la détection et l'assignation des gestes tactiles. (#5652)
* Les survols d'écran tactile ne sont plus annoncés dans l'aide à la saisie. (#5652)
* NVDA n'échoue plus à lister les commentaires dans la liste d'éléments d'Excel quand le commentaire est sur une cellule fusionnée. (#5704)
* Dans certains cas très rares, NVDA n'échoue plus à lire le contenu d'une feuille sous Excel quand l'annonce des en-têtes de lignes et de colonnes est activée (#5705)
* Sous Google Chrome, naviguer dans une composition de saisie pour des caractères est-asiatiques n'échoue plus avec une erreur. (#4080)
* Quand on recherche Apple Music sous iTunes, le mode navigation du document de résultats de recherche est maintenant mis à jour comme prévu. (#5659)
* Sous Microsoft Excel, l'appui sur maj+f11 pour créer une nouvelle feuille annonce maintenant votre nouvelle position au lieu de ne rien annoncer. (#5689)
* Correction des problèmes d'affichage braille quand on saisit des caractères Coréens. (#5640)

### Changements pour les Développeurs

* La nouvelle classe audioDucking.AudioDucker permet au code qui produit l'audio d'indiquer quand l'audio en arrière-plan devrait être atténuée. (#3830)
* Le constructeur de nvwave.WavePlayer possède maintenant un mot-clé argument wantDucking qui spécifie si l'audio en arrière-plan devrait être atténuée durant l'émission de l'audio. (#3830)
 * Quand ceci est activé (ce qui est le défaut), il est essentiel que WavePlayer.idle soit appelé quand appproprié.
* Entrées/sorties améliorées pour les afficheurs braille : (#5609)
 * Les pilotes d'afficheurs braille Thread-safe peuvent se déclarer comme tels en utilisant l'attribut BrailleDisplayDriver.isThreadSafe. Un pilote doit être thread-safe pour bénéficier des fonctionnalités suivantes.
 * Les données sont écrites dans les pilotes thread-safe en arrière-plan, améliorant ainsi les performances.
 * hwIo.Serial étend pyserial pour appeler un appelable quand les données sont reçues au lieu que les pilotes aient à surveiller.
 * hwIo.Hid fournit le support pour les afficheurs communiquant via USB HID.
 * hwPortUtils et hwIo peuvent optionnellement fournir une journalisation détaillée de débogage, incluant les équipements trouvés et toutes les données envoyées et reçues.
* plusieurs nouvelles propriétés sont accessible depuis les gestes sur un écran tactile : (#5652)
 * Les objets MultitouchTracker contiennent maintenant une propriété childTrackers qui contient les MultiTouchTrackers dont le tracker est composé. For example, 2 finger double tap has child trackers for two 2-finger taps. The 2-finger taps themselves have child trackers for two taps.
 * Les objets MultiTouchTracker contiennent aussi maintenant la propriété rawSingleTouchTracker si le tracker est le résultat d'une tape, d'un glisser ou survol d'un seul doigt. Le SingleTouchTracker permet d'accéder à l'ID sous-jacent assigné au doigt par le système d'exploitation et de savoir si le doigt est toujours en contact
 * Les TouchInputGestures ont maintenant des propriétés x et y, supprimant le besoin d'accéder au tracker pour des cas triviaux.
 * Les TouchInputGesturs contiennent maintenant une propriété preheldTracker, qui est un objet MultitouchTracker représentant les autres doigts appuyés au moment où l'action a été exécutée.
* Deux nouveaux gestes tactiles peuvent être émis : (#5652)
 * Tapes et maintiens multiples (ex. tape et maintien double)
 * Un identifiant généralisé avec le compte des doigts supprimé pour les maintiens (ex. maintien+survol pour 1finger_hold+hover).

## 2015.4

Les points forts de cette version incluent des améliorations de performances sous Windows 10 ; l'inclusion dans les options d'accessibilité sous Windows 8 et au-delà; des amélioration sous Microsoft Excel, incluant la possibilité de lister et renommer les feuilles et l'accès aux cellules verrouillées dans les feuilles protégées; et le support de l'édition du texte enrichi sous Mozilla Firefox, Google Chrome et Mozilla Thunderbird.

### Nouvelles Fonctionnalités

* NVDA apparaît maintenant dans les Options d'Ergonomie sous Windows 8 et au-delà. (#308)
* Quand on se déplace dans les cellules sous Excel, les changement de mise en forme sont maintenant annoncés automatiquement si les options appropriées sont activées dans le dialogue "Mise en forme des documents". (#4878)
* Une option " Annoncer l'Emphase " a été ajoutée au dialogue " Mise en Forme des documents " de NVDA. Activée par défaut, cette option autorise NVDA à annoncer automatiquement l'existence de texte mis en emphase dans les documents. Pour l'instant ceci ne fonctionne que pour les balises em et strong en mode navigation pour Internet Explorer et autres contrôles MSHTML. (#4920)
* L'existence de texte inséré ou effacé est maintenant annoncée en mode navigation pour Internet Explorer et autres contrôles MSHTML, si l'option "Annoncer les révisions de l'éditeur" de NVDA est activée. (#4920)
* Quand, dans la liste d'éléments de NVDA sous Microsoft Word, des demandes de modification sont constatées, plus d'informations telles que la nature du changement des propriétés de formatage sont maintenant affichées. (#4920)
* Microsoft Excel : lister et renommer les feuilles est maintenant possible depuis la liste d'éléments de NVDA (NVDA+f7). (#4630, #4414)
* Il est maintenant possible de configurer si un symbole réel doit être envoyé au synthétiseur (ex. pour créer une pause ou un changement d'inflection) dans le dialogue de prononciation des symboles. (#5234)
* Sous Microsoft Excel, NVDA annonce maintenant tout message d'entrée défini par l'auteur de la feuille sur les cellules. (#5051)
* Support des terminaux Baum Pronto! V4 et VarioUltra connectés en Bluetooth. (#3717)
* Support de l'édition du texte enrichi dans les applications Mozilla telles que Google Docs avec le support braille activé dans Mozilla Firefox et la composition HTML sous Mozilla Thunderbird. (#1668)
* Support de l'édition du texte enrichi sous Google Chrome et les navigateurs basés sur Chrome tels que Google Docs avec le support braille activé. (#2634)
 * Ceci requiert Chrome version 47 ou au-delà.
* En mode navigation sous Microsoft Excel, on peut naviguer vers les cellules verrouillées dans les feuilles protégées. (#4952)

### Changements

* L'option " Annoncer les Révisions de l'Éditeur " dans le dialogue "Mise en forme des Documents" de NVDA est maintenant activée par défaut. (#4920)
* Quand on se déplace par caractère sous Microsoft Word et que l'option "Annoncer les révisions de l'éditeur" de NVDA est activée, NVDA annonce maintenant moins d'informations concernant les demandes de modification, ce qui rend la navigation plus efficace. Pour voir les informations supplémentaires, utilisez la liste d'éléments. (#4920)
* Le traducteur braille liblouis a été mis à jour à la version 2.6.4. (#5341)
* Plusieurs symboles (incluant les symboles mathématiques de base) ont été déplacés au niveau "quelques-uns" pour qu'ils soient annoncés par défaut. (#3799)
* Si le synthétiseur le supporte, la parole devrait maintenant marquer une pause pour les parenthèses et le tiret demi cadratin (–). (#3799)
* Quand on sélectionne du texte, le texte est annoncé avant l'indication de sélection et non après. (#1707)

### Corrections de Bogues

* Améliorations majeures de performances quand on navigue dans la liste de messages d'Outlook 2010/2013. (#5268)
* Dans un graphique sous Microsoft Excel, la navigation avec certaines touches (comme changer de feuille avec contrôle+pagePrec et contrôle+pageSuiv) fonctionne maintenant correctement. (#5336)
* Correction de l'apparence visuelle des boutons dans le dialogue d'avertissement qui est affiché quand on essaie d'installer une version inférieure de NVDA. (#5325)
* Sous Windows 8 et au-delà, NVDA démarre maintenant beaucoup plus tôt quand il est configuré pour démarrer après la connexion à Windows. (#308)
 * Si vous avez configuré cela avec une version précédente de NVDA, vous devrez le désactiver puis le réactiver dans le dialogue Paramètres Généraux pour que le changement prenne effet. Suivez cette procédure :
  1. Ouvrez le dialogue "Paramètres Généraux".
  1. Décochez la case "Démarrer NVDA automatiquement après ma connexion à Windows".
  1. Appuyez sur le bouton OK.
  1. Ouvrez de nouveau le dialogue "Paramètres Généraux".
  1. Cochez la case "Démarrer NVDA automatiquement après ma connexion à Windows".
  1. Appuyez sur le bouton OK.
* Améliorations de performance pour UI Automation incluant l'Explorateur de fichier et la barre des tâches. (#5293)
* NVDA passe maintenant correctement en mode formulaire quand on tabule vers des contrôles ARIA grid en lecture seule en mode navigation pour Mozilla Firefox et autres contrôles basés sur Gecko. (#5118)
* NVDA annonce maintenant correctement " Pas de précédent " au lieu de " pas de suivant " quand il n'y a plus d'objet quand on glisse à gauche sur un écran tactile.
* Correction des problèmes apparaissant à la frappe de plusieurs mots dans la zone de filtre dans le dialogue "Gestes de commandes". (#5426)
* NVDA ne se bloque plus parfois quand on se reconnecte à un terminal braille HumanWare Brailliant BI/B series via USB. (#5406)
* Dans les langues comportant des caractères conjoints, la description de caractère fonctionne maintenant comme prévu pour les caractères anglais en majuscule. (#5375)
* NVDA ne devrait plus se bloquer occasionnellement à l'affichage du menu Démarrer de Windows 10. (#5417)
* Dans Skype for Desktop, les notifications qui s'affichent avant qu'une notification précédente ne disparaisse sont maintenant annoncées. (#4841)
* les notifications sont maintenant annoncées correctement dans Skype for Desktop 7.12 et au-delà. (#5405)
* NVDA annonce maintenant correctement le focus quand on quitte un menu contextuel dans certaines applications comme Jart. (#5302)
* Sous Windows 7 et au-delà, la couleur est de nouveau annoncée dans certaines applications comme Wordpad. (#5352)
* En édition sous Microsoft PowerPoint, l'appui sur Entrer annonce maintenant automatiquement le texte entré tel qu'une puce ou un nombre. (#5360)

## 2015.3

Les points forts de cette version incluent le support initial de Windows 10 ; la possibilité de désactiver la navigation par lettre en mode navigation (utile pour certainnes applications web) ; Des améliorations sous Internet Explorer et des corrections de texte brouillé quand on tape dans certaines applications avec le braille actif.

### Nouvelles Fonctionnalités

* L'existence de fautes d'orthographe est annoncée dans les zones d'édition pour Internet Explorer et autres contrôles MSHTML. (#4174)
* Beaucoup plus de symboles mathématiques unicodes sont maintenant annoncés quand ils apparaissent dans le texte. (#3805)
* Les suggestions de recherche dans l'écran de démarrage de Windows 10 sont automatiquement annoncées (#5049)
* Support des terminaux EcoBraille 20, EcoBraille 40, EcoBraille 80 et EcoBraille Plus. (#4078)
* En mode navigation, vous pouvez maintenant activer ou désactiver la navigation par lettre unique en pressant NVDA+maj+espace. Quand elle est désactivée, les touches de lettres uniques sont passées à l'application, ce qui est utile pour quelques applications web comme Gmail, Twitter et Facebook. (#3203)
* Nouvelles tables braille : Finnois 6 points, Irlandais intégral, Irlandais abrégé, Coréen intégral (2006), Coréen abrégé (2006). (#5137, #5074, #5097)
* Le clavier QWERTY de l'afficheur braille Papenmeier BRAILLEX Live Plus est maintenant supporté. (#5181)
* Support expérimental du navigateur web et moteur de navigation Microsoft Edge sous Windows 10. (#5212)
* Nouvelle langue : Kannada.

### Changements

* Mise à jour du traducteur braille liblouis à la version 2.6.3. (#5137)
* Si vous essayez d'installer une version de NVDA plus ancienne que la version déjà installée, vous serez maintenant averti que ce n'est pas recommandé et que NVDA devrait être complètement désinstallé avant de continuer. (#5037)

### Corrections de Bogues

* En mode navigation sous Internet Explorer et autres contrôles MSHTML, la navigation rapide par champs de formulaire n'inclut plus incorrectement les éléments de listes de présentation. (#4204)
* Sous Firefox, NVDA n'essaie plus de créer une description pour les panneaux d'onglets ARIA basés sur tout le texte contenu. (#4638)
* Sous Internet Explorer et autres contrôles MSHTML, tabuler dans des sections, articles ou dialogues n'annonce plus tout le contenu du conteneur comme étant son nom. (#5021, #5025)
* Quand on utilise les terminaux braille Baum/HumanWare/APH avec un clavier braille, la saisie braille ne s'arrête plus de fonctionner après qu'on ait pressé un autre type de touche sur le terminal. (#3541)
* Sous Windows 10, des information irrelevantes ne sont plus annoncées quand on presse alt+tab ou alt+maj+tab pour naviguer entre les applications. (#5116)
* Le texte entré n'est plus mélangé quand on utilise certaines applications comme Microsoft Outlook avec un terminal braille. (#2953)
* En mode navigation sous Internet Explorer et autres contrôles MSHTML, le contenu correct est maintenant reporté quand un élément apparaît ou change et est immédiatement mis en focus. (#5040)
* En mode navigation sous Microsoft Word, la navigation par lettre unique met maintenant à jour l'afficheur braille et le curseur de revue comme attendu. (#4968)
* En braille, des espaces irrelevants ne sont plus affichés entre ou après des indicateurs de contrôles et de présentation. (#5043)
* Quand une application répond lentement et que vous passez sur une autre fenêtre, NVDA est maintenant beaucoup plus réactif sur les autres applications dans la plupart des cas. (#3831)
* Les notifications de Toast sous Windows 10 sont maintenant annoncées comme prévu. (#5136)
* La valeur est maintenant annoncée quand elle change dans certaines listes déroulantes (UI Automation) dans des cas où ce n'était pas le cas précédemment.
* En mode navigation dans les navigateurs web, la tabulation fonctionne maintenant comme prévu après avoir tabulé vers un document cadre. (#5227)
* L'écran de verrouillage de Windows 10 peut maintenant être quitté en utilisant un écran tactile. (#5220)
* Sous Windows 7 et au-delà, le texte n'est plus mélangé quand on tape dans certaines applications comme Wordpad et Skype et qu'on utilise un afficheur braille. (#4291)
* Sur l'écran de verrouillage de Windows 10 , il n'est plus possible de lire le presse-papiers, d'accéder aux applications en cours d'exécution avec le curseur de revue, de changer la configuration de NVDA, etc. (#5269)

### Changements pour les Développeurs

* Vous pouvez maintenant injecter de la saisie brute depuis un clavier système non supporté nativement par Windows (ex : un clavier QWERTY sur un afficheur braille) en utilisant la nouvelle fonction keyboardHandler.injectRawKeyboardInput. (#4576)
* eventHandler.requestEvents a été ajouté pour requérir des événements particuliers qui sont bloqués par défaut; ex : montrer les événements concernant un contrôle spécifique ou certains événements quand ils sont en arrière-plan. (#3831)
* Plutôt qu'un simple attribut i18nName, synthDriverHandler.SynthSetting possède maintenant un displayNameWithAccelerator séparé et des attributs displayName pour éviter l'annonce du raccourci dans la boucle des paramètres synthétiseur dans certaines langues.
 * Pour assurer la compatibilité descendante, dans le constructeur, displayName est optionnel et sera dérivé de displayNameWithAccelerator s'il n'est pas fourni. Cependant, si vous voulez avoir un raccourci pour un paramètre, les deux doivent être fournis.
 * L'attribut i18nName est déprécié et sera peut-être retiré dans une version future.

## 2015.2

Les points forts de cette version incluent la possibilité de lire les graphiques dans Microsoft Excel et le support de la lecture et de la navigation interactive dans les contenus mathématiques.

### Nouvelles Fonctionnalités

* Avancer et reculer par phrase sous Microsoft Word et Outlook est maintenant possible avec alt+flècheBas et alt+flècheHaut respectivement. (#3288)
* De nouvelles tables de conversion braille pour plusieurs langues Indiennes. (#4778)
* Dans Microsoft Excel, NVDA annonce maintenant quand une cellule a un contenu en débordement ou réajusté. (#3040)
* Une liste d'éléments dans Microsoft Excel (NVDA+f7), permet de lister les graphiques, commentaires et formules. (#1987)
* Support de la lecture des graphiques dans Microsoft Excel : Sélectionnez le graphique en utilisant la liste d'éléments (NVDA+f7) puis utilisez les flèches pour aller à tous les points de données. (#1987)
* En utilisant MathPlayer 4 de Design Science, NVDA peut maintenant lire et naviguer de façon interactive dans les contenus mathématiques dans les navigateurs Internet et dans Microsoft Word et PowerPoint. Veuillez consulter la section "Lecture des Contenus Mathématiques" dans le Guide de l'utilisateur pour plus de détails. (#4673)
* Il est maintenant possible d'assigner des gestes de commande (commandes clavier, gestes tactiles, etc.) pour tous les dialogues des préférences NVDA et les options de mise en forme de document en utilisant le dialogue Gestes de Commandes. (#4898)

### Changements

* Dans le dialogue de mise en forme des documents, les raccourcis clavier pour l'annonce des listes, l'annonce des liens, l'annonce du numéro de ligne et l'annonce du nom de la police ont été changés (en anglais). (#4650)
* Dans le dialogue des paramètres de la souris de NVDA, des raccourcis clavier ont été ajoutés pour "Sonoriser les coordonnées quand la souris se déplace" et "La brillance modifie le volume des coordonnées audio". (#4916)
* Amélioration significative de l'annonce des couleurs. (#4984)
* Mise à jour du traducteur braille liblouis à la version 2.6.2. (#4777)

### Corrections de Bogues

* Les descriptions de caractère sont maintenant traitées correctement pour les caractères conjoints dans certaines langues Indiennes. (#4582)
* Si l'option " Se baser sur la langue de la voix pour le traitement des caractères et symboles " est cochée, le dialogue Prononciation des symboles et ponctuations utilise maintenant correctement la langue de la voix. La langue dont la prononciation est éditée est aussi indiquée dans le titre du dialogue. (#4930)
* Dans Internet Explorer et autres contrôles MSHTML, les caractères frappés ne sont plus annoncés de manière inappropriée dans les listes déroulantes éditables telles que le champ de recherche Google sur la page d'accueil de Google. (#4976)
* Quand on sélectionne des couleurs dans les applications Microsoft Office, le nom des couleurs est maintenant annoncé. (#3045)
* L'affichage du Braille Danois fonctionne à nouveau. (#4986)
* pagePrec / pageSuiv peuvent de nouveau être utilisées pour changer de diapositive dans un diaporama PowerPoint. (#4850)
* Dans Skype for Desktop 7.2 et au-delà, les notifications de frappe sont maintenant annoncées et les problèmes intervenant immédiatement après que le focus ait quitté une conversation ont été corrigés. (#4972)
* Correction de problèmes de frappe de certains symboles telles que les crochets dans le champ de filtrage dans le dialogue de saisie des gestes de commande. (#5060)
* Dans Internet Explorer et autres contrôles MSHTML, l'appui sur g ou maj+g pour naviguer vers les graphiques inclut maintenant les éléments marqués comme des images pour des raisons d'accessibilité (i.e. ARIA role img). (#5062)

### Changements pour les Développeurs

* brailleInput.handler.sendChars(mychar) N'ignorera plus un caractère s'il est égal au caractère précédent en s'assurant que la touche enfoncée a été correctement relâchée.
* Les scripts pour changer le mode de toucher honnoreront maintenant les nouvelles étiquettes ajoutée à touchHandler.touchModeLabels. (#4699)
* Les modules complémentaires peuvent fournir leur propre implémentation de présentation mathématique. Voir le package mathPres pour plus de détails. (#4509)
* Des commandes de parole ont été implémentées pour insérer une pause entre les mots et pour changer la hauteur, le volume et le débit. Voir les commandes BreakCommand, PitchCommand, VolumeCommand et RateCommand dans le module speech. (#4674)
 * Il y a aussi speech.PhonemeCommand pour insérer une prononciation spécifique, mais l'implémentation courante supporte un nombre très limité de phonèmes.

## 2015.1

Les points forts de cette version incluent le mode navigation pour les documents dans Microsoft Word et Outlook ; des améliorations majeures de la prise en charge de Skype for Desktop ; et des correctifs importants pour Microsoft Internet Explorer.

### Nouvelles Fonctionnalités

* Vous pouvez maintenant ajouter de nouveaux symboles dans le dialogue Symboles de Prononciation. (#4354)
* Dans le dialogue Gestes de Commandes, vous pouvez utiliser le nouveau champ "Filtrer par" pour n'afficher que les gestes contenant des mots spécifiques. (#4458)
* NVDA annonce maintenant automatiquement le nouveau texte dans mintty. (#4588)
* Dans le dialogue de recherche du mode navigation, il y a maintenant une option permettant d'effectuer une recherche tenant compte de la casse. (#4584)
* La navigation rapide (h pour titre etc) et la Liste d'éléments (NVDA+f7) sont maintenant disponibles dans les documents Microsoft Word en activant le mode navigation avec NVDA+espace. (#2975)
* La lecture des messages HTML sous Microsoft Outlook 2007 et les versions supérieures a été considérablement améliorée, le mode navigation étant automatiquement activé pour ces messages. Si le mode navigation n'est pas activé dans certaines situations rares, vous pouvez l'activer par NVDA+espace. (#2975)
* Dans Microsoft Word, les en-têtes de colonnes de tableaux sont annoncés automatiquement pour les tableaux où la ligne d'en-têtes a été explicitement spécifiée par l'auteur via les propriétés de tableau de Microsoft Word. (#4510)
 * Cependant, pour des tableaux où les lignes ont été fusionnées, cela ne marchera pas automatiquement. Dans cette situation vous pouvez toujours définir les en-têtes de colonnes manuellement sous NVDA avec NVDA+maj+c.
* Dans Skype for Desktop, les notifications sont maintenant annoncées. (#4741)
* Dans Skype for Desktop, vous pouvez maintenant entendre et revoir les messages récents en utilisant les raccourcis de NVDA+control+1 à NVDA+control+0; ex: NVDA+control+1 pour le message le plus récent et NVDA+control+0 pour le dixième plus récent. (#3210)
* Dans une conversation sous Skype for Desktop, NVDA annonce maintenant quand un correspondant est en train d'écrire. (#3506)
* NVDA peut maintenant être installé silencieusement via la ligne de commande sans démarrage de la copie installée après installation. Pour faire cela, utilisez --install-silent. (#4206)
* Support des afficheurs braille Papenmeier BRAILLEX Live 20, BRAILLEX Live et BRAILLEX Live Plus. (#4614)

### Changements

* dans le dialogue Mise en Forme des Documents de NVDA, l'option d'annonce des fautes d'orthographe a maintenant un raccourci (alt+f). (#793)
* NVDA utilisera maintenant la langue de la voix du synthétiseur pour le traitement des caractères et symboles (incluant le nom des symboles de ponctuation), que le changement automatique de langue soit activé ou non. Pour désactiver cette fonction de manière à ce que NVDA utilise à nouveau la langue de son interface, décochez la nouvelle option dans les paramètres vocaux appelée Se baser sur la langue de la voix pour le traitement des caractères et symboles. (#4210)
* Le support du synthétiseur Newfon a été supprimé. Newfon est maintenant disponible sous la forme d'un module complémentaire. (#3184)
* Skype for Desktop 7 ou plus récent est maintenant requis pour utilisation avec NVDA; les versions plus anciennes ne sont pas supportées. (#4218)
* Le téléchargement des mises à jour de NVDA est maintenant plus sécurisé. (En particulier, l'information de mise à jour est récupérée via https et le hash du fichier est vérifié après téléchargement.) (#4716)
* eSpeak a été mis à jour à la version 1.48.04 (#4325)

### Corrections de Bogues

* Dans Microsoft Excel, support du cas où les cellules d'en-tête de ligne et de colonne sont fusionnées. Ex : Si A1 et B1 sont fusionnées, B2 aura maintenant A1 et B1 annoncées comme en-tête de colonne, au lieu de rien. (#4617)
* Lors de l'édition du contenu d'une boîte de texte dans Microsoft PowerPoint 2003, NVDA annoncera correctement le contenu de chaque ligne. Précédemment les lignes perdaient un caractère à chaque nouveau paragraphe. (#4619)
* Tous les dialogues de NVDA sont maintenant centrés sur l'écran, améliorant la présentation visuelle et l'utilisation. (#3148)
* Dans Skype pour bureau, lors de la saisie d'un message d'introduction pour ajouter un contact, l'entrée et le déplacement dans le texte fonctionnent maintenant correctement. (#3661)
* Quand le focus va à un nouvel élément dans les arborescences de l'interface de développement d'Eclipse, si l'élément précédent est une case à cocher, il est maintenant correctemment annoncé. (#4586)
* Dans le dialogue de vérification orthographique de Microsoft Word, l'erreur suivante sera automatiquement annoncée quand la dernière a été corrigée ou ignorée via son raccourci clavier. (#1938)
* Le texte est à nouveau correctement lisible dans les fenêtres telles que le terminal de Tera Term Pro et les documents sous Balabolka. (#4229)
* Le focus retourne maintenant correctement au document en cours d'édition en fin de saisie en Coréen ou autre langue Est-Asiatique, quand l'édition est dans un cadre sous Internet Explorer et autres documents MSHTML. (#4045)
* Dans le dialogue Gestes de Commandes, quand on sélectionne une configuration clavier pour l'ajout d'un geste clavier, l'appui sur échap ferme maintenant le menu comme prévu au lieu de fermer le dialogue. (#3617)
* Quand on supprime un module complémentaire, le répertoire du module est maintenant effacé correctement au redémarrage de NVDA. avant, il fallait redémarrer deux fois. (#3461)
* Des problèmes majeurs ont été corrigés dans l'utilisation de Skype for Desktop 7. (#4218)
* Quand vous envoyez un message sous Skype for Desktop, il n'est plus lu deux fois. (#3616)
* Dans Skype for Desktop, NVDA ne devrait plus de temps en temps lire un grand nombre de messages (peut-être même une conversation entière). (#4644)
* correction d'un problème qui faisait que la commande d'annonce de la date et de l'heure de NVDA ne respectait pas les paramètres régionaux définis par l'utilisateur dans certains cas. (#2987)
* En mode navigation, un texte sans signification (s'étendant parfois sur plusieurs lignes) n'est plus affiché pour certains graphiques comme on peut en trouver sur Google Groups. (En particulier, ceci arrivait pour les images encodées en base64.) (#4793)
* NVDA ne devrait plus se figer après quelques secondes quand le focus quitte une application Windows 8 Metro-style en cours de suspension. (#4572)
* L'attribut aria-atomic dans les régions live sous Mozilla Firefox est maintenant respecté même quand l'élément atomique lui-même change. Précédemment cela n'affectait que les éléments descendants. (#4794)
* Le mode navigation reflètera les mises à jour, et les régions live seront annoncées, pour les documents en mode navigation dans les applications ARIA incluses dans un document sous Internet Explorer ou autres contrôles MSHTML (#4798)
* Quand du texte est modifié ou ajouté dans des régions live de texte sous Internet Explorer et autres contrôles MSHTML, seul le texte modifié ou ajouté est annoncé, plutôt que tout le texte de l'élément contenant. (#4800)
* Le contenu indiqué par l'attribut aria-labelledby sur des éléments sous Internet Explorer et autres contrôles MSHTML remplace correctement le contenu original là où il est approprié de le faire. (#4575)
* Lors de la vérification orthographique sous Microsoft Outlook 2013, le mot mal orthogaphié est maintenant annoncé. (#4848)
* Sous Internet Explorer et autres contrôles MSHTML, le contenu des éléments cachés avec visibility:hidden n'est plus présenté de manière inappropriée en mode navigation. (#4839, #3776)
* Sous Internet Explorer et autres contrôles MSHTML, l'attribut titre sur les contrôles de formulaire ne prend plus la préférence de manière inappropriée sur les autres associations d'étiquette. (#4491)
* Sous Internet Explorer et autres contrôles MSHTML, NVDA n'ignore plus la mise en focus des éléments à cause de l'attribut aria-activedescendant. (#4667)

### Changements pour les Développeurs

* Mise à jour de wxPython à la version 3.0.2.0. (#3763)
* Mise à jour de Python vers 2.7.9. (#4715)
* NVDA ne se plante plus au redémarrage après retrait ou mise à jour d'un module complémentaire qui importe speechDictHandler dans son module installTasks. (#4496)

## 2014.4

### Nouvelles Fonctionnalités

* Nouvelles langues : Espagnol Colombien, Punjabi
* Il est maintenant possible de redémarrer NVDA normalement ou avec les modules complémentaires désactivés depuis le dialogue d'arrêt de NVDA. (#4057)
 * NVDA peut aussi être démarré sans modules complémentaires en utilisant l'option de ligne de commande --disable-addons.
* Dans les dictionnaires de prononciation, il est maintenant possible de spécifier qu'un modèle ne devrait correspondre que s'il s'agit d'un mot entier. (#1704)

### Changements

* Si vous vous déplacez vers un objet en mode navigation par objet et que cet objet est dans un document en mode revue de document, le mode de revue de document sera automatiquement activé. Précédemment, cela n'arrivait que si l'objet navigateur était déplacé à la suite d'un changement de focus. (#4369)
* La liste des afficheurs braille et celle des synthétiseurs dans leurs dialogues de paramétrage respectifs sont maintenant triées dans l'ordre alphabétique à l'exception de "Pas de Braille" et "Pas de parole" qui se trouvent maintenant en fin de liste. (#2724)
* Mise à jour du traducteur Braille liblouis à la version 2.6.0. (#4434, #3835)
* En mode navigation, l'appui sur e et maj+e pour naviguer entre les zones dédition inclut maintenant les listes déroulantes éditables. Ceci inclut la boîte de recherche dans la dernière version de Google Search. (#4436)
* Un clic gauche sur l'icône NVDA dans la zone de notification ouvre maintenant le menu NVDA au lieu de ne rien faire. (#4459)

### Corrections de bogues

* Quand on ramène le focus vers un document en mode navigation (ex. alt tab vers une page web déjà ouverte) le curseur de revue est correctement positionné au curseur virtuel plutôt qu'au contrôle en focus (ex. un lien proche). (#4369)
* Dans les diaporamas Powerpoint, le curseur de revue suit correctement le curseur virtuel. (#4370)
* Dans Mozilla Firefox et autres navigateurs basés sur Gecko, un nouveau contenu à l'intéieur d'une région live sera annoncé même si le nouveau contenu a un type ARIA live utilisable différent de la région live parent. Ex : Un contenu marqué comme assertif est ajouté à une région live marquée comme polie. (#4169).
* Dans Internet Explorer et autres contrôles MSHTML, certains cas où un document est contenu dans un autre document n'empêchent plus l'utilisateur d'accéder à certains contenus, (en particuliers les cadres dans des cadres). (#4418)
* NVDA ne se plante plus quand on essaie d'utiliser un terminal braille Handy Tech dans certains cas. (#3709)
* Sous Windows Vista, un faux dialogue "Point d'entrée non trouvé" n'est plus affiché dans plusieurs cas tels que le démarrage de NVDA depuis le bureau ou depuis le raccourci clavier. (#4235)
* De sérieux problèmes avec les contrôles de texte éditable dans les dialogues des versions récentes d'Eclipse ont été corrigés. (#3872)
* Dans Outlook 2010, le déplacement du curseur fonctionne maintenant comme prévu dans le champ endroit des demandes de rendez-vous et de réunions. (#4126)
* Dans une région active, le contenu marqué comme inactif (ex : aria-live="off") est maintenant correctement ignoré. (#4405)
* Durant l'annonce d'une barre dd'état ayant un nom, le nom est maintenant correctement séparé du premier mot du texte de la barre d'état. (#4430)
* Dans les champs de saisie de mot de passe quand l'écho par mot est activé, de multiples astérisques ne sont plus annoncées sans raison au commencement d'un nouveau mot. (#4402)
* Dans la liste de messages de Microsoft Outlook, des éléments ne sont plus annoncés sans raison comme éléments de données. (#4439)
* Quand on sélectionne du texte dans le contrôle d'édition de code de l'IDE d'Eclipse, la sélection entière n'est plus annoncée chaque fois que la sélection change. (#2314)
* Différentes versions d'Eclipse, telles que Spring Tool Suite ou la version incluse dans le pack d'outils de développement d'Android, sont maintenant reconnues comme Eclipse et prises en compte de manière appropriée. (#4360)
* Le suivi de la souris et l'exploration tactile sous Internet Explorer et autres contrôles MSHTML (incluant beaucoup d'applications Windows 8) sont maintenant beaucoup plus précis sur les écrans à haute résolution ou quand on change le niveau de zoom du document. (#3494)
* Le suivi de la souris et l'exploration tactile sous Internet Explorer et autres contrôles MSHTML annonceront maintenant l'étiquette de davantage de boutons. (#4173)
* Quand on utilise un terminal braille Papenmeier BRAILLEX avec BrxCom, les touches du terminal fonctionnent maintenant comme prévu. (#4614)

### Changements pour les Développeurs

* Pour les exécutables qui hébergent beaucoup d'applications différentes (ex : javaw.exe), du code peut maintenant être fourni pour charger des modules spécifiques pour chaque application au lieu de charger le même module pour toutes les applications hébergées. (#4360)
 * Consultez la documentation du code de appModuleHandler.AppModule pour des détails.
 * Le support de javaw.exe est implémenté.

## 2014.3

### Nouvelles fonctionnalités

* Les sons joués au démarrage et à l'arrêt de NVDA peuvent être désactivés via une nouvelle option dans le dialogue "Paramètres Généraux". (#834)
* L'aide des modules complémentaires est accessible depuis le Gestionnaire de Modules Complémentaires pour les modules qui le permettent. (#2694)
* Support du Calendrier sous Microsoft Outlook 2007 et plus récent (#2943) incluant :
 * L'annonce de l'heure courante quand on se déplace avec les flèches,
 * L'indication si le temps sélectionné est à l'intérieur d'un rendez-vous,
 * L'annonce du rendez-vous sélectionné à l'appui sur la touche tab
 * Le filtrage intelligent de la date pour ne l'annoncer que si la date ou le rendez-vous sélectionnés sont sur un jour différent du dernier
* Support amélioré de la boîte de réception et des autres listes de messages sous Outlook 2010 et plus récent (#3834) incluant :
 * La possibilité de ne pas annoncer les titres de colonnes (de, sujet etc) en désactivant l'annonce des lignes et colonnes d'un tableau dans le dialogue "Mise en forme des documents",
 * La possibilité d'utiliser les commandes de navigation dans un tableau (contrôle+alt+flèches) pour se déplacer dans une colonne particulière.
* Microsoft word : si une image incluse n'a pas de texte alternatif défini, NVDA annoncera à la place le titre de l'image si l'auteur en a donné un. (#4193)
* Microsoft Word : annonce de l'indentation du paragraphe avec la commande d'annonce du format (NVDA+f) et automatiquement quand le nouveau paramètre "Annoncer l'indentation des paragraphes" du dialogue "Mise en Forme des Documents" est activé. (#4165)
* Annonce du texte inséré automatiquement tel qu'une nouvelle puce, indentation par numéro ou tabulation quand on presse "Entrée" dans les documents éditables et les champs de texte. (#4185)
* Microsoft word : si le curseur est dans un commentaire, l'appui sur NVDA+alt+c annoncera le texte de celui-ci. (#3528)
* Support amélioré de la lecture automatique des titres de lignes et de colonnes sous Microsoft Excel (#3568) incluant :
 * Support des jeux de noms définis par Excel pour identifier les cellules de titre (compatible avec la revue d'écran Jaws)
 * Les commandes de définition de titre de colonne (NVDA+maj+c) et de définition de titre de ligne (NVDA+maj+r) stockent maintenant les paramètres dans la feuille de travail. Ils sont de ce fait, disponibles à la prochaine ouverture de la feuille et utilisables par les autres revues d'écran supportant les jeux de noms définis.
 * Ces commandes peuvent maintenant aussi être utilisées plusieurs fois dans une feuille pour définir différents titres pour différentes régions.
* Support de la lecture automatique des titres de lignes et de colonnes sous Microsoft Word (#3110) incluant :
 * Support des signets MS Word pour identifier les cellules de titre (compatible avec la revue d'écran Jaws)
 -  Les commandes de définition de titre de colonne (NVDA+maj+c) et de définition de titre de ligne (NVDA+maj+r) quand on est sur la première cellule de titre d'un tableau vous permettent d'indiquer à NVDA que ces titres devraient être annoncés automatiquement. les paramètres sont stockés dans le document pour être disponibles lors de la prochaine ouverture du document et pour être utilisable par les revues d'écran supportant le schéma de signets.
* Microsoft Word : annonce de la distance au bord gauche de la page à l'appui sur la touche tab. (#1353)
* Microsoft Word : ajout d'un retour vocal et braille pour la plupart des raccourcis clavier de formatage disponibles (gras, italique, souligné, alignement et niveau hiérarchique). (#1353)
* Microsoft Excel : si la cellule sélectionnée contient des commentaires, ceux-ci peuvent être annoncés, désormais, en tapant NVDA+alt+c. (#2920)
* Microsoft Excel : ajout d'un dialogue spécifique de NVDA pour éditer les commentaires sur la cellule sélectionnée quand on saisit la commande d'Excel maj+f2 pour entrer en mode édition de commentaire. (#2920)
* Microsoft Excel : retour vocal et braille pour beaucoup plus de raccourcis de déplacement de sélection (#4211) incluant :
 * Mouvement vertical de la page (Page Précédente et Page Suivante)
 * Mouvement horizontal de la page (alt+Page Précédente et alt+Page Suivante)
 * Extension de la sélection (les touches ci-dessus combinées à Maj).
 * Sélection de la région en cours (contrôle+maj+8)
* Microsoft Excel : annonce de l'alignement vertical et horizontal des cellules avec la commande d'annonce de mise en forme (NVDA+f) et automatiquement si l'option d'annonce de l'alignement est activée dans le dialogue "Mise en Forme des Documents". (#4212)
* Microsoft Excel : annonce du style d'une cellule avec la commande d'annonce de mise en forme (NVDA+f) et automatiquement si l'option d'annonce du style est activée dans le dialogue "Mise en Forme des Documents". (#4213)
* Microsoft Powerpoint : quand on déplace des formes dans une diapositive avec les flèches, la position courante de la forme est maintenant annoncée (#4214) incluant :
 * L'annonce de la distance entre la forme et chaque bord de la diapositive.
 * Si la forme couvre ou est couverte par une autre forme, la distance de couverture et l'autre forme sont annoncées.
 * Pour obtenir cette information à tout moment sans déplacer une forme, tapez la commande d'annonce de position (NVDA+effacement)
 * Quand on sélectionne une forme, si elle est couverte par une autre, l'état Masqué est annoncé.
* La commande d'annonce de position (NVDA+effacement) est plus spécifique au contexte dans certaines situations. (#4219):
 * Dans les zones d'édition standards et le mode navigation, la position du curseur a un pourcentage dans le contenu, et ses coordonnées à l'écran sont annoncées.
 * Sur les formes dans les Présentations Powerpoint, la position de la forme par rapport à la diapositive et aux autres forme est annoncée.
 * Un double-appui sur cette commande produira l'ancienne façon d'annoncer l'information de position pour l'ensemble du contrôle.
* Nouvelle langue : Catalan.

### Changements

* Mise à jour de la librairie de traduction en braille liblouis vers la version 2.5.4. (#4103)

### Corrections de bogues

* Dans Google Chrome et les navigateurs basés sur Chrome, certains segments de texte (tels que ceux avec un accent) ne sont plus répétés lors de la lecture du texte d'une alerte ou d'un dialogue. (#4066)
* En mode navigation dans les applications Mozilla, l'appui de la touche entrée sur un bouton etc... n'échoue plus à l'activation (ou n'active plus le mauvais élément) dans certains cas comme le bouton en haut de Facebook. (#4106)
* Des informations inutiles ne sont plus annoncées lorsque l'on tabule dans iTunes. (#4128)
* Dans certaines listes d'iTunes comme la liste des musiques, le déplacement à l'élément suivant fonctionne maintenant correctement. (#4129)
* Les éléments HTML considérés comme cachés à cause des marques WAI ARIA sont maintenant inclus dans la liste d'éléments en mode navigation et dans la navigation rapide dans Internet Explorer. (#4140)
* Les liens sur la même page dans les versions récentes d'Internet Explorer déplacent bien le curseur et annoncent bien la position de la destination en mode navigation. (#4134)
* Microsoft Outlook 2010 et plus récent : amélioration de l'accès aux dialogues sécurisées comme les profils ou la configuration des courriels. (#4090, #4091, #4095)
* Microsoft Outlook : diminution de la verbosité des barres d'outils de commandes lorsque l'on navigue dans certains dialogues. (#4096, #3407)
* Microsoft Word : tabuler sur une cellule vide dans un tableau n'annonce plus que l'on quitte le tableau. (#4151)
* Microsoft Word : le premier caractère après la fin d'un tableau (y compris une nouvelle ligne vide) n'est plus considéré à tort comme étant à l'intérieur du tableau. (#4152)
* Dialogue du correcteur orthographique de Microsoft Word 2010 : annonce du vrai mot mal orthographié au lieu de simplement annoncer le premier mot en caractères gras rencontré. (#3431)
* En mode navigation sous Internet Explorer et les autres contrôles MSHTML, tabuler ou utiliser une lettre de navigation pour atteindre une zone d'édition annonce de nouveau l'étiquette (en particulier, là ou des éléments d'étiquette HTML sont utilisés). (#4170)
* Microsoft Word : l'annonce de l'existence et de la position des commentaires est plus précise. (#3528)
* Amélioration de la navigation dans certains dialogues des produits MS Office tels que Word, Excel et Outlook en n'annonçant plus certaines barres d'outils de conteneurs inutiles pour l'utilisateur. (#4198)
* Des volets de Tâches tels que le gestionnaire de presse-papiers ou la récupération de fichiers ne semblent plus accidentellement prendre le focus quand on ouvre une application comme Word ou Excel, ce qui obligeait parfois l'utilisateur à changer de fenêtre et revenir pour accéder au document ou à la feuille de calcul. (#4199)
* NVDA ne refuse plus de fonctionner sur les version récentes de Windows quand la langue de l'utilisateur du système est définie comme Serbe (Latin). (#4203)
* En mode aide à la saisie, l'appui sur verrouillage numérique active et désactive maintenant correctement le verrouillage numérique, au lieu de créer une désynchronisation entre l'état du clavier et l'état du système. (#4226)
* Sous Google Chrome, le titre du document est à nouveau annoncé quand on change d'onglet. Sous NVDA 2014.2, cela ne se produisait pas dans certains cas. (#4222)
* Sous Google Chrome et les navigateurs basés sur Chrome, l'URL du document n'est plus indiqué à l'annonce du document. (#4223)
* Quand on utilise "dire tout" avec le synthétiseur "Pas de parole" (utile pour des tests automatiques), dire tout ira maintenant jusqu'au bout au lieu de s'arrêter à la première erreur. (#4225)
* Dans le dialogue de signature de Microsoft Outlook, la zone d'édition de la signature est maintenant accessible, permettant le suivi du curseur et la détection du format. (#3833)
* Microsoft Word : Quand on lit la dernière ligne d'une cellule de tableau, la cellule entière n'est plus relue. (#3421)
* Microsoft Word : Quand on lit la première ou la dernière ligne d'une table des matière, la table entière n'est plus relue. (#3421)
* En mode "écho clavier par mot" et dans quelques autres cas, les mots ne sont plus incorrectement coupés à certains marquages tels que les signes de voyelle ou les viramas dans les langues indiques. (#4254)
* Sous Goldwave, les champs d'éditions numériques sont maintenant traités correctement. (#670)
* Microsoft Word : quand on se déplace par paragraphe avec contrôle+flècheBas / contrôle+flècheHaut, deux appuis ne sont plus nécessaires dans les listes numérotées ou à puces. (#3290)

### Changements pour les Développeurs

* NVDA possède maintenant un support unifié pour la documentation des modules complémentaires. Consultez la section "Documentation des modules complémentaires" du "Guide de Développement" pour plus de détails. (#2694)
* Quand on fournit des liens de gestes sur un ScriptableObject via __gestures, il est maintenant possible de fournir le mot clé None comme script. Ceci délie le geste dans toutes les classes de base. (#4240)
* Il est maintenant possible de changer le raccourci clavier utilisé pour démarrer NVDA pour les localisations où le raccourci normal pose problème. (#2209)
 * Cela se fait via gettext.
 * Notez que le texte pour l'option Créer un raccourci sur le bureau dans le dialogue d'installation de NVDA, ainsi que le raccourci clavier dans le Guide de l'Utilisateur doivent aussi être mis à jour.

## 2014.2

### Nouvelles fonctionnalités

* L'annonce du texte sélectionné est maintenant possible dans certains champs de saisie personnalisés où l'information d'affichage est utilisée. (#770)
* Dans les applications Java accessibles, l'information sur la position est maintenant annoncée pour les boutons radio et les autres contrôles qui ont une information de groupe. (#3754)
* Dans les applications Java accessibles, les touches de raccourci sont maintenant annoncées lorsque disponibles. (#3881)
* En mode navigation, les étiquettes des régions sont maintenant annoncées. Elles sont maintenant incluses dans le dialogue de liste des éléments. (#1195)
* En mode navigation, les régions labellisées sont maintenant traitées comme des régions. (#3741)
* Dans les documents et applications Internet Explorer, les régions live (aria-live dans la norme w3C) sont supportées, ce qui permet aux auteurs de page web de signaler du contenu comme pouvant changer. (#1846)

### Changements

* Lorsqu'on quitte un dialogue ou une application dans un document en mode navigation, le nom et le type de ce document ne sont plus annoncés. (#4069)

### Corrections de bogues

* Le menu Système standard de Windows n'est plus accidentellement silencieux dans les applications Java. (#3882)
* Lorsque l'on copie du texte avec la revue d'écran, les sauts de ligne ne sont plus ignorés. (#3900)
* Les objets vides inutiles ne sont plus annoncés dans certaines applications lorsque le focus change ou lors de l'utilisation du navigateur d'objets en mode de revue simple. (#3839)
* Les dialogues de messages et les autres dialogues créés par NVDA causent à nouveau l'arrêt de la parole avant leur annonce.
* En mode navigation, les étiquettes des liens et boutons sont maintenant affichées correctement là où il a été défini par l'auteur pour l'accessibilité (spécifiquement, l'utilisation de aria-label ou aria-labelledby). (#1354)
* En mode navigation dans Internet Explorer, le texte contenu dans un élément marqué comme étant pour la présentation (aria-presentation) n'est plus ignoré de manière inappropriée. (#4031)
* Il est maintenant possible de saisir du texte en vietnamien avec le logiciel Unikey. Pour ce faire, décochez la case "Exécuter les touches d'autres applications" ajoutée dans le dialogue "Paramètres du Clavier" de NVDA. (#4043)
* En mode navigation, les boutons radio ou les cases à cocher dans les menus sont annoncés comme des contrôles au lieu de simples textes cliquables. (#4092)
* NVDA ne passe plus incorrectement du mode formulaire au mode navigation lorsqu'un menu radio ou à cocher a le focus. (#4092)
* Dans Microsoft PowerPoint, quand l'écho par mots est activé, les caractères effacés avec la touche retour-arrière ne sont plus annoncés dans le cadre du mot tapé. (#3231)
* Les étiquettes des zones de listes déroulantes sont maintenant correctement annoncées dans les dialogues d'options de Microsoft Office 2010. (#4056)
* En mode navigation dans les applications Mozilla, utiliser les touches de navigation rapide pour aller au bouton ou au champ de formulaire précédent/suivant incluera maintenant les boutons bascule comme prévu. (#4098)
* Le contenu des alertes des applications Mozilla n'est plus annoncé deux fois. (#3481)
* En mode navigation, les conteneurs et régions ne sont plus répétés pendant qu'on navigue dedans en même temps que le contenu de la page change (ex : les sites de Facebook/Twitter). (#2199)
* NVDA récupère mieux la main lorsqu'on change d'application à partir des applications qui cessent de répondre. (#3825)
* Le curseur (point d'insertion) est de nouveau correctement mis à jour lorsqu'on utilise la commande dire tout dans une zone d'édition dessinée directement à l'écran. (#4125)

## 2014.1

### Nouvelles fonctionnalités

* Support de Microsoft PowerPoint 2013. Notez que le mode protégé n'est pas supporté. (#3578)
* Dans Microsoft Word et Excel, NVDA peut maintenant lire le symbole sélectionné en choisissant un symbole dans le dialogue d'insertion de symbole. (#3538)
* Il est maintenant possible de définir si du contenu dans des documents peut être identifié comme cliquable, via une nouvelle option dans le dialogue Mise en Forme des Documents. Cette option est activée par défaut (conformément au comportement précédent). (#3556)
* Support des afficheurs braille connectés via Bluetooth sur des ordinateurs utilisant Widcomm Bluetooth Software. (#2418)
* Lors de l'édition de texte dans Powerpoint, les liens sont maintenant rapportés. (#3416)
* Dans les applications ARIA ou les dialogues Web, il est maintenant possible de forcer NVDA à passer en mode navigation avec NVDA+Espace, permettant le parcours de cette application ou de ce dialogue comme un document. (#2023)
* Dans Outlook Express / Windows Mail / Windows Live Mail, NVDA annonce maintenant si un message a une pièce jointe ou s'il est marqué. (#1594)
* Lors de la navigation dans des tableaux dans les applications Java accessibles, les coordonnées de lignes et de colonnes sont maintenant signalées, ainsi que les titres de colonnes et de lignes, s'ils existent. (#3756)

### Changements

* Pour les afficheurs braille Papenmeier, la commande passer en mode revue/focus a été supprimée. Les utilisateurs peuvent assigner leur propre combinaison en utilisant le dialogue Geste d'entrée. (#3652)
* NVDA dépend maintenant des runtimes Microsoft VC version 11, ce qui signifie qu'il ne peut plus être exécuté sur les systèmes d'exploitation plus vieux que Windows XP SP2 ou Windows Server 2003 SP1.
* Le niveau de symboles et ponctuations Quelques-uns annonce maintenant les caractères astérisque (*) et plus (+). (#3614)
* Mise à jour d'eSpeak vers la version 1.48.04 qui inclut de nombreuses corrections de langue et corrige plusieurs plantages. (#3842, #3739, #3860)

### Corrections de bogues

* Lorsque l'on se déplace ou que l'on sélectionne des cellules dans Microsoft Excel, NVDA ne devrait plus annoncer l'ancienne cellule au lieu de la nouvelle cellule lorsque Microsoft Excel est lent à déplacer la sélection. (#3558)
* NVDA gère correctement l'ouverture d'une liste déroulante pour une cellule dans Microsoft Excel via le menu contextuel. (#3586)
* Le nouveau contenu des pages du magasin iTunes 11 est correctement affiché en mode navigation lorsqu'on suit un lien dans le magasin ou en ouvrant le magasin. (#3625)
* Les boutons pour la prévisualisation des chansons dans la boutique iTunes 11 affichent maintenant leur label en mode navigation. (#3638)
* En mode navigation dans Google Chrome, les étiquettes des cases à cocher et des boutons radio sont maintenant affichées correctement. (#1562)
* Dans Instantbird, NVDA ne signale plus d'informations inutiles chaque fois que vous vous déplacez à un contact dans la liste des contacts. (#2667)
* En mode navigation dans Adobe Reader, le texte correct est maintenant rendu pour les boutons, etc où l'étiquette a été remplacée à l'aide d'une info-bulle ou d'autres moyens. (#3640)
* En mode navigation dans Adobe Reader, les graphiques étrangers contenant le texte "mc-ref" ne seront plus rendus. (#3645)
* NVDA ne signale plus toutes les cellules dans Microsoft Excel comme soulignées dans leurs informations de formatage. (#3669)
* NVDA n'affiche plus de caractères illisibles dans les documents en mode navigation tels que ceux trouvés dans la gamme de l'usage privé Unicode. Dans certains cas, cela empêchait l'affichage de certains intitulés de champs. (#2963).
* Les langues d'entrée Est-Asiatiques n'échouent plus dans PuTTY. (#3432)
* Naviguer dans un document après avoir annulé Dire Tout n'annonce plus la sortie d'un conteneur dans lequel NVDA n'est pas passé pendant Dire Tout. (#3688)
* Lorsque l'on utilise les touches de navigation rapide en mode dire tout avec le survol activé, NVDA annonce plus précisément le nouveau champ (ex : il annonce maintenant un titre est un titre au lieu de n'annoncer que son texte). (#3689)
* Les touches de navigation rapide pour sauter au début ou à la fin d'un conteneur fonctionnent maintenant correctement en mode dire tout quand le survol est activé au lieu d'interrompre la lecture. (#3675)
* Les noms de gestes tactiles listés dans le dialogue Gestes d'Entrée de NVDA sont maintenant mieux nommés et traduits. (#3624)
* NVDA ne cause plus le plantage de certains programmes lorsque l'on déplace la souris sur leur zone d'édition riche (TRichEdit). Ces programmes incluent Jarte 5.1 et BRfácil. (#3693, #3603, #3581)
* Dans Internet Explorer et autres composants MSHTML, les conteneurs comme les tableaux marqués comme présentation par ARIA ne sont plus rapportés à l'utilisateur. (#3713)
* Dans Microsoft Word, NVDA ne répète plus les informations de ligne/colonne d'une cellule d'un tableau de manière inappropriée en braille. (#3702)
* Dans les langues utilisant l'espace comme séparateur de groupes de nombres ou de milliers comme le Français ou l'Allemand, les groupes distincts de texte ne sont plus prononcés comme un nombre. Cela était particulièrement problématique dans les cellules de tableaux. (#3698)
* Le Braille n'échoue plus à la mise à jour lorsque le curseur système est déplacé dans Microsoft Word 2013. (#3784)
* Lorsque l'on est sur le premier caractère d'un titre dans Microsoft Word, le texte indiquant qu'il s'agit d'un titre (y compris son niveau) ne disparaît plus de l'afficheur braille. (#3701)
* Lorsqu'un profil de configuration est déclenché par une application et que celle-ci est quittée, NVDA n'échoue plus en désactivant le profil. (#3732)
* Lors de la saisie en langue d'entrée d'Asie dans un contrôle de NVDA lui-même (ex : le dialogue rechercher en mode navigation), NVDA n'est plus annoncé à la place du candidat. (#3726)
* Les onglets du dialogue des options d'Outlook 2013 sont maintenant signalés. (#3826)
* Amélioration du support des ARIA Live Regions dans Firefox et les autres applications basées sur Mozilla Gecko :
 * Support des mise à jours aria-atomic et du filtrage des mise à jours aria-busy (#2640)
 * Le texte alternatif (comme l'attribut alt ou aria-label) est inclus s'il n'y a aucun autre texte. (#3329)
 * Les mises à jour de région ARIA-live ne sont plus silencieuses si elles se produisent en même temps que le focus bouge. (#3777)
* Certains éléments de présentation dans Firefox et dans les autres applications Mozilla Gecko ne sont plus montrés en mode navigation (spécifiquement quand l'élément est marqué avec aria-presentation mais est aussi activable). (#3781)
* Amélioration des performances lors de la navigation sur un document dans Microsoft Word avec l'annonce des erreurs d'orthographe activée. (#3785)
* Plusieurs correctifs pour le support des applications Java accessibles :
 * Le premier contrôle actif dans un cadre ou dialogue n'échoue plus à être déclaré lorsque le cadre ou dialogue vient au premier plan. (#3753)
 * Les informations de position inutiles ne sont plus annoncées pour les boutons radio (par exemple 1 sur 1). (#3754)
 * Meilleur rendu des contrôles JComboBox (html n'est plus rapporté, meilleure communication des États développé et réduit). (#3755)
 * Lors de l'annonce du texte d'un dialogue, certains textes manquants jusqu'alors sont maintenant lus. (#3857)
 * Les changements dans le nom, la valeur ou la description du contrôle ayant le focus sont maintenant rapportés avec plus de précision. (#3770)
* Correction d'un crash de NVDA sous Windows 8 lors de l'activation de certains contrôles RichEdit contenant de grandes quantités de texte (visionneuse de journaux NVDA, ou dans windbg par exemple). (#3867)
* Sur les systèmes avec un paramètre d'affichage haute DPI (la plupart des écrans modernes), NVDA ne place plus la souris au mauvais endroit dans certaines applications. (#3758, #3703)
* Correction d'un problème occasionnel lors de la navigation sur le web où NVDA cessait de fonctionner correctement jusqu'à ce qu'on le redémarre, même si elle ne s'est pas figé ou s'il n'a pas plantée. (#3804)
* Un afficheur braille Papenmeier peut maintenant être utilisé même si aucun afficheur braille Papenmeier n'a déjà été branché en USB. (#3712)
* NVDA ne se bloque plus lorsque l'ancien modèle d'afficheur braille Papenmeier BRAILLEX est sélectionné sans qu'un afficheur ne soit connecté.

### Changements pour les développeurs

* AppModule contient maintenant les propriétés productName et productVersion. Ces informations sont maintenant également affichées dans les informations pour les développeurs (NVDA+F1). (#1625)
* Dans la console Python, on peut maintenant appuyer sur Tab pour avoir une auto-complétion. (#433)
 * S'il y a plusieurs possibilités, on peut appuyer une deuxième fois sur Tab afin de choisir dans une liste.

## 2013.3

### Nouvelles Fonctionnalités

* Les champs de formulaires sont maintenant annoncés dans les documents Microsoft Word. (#2295)
* NVDA peut maintenant annoncer les informations de révision dans Microsoft Word lorsque le suivi des modifications est activé. Notez qu'annoncer les révisions de l'éditeur dans le dialogue Paramètres de préférences de mise en forme des document de NVDA (désactivée par défaut) doit être activée également pour qu'elles soient annoncées. (#1670)
* Les listes déroulantes dans Microsoft Excel 2003 à 2010 sont maintenant annoncées lors de leur ouverture et lorsqu'on navigue autour. (#3382)
* Une nouvelle option "Permettre le survol en mode dire tout" dans le dialogue des paramètres du clavier permet de naviguer dans un document avec les commandes de navigation rapide en mode navigation, ou de se déplacer entre les lignes ou paragraphes tout en restant dans dire tout. Cette option est désactivée par défaut. (#2766)
* Il existe maintenant un dialogue Geste de Saisie qui permet une configuration plus aisée des gestes d'entrée (comme les touches de raccourcis clavier) des commandes NVDA. (#1532)
* Il est maintenant possible d'avoir des paramètres différents pour différentes situations à l'aide de profils de configuration. Les profils peuvent être activés manuellement ou automatiquement (par exemple pour une application particulière). (#87, #667, #1913)
* Dans Microsoft Excel, les cellules qui sont des liens sont maintenant annoncées comme liens. (#3042)
* Dans Microsoft Excel, l'existence de commentaires sur une cellule est maintenant signalé à l'utilisateur. (#2921)

### Corrections de Bogues

* Zend Studio fonctionne maintenant de la même manière qu'Eclipse. (#3420)
* Le changement d'état de certaines cases à cocher dans le dialogue des règles de messages de Microsoft Outlook 2010 est maintenant annoncé. (#3063)
* NVDA signale maintenant l'état épinglé pour des éléments épinglés comme des onglets dans Mozilla Firefox. (#3372)
* Il est maintenant possible de lier des scripts à des touches de raccourci contenant les touches Alt et/ou Windows comme modificateurs. précédemment, si cela était fait, l'exécution de ces script causait l'activation de la barre de menus ou du menu démarrer. (#3472)
* Sélectionner du texte dans des documents en mode navigation (ex : en utilisant ctrl+maj+fin) ne cause plus le changement de disposition du clavier dans les systèmes ayant plusieurs dispositions clavier installées. (#3472)
* Internet Explorer ne devrait plus se bloquer ou devenir inutilisable lors de la fermeture de NVDA. (#3397)
* certains gestes physiques et autres événements sur certains ordinateurs récents ne sont plus considérés comme des appuis de touches inappropriés. Auparavant, ceux-ci arrêtaient la parole et parfois déclenchaient des commandes NVDA. (#3468)
* NVDA se comporte maintenant comme prévu dans Poedit 1.5.7. Les utilisateurs utilisant des versions antérieures devront mettre à jour poedit. (#3485)
* NVDA peut maintenant lire des documents protégés dans Microsoft Word 2010, ne causant plus aucun plantage de Microsoft Word. (#1686)
* Passer un paramètre de ligne de commande inconnue au package de distribution de NVDA ne provoque plus une boucle de dialogues de messages d'erreurs sans fin. (#3463)
* NVDA n'échoue plus lors de l'annonce du texte alt des graphiques et des objets dans Microsoft Word si le texte alt contient des guillemets ou d'autres caractères non-standards. (#3579)
* Le nombre d'éléments pour certaines listes horizontales en mode Navigation est maintenant correct. Auparavant, il pouvait être le double de la quantité réelle. (#2151)
* Lorsque vous appuyez sur Ctrl+A dans une feuille de calcul Microsoft Excel, la sélection mise à jour sera maintenant signalée. (#3043)
* NVDA peut maintenant lire correctement les documents XHTML dans Microsoft Internet Explorer et autres contrôles MSHTML. (#3542)
* Dialogue des paramètres du clavier : si aucune touche n'a été choisie pour être utilisée comme touche NVDA, une erreur est présentée à l'utilisateur lorsqu'il a fermé le dialogue. Au moins une touche doit être choisie pour utiliser correctement NVDA. (#2871)
* Dans Microsoft Excel, NVDA annonce maintenant les cellules fusionnées différemment par rapport à l'annonce de plusieurs cellules sélectionnées. (#3567)
* Le curseur du mode navigation n'est plus incorrectement positionné en quittant un dialogue ou une application du document. (#3145)
* Correction d'un problème où le pilote Braille des afficheurs braille HumanWare de séries Brailliant BI/B n'était pas affiché comme choix possible dans le dialogue des paramètres braille sur certains systèmes, même si un tel afficheur est connecté via USB.
* NVDA n'échoue plus pour passer en revue de l'écran lorsque l'objet du navigateur n'a pas d'emplacement réel sur l'écran. Dans ce cas, le curseur de revue est maintenant placé en haut de l'écran. (#3454)
* Correction d'un problème qui causait l'échec du pilote de l'afficheur braille Freedom Scientific dans certaines circonstances lorsque le port a été réglé sur USB. (#3509, #3662)
* Correction d'un problème où les touches des afficheurs braille Freedom Scientific n'étaient pas détectées dans certaines circonstances. (#3401, #3662)

### Changements pour les développeurs

* On peut maintenant spécifier la catégorie affichée à l'utilisateur pour les scripts en utilisant l'attribut scriptCategory de la classe ScriptableObject et l'attribut category sur les méthodes de scripts. Reportez-vous à la documentation de baseObject.ScriptableObject pour plus de détails. (#1532)
* config.save est obsolète et pourrait être supprimée dans une version future. Utilisez plutôt config.conf.save. (#667)
* config.validateConfig est obsolète et pourrait être supprimée dans une version future. Les modules complémentaires utilisant cette fonction devraient proposer leur propre implémentation. (#667, #3632)

## 2013.2

### Nouvelles Fonctionnalités

* Support du framework Chromium Embedded, un composant de navigateur web utilisé par certaines applications. (#3108)
* Nouvelle variante eSpeak : Iven3.
* Dans Skype, les nouveaux messages de conversation sont maintenant automatiquement rapportés lorsque la fenêtre de conversation est active. (#2298)
* Support de Tween, incluant l'annonce du nom des onglets et moins de verbosité en lisant les tweets.
* Vous pouvez maintenant désactiver l'affichage des messages NVDA en braille en mettant à 0 la durée d'affichage dans les préférences Braille. (#2482)
* Dans le gestionnaire de modules complémentaires, il y a maintenant un bouton Obtenir des modules complémentaires qui ouvre le site des modules complémentaires NVDA à fin d'en installer. (#3209)
* Dans le dialogue de bienvenue qui se lance au premier démarrage de NVDA, vous pouvez maintenant définir si NVDA doit démarrer après l'ouverture de votre session. (#2234)
* Le mode veille de NVDA est automatiquement activé lors de l'utilisation de Dolphin Cicero. (#2055)
* La version Windows x64 de Miranda IM/Miranda NG est maintenant supportée. (#3296)
* Les suggestions de recherche dans l'écran de démarrage de Windows 8.1 sont automatiquement annoncées. (#3322)
* Support du parcours et de l'édition des feuilles de calcul dans Microsoft Excel.
* Les afficheurs brailles Freedom Scientific Focus 14 Blue et Focus 80 Blue, comme les Focus 40 Blue dans certaines configuration qui n'étaient pas supportées avant, sont maintenant prises en charge lorsque connectées via Bluetooth. (#3307)
* Les suggestions d'auto-complétion sont maintenant annoncées dans Outlook 2010. (#2816)
* Nouvelles tables braille : anglais (Royaume-Uni) braille informatique, Coréen grade 2, Russe code braille informatique.
* Nouvelle langue : Farsi. (#1427)

### Changements

* Sur un écran tactile, glisser une fois le doigt vers la gauche ou la droite lorsque l'on est en mode objet passe au mode revue précédent/suivant de l'objet. Utilisez deux doigts pour l'ancienne méthode.
* La case à cocher Annoncer les tables de visualisation qui se trouve dans le dialogue Mode Navigation a été renommée en Inclure les tables de visualisation pour indiquer que la navigation rapide ne les trouvera pas si la case est décochée. (#3140)
* Le mode revue à plat a été remplacé par les modes revue d'objet, de document ou d'écran. (#2996)
 * La revue d'objet permet de lire le texte de l'objet sous le navigateur, la revue de document tout le texte d'un document en mode navigation, et le mode revue de l'écran permet de lire tout le texte visible à l'écran de l'application en cours.
 * Les commandes de la revue à plat sont maintenant utilisées pour basculer entre les modes de revue.
 * Le navigateur d'objet suit automatiquement le curseur de revue lorsqu'en mode revue d'objet.
 * Lorsqu'en mode revue de l'écran, celui-ci reste actif jusqu'à ce que vous en changiez.
 * Lorsqu'en mode revue d'objet ou de document, NVDA peut automatiquement basculer d'un mode à l'autre selon que vous êtes ou non sur un document en mode navigation.
* Librairie de traduction braille liblouis mise à jour vers la version 2.5.3. (#3371)

### Corrections de Bogues

* Activer un objet annonce maintenant l'action avant l'activation au lieu de l'inverse (ex : étendre lorsque l'on étend au lieu de réduire). (#2982)
* Meilleure gestion du curseur dans certaines zones d'édition Skype en version récentes, comme la zone de saisie des conversations et dans la recherche de contact. (#1601, #3036)
* Dans la liste des actions récentes Skype, le nombre de nouveaux événements est affiché lorsqu'applicable. (#1446)
* Meilleure gestion du curseur pour la lecture de droite à gauche de texte sur l'écran. Ex : éditer du texte en arabe dans Microsoft Excel. (#1601)
* La navigation rapide vers les boutons et champs de formulaires localisera maintenant les liens marqués comme des boutons pour l'accessibilité dans Internet Explorer. (#2750)
* En mode navigation, le contenu dans les arborescences n'est plus rendu, vu qu'une présentation à plat n'est pas utile. Vous pouvez appuyer sur entrée dans une arborescence pour interagir avec lorsqu'elle a le focus. (#3023)
* Appuyer sur Alt+Bas ou haut dans une zone de liste en mode focus ne repasse plus incorrectement en mode navigation. (#2340)
* Dans Internet Explorer 10, les cellules de tableau n'activent plus le mode focus sauf si marquées comme activables par le développeur. (#3248)
* NVDA n'échoue plus au démarrage si l'heure système est antérieure à la dernière mise à jour. (#3260)
* Si une barre de progression est affichée en braille, le braille est mis à jour avec la barre de progression. (#3258)
* En mode navigation dans les applications Mozilla, les titres de tableau ne sont plus rendus deux fois. De plus, le résumé est aussi affiché s'il y a un titre. (#3196)
* Lorsqu'on change de langue dans Windows 8, NVDA parle la bonne langue au lieu de ne pas en changer.
* NVDA annonce les modes de conversion IME dans windows 8.
* NVDA n'annonce plus du vide sur le bureau lorsque les méthodes Google Japonaise ou Atok sont utilisées. (#3234)
* Dans windows 7 et supérieur, NVDA n'annonce plus la reconnaissance vocale ou le tactile comme un changement de langue.
* NVDA n'annonce plus un caractère spécial (0x7f) quand on presse contrôle+retourArrière dans certains éditeurs quand l'écho caractères est activé. (#3315)
* eSpeak ne change plus de hauteur, volume, etc. de manière inappropriée quand NVDA lit un texte contenant certains caractères de contrôle ou XML. (#3334) (régression de #437)
* Dans les applications Java, les changements de l'étiquette ou de la valeur du contrôle en focus sont maintenant annoncés automatiquement, et sont reflétés lors d'une interrogation ultérieure du contrôle. (#3119)
* Dans les contrôles Scintilla, les lignes sont maintenant annoncées correctement quand le renvoi à la ligne automatique est activé. (#885)
* Dans les applications Mozilla, le nom des listes en lecture seule est correctement annoncé ; ex : en navigant entre les tweets en mode focus sur Twitter.com. (#3327)
* Le contenu des dialogues de confirmation Microsoft Office 2013 est maintenant automatiquement lu.
* Amélioration des performances lors de la lecture de tableaux dans Microsoft Word. (#3326)
* Les commandes de lecture de tableau de NVDA (contrôle+alt+flèches) fonctionnent mieux dans certains tableaux Microsoft Word où une cellule prend plusieurs rangées.
* Si le gestionnaire de modules complémentaires est déjà ouvert, l'activer à nouveau (par le menu outils ou en ouvrant un fichier .nvda-addon) n'échoue plus ou ne rend plus impossible la fermeture du gestionnaire de modules complémentaires. (#3351)
* NVDA ne se fige plus dans les dialogues quand l'IME Japonais ou Chinois est utilisé dans Office. (#3064)
* Les espaces multiples ne sont plus compressés en un seul en braille. (#1366)
* Les outils pour développeurs Zend dans Eclipse PHP sont accessibles au même titre qu'Eclipse. (#3353)
* Dans Internet Explorer, il n'est à nouveau plus nécessaire d'appuyer sur Tab pour interagir avec un objet intégré après avoir appuyé sur entré dessus. (#3364)
* Lors de l'édition de texte dans Microsoft PowerPoint, la dernière ligne n'est plus rapportée comme la ligne du dessus, si la dernière ligne est blanche. (#3403)
* Dans Microsoft PowerPoint, les objets ne sont plus parfois annoncé deux fois lorsqu'on les sélectionne ou qu'on choisi de les éditer. (#3394)
* NVDA ne fait plus planter ou figer Adobe Reader avec certains documents PDF mal formés contenant des lignes hors d'un tableau. (#3399)
* NVDA détecte maintenant correctement le prochain slide ayant le focus lorsqu'on en supprime un dans la vue miniature de PowerPoint. (#3415)

### Changements pour les développeurs

* windowUtils.findDescendantWindow a été ajouté pour rechercher une fenêtre descendante (hwnd) spécifiant la même visibilité, type d'élément ou nom de classe.
* La console python distante ne se ferme plus au bout de dix seconde si rien n'a été entré. (#3126)
* L'inclusion du module bisect dans les binaires est maintenant dépréciée et pourrait être supprimée dans une future version. (#3368)
 * Les modules complémentaires dépendant de bisect (incluant le module urllib2) devraient être mis à jour pour inclure

## 2013.1.1

Cette version corrige un problème qui faisait que NVDA cessait de fonctionner au démarrage s'il était configuré pour utiliser la langue irlandaise. Elle apporte des mises à jour des traductions et des corrections de bogues mineurs.

### Corrections de Bogues

* Les caractères corrects sont affichés lorsque l'on saisit dans l'interface utilisateur de NVDA en utilisant une méthode de saisie Coréenne ou Japonnaise en tant que méthode par défaut. (#2909)
* Dans Internet Explorer et les autres objets MSHTML, les champs marqués comme contenant une entrée invalide sont correctement gérés. (#3256)
* NVDA n'échoue plus au démarrage en présence de la langue irlandaise.

## 2013.1

Les apports majeurs de cette version incluent une disposition clavier ordinateur portable plus intuitive et logique ; un support basique de Microsoft PowerPoint ; le support des descriptions longues dans les navigateurs web ; et le support de la saisie du braille informatique pour les afficheurs brailles disposant d'un clavier braille.

### Important

#### Nouvelle disposition clavier ordinateur portable

La disposition clavier ordinateur portable a été revue pour être plus intuitive et cohérente.
La nouvelle disposition utilise les flèches combinées avec la touche NVDA et autres touches pour les commandes de revue.

Notez les changements suivants pour les commandes communément utilisées :

| Nom |Touche|
|---|---|
|Dire tout |NVDA+a|
|Lire la ligne courante |NVDA+l|
|Lire le texte sélectionné |NVDA+maj+s|
|Lire la barre d'état |NVDA+maj+end|

En plus d'autres changements, toutes les commandes de la navigation par objet, de la revue de texte, clic souris et de paramétrage de voix ont changé.
Veuillez lire le document [Résumé des commandes](keyCommands.html) pour les nouveaux raccourcis.

### Nouvelles Fonctionnalités

* Support basique de l'édition et de la lecture des présentations Microsoft PowerPoint. (#501)
* Support basique pour la lecture et l'écriture de messages dans Lotus Notes 8.5. (#543)
* Support du changement automatique de langue lors de la lecture de documents dans Microsoft Word. (#2047)
* En mode navigation dans les documents MSHTML (ex : Internet Explorer) et Gecko (ex : Firefox), l'existence des longues descriptions est maintenant annoncée. Il est aussi possible d'ouvrir les longues descriptions dans une nouvelle fenêtre en appuyant sur NVDA+D. (#809)
* Les notifications dans Internet Explorer 9 et supérieur sont maintenant lues (comme les fenêtres publicitaires bloquées ou les téléchargements). (#2343)
* L'annonce automatique du titre des lignes et colonnes d'un tableau est maintenant supportée dans Internet Explorer et les autres contrôles MSHTML. (#778)
* Nouvelles langues : Aragonais, Irlandais.
* Nouvelles tables Braille : Danois Grade 2, Coréen Grade 1. (#2737)
* Support des afficheurs Braille connectés via le Bluetooth sur les ordinateurs utilisant Bluetooth Stack for Windows by Toshiba. (#2419)
* Support de la sélection du port pour les afficheurs freedom Scientific (Automatique, USB ou Bluetooth).
* Support des bloc-notes BrailleNote de Humanware lorsqu'ils agissent comme afficheur Braille pour un lecteur d'écran. (#2012)
* Support des anciens modèles d'afficheur Braille Papenmeier BRAILLEX. (#2679)
* Support de la saisie en braille informatique pour les afficheurs braille disposant d'un clavier braille. (#808)
* Nouvelles options de clavier permettant d'interrompre ou non la parole lorsqu'on appuie sur une touche et ou sur entrer. (#698)
* Support de certains navigateurs basés sur Google Chrome : Rockmelt, BlackHawk, Comodo Dragon et SRWare Iron. (#2236, #2813, #2814, #2815)

### Changements

* liblouis Braille Translator mis à jours vers la version 1.5.2. (#2737)
* La disposition clavier ordinateur portable a été revue pour être plus intuitive et cohérente. (#804)
* Mise à jours de la synthèse vocale eSpeak vers la version 1.47.11. (#2680, #3124, #3132, #3141, #3143, #3172)

### Corrections de Bogues

* La touche de navigation rapide pour passer au séparateur précédent ou suivant en mode navigation fonctionne maintenant dans Internet Explorer et les autres documents MSHTML. (#2781)
* Si NVDA revient à eSpeak ou pas de parole à cause d'une erreur dans le synthétiseur configuré lors du démarrage de NVDA, la configuration n'est plus modifiée pour prendre la valeur du nouveau synthétiseur, ce qui signifie que NVDA essaiera encore de charger le synthétiseur en erreur lors du prochain démarrage. (#2589)
* Si NVDA revient à pas de braille à cause d'une erreur dans l'afficheur braille configuré lors du démarrage de NVDA, la configuration n'est plus modifiée pour prendre la valeur du nouvel afficheur, ce qui signifi que NVDA essayera encore de chargé l'afficheur braille en erreur lors du prochain démarrage. (#2264)
* En mode navigation dans les applications Mozilla, les mises à jour de tableaux sont maintenant correctement rendues. Par exemple, dans les cellules mises à jour, les coordonnées de ligne et de colonne sont correctement annoncées et les touches de navigation dans un tableau fonctionnent comme prévu. (#2784)
* En mode navigation dans les navigateurs Internet, certains graphiques cliquables sans étiquette n'étaient pas rendus et le sont maintenant correctement. (#2838)
* Les anciennes et nouvelles versions de SecureCRT sont maintenant supportées. (#2800)
* Pour certaines méthodes d'entrée IME dans Windows XP, la chaîne de lecture est maintenant correctement rapportée.
* La liste de candidats de la méthode d'entrée Chinois simplifié Microsoft Pinyin sous Windows 7 est maintenant lue correctement lorsqu'on change de page avec les flèches gauche et droite, et en l'ouvrant la première fois avec Origine.
* Quand la personnalisation de prononciations des symboles est sauvegardée, le champ avancé "préservé" n'est plus supprimé. (#2852)
* Lorsqu'on désactive la recherche automatique de mise à jour, il n'est plus nécessaire de redémarrer NVDA pour que le changement prenne effet.
* NVDA n'est plus en échec dès le démarrage si un module complémentaire n'a pas pu être supprimé parce que son dossier est utilisé par une autre application. (#2860)
* Le nom des onglets dans le dialogue des préférences de DropBox peut maintenant être vu en mode revue à plat.
* Si la langue d'entrée est changée par une autre que celle par défaut, NVDA détecte maintenant correctement les touches pour les commandes et l'aide à la saisie.
* Pour les langues comme l'Allemand ou le signe + (plus) est une seule touche du clavier, il est maintenant possible d'y assigner un raccourci avec le mot "plus". (#2898)
* Dans Internet Explorer et les autres contrôles MSHTML, les balises de citation sont signalées à l'endroit approprié. (#2888)
* Les afficheurs Braille HumanWare de série Brailliant BI/B peuvent maintenant être sélectionnés quand l'afficheur est connecté via bluetooth mais qu'il n'a jamais été connecté via USB.
* Filtrer les éléments dans la liste des éléments en mode navigation avec des filtres en texte majuscules retourne maintenant les même résultats que si tout était en minuscule. (#2951)
* Dans les navigateurs Mozilla, le mode navigation peut à nouveau être utilisé quand du contenu flash est activé. (#2546)
* Lorsque l'on utilise une table braille abrégé et que l'option Afficher le mot sous le curseur en braille informatique est activée, le curseur braille est maintenant positionné correctement lorsque situé après un mot dans lequel un caractère est représenté par plusieurs cellules brailles (ex : signe majuscule, signe de lettre, signe de nombre, etc.). (#2947)
* Le texte sélectionné est maintenant correctement affiché en braille dans des applications comme Microsoft Word 2003 et les zone d'édition dans Internet Explorer.
* Il est à nouveau possible de sélectionner du texte en arrière dans Microsoft Word lorsque le braille est activé.
* Lorsqu'on lit ou supprime un caractère avec retour-arrière ou suppr dans une zone d'édition Scintilla, NVDA annonce correctement les caractères multibyte. (#2855)
* NVDA n'échouera plus à l'installation lorsque le chemin du profil contient des caractères multibyte. (#2729)
* L'annonce des groupes dans les vues de liste (SysListview32) dans les applications 64-bits ne cause plus d'erreur.
* En mode navigation dans les applications Mozilla, le contenu texte n'est plus considéré comme éditable dans de rares cas. (#2959)
* Dans IBM Lotus Symphony et OpenOffice, déplacer le curseur déplace également le curseur de revue lorsqu'aproprié.
* Le contenu Adobe Flash est maintenant accessible dans Internet Explorer sous Windows 8. (#2454)
* Correction du support bluetooth de l'afficheur braille Papenmeier Braillex Trio. (#2995)
* Corrigée l'impossibilité d'utiliser certaines voix Microsoft SAPI version 5 tel que les voix Koba Speech 2. (#2629)
* Dans les applications utilisant Java Access Bridge, l'afficheur braille est correctement rafraîchi lorsque le curseur se déplace dans une zone d'édition. (#3107)
* Support du repère form en mode navigation dans les documents supportant les repères. (#2997)
* Le pilote de synthèse vocale espeak supporte mieux le mode épellation (ex : annonce la valeur de la lettre plutôt que sa phonéthique). (#3106)
* NVDA n'échoue plus lors de la copie de la configuration utilisateur pour utilisation à l'écran de connexion et les autres écrans sécurisés lorsque le chemin du profil contient des caractères non ASCII. (#3092)
* NVDA ne se fige plus lorsque l'on saisi des caractères asiatiques dans certaines applications .NET. (#3005)
* Il est maintenant possible d'utiliser le mode navigation pour les pages sous Internet Explorer 10 lorsque l'on est en mode standard ; Ex : la page de connexion de [www.gmail.com](http://www.gmail.com). (#3151)

### Changements pour les développeurs

* Les afficheurs Braille peuvent maintenant supporter la sélection manuelle du port. (#426)
 * C'est surtout utile pour les afficheurs Braille qui supportent la connexion via un port série.
 * Cela se fait en utilisant la méthode de classe getPossiblePorts dans la classe BrailleDisplayDriver.
* La saisie en braille via un clavier braille est maintenant supportée. (#808)
 * La saisie en braille est gérée par la classe brailleInput.BrailleInputGesture ou d'une sous-classe.
 * Les sous-classes de braille.BrailleDisplayGesture (implémentée comme dans les pilotes d'afficheurs brailles) peuvent aussi hériter de brailleInput.BrailleInputGesture. Cela permet que les commandes braille et la saisie soient gérés par la même classe de commande.
* On peut maintenant utiliser comHelper.getActiveObject pour récupérer un objet COM depuis un processus normal quand NVDA est exécuté avec le privilège UIAccess. (#2483)

## 2012.3

Les apports majeurs de cette version incluent le support de la saisie des caractèrs asiatiques ; le support expérimental des écrans tactiles sous Windows 8 ; l'annonce des numéro de page et le support amélioré des tableaux dans Adobe Reader ; le support de la navigation entre les cellules des liste multi-colones ou en tableau ; le support de plusieurs nouveaux afficheurs Braille ; et l'annonce des titres de lignes et colonnes dans les tableaux Microsoft Excel.

### Nouvelles Fonctionnalités

* NVDA supporte maintenant la saisie des caractères asiatiques en utilisant les méthodes IME et les services de saisie de texte dans toutes les applications, incluant :
 * Rapport et navigation dans les listes de suggestions;
 * Rapport et navigation dans les chaînes de composition ; et
 * Lecture des chaînes lues.
* La présence de soulignements et de superpositions est maintenant rapportée dans les documents Adobe Reader. (#2410)
* Quand la fonction touches rémanentes de Windows est activée, la touche NVDA se comportera comme les autre touches de combinaisons. Cela vous permet de l'utiliser sans la maintenire enfoncée pendant que vous pressez d'autre touches. (#230)
* L'annonce de titre des lignes et colonnes de tableaux est maintenant supportée dans Microsoft Excel. Appuyez sur NVDA+maj+c pour définir la ligne contenant le titre des colonnes, et NVDA+maj+r pour la colonne contenant le titre des lignes. Appuyer deux fois rapidement l'une de ces combinaison efface le paramètre. (#1519)
* Support pour les afficheurs braille HIMS Braille Sense, Braille EDGE et SyncBraille. (#1266, #1267)
* Lorsque les notifications Toast Windows 8 apparaissent, NVDA les annonce si l'annonce des infobulles est activée. (#2143)
* Support expérimentale des écrans tactiles sous Windows 8, incluant :
 * Lecture du texte sous le doigt lorsqu'on le bouge autour
 * Beaucoup de gestes pour naviguer entre les objets, le curseur de revue, et d'autres commandes de NVDA.
* Support de VIP Mud. (#1728)
* Dans Adobe Reader, si un tableau a un résumé, il est maintenant présenté. (#2465)
* Dans Adobe Reader, les titres de lignes et de collones des tableaux peuvent maintenant être annoncés. (#2193, #2527, #2528)
* Nouvelles langues : Éthiopien, Coréen, Népalais, Slovénien.
* NVDA peut maintenant lire les suggestions de l'autocomplétion lorsqu'on saisi des adresses e-mail dans Microsoft Outlook 2007. (#689)
* Deux nouvelles variantes de voix Espeak : Gene, Gene2. (#2512)
* Dans Adobe Reader, les numéros de pages peuvent maintenant être rapportés. (#2534)
 * Dans Reader 11, les étiquettes de pages sont maintenant raportées si présentes, reflétant les changements de numéro de page dans différentes sections, etc. Dans les versions inférieures, ce n'est pas possible et seulement les numéros de pages séquentiels sont rapportés.
* Il est maintenant possible de réinitialiser la configuration de NVDA à celle par défaut en appuyant trois fois sur NVDA+Ctrl+r, ou en choisissant Réinitialiser la configuration aux paramètres par défaut dans le menu de NVDA. (#2086)
* Support des afficheurs braille Seika Version 3, 4 et 5 et Seika80 de Nippon Telesoft. (#2452)
* les premiers et derniers curseurs routines des afficheurs braille Pacmate et Focus de Freedom Scientific peuvent maintenant être utilisés pour défiler vers l'avant ou vers l'arrière. (#2556)
* Plus de possibilités sont supportées pour les afficheurs brailles Focus de Freedom Scientific comme les bares pour avancer, les bares de basculement et certaines combinaisons de points pour des actions communes. (#2516)
* Dans les applications utilisant IAccessible2 comme les applications Mozilla, les titres de lignes et collones des tableaux peuvent être rapportés même en n'étant pas en mode navigation. (#926)
* Support préliminaire des contrôles de documents de Microsoft Word 2013. (#2543)
* L'alignement du texte peut maintenant être rapporté dans les applications utilisant IAccessible2 comme les applications Mozilla. (#2612)
* Lorsqu'une ligne de tableau ou un élément d'une liste multi-colonnes standard Windows a le focus, il est possible d'utiliser les commande de navigation de tableau pour passer de cellule en cellule. (#828)
* Nouvelles tables Brailles : Estonien Grade 0, Portugais Braille informatique 8 points, et Braille informatique Italien six points. (#2139, #2662)
* Si NVDA est installé, ouvrir un paquet de module complémentaire NVDA (par exemple depuis l'explorateur ou après l'avoir téléchargé) proposera l'installation de celui-ci. (#2306)
* Support des modèles plus récents de plages Braille Papenmeier BRAILLEX. (#1265)
* L'information de position (Ex : 1 sur 4) est maintenant rapportée dans les éléments des listes de l'explorateur Windows dans Windows 7 et supérieur. Cela inclut également les éléments UIAutomation qui supportent les propriétés itemIndex et et itemCount. (#2643)

### Changements

* Dans le dialogue de préférences du curseur de revue de NVDA, l'option suivre le focus clavier a été renommée en Suivre le focus système, en conformité avec les terminologies utilisées ailleurs dans NVDA.
* Quand le braille suit la revue et que le curseur est dans un objet qui n'est pas un objet texte (P.EX. une zone d'édition), les touches routines activent maintenant l'objet. (#2386)
* L'option Sauvegarder la configuration en quittant est activée par défaut pour les nouvelles configurations.
* Lorsque l'on met à jours une copie installée de NVDA, le raccourci clavier du bureau n'est plus remis à contrôle+alt+n s'il a été changé manuellement par l'utilisateur. (#2572)
* La liste des modules complémentaires dans le gestionnaire de modules complémentaires affiche le nom du paquet avant son état. (#2548)
* Lorsqu'on installe la même version ou une autre d'un module complémentaire actuellement installé, NVDA proposera de mettre à jour le module complémentaire plutôt qu'afficher un message d'erreur et abandonner. (#2501)
* Les commandes de navigation par objets (excepté la commande rapporter l'objet courant) rapportent maintenant moins d'informations. Vous pouvez toujours obtenir les autres informations en utilisant la commande Rapporter l'objet courant. (#2560)
* Mise à jour de liblouis vers la version 2.5.1. (#2319, #2480, #2662, #2672)
* Le document Références Rapides des touches de Raccourcis a été renommé en résumé des touches de commandes puisqu'il inclut maintenant les commandes tactiles et les commandes clavier.
* La liste d'éléments en mode Navigation se souviendra maintenant du type d'élément à afficher (Par exemple : les liens, les titres ou les repères) chaque fois que ce dialogue est appelé dans la même session de NVDA. (#365)
* La plupart des applications en interface Windows 8 (Par exemple : Mail, Calendrier) n'activent plus le mode navigation pour toute l'application.
* Le serveur-COM pour les afficheurs Braille Handy Tech est mis à jours vers la version 1.4.2.0.

### Corrections de Bogues

* Sous Windows Vista et supérieur, NVDA ne traite plus la touche Windows comme étant gardée appuyée lors du déverrouillage après l'avoir verrouillé en appuyant Windows+L. (#1856)
* Dans Adobe Reader, les titres de colonnes sont maintenant bien reconnus comme des cellules ; P.Ex. les coordonnées sont annoncées et sont accessibles avec les touches de navigation pour les tableaux. (#2444)
* Dans Adobe Reader, les cellules sur plusieurs colonnes sont correctement traitées. (#2437, #2438, #2450)
* Le package de NVDA distribué vérifie maintenant son intégrité avant de s'exécuter. (#2475)
* Les fichiers temporaires de téléchargement sont maintenant supprimés si le téléchargement d'une mise à jour de NVDA échoue. (#2477)
* Lorsque l'on copie la configuration utilisateur dans la configuration système (pour l'utiliser dans l'écran d'identification à Windows et les autres écrans sécurisés de Windows) NVDA ne se figera plus sous XP pendant la procédure où il s'exécute en tant qu'administrateur. (#2485)
* Les tuiles dans l'écran de démarrage Windows 8 sont maintenant mieux présentées vocalement et en braille. Le nom n'est plus répété, non sélectionné n'est plus rapporté sur toutes les tuiles, et l'information de statut en temps réel est présenté comme la description de la tuile (P.Ex. la température actuelle pour la météo).
* Les mot de passes ne sont plus annoncés lorsqu'on lie un champ de mot de passe dans Microsoft Outlook et d'autres champs d'édition standards marqués comme protégés. (#2021)
* Dans Adobe Reader, les changement dans les champs de formulaires sont correctement rendus en mode navigation. (#2529)
* Amélioration du support pour le correcteur orthographique de Microsoft Word, incluant une lecture plus précise de l'erreur d'orthographe actuelle, et la possibilité de supporter le correcteur orthographique lorsqu'on exécute une version installée de NVDA sous Windows Vista ou supérieur.
* Les modules complémentaires qui incluent des fichiers contenant des caractères non anglais peuvent être installés correctement dans la majorité des cas. (#2505)
* Dans Adobe Reader, la langue du texte n'est plus perdue lorsqu'il est mis à jour ou qu'on le fait défilé. (#2544)
* Lors de l'installation d'un module complémentaire, le dialogue de confirmation affiche le nom traduit du module complémentaire si disponible. (#2422)
* Dans les applications utilisant UI Automation (comme les applications .net et Silverlight), le calcul de valeurs numériques pour des composants comme les sliders a été corrigé. (#2417)
* La configuration du rapport des barres de progression est maintenant prise en compte pour les barres de progression non déterminables affichées par NVDA lors de l'installation, de la création d'une version portable etc. (#2574)
* Les commandes de NVDA ne peuvent plus être exécutées depuis un afficheur Braille tant qu'un écran sécurisé de Windows (comme l'écran de verrouillage de l'ordinateur) est actif. (#2449)
* En mode navigation, le braille est mis à jour si le texte affiché change. (#2074)
* Lorsque l'on est dans un écran sécurisé tel que la fenêtre d'ordinateur verrouillé, les messages des applications annonçant ou affichant du braille directement via NVDA sont maintenant ignorés.
* En mode navigation, il est maintenant impossible de passer le bas du document avec la flèche droite en étant sur le dernier caractère, ou en sautant à la fin d'un conteneur quand celui-ci est le dernier élément du document. (#2463)
* Les contenus extérieurs ne sont plus incorrectement inclus lors du rapport du texte des dialogues dans les applications web (spécifiquement, les dialogues ARIA sans attribut aria-describedby). (#2390)
* NVDA ne rapporte ou ne situe plus incorrectement certains champs d'édition dans les documents MSHTML (Ex : Internet Explorer), spécifiquement où un rôle ARIA explicite a été défini par l'auteur de la page web. (#2435)
* La touche Retour-arrière est maintenant correctement traitée lors de l'annonce des mots tapés dans les invites de commandes. (#2586)
* Les coordonnées de cellules dans Microsoft Excel sont maintenant affichées en Braille.
* Dans Microsoft Word, NVDA ne vous laisse plus bloqué dans un paragraphe avec liste formatée lorsque vous essayez de naviguer autour d'une puce ou d'un nombre avec la flèche gauche ou ctrl+flèche gauche. (#2402)
* En mode navigation dans les applications Mozilla, les éléments de certaines zones de listes (spécifiquement, les zones de listes ARIA) ne sont plus mal affichés.
* En mode navigation dans les applications Mozilla, certains éléments affichés avec un nom incorrect ou juste un espaces blancs sont maintenant affichés avec le bon nom.
* En mode navigation dans les applications Mozilla, certains espaces blancs superflus ont été éliminés.
* En mode navigation dans les navigateurs Internet, certains graphiques étant marqués explicitement comme étant pour la présentation (spécifiquement, avec un attribut alt="") sont maintenant ignorés.
* Dans les navigateurs Internet, NVDA cache maintenant le contenu marqué comme caché des lecteurs d'écran (spécifiquement, l'utilisation de l'attribut aria-hidden). (#2117)
* Les valeurs monétaires négatives (ex : -$123) sont correctement annoncées comme négatives, quelque soit le niveau du symbole. (#2625)
* Pendant dire tout, NVDA ne restorera pas le langage par défaut de manière inappropriée quand la ligne n'est pas une fin de phrase. (#2630)
* Les informations de mise en forme sont correctement détectées dans Adobe Reader 10.1 et plus récent. (#2175)
* Dans Adobe Reader, si un texte alternatif est fourni, seulement ce texte sera rendu. Précédamment, du texte en trop était lu. (#2174)
* Lorsqu'un document contient une application, le contenu de l'application n'est plus inclus dans le mode navigation. Cela permet d'éviter de se déplacer dans l'application de manière inattendue. On peut se déplacer dans l'application de la même manière que pour un objet embarqué. (#990)
* Dans les applications Mozilla, les valeurs des boutons rotatifs sont correctement rapportées lorsqu'elles changent. (#2653)
* Mise à jour du support d'Adobe Digital Editions pour qu'il fonctionne avec la version 2.0. (#2688)
* Appuyer sur NVDA+FlècheHaute lorsqu'on est dans une zone de liste dans Internet explorer et autres documents MSHTML ne lira plus tous les éléments. Seul l'élément actif sera lu. (#2337)
* Les dictionnaires de paroles se sauvegarderont bien quand on utilise un dièse (#) dans le champ Mot réel et Remplacement. (#961)
* Le mode navigation dans les documents MSHTML (ex : Internet Explorer) affiche maintenant le contenu visible contenu dans du contenu invisible. Spécifiquement : les éléments ayant un style visibility:visible contenu dans un élément avec le style visibility:hidden. (#2097)
* Les liens du centre de sécurité de Windows XP ne rapportent plus de texte superflu après leur nom. (#1331)
* Les champs de texte UI Automation (Ex : la zone de recherche du menu démarrer de Windows 7) sont dèsormais correctement annoncés lorsqu'on déplace la souris autour au lieu de ne rien dire.
* Les changements de disposition de clavier ne sont plus annoncés pendant dire tout, ce qui était particulièrement problématique dans les documents multi-lingues incluant du texte en Arabe. (#1676)
* Le contenu entier de certains champs de texte UI Automation (ex : le champ de recherche dans le menu démarrer de Windows 7/8) n'est plus annoncé à chaque changement.
* Lorsqu'on navigue entre les groupes dans l'écran d'accueil de Windows 8, un groupe sans étiquette n'annoncera plus la première tuile comme le nom du groupe. (#2658)
* Lorsqu'on ouvre l'écran d'accueil de Windows 8, le focus est correctement placé sur le premier élément, au lieu de sauter au début de l'écran ce qui peut causer des confusions dans la navigation. (#2720)
* NVDA ne plantera plus au démarrage lorsque le répertoire du profil de l'utilisateur contient des caractères multibyte. (#2729)
* En mode navigation dans Google Chrome, le texte des onglets est maintenant correctement affiché.
* En mode navigation, les boutons de menu sont maintenant rapportés correctement.
* Dans OpenOffice.org/LibreOffice Calc, la lecture des cellules des tableaux fonctionne correctement. (#2765)
* NVDA peut à nouveau fonctionner dans la liste des messages de Yahoo! Mail avec Internet Explorer. (#2780)

### Changements pour les développeurs

* Le fichier journal précédent est maintenant renommé en nvda-old.log à l'initialisation de NVDA. Par conséquent, si NVDA plante ou est redémarré, les informations journalisées de cette session sont toujours accessibles pour inspection. (#916)
* Accéder à la propriété role dans chooseNVDAObjectOverlayClasses ne la rend plus incorrecte et pas rapporté lors du focus pour certains objets tel que les fenêtres d'invites de commandes et les contrôles Scintilla. (#2569)
* Les menus Préférences, Outils et Aide de NVDA sont maintenant accessibles comme des attributs de gui.mainFrame.sysTrayIcon només respectivement preferencesMenu, toolsMenu et helpMenu. Cela permet aux plugins de pouvoir plus facilement ajouter des éléments à ces menus.
* Le script navigatorObject_doDefaultAction dans globalCommands a été renommé en review_activate.
* Les messages de contexte Gettext sont maintenant supportés. Cela permet de pouvoir définir plusieurs traductions pour un message en Anglais selon le contecte. (#1524)
 * Cela se fait en utilisant la fonction pgettext(context, message).
 * Ceci est supporté aussi bien pour NVDA que pour les modules complémentaires.
 * xgettext et msgfmt de GNU Gettext doivent être utiliser pour créer tout fichier po ou mo. Les outils Python ne supportent pas les messages de contextes.
 * Pour xgettext, passez le paramètre de ligne de commande --keyword=pgettext:1c,2 pour activer l'inclusion des messages de contextes.
 * Visitez https://www.gnu.org/software/gettext/manual/html_node/Contexts.html#Contexts pour plus d'informations.
* Il est maintenant possible d'accéder aux modules intégrés de NVDA afin d'en étendre les fonctionnalités. Reportez-vous au module nvdaBuiltin pour plus de détails.
* Le support de traduction dans les Modules complémentaires est maintenant supporté dans le module installTask du module complémentaire. (#2715)

## 2012.2.1

Cette version comble des failles de sécuritée (en mettant à jour vers Python 2.7.3)

## 2012.2

Les apports majeurs de cette version incluent un installateur et créateur de version portable intégré, des mises à jours automatiques, une gestion facile des nouveaux modules complémentaires NVDA, l'annonce des graphique dans Microsoft Word, le support des application Metro Windows 8, et des corrections de bogues importants.

### Nouvelles Fonctionnalités

* NVDA peut maintenant rechercher, télécharger et installer automatiquement les mises à jour. (#73)
* Étendre les fonctionnalités de NVDA a été facilité par l'ajout d'un gestionnaire de Modules Complémentaires (accessible depuis le menu Outils du menu NVDA) vous permettant d'installer ou de désinstaller des paquets de Modules Complémentaires (fichiers .nvda-addon) contenant des plugins et des drivers. Notez bien que le gestionnaire de Modules Complémentaires n'affiche pas les anciens plugins ou pilotes copiés manuellement dans votre répertoire de configuration. (#213)
* Beaucoup plus de fonctionnalités de NVDA sont maintenant utilisables dans les applications en style Metro sous Windows 8 lorsqu'on utilise une copie installée de NVDA, incluant la prononciation des caractères saisis, et le mode navigation pour les documents web (incluant le support pour la version metro de Internet Explorer 10). Les copies portables de NVDA ne peuvent accéder aux applications Metro. (#1801)
* En mode navigation (Internet Explorer, Firefox etc.) il est maintenant possible de sauter au début et de passer la fin de certains éléments contenants (incluant les listes et les tableaux) avec maj+, et , respectivement. (#123)
* Nouvelle langue : grecque.
* Les graphiques et le texte alternatif sont maintenant lus dans les documents Microsoft Word. (#2282, #1541)

### Changements

* L'annonce des coordonnées des cellules dans Microsoft Excel est maintenant après le contenu plutôt qu'avant, et est maintenant seulement incluse si les options Annoncer les tableaux et Annoncer les coordonnées des cellules dans un tableau sont activées dans les options de mise en forme des documents.
* NVDA est maintenant distribué en un seul package. Plutôt qu'une version portable et une version installée, il n'y a maintenant qu'un fichier qui lorsqu'il démarre, lancera une copie temporaire de NVDA qui vous permettra d'installer ou de créer une copie portable. (#1715)
* NVDA est maintenant toujours installé dans Program Files sur tous les systèmes. Mettre à jours une installation la déplacera automatiquement si elle n'y était pas installée.

### Corrections de Bogues

* Avec le changement automatique de la langue activé, le Contenu tel que le texte alternatif pour les graphiques et les étiquettes pour certains champs dans Mozilla Gecko (P.ex. Firefox) sont maintenant prononcé dans la langue correcte si marquée de manière appropriée.
* Dire Tout dans BibleSeeker (et autre contrôles TRxRichEdit) ne s'arrête plus au milieu d'un passage.
* Les listes que l'on trouve dans les propriétés de fichiers de l'explorateur de Windows 8 (onglet permissions) et dans Windows Update sous Windows 8 sont maintenant lues correctement.
* Correction de blocages possibles dans MS Word qui causaient un délai de plus de deux secondes pour récupérer le texte d'un document (lignes extrêmement longues ou table des matières). (#2191)
* La détection de séparation de mots fonctionne maintenant correctement quand l'espace est suivi de certaines ponctuations. (#1656)
* En mode Navigation dans Adobe Reader, il est maintenant possible de naviguer dans les différents niveaux de titres en utilisant les touches de navigation rapide et la liste. (#2181)
* Dans Winamp, le braille est maintenant correctement mis à jour quand on change d'élément dans l'éditeur de playliste. (#1912)
* L'arborescence dans la liste des éléments (disponibles pour les documents en mode navigation) est maintenant correctement dimentionné pour afficher le texte de tous les éléments. (#2276)
* Dans les applications utilisant Java Access Bridge, les champs de texte éditables sont maintenant correctement présentés en braille. (#2284)
* Dans les applications utilisant java Access Bridge, les champs de textes éditables ne rapporte plus de caractères étranges dans certaines circonstences. (#1892)
* Dans les applications utilisant Java Access Bridge, à la fin d'un champ de texte éditable, la ligne courante est maintenant lue correctement. (#1892)
* En mode Navigation dans les applications utilisant Mozilla Gecko 14 et supérieur (e.g. Firefox 14), la navigation rapide fonctionne maintenant dans les bloques de citation et les objets inclus. (#2287)
* Dans Internet Explorer 9, NVDA ne lit plus de contenu non désiré quand le focus est dans certains repaires ou éléments activables (plus précisément, un élément div pouvant avoir le focus ou ayant un rôle de repaire ARIA).
* L'icône de NVDA pour les raccourcis du bureau et du menu démarrer est correctement affichée dans les éditions 64 bit de Windows. (#354)

### Changements pour les développeurs

* En raison du remplacement de l'installateur NSIS pour NVDA par un installateur en Python, il n'est plus nécessaire pour les traducteurs de maintenir un fichier langstrings.txt pour l'installateur. Toutes ces chaînes traduites sont maintenant gérées par les fichiers po gettext.

## 2012.1

Les apports majeurs de cette version incluent des fonctionnalités pour une lecture plus fluide du Braille; des indications de mise en forme des documents en Braille; l'accès à beaucoup plus d'informations de mise en forme ainsi qu'une amélioration de performances sous Microsoft Word et le support du magasin Itune.

### Nouvelles Fonctionnalités

* NVDA peut annoncer le nombre de tabulations et d'espaces en début de ligne dans l'ordre où ils apparaissent.
* NVDA peut maintenant détecter les appuis de touches venant de claviers alternatifs tels que les claviers à l'écran et les reconnaissances vocales.
* NVDA peut maintenant détecter les couleurs dans les consoles de commande Windows.
* Les caractères gras, italiques et soulignés sont maintenant signalés en braille en utilisant les signes définis dans la table braille en cours. (#538)
* Dans les documents Microsoft Word, beaucoup plus d'informations sont maintenant annoncées, parmi lesquelles :
 * Les informations en ligne comme les numéros de notes en bas de page et de notes en fin de document, niveaux de titres, l'existence de commentaires, les niveaux d'imbrication des tables, les liens, la couleur du texte;
 * annonce, quand on entre dans les paragraphes tels que l'historique des commentaires, l'historique des notes de bas de page et des notes de fin de document et l'historique des en-têtes et pieds de page;
* Le braille indique maintenant le texte sélectionné en utilisant les points 7 et 8. (#889)
* Dans les documents, les contrôles tels que lien, bouton titre sont maintenant affichées en Braille. (#202)
* Prise en compte des terminaux braille USB hedo ProfiLine et MobilLine. (#1863, #1897)
* Par défaut, NVDA essaie maintenant de ne pas couper les mots en Braille quand c'est possible. Ceci peut être désactivé dans le dialogue "Paramètres Braille". (#819) (#946)
* Il est maintenant possible d'afficher le Braille par paragraphe plutôt que par ligne, ce qui peut permettre une lecture plus fluide de grandes portions de texte. Ceci peut être configuré en utilisant l'option "Lire par paragraphe" du dialogue "Paramètres Braille". (#1891)
* En mode navigation, on peut activer l'objet sous le curseur à partir du terminal braille. Cela se fait en appuyant sur le curseur routine correspondant à la position du curseur. Si le curseur n'est pas encore à la position souhaitée, il faut presser deux fois la touche. (#1893)
* Support de base des zones web telles que le magasin dans Itune.
* Dans les livres sous Adobe Digital Editions 1.8.1 et au-delà, les pages sont maintenant tournées automatiquement en mode dire tout.
* Nouvelle table de conversion braille : Portugais grade 2, Islandais informatique 8 points, Tamoul grade 1, Espagnol informatique 8 points, Farsi grade 1. (#2014)
* L'annonce des cadres dans les documents peut maintenant être configurée dans le dialogue de mise en forme des documents. (#1900)
* Le mode veille est automatiquement activé quand on utilise Openbook. (#1209)
* Sous Poedit, les traducteurs peuvent maintenant lire les commentaires ajoutés par les traducteurs ou extraits automatiquement. Les messages non traduits ou confus sont marqués par une étoile et on entend un bip quand on passe dessus. (#1811)
* Support des terminaux braille HumanWare Brailliant Bi & B. (#1990)
* Nouvelle langue: Norvégienne Bokmål.

### Changements

* Les commandes permettant de décrire le caractère courant ou d'épeler le mot ou la ligne en cours épellent maintenant dans la langue appropriée au texte si le changement automatique de langue est activé et si les informations relatives à la langue sont disponibles.
* Mise à jour du synthétiseur eSpeak à la version 1.46.02.
* NVDA tronque maintenant les noms très longs (plus de 30 caractères) devinés dans les graphiques et les liens URLs car ils nuisent souvent à la lecture. (#1989)
* Certaines informations affichées en Braille ont été abrégées. (#1955)
* Quand le curseur de revue ou le curseur système se déplacent, le braille défile maintenant de la même manière que par le défilement manuel. Ceci est plus cohérent quand le Braille est configuré pour une lecture par paragraphe ou pour éviter la coupure de mots. (#1996)
* Mise à jour de la table Espagnole Grade 1.
* Mise à jour du convertisseur braille liblouis à la version 2.4.1.

### Corrections de Bogues

* Sous Windows 8, le focus n'est plus retiré intempestivement de la zone de recherche de l'explorateur ce qui empêchait NVDA d'interagir avec elle.
* importantes améliorations de performances durant la lecture d'un document Microsoft Word quand l'annonce automatique des changements de format du document est activée ce qui rend plus confortable la vérification du format d'un texte. Les performances générales peuvent aussi être améliorées pour certains utilisateurs.
* Le mode navigation est maintenant utilisé pour les contenus Adobe Flash.
* Correction de la qualité audio parfois pauvre quand on utilise Microsoft Speech API version5 avec la sortie audio réglée sur autre chose que le mappeur Microsoft utilisé par défaut. (#749)
* NVDA peut de nouveau être utilisé avec le synthétiseur "pas de parole", en s'appuyant uniquement sur le Braille ou la visionneuse de parole.
* Les commandes de navigation par objet n'annoncent plus "pas d'enfant" ou "pas de parent" mais un texte correspondant à la documentation.
* Quand NVDA est configuré dans une langue autre que l'anglais, le nom de la touche de tabulation est maintenant annoncé dans la langue appropriée.
* Sous Mozilla Gecko (ex : Firefox), NVDA ne passe plus en mode navigation de manière intermittente quand on parcourt les menus dans un document. (#2025)
* Dans la calculatrice, la touche Retour-arrière annonce maintenant le résultat au lieu de ne rien annoncer. (#2030)
* En mode navigation, la commande de déplacement de la souris vers l'objet de navigation courant amène au centre de l'objet sous le curseur de revue plutôt qu'en haut à gauche ce qui améliore le fonctionnement dans certains cas. (#2029)
* En mode navigation, quand le passage automatique en mode formulaire au changement de focus est activé, la mise en focus d'une barre d'outils activera maintenant le mode formulaire. (#1339)
* La commande d'annonce du titre fonctionne à nouveau correctement sous Adobe Reader.
* Quand le passage automatique en mode formulaire au changement de focus est activé, le mode formulaire est activé pour les cellules de tableau en focus (ex : grilles arias). (#1763)
* Sous Itune, l'information de position est maintenant annoncée correctement dans certaines listes.
* Sous Adobe Reader, certains liens ne sont plus traités comme des zones d'édition non modifiables.
* l'étiquette de certaines zones d'édition n'est plus incluse de manière incorrecte à l'annonce du texte d'un dialogue. (#1960)
* La description des groupages est de nouveau annoncée si l'annonce de la description des objets est activée.
* la taille en format lisible est maintenant incluse dans le texte du dialogue de propriété des disques de l'explorateur Windows.
* La double annonce du texte des pages de propriété a été supprimée dans certains cas. (#218)
* Amélioration du suivi du curseur dans les zones d'édition s'appuyant sur du texte écrit à l'écran. En particulier, cela améliore l'utilisation de l'éditeur de cellules dans Microsoft Excel et dans l'éditeur de messages d'Eudora. (#1658)
* Sous Firefox 11, la commande NVDA+Contrôle+Espace (aller à l'objet virtuel contenant) fonctionne maintenant comme prévu pour quitter un objet embarqué tel qu'un objet Flash.
* NVDA se relance maintenant correctement après un changement de configuration quand il est installé dans un répertoire dont le nom comporte des caractères non Ascii. (#2079)
* Le Braille respecte correctement les réglages pour l'affichage des touches de raccourci des objets, de l'information de rang et des descriptions.
* Dans les applications Mozilla, le passage entre le mode formulaire et le mode navigation n'est plus ralenti quand le Braille est activé.
* Amener le curseur sur l'espace situé à la fin d'un paragraphe en utilisant les routines curseur Braille ne ramène plus au début du texte. (#2096)
* NVDA fonctionne de nouveau correctement avec le synthétiseur Audiologic Tts3. (#2109)
* Les documents Microsoft Word sont correctement traités comme multilignes. Cela permet un comportement plus approprié du Braille quand le document est en focus.
* Sous Microsoft Internet Explorer, il n'y a plus d'erreur quand le focus se trouve sur certains contrôles rares (#2121)
* Le changement de nom d'une ponctuation ou d'un symbole prendra effet instantanément sans nécessiter un redémarrage de NVDA.
* Lorsque l'on utilise eSpeak, La parole ne se met plus en mode silence dans certains cas dans le dialogue Enregistrer Sous de la visionneuse du journal. (#2145)

### Changements pour les Développeurs

* Il y a maintenant une console Python à distance pour les situations ou le débogage à distance est utile. Consultez le guide de développement pour les détails.
* Le chemin de base du code NVDA est maintenant supprimé dans le log pour améliorer la lisibilité. (#1880)
* Les objets Textinfo ont maintenant une méthode activate() pour activer la position représentée par le Textinfo.
 * Ceci est utilisé par le Braille pour activer la position en utilisant les curseur routines sur les afficheurs braille. Cependant, il pourrait y avoir d'autres utilisations dans le futur.
* TreeInterceptors et NVDAObjects qui n'exposent qu'une page de texte à la fois peuvent prendre en compte le défilement automatique des pages en mode "dire tout" en utilisant le mix-in textInfos.DocumentWithPageTurns. (#1978)
* Plusieurs contrôles et valeurs de constantes ont été renommés ou déplacés. (#228)
 * Les constantes speech.REASON_* ont été déplacées dans controlTypes.
 * Dans controlTypes, speechRoleLabels et speechStateLabels ont été renommées respectivement en roleLabels et stateLabels.
* L'affichage Braille est maintenant journalisé au niveau entrée/sortie. D'abord, le texte non converti de toutes les régions est journalisé suivi par les cellules braille de la fenêtre en cours d'affichage. (#2102)
* Les sous-classes de sapi5 synthDriver peuvent désormais remplacer _getVoiceTokens et étendre init pour prendre en charge les jetons vocaux personnalisés, comme avec sapi.spObjectTokenCategory pour obtenir des jetons à partir d'un emplacement de registre personnalisé.

## 2011.3

Les apports majeurs de cette version incluent le changement automatique de langue pendant la lecture de documents contenant les informations de langue appropriées; le support des environnements Java 64 bits; l'annonce des informations de formatage du texte en mode navigation dans les applications Mozilla; une meilleure prise en compte des plantages ou blocage d'applications; et les premières adaptations pour Windows 8.

### Nouvelles fonctionnalités

* NVDA peut maintenant changer la langue du synthétiseur eSpeak à la volée quand on lit des documents web/pdf contenant les informations de langue appropriées. Le changement automatique de langue ou de dialecte peut être activé ou désactivé dans le dialogue Paramètres Vocaux. (#845)
* Java Access Bridge 2.0.2 est maintenant supporté ce qui inclut les environnements Java Runtime 64 bits.
* Sous Mozilla Gecko (ex : Firefox) Les niveaux de titre sont maintenant annoncés quand on utilise la navigation par objet.
* Le formatage du texte peut maintenant être annoncé quand on utilise le mode navigation sous Mozilla Gecko (ex : Firefox et ThunderBird). (#394)
* Les textes soulignés et/ou biffés peuvent maintenant être détectés et annoncés dans les contrôles de texte IAccessible2 standards tels qu'on en trouve dans les applications Mozilla.
* En mode navigation sous Adobe Reader, le nombre de ligne et de colonnes d'un tableau est maintenant annoncé.
* Le synthétiseur Microsoft Speech Platform est maintenant supporté. (#1735)
* Les numéros de ligne et de colonne sont maintenant annoncés pour le curseur sous IBM Lotus Symphony. (#1632)
* Le pourcentage de changement de hauteur de voix quand une lettre majuscule est prononcée est maintenant configurable dans le dialogue Paramètres vocaux. Cela remplace l'ancienne case à cocher "Augmenter la hauteur de la voix pour signaler les majuscules". Pour désactiver cette fonction, mettez le pourcentage à 0. (#255)
* L'annonce de la couleur du texte et de l'arrière-plan est maintenant inclus dans l'annonce du formatage du texte des cellules sous Microsoft Excel. (#1655)
* Dans les applications utilisant Java Access Bridge, la commande d'activation de l'objet de navigation courant fonctionne maintenant pour les contrôles qui le nécessitent. (#1744)
* Nouvelle langue : Tamoul.
* Prise en charge de base de MathPlayer de Design Science.

### Changements

* NVDA redémarre maintenant automatiquement en cas de plantage.
* Quelques informations affichées en Braille ont été abrégées. (#1288)
* Le script de lecture de la fenêtre active (NVDA+B) a été amélioré pour filtrer les contrôles inutiles et est maintenant beaucoup plus facile à interrompre. (#1499)
* La lecture automatique au chargement d'un document navigable est maintenant optionnelle via un paramètre dans le dialogue Mode Navigation. (#1414)
* Quand on essaie de lire la barre d'état (NVDA+fin en configuration clavier ordinateur de bureau), NVDA lira la dernière ligne de texte à l'écran s'il ne peut trouver de vraie barre d'état. (#649)
* Dans les documents navigables, pendant la lecture avec la commande dire tout, NVDA marquera maintenant une pause après les titres et les autres marques de blocs au lieu de lire tout le texte comme une seule longue phrase.
* En mode navigation, l'appui sur entrée ou espace quand on se trouve sur un onglet active celui-ci plutôt que de passer en mode formulaire. (#1760)
* Mise à jour du synthétiseur eSpeak à la version 1.45.46.

### Corrections de bogues

* NVDA ne montre plus les puces ou les numérotations dans les listes sous Internet Explorer et autres contrôles MSHTML quand l'auteur a spécifié que celles-ci ne doivent pas être montrées (ex : style de liste "none"). (#1671)
* Le redémarrage de NVDA après blocage (ex : en pressant contrôle+alt+n) n'arrête plus la copie en cours sans en démarrer une nouvelle.
* Dans la console de commandes Windows, l'appui sur retour-arrière ou les flèches ne provoque plus de résultats bizarres dans certains cas. (#1612)
* L'élément sélectionné dans les listes déroulantes WPF (et possiblement d'autres listes déroulantes présentées par UI Automation) qui n'autorisent pas l'édition de texte est maintenant annoncé correctement.
* En mode navigation sous adobe Reader, il est maintenant toujours possible d'aller de la ligne de titre à la ligne suivante et vice-versa en utilisant les commandes de déplacement à la ligne suivante et de déplacement à la ligne précédente. En outre, la ligne de titre n'est plus annoncée comme ligne 0.
* En mode navigation sous Adobe Reader, il est maintenant possible d'entrer et des ressortir des cellules vides d'un tableau.
* Les informations de position sans signification (ex : 0 sur 0 niveau 0) ne sont plus affichées en Braille.
* Quand le Braille suit le curseur de revue, il peut maintenant afficher le contenu en revue à plat. (#1711)
* Le texte d'un contrôle texte n'est plus affiché deux fois sur le terminal braille dans certains cas (ex : défilement arrière depuis le début d'un document Wordpad).
* En mode navigation sous Internet Explorer, l'appui sur la touche Entrer sur un bouton de téléchargement de fichier affiche maintenant correctement le dialogue permettant de choisir le fichier à envoyer au lieu de passer en mode formulaire. (#1720)
* Le changement dynamique de contenu, par exemple dans les consoles DOS, ne sont plus annoncés si le mode veille est activé pour l'application en cours. (#1662)
* En mode navigation, le comportement de alt+flèchehaute et alt+flèchebasse pour réduire et développer les listes déroulantes a été amélioré.
* NVDA s'accommode maintenant de beaucoup plus de situations telles que des applications cessant de répondre et qui le gelaient complètement. (#1408)
* Dans les documents navigables sous Mozilla Gecko (Firefox etc), NVDA n'échoue plus à présenter le texte dans le cas très spécial où un élément est stylé comme display:table. (#1373)
* NVDA n'annonce plus les contrôles d'étiquette quand le focus entre dans l'une d'entre elles. Cela supprime la double annonce de l'étiquette pour certains champs de formulaire sous Firefox (Gecko) et Internet Explorer (MSHTML). (#1650)
* NVDA réussit maintenant à lire le contenu d'une cellule Microsoft Excel après qu'on y ait collé du contenu par Ctrl+v. (#781)
* Sous Adobe Reader, des informations irrelevantes concernant le document ne sont plus annoncées quand on se déplace à un contrôle sur une autre page en mode formulaire. (#1659)
* En mode navigation dans les applications Mozilla Gecko telles que Firefox, les boutons à deux états sont maintenant correctement détectés et annoncés. (#1757)
* NVDA peut maintenant lire correctement la barre d'adresse de l'explorateur Windows dans la préversion pour développeur de Windows 8.
* NVDA ne plante plus certaines applications telles que Winver et Wordpad de la préversion pour développeur de Windows 8 en raison d'une mauvaise traduction de certains glyphes.
* En mode navigation dans les applications utilisant Mozilla Gecko 10 ou au-delà (comme Firefox 10), le curseur se positionne plus souvent correctement quand on charge une page avec une ancre cible. (#360)
* En mode navigation dans les applications Mozilla Gecko (ex : Firefox), les étiquettes des images sont maintenant présentées.
* Avec le suivi de la souris activé, le passage de la souris sur certains champs d'édition n'entraîne plsu le plantage de l'application.
* NVDA fonctionne maintenant correctement dans plusieurs dialogues "à propos" dans les applications distribuées avec Windows XP, parmi lesquelles le dialogues "à propos" du bloc-notes. (#1855) et celui de Windows.
* Correction de la revue par mots dans les champs d'édition de Windows. (#1877)
* quitter un champ d'édition avec flèche-haut, flèche-gauche ou page-précédente quand on est en mode formulaire passe maintenant automatiquement en mode navigation quand le mode formulaire automatiquement au déplacement du curseur est activé. (#1733)

### Changements pour les Développeurs

* NVDA peut maintenant dire aux synthétiseurs de changer de langue pour certaines portions de texte.
 * Pour permettre cela, les pilotes doivent supporter speech.LangChangeCommand dans les séquences passées à SynthDriver.speak().
 * SynthDriver objects doit aussi fournir l'argument de langue aux objets VoiceInfo (ou remplacer l'attribut langue pour récupérer la langue courante). Sinon, la langue de l'interface utilisateur de NVDA sera utilisée.

## 2011.2

Les apports majeurs de cette version incluent des améliorations notables concernant la ponctuation et les symboles, y compris leurs niveaux de prononciation désormais configurables, l'étiquetage personnalisé ainsi que la descriptions des caractères; la suppression des pauses à la fin des lignes en cours de lecture avec la commande "Dire tout"; le support amélioré des ARIA dans Internet Explorer ; un meilleur support pour les documents XFA/LiveCycle PDF dans Adobe Reader ; la possibilité d'exploiter le texte écrit à l'écran sous encore plus de logiciels; et enfin, l'accès à l'information de mise en forme et la couleur du texte écrit à l'écran.

### Nouvelles fonctionnalités

* Il est maintenant possible d'entendre la description d'un caractère donné en appuyant deux fois rapidement sur une combinaison de touches, ce qui appelle le script Revue Caractère courant. Pour les caractères en anglais, c'est la norme de l'alphabet phonétique international qui sera utilisée. Pour les langues pictographiques telles que le chinois traditionnel, un exemple composé d'une ou plusieurs phrases utilisant le symbole en question est fourni. De même, l'appui sur les touches servant à appeler le script Revue Mot Courant ou Revue Ligne Courante trois fois épellera le mot/ligne en utilisant la première de ces descriptions. (#55)
* À l'avenir, NVDA verra plus de texte dans le cas d'une représentation plate sous des applications telles que Mozilla Thunderbird. Ces logiciels transmettent leur texte directement à l'écran sous forme de glyphes.
* Il est maintenant possible de choisir entre plusieurs niveaux d'annonce de ponctuation et symboles. (#332)
* Lorsque des ponctuations ou d'autres symboles sont répétés plus de quatre fois, le nombre de leur répétitions est désormais annoncé au lieu de lire les symboles répétitivement. (#43)
* Nouvelles tables Braille: norvégien Braille informatique 8 points, Éthiopien intégral, Slovène intégral, Serbe intégral. (#1456)
* La vocalisation n'observe plus de pauses anormales à la fin de chaque ligne en mode dire tout. (#149)
* NVDA annoncera si quelque chose est réorganisé (selon la propriété Aria-Sort) dans les navigateurs web. (#1500)
* Les caractères Braille unicodes sont maintenant affichés correctement sur les plages tactiles. (#1505)
* Sous Internet Explorer et autres contrôles MSHTML, quand le focus se déplace au sein d'un groupe de contrôles (entouré par un ensemble de champs), NVDA annoncera désormais le nom du groupe, (la légende). (#535)
* Sous Internet Explorer et autres contrôles MSHTML, les propriétés aria-labelledBy et aria-describedBy sont maintenant honnorées.
* Sous Internet Explorer et autres contrôles MSHTML, le ssupport des ARIA tout comme celui des liste, des cellules dans une grille, les barres de défilement et des barre de progression a été améliorée.
* Les utilisateurs peuvent désormais changer la prononciation des ponctuations et des symboles ainsi que le niveau auquel ils sont annoncés. (#271, #1516)
* Sous Microsoft Excel, le nom de la feuille active est maintenant annoncé quand on change de feuille avec contrôle+page précédente ou contrôle+page suivante. (#760)
* Quand on navigue dans un tableau en utilisant la touche tab sous Microsoft Word, NVDA annonce maintenant la cellule courante alors que vous vous déplacez. (#159)
* Vous pouvez maintenant déterminer si les coordonnées des cellules d'un tableau doivent être annoncées dans le dialogue Mise en forme du document, sous le menu Préférences. (#719)
* NVDA est présentement capable de détecter les informations de formatage et la couleur d'un texte écrit à l'écran.
* Dans la liste de messages de Outlook Express / windows Mail / Windows Live Mail, NVDA annonce maintenant si le message est non lu et si le message est réduit ou développé dans le cas des conversations groupées. (#868)
* eSpeak a maintenant un paramètre d'accélération de la parole qui en triple le débit.
* Support de la zone "Calendrier" qui se trouve dans le dialogue d'information Date et Heure qui est atteignable à partir de l'horloge de Windows 7. (#1637)
* Des affectations de touches supplémentaires ont été ajoutées pour l'afficheur Braille MDV Lilli. (#241)
* Nouvelles langues: Albanais, Bulgare.

### Changements

* Pour déplacer le curseur système au curseur de revue, appuyez maintenant sur les touches qui appellent le script Déplace Focus Vers Objet Navigation (Clavier d'ordinateur de bureau NVDA+maj+Moins pavé numérique, Clavier d'ordinateur portable, NVDA+Maj+Retour-arrière) deux fois rapidement. Cela libère plus de touches. (#837)
* Pour entendre la représentation décimale et hexadécimale du caractère sous le curseur de revue, appuyez maintenant sur Revue Caractère Courant trois fois plutôt que deux. Le double-appui vocalise la description du caractère.
* Mise à jour de la synthèse vocale eSpeak vers la version 1.45.03. (#1465)
* Les tableaux de visualisation ne sont plus annoncés dans les applications Mozilla Gecko quand le focus s'y déplace en mode navigation ou en dehors d'un document.
* Sous Internet Explorer et d'autres contrôles MSHTML, le mode navigation fonctionne maintenant dans les applications ARIA. (#1452)
* Mise à jour dutraducteur braille liblouis vers la version 2.3.0.
* Quand le mode navigation est actif et que l'on atteint un contrôle soit par une touche de navigation rapide ou en y déplaçant le focus, le nom du contrôle est annoncé s'il y a lieu.
* Les barres de progression sont désormais signalées en mode navigation.
* Les nœuds marqués avec un rôle ARIA de présentation dans Internet Explorer et autres contrôles MSHTML sont maintenant filtrés du mode revue simple et de l'ascendance du focus.
* L'interface utilisateur de NVDA et la documentation font maintenant référence aux tampons virtuels en tant que mode navigation, le terme "tampons virtuels" n'ayant pas de signification pour la plupart des utilisateurs. (#1509)
* Quand l'utilisateur veut copier ses paramètres utilisateur pour inclusion dans le profil système pour qu'ils soient utilisables sur l'écran d'ouverture de session etc, et que ces paramètres contiennent des plugins personnalisés, il est maintenant averti d'un risque de sécurité potentiel. (#1426)
* Le service NVDA ne procède plus à un démarrage et un arrêt de NVDA sur les bureaux de saisie de l'utilisateur.
* Sous Windows Xp et Windows Vista, NVDA n'utilise plus UI Automation même s'il est disponible à travers la plate-forme de mise à jour système. Bien que l'utilisation de UI Automation améliore l'accessibilité de certaines applications modernes, sous XP et Vista, son utilisation causait trop de blocages, pannes de programes et dégradations de performances. (#1437)
* Dans les applications utilisant Mozilla Gecko 2 et suivants (comme Firefox 4 et suivants), un document peut maintenant être lu en mode navigation avant d'être complètement chargé.
* NVDA annonce maintenant l'état d'un conteneur quand le focus arrive à l'un de ses contrôles (Par exemple, quand le focus arrive sur un document en cours de chargement, il sera annoncé comme occupé).
* L'interface utilisateur de NVDA et la documentation n'utilisent plus les termes "premier enfant" et "parent" en ce qui concerne la navigation par objet, ces termes étant sources de confusions pour beaucoup d'utilisateurs.
* Réduit n'est plus annoncé pour certains menus qui ont des sous-menus.
* Le script reportCurrentFormatting (NVDA+f) annonce maintenant le format du texte à la position du curseur de revue et non plus à celle du curseur système ou focus. Comme, par défaut, le curseur de revue suit le curseur système, la plupart des utilisateurs ne devraient pas s'en apercevoir. Cependant, cela permettra à l'utilisateur de connaître le format du texte quand il se déplace avec le curseur de revue, en particulier en revue à plat.

### Correction de bogues

* La fermeture des zones de liste déroulantes dans un document navigable lorsque le mode formulaire a été forcé avec NVDA+espace ne fais plus repasser automatiquement en mode navigation. (#1386)
* Dans les documents Gecko (Firefox par exemple) et MSHTML (par exemple Internet Explorer), NVDA restitue maintenant correctement le texte se trouvant sur la même ligne au lieu de le présenter sur des lignes séparées. (#1378)
* Lorsque Braille suit revue, quand l'objet de navigation est déplacé vers un document navigable (document web, pdf, ou courriel au format HTML), soit manuellement, soit en raison d'un changement de focus, le curseur Braille indiquera le contenu du document de façon appropriée. (#1406, #1407)
* Lorsque l'annonce des ponctuations est désactivée, certaines ponctuations ne sont plus prononcées, ce qui arrivait parfois avec certaines synthèses vocales. (#332)
* Plus de problèmes lors du chargement de configuration des synthétiseurs de parole qui ne supportent pas les paramètres vocaux tels que Audiologic Tts3. (#1347)
* Le menu Extras de Skype est maintenant lu correctement. (#648)
* Le fait de cocher la case "La brillance modifie le volume des coordonnées audio" qui fait partie du dialogue Paramètres de la souris ne devrait plus causer un retard notable de bips lors du déplacement de la souris en présence de l'affichage de Windows Vista / Windows 7 quand Aero est actif. (#1183)
* Quand NVDA est configuré pour utiliser le clavier Ordinateur Portable, NVDA+supprime fonctionne maintenant comme documenté, annonçant les dimensions correctes de l'objet de navigation courant.
* Maintenant, NVDA honore de manière appropriée l'attribut aria sélectionné dans les documents d'Internet Explorer.
* Quand il passe automatiquement en mode formulaire dans les documents navigables, NVDA annonce désormais les informations de contexte de celui-ci. Par exemple, si un élément de zone de liste reçoit le focus, la zone de liste sera annoncée en premier. (#1491)
* Dans Internet Explorer et d'autres contrôles MSHTML, les boîtes à listes dans les ARIA sont maintenant traités en tant que listes, plutôt que comme des éléments de liste.
* Quand un contrôle d'édition en lecture seule reçoit le focus, NVDA annonce désormais qu'il est en lecture seule. (#1436)
* En mode navigation, NVDA se comporte comme requis en présence des zones d'édition en lecture seule.
* Dans les documents navigables, NVDA ne quitte plus par intermittences le mode formulaire lorsque aria-activedescendant est défini; par exemple lorsque la liste des suggestions apparaît dans certains contrôles à complétion automatique.
* Dans Adobe Reader, le nom des contrôles est maintenant annoncé lors d'un mouvement de curseur ou lors de la navigation qui requiert l'utilisation des touches d'accès rapides en mode navigation.
* Dans les documents PDF XFA sous Adobe Reader, les boutons, les liens et les graphiques sont maintenant identifiés correctement.
* Dans les documents PDF XFA d'Adobe Reader, tous les éléments sont maintenant rendus sur des lignes séparées. Cette modification a été apportée parce que de grandes sections d'un document, (parfois même le document intégral) étaient restitués sans pauses en raison de l'absence générale de la structure de ces documents.
* Correction des problèmes de déplacement du curseur vers ou loin de certains champs d'édition dans les documents XFA PDF dans Adobe Reader.
* Dans les documents PDF XFA d'Adobe Reader, les changements d'état d'une liste déroulante ayant le focus seront désormais annoncés.
* Les zones de liste déroulantes du type Owner-Drawn comme celles de choix des couleurs dans Outlook Express sont maintenant accessibles avec NVDA. (#1340)
* Dans les langues qui utilisent un espace pour séparer les groupes de chiffres/milliers comme le français et l'allemand, les nombres appartenant à des séquences textuelles distinctes ne sont plus prononcés comme un nombre entier. Ceci était particulièrement problématique pour les cellules de tableau contenant des nombres. (#555).
* Les nœuds ARIA ayant un rôle de description sous Internet Explorer et autres contrôles MSHTML sont maintenant traités comme du texte statique, non comme des zones d'édition.
* Correction de plusieurs problèmes où l'appui sur TAB quand le focus est sur un document en mode navigation dysfonctionnait; (la touche TAB se déplaçait inopportunément vers la barre d'adresse dans Internet Explorer, par exemple). (#720, #1367)
* Lorsque NVDA lit intégralement un texte et qu'il rencontre des listes, NVDA dit maintenant "Liste de 5 éléments" au lieu de "Listeavec 5 éléments" Anglais uniquement. (#1515)
* Il est probable que désormais, la touche de tabulation ne vous amène plus à la barre d'adresses, lors de la première ouverture d'Internet Explorer et de l'affichage d'une page Web.
* En mode "Aide à la saisie", les gestes sont consignés dans le journal de NVDA, même si les scripts qu'ils déclenchent ne relèvent pas du mode "Aide à la saisie", comme c'est le cas pour les commande de défilement Avance ou Recul sur un afficheur Braille.
* En mode "Aide à la saisie", lorsqu'une touche modificatrice du clavier est maintenue appuyée, NVDA ne la signale plus comme si elle était elle-même modifiée; par exemple, NVDA+NVDA.
* Dans les documents Adobe Reader, l'appui sur C ou Maj+C pour accéder à une zone de liste déroulante fonctionne maintenant correctement.
* Le fait que des lignes sélectionnables d'un tableau soient sélectionnées est maintenant annoncé de la même façon que pour les éléments d'une liste ou ceux d'une arborescence.
* Les contrôles sous FireFox et d'autres applications Gecko peuvent être activés en mode navigation, même si leur contenu flotte hors écran. (#801)
* Il ne vous est plus possible d'ouvrir un dialogue de paramètres NVDA quand un autre dialogue de paramètres est actif. Cela conduisait, par le passé, à un gel du dialogue de configuration. (#1451)
* Réintégration du dialogue de l'Éditeur NVDA des cellules Excel. Celui-ci a été accidentellement désactivé dans NVDA 2011.1.
* Dans Microsoft Excel, il n'y a plus de ralentissement quand on maintient enfoncées ou que l'on appuie rapidement sur les touches pour se déplacer entre les cellules ou les sélectionner.
* Correction des arrêts intermittents du service NVDA, ce qui se traduisait par la non-réponse du lecteur d'écran en présence des bureaux sécurisés de Windows.
* Correction des problèmes qui survenaient avec les afficheurs Braille lorsqu'un changement causait la disparition du texte qui y était affiché.
* La fenêtre de téléchargements sous Internet Explorer 9 peut maintenant être explorée et lue avec NVDA. (#1280)
* Il n'est plus possible de démarrer accidentellement plusieurs copies de NVDA en même temps. (#507)
* Sur les systèmes lents, NVDA n'affiche plus inopportunément sa fenêtre principale quand il est en cours d'exécution. (#726)
* NVDA ne gèle plus sous Windows XP lors du démarrage d'une application WPF. (#1437)
* La commande "Dire tout" et "lire tout avec le curseur de revue" sont maintenant en mesure de travailler dans certains contrôles de texte UI automation qui prennent en charge toutes les méthodes requises. (Par exemple vous pouvez maintenant utiliser "Dire tout" avec le curseur de revue pour consulter les documents ouverts dans la Visionneuse XPS).
* Lors de la création d'une règle de messages, NVDA ne classe plus incorrectement certains éléments de liste du dialogue "Appliquer la règle maintenant" sous Outlook Express ou Windows Live Mail. Il ne les considère plus comme étant des cases à cocher. (#576)
* Les zones de listes déroulantes ne sont plus signalés comme comportant un sous-menu.
* NVDA est maintenant capable de lire la liste des destinataires inscrits dans les champs à, CC et CCI sous Microsoft Outlook. (#421)
* Résolution d'un dysfonctionnement dans le dialogue Paramètres vocaux de NVDA où la valeur des barres de défilement n'était parfois pas annoncée lorsqu'on la changeait. (#1411)
* NVDA n'échoue plus quand il s'agit d'annoncer la nouvelle cellule lors du déplacement dans une feuille de calcul Excel, après un couper-coller. (#1567)
* NVDA ne se dégrade plus quand il devine les noms des couleurs quand les annonces de ceux-ci sont de plus en plus nombreuses.
* Dans Internet Explorer et d'autres contrôles MSHTML, correction de l'incapacité de lire des parties de pages rares, quand elles contiennent des IFrames marquées avec un rôle ARIA de présentation. (#1569)
* Dans Internet Explorer et autres contrôles MSHTML, élimination d'un dysfonctionnement rare qui faisait que le focus rebondissait infiniment entre le document et une zone d'édition multilignes quand on était en mode formulaire. (#1566)
* Dans Microsoft Word 2010, NVDA saura désormais lire les dialogues de confirmation automatiquement. (#1538)
* Le programme d'installation de NVDA en Chinois de Hong-Kong n'affiche plus du texte tronqué sous Windows Vista et Windows 7. (#1596)
* NVDA n'est plus incapable de charger le synthétiseur SAPI 5 si la configuration utilisateurs contient les paramètres SAPI 5 mais qu'il manque un paramètre d'une voix quelconque. (#1599)
* Dans les zones d'édition sous Internet Explorer et autres contrôles MSHTML, NVDA ne ralentit plus et ne se fige plus quand le braille est activé.
* En mode navigation sous FireFox, NVDA ne refuse plus d'inclure du contenu d'un node qui peut recevoir le focus et qu'un rôle ARIA de présentation est présent.
* Sous Microsoft Word avec le braille activé, Les lignes des pages après la première page sont maintenant annoncées correctement. (#1603)
* Sous Microsoft Word 2003, les textes de droite à gauche sont de nouveau lues correctement quand le braille est activé. (#627)
* Sous Microsoft Word, Dire tout fonctionne maintenant correctement quand le document ne finit pas par un signe de fin de phrase.
* À l'ouverture d'un message au format texte brut sous Windows Live Mail 2011, NVDA se positionnera directement sur le document contenant le message permettant ainsi de le lire.
* NVDA ne se fige plus temporairement ni ne refuse de parler dans les boîtes de dialogue Déplacer vers / Copier vers dans Windows Live Mail. (#574)
* Dans Outlook 2010, NVDA suivra désormais correctement le focus dans la liste des messages. (#1285)
* Certains problèmes de connexion USB ont été résolus avec l'afficheur braille MDV Lilli. (#241)
* Dans Internet Explorer et autres champs MSHTML, les espaces ne sont plus ignorés en mode navigation dans certains cas (par exemple après un lien).
* Dans Internet Explorer et d'autres contrôles MSHTML, certains sauts de ligne superflus ont été éliminés en mode navigation. plus précisément, les éléments HTML avec un style d'affichage None ne forcent plus un saut de ligne. (#1685)
* Si NVDA ne parvient pas à démarrer, l'échec de la lecture du son d'arrêt critique de Windows n'encombre plus le message d'erreur critique dans le fichier journal.

### Changements pour les développeurs

* La documentation pour développeurs peut maintenant être générée en utilisant SCons. Voir readme.txt à la racine de la distribution source pour plus de détails, y compris ceux qui concernent les dépendances associées.
* Les locales peuvent maintenant fournir des descriptions de caractères. Voir la section Descriptions des Caractères du Guide du développeur pour plus de détails. (#55)
* Les locales peuvent maintenant fournir des informations sur la prononciation de la ponctuation et autres symboles spéciaux. Voir la section Prononciation des Symboles du Guide du développeur pour plus de détails. (#332)
* On peut désormais compiler NVDAHelper avec plusieurs options de débogage en utilisant la variable nvdaHelperDebugFlags SCons. Voir readme.txt à la racine de la distribution source pour plus de détails. (#1390)
* Les pilotes des synthèses vocales adoptent maintenant une séquence de commandes en mode texte et la parole lors de la synthétisation, et non seulement du texte et un index.
 * Cela permet la prise en compte des indexes intégrés, les changements de paramètres, etc
 * Les pilotes devraient implémenter SynthDriver.speak() au lieu de SynthDriver.speakText() et SynthDriver.speakCharacter().
 * Les anciennes méthodes seront utilisées si SynthDriver.speak() n'est pas mis en œuvre, mais ils sont obsolètes et seront supprimées dans une version future.
* gui.execute() a été supprimé. wx.CallAfter() doit être utilisé à la place.
* gui.scriptUI a été supprimé.
 * Pour les boîtes de dialogue de messages, utilisez wx.CallAfter(gui.messageBox, ...).
 * Pour toutes les autres boîtes de dialogue, de vraies boîtes de dialogue wx doivent être utilisées à la place.
 * Une nouvelle fonction gui.runScriptModalDialog() simplifie l'utilisation des boîtes de dialogue modales à partir de scripts.
* Les pilotes de synthétiseur peuvent désormais prendre en charge les paramètres booléens. Voir SynthDriverHandler.BooleanSynthSetting.
* SCons accepte désormais une variable certTimestampServer spécifiant l'URL d'un serveur d'horodatage à utiliser pour horodater les signatures d'authenticité. (#1644)

## 2011.1.1

Cette version apporte plusieurs correctifs de sécurité et traite d'autres questions importantes dans NVDA 2011.1.

### Corrections de bogues

* L'élément "Faire un Don" faisant partie du menu NVDA est maintenant indisponible lors de l'exécution à l'ouverture de session, sur l'écran de verrouillage, en présence du contrôle du compte utilisateur (UAC) et autres écrans Windows sécurisés, car il s'agit d'un risque de sécurité. (#1419)
* Il est maintenant impossible de copier ou coller au sein de l'interface utilisateur de NVDA en présence d'un bureau sécurisé (écran de verrouillage, fenêtre d'ouverture de session, ainsi que sous le contrôle du compte utilisateur UAC). Ceci pour combler une faille de sécurité. (#1421)
* Sous FireFox 4, la commande du mode navigation Aller à l'écran contenant, (NVDA+contrôle+espace) fonctionne comme il se doit pour quitter des objets inclus comme les contenus Flash. (#1429)
* Quand l'option Annoncer les Touches de Commande est active, les caractères en majuscules ne sont plus indûment traités comme des touches de commande. (#1422)
* Lorsque Annoncer les Touches de commande est activée, l'appui sur la barre d'espace en conjonction avec les modificateurs autres que Maj (tels que Contrôle et Alt) est maintenant annoncé en tant que touche de commande. (#1424)
* Maintenant, la journalisation est complètement désactivée lors de l'ouverture de session, lors du verrouillage de l'ordinateur, sous le contrôle du compte utilisateur UAC ou autres écrans Windows sécurisés, car il s'agit d'un risque de sécurité. (#1435)
* En mode Aide à la Saisie, les gestes sont maintenant inclus dans le journals, même s'ils ne sont pas liés à un script particulier, (conformément au guide de l'utilisateur). (#1425)

## 2011.1

Nouveautés marquantes de cette version : Annonce automatique du texte dans mIRC, PuTTY, Tera Term et SecureCRT ; Prise en charge des plugins globaux ; Annonce des puces et de la numérotation sous Microsoft Word ; De nouvelles commandes assignées pour les terminaux braille, en particuliers les touches permettant d'aller à la ligne précédente ou suivante ; Prise en charge de plusieurs terminaux Baum, HumanWare et APH braille ; Annonce des couleurs pour divers contrôles, incluant les contrôles de texte sous IBM Lotus Symphony.

### Nouvelles Fonctionnalités

* Les couleurs peuvent maintenant être annoncées pour certains contrôles. L'annonce automatique peut être configurée dans le dialogue Mise en forme des documents du menu Préférences. Elles peuvent aussi être annoncées à la demande grâce à la commande NVDA+f.
 * Pour le moment ceci est pris en charge dans les zones d'édition standards Iaccessible2 (par exemple les applications Mozilla) ainsi que dans les zones d'édition enrichie (comme dans Wordpad ou IBM Lotus Symphony).
* En mode navigation, vous pouvez maintenant sélectionner une page (en utilisant maj+page suivante et maj+page précédente), ou un paragraphe (en utilisant maj+contrôle+flèche bas et maj+contrôle+flèche haut). (#639)
* NVDA annonce maintenant automatiquement le texte sous mIRC, PuTTY, Tera Term et SecureCRT. (#936)
* L'utilisateur peut maintenant créer ou réassigner des touches de commande pour n'importe quel script dans NVDA grâce à une architecture unique de gestion des commandes utilisateur. (#194)
* Prise en charge des plugins globaux. Les plugins globaux permettent d'ajouter de nouvelles fonctions à NVDA utilisables pour toutes les applications. (#281)
* Un petit bip est maintenant émis quand on entre un caractère en pressant la touche maj alors que le verrouillage majuscule est activé. Ceci peut être désactivé en décochant la case approprié dans le dialogue Paramètres du clavier du menu Préférences.
* Les sauts de page sont maintenant annoncés quand on se déplace par ligne dans Microsoft Word. (#788)
* Les puces et la numérotation sont maintenant annoncés quand on se déplace par ligne dans Microsoft Word. (#208)
* Une commande pour activer le mode veille pour l'application en cours (NVDA+maj+s) est maintenant disponible. Le mode veille désactive toutes les fonctions de revue d'écran de NVDA pour une application donnée. Ceci est très utile pour les application parlantes ou ayant leur propre système de revue d'écran. Pressez à nouveau la commande pour quitter le mode veille.
* Quelques touches de commande supplémentaire ont été ajoutées pour les terminaux braille. Consultez la section Terminaux braille pris en charge dans le guide de l'utilisateur pour des informations supplémentaires. (#209)
* Pour faciliter le travail des développeurs de podules complémentaires, les modules applicatifs ainsi que les plugins globaux peuvent maintenant être rechargés sans besoin de redémarrer NVDA. Utilisez Outils :> Rechargement des plugins dans le menu NVDA ou NVDA+contrôle+f3. (#544)
* NVDA mémorise maintenant la position où vous vous trouviez quand vous retournez à une page web déjà visitée. Cela reste vrai jusqu'à ce que vous fermiez le navigateur ou NVDA. (#132)
* On peut maintenant utiliser les terminaux braille Handy Tech sans installer le pilote universel Handy Tech. (#854)
* Prise en charge de plusieurs terminaux braille Baum, HumanWare et APH. (#937)
* La barre d'état sous Media Player Classic Home Cinema est maintenant reconnue.
* L'afficheur braille Freedom Scientific Focus 40 Blue peut désormais être utilisé lorsqu'il est connecté via Bluetooth. (#1345)

### Changements

* L'information de position de l'objet n'est plus annoncée par défaut dans les cas où celle-ci était souvent incorrecte (beaucoup de menus, la liste des tâches actives, la zone de notification etc). Cependant, cette annonce peut être réactivée grâce à une option dans le dialogue Présentation des objets.
* L'aide clavier a été renommée en aide des commandes pour souligner le fait que les commandes peuvent provenir de sources autres que le clavier.
* L'aide des commandes n'annonce plus le nom du script car cette information n'a pas d'intérêt pour l'utilisateur. Cependant, l'information est conservée dans le journal pour les développeurs et les utilisateurs avancés.
* Lorsque NVDA détecte qu'il est bloqué, il continue à intercepter les touches de commande, bien qu'il continue à passer toutes les autres touches directement au système. Cela empêche l'utilisateur de verrouiller les majuscule de manière non intentionnelle etc. (#939)
* Si des touches sont maintenues enfoncées après entrée de la commande indiquant de passer la touche suivante directement au système, toutes les touches (y compris leur répétition) sont passées directement au système jusqu'à relâche de la dernière touche.
* Si la touche NVDA est pressée deux fois rapidement de manière à ce que la seconde pression soit directement passée au système et que la seconde pression est maintenue, toutes les répétitions de la touche seront maintenant passée au système.
* Les touches permettant de hausser, baisser le volume et de rendre muet sont maintenant annoncées en mode aide de commandes. Ceci peut être utile si l'utilisateur n'est pas certain de connaître la fonction de ces touches.
* Le raccourci clavier pour l'élément Curseur de revue dans le menu Préférences de NVDA a été modifié de r à c pour éliminer le conflit avec l'élément Paramètres Braille (interface en anglais).

### Correction de Bogues

* Quand on ajoute une nouvelle entrée au dictionnaire, le titre du dialogue est maintenant "Ajouter une entrée au dictionnaire" au lieu de "Editer une entrée du dictionnaire". (#924)
* Dans les boîtes de dialogue du dictionnaire de la voix, le contenu des colonnes Expression régulière et Sensible à la casse de la liste des entrées du dictionnaire est désormais présenté dans la langue NVDA configurée au lieu d'être toujours en anglais.
* Dans AIM, l'information de rang est maintenant annoncée dans les arborescences.
* Sur les potentiomètres du dialogue Paramètres vocaux, flèchehaut/pageprec/début augmentent la valeur du paramètre, flèchebas/pagesuiv/fin la diminuent. Précédemment, l'inverse seproduisait ce qui n'était pas logique et incohérent avec la boucle des paramètres synthétiseur. (#221)
* Dans les tampons virtuels avec la disposition d'écran désactivée, certaines lignes vides superflues n'apparaissent plus.
* Si la touche NVDA est pressée deux fois rapidement mais qu'une autre touche est pressée dans l'intervalle, la seconde touche NVDA n'est plus passée au système.
* Les touches de ponctuation sont maintenant annoncées en mode aide des commandes même si l'annonce des ponctuation est désactivée. (#977)
* Dans le dialogue Paramètres du clavier, le nom des configurations clavier est maintenant présenté dans la langue choisie pour NVDA et non systématiquement en anglais. (#558)
* Correction d'un problème qui faisait que certains éléments étaient annoncés comme vides dans les documents Adobe reader; par exemple, les liens dans la table des matières du guide de l'utilisateur d'IOS 4.1 pour l'Iphone de Apple.
* Le bouton "Utilisez les paramètres NVDA actuellement sauvegardés pour l'écran de connexion à Windows" dans le dialogue "Paramètres généraux" fonctionne maintenant quand on l'utilise immédiatement après l'installation de NVDA mais avant qu'aucun écran sécurisé n'ait été utilisé. Précédemment, il prétendait fonctionnait alors qu'il n'en était rien. (#1194)
* Il n'est plus possible d'ouvrir simultanément deux boîtes de dialogue de paramètres NVDA. Cela résout les problèmes où une boîte de dialogue ouverte dépend d'une autre boîte de dialogue ouverte ; par exemple. changer le synthétiseur pendant que la boîte de dialogue Paramètres vocaux est ouverte. (#603)
* Sur les systèmes où le contrôle d'accès utilisateur est activé, le bouton "Utilisez les paramètres NVDA actuellement sauvegardés pour l'écran de connexion à Windows" du dialogue "Paramètres généraux" fonctionne maintenant si le nom de compte utilisateur contient un blanc. (#918)
* Sous Internet Explorer et pour les autres contrôles MSHTML, NVDA utilise maintenant l'URL en dernier ressort pour déterminer le nom du lien plutôt que de présenter un lien vide. (#633)
* NVDA n'ignore plus le focus dans les menus d'AOL Instant Messenger 7. (#655)
* annonce de la bonne étiquette dans le dialogue de vérification orthographique de Microsoft Word (Ex : absent du dictionnaire, erreur grammaticale, ponctuation). Précédemment, elles étaient toutes annoncées comme ereurs grammaticales. (#883)
* Entrer du texte sous Microsoft Word en utilisant un afficheur braille ne devrait plus provoquer l'apparition de caractères parasites ainsi qu'un blocage occasionnel à l'utilisation d'une touche de routing curseur. (#1212) Cependant, une limitation fait que les textes en Arabe ne peuvent plus être lus en braille sou Word 2003 et les versions antérieures. (#627)
* Quand on presse la touche effacement dans une zone d'édition, le curseur de texte, sur les afficheurs braille, devrait maintenant être toujours mis à jour correctement pour refléter le changement. (#947)
* Les changements dynamiques de page sous Gecko2 (Ex : Firefox 4) sont maintenant pris en compte correctemeent quand plusieurs onglets sont ouverts. Précédemment, seuls les changements affectant le premier onglet étaient pris en compte. (Bogue Mozilla 610985)
* NVDA annonce maintenant correctement les suggestions pour les erreurs grammaticales ou de ponctuation dans le vérificateur orthographique de Microsoft Word. (#704)
* Sous Internet Explorer et pour les autres contrôles MSHTML, NVDA ne présente plus les ancres de destination comme des liens vides dans le document. Désormais, ces ancres sont cachées comme elles doivent l'être. (#1326)
* La navigation par objet dans et autour des fenêtres de groupage standards n'est plus impossible ou assymétrique.
* Sous Firefox et autres contrôles basés sur Gecko, NVDA ne reste plus bloqué dans un sous-cadre si le chargement de celui-ci se termine avant le chargement du document qui le contient.
* NVDA annonce maintenant correctemeent le caractère suivant quand un caractère est effacé en utilisant la touche effacer du pavé numérique. (#286)
* Sur l'écran de connexion à Windows XP, le nom de l'utilisateur est de nouveau annoncé quand on change d'utilisateur.
* Correction d'un problème de lecture de texte dans la console Windows quand l'annonce des numéros de lignes est activée.
* En mode navigation, le dialogue de la liste des liens est maintenant utilisable par une personne voyante. Tous les contrôles sont visibles à l'écran . (#1321)
* La liste d'entrées dans le dialogue du dictionnaire de prononciation est maintenant plus facile à utiliser pour une personne voyante, la liste étant assez large pour que toutes les colonnes soient visibles à l'écran. (#90)
* Sur les terminaux braille ALVA BC640/BC680, NVDA n'oublie plus les touches maintenues enfoncées après qu'une autre touche ait été relachée.
* Adobe Reader X ne se plante plus quand on quite l'option Document non balisé avant que le dialogue de mise en forme apparaisse; (#1218)
* NVDA active maintenant le bon terminal braille quand on recharge la configuration sauvegardée. (#1346)
* L'utilitaire de projet de Visual Studio 2008 et de nouveau lu correctement. (#974)
* NVDA ne refuse plus de fonctionner dans les applications dont le nom de programme comporte des caractères non Ascii. (#1352)
* Quand on lit ligne par ligne sous l'éditeur AkelPad, NVDA n'annonce plus le premier caractère de la ligne suivante à la fin de la ligne courante.
* Dans l'éditeur de code de Visual Studio 2005 ou 2008, NVDA ne lit plus l'ensemble du texte chaque fois qu'on entre un caractère. (#975)
* Correction du problème qui faisait que certains terminaux braille n'étaient pas effacés correctement quand on arrêtait NVDA ou quand on changeait de terminal.
* Le focus initial n'est plus parfois annoncé deux fois au démarrage de NVDA. (#1359)

### Changements pour les Dévelopeurs

* SCons est maintenant utilisé pour préparer l'arborescence de la source et pour créer les versions binaires, archives portables, installateurs, etc. Voir Readme.txt à la racine de la distribution source pour plus de détails.
* Les noms des touches utilisés par NVDA (y compris les maps des touches) ont été rendues plus facile/logiques ; p. ex. UpArrow au lieu d'extendedUp et numpadPageUp au lieu de prior. Voir le module vkCodes pour en obtenir la liste.
* Toute la frappe venant de l'utilisateur est maintenant représentée par une instance de inputCore.InputGesture. (#601)
 * Chaque source d'entrée sous-classe la classe de base de InputGesture.
 * Les appuis sur les touches du clavier système sont englobés par la classe keyboardHandler.KeyboardInputGesture.
 * Les appuis sur les boutons, ceux sur les roulettes et d'autres contrôles sur un afficheur braille sont englobés par les sous-classes de la classe braille.BrailleDisplayGesture. Ces sous-classes sont fournis par chaque pilote d'afficheur braille.
* Les gestes d'entrée sont affectés à ScriptableObjects à l'aide de la méthode ScriptableObject.bindGesture() sur une instance ou une dict __gestures sur la classe qui mappe des identificateurs de gestes aux noms des scripts. Voir baseObject.ScriptableObject pour plus de détails.
* Les modules d'applications ne possèdent plus de fichiers de mappage de touches. Toutes les assignations d'entrée doivent être faits dans le module de l'application lui-même.
* Tous les scripts prennent maintenant une instance de InputGesture au lieu d'une pression de touche.
 * Les gestes d'entrées au clavier (KeyboardInputGestures) peuvent être envoyés à l'OS par le moyen de la méthode de gestes send().
* Pour envoyer un appui de touche arbitraire, vous devez, désormais, créer un geste d'entrée clavier (KeyboardInputGesture) en utilisant KeyboardInputGesture.fromName(), puis utilisez sa méthode send().
* Les locales peuvent maintenant fournir un fichier de mappage de gestes d'entrée pour que l'on puisse ajouter de nouvelles affectations ou remplacer des affectations existantes pour les scripts n'importe où dans NVDA. (#810)
 * Les mappages des gestes d'entrée pour les locales doivent être placés dans locale\LANG\gestures.ini, où LANG est le code de langue.
 * Voir inputCore.GlobalGestureMap pour plus de détails sur le format de fichier.
* Les nouveaux comportements LiveText et Terminal NVDAObject facilitent l'annonce automatique du nouveau texte. Voir ces classes dans NVDAObjects.behaviors pour plus de détails. (#936)
 * La classe de superposition de NVDAObjects.window.DisplayModelLiveText peut être utilisée pour les objets qui doivent récupérer le texte écrit à l'écran.
 * Voir les modules d'application pour Mirc et Putty pour des exemples d'utilisation.
* Le module d'application _default n'existe plus. Les modules d'application doivent à présent sous-classer appModuleHandler.AppModule (la classe de base AppModule).
* Le support des plugins globaux qui peuvent globalement assigner des scripts, manipulent les évènements de NVDAObject et choisissent les classes de superposition de NVDAObject. (#281) Voir globalPluginHandler.GlobalPlugin pour plus de détails.
* Dans les objets SynthDriver, les attributs de paramètres de chaînes available* (ex: availableVoices et availableVariants) sont maintenant OrdeeredDicts indexés par ID au lieu de listes.
* synthDriverHandler.VoiceInfo prend maintenant un argument optionnel de langue qui spécifie la langue de la voix.
* Les objets SynthDriver fournissent maintenant un attribut langue qui spécifie la langue de la voix en cours.
 * L'implémentation de base utilise la langue specifiée sur les objets VoiceInfo dans availableVoices. Ceci est adapté à la plupart des synthétiseurs qui supportent une langue par voix.
* Les pilotes d'afficheurs braille ont été améliorés pour permettre aux boutons, roulettes et autres contrôles d'être reconnus par les scripts NVDA :
 * Les pilotes peuvent fournir un ensemble de gestes de saisie global connectables à des scripts n'importe où dans NVDA.
 * Ils peuvent aussi fournir leurs propres scripts pour effectuer des fonctions spécifiques à l'afficheur.
 * Veuillez consulter braille.BrailleDisplayDriver pour les détails et les pilotes d'afficheurs braille existants pour des exemples.
* La propriété 'selfVoicing' des classes AppModule a maintenant été renommée en 'sleepMode'.
* Les événements app module event_appLoseFocus et event_appGainFocus ont maintenant été renommés en event_appModule_loseFocus et event_appModule_gainFocus, respectivement, pour que la convention de nommage soit cohérente avec les app modules et les intercepteurs d'arborescences.
* Tous les pilotes d'afficheurs braille devraient maintenant utiliser braille.BrailleDisplayDriver au lieu de braille.BrailleDisplayDriverWithCursor.
 * Le curseur est maintenant géré hors du pilote.
 * Les pilotes existants doivent seulement changer leur instruction de classe en conséquence et renommer leur méthode _display en display.

## 2010.2

Les points forts de cette version incluent une navigation par objets grandement simplifiée; des tampons virtuels pour les contenus Adobe Flash; l'accès à beaucoup de contrôles précédemment inaccessibles en récupérant le texte écrit à l'écran; la revue à plat du texte à l'écran; le support des documents IBM Lotus Symphony; l'annonce des en-têtes de lignes et de colonnes sous Mozilla Firefox; et une amélioration significative de la documentation utilisateur.

### Nouvelles fonctionnalités

* La navigation parmi les objets avec le curseur de revue a été grandement simplifiée. Le curseur de revue exclut maintenant les objets inutiles; par exemple, les objets ne servant qu'à des fins d'affichage ou les objets non disponibles.
* Dans les applications utilisant Java Access Bridge (parmi lesquelles OpenOffice.org), la mise en forme du texte peut maintenant être annoncée dans les zones d'éditions. (#358, #463)
* Quand on déplace la souris parmi des cellules Microsoft Excel, NVDA les annonce correctement.
* Dans les applications utilisant le Java Access Bridge, le texte d'un dialogue est maintenant annoncé quand le dialogue apparaît. (#554)
* On peut maintenant utiliser le mode navigation pour naviguer dans les contenus Adobe Flash. La navigation par objet et l'interaction directe avec les contrôles en activant le mode formulaire sont toujours supportés. (#453)
* Les contrôles de texte éditable dans l'environnement Eclipse, incluant l'éditeur de code, sont maintenant accessibles. Vous devez utiliser Eclipse 3.6 au minimum. (#256, #641)
* NVDA peut maintenant accéder à la plupart du texte écrit à l'écran. (#40, #643)
 * Cela permet de lire des contrôles qui n'exposent pas leur information d'une manière directe plus fiable.
 * Les contrôles rendus accessibles par ce moyen incluent certains éléments de menus qui affichent des icÔnes (ex. le menu "Ouvrir avec" des fichiers de Windows XP) (#151), les zones d'édition dans les applications Windows Live (#200), la liste des erreurs dans Outlook Express (#582), les zones d'édition dans TextPad (#605), les listes dans Eudora, beaucoup de contrôles dans le programme australien E-Tax et la barre de formules dans Microsoft Excel.
* Support de l'éditeur de code dans Microsoft Visual Studio 2005 et 2008. Il est nécessaire d'utiliser au moins Visual Studio Standard, cela ne fonctionne pas dans les éditions Express. (#457)
* Support des documents IBM Lotus Symphony.
* Support expérimental de Google Chrome. Veuillez noter que le support des revues d'écran par Google Chrome est loin d'être terminé et que du travail complémentaire sera peut-être nécessaire côté NVDA.
* L'état des touches (verrouillage majuscule, verrouillage numérique et arrêt défilement) est maintenant affiché en braille quand elles sont pressées. (#620)
* Les bulles d'aide sont maintenant affichées en braille quand elles apparaissent. (#652)
* Ajout d'un pilote pour l'afficheur braille MDV Lilli. (#241)
* Quand on sélectionne une ligne ou une colonne entière dans MS Excel par les raccourcis maj+espace ou ctrl+espace, la nouvelle sélection est maintenant annoncée. (#759)
* Dans les tableaux, les titres de lignes ou de colonnes peuvent maintenant être annoncés. Ceci est configurable depuis le dialogue Mise en forme des documents du menu Préférences.
 * Actuellement, ceci est supporté dans les documents sous les applications Mozilla comme Firefox (à partir de la version 3.6.11) et Thunderbird (à partir de la version 3.1.5). (#361)
* Introduction de commandes pour la revue à plat : (#58)
 * NVDA+pavnum7 active la revue à plat, place le curseur de revue à la position de l'objet en cours, vous permettant d'explorer l'écran (ou un document) avec les commandes de revue de texte.
 * NVDA+pavnum1 Amène le curseur de revue dans l'objet représenté par le texte à la position du curseur de revue, vous permettant de naviguer par objets à partir de ce point.
* Les paramètres courants de NVDA peuvent maintenant être copiés sur les écrans sécurisés de Windows tels que l'écran de connexion ou l'écran UAC en pressant un bouton dans le dialogue Paramètres généraux. (#730)
* Support de Mozilla Firefox 4.
* Support de Microsoft Internet Explorer 9.

### Changements

* Les commandes dire tout à partir de l'objet de navigation (NVDA+pavNumPlus), déplacer l'objet de navigation à l'objet suivant de même niveau (NVDA+pavNum6) et déplacer l'objet de navigation à l'objet précédent de même niveau (NVDA+pavNum4) ont été supprimées pour le moment. Elles sont boguées et cela libère des touches pour d'éventuelles nouvelles fonctionnalités.
* Dans le dialogue Synthétiseurs, seul le nom du synthétiseur est maintenant affiché. Précédemment, il était préfixé par le nom du pilote, ce qui n'a d'intérêt qu'en interne.
* Dans les applications embarquées ou les documents navigables à l'intérieur d'un autre document navigable (ex. Flash), vous pouvez maintenant presser nvda+contrôle+espace pour quitter l'application embarquée ou le document navigable et retourner au document de niveau supérieur. Précédemment, on utilisait nvda+espace. Maintenant, nvda+espace est utilisé uniquement pour basculer entre le mode formulaire et le mode navigation dans les documents navigables.
* Si la visionneuse de parole (activée dans le menu Outils) reçoit le focus (ex. on a cliqué dessus) son contenu ne sera pas raffraîchi jusqu'à ce qu'on la quitte. Cela permet de sélectionner plus facilement le texte (Ex. pour copie).
* la visionneuse de journal et la console Python sont maximisées quand elles sontactivées.
* Quand le focus est dans une feuille de travail sous MS Excel, et que plusieurscellules sont sélectionnées, l'ensemble des sélections est annoncée, plutôt que la cellule active seulement. (#763)
* La sauvegarde de la configuration, et la modification de certaines options sensibles, sont maintenant désactivées quand NVDA s'exécute en mode sécurisé. (sur les écrans de connexion ou UAC).
* Mise à jour du synthétiseur eSpeak à la version 1.44.01.
* Si NVDA est en cours d'exécution, L'activation du raccourci de NVDA sur le bureau (ou contrôle+alt+n) arrêtera et relancera NVDA.
* Suppression de la case à cocher Annoncer le texte souris du dialogue Paramètres de la souris, remplacé par une case à cocher "Activer le suivi de la souris qui convient mieux au script Bascule du sivi de la souris (NVDA+m).
* Mise à jour de la configuration clavier Laptop pour qu'elle contienne toutes les commandes disponibles dans la configuration Desktop et qu'elle fonctionne sur les claviers non anglophones. (#798, #800)
* Améliorations et mises à jour significatives de la documentation incluant la documentation de la configuration clavier Laptop et la synchronisation entre le manuel Référence rapide des touches de commande et le guide utilisateur. (#455)
* Mise à jour du traducteur braille liblouis à la version 2.11. Cela corrige en particulier des problèmes avec les tables de conversion chinoises et l'affichage des caractères non définis dans les tables. (#484, #499)

### Corrections de bogues

* Sous µTorrent, l'élément focalisé dans la liste de torrents n'est plus répété indéfiniment et ne vole plus le focus quand un menu s'ouvre.**
* Sous µTorrent, les noms des fichiers dans la liste de contenu du torrent sont maintenant annoncés.
* Dans les applications Mozilla, le focus est maintenant détecté correctement quand il arrive sur un tableau ou une arborescence vide.
* Dans les applications Mozilla, "non coché" est maintenant correctement annoncé pour les contrôles cochables tels que les cellules de tableaux cochables. (#571)
* dans les applications Mozilla, le texte des dialogues Aria correctement implémentés n'est plus ignoré et sera correctement annoncé quand le dialogue apparaît.
* Dans Internet Explorer et autres contrôles MSHTML, l'attribut de niveau Aria est maintenant honnoré correctement.
* Dans Internet Explorer et autres contrôles MSHTML, le rôle Aria est maintenant préféré aux autres informations de tupe pour donner une expérience Aria plus correcte et plus prévisible.
* Correction d'une panne rare dans Internet Explorer durant la navigation de cadre en cadre.
* Dans Microsoft Word documents, les textes écrits de droite à gauche (comme les textes en Arabe) sont de nouveau lisibles. (#627)
* Forte réduction du délain d'annonce quand une grande quantité de texte est affichée dans une console de commande sur les systèmes 64 bits. (#622)
* Si Skype est déjà actif quand NVDA démarre, il n'est plus nécessaire de redémarrer Skype pour activer l'accessibilité. Ceci peut être aussi vrai pour d'autre applications qui testent l'indicateur de présence d'une revue d'écran.
* dans les applications Microsoft Office, NVDA ne se plante plus quand on presse nvda+b ou quand on navigue sur certains objets des barres d'outils. (#616)
* Correction de l'annonce incorrecte de nombres contenant un 0 après un séparateur; ex. 1,023. (#593)
* Adobe Acrobat Pro et Reader 9 ne se plantent plus quand on ferme un fichier ou qu'on effectue certaines autres tâches. (#613)
* La sélection est maintenant annoncée quand on presse contrôle+a pour sélectionner tout le texte dans certains champs d'édition comme sous Microsoft Word. (#761)
* Dans les contrôles Scintilla (ex. Notepad++), le texte n'est plus mal sélectionné quand NVDA déplace le curseur comme pendant dire tout. (#746)
* Il est à nouveau possible d'explorer le contenu des cellules sous MS Excel avec le curseur de revue.
* NVDA peut de nouveau lire ligne par ligne dans certaines zones de texte problématiques sous Internet Explorer 8. (#467)
* Windows Live Messenger 2009 ne s'arrête plus immédiatement après avoir démarré quand NVDA est actif. (#677)
* Dans les navigateurs internet, il n'est plus nécessaire de presser tab pour interagir avec les contenus embarqués comme les contenus flash après avoir pressé entrée sur l'objet embarqué ou en revenant d'une autre application. (#775)
* Dans les contrôles Scintilla (ex: Notepad++) le début des longues lignes n'est plus tronqué quand il sort de l'écran. Ces longues lignes sont également correctement affichées en Braille quand elles sont sélectionnées.
* Sous Loudtalks, il est maintenant possible d'accéder à la liste des contacts.
* L'url du document et "MSAAHTML Registered Handler" ne sont plus annoncés de manière incongrue sous Internet Explorer et les autres contrôles MSHTML. (#811)
* Dans les arborescence de l'éditeur d'Eclipse, l'élément précédemment en focus n'est plus annoncé par erreur quand un nouvel élément prend le focus.
* NVDA fonctionne maintenant correctement sur les systèmes où le répertoire courant a été retiré du chemin de recherche des dlls (en mettant l'entrée de registre CWWDIllegalInDllSearch à 0xFFFFFFFF). Note : ceci ne concerne pas la plupart des utilisateurs. (#907)
* Quand les commandes de navigation dans un tableau sont utilisées hors d'un tableau sous Microsoft word, "limite du tableau" n'est plus annoncé après "hors du tableau". (#921)
* Sous Microsoft Word, quand les commandes de navigation dans un tableau ne peuvent plus agir parce qu'on a atteint la limite du tableau, "limite du tableau" est maintenant annoncé dans la langue configurée dans NVDA et non systématiquement en anglais. (#921)
* Sous Outlook Express, Windows Mail et Windows Live Mail, l'état des cases à cocher dans les listes de règles de messages est maintenant annoncé. (#576)
* La description des règles de messages peut maintenant être lue sous Windows Live Mail 2010.

## 2010.1

Cette version met l'accent principalement sur des corrections de bugs et des améliorations de l'expérience utilisateur. Elle introduit notamment certains correctifs significatifs visant la stabilité.

### Nouvelles fonctionnalités

* NVDA n'échoue plus lors de son lancement sur un système quand aucun périphérique de sortie audio n'est présent. Bien entendu, un afficheur braille ou le synthétiseur Silence en liaison avec la visionneuse de parole devra être utilisé pour la sortie dans ce cas. (#425)
* La case à cocher (annoncer les repères de navigation) a été ajoutée au dialogue de paramètres de formatage du document. Elle vous permet de déterminer si NVDA doit annoncer les points de repère dans les documents Web. Afin d'assurer la compatibilité avec la version précédente, cette option est activée par défaut.
* Si annoncer les touches de commande est activée, NVDA annoncera désormais les noms des touches multimédia (par exemple, jouer, arrêter, page d'accueil, etc) disponibles sur de nombreux claviers quand elles sont actionnées. (#472)
* NVDA annonce maintenant le mot lors de sa suppression lorsque vous appuyez sur Ctrl+Retour-arrière dans les applications qui supportent un tel paramètre. (#491)
* Les touches fléchées peuvent désormais être utilisées dans la fenêtre de Web Formator pour naviguer et lire le texte. (#452)
* La liste des entrées du carnet d'adresses Microsoft Office Outlook est maintenant supportée.
* NVDA supporte beaucoup mieux les documents modifiables intégrés en (mode conception) dans Internet Explorer. (#402)
* Un nouveau script (NVDA+Maj+Moins du pavé numérique) vous permet de déplacer le focus du système à l'objet de navigation courant.
* De nouveaux scripts pour verrouiller et déverrouiller les boutons gauche et droit. Utile pour réaliser les opérations de glisser déposer. maj+Divisé du pavé numérique pour verrouiller / déverrouiller le bouton gauche, Maj+Multiplié du pavé numérique pour verrouiller ou déverrouiller le bouton droit.
* Ajout de nouvelles table Braille: Allemand 8 points braille informatique, Allemand abrégé grade 2, finnois 8 points braille informatique, chinois (Hong Kong, Cantonais), Chinois (Taiwan, Mandarin). (#344], #369, #415, #450)
* Il est maintenant possible de désactiver la création du raccourci sur le bureau (et donc la combinaison de touches de lancement) lors de l'installation de NVDA. (#518)
* NVDA peut, à présent, exploiter IAccessible2 lorsqu'il est présents dans les applications 64 bits. (#479)
* Amélioration du support pour les régions Live dans des applications Mozilla. (#246)
* Le contrôleur NVDA Client API est maintenant prévu pour permettre aux applications de contrôler NVDA, par exemple pour vocaliser du texte, désactiver la parole, afficher un message en Braille...etc
* Les informations et les messages d'erreur sont désormais lus dans l'écran d'ouverture de session sous Windows Vista et Windows 7. (#506)
* Dans Adobe Reader, les formulaires PDF interactifs développés avec Adobe LiveCycle sont maintenant supportés. (#475)
* Dans Miranda IM, NVDA maintenant lit automatiquement les messages entrants dans les fenêtres de discussion si l'annonce des changements dynamiques est activée. En outre, des commandes ont été ajoutées pour permettre l'annonce des trois plus récents messages (NVDA+contrôle+numéro). (#546)
* Les champs de saisie de texte sont désormais compatibles avec le contenu Adobe Flash. (#461)

### Changements

* Le message d'aide clavier extrêmement verbeux dans le menu Démarrer de Windows 7 n'est plus vocalisé.
* Le synthétiseur (Display) a été remplacé par un nouveau visualiseur de la parole. Pour l'activer, choisissez (Visionneuse de Parole) à partir du menu Outils. Le visualiseur de parole peut être utilisé indépendamment de la synthèse vocale que vous utilisez. (#44)
* Les messages s'affichant en Braille seront automatiquement abandonné si l'utilisateur appuie sur une touche qui se traduit par un changement tel qu'un mouvement de focus. Auparavant, le message restait affiché pendant la durée qui a été initialement configurée.
* Possibilité de choisir si le Braille doit être attaché au focus ou au pointeur de revue (NVDA+Ctrl+T). Ceci peut désormais être également paramétré à partir du dialogue des options Braille, et est enregistré dans la configuration utilisateur.
* Mise à jour de la synthèse vocale eSpeak vers la version 1.43.03.
* Mise à jour de liblouis vers la version 1.8.0.
* En mode navigation, l'annonce des éléments lors du déplacement par caractère ou par mot a été nettement améliorée. Auparavant, beaucoup d'informations non-pertinentes étaient transmises et les rapports étaient très différents de ceux obtenus lors du déplacement par ligne. (#490)
* Désormais, la touche Ctrl arrête tout simplement la parole comme c'est le cas pour les autres touches, plutôt que de la mettre en pause. Pour suspendre / reprendre la parole, utilisez la touche Maj.
* Le nombre de ligne et de colonnes des tableaux ne sont plus annoncés quand le focus change, car cette annonce est plutôt verbeuse et n'est généralement pas utile.

### Corrections de bogues

* NVDA n'échoue plus lors de son lancement si la prise en charge de l'UI Automation semble disponible mais que l'initialisation de ce dernier échoue pour une raison quelconque. (#483)
* Le contenu d'une ligne de tableau n'est plus annoncé comme c'était le cas parfois, lors du déplacement du focus dans une cellule dans les applications Mozilla. (#482)
* NVDA ne met plus aussi longtemps, quand il s'agit de développer les branches d'une arborescence qui contiennent une quantité très importante de sous-éléments.
* Quand il dresse la liste des voix SAPI 5, NVDA tentera, désormais, de détecter les voix qui dysfonctionnent et les exclura du dialogue Paramètres de la voix et de la boucle paramètres des synthétiseurs. Auparavant, même quand il n'y avait qu'une seule voix posant problème, il arrivait au pilote SAPI 5 intégré à NVDA de ne pas démarrer correctement.
* En mode navigation, les touches de raccourci de l'objet sont correctement annoncées, conformément à ce qui est défini dans les paramètres du dialogue Présentation des objets. (#486)
* En mode navigation, les coordonnées d'une ligne ou d'une colonne ne sont plus mal lues pour les titres de ligne et de colonne quand l'annonce des tableaux est désactivée.
* En mode navigation, les coordonnées de la ligne ou celles d'une colonne sont désormais détectées correctement lorsque vous quittez un tableau, puis réintégrez la même cellule sans visiter d'abord une autre cellule ; par exemple, en appuyant sur Flèche-Haut puis Flèche-Bas sur la première cellule d'un tableau. (#378)
* Les lignes vides dans les documents Microsoft Word et dans les zones d'édition Microsoft HTML figurent maintenant correctement sur les afficheurs Braille. Précédemment, NVDA affichait la phrase actuelle en Braille, mais pas la ligne actuelle dans ce cas-là. (#420)
* Introductions de plusieurs correctifs de sécurité lors de l'exécution de NVDA à l'ouverture de session Windows et en présence d'autres bureaux sécurisés. (#515)
* La position du curseur (caret) est maintenant correctement mise à jour lorsque vous effectuez une lecture intégrale qui s'arrête au bas de l'écran, dans les champs d'édition Windows standard et des documents Microsoft Word. (#418)
* En mode navigation, le texte n'est plus incorrectement inclus pour des images dans les liens et les autres objets cliquables lorsque ceux-ci sont marqués comme étant incompatibles avec les lecteurs d'écran. (#423)
* Des corrections ont été apportées à la disposition du clavier Ordinateur portable. (#517)
* Lorsque le curseur Braille est attaché au pointeur de la revue est que vous focalisez une fenêtre de console DOS, le curseur de la revue peut accéder maintenant correctement au texte de celle-ci.
* Lorsque vous travaillez avec TeamTalk3 ou TeamTalk4 classique, la barre de progression du VuMètre dans la fenêtre principale n'est plus annoncée au fur et à mesure qu'elle s'actualise. De plus, des caractères spéciaux peuvent être lus correctement dans la fenêtre de chat entrant.
* Les éléments du menu démarrer ne sont plus annoncés deux fois sous Windows 7. (#474)
* L'activation des liens même-page sous Firefox 3.6 déplace le curseur dans le document et le positionne à l'endroit approprié sur la page.
* Résolution du problème où certains texte n'était pas restitués sous Adobe Reader. Cela concernait certains types de documents PDF.
* NVDA ne lit plus incorrectement certains nombres séparés par un tiret, par exemple 500-1000. (#547)
* Sous Windows XP, NVDA ne provoque plus le gel d'Internet Explorer lorsque l'état des cases à cocher change dans Windows Update. (#477)
* Lorsque vous utilisez la synthèse vocale intégrée ESpeak, avec l'option émettre des bips et parler, cela ne cause plus des plantages intermittents sur certains systèmes. Ce bogue a été observé, par exemple, lors de la copie de grandes quantités de données via l'Explorateur Windows.
* NVDA n'annonce plus qu'un document Firefox est occupé (par exemple en raison d'une mise à jour ou de rafraîchissement) lorsque ce document est en arrière-plan. Cela faisait également que la barre d'état de l'application au premier plan soit indûment annoncée.
* Lors du basculement entre les dispositions de clavier Windows (avec Ctrl+Maj ou Alt+Maj), le nom complet de la méthode d'entrée est signalé vocalement et en Braille. Avant, cette commutation était parlée seulement, et les claviers alternatifs (par exemple Dvorak) n'étaient pas reportés du tout.
* Si la case annoncer les tableaux est décochée, les informations du tableau ne sont plus données quand le focus change.
* Certains contrôles de vues arborescentes standard dans les applications 64 bits, (par exemple le contenu de l'arborescence dans Microsoft HTML Help) sont désormais accessibles. (#473)
* Correction de quelques problèmes avec la journalisation de messages contenant des caractères non-ASCII. Cela pouvait causer la consignation d'erreurs parasites dans certains cas, sur les systèmes non-Anglais. (#581)
* Les informations contenues dans le dialogue À propos de NVDA apparaissent maintenant dans la langue système ou celle configurée par l'utilisateur au lieu de s'afficher toujours en anglais. (#586)
* Plus aucun problème n'est rencontré après que le dialogue Synthétiseurs ait été utilisé pour migrer d'une voix vers une autre qui dispose de paramétrages moins nombreux que la voix de départ.
* Dans la fenêtre de Skype 4.2, les noms de contacts ne sont plus vocalisés deux fois dans la liste de contacts.
* Correction de quelques fuites de mémoire potentiellement important au niveau de l'interface graphique et en mode navigation. (#590, #591)
* Contournement d'un dysfonctionnement grave de quelques synthétiseurs SAPI 4 qui était à l'origine des erreurs fréquentes et des blocages de NVDA. (#597)

## 2009.1

Les points forts principaux de cette version comprennent le support des éditions 64 bits de Windows; la prise en charge améliorée des documents s'affichant sous Microsoft Internet Explorer et Adobe Reader; le support de Windows 7, la lecture de l'ouverture de session Windows, Ctrl+Alt+Suppr et des écrans Contrôle du Compte Utilisateur (UAC) ainsi que la possibilité d'interagir avec les contenus Adobe Flash et Sun Java sur des pages Web. Il ya eu également plusieurs correctifs de stabilité et des améliorations significatives touchant l'expérience générale des utilisateurs.

### Nouvelles fonctionnalités

* Le support officiel des éditions 64 bits de Windows! (#309)
* Ajout d'un pilote pour la synthèse vocale Newfon. Notez que cela nécessite une version spéciale de celle-ci. (#206)
* Dans les documents navigables, le mode formulaire et le mode navigation peuvent désormais être signalés en utilisant des sons distincts au lieu de la parole. Cette fonction est activée par défaut. Ceci peut être configuré à partir du dialogue Mode Navigation. (#244)
* NVDA n'interrompt plus la parole lorsque les touches de réglage du volume sont actionnées au clavier, ce qui permet à l'utilisateur de modifier le volume et écouter immédiatement le résultat. (#287)
* Le support des documents nécessitant Microsoft Internet Explorer et Adobe Reader a été complètement réécrit. Ce support a été unifié avec le support de base utilisé pour Mozilla Gecko. Ainsi, des fonctions telles que le chargement rapide des pages, la navigation extensive utilisant les touches rapide, la liste des liens, la sélection de texte, le mode formulaire automatique et le support Braille sont maintenant disponibles avec ces documents.
* Amélioration de prise en charge de l'élément Sélection de la date qui fait partie du dialogue Propriétés de la date / heure sous Windows Vista.
* Prise en charge améliorée du Menu Démarrer moderne sous Windows XP / Vista, (en particulier l'élément (Tous les programmes). L'information appropriée de niveau des entrées composant les menus est maintenant annoncée.
* La quantité de texte annoncé quand la souris est déplacée est maintenant configurable à partir du dialogue Paramètres de la Souris. Un choix entre paragraphe, ligne, mot ou caractère peut être fait.
* Annonce des fautes d'orthographe sous le curseur dans Microsoft Word.
* Support du vérificateur orthographique de Microsoft Word 2007. Une prise en charge partielle peut être disponible pour les versions antérieures de Microsoft Word.
* Meilleur support pour Windows Live Mail. Les messages en texte brut peuvent désormais être lus et les éditeurs des courriels au format texte brut et HTML sont utilisables.
* Sous Windows Vista, si l'utilisateur se déplace vers le bureau sécurisé (soit parce que le dialogue de contrôle UAC apparaît, ou parce que la combinaison CTRL+ALT+SUPPR a été tapée), NVDA annonce le fait que l'utilisateur est maintenant sur le bureau sécurisé.
* NVDA peut annoncer le texte sous la souris dans les fenêtres de console DOS.
* Support pour UI Automation via le client UI Automation API disponibles dans Windows 7, plus quelques corrections visant l'amélioration des performances de NVDA sous cet environnement.
* NVDA peut être configuré pour démarrer automatiquement lorsque vous ouvrez une session Windows. Cette option se trouve dans le dialogue Paramètres généraux.
* NVDA peut lire les écrans sécurisés de Windows telles que celui de l'ouverture de session, CTRL+ALT+SUPPR ainsi que celui du Contrôle du Compte Utilisateur sous Xp et versions ultérieures.
* Ajout d'un pilote pour les afficheurs Braille Optelec ALVA série BC6.
* Lors du parcours des pages Web, vous pouvez maintenant appuyer sur n et Maj+n respectivement pour vous déplacer entre des blocs de liens en avant ou en arrière.
* Lorsque vous naviguez dans des documents Web, les points de repère ARIA sont maintenant annoncés et vous pouvez les parcourir vers l'avant ou en arrière en utilisant d et maj+d, respectivement. (#192).
* Le dialogue Liste des liens disponible pour les pages Web est devenu une liste d'éléments. Celle-ci peut contenir des liens, des titres et des points de repère. Les titres et les repères sont présentés hiérarchiquement. (#363)
* Le nouveau dialogue Liste des éléments contient un champ "filtrer par", permettant de trier la liste pour ne montrer que les éléments correspondant au texte qui a été tapé. (#173)
* Les versions portables de NVDA détectent maintenant les configurations utilisateur si celles-ci sont présentes dans le dossier «UserConfig« se trouvant dans le répertoire NVDA, et les appliquent s'il y a lieu. Tout comme pour les versions avec programme d'installation, les configurations utilisateur et la configuration de NVDA lui-même sont séparées.
* Les modules d'applications qui ont été personnalisées, les pilotes d'affichage Braille et ceux des synthèses vocales peuvent maintenant être sauvegardés dans le répertoire de configuration de l'utilisateur. (#337)
* Les écrans virtuels sont maintenant restitués en arrière-plan, ce qui permet à l'utilisateur d'interagir avec le système dans une certaine mesure au cours du processus de rendu. L'utilisateur sera averti que le document est en cours de formatage si le temps de chargement de l'écran prend plus d'une seconde.
* Si NVDA détecte qu'il a gelé pour une raison quelconque, il libèrera automatiquement toutes les frappes de sorte que l'utilisateur ait une meilleure chance de récupérer le système.
* Support du glisser-déposer dans les ARIAS Gecko de MOZILLA. (#239)
* Le titre du document, la ligne courante ou le contenu de la sélection sont maintenant vocalisés lorsque vous déplacer le focus dans un document navigable. Cela rend le comportement de la navigation plus compatible avec celui pratiqué en présence d'objets ou documents normaux. (#210)
* En mode navigation, vous pouvez maintenant interagir avec les objets embarqués (tels que les contenus Adobe Flash et Sun Java) en appuyant sur ENTRÉE quand vous y êtes positionné. Si l'objet inclus est accessible, vous pouvez ensuite tabuler autour de lui comme dans toute autre application. Pour revenir à la navigation dans le document, appuyez sur NVDA+Espace. (#431)
* En mode navigation, o et Maj+o déplacent vers l'objet embarqué suivant et précédent, respectivement.
* Désormais, NVDA peut accéder entièrement aux applications en cours d'exécution en tant qu'administrateur sous Windows Vista et versions ultérieures. Vous devez installer une version officielle de NVDA pour que cela fonctionne. Cela ne fonctionne pas pour les versions portables et les versions dites de développement, (Snapshots). (#397)

### Changements

* NVDA n'annonce plus "NVDA est prêt" quand il se lance.
* Les sons de démarrage et d'arrêt de NVDA sont maintenant joués avec le périphérique audio configuré dans NVDA au lieu du périphérique Windows par défaut. (#164)
* Les annonces de barres de progression ont été améliorées. Plus précisément, vous pouvez maintenant configurer NVDA de façon à ce qu'il les affiche, qu'il émette un signal sonore, ou même activer l'annonce et les signaux sonores en même temps.
* Certains rôles génériques, tels que volet, application ou cadre, ne sont plus signalés en cours de navigation à moins que le contrôle soit sans nom.
* La commande de revue «copie du texte sélectionné» (NVDA+f10) copie la sélection à partir du marqueur de début jusqu'à et y compris, la position du curseur, au lieu d'exclure la position de revue courante. Cela permet la copie du dernier caractère d'une ligne, ce qui n'était pas possible auparavant. (#430)
* Le script navigatorObject_where (Ctrl+NVDA+5 du pavé numérique) a été supprimé. Cette combinaison de touches ne fonctionne pas sur certains claviers, et le script en question n'a pas été jugé très utile.
* Le script navigatorObject_currentDimentions a été réassigné à NVDA+Supprimer du pavé numérique. L'ancienne combinaison de touches ne fonctionnait pas sur certains claviers. Ce script rapporte maintenant la largeur et la hauteur de l'objet au lieu des coordonnées droite / bas.
* Amélioration des performances (en particulier sur les netbooks) où de nombreux bips se produisent en une succession rapide, par exemple lors du mouvement de la souris véloce avec coordonnées audio activées. (#396)
* Le son d'erreur de NVDA n'est plus joué dans les versions candidates et les versions finales. Notez que les rapports d'erreurs sont toujours activés.

### Corrections de bogues

* Quand NVDA est exécuté à partir d'un chemin DOS 8.3, mais qu'il est installé dans le chemin d'accès long correspondant (par exemple progra~1 versus Program Files) NVDA identifie correctement la copie installée et charge les paramètres utilisateur en mémoire.
* L'annonce du titre de la fenêtre en premier plan en cours obtenue par la commande NVDA+t fonctionne désormais correctement quand on est dans les menus.
* L'affichage en Braille n'inclut plus d'informations inutiles dans le contexte d'une navigation, telles que les volets non-étiquetés.
* Plus question d'annoncer des informations inutiles lors d'un changement de focus, comme pour les volets racine, les volets en couches et les volets de défilement dans les applications Java ou les applications Lotus.
* Rendu les champs de recherche par mot-clé dans l'afficheur d'aide Windows (CHM) beaucoup plus utilisable. En raison du dysfonctionnement permanent de cette zone, le mot-clé actuelle ne pouvait pas être lu, car en évolution constante.
* Annonce correcte des numéros de pages sous Microsoft Word, si la numérotation des pages a été spécifiquement modifiée dans le document.
* Prise en charge meilleure des champs d'éditions dans les dialogues Microsoft Word (par exemple, le dialogue Polices). Il est maintenant possible de naviguer dans ces zones avec les touches fléchées.
* Prise en charge améliorée des fenêtre DOS. En concret: NVDA peut maintenant lire le contenu de certaines consoles qu'il considérait vierges habituellement. L'appui sur Ctrl+pause n'arrête plus NVDA.
* Sous Windows Vista et versions ultérieures, l'installation de NVDA le démarre maintenant avec les privilèges utilisateur normaux lors de la demande d'exécuter NVDA qui s'affiche en fin d'installation.
* La touche retour-arrière est maintenant traitées correctement en mode écho clavier par mots. (#306)
* Ne pas dire de manière incorrecte "Menu Démarrer" en présence des menus contextuels dans l'Explorateur Windows / le shell Windows. (#257)
* NVDA gère désormais correctement les étiquettes ARIA dans Mozilla Gecko lorsqu'il n'y a pas d'autres contenus utiles. (#156)
* NVDA ne passe plus automatiquement en mode formulaire de façon incorrecte dans les champs modifiables qui mettent à jour leur valeur lors des changements de focus, comme c'était le cas pour https://tigerdirect.com/. (#220)
* NVDA tentera, désormais, de se remettre de certaines situations qui, auparavant, provoquaient son gel complet. Cela peut prendre jusqu'à 10 secondes avant que NVDA ne détecte et récupère d'un tel gel.
* Quand la langue NVDA est réglée sur "User-Default", utiliser la langue d'affichage de l'utilisateur Windows au lieu de la configuration locale Windows. (#353)
* NVDA reconnaît maintenant l'existence des contrôles dans AOL Instant Messenger 7.
* La commande «passer la touche à l'application active» ne se bloque plus lorsqu'une touche est maintenue enfoncée. Auparavant, NVDA cessé d'accepter des commandes si cela se produisait et devait être redémarré. (#413)
* La barre des tâches n'est plus ignorée quand elle reçoit le focus, ce qui se produit souvent lorsque vous quittez une application. Auparavant, NVDA se comportaient comme si le focus n'avait pas du tout changé.
* Lors de l'exploration des zones detexte dans les applications qui utilisent Java Access Bridge (comme dans OpenOffice.org), NVDA fonctionne désormais correctement lorsque l'annonce des numéros de ligne est activée.
* La commande de revue de copie (NVDA+f10) traite correctement la situation où elle est utilisée sur une position avant le marqueur de début. Auparavant, cela pouvait causer des problèmes tels que des arrêts intermittents de NotePad++.
* Certains caractères de contrôle du type (0x1) ne provoque plus un comportement étrange de eSpeak (comme des variations de volume et de hauteur) quand il est rencontré dans le texte. (#437)
* La commande dire le texte sélectionné (NVDA+Maj+flèche haut) annonce maintenant correctement qu'il n'y a pas de sélection dans les objets qui ne supportent pas la sélection de texte.
* Correction d'un problème où l'appui sur la touche ENTRÉE sur les boutons de Miranda-IM ou sur certains de ses liens causait le gel de NVDA. (#440)
* La ligne actuelle ou la sélection est maintenant correctement respectée lors de l'épellation ou la copie de l'objet de navigation courant.
* Travaill autour d'un dysfonctionnement qui causait la vocalisation de certains éléments indésirables de la corbeille de Windows après le nom des liens, surtout dans les dialogues de l'Explorateur Windows et celles de Internet Explorer. (#451)
* Correction d'un problème d'annonce de la date et de l'heure par le biais de la commande (NVDA+F12). Antérieurement, l'annonce de la date était tronquée sur certains systèmes. (#471)
* Résolution du problème où le signe représentant le lecteur d'écran actif sur le système était parfois estompé inopinément après l'interaction avec des écrans sécurisés de Windows. Cela pouvait provoquer des problèmes dans les applications qui vérifient le signe indiquant la présence d'un lecteur d'écran, ce qui inclut Skype, Adobe Reader et Jart. (#462)
* Dans une zone de liste déroulante sous Internet Explorer 6, l'élément actif est maintenant annoncé quand il est atteint. (#342)

## 0.6p3

### Nouvelles fonctionnalités

* Comme la barre de formule de calcul Microsoft Excel est inaccessible à NVDA, un dialogue NVDA spécifique a été prévu lorsque l'utilisateur appuie sur F2 pour éditer une cellule.
* Prise en charge du formatage de texte dans les contrôles IAccessible2, y compris les applications Mozilla.
* Les fautes d'orthographe peuvent maintenant être signalé lorsque cela est possible. Ceci est configurable à partir du dialogue Mise en forme du document sous le menu Préférences.
* NVDA peut être configuré pour émettre un signal sonore, soit pour toutes les barres de progression ou seulement pour indiquer celles qui sont visibles. Alternativement, il peut être configuré pour vocaliser les valeurs des barres de progression toutes les 10%.
* Les liens peuvent maintenant être identifiés dans des contrôles RichEdit.
* Maintenant, la souris peut être déplacée vers le caractère sous le curseur de revue en présence de la plupart des zones d'édition. Auparavant, la souris ne pouvait atteindre que le milieu de la zone modifiable.
* En mode navigation, le pointeur de revue capture désormais le texte de la mémoire tampon, pas uniquement le texte interne de l'objet de navigation (qui n'est souvent pas nécessaire pour l'utilisateur). Cela signifie que vous pouvez naviguer dans le document hiérarchiquement en utilisant l'objet de navigation et le curseur de revue se déplace jusqu'à cet endroit dans la mémoire tampon.
* Gérer certains états supplémentaires des zones en Java.
* Si la commande titre (NVDA+t) est actionnée deux fois rapidement, NVDA épelle le titre. Si vous effectuez trois fois cette combinaison de touches, le titre est copié dans le presse-papiers.
* L'aide clavier prononce maintenant les noms des touches de modification lorsque vous les enfoncez toutes seules.
* Les noms des touches annoncées par l'aide clavier sont maintenant traduisibles.
* Ajout du support pour la zone de texte reconnu dans SiRecognizer. (#198)
* Support des afficheurs braille !
* Ajout de la commande (NVDA+c) pour lire le texte se trouvant dans le presse-papiers de Windows. (#193)
* Dans les documents navigables, si NVDA passe automatiquement en mode formulaire, vous pouvez utiliser la touche ÉCHAPPE pour revenir en mode navigation. NVDA+espace peut également être utilisée.
* Dans les documents navigables, lorsque le focus change ou que le curseur est déplacé, NVDA peut basculer automatiquement en mode formulaire ou en mode navigation en fonction de la commande sous le curseur. Ce paramètre est configuré à partir du dialogue Mode Navigation. (#157)
* Réécriture du pilote des synthèses vocales fonctionnant selon la norme SAPI4. Cette nouvelle mouture remplace le pilote Sapi4 fourni par Serotek et les pilotes Sapi4 ActiveVoice et devrait corriger les problèmes rencontrés avec ces pilotes.
* L'application NVDA comprend maintenant un manifeste, ce qui signifie qu'elle ne fonctionne plus en mode de compatibilité sous Windows Vista.
* Le fichier de configuration et des dictionnaires des synthétiseurs de parole sont maintenant sauvegardées dans le dossier applications data de l'utilisateur si NVDA a été installé. Cela est nécessaire pour Windows Vista et permet également aux utilisateurs d'avoir plusieurs configurations individuelles.
* Ajout de support des informations sur la position dans les contrôles IAccessible2.
* Possibilité de copier du texte dans le presse-papiers en utilisant le pointeur de revue. NVDA+F9 définit le marqueur de début jusqu'à la position actuelle du curseur de revue. NVDA+F10 récupère le texte entre les marqueurs de début et la position actuelle du curseur de revue puis le copie dans le presse-papiers. (#240)
* Ajout du support pour certaines zones d'édition du logiciel TV Pinacle.
* Lors de l'annonce de sélections, si le texte sélectionné est assez long, (512 caractères ou plus), NVDA donne désormais le nombre de caractères sélectionnés, plutôt que de dire toute la sélection. (#249)

### Changements

* Si la sortie audio est configurée de façon à utiliser le périphérique par défaut de Windows (Mappeur de son Microsoft), NVDA dirigera ESpeak au périphérique par défaut. Il émettra un signal sonore en cas de changement de carte son. Par exemple, NVDA se tournera vers un périphérique audio USB si celui-ci est connecté et qu'il devient automatiquement le périphérique actif.
* Amélioration des performances de la synthèse vocale ESpeak avec certains pilotes audio de Windows Vista.
* Les annonces des liens, des titres, des tableaux, des listes et des citations peuvent être configurées à partir du dialogue Mise en forme du document. Avant, pour configurer ces paramètres pour le mode navigation, il fallait recourir au dialogue Mode Navigation. Maintenant, tous les documents obéissent à cette configuration.
* Le débit par défaut est maintenant activé dans le dialogue Synthétiseurs.
* Amélioration du chargement et du déchargement des modules d'applications.
* La commande Titre (NVDA+t) n'annonce maintenant que le titre au lieu de l'objet entier. Si l'objet de premier plan n'a pas de nom, le nom du processus de l'application est utilisé.
* Au lieu des indication (Mode Focus) et (Mode Tampon Virtuel), NVDA annonce (Mode formulaire) et (Mode navigation).
* Les voix sont maintenant sauvegardées dans le fichier de configuration selon leur ID et non par index. Cela rend les paramètres vocaux plus fiables quel que soit la version du système d'exploitation et les changements de configuration. Ces paramètres ne seront pas conservées dans des configurations anciennes et une erreur peut être écrite dans le journal la première fois qu'un synthétiseur est utilisé. (#19)
* Le niveau d'un élément d'arborescence est maintenant annoncé en premier s'il a changé par rapport à l'élément précédemment focalisé pour toutes les vues arborescentes. Auparavant, cela n'était valable que pour les arborescences Windows en natif, (SysTreeView32).

### Corrections de bogues

* Le dernier segment audio n'est plus tronquée lors de l'utilisation de NVDA avec eSpeak sur un serveur de bureau à distance.
* Correction du problème d'enregistrement du dictionnaire de prononciation de certaines voix.
* Éliminé le décalage lors du déplacement par des unités autres que caractères (mot, ligne, etc.) vers le bas des longs documents au format texte brut au sein des tampons virtuels de Mozilla Gecko. (#155)
* Si l'écho par mots est activé, annoncer le mot quand Entrée est enfoncée.
* Résolution des dysfonctions relatives à l'encodage des caractères dans les documents richedit.
* La visionneuse du journal de NVDA utilise maintenant l'édition enrichie au lieu de l'édition simple pour afficher le journal. Cela améliore la lecture par mot avec NVDA.
* Correction de certaines dysfonctions liées aux objets embarqués dans les contrôles à édition enrichie.
* NVDA lit maintenant les numéros de page dans Microsoft Word. (#120)
* Résolu le problème où tabuler vers une case à cocher cochée dans une mémoire tampon virtuelle Mozilla Gecko et l'appui sur espace n'annonçait pas que la case à cocher était décochée.
* Annoncer correctement les cases à cocher partiellement cochées dans les applications Mozilla.
* Si la sélection de texte s'étend ou se réduit dans les deux sens, lire la sélection comme un segment unique au lieu de deux.
* Lors de la lecture à la souris, le texte dans les zones d'édition Mozilla Gecko doit maintenant être lu.
* Dire Tout ne devrait plus provoquer l'échec de certaines synthèses SAPI5.
* Correction d'un problème qui faisait que les changements de sélection de texte n'étaient pas lus dans les contrôles d'édition standard de windows, avant le premier changement de focus après que NVDA eut était lancé.
* Correction du suivi de la souris dans les objets Java. (#185)
* NVDA n'annonce plus les arborescences Java comportant des éléments sans enfants comme étant réduites.
* Annoncer l'objet ayant le focus quand une fenêtre Java est au premier plan. Auparavant, seul l'objet Java de niveau supérieur était restitué.
* Le pilote de la synthèse vocale eSpeak ne s'arrête plus complètement après une seule erreur.
* Résolution du problème qui faisait que les paramètres mis à jour de la voix (débit, tonalité, etc.) n'étaient pas sauvegardés lorsque la voix a été changée via la boucle de réglages du synthétiseur.
* Amélioration de la vocalisation des caractères et des mots.
* Le nouveau texte qui n'était pas annoncé auparavant dans les applications console texte (par exemple, certains jeux d'aventure en mode texte) est désormais annoncé.
* NVDA ignore désormais les changements de focus dans les fenêtres en arrière-plan. Auparavant, un changement de focus en arrière-plan pouvait être traité comme si l'objet réel a changé.
* Amélioration de la détection du focus lorsque vous quittez les menus contextuels. Avant, NVDA ne réagissait souvent pas du tout lorsque vous quittez un menu contextuel.
* NVDA annonce maintenant l'activation du menu contextuel dans le menu Démarrer.
* Le menu Démarrer classique est désormais annoncé comme menu démarrer au lieu d'être traité en tant que menu de l'Application.
* Amélioration de la lecture des alertes comme celles rencontrées dans Mozilla Firefox. Le texte ne doit plus être lu plusieurs fois et les autres informations superflues ne sont plus lues. (#248)
* Le texte des zones d'édition focusables, qui sont en lecture seule ne seront plus inclus lors de la récupération du texte des dialogues. Ceci corrige, par exemple, le problème de lecture automatique de tout le contrat de licence dans les installateurs.
* NVDA n'annonce plus la désélection de texte en quittant certains contrôles d'édition (exemple : barre d'adresse de Internet Explorer, champs d'adresse de courrier électronique Thunderbird 3).
* Lors de l'ouverture des courriels en texte clair dans Outlook Express et Windows Mail, le focus est correctement positionné dans le message prêt pour que l'utilisateur lise. Auparavant, l'utilisateur devait appuyer sur tab ou cliquer sur le message afin d'utiliser les touches de curseur et le lire.
* Correction de plusieurs problèmes majeurs avec la fonctionn « Annoncer les touches de commande ».
* NVDA peut maintenant lire le texte dépassant 65535 caractères dans les zones d'édition standard (par exemple un gros fichier dans le bloc-notes).
* Meilleure lecture par ligne des champs éditables MSHTML, (Les messages éditables sous Outlook Express et les champs de saisie de texte de Internet Explorer).
* NVDA ne se fige plus complètement comme il lui arrivait souvent, lors de l'édition de texte dans OpenOffice. (#148, #180)

## 0.6p2

* Amélioration de la voix ESpeak par défaut pour NVDA.
* Ajout d'une disposition clavier pour ordinateur portable. Les disposition clavier peuvent être configurées dans le dialogue Paramètres du clavier de NVDA. (#60)
* Support des éléments de groupages dans les contrôles SysListView32, généralement rencontrés sous Windows Vista. (#27)
* Annonce de l'état coché des éléments des arborescences dans les contrôles SysTreeview32.
* Ajout de touches de raccourcis pour beaucoup de dialogues de configuration de NVDA.
* Support des applications tirant parti de IAccessible2 comme Mozilla Firefox quand NVDA est exécuté à partir des médias portables, sans besoin d'enregistrer de fichiers Dll spécifiques.
* Résolution d'un arrêt inopiné dans la liste des liens dans les tampons virtuels au sein des applications Gecko. (#48)
* NVDA ne devrait plus arrêter inopinément les applications Mozilla Gecko comme Firefox et Thunderbird si NVDA s'exécute avec des privilèges plus hauts que l'application Mozilla Gecko. Par exemple quand NVDA est exécuté en tant qu'Administrateur.
* Les dictionnaires de parole (précédemment Dictionnaires utilisateur) peuvent être soit sensibles à la casse ou non, et les entrées peuvent être optionellement des expressions régulières. (#39)
* Que NVDA utilise ou non un mode 'disposition d'écran' pour les tampons virtuels, les documents sont maintenant configurables moyennant un dialogue dans les paramètres.
* Ne plus rapporter les balises des ancres ne contenant pas de href dans les documents Gecko comme liens. (#47)
* La commande Rechercher de NVDA mémorise maintenant votre dernière recherche, dans tous les programmes. (#53)
* Correction des problèmes où l'état coché n'était pas annoncé pour certaines cases à cocher et certains boutons radio dans les tampons virtuels.
* Le mode envoi de touches dans un tampon virtuel est maintenant propre à chaque document, plutôt qu'à tout NVDA. (#33)
* Correction de dysfonctionnements de changement de focus ainsi que des interuptions de la paroles ayant lieu parfois lors de l'utilisation de NVDA sur un système qui avait été mis en veille ou était plutôt lent.
* Amélioration du support des listes déroulantes dans Mozilla Firefox. Précisément, quand on utilise les flèches autour, le texte n'est plus répété, et lorsqu'on les quitte, les contrôles ancêtres ne sont pas annoncés inutilement. De plus, les touches d'accès des tampons virtuels fonctionnent maintenant quand l'une d'elles est focalisée, alors que vous êtes dans un tampon virtuel.
* Amélioration de la précision de localisation de la barre d'état dans de nombreux programmes. (#8)
* Ajout de l'outil interactif à la console Python de NVDA, pour permettre aux développeurs d'examiner et manipuler les objets internes de NVDA quand il est actif.
* Les scripts SayAll, reportSelection et reportCurrentLine fonctionnent désormais correctement en mode pass-through dans un tampon virtuel. (#52)
* Les scripts augmenter et diminuer la valeur ont été supprimés. Les utilisateurs doivent utiliser les paramètres de la boucle synthétiseur (Ctrl+NVDA+flèches) ou le dialogue Paramètres vocaux.
* Amélioration du registre et de l'échelle des bips des barres de progression.
* Ajout de nouvelles touches de navigation rapide aux tampons virtuels : l pour liste, i pour élément de liste, e pour champ d'édition, b pour bouton, x pour case à cocher, r pour bouton radio, g pour bannière, q pour citation, c pour liste déroulante, 1 à 6 pour les niveaux de titre respectifs, s pour séparateur, m pour cadre. (#67, #102, #108)
* L'annulation du chargement d'un nouveau document dans Mozilla Firefox permet désormais à l'utilisateur de continuer à utiliser le tampon virtuel de l'ancien document si l'ancien document n'a pas encore été détruit. (#63)
* La navigation par mots dans les tampons virtuels est plus précise, maintenant que les mots ne contiennent pas accidentellement du texte de plus d'un champs. (#70)
* Amélioration de la précision de suivi du focus et de la mise à jour de celui-ci lors de la navigation dans les tampons virtuels de Mozilla Gecko.
* Ajout d'un script findPrevious (maj+NVDA+f3) pour utilisation dans de nouveaux tampons virtuels.
* Correction de lenteur dans les dialogues Mozilla Gecko (Firefox et Thunderbird). (#66)
* Ajout de la possibilité de consulter le fichier journal NVDA courant. Il se trouve dans le menu NVDA > Outils.
* Les scripts tels que dire l'heure et la date prennent maintenant en compte la langue courante, la ponctuation et l'ordre des mots reflètent désormais cette langue.
* La liste déroulante des langues dans le dialogue paramètres généraux de NVDA affiche maintenant les noms complets des langues pour en faciliter l'utilisation.
* Lors de la revue du texte dans l'objet de navigation courant, le texte est toujours à jour s'il change dynamiquement. Par exemple la revue du texte d'un élément de liste du Gestionnaire des tâches. (#15)
* Lorsque vous naviguez à la souris, le paragraphe courant du texte sous la souris est maintenant annoncé, plutôt que tout le texte dans l'objet spécifique, ou tout simplement le mot courant. De plus, les coordonnées audio et l'annonce des rôles des objets sont optionnels, ils sont désactivés par défaut.
* Prise en charge de la lecture de texte à la souris dans Microsoft Word
* Correction d'un bogue où le fait de quitter la barre de menu des applications comme Wordpad faisait que la sélection de texte n'était plus annoncée.
* Dans Winamp, le titre de la piste n'est plus annoncé répétitivement lors de la commutation des pistes, ou lors de la pause, la reprise ou l'arrêt de la lecture.
* Dans Winamp, Ajout de la possibilité d'annoncer l'état des contrôles de la lecture aléatoire et de la répétition quand celles-ci sont activées. Fonctionne dans la fenêtre principale et dans l'éditeur des listes de lecture.
* Amélioration de l'activation des champs spécifiques aux tampons virtuels de Mozilla Gecko. Ceux-ci peuvent inclure des graphiques cliquables, des liens contenant des paragraphes, et d'autres structures unusuelles.
* Correction d'un ralentissement initial lors de l'ouverture des dialogues de NVDA sous certains systèmes. (#65)
* Ajout d'un support spécifique pour le programme Total Commander.
* Correction d'un bogue du pilote Sapi4 Serotek, où la tonalité se bloquait sur une valeur fixe, c'est-à-dire qu'elle restait élevée après la lecture d'une lettre majuscule. (#89)
* Annonce du texte cliquable et d'autres champs comme étant cliquables dans les tampons virtuels de Mozilla Gecko. Par exemple, un champs qui a un attribut HTML onclick. (#91)
* Lors du déplacement dans les tampons virtuels de Mozilla Gecko, faites défiler le champ courant afin qu'il soit visible, - utile pour que les pairs voyants aient une idée de l'endroit où se trouve l'utilisateur dans le document. (#57)
* Ajout du support de base pour les évènements ARIA live region show dans les applications s'appuyant sur IAccessible2. Utile pour le programme IRC ChatZilla. Les nouveaux messages seront désormais automatiquement lus.
* Quelques légères améliorations pour aider à l'utilisation des applications tirant parti de Web ARIA, par exemple, Google Docs.
* Arrêt des ajouts de lignes vides supplémentaires au texte lors de la copie à partir d'un tampon virtuel.
* La touche espace n'active plus un lien dans la Liste des Liens. Maintenant, la touche peut être utilisée comme d'autres lettres afin de commencer à taper le nom d'un lien spécifique que vous souhaitez atteindre.
* Le script moveMouseToNavigator (NVDA+PavNumDivisé) déplace maintenant la souris au centre de l'objet navigateur, plutôt que vers le haut à gauche.
* Ajout des scripts pour cliquer avec les bouton gauche et droit de la souris (PavnumDivisé et PavNumMultiplié respectivement).
* Amélioration de l'accès à la barre des tâches système de Windows. Le focus ne devrait plus mal suivre et sauter d'un endroit à un autre. Rappel : pour accéder à la barre des tâches système, utilisez la commande Windows+b. (#10)
* Amélioration des performances et arrêt de l'annonce du texte supplémentaire à l'appui sur une touche de curseur dans une zone d'édition quand le curseur arrive à la fin.
* NVDA n'a plus la possibilité de faire attendre l'utilisateur quand certains messages sont parlés. Ceci corrige des arrêts/gels avec quelques synthèses vocales. (#117)
* Ajout du support de la synthèse vocale Audiologic Tts3, contribué par Gianluca Casalino. (#105)
* Amélioration probable des performances lors du parcours des documents dans Microsoft Word.
* Amélioration de la précision lors de la lecture du texte des alertes dans les applications Mozilla Gecko.
* Corrections de dysfonctionnements possibles lors de l'enregistrement de la configuration dans les versions non-anglaises de Windows. (#114)
* Ajout d'un dialogue de bienvenue à NVDA. Ce dialogue est conçu pour fournir des informations essentielles aux nouveaux utilisateurs et permet de configurer le verrouillage majuscules comme touche NVDA. Ce dialogue s'affiche lorsque NVDA est démarré par défaut, jusqu'à ce qu'il soit décoché.
* Correction du support de base pour Adobe Reader, il est désormais possible de lire des documents sous les versions 8 et 9.
* Correction de quelques erreurs qui pouvaient se produire quand les touches étaient enfoncées avant que NVDA soit correctement lancé.
* Si l'utilisateur a configuré NVDA pour qu'il sauvegarde la configuration en quittant, le logiciel s'assurera que la configuration est correctement enregistrée lors de l'arrêt ou de la déconnexion de Windows.
* Ajout d'un logo sonore NVDA à la partie initiale de l'installateur, contribué par Victer Tsaran.
* NVDA, aussi bien en cours d'exécution sous le programme d'installation qu'autrement, nettoiera désormais correctement son icône de la barre des tâches quand il quitte.
* Les étiquettes des contrôles standard dans les dialogues de NVDA (tels que les boutons OK et annuler) s'affichent maintenant dans la langue utilisée par NVDA, plutôt que de rester en anglais.
* L'icône NVDA est maintenant utilisée pour les raccourcis de NVDA dans le menu démarrer et sur le bureau, plutôt qu'une icône de programme par défaut.
* Lecture des cellules dans Excel lors du déplacement avec tab et maj+tab. (#146)
* Correction des annonces doubles, notamment pour certaines listes de Skype.
* Amélioration du suivi du curseur dans les applications IAccessible2 et Java, comme OpenOffice et Lotus Symphony. NVDA attend que le curseur se déplace dans les documents plutôt que de lire accidentellement le mot ou la ligne incorrects à la fin des paragraphes. (#119)
* Prise en charge des contrôles AkelEdit trouvés dans AkelPad 4.0.
* NVDA ne se bloque plus dans Lotus Synphony lors du déplacement à partir du document vers la barre de menu.
* NVDA ne se bloque plus sous Windows XP dans l'applet Ajout/Suppression de programmes, au lancement d'un programme de désinstallation. (#30)
* NVDA ne se bloque plus à l'ouverture de Spybot Search and Destroy.

## 0.6p1

### Accès au contenu web grâce aux nouveaux tampons virtuels en développement (présentement pour les applications Mozilla Gecko comprenant Firefox3 et Thunderbird3)

* Les temps de chargement ont été améliorés à un facteur de presque trente (vous n'avez plus à attendre du tout pour que la plupart des pages Web se chargent dans la mémoire tampon).
* Ajout d'une liste de liens (NVDA+F7)
* Amélioration du dialogue de recherche (contrôle+NVDA+f) afin que NVDA effectue une recherche insensible à la casse, plus une correction de problèmes de focus dans ledit dialogue.
* Il est maintenant possible de sélectionner et copier du texte dans les nouvelles mémoires tampon.
* Par défaut, les nouvelles mémoires tampon rendent le document dans le format de l'écran, (les liens et les contrôles ne sont pas sur des lignes séparées, sauf s'ils le sont vraiment visuellement). Vous pouvez activer ou désactiver cette fonction avec NVDA+v.
* Il est possible de naviguer par paragraphes avec contrôle+Flèche haut et contrôle+Flèche bas.
* Support amélioré du contenu dynamique.
* Amélioration de la précision globale de la lecture des lignes et des champs lors du déplacement avec les flèches haut et bas.

### Internationalisation

* Il est maintenant possible de saisir des caractères accentués qui reposent sur une "lettre morte", alors que NVDA est en cours d'exécution.
* NVDA annonce maintenant que la disposition du clavier a changé (lors de l'appui sur alt+maj).
* La fonction d'annonce de l'heure et de la date prend maintenant en compte les options régionales et linguistiques courantes du système.
* Ajout de la traduction en tchèque (par Tomas Valusek avec l'aide de Jaromir Vit)
* Ajout de la traduction en vietnamien par Dang Hoai Phuc
* Ajout de la traduction en Africaans (af_ZA), par Willem van der Walt.
* Ajout de la traduction en russe par Dmitry Kaslin
* Ajout de la traduction en polonais par DOROTA CZAJKA et amis.
* Ajout de la traduction en japonais par Katsutoshi Tsuji.
* Ajout de la traduction en thaï par Amorn Kiattikhunrat.
* Ajout de la traduction en croate par Mario Percinic et Hrvoje Katic.
* Ajout de la traduction en galicien par Juan C. Buño.
* Ajout de la traduction en ukrainien par Aleksey Sadovoy.

### Synthèse de la parole

* NVDA est maintenant livré avec eSpeak 1.33 qui présente de nombreuses améliorations, parmi lesquelles il y a des langues améliorées, des variantes portant des noms ainsi que la capacité de parler plus vite.
* Le dialogue des paramètres de la voix vous permet maintenant de changer la variante d'un synthétiseur s'il en prend en charge. Une variante est généralement une légère variation de la voix en cours. (eSpeak prend en charge les variantes).
* Ajout de la possibilité de changer l'inflexion de la voix dans le dialogue des Paramètres Vocaux si le synthétiseur en cours la prend en charge. (eSpeak prend en charge l'inflexion).
* Ajout de la possibilité de désactiver l'annonce de l'information de position de l'objet (par exemple 1 sur 4). Cette option se trouve dans le dialogue Présentation des Objets.
* NVDA peut désormais émettre un bip signalant une lettre majuscule. Ceci peut être activé ou désactivé grâce à une case à cocher qui fait partie du dialogue Paramètres Vocaux. De plus, il y a une case à cocher, Augmenter la hauteur de la voix pour signaler les majuscules pour indiquer si NVDA doit réellement augmenter la tonalité pour les majuscules. Donc maintenant, vous pouvez avoir soit augmenter la hauteur, dire maj ou un bip, pour les lettres majuscules.
* Ajout de la possibilité de mise en pause de la parole (comme pour Voice Over sous Mac). Quand NVDA dit quelque chose, vous pouvez appuyer sur les touches contrôle ou maj pour arrêter la parole comme à l'ordinaire. Mais si vous appuyez sur maj à nouveau (aussi longtemps que vous n'avez pas appuyé sur d'autres touches), la parole continuera exactement où elle avait cessé.
* Ajout d'un pilote de synthèse virtuel qui délivre du texte dans une fenêtre au lieu de parler via un synthétiseur vocal. Cela devrait être plus agréable pour les développeurs voyants qui n'utilisent pas la synthèse de la parole, mais qui veulent savoir ce qui est dit par NVDA. Il y a probablement encore quelques bogues, mais la rétroaction est très certainement bienvenue.
* NVDA n'annonce plus la ponctuation par défaut. Vous pouvez activer l'annonce de la ponctuation avec NVDA+p.
* ESpeak parle un peu plus lentement par défaut, ce qui devrait faciliter sa compréhension pour les gens qui utilisent eSpeak pour la première fois, lors de l'installation ou lorsqu'ils débutent dans l'utilisation de NVDA.
* Ajout des dictionnaires utilisateur à NVDA. Ceux-ci vous permettent de faire prononcer à NVDA du texte différemment. Il y a trois dictionnaires : par celui par défaut, celui de la voix, et celui dit temporaire. Les entrées que vous ajoutez au dictionnaire par défaut sont tout le temps passées à NVDA. Les ictionnaires vocaux sont spécifiques au synthétiseur et la voix actuelle que vous avez défini. Le dictionnaire temporaire sert dans les périodes où vous voulez définir rapidement une règle pendant que vous accomplissez une tâche spécifique, mais que vous ne voulez pas qu'il soit permanent. (il disparaîtra si vous quittez NVDA). Pour l'instant, les règles sont les expressions régulières, pas seulement du texte normal.
* Les synthèses vocales peuvent maintenant utiliser n'importe quel périphérique de sortie audio de votre système. Servez-vous de la liste déroulante de sortie dans le dialogue Synthétiseur avant de choisir le synthétiseur que vous voulez.

### Performance

* NVDA ne prend plus une énorme quantité de mémoire système, lors de l'édition des messages dans les zones d'édition MSHTML.
* Amélioration de la performance lors de la revue du texte à l'intérieur de nombreux contrôles qui n'ont pas de vrai curseur. par exemple la fenêtre de l'historique de MSN Messenger, les éléments d'arborescences, les éléments de vue de liste etc.
* Amélioration de la performance dans les documents à édition enrichie.
* NVDA ne devrait plus indûment utiliser une taille de mémoire système de plus en plus grande sans aucune raison.
* Correction des bogues quand on essayait de focaliser une fenêtre de console DOS plus de trois fois. NVDA avait tendance à se bloquer complètement.

### Raccourcis clavier

* NVDA+ Maj + PavNum6 et NVDA + Maj + PavNum4 vous permettent de naviguer vers l'objet suivant ou précédent à la volée, respectivement. Cela signifie que vous pouvez naviguer dans un programme en utilisant uniquement ces deux touches sans souci, vers le haut par objet parent ou vers le bas pour atteindre le premier enfant quand vous parcourez la hiérarchie des objets. Par exemple dans un navigateur web comme Firefox, vous pouvez parcourir le document de l'objet, en utilisant simplement ces deux touches. Si suivant ou précédent vous amène vers le haut d'un objet, ou vers le bas au sein d'un objet, des bips se feront entendre et vous indiquent la direction.
* Vous pouvez maintenant ajuster les paramètres de la voix sans ouvrir le dialogue Paramètres vocaux, grâce à la boucle de réglages de la synthèse vocale. La boucle de la synthèse est un groupe de paramètres de voix que vous pouvez faire défiler en appuyant sur Ctrl+NVDA+droite et Ctrl+NVDA+gauche. Pour modifier un paramètre, utilisez Ctrl+NVDA+haut et Ctrl+NVDA+bas.
* Ajout d'un raccourci pour l'annonce de la sélection en cours dans les zones d'édition. (NVDA+maj+Flèche haut).
* Plusieurs raccourcis NVDA qui prononcent le texte (comme l'annonce de la ligne courante etc), épellent le texte désormais, si elles sont exécutées deux fois rapidement.
* Les touches Verrouillage Majuscule, Insert pavé numérique et Insert Clavier Étendu peuvent toutes s'utiliser comme touches modificatrices NVDA. De même, si une de ces touches est utilisée, l'appui deux fois sans appuyer sur d'autres touches enverra la touche directement au système d'exploitation, comme si vous avez enfoncé la touche sans que NVDA soit lancé. Pour faire d'une de ces touches la touche NVDA, cochez la case à cocher s'y rapportant dans le dialogue Paramètres du clavier, (précédemment nommée dialogue de l'écho clavier).

### Support de programmes

* Amélioration du support des documents Firefox 3 et Thunderbird 3. Le temps de chargement a été amélioré à un facteur de près de trente. Une disposition d'écran est utilisée par défaut (appuyer sur NVDA+v pour alterner entre cette disposition et aucune disposition d'écran). Une liste de liens (NVDA+f7 a été ajoutée). Le dialogue Rechercher (Ctrl+NVDA+f) est désormais insensible à la casse. Un support bien meilleur du contenu dynamique. La sélection et la copie du texte sont désormais possibles.
* Dans les fenêtres de l'historique de MSN Messenger et Windows Live Messenger, il est maintenant possible de sélectionner et copier du texte.
* Amélioration du support du logiciel Audacity.
* Ajout du support de quelques zones d'édition/texte dans Skype.
* Amélioration du support de Miranda Instant Messenger.
* Correction de problèmes de focus lors de l'ouverture des courriels au format HTML et texte clair sous Outlook Express.
* Les corps des messages de groupes de discussion dans Outlook express sont désormais étiquetés correctement.
* NVDA peut maintenant lire les addresses dans les champs de messages de Outlook Express (à/de/cc etc).
* NVDA devrait être plus exact quand il annonce le message suivant sous Outlook Express quand un message est supprimé de la liste de messages.

### APIs et toolkits

* Amélioration de la navigation par objet pour les objets MSAA. Si une fenêtre contient un menu système, une barre de titre ou des barres de défilement, vous pouvez maintenant les atteindre.
* Ajout du support de l'API d'accessibilité IAccessible2. En dehors de sa capacité d'annoncer plus de contrôles, NVDA peut aussi accéder au curseur dans les applications telles que Firefox 3 et Thunderbird 3, ce qui vous permet d'y naviguer, sélectionner ou y éditer du texte.
* Ajout du support des zones d'édition de Scintilla, (ces zones se rencontrent dans Notepad++ ou Tortoise SVN).
* Prise en charge des applications Java (via Java Access Bridge). Cela peut fournir le support de base pour OpenOffice (si Java est activé) et toute autre application Java autonome. Notez que les applets java dans un navigateur web ne fonctionnent pas encore.

### Souris

* Amélioration du support pour la lecture de ce qui est sous le pointeur de la souris quand il se déplace. Il est maintenant plus rapide, et il peut désormais, dans certains contrôles tels que les zones d'édition standard, Java et IAccessible2, lire le mot courant, non seulement l'objet en cours. C'est peut-être utile pour des personnes non-voyantes qui veulent juste lire une partie spécifique du texte avec la souris.
* Ajout d'une nouvelle option de configuration qui se trouve dans le dialogue des paramètres de la souris. Sonoriser les coordonnées audio quand la souris se déplace. Si cochée, cette case fait qu'un son de 40 ms est émis chaque fois que la souris bouge. La tonalité, (entre 220 et 1760 hz) représente l'axe des y et le volume de gauche à droite, représente l'axe des x. Cela permet à une personne aveugle d'avoir une idée approximative d'où la souris se trouve sur l'écran alors qu'elle est déplacée. Cette fonction dépend aussi de reportObjectUnderMouse qui doit être activé. C'est-à-dire que si vous souhaitez désactiver rapidement et les bips et l'annonce des objets, appuyez sur NVDA+m. Les bips sont également plus forts ou plus faibles, selon la brillance de l'écran à ce stade.

### Présentation des objets et interaction

* Amélioration du support des arborescence les plus communes. NVDA vous indique maintenant le nombre d'éléments dans une branche lorsque vous la développez. Il annonce également le niveau lors du déplacement dans et hors des branches. Et, il annonce le nombre de l'élément courant ainsi que le nombre d'éléments, selon la branche en cours, pas l'arborescence en entier.
* Amélioration de ce qui est annoncé lorsque le focus change, quand vous vous déplacez dans les programmes ou au sein du système d'exploitation. Maintenant, au lieu d'entendre seulement le contrôle où vous êtes, vous entendez aussi des informations sur tous les contrôles dont il fait partie. Par exemple si vous tabulez et vous trouvez sur un bouton à l'intérieur d'un groupage, ce groupage sera annoncé également.
* NVDA essaie maintenant de vocaliser les messages de nombreux dialogues quand ils apparaissent. C'est exact la plupart du temps, bien qu'il y a encore beaucoup de dialogues qui ne sont pas aussi bons qu'ils pourraient l'être.
* Ajout de la case à cocher Annoncer la description de l'objet au dialogue des paramètres de Présentation des objets. Les utilisateurs avec pouvoir souhaiteraient parfois la décocher pour empêcher NVDA d'annoncer beaucoup de descriptions supplémentaires se rapportant à des contrôles particuliers comme dans les applications Java.
* NVDA annonce automatiquement le texte sélectionné dans les zones d'édition lorsque le focus se déplace à celles-ci. S'il n'y a pas de texte sélectionné, alors il annonce seulement la ligne courante comme d'habitude.
* NVDA est beaucoup plus prudent maintenant quand il émet des bips indiquant les modifications de barre de progression dans les applications. Il ne s'affole plus dans les logiciels Eclipse tels que Lotus Notes/Symphony et Accessibility Probe.

### Interface Utilisateur

* Suppression de la fenêtre d'interface NVDA et son remplacement par un simple menu appelé NVDA.
* Le dialogue des paramètres de l'interface utilisateur de NVDA s'appelle maintenant paramètres généraux. Il contient, en outre, un paramètre supplémentaire : une zone de liste déroulante pour définir le niveau de journalisation, pour déterminer quels messages doivent être écrits dans le fichier journal de NVDA. Notez que le fichier journal de NVDA s'appelle maintenant nvda.log, pas debug.log.
* Suppression de la case à cocher Annoncer les noms de groupe des objets qui se trouvait dans le dialogue Présentation des objets. L'annonce des noms de groupe est maintenant gérée différemment.

## 0.5

* NVDA dispose maintenant d'une synthèse vocale intégrée appelée eSpeak, développée par Jonathan Duddington. Elle est très réactive, légère et elle prend en charge beaucoup de langues différentes. Les synthèses vocales Sapi peuvent encore être utilisées, mais eSpeak sera utilisée par défaut.
 * eSpeak ne dépend d'aucun logiciel spécial pour être installée, elle peut donc être utilisée avec NVDA sur n'importe quel ordinateur, sur une clef USB, ou partout.
 * Pour plus d'informations au sujet d'eSpeak, où pour trouver d'autres versions, aller à https://espeak.sourceforge.net/.
* Correction d'un bogue où le mauvais caractère était annoncé lors de l'appui sur supprime dans les volets éditables dans Internet Explorer / Outlook Express.
* Ajout du support pour plus de champs d'édition dans Skype.
* Les tampons virtuels ne sont chargés que lorsque le focus es sur la fenêtre qui a besoin d'être chargée. Ceci corrige quelques problèmes quand le volet de visualisation est actifdans Outlook Express.
* Ajout d'arguments en ligne de commande à NVDA :
 * -m, --minimal: ne joue pas les sons de démarrage et d'arrêt et ne présente pas d'interface au démarrage si configuré à cet effet.
 * -q, --quit: Met fin à tout autre instance déjà en cours d'exécution de NVDA et arrête ce dernier
 * -s, --stderr-file fileName: Spécifiez où NVDA doit placer les erreurs non interceptées ainsi que les exceptions
 * -d, --debug-file fileName: spécifie où NVDA doit placer les messages de débogage
 * -c, --config-file: spécifie un autre fichier de configuration
 * -h, -help: affiche un message d'aide dressant la liste des arguments en ligne de commande
* Correction d'un bogue faisant que les symboles de ponctuation n'étaient pas traduits vers la langue appropriée, lors de l'utilisation d'une langue autre que l'anglais, et quand l'écho par caractères était activé.
* Ajout des fichiers de la langue Slovaque grâce à Peter Vagner
* Ajout d'un dialogue de paramétrage du Mode Navigation ainsi qu'un dialogue de Mise en forme du Document, de Peter Vagner.
* Ajout de la traduction française grâce à Michel Such
* Ajout d'un script pour faire basculer le bip signalant les barres de progression entre activé et désactivé (insert+u). Proposé par Peter Vagner.
* Fait en sorte que plusieurs messages de NVDA soient traduisibles en d'autres langues. Cela comprend les descriptions de scripts quand on se trouve dans l'aide clavier.
* Ajout d'un dialogue de recherche pour les tampons virtuels (Internet Explorer et Firefox). L'appui sur Ctrl+F dans une page affichera un dialogue dans lequel vous pouvez taper un texte à rechercher. La touche Entrée recherche alors ce texte et placera le curseur du tampon virtuel sur cette ligne. La touche F3 recherchera l'occurrence suvante du texte.
* Lorsque l'écho par caractère est activé, les caractères qui ne l'étaient pas seront sonorisés. Techniquement, les caractères ASCII 32 à 255 peuvent être annoncés maintenant.
* Rebaptisé certains types de contrôle pour une meilleure lisibilité. Texte modifiable est maintenant édition, contour est maintenant arborescence et bouton-poussoir est maintenant bouton.
* Lors du déplacement avec les flèches entre les éléments dans une liste, ou entre ceux d'une vue arborescente, le type de contrôle (élément de liste, élément de vue arborescente) n'est plus annoncée. Ceci pour accélérer la navigation.
* A un pop-up (pour indiquer que le menu contient un sous-menu) est maintenant rapporté comme étant sous-menu.
* Au cas où une langue utilise contrôle et alt (ou altGR) pour la frappe d'un caractère spécial, NVDA annonce maintenant ce caractère, quand l'écho par caractères est activé.
* Correction de quelques problèmes de revue des contrôles à texte statique.
* Ajout de la traduction en chinois traditionnel, grâce à Coscell Kao.
* Restructuré une partie importante du code NVDA, ce qui a maintenant pour effet de résoudre de nombreux problèmes avec l'interface utilisateur, (y compris ceux rencontrés dans les dialogues des paramètres).
* Ajout du support SAPI4 de NVDA. Actuellement, il existe deux pilotes SAPI4, l'un basé sur le code contribué par Serotek Corporation et un autre basé sur com Interface. ActiveVoice.ActiveVoice. Ces deux pilotes ont des problèmes, à vous de voir ce qui fonctionne le mieux pour vous.
* Désormais, quand vous essayez d'exécuter une nouvelle instance de NVDA alors qu'une copie plus ancienne est en cours d'exécution, cela entraînera la fermeture de la nouvelle instance. Cela corrige un problème majeur où plusieurs instances de NVDA rendaient votre système très inutilisable.
* Remplacé le titre de l'interface utilisateur de NVDA par la mention NVDA.
* Correction d'un bogue dans Outlook Express où l'appui sur Retour-Arrière au début d'un message en cours d'édition provoquait une erreur.
* Ajout d'un correctif de Rui Batista qui comporte un script pour signaler l'état actuel de la batterie sur les ordinateurs portables (insert+maj+b).
* Ajout d'un pilote de synthétisation appelé Silence. Il s'agit d'un pilote de synthhétiseur qui ne parle pas du tout, ce qui permet de rendre NVDA complètement silencieux, tout le temps. Finalement, cela pourrait être utilisé avec le support Braille, quand nous aurons mis ce dernier en place.
* Ajout du réglage de la hauteur des majuscules pour synthèses vocales (capitalPitchChange) grâce à JJ Meddaugh
* Ajout d'un correctif de J.J. Meddaugh qui rend le script de basculement de l'annonce des objets sous la souris conforme aux autres scripts. NVDA annonce (activé / désactivé) plutôt que de changer toute la déclaration.
* Ajout de la traduction en espagnol (es), contribution de Juan C. Buño.
* Ajout du fichier de la langue hongroise par Tamas Gczy.
* Ajout du fichier pour la langue portugaise par Rui Batista.
* La modification de la voix dans le dialogue Paramètres vocaux définit maintenant les curseurs de débit, de tonalité et de volume aux nouvelles valeurs selon le synthétiseur, plutôt que de forcer ce dernier à prendre en compte les anciennes valeurs. Cela résout des problèmes où une synthèse vocale comme Eloquence ou viavoice tendaient à parler à un débit beaucoup plus rapide que toutes les autres synthèses.
* Correction d'un bogue où soit la parole s'arrêtait, soit NVDA cessait de fonctionner tout-à-fait, lorsque dans une fenêtre de console Dos.
* Si le support d'une telle langue existe, NVDA peut maintenant automatiquement afficher son interface et diffuser ses messages dans la langue définie par Windows. Une langue particulière peut toutefois être choisie manuellement depuis le dialogue Paramètres de l'interface utilisateur également.
* Ajout du script « toggleReportDynamicContentChanges » (insert+5). Cela détermine si le nouveau texte ou d'autres changements dynamiques doivent être automatiquement annoncés. Pour le moment, cela ne fonctionne que dans les fenêtres de Console Dos.
* Ajout du script « toggleCaretMovesReviewCursor » (insert+6). Cela détermine si le curseur de revue doit être automatiquement repositionné lorsque le curseur système se déplace. Ceci est utile dans les fenêtres de console Dos quand on essaie de lire les informations alors que l'écran est actualisé.
* Ajout du script « toggleFocusMovesNavigatorObject » (insert+7). Cela détermine si l'objet de navigation est repositionné sur l'objet ayant le focus lorsqu'il change.
* Ajout d'une documentation traduite en diverses langues. Jusqu'à présent, il y a le français, l'espagnol et le finnois.
* Suppression partielle de la documentation développeur de la distribution binaire de NVDA, elle se trouve maintenant dans la version source seulement.
* Correction d'un bogue possible dans Windows Live Messenger et MSN Messenger, quand l'appui sur flèches haut et bas dans la liste de contacts provoquait des erreurs.
* Les nouveaux messages sont maintenant lus automatiquement lors d'une conversation Windows Live Messenger. (fonctionne uniquement pour les versions anglaises jusqu'à présent)
* La fenêtre de l'historique d'une conversation Windows Live Messenger peut maintenant être lue en utilisant les touches fléchées. (Fonctionne uniquement pour les versions anglaises jusqu'à présent)
* Ajout du script 'passNextKeyThrough' (insert+f2). Appuyez sur cette touche, et la prochaine touche sera passée directement à Windows. Cela est utile si vous devez appuyer sur une touche dans une application mais que NVDA utilise cette touche pour autre chose.
* NVDA ne gèle plus pendant une minute ou plus à l'ouverture de très gros documents dans MS Word.
* Correction d'un bogue qui faisait que si on se déplaçait hors d'un tableau sous MS Word, et que l'on y revenait, le nombre de rangées ou de colonnes courantes n'étaient pas annoncé, même si on regagnait exactement la même cellule.
* Quand on lance NVDA en utilisant une synthèse vocale inexistante ou qui ne fonctionne pas, le moteur SAPI5 sera chargé. Si SAPI5 ne fonctionne pas non plus, alors la parole sera réglée sur silence.
* Les scripts d'augmentation ou de diminution de débit ne montent plus à plus de 100 et ne descendent plus à moins de 0.
* Si une erreur est détectée quand on choisit une langue via le dialogue Langue de l'interface utilisateur, NVDA alerte l'utilisateur à ce sujet.
* NVDA demande si la configuration doit être sauvegardée et s'il doit redémarrer lors du changement de langue sous le dialogue Langue de l'interface utilisateur. NVDA doit être relancé pour que les changements prennent effet.
* Lorsqu'un synthétiseur choisi par l'utilisateur ne peut pas être chargé à l'aide du dialogue Synthétiseur, NVDA affiche une alerte à cet effet.
* Lors du chargement d'un synthétiseur pour la première fois, NVDA lui permet de choisir les paramètres de voix, de débit et de hauteur les mieux adaptés, plutôt que de le forcer à appliquer des valeurs par défaut qu’il juge correctes. Cela corrige un problème où les synthétiseurs Eloquence et Viavoice sapi4 tendaient à parler trop vite de prime abord.
