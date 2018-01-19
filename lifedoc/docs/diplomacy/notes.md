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

## Randnotiz

* Maximal physisch vorhandene Einheiten eintragen und beachten

* * *

# 19.01.2018 Wegesnotizen

* Fotografie des seitlichen Profils der Spielfiguren zur digitalen Abbildung
* sich drehende Würfel --> bei Erhalt der Zufallszahl, Stop und Zahlen bezeihungsweise Summen anzeigen
* Kampfergebnis mit Sound- und Bild-/Animationsuntermalung
* Gebiete mit namen und abstand zu anderen gebieten --> neo4j