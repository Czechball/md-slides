---
title: JSON
theme: black
revealOptions:
  transition: 'slide'
---

# JSON  
*JavaScript Object Notation*  
```json
{
    "prezentace": "json",
    "délka": 99,
    "bloat": null
}
```

----

## Přístup k materiálům

### Prezentace
`slides.zonc.eu/json.html`  
<img src=files/qrcode_slides.zonc.eu.png width=30%></img> 

----

### Příklady
`github.com/Czechball/json-prezentace`
<img src=files/qrcode_json-priklady.png width=30%></img>

---

## Co je to JSON

* Oteřený standard formátu souborů a pro výměnu dat
* Objektový zápis
* Libovolná datová struktura, typy
  * int, string, bool
    * objekty, pole

---

## Využití JSONu

* Weby
* Konfigurace
* Databáze
  * MongoDB

----

## MongoDB

* NoSQL
* Document-oriented
* Kolekce > obsahují dokumenty (json soubory)
* Flexibilita (tvoření schématu on-the-go), škálovatelnost

---

## Datová struktura

* Klíče vždy v úvozovkách - `{"klíč":..}`
* Řetězec
  * Hodnota v `""` = string  
```json
{"jmeno":"Pavel"}
```
* Číslo
```json
{"cena":50}
```
* Bool
```json
{"radost":false}
```

----

## Datová struktura II

### Speciální typy

* Null (žádná hodnota)
```json
{"hodnota":null}
```

### Struktura

* Objekty (příklad jednoho objektu)
  * Veškeré objekty použité jako hodnoty musí následovat JSON syntax
```json
{
"pc":{"os":"GNU", "cena":20, "typ":"dell"}
}
```

----

## Datová struktura III

* Arraye
  * Možné i blokové formátování

```json
{
    "znacky":
    [
        "HP",
        "Lenovo",
        "Asus"
    ]
}
```

---

## JSON schéma

* "Template" pro JSON
  * Definují se datové typy

*Schéma*  
```json
{
  "type": "object",
  "properties": {
    "model": { "type": "string"},
    "pamet": { "type": "number" },
    "datum_vyroby": { "type": "string", "format": "date" },
    "podpora_5g": { "type": "boolean" }
  }
}
```

----

*JSON*
```json
{
  "model": "LG-D855",
  "pamet": 2,
  "datum_vyroby": "2014-06-00",
  "podpora_5g": false
}
```

---

## Využití v JavaScriptu

----

## Příklad

---

## Využití v PHP

----

## Příklad

---

## Využití v PHP + JS

----

## Příklad