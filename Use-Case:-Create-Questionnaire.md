### Charakterisierende Informationen

<table>
    <tr>
        <th>Ziel des Use Cases </th>
        <td> ein neuer Fragebogen wurde erfolgreich angelegt </td>
    </tr>
    <tr>
        <th>Vorbedingung </th>
        <td>  </td>
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
        <td> es gibt eine LV oder eine Dozenten-Rolle, für die noch kein Fragebogen existiert </td>
    </tr>
</table>


### Szenario für den Standardablauf

| Schritt | Nutzer | Beschreibung der Aktivität |
|---------|--------|----------------------------|
| 1 | FSR | Eine Name für den Fragebogen wird eingegeben, optional auch eine Beschreibung des Fragebogens. |
| 2 | FSR | Neue Fragen können hinzugefügt und bestehende verändert oder entfernt werden. Hierbei wird auch festgelegt, um welchen Fragetyp(Noten- vs. Freitext-Frage) es sich jeweils handelt. |
| 3 | FSR | Fragebogen wird abschließend gespeichert. |
| 4 | FSR | Vorschau des Fragebogens soll angezeigt werden |


### Szenarien für alternative Abläufe

| Schritt | Bedingung für Alternative | Beschreibung der Aktivität |
|---------|---------------------------|----------------------------|
| 1 | Benutzer gibt keinen oder keinen eindeutigen Namen für den Fragebogen an. | Benutzer wird aufgefordert, einen eindeutigen Namen anzugeben. |
| 1 | Ein bestehender Fragebogen wird kopiert, dabei wird schritt 2 übersprungen. |
| 3 | Fragebogen enthält keine Fragen | Speichern des Fragebogens wird verhindert, Benutzer wird aufgefordert, Fragen hinzuzufügen. |
| 4 | Benutzer ist mit Fragebogen nicht zufrieden | Benutzer kann zu Schritt 3 zurück gehen. |
