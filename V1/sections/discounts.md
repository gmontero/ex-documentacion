Obtener colección de descuentos
-------------------------------

* `GET /v1/discounts.json` retornara todos los descuentos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del descuento.
- *percentage*, filtra por porcentaje de descuento.
- *state*, boolean (0 o 1) indica si los descuentos estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/discounts.json?limit=10&offset=0`
* `GET /v1/discounts.json?fields=[name,percentage,state]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/discounts.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/discounts/1.json",
      "id": 1,
      "name": "Ajuste Precio",
      "percentage": "14.3",
      "state": 1,
      "automatic": 0
    },
    {
      "href": "http://api.bsale.cl/v1/discounts/3.json",
      "id": 3,
      "name": "Descuento CPT",
      "percentage": "75.0",
      "state": 0,
      "automatic": 0
    },
    {
      "href": "http://api.bsale.cl/v1/discounts/2.json",
      "id": 2,
      "name": "Descuento Imagestion",
      "percentage": "25.0",
      "state": 1,
      "automatic": 0
    }
  ]
}
```
Obtener una moneda
------------------

* `GET /v1/discounts/1.json` retornara un descuento específico.

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/discounts/1.json",
  "id": 1,
  "name": "Ajuste Precio",
  "percentage": "14.3",
  "state": 1,
  "automatic": 0
}
```
Cantidad de descuentos.
-----------------------------------

* `GET /v1/discounts/count.json`
```json
{
  "count": 3
}
```