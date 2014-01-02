### Charakterisierende Informationen

<table>
    <tr>
        <th>Ziel des Use Cases </th>
        <td> Im Evaluierungssystem sollen für das aktuelle Semester folgende Daten vorhanden sein: Die Lehrveranstaltungen, die dazugehörigen hauptverantwortlichen Dozenten, sowie die Studierenden und die dazugehörigen Belegungen. </td>
    </tr>
    <tr>
        <th>Vorbedingung </th>
        <td> Studienreferat hat die Belegungsdaten des aktuellen Semesters als Excel-Sheet exportiert und dem FSR zugesandt </td>
    </tr>
    <tr>
        <th>Nachbedingung </th>
        <td> Ziel des Use Cases wurde erreicht, Datenbank muss in konsistentem Zustand sein </td>
    </tr>
    <tr>
        <th>Beteiligte Nutzer </th>
        <td> Fachschaftsrat </td>
    </tr>
    <tr>
        <th>Auslösendes Ereignis </th>
        <td> Universitätsverwaltung hat die Belegungsdaten an den FSR geschickt </td>
    </tr>
</table>

### Szenario für den Standardablauf

| Schritt | Nutzer | Beschreibung der Aktivität |
|---------|--------|----------------------------|
| 1 | FSR | gibt Name der Evaluierungsperiode (z. B. WS 2011/12) und Standard-Evaluierungszeitraum an |
| 2 | FSR | Excel-Datei wird per Webformular im Adminbereich in das Evaluierungssystem geladen |
| 3 | FSR | Zusammenfassende Statistik des Imports wird geprüft (Anzahl der importierten Lehrveranstaltungen, Dozenten, Studierenden, Belegungen) |

### Szenarien für alternative Abläufe

| Schritt | Bedingung für Alternative | Beschreibung der Aktivität |
|---------|---------------------------|----------------------------|
| 2 | wenigstens ein Datensatz des Excel-Sheets ist fehlerhaft | fehlerhafte Datensätze werden angezeigt, diese können einzeln korrigiert werden; der Import kann optional vom FSR als Ganzes abgebrochen werden, in diesem Fall befindet sich die Datenbank im selben Zustand wie vor dem Import |