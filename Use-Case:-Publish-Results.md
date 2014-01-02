### Charakterisierende Informationen 

<table>
    <tr>
        <th>Ziel des Use Cases </th>
        <td> Die Ergebnisse der Evaluierungsperiode sind online einsehbar. </td>
    </tr>
    <tr>
        <th>Vorbedingung </th>
        <td> Evaluierungszeiträume (fast) aller Lehrveranstaltungen sind abgelaufen (siehe Hinweis in SichtbarkeitErgebnisse) sowie die Prüfungsergebnisse veröffentlicht, alle betreffenden Lehrveranstaltungen haben den [[Use Case: Review Comments]] durchlaufen </td>
    </tr>
    <tr>
        <th>Nachbedingung </th>
        <td> siehe Ziel des Use Cases </td>
    </tr>
    <tr>
        <th>Beteiligte Nutzer </th>
        <td> Fachschaftsrat, Betreuer </td>
    </tr>
    <tr>
        <th>Auslösendes Ereignis </th>
        <td> die letzten Prüfungsergebnisse wurden veröffentlicht </td>
    </tr>
</table>

### Szenario für den Standardablauf 

|_.Schritt |_.Nutzer |_.Beschreibung der Aktivität |
|----------|---------|-----------------------------|
| 1 | FSR | ruft Liste aller evaluierten Lehrveranstaltungen auf |
| 2 | FSR | wählt die zu veröffentlichenden Lehrveranstaltungen aus, mit einem Klick können alle LV auf einmal ausgewählt werden |
| 3 | FSR | bestätigt die zu veröffentlichenden Lehrveranstaltungen |
| 4 | FSR | erhält kurze Bestätigung (z.B. "zehn von 35 LVs veröffentlicht") |
| (5*) | Betreuer | erhält automatisch eine Benachrichtigungsmail, in der er über die Veröffentlichung seiner Veranstaltungen informiert wird |

* = nice to have

### Szenarien für alternative Abläufe 

| Schritt | Bedingung für Alternative | Beschreibung der Aktivität |
|---------|---------------------------|----------------------------|
### Ergänzende Einschränkungen 

* Lehrveranstaltungen können nur dann veröffentlicht werden, wenn eine bestimmte Anzahl von Bewertungen abgegeben wurde. (analog zu der in SichtbarkeitErgebnisse beschriebenen)


### Sichtbarkeit der Ergebnisse

Nachdem alle Lehrveranstaltungen evaluiert wurden, müssen die Ergebnisse noch veröffentlicht werden.

Dabei sind alle Notenbewertungen für alle angemeldeten Benutzer einsehbar. Jeder Betreuer kann seine persönliche Bewertung (Noten und Kommentare) der von ihm betreuten Lehrveranstaltungen sowie die lehrveranstaltungsbezogenen Bewertungen einsehen. Der Hauptverantwortliche kann die Noten und Kommentare aller Lehrveranstaltungen seines Lehrbereiches einsehen. Darunter fallen auch die Bewertungen der Betreuer, damit er sich ein Bild von den einzelnen Leistungen machen kann. Die Geschäftsführung kann die komplette Bewertung aller Lehrveranstaltungen einsehen.

Um in ausreichendem Maße Anonymität zu gewährleisten, gibt es allerdings die Beschränkung, dass die Antworten auf eine Kommentar(?)frage nur dann veröffentlicht werden dürfen, wenn eine festgelegte Anzahl dafür existiert. Diese Anzahl ist für alle Lehrveranstaltungen gleich. Zensierte (sprich: verborgene) Kommentare zählen nicht in die Anzahl mit hinein. Die kritische Anzahl muss außerdem konfigurierbar sein.

Bei der Veröffentlichung ist zu beachten, dass diese erst dann geschehen sollte, wenn die Prüfungsergebnisse in allen Lehrveranstaltungen veröffentlicht wurden. In einzelnen Lehrveranstaltungen kann es allerdings passieren, dass die Prüfungstermine bzw. die Bekanntgabe der Prüfungsergebnisse erst sehr spät stattfinden, mitunter erst im neuen Semester oder gar noch später. Diese werden dann zunächst nicht veröffentlicht, vielmehr wird die Veröffentlichung hier für die betreffenden Lehrveranstaltungen nachgereicht.
