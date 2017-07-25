Die DBForm ermöglicht den Zugriff auf die `Form_X` Tabellen der Datenbank. Diese gehört zu den Formulareingaben rund um LForm und DBChoice.

| Themen |
| :- |
| [Befehle/Eingänge (Commands.json)](#eingaenge) |
| [Ausgänge (Component.json => Links)](#ausgaenge) |
| [Anbindungen (Component.json => Connector)](#anbindungen) |

## <a name='eingaenge'></a>Befehle/Eingänge (Commands.json)
Diese Befehle bietet diese Komponente als Aufruf an.

|||
| :----------- |:----- |
|Beschreibung| installiert DBForm in diese Veranstaltung|
|Befehl| post /course|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| entfernt die Komponente aus der Veranstaltung|
|Befehl| delete /course(/course)/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ändert ein Formular|
|Befehl| put /form(/form)/:formid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| entfernt ein Formular|
|Befehl| delete /form(/form)/:formid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| speichert ein neues Formular|
|Befehl| post /form|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt ein einzelnes Formular|
|Befehl| get /form(/form)/:formid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Formulare einer Veranstaltung|
|Befehl| get /form/course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| prüft, ob die Komponente in diese Veranstaltung installiert wurde|
|Befehl| get /link/exists/course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Formulare einer Übungsserie|
|Befehl| get /form/exercisesheet/:esid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Formulare einer Aufgabe|
|Befehl| get /form/exercise/:eid|
|Eingabetyp| -|
|Ausgabetyp| -|


## <a name='ausgaenge'></a>Ausgänge (Component.json => Links)
Wenn eine Komponente selbst noch Unteranfragen an andere Komponenten stellen möchte, dann werden diese über die `Ausgänge` bearbeitet.
Dabei kann ein Ausgang bereits auf eine Komponente gerichtet sein (`Ziel`) oder durch die Zielkomponente selbst angebunden werden (`Connector`)

||out|
| :----------- |:----- |
|Ziel| DBQuery2|
|Befehl| POST /query|
|Beschreibung| Dieser Ausgang wird für diverse Anfragen verwendet.|


## <a name='anbindungen'></a>Anbindungen (Component.json => Connector)
Eine Anbindung verlangt von einer anderen Komponente (`Ziel`) die Anbindung/Verbindung zu dieser Komponente.
Wenn eine Anbindung den aufzurufenden Befehl vorgibt, dann ist die Notation: METHODE URL (PRIORITÄT).

|Ausgang|request|
| :----------- |:----- |
|Ziel| CLocalObjectRequest|
|Beschreibung| damit DBForm als lokales Objekt aufgerufen werden kann|


Stand 25.07.2017
