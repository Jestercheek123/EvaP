### Charakterisierende Informationen 

<table>
    <tr>
        <th>Ziel des Use Cases </th>
        <td> Information zu einer Lehrveranstaltung sind korrekt und vollständig im System vorhanden (Name und Art der Lehrveranstaltung, Betreuer (Name, Tiel, Foto?) und deren jeweilige Rollen [Dozent, Seminarleiter, Übungsleiter, Projektbetreuer, etc.]) </td>
    </tr>
    <tr>
        <th>Vorbedingung </th>
        <td> Import der Lehrveranstaltungen wurde erfolgreich durchgeführt, LA hat sich eingeloggt </td>
    </tr>
    <tr>
        <th>Nachbedingung </th>
        <td> Die Informationen der Lehrveranstaltung sind aktuell, korrekt und vollständig.</td>
    </tr>
    <tr>
        <th>Beteiligte Nutzer </th>
        <td> Dozenten der LV und deren Stellvertreter, FSR </td>
    </tr>
    <tr>
        <th>Auslösendes Ereignis </th>
        <td>  </td>
    </tr>
</table>


### Szenario für den Standardablauf 

| Schritt | Nutzer | Beschreibung der Aktivität |
|---------|--------|----------------------------|
| 1 | Lehrbereichs-Admin | prüft und ändert ggf. den Namen der Lehrveranstaltung |
| 2 | Lehrbereichs-Admin | prüft und ändert ggf. die Art der Lehrveranstaltung |
| 3 | Lehrbereichs-Admin | prüft und passt ggf. den Evaluierungszeitraum an (welche constraints?) |
| 4 | Lehrbereichs-Admin | prüft und ergänzt Dozenten/Betreuer und weist diesen zusätzliche Fragebögen zu |


### Szenarien für alternative Abläufe 

| Schritt | Bedingung für Alternative | Beschreibung der Aktivität |
|---------|---------------------------|----------------------------|
| 4 | Konsistenzbedingungen wurden nicht eingehalten (z. B. zu jeder Vorlesung muss mind. einmal der Dozenten-Fragebogen zugewiesen werden) | Speichern nicht möglich, zurück zu Schritt 2 |

### Ergänzende Einschränkungen 

* Evaluierungszeitraum sollte eine Mindestdauer von einer Woche haben
* Evaluierungszeitraum muss vor der Prüfung liegen
* der FSR muss ebenfalls die Lehrveranstaltungs-Infos ändern können, für den Fall, dass die Dozenten die Informationen nicht selbst eintragen bzw. dem FSR die Informationen nur per Mail zukommen lassen. Damit ist gewährleistet, dass der Evaluierungsprozess selbst bei mangelnder Kooperationsbereitschaft durchgeführt werden kann.