Entity Modell
==

###Analyse
Das system benötigt keine Datenbank, da Node eine einzelne Instanz ist und Daten zwischen jede einzelne requests sepichern kann. Node wird verwendet um die WebView herrunter zu laden und um eine realtime Verbindung zu erstellen mit WebSockets.
Die benutzer die auf das DBMS erstellt werden sind Kellner (schreib + leserechte), Admin (alles) und Koch (nur leserechte).
Auf dem Haubtcomputer (server) werden alle Produkte eingegeben und gespeichert (in einer JSON-Datei). Performance ist sehr wichtig, deshalb werden alle vollendete Bestellungen in "Log_Tabellen" gegeben.


###Annahmen
*keine*

###Tabellen
*Alle tabelle haben ein **primary_key** namens id*
- **Produkte:** Name, Kategorie, Preis
- **Extras:** Name, Preis
- **Tische:** Name, Gridpos 
- **Kategorien:** Name
- **Status:** Name, Description

####Zwischentabellen (M - N) und Schwache Enthitäten
- Produkt - Extras
- **Bestellungen:** Tisch_id, Produkte_id, Datum, Status

####History
- Log_Bestellungen
- Log_Tisch
- Log_Produkte_id
- Log_Extra

####Er-Modell
![Visual Rappresentation of the DB][logo]

[logo]: https://raw.githubusercontent.com/DoneProject/StatusBoard/master/imgs/er.png
