Die DBChoice ermöglicht den Zugriff auf die `Choice_X` Tabellen der Datenbank. Diese gehört zu den Formulareingaben rund um LForm und DBForm.

| Themen |
| :- |
| [Befehle/Eingänge (Commands.json)](#eingaenge) |
| [Ausgänge (Component.json => Links)](#ausgaenge) |
| [Anbindungen (Component.json => Connector)](#anbindungen) |

## <a name='eingaenge'></a>Befehle/Eingänge (Commands.json)
Diese Befehle bietet diese Komponente als Aufruf an.

|||
| :----------- |:----- |
|Beschreibung| installiert DBChoice in diese Veranstaltung|
|Befehl| post (/:preChoice(/:preForm(/:preExercise)))/course|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| entfernt die Komponente aus der Veranstaltung|
|Befehl| delete (/:preChoice(/:preForm(/:preExercise)))/course(/course)/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ändert eine Antwortmöglichkeit|
|Befehl| put (/:preChoice(/:preForm(/:preExercise)))/choice(/choice)/:choiceid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| entfernt eine Antwortmöglichkeit|
|Befehl| delete (/:preChoice(/:preForm(/:preExercise)))/choice(/choice)/:choiceid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| speichert eine neue Antwortmöglichkeit|
|Befehl| post (/:preChoice(/:preForm(/:preExercise)))/choice|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt eine einzelne Antwortmöglichkeit|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/choice(/choice)/:choiceid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Antwortmöglichkeiten einer Veranstaltung|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/choice/course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| prüft, ob die Komponente in diese Veranstaltung installiert wurde|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/link/exists/course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Antwortmöglichkeiten einer Übungsserie|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/choice/exercisesheet/:esid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Antwortmöglichkeiten einer Aufgabe|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/choice/exercise/:eid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| ermittelt alle Antwortmöglichkeiten eines Formulars|
|Befehl| get (/:preChoice(/:preForm(/:preExercise)))/choice/form/:formid|
|Eingabetyp| -|
|Ausgabetyp| -|


## <a name='ausgaenge'></a>Ausgänge (Component.json => Links)
Wenn eine Komponente selbst noch Unteranfragen an anderen Komponenten stellen möchte, dann werden diese über die `Ausgänge` bearbeitet.
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
|Beschreibung| damit DBChoice als lokales Objekt aufgerufen werden kann|


Stand 25.07.2017
