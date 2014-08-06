Obtener colección de condiciones de venta
-----------------------------------------

* `GET /v1/sale_conditions.json` retornara todas las condiciones de venta.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso.
- *expand*, permite expandir instancias y colecciones.
- *timecondition*, permite filtrar por tiempo de la condicion de venta.
- *timeunity*, filtra por la unidad de tiempo.
- *state*, boolean (0 o 1) indica si las condiciones de venta estan activas(0) inactivas(1).

####Ejemplos

* `GET /v1/sale_conditions.json?limit=10&offset=0`
* `GET /v1/sale_conditions.json?fields=[name,ledgeraccount]`
* `GET /v1/sale_conditions.json?state=0`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/sale_conditions.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/sale_conditions/1.json",
      "id": 1,
      "name": "Al dia",
      "timeCondition": 7,
      "timeUnity": 0,
      "state": 0
    }
  ]
}
```
Obtener una condicion de venta
------------------------------

* `GET /v1/sale_conditions/1.json` retornara una condicion de venta específica.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/sale_conditions/1.json",
  "id": 1,
  "name": "Al dia",
  "timeCondition": 7,
  "timeUnity": 0,
  "state": 0
}```
Cantidad de condiciones de venta
--------------------------------

* `GET /v1/sale_conditions/count.json`
```json
{
  "count": 1
}
```