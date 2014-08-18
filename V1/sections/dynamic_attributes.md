Obtener colección de Atributos dinámicos
----------------------------------------

* `GET /v1/dynamic_attributes.json` retornara todos los Atributos dinámicos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del atributo.
- *type*, filtra tipo de atributo.
- *state*, boolean (0 o 1) indica si las listas de precio estan activas(0) inactivas (1).
- *paymenttypeid*, filtra por la forma de pago.
- *documenttypeid*, fitra por el tipo de documento.

####Ejemplos

* `GET /v1/dynamic_attributes.json?limit=10&offset=0`
* `GET /v1/dynamic_attributes.json?fields=[name,type,state]`
* `GET /v1/dynamic_attributes.json?paymenttypeid=1`
* `GET /v1/dynamic_attributes.json?expand=[coin,details]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/dynamic_attributes.json",
  "count": 15,
  "limit": 4,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/12.json",
      "id": 12,
      "name": "Fono Contacto",
      "tip": "Fono Contacto",
      "type": 4,
      "isMandatory": 0,
      "state": 0,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/4.json",
        "id": "4"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/16.json",
      "id": 16,
      "name": "Fono Contacto",
      "tip": "",
      "type": 4,
      "isMandatory": 0,
      "state": 0,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/10.json",
        "id": "10"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/15.json",
      "id": 15,
      "name": "Nombre Contacto",
      "tip": "",
      "type": 4,
      "isMandatory": 0,
      "state": 0,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/10.json",
        "id": "10"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/3.json",
      "id": 3,
      "name": "Número",
      "tip": "",
      "type": 4,
      "isMandatory": 0,
      "state": 0,
      "payment_type": {
        "href": "https://api.bsale.cl/v1/payment_types/5.json",
        "id": "5"
      }
    }
  ]
}
```
Obtener un atributo dinámico
----------------------------

* `GET /v1/dynamic_attributes/3.json`

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/dynamic_attributes/3.json?expand=[payment_type]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/dynamic_attributes/3.json",
  "id": 3,
  "name": "Número",
  "tip": "",
  "type": 4,
  "isMandatory": 0,
  "state": 0,
  "payment_type": {
    "href": "https://api.bsale.cl/v1/payment_types/5.json",
    "id": "5"
  }
}
```
Obtener detalles de un atributo dinámico
----------------------------------------

* `GET /v1/price_lists/3/details.json`
```json
{
  "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details.json",
  "count": 9,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/1.json",
      "id": 1,
      "name": "Operación Constituye Venta",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/2.json",
      "id": 2,
      "name": "Venta por Efectuar",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/3.json",
      "id": 3,
      "name": "Consignaciones",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/4.json",
      "id": 4,
      "name": "Entrega Gratuita",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/5.json",
      "id": 5,
      "name": "Traslado Interno",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/6.json",
      "id": 6,
      "name": "Otros Traslados No Venta",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/7.json",
      "id": 7,
      "name": "Guía Devolución",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/8.json",
      "id": 8,
      "name": "Traslado para Exportación",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/9.json",
      "id": 9,
      "name": "Venta para Exportación",
      "state": 1
    }
  ]
}
```
Obtener un de detalle de un atributo dinámico
---------------------------------------------

* `GET /v1/dynamic_attributes/8/details/9.json`
```json
{
  "href": "https://api.bsale.cl/v1/dynamic_attributes/8/details/9.json",
  "id": 9,
  "name": "Venta para Exportación",
  "state": 1
}
```