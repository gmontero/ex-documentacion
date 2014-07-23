Obtener colección de tipos de producto
--------------------------------------

* `GET /v1/product_types.json` retornara todos los tipos de producto.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre tipo producto.
- *state*, boolean (0 o 1) indica si los tipos de producto estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/product_types.json?limit=10&offset=0`
* `GET /v1/product_types.json?fields=[name,state]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/product_types.json",
  "count": 7,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/product_types/3.json",
      "id": 3,
      "name": "APPS One Time",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/2.json",
      "id": 2,
      "name": "APPS Recurrente",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/4.json",
      "id": 4,
      "name": "Desarrollo One Time",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/7.json",
      "id": 7,
      "name": "Desarrollo Recurrente",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/6.json",
      "id": 6,
      "name": "Plataforma One Time",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/5.json",
      "id": 5,
      "name": "Plataforma Recurrente",
      "isEditable": 1,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    },
    {
      "href": "http://api.bsale.cl/v1/product_types/1.json",
      "id": 1,
      "name": "Sin Tipo",
      "isEditable": 0,
      "state": 0,
      "imagestionCategoryId": 0,
      "prestashopCategoryId": 0
    }
  ]
}
```
Obtener un tipo de producto
---------------------------

* `GET /v1/product_types/2.json` retornara un tipo de producto específico.

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/product_types/2.json",
  "id": 2,
  "name": "APPS Recurrente",
  "isEditable": 1,
  "state": 0,
  "imagestionCategoryId": 0,
  "prestashopCategoryId": 0
}
```

Obtener los productos de un tipo de producto
--------------------------------------------

* `GET /v1/product_types/3/products.json`
```json
{
  "href": "http://api.bsale.cl/v1/products.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/products/2.json",
      "id": 2,
      "name": "Asesoria Informatica Imagestion Capacitacion",
      "description": "",
      "classification": 1,
      "ledgerAccount": "",
      "costCenter": "",
      "allowDecimal": 1,
      "stockControl": 0,
      "printDetailPack": 0,
      "state": 0,
      "prestashopProductId": 0,
      "presashopAttributeId": 0,
      "product_type": {
        "href": "http://api.bsale.cl/v1/product_types/3.json",
        "id": "3"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/products/49.json",
      "id": 49,
      "name": "Etravel Capacitacion",
      "description": "",
      "classification": 1,
      "ledgerAccount": "",
      "costCenter": "",
      "allowDecimal": 1,
      "stockControl": 0,
      "printDetailPack": 0,
      "state": 0,
      "prestashopProductId": 0,
      "presashopAttributeId": 0,
      "product_type": {
        "href": "http://api.bsale.cl/v1/product_types/3.json",
        "id": "3"
      }
    }
  ]
}
```

Cantidad de tipos de producto.
--------------------------

* `GET /v1/product_types/count.json`
```json
{
  "count": 1926
}
```