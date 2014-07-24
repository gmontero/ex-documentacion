Obtener colección de documentos
-------------------------------

* `GET /v1/documents.json` retorna todos los documentos.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *emissiondate*, filtra documentos por la fecha de emision.
- *expirationdate*, filtra documentos por la fecha de vencimiento.
- *number*, filtra documentos por el folio.
- *token*, filtra documentos por el token.
- *documenttypeid*, filtra documentos por el tipo de documento.
- *clientid*, filtra documentos por el cliente.
- *officeid*, filtra documentos por la sucursal.
- *saleconditionid*, filtra documentos por la condicion de venta.
- *state*, boolean (0 o 1) indica si los documentos estan activos(0) inactivos (1).

####Ejemplos

* `GET /v1/documents.json?limit=10&offset=0`
* `GET /v1/documents.json?fields=[number,totalAmount]`
* `GET /v1/documents.json?number=53`
* `GET /v1/documents.json?documenttypeid=1`
* `GET /v1/documents.json?expand=[document_types,client,office]`
* `GET /v1/documents.json?emissiondate=2011-07-01&expirationdate=2011-08-01&state=0`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/documents.json",
  "count": 1449,
  "limit": 2,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/documents/15.json",
      "id": 15,
      "emissionDate": "2011-07-01",
      "expirationDate": "2011-07-01",
      "number": 1,
      "totalAmount": "120410.0",
      "netAmount": "120410.0",
      "taxAmount": "0.0",
      "exemptAmount": "120410.0",
      "urlTimbre": "-",
      "urlPdf": "http://app.bsale.cl/view/613/88cab16269f8.pdf",
      "token": "88cab16269f8",
      "state": 0,
      "userId": 1,
      "urlXml": null,
      "address": "San Crescente 240",
      "municipality": "Las Condes",
      "city": "Santiago",
      "document_type": {
        "href": "http://api.bsale.cl/v1/document_types/1.json",
        "id": "1"
      },
      "client": {
        "href": "http://api.bsale.cl/v1/clients/1.json",
        "id": "1"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/documents/190.json",
      "id": 190,
      "emissionDate": "2011-03-29",
      "expirationDate": "2011-03-29",
      "number": 40,
      "totalAmount": "22207210.0",
      "netAmount": "22207210.0",
      "taxAmount": "0.0",
      "exemptAmount": "22207210.0",
      "urlTimbre": "-",
      "urlPdf": "http://app.bsale.cl/view/613/f7712ecede59.pdf",
      "token": "f7712ecede59",
      "state": 0,
      "userId": 5,
      "urlXml": null,
      "address": "Este de Punta Chiguao S/N",
      "municipality": "Quellon",
      "city": "Quellon",
      "document_type": {
        "href": "http://api.bsale.cl/v1/document_types/1.json",
        "id": "1"
      },
      "client": {
        "href": "http://api.bsale.cl/v1/clients/29.json",
        "id": "29"
      },
      "office": {
        "href": "http://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    }
```
Obtener un documento
--------------------

* `GET /v1/documents/190.json` retorna un documento específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/documents/190.json?expand=[document_type,office]`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/documents/190.json",
  "id": 190,
  "emissionDate": "2011-03-29",
  "expirationDate": "2011-03-29",
  "number": 40,
  "totalAmount": "22207210.0",
  "netAmount": "22207210.0",
  "taxAmount": "0.0",
  "exemptAmount": "22207210.0",
  "urlTimbre": "-",
  "urlPdf": "http://app.bsale.cl/view/613/f7712ecede59.pdf",
  "token": "f7712ecede59",
  "state": 0,
  "userId": 5,
  "urlXml": null,
  "address": "Este de Punta Chiguao S/N",
  "municipality": "Quellon",
  "city": "Quellon",
  "document_type": {
    "href": "http://api.bsale.cl/v1/document_types/1.json",
    "id": "1"
  },
  "client": {
    "href": "http://api.bsale.cl/v1/clients/29.json",
    "id": "29"
  },
  "office": {
    "href": "http://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  }
}
```
Cantidad de documentos
----------------------

* `GET /v1/documents/count.json`
```json
{
  "count": 1449
}
```
Crea un documento
-----------------

* `POST /v1/documents.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "documentTypeId": 2,
  "priceListId": 2,
  "emissionDate": "2014-07-23",
  "expirationDate": "2014-07-23",
  "declareSii": 1,
  "officeId": 1,
  "exchangeRate": 24054,
  "details": [
    {
      "discount": 0,
      "comment": "Prueba API nueva",
      "variantId": 1,
      "quantity": 1,
      "netUnitValue": 5.6
    }
  ],
  "client": {
    "code": "76018303-2",
    "activity": "Servicios Relacionados con la Acuicultura",
    "lastName": "Reinoso",
    "company": "Ocea Chile S.A.",
    "firstName": "Julio",
    "email": "facturas@ocea.cl"
  },
  "payments": [
    {
      "paymentTypeId": 1,
      "amount": 70000,
      "recordDate": "2014-07-22"
    }
  ]
}
```
####Respuesta
```json
{
  "urlPdf": "http://app.bsale.cl/view/613/e46554f50e44.pdf",
  "client": {
    "href": "http://api.bsale.cl/v1/clients/7.json",
    "id": "7"
  },
  "urlXml": " ",
  "exemptAmount": "134702.4",
  "href": "http://api.bsale.cl/v1/documents/10145.json",
  "city": "Puerto Montt",
  "totalAmount": "134702.4",
  "urlTimbre": "http://s3.amazonaws.com/bsale/imaginexti/timbres/T34_F1760.png",
  "number": 1760,
  "document_type": {
    "href": "http://api.bsale.cl/v1/document_types/2.json",
    "id": "2"
  },
  "address": "Av. Juan Soler Manfredini 41 1801",
  "token": "e46554f50e44",
  "emissionDate": "2014-07-23",
  "municipality": "Puerto Montt",
  "state": 0,
  "expirationDate": "2014-07-23",
  "id": 10145,
  "office": {
    "href": "http://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "userId": 1,
  "taxAmount": "0.0",
  "netAmount": "134702.4"
}
```