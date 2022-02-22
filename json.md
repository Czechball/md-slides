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
*Součást [md-slides na GitHubu](https://github.com/Czechball/md-slides)*

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

* Nativní
* Jednoduchý parsing
* `JSON.parse()`
* `JSON.stringify()`

----

## Příklad

* Fetchování JSON z url a načtení lokálně přes async request
```js
async function zobrazit() {
      const requesturl = 'https://example.com/neco.json';
      const request = new Request(requesturl);
      const response = await fetch(request);
      const data = await response.json();
    }
````

----

## Příklad

`json.zonc.eu/examples/zelenina.html`  
<img src=files/qrcode_json.zonc.eu.png width=30%></img> 

---

## Využití v PHP

* `json_decode`
* Objekty, arraye

----

## Příklad

*Získání dat*
```php
$stmt = $dbHandle->prepare($sql);
```

*Vytvoření arraye*
```php
$data = get_all($dbHandle, $db_table);
```

*Dump JSON objektu*
```php
echo json_encode($data, JSON_FORCE_OBJECT);
```

----

## Ukázkový kód

* [json-prezentace](https://github.com/Czechball/json-prezentace/blob/main/examples/fetch_data.php)

---

## Využití v PHP + JS

* Možnosti využití AJAXu
* Post requesty
* API?

----

## Příklad

```js
var xmlhttp = new XMLHttpRequest();
        xmlhttp.open("POST", "fetch_data.php", true);
        xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
        xmlhttp.onreadystatechange = function() {
            if (this.readyState === 4 || this.status === 200){ 
              let jsObject = JSON.parse(this.response);
              console.log(jsObject);
            }       
        };
        xmlhttp.send("db_table=" + qs["db_table"]);
```

---

## Samostatná práce

* Dokončení mého hrozného kódu
* Možnost kombinace `zelenina.html` a PHP části
* W3Schools, StackOverflow, Twitter...

---

# Děkuji za pozornost

*Prezentace: reveal-md*