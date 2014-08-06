Obtener colección de variantes
------------------------------

* `GET /v1/variants.json` retornara todas las variantes.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *description*, Permite filtrar por nombre de la variante.
- *barcode*, filtra por codigo de barra del producto.
- *code*, filtra por codigo del producto.
- *serialnumber*, filtra los clientes por email.
- *productid*, recupera los clientes con forma de pago.
- *state*, boolean (0 o 1) indica si los clientes estan activos(0) inactivos (1).

####Ejemplos

* `GET /v1/variants.json?limit=10&offset=0`
* `GET /v1/variants.json?fields=[description,barCode,code]`
* `GET /v1/variants.json?state=0`
* `GET /v1/variants.json?productid=26`
* `GET /v1/variants.json?expand=[product]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/variants.json",
  "count": 165,
  "limit": 4,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/variants/101.json",
      "id": 101,
      "description": " Sitio Web",
      "unlimitedStock": 1,
      "allowNegativeStock": 0,
      "state": 0,
      "barCode": "6584",
      "code": "6584",
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
        "href": "https://api.bsale.cl/v1/products/26.json",
        "id": "26"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/variants/167.json",
      "id": 167,
      "description": "Anual",
      "unlimitedStock": 1,
      "allowNegativeStock": 0,
      "state": 0,
      "barCode": "619904148",
      "code": "619904148",
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
        "href": "https://api.bsale.cl/v1/products/75.json",
        "id": "75"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/variants/170.json",
      "id": 170,
      "description": "Anual",
      "unlimitedStock": 1,
      "allowNegativeStock": 0,
      "state": 0,
      "barCode": "621165228",
      "code": "621165228",
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
        "href": "https://api.bsale.cl/v1/products/78.json",
        "id": "78"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/variants/206.json",
      "id": 206,
      "description": "Asesoria Informatica",
      "unlimitedStock": 1,
      "allowNegativeStock": 0,
      "state": 55,
      "barCode": "1401120184",
      "code": "1401120184",
      "imagestionCenterCost": 0,
      "imagestionAccount": 0,
      "imagestionConceptCod": 0,
      "imagestionProyectCod": 0,
      "imagestionCategoryCod": 0,
      "imagestionProductId": 0,
      "serialNumber": 0,
      "prestashopCombinationId": 0,
      "prestashopValueId": 0,
      "product": {
        "href": "https://api.bsale.cl/v1/products/93.json",
        "id": "93"
      }
    }
  ]
}
```
Obtener una variante
--------------------

* `GET /v1/variants/101.json` retornara una variante específica.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/variants/101.json?expand=[product]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/variants/101.json",
  "id": 101,
  "description": " Sitio Web",
  "unlimitedStock": 1,
  "allowNegativeStock": 0,
  "state": 0,
  "barCode": "6584",
  "code": "6584",
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
    "href": "https://api.bsale.cl/v1/products/26.json",
    "id": "26"
  }
}
```
Cantidad de variantes
---------------------

* `GET /v1/variants/count.json`
```json
{
  "count": 165
}
```
Crea un cliente.
--------------------

* `POST /v1/variants.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "unlimitedStock": 0,
  "allowNegativeStock": 0,
  "description": "Calcetas con rombos",
  "code": "1394725851",
  "serialNumber": "15269874",
  "productID": "1",
  "barCode": "1394725851"
}
```
####Respuesta
```json
{
  "code": "1394725851",
  "imagestionAccount": 0,
  "state": 0,
  "allowNegativeStock": 0,
  "unlimitedStock": 0,
  "product": {
    "href": "https://api.bsale.cl/v1/products/1.json",
    "id": "1"
  },
  "prestashopCombinationId": 0,
  "imagestionProyectCod": 0,
  "barCode": "1394725851",
  "serialNumber": 15269874,
  "prestashopValueId": 0,
  "description": "Calcetas con rombos",
  "href": "https://api.bsale.cl/v1/variants/208.json",
  "imagestionProductId": 0,
  "imagestionCategoryCod": 0,
  "imagestionCenterCost": 0,
  "imagestionConceptCod": 0,
  "id": 208
}
```
Modifica una variante
---------------------

* `PUT /v1/variants/208.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "id": 208,
  "description": "Calcetas con rombos rojos"
}
```
####Respuesta
```json
{
  "code": "1394725851",
  "imagestionAccount": 0,
  "state": 0,
  "allowNegativeStock": 0,
  "unlimitedStock": 0,
  "product": {
    "href": "https://api.bsale.cl/v1/products/1.json",
    "id": "1"
  },
  "prestashopCombinationId": 0,
  "imagestionProyectCod": 0,
  "barCode": "1394725851",
  "serialNumber": 15269874,
  "prestashopValueId": 0,
  "description": "Calcetas con rombos rojos",
  "href": "https://api.bsale.cl/v1/variants/208.json",
  "imagestionProductId": 0,
  "imagestionCategoryCod": 0,
  "imagestionCenterCost": 0,
  "imagestionConceptCod": 0,
  "id": 208
}
```
Eliminar una variante virtualmente (desactivar).
----------------------------------------------

* `DELETE /v1/variants/208.json` cambia el estado de la variante.
```json
{
  "code": "1394725851",
  "imagestionAccount": 0,
  "state": 1,
  "allowNegativeStock": 0,
  "unlimitedStock": 0,
  "product": {
    "href": "https://api.bsale.cl/v1/products/1.json",
    "id": "1"
  },
  "prestashopCombinationId": 0,
  "imagestionProyectCod": 0,
  "barCode": "1394725851",
  "serialNumber": 15269874,
  "prestashopValueId": 0,
  "description": "Calcetas con rombos rojos",
  "href": "https://api.bsale.cl/v1/variants/208.json",
  "imagestionProductId": 0,
  "imagestionCategoryCod": 0,
  "imagestionCenterCost": 0,
  "imagestionConceptCod": 0,
  "id": 208
}
```