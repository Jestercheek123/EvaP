
### Charakterisierende Informationen

<table>
    <tr>
        <th>Ziel des Use Cases </th>
        <td> Der Student soll die von ihm belegten LV bewerten können. </td>
    </tr>
    <tr>
        <th>Vorbedingung </th>
        <td> Evaluierungszeitraum hat allgemein und für die LV begonnen. Student hat die LV belegt. </td>
    </tr>
    <tr>
        <th>Nachbedingung </th>
        <td> Ziel des Use Cases wurde erreicht, Datenbank muss in konsistentem Zustand sein </td>
    </tr>
    <tr>
        <th>Beteiligte Nutzer </th>
        <td> Student </td>
    </tr>
    <tr>
        <th>Auslösendes Ereignis </th>
        <td> </td>
    </tr>
</table>


### Szenario für den Standardablauf 

| Schritt | Nutzer | Beschreibung der Aktivität |
|---------|--------|----------------------------|
| 1 | Student | Beantwortet jede allgemeine Frage für die LV sowie jede Dozentenfrage ein mal pro Dozent (min./max. ein Dozent muss bewertet werden?)  |
| 2 | Student | Bewertung der LV wird gespeichert (ohne Verbindung zum Studenten) und der Student wird als 'hat-gewählt' für die LV gespeichert |

### Szenarien für alternative Abläufe 

| Schritt | Bedingung für Alternative | Beschreibung der Aktivität |
|---------|---------------------------|----------------------------|
