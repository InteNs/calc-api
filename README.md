# we gaan een rekenmachine API maken!


hier zijn de regels:
-----

je maakt een berekening aan door een POST request te maken naar `/calculations`

dit is de json:
```json
{
  "value_a":  5,
  "value_b":  5,
  "operator": "*"
}
```
de `operator` kan een van de volgende waardes zijn: `["*", "+", "-", "/"]`

er moet validatie zijn op het correct zijn van de berekening:
- missende `value_a`, `value_b` of `operator`
- bij een correcte berekening die niet kan worden uitgevoerd wordt het resultaat `nil`

alle calculations moeten worden opgeslagen zodat je een geschiedenis kan bekijken

- gesorteerd op de aanmaak datum

```
GET    /calculations
GET    /calculations/:id
DELETE /calculations/:id
POST   /calculations
```

de json response moet natuurlijk de uitkomst van de berekening bevatten:

```json
{
  "value_a":  5,
  "value_b":  5,
  "operator": "*",
  "result":   25
}
```

extras:
-----

je moet alleen calucations die de laatste 5 minuten zijn aangemaakt ophalen:
(via scopes)

```
GET /calculations/today
```

maak unit en request specs (met factories) voor je code!
