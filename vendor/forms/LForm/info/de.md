LForm ist die übergeordnete Komponente von DBForm und DBChoice und gehört zu den Komponenten der Eingabeformulare.

| Themen |
| :- |
| [Befehle/Eingänge (Commands.json)](#eingaenge) |
| [Ausgänge (Component.json => Links)](#ausgaenge) |
| [Anbindungen (Component.json => Connector)](#anbindungen) |

## <a name='eingaenge'></a>Befehle/Eingänge (Commands.json)
Diese Befehle bietet diese Komponente als Aufruf an.

|||
| :----------- |:----- |
|Beschreibung| speichert bzw. ändert ein Form-Objekt|
|Befehl| post /form|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| installiert die Komponente in die Veranstaltung|
|Befehl| post /course|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| entfernt die Komponente aus der Veranstaltung|
|Befehl| delete /course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|

|||
| :----------- |:----- |
|Beschreibung| prüft, ob die Komponente in dieser Veranstaltung installiert ist|
|Befehl| get /link/exists/course/:courseid|
|Eingabetyp| -|
|Ausgabetyp| -|


## <a name='ausgaenge'></a>Ausgänge (Component.json => Links)
Wenn eine Komponente selbst noch Unteranfragen an andere Komponenten stellen möchte, dann werden diese über die `Ausgänge` bearbeitet.
Dabei kann ein Ausgang bereits auf eine Komponente gerichtet sein (`Ziel`) oder durch die Zielkomponente selbst angebunden werden (`Connector`)

||form|
| :----------- |:----- |
|Ziel| DBForm|
|Befehl| POST /form|
|Beschreibung| zum Erstellen, Ändern und Löschen von Form-Einträgen|

||form|
| :----------- |:----- |
|Ziel| DBForm|
|Befehl| PUT /form/:formid|
|Beschreibung| zum Erstellen, Ändern und Löschen von Form-Einträgen|

||form|
| :----------- |:----- |
|Ziel| DBForm|
|Befehl| DELETE /form/:formid|
|Beschreibung| zum Erstellen, Ändern und Löschen von Form-Einträgen|

||choice|
| :----------- |:----- |
|Ziel| DBChoice|
|Befehl| POST /choice|
|Beschreibung| zum Erstellen und Ändern von Choice-Einträgen|

||choice|
| :----------- |:----- |
|Ziel| DBChoice|
|Befehl| PUT /choice/:choiceid|
|Beschreibung| zum Erstellen und Ändern von Choice-Einträgen|

||postCourse|
| :----------- |:----- |
|Ziel| DBForm,DBChoice|
|Befehl| GET /link/exists/course/:courseid|
|Beschreibung| Wenn auch andere Komponenten beim Erstellen einer Veranstaltung aufgerufen werden wollen, dann können sie sich an diesen Ausgäng hängen.|

||postCourse|
| :----------- |:----- |
|Ziel| DBForm,DBChoice|
|Befehl| POST /course|
|Beschreibung| Wenn auch andere Komponenten beim Erstellen einer Veranstaltung aufgerufen werden wollen, dann können sie sich an diesen Ausgäng hängen.|

||postCourse|
| :----------- |:----- |
|Ziel| DBForm,DBChoice|
|Befehl| DELETE /course/:courseid|
|Beschreibung| Wenn auch andere Komponenten beim Erstellen einer Veranstaltung aufgerufen werden wollen, dann können sie sich an diesen Ausgäng hängen.|


## <a name='anbindungen'></a>Anbindungen (Component.json => Connector)
Eine Anbindung verlangt von einer anderen Komponente (`Ziel`) die Anbindung/Verbindung zu dieser Komponente.
Wenn eine Anbindung den aufzurufenden Befehl vorgibt, dann ist die Notation: METHODE URL (PRIORITÄT).

|Ausgang|extension|
| :----------- |:----- |
|Ziel| LExtension|
|Beschreibung| wir wollen als Veranstaltungserweiterung installierbar sein (in der Kursverwaltung kann LForm dann ausgewählt werden)|

|Ausgang|request|
| :----------- |:----- |
|Ziel| CLocalObjectRequest|
|Beschreibung| damit LForm als lokales Objekt aufgerufen werden kann|

|Ausgang|request|
| :----------- |:----- |
|Ziel| CHelp|
|Beschreibung| hier werden Hilfedateien beim zentralen Hilfesystem angemeldet, sodass sie über ihre globale Adresse abgerufen werden können|
|| GET /help/:language/extension/LForm/LForm.md|
|| GET /help/:language/extension/LForm/LFormA.png|
|| GET /help/:language/extension/LForm/LFormB.png|


Stand 25.07.2017
