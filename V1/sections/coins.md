Obtener colección de monedas
----------------------------

* `GET /v1/coins.json` retornara todas las monedas.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre de la moneda.
- *symbol*, filtra por simbolo de la moneda.
- *state*, boolean (0 o 1) indica si las monedas estan activas(0) inactivas(1).

####Ejemplos

* `GET /v1/coins.json?limit=10&offset=0`
* `GET /v1/coins.json?fields=[name,symbol,state]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/coins.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/coins/3.json",
      "id": 3,
      "name": "Dolar",
      "symbol": "USD",
      "decimals": 2,
      "totalRound": 0
    },
    {
      "href": "http://api.bsale.cl/v1/coins/1.json",
      "id": 1,
      "name": "Peso Chileno",
      "symbol": "$",
      "decimals": 0,
      "totalRound": 0
    },
    {
      "href": "http://api.bsale.cl/v1/coins/2.json",
      "id": 2,
      "name": "UF",
      "symbol": "(UF)",
      "decimals": 2,
      "totalRound": 0
    }
  ]
}
```
Obtener una moneda
------------------

* `GET /v1/coins/1.json` retornara una moneda específica.

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/coins/1.json",
  "id": 1,
  "name": "Peso Chileno",
  "symbol": "$",
  "decimals": 0,
  "totalRound": 0
}
```
Cantidad de monedas.
-----------------------------------

* `GET /v1/coins/count.json`
```json
{
  "count": 3
}
```