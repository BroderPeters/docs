# 14.01.2018 - Notizen
* Provinzfaktor (aktuell: 1,4 pro Provinz)
* Hauptstädte, Weltwunder = + 0,6
	* Provinz mit Hauptstadt **und** Weltwunder = 1,4 + 0,6 + 0,6
* 2/3 Provinzen eines Landes um dieses einzunehmen
* Ereignisse: Beschreibung, Auswirkung in Form von +/- Gold, +/- Einheiten
* Weltereignisse (am Ende jeder vollen Runde): Beschreibung, Typ, Auswirkung in Form von +/- Gold, +/- Einheiten oder anderen für alle oder bestimmte Nationen
* Zufallswürfel implementieren
* Einheiten können zu jedem Zeitpunkt verkauft werden
* Maximal drei Einheiten in einer Provinz/Schiff
* Kampf gegen neutrale Provinz = (Stärke) n:2
* Kampf gegen Spieler = n:m
* Kein Heimvorteil (Kampf ein eigenem Land/eigener Provinz)
* Handel unter Spielern um Einheiten, Provinzen
* Gold leihen unter Spielern mit Bedingungen
* feste Runden-/Zugzeit

## Einheitenübersicht
<table>
    <tr>
		<th>Einheitentyp</th>
		<th>Kosten</th>
		<th>Stärke</th>
		<th>Reichweite</th>
	</tr>
	<tr>
        <td>Infanterie</td>
		<td>9</td>
		<td>1</td>
		<td>2</td>
    </tr>
	<tr>
        <td>Kavallerie</td>
		<td>13</td>
		<td>2</td>
		<td>3</td>
    </tr>
	<tr>
        <td>Artillerie</td>
		<td>16</td>
		<td>3</td>
		<td>1</td>
    </tr>
	<tr>
        <td>Schiff</td>
		<td>29</td>
		<td>1</td>
		<td>1 Faden</td>
    </tr>
</table>

## Eindrücke

![IMG-20180114-WA0002.jpg](/images/IMG-20180114-WA0002.jpg)
![IMG-20180114-WA0004.jpg](/images/IMG-20180114-WA0004.jpg)
*Die Animation mit dem Titel "Geilste Front ever" musste aufgrund der Dateigröße entfernt werden.*

## ER-Modell
![ERModel_20180114.png](/images/ERModel_20180114.png "Skizziertes ER-Modell")

##Brainstorm
* Logging der Geschehnisse in Spielzügen
* Einheiten können zu jedem Zeitpunkt verkauft werden (Popup/Benachrichtigung für Spielleiter)
* Android/iOS-App
* Browserbasiert
* Message Broker
* Datenbank
* Einplatinencomputer als Host mit lokalem Netzwerk

* * *

# 15.01.2018 - Wegesnotizen

* Plattformunabhängig = webbasiert, lokal
* Spielstand und initiale Spielkonfiguration müssen geladen werden können
* Login für Spieler durch von Spieleleiter generiertem Passwort
* dynamisches und manuelles Update der angezeigten Übersicht
* Statistiken eines Spiels sammeln, eventuell an cloud.broderpeters.de für alle Spiele

* * *

# 16.01.2018 - Wegesnotizen

## Automatisierung im Vergleich zum physischen Spielerlebnis

* Gold auszahlen und abrechnen
* Kampfsimulation,  n:m: Vergleich der Summe von n zufallsgenerierten Zahlen mit der Summe von m zufallsgenerierten Zahlen

## Spielleiter

* Startet und ?beendet? eine Runde (Spieler hat dennoch Zugzeit x, welche vom Spielleiter festgelegt wird

## Randnotizen

* Maximal physisch vorhandene Einheiten eintragen und beachten

* * *

# 19.01.2018 - Wegesnotizen

* Fotografie des seitlichen Profils der Spielfiguren zur digitalen Abbildung
* sich drehende Würfel --> bei Erhalt der Zufallszahl, Stop und Zahlen bezeihungsweise Summen anzeigen
* Kampfergebnis mit Sound- und Bild-/Animationsuntermalung
* Provinzen mit Namen und Abstand zu anderen Provinzen --> neo4j?

# 19.01.2018 - Notizen

##Zugablauf
1. *manuell*: Zugstart nach Freigabe durch Spielleiter
2. *automatisch*: Kostenkalkulation
	1. Kalkulation der Steuern anhand der Provinzen, Haupstädte und Weltwunder
	2. Abzug offener Schulden
	3. Auszahlung
3. *manuell*: Kauf von Einheiten
	1. Prüfung, ob und wie viele Einheiten gekauft werden können
	2. Auswahl zu kaufender Einheiten
		1. Hintergrundberechnung mit aktuellem Vermögen, ob und wie viele Einheiten gekauft werden können
	3. Zusammenfassung ausgewählter Einheiten und Kosten
	4. Kaufbestätigung
	5. Einzahlung
	6. Mitteilung an den Spielleiter
	7. Setzen der gekauften Einheiten auf das Spielfeld
		1. Prüfen des Zielfeldes auf maximale Einheiten
4. *manuell*: Verkauf von Einheiten
	1. Auflistung vorhandener Einheiten
	2. Auswahl zu verkaufender Einheiten
	3. Zusammenfassung ausgewählter Einheiten und Kosten
	4. Verkaufsbestätigung
	5. Auszahlung
	6. Mitteilung an den Spielleiter
	7. Entfernen der verkauften Einheiten vom Spielfeld
5. *manuell*: Bewegen von Einheiten
	1. Übersicht aller möglich zu bewegenden Einheiten
	2. Auswahl der zu bewegenden Einheit(en)
	3. Auswahl des Zielfeldes
		1. Prüfen, ob Zielfeld gültigen Reichweite einhält
		2. Prüfen des Zielfelde auf maximale Einheiten
	4. Bestätigung durch den Spieler
	5. Bewegen der Einheit(en)
	6. Bestätigung durch den Spielleiter
	7. Prüfung, ob auf Zielfeld gekämpft werden kann
	8. Zusammenfassung der möglichen Kampfsituation (Kampfkraftverhältnis)
	9. Bestätigung durch den Spieler, ob auf Zielfeld gekämpft werden soll
	10. Kampfsimulation
	11. Auswertung der Kampfsimulation
		1. Mitteilung an den Spielleiter
	12. Entfernen besiegter Einheiten
	13. Zuordnung/Entfernen neuer Provinz
	14. Bestätigung durch den Spieler
	15. Bestätigung durch den Spielleiter
6. *manuell*: Optionales Ziehen einer Ereigniskarte
	1. Auswertung der Ereigniskarte
	2. Bestätigung durch den Spieler
7. *automatisch*: Beenden der Runde durch Erreichen der letzten Aktion oder Ablauf der Zugzeit

## ER-Modell
![ERModel_20170120.png](/images/ERModel_20170120.png "Skizziertes ER-Modell")

## Randnotizen

* Spielerreihenfolge wird durch Spielleiter festgelegt
* Spieler können Einheiten nur in ihrem Zug und nur nach dem Kauf von Einheiten und vor der Bewegung von Einheiten verkaufen
* Farbe des Spielers in Ecke einblenden
* Anstatt Schulden --> Gold auch in Minusbereich
* Maximale Einheiten pro Provinz --> Konfigurierbar