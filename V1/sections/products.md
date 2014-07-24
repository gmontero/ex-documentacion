Obtener colección de clientes
-----------------------------

* `GET /v1/products.json` retornara todos los productos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del producto.
- *ledgeraccount*, filtra por cuenta contable de los productos.
- *costcenter*, filtra centro de costo de los productos.
- *producttypeid*, filtra por tipo de producto.
- *state*, boolean (0 o 1) indica si los productos estan activos(0) inactivos (1).

####Ejemplos

* `GET /v1/products.json?limit=10&offset=0`
* `GET /v1/products.json?fields=[name,ledgeraccount,description]`
* `GET /v1/products.json?producttypeid=1`
* `GET /v1/products.json?expand=[product_type]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/products.json",
  "count": 53,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/products/62.json",
      "id": 62,
      "name": "Activox Desarrollo Controles de Cambio",
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
        "href": "http://api.bsale.cl/v1/product_types/4.json",
        "id": "4"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/products/30.json",
      "id": 30,
      "name": "Activox Hosting",
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
        "href": "http://api.bsale.cl/v1/product_types/5.json",
        "id": "5"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/products/29.json",
      "id": 29,
      "name": "Activox Soporte",
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
        "href": "http://api.bsale.cl/v1/product_types/7.json",
        "id": "7"
      }
    }
  ]
}
```
Obtener un producto
-------------------

* `GET /v1/products/62.json` retornara un producto específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/products/62.json?expand=[product_type]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/products/62.json",
  "id": 62,
  "name": "Activox Desarrollo Controles de Cambio",
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
    "href": "http://api.bsale.cl/v1/product_types/4.json",
    "id": "4"
  }
}
```
Obtener variantes de un producto
--------------------------------

* `GET /v1/products/62/variants.json`
```json
{
  "href": "http://api.bsale.cl/v1/variants.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/variants/149.json",
      "id": 149,
      "description": "Base",
      "unlimitedStock": 1,
      "allowNegativeStock": 0,
      "state": 0,
      "barCode": "abx-01",
      "code": "abx-01",
      "imagestionCenterCost": null,
      "imagestionAccount": null,
      "imagestionConceptCod": null,
      "imagestionProyectCod": null,
      "imagestionCategoryCod": 0,
      "imagestionProductId": 0,
      "serialNumber": 0,
      "prestashopCombinationId": 0,
      "prestashopValueId": 0,
      "product": {
        "href": "http://api.bsale.cl/v1/products/62.json",
        "id": "62"
      }
    }
  ]
}
```
Cantidad de productos
---------------------

* `GET /v1/products/count.json`
```json
{
  "count": 53
}
```
Crea un producto
----------------

* `POST /v1/clients.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "name": "Calcetines",
  "description": "Multiples colores de calcetines",
  "allowDecimal": 0,
  "ledgerAccount": "Calcetas",
  "costCenter": "23",
  "stockControl": 1  
}
```
####Respuesta
```json
{
  "stockControl": 1,
  "name": "Calcetines",
  "ledgerAccount": "Calcetas",
  "href": "http://api.bsale.cl/v1/products/97.json",
  "prestashopProductId": 0,
  "presashopAttributeId": 0,
  "costCenter": "23",
  "printDetailPack": 0,
  "product_type": {
    "href": "http://api.bsale.cl/v1/product_types/1.json",
    "id": "1"
  },
  "classification": 1,
  "description": "Multiples colores de calcetines",
  "id": 97,
  "state": 0,
  "allowDecimal": 0
}
```
Modifica un producto
--------------------

* `PUT /v1/products/67.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "id":"97",
  "name": "Calcetines de Mujer", 
}
```
####Respuesta
```json
{
  "stockControl": 1,
  "name": "Calcetines de Mujer",
  "ledgerAccount": "Calcetas",
  "href": "http://api.bsale.cl/v1/products/97.json",
  "prestashopProductId": 0,
  "presashopAttributeId": 0,
  "costCenter": "23",
  "printDetailPack": 0,
  "product_type": {
    "href": "http://api.bsale.cl/v1/product_types/1.json",
    "id": "1"
  },
  "classification": 1,
  "description": "Multiples colores de calcetines",
  "id": 97,
  "state": 0,
  "allowDecimal": 0
}
```
Eliminar un producto virtualmente (desactivar).
----------------------------------------------

* `DELETE /v1/products/97.json` cambia el estado del producto.
```json
{
  "href": "http://api.bsale.cl/v1/products/97.json",
  "id": 97,
  "name": "Calcetines",
  "description": "Multiples colores de calcetines",
  "classification": 1,
  "ledgerAccount": "Calcetas",
  "costCenter": "23",
  "allowDecimal": 0,
  "stockControl": 1,
  "printDetailPack": 0,
  "state": 1,
  "prestashopProductId": 0,
  "presashopAttributeId": 0,
  "product_type": {
    "href": "http://api.bsale.cl/v1/product_types/1.json",
    "id": "1"
  }
}
```