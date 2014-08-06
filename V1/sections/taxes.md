Obtener colección de impuestos
------------------------------

* `GET /v1/taxes.json` retornara todos los impuestos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del impuesto.
- *percentage*, filtra por porcentaje de impuesto.
- *code*, filtra codigo.
- *ledgeraccount*, filtra por cuenta contable.
- *state*, boolean (0 o 1) indica si los impuestos estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/taxes.json?limit=10&offset=0`
* `GET /v1/taxes.json?fields=[name,percentage,state]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/taxes.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/taxes/2.json",
      "id": 2,
      "name": "Exento",
      "percentage": "0.0",
      "forAllProducts": 1,
      "ledgerAccount": null,
      "code": "0",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/taxes/1.json",
      "id": 1,
      "name": "IVA",
      "percentage": "19.0",
      "forAllProducts": 0,
      "ledgerAccount": null,
      "code": "0",
      "state": 0
    }
  ]
}
```
Obtener un impuesto
-------------------

* `GET /v1/taxes/1.json` retornara un impuesto específico.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/taxes/1.json",
  "id": 1,
  "name": "IVA",
  "percentage": "19.0",
  "forAllProducts": 0,
  "ledgerAccount": null,
  "code": "0",
  "state": 0
}
```
Obtener cantidad de impuestos.
-----------------------------------

* `GET /v1/taxes/count.json`
```json
{
  "count": 3
}
```