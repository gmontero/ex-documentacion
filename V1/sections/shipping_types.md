Obtener colección de tipos de despacho
--------------------------------------

* `GET /v1/shipping_types.json` retornara todos los tipos de libro.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre tipo libro.
- *codesii*, filtra por el codigo tributario del tipo de despacho.
- *state*, boolean (0 o 1) indica si los tipos de libro estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/shipping_types.json?limit=10&offset=0`
* `GET /v1/book_types.json?fields=[name,codesii,state]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/shipping_types.json",
  "count": 9,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/shipping_types/3.json",
      "id": 3,
      "name": "tipo_despacho.consignaciones",
      "codeSii": 3,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/4.json",
      "id": 4,
      "name": "tipo_despacho.entrega_gratuita",
      "codeSii": 4,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/7.json",
      "id": 7,
      "name": "tipo_despacho.guia_de_devolucion",
      "codeSii": 7,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/1.json",
      "id": 1,
      "name": "tipo_despacho.operacion_constituye_venta",
      "codeSii": 1,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/6.json",
      "id": 6,
      "name": "tipo_despacho.otros_traslados_no_venta",
      "codeSii": 6,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/5.json",
      "id": 5,
      "name": "tipo_despacho.traslados_internos",
      "codeSii": 5,
      "useDestinationOffice": 1,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/8.json",
      "id": 8,
      "name": "tipo_despacho.traslado_para_exportacion",
      "codeSii": 8,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/2.json",
      "id": 2,
      "name": "tipo_despacho.ventas_por_efectuar",
      "codeSii": 2,
      "useDestinationOffice": 0,
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/shipping_types/9.json",
      "id": 9,
      "name": "tipo_despacho.venta_para_exportacion",
      "codeSii": 9,
      "useDestinationOffice": 0,
      "state": 0
    }
  ]
}
```
Obtener un tipo de despacho
---------------------------

* `GET /v1/shipping_types/6.json` retornara un tipo de despacho específico.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/shipping_types/6.json",
  "id": 6,
  "name": "tipo_despacho.otros_traslados_no_venta",
  "codeSii": 6,
  "useDestinationOffice": 0,
  "state": 0
}
```