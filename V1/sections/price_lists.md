Obtener colección de listas de precio
-------------------------------------

* `GET /v1/price_lists.json` retornara todas las listas de precio.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre de la lista de precio.
- *coinid*, filtra por la moneda.
- *state*, boolean (0 o 1) indica si las listas de precio estan activas(0) inactivas (1).

####Ejemplos

* `GET /v1/price_lists.json?limit=10&offset=0`
* `GET /v1/price_lists.json?fields=[name,description,state]`
* `GET /v1/price_lists.json?coinid=1`
* `GET /v1/price_lists.json?expand=[coin,details]`

####Respuesta
```json
{
  "href": "https://localhost:9292/v1/price_lists.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://localhost:9292/v1/price_lists/1.json",
      "id": "1",
      "name": "Lista Base",
      "description": "",
      "state": 0,
      "coin": {
        "href": "https://localhost:9292/v1/coins/1.json",
        "id": "1"
      },
      "details": {
        "href": "https://localhost:9292/v1/price_lists/1/details.json"
      }
    },
    {
      "href": "https://localhost:9292/v1/price_lists/2.json",
      "id": "2",
      "name": "Lista UF",
      "description": "",
      "state": 0,
      "coin": {
        "href": "https://localhost:9292/v1/coins/2.json",
        "id": "2"
      },
      "details": {
        "href": "https://localhost:9292/v1/price_lists/2/details.json"
      }
    },
    {
      "href": "https://localhost:9292/v1/price_lists/3.json",
      "id": "3",
      "name": "LISTA USD",
      "description": null,
      "state": 0,
      "coin": {
        "href": "https://localhost:9292/v1/coins/3.json",
        "id": "3"
      },
      "details": {
        "href": "https://localhost:9292/v1/price_lists/3/details.json"
      }
    }
  ]
}
```
Obtener una lista de precio
---------------------------

* `GET /v1/price_lists/3.json` retornara un cliente específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/price_lists/3.json?expand=[details, coin]`

####Respuesta
```json
{
  "href": "https://localhost:9292/v1/price_lists/3.json",
  "id": "3",
  "name": "LISTA USD",
  "description": null,
  "state": 0,
  "coin": {
    "href": "https://localhost:9292/v1/coins/3.json",
    "id": "3"
  },
  "details": {
    "href": "https://localhost:9292/v1/price_lists/3/details.json"
  }
}
```
Obtener detalles de una lista de precio
---------------------------------------

* `GET /v1/price_lists/3/details.json`
```json
{
  "href": "https://localhost:9292/v1/price_lists/3/details.json",
  "count": 114,
  "limit": 4,
  "offset": 0,
  "items": [
    {
      "href": "https://localhost:9292/v1/price_lists/3/details/349.json",
      "id": 349,
      "priceListId": 3,
      "variantId": 149,
      "variantValue": "1.0"
    },
    {
      "href": "https://localhost:9292/v1/price_lists/3/details/350.json",
      "id": 350,
      "priceListId": 3,
      "variantId": 83,
      "variantValue": "1.0"
    },
    {
      "href": "https://localhost:9292/v1/price_lists/3/details/351.json",
      "id": 351,
      "priceListId": 3,
      "variantId": 78,
      "variantValue": "1.0"
    },
    {
      "href": "https://localhost:9292/v1/price_lists/3/details/352.json",
      "id": 352,
      "priceListId": 3,
      "variantId": 169,
      "variantValue": "50.0"
    }
  ],
  "next": "https://localhost:9292/v1/price_lists/3/details.json?limit=25\u0026offset=25"
}
```
Obtener un de detelle de una lista de precio
--------------------------------------------

* `GET /v1/price_lists/3/details/349.json`
```json
{
  "href": "https://localhost:9292/v1/price_lists/3/details/349.json",
  "id": 349,
  "priceListId": 3,
  "variantId": 149,
  "variantValue": "1.0"
}
```
Cantidad de clientes.
-----------------------------

* `GET /v1/price_lists/count.json`
```json
{
  "count": 3
}
```