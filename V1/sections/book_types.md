Obtener colección de tipos de libro
-----------------------------------

* `GET /v1/book_types.json` retornara todos los tipos de libro.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre tipo libro.
- *dteprocess*, filtra por proceso.
- *code*, filtra por codigo interno.
- *state*, boolean (0 o 1) indica si los tipos de libro estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/book_types.json?limit=10&offset=0`
* `GET /v1/book_types.json?fields=[name,code,state]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/book_types.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/book_types/3.json",
      "id": 3,
      "name": "Libro Boleta",
      "dteProcess": "Boleta",
      "code": "2",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/book_types/2.json",
      "id": 2,
      "name": "Libro Compra",
      "dteProcess": "Compra",
      "code": "1",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/book_types/1.json",
      "id": 1,
      "name": "Libro Venta",
      "dteProcess": "Venta",
      "code": "0",
      "state": 1
    }
  ]
}
```
Obtener un tipo de libro
------------------------

* `GET /v1/book_types/1.json` retornara un tipo de libro específico.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/book_types/1.json",
  "id": 1,
  "name": "Libro Venta",
  "dteProcess": "Venta",
  "code": "0",
  "state": 1
}
```
Cantidad de tipos de libro.
-----------------------------------

* `GET /v1/book_types/count.json`
```json
{
  "count": 3
}
```