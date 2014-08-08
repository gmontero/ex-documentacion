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
* `GET /v1/documents.json?emissiondate=1309478400&expirationdate=1309478400&state=0`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/documents.json",
  "count": 1452,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/documents/15.json",
      "id": 15,
      "emissionDate": 1309478400,
      "expirationDate": 1309478400,
      "number": 1,
      "totalAmount": 120410.0,
      "netAmount": 120410.0,
      "taxAmount": 0.0,
      "exemptAmount": 120410.0,
      "urlTimbre": "-",
      "urlPdf": "https://app.bsale.cl/view/613/88cab16269f8.pdf",
      "token": "88cab16269f8",
      "state": 0,
      "userId": 1,
      "urlXml": null,
      "address": "San Crescente 240",
      "municipality": "Las Condes",
      "city": "Santiago",
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/1.json",
        "id": "1"
      },
      "client": {
        "href": "https://api.bsale.cl/v1/clients/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/documents/190.json",
      "id": 190,
      "emissionDate": 1301356800,
      "expirationDate": 1301356800,
      "number": 40,
      "totalAmount": 22207210.0,
      "netAmount": 22207210.0,
      "taxAmount": 0.0,
      "exemptAmount": 22207210.0,
      "urlTimbre": "-",
      "urlPdf": "https://app.bsale.cl/view/613/f7712ecede59.pdf",
      "token": "f7712ecede59",
      "state": 0,
      "userId": 5,
      "urlXml": null,
      "address": "Este de Punta Chiguao S/N",
      "municipality": "Quellón",
      "city": "Quellón",
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/1.json",
        "id": "1"
      },
      "client": {
        "href": "https://api.bsale.cl/v1/clients/29.json",
        "id": "29"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    }
  ]
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
  "href": "https://api.bsale.cl/v1/documents/190.json",
  "id": 190,
  "emissionDate": 1301356800,
  "expirationDate": 1301356800,
  "number": 40,
  "totalAmount": 22207210.0,
  "netAmount": 22207210.0,
  "taxAmount": 0.0,
  "exemptAmount": 22207210.0,
  "urlTimbre": "-",
  "urlPdf": "https://app.bsale.cl/view/613/f7712ecede59.pdf",
  "token": "f7712ecede59",
  "state": 0,
  "userId": 5,
  "urlXml": null,
  "address": "Este de Punta Chiguao S/N",
  "municipality": "Quellón",
  "city": "Quellón",
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/1.json",
    "id": "1"
  },
  "client": {
    "href": "https://api.bsale.cl/v1/clients/29.json",
    "id": "29"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  }

```
Obtener colección de documentos
-------------------------------

* `GET /v1/documents/summary.json` retorna resumen.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *emissiondaterange*, filtra por rango de fecha de emision.
- *generationdaterange*, filtra por rango de fecha de generacion.
- *codesii*, Código documento basado en los identificadores del SII, pueden ser varios separados por coma.
- *perdocument*, Boolean (0 o 1) indica si el resultado lo agrupa por documento.

####Ejemplos

* `GET /v1/documents.json?limit=10&offset=0`
* `GET /v1/documents/summary.json?emissiondaterange=[1404187200,1406779200]`
* `GET /v1/documents/summary.json?generationdaterange=[1404187200,1406779200]`
* `GET /v1/documents/summary.json?codesii=[33,31]`
* `GET /v1/documents/summary.json?perdocument=1`

####Respuesta
```json
[
  {
    "generationDate": "",
    "emissionDate": "",
    "documentTypeName": "Boleta Electrónica",
    "codeSii": "39",
    "month": 7,
    "year": 2014,
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "count": 1,
    "totalNetAmount": 2791.0,
    "totalTaxAmount": 530.0,
    "totalAmount": 3321.0,
    "totalExemptAmount": 0.0,
    "taxes": [
      {
        "taxId": 1,
        "taxName": "IVA",
        "taxAmount": 530.0
      }
    ],
    "details": [
      {
        "itemLedgerAccount": "",
        "totalNetAmount": 2791.0
      }
    ],
    "documentId": 10383,
    "documentNumber": 9093
  },
  {
    "generationDate": "",
    "emissionDate": "",
    "documentTypeName": "Boleta Electrónica",
    "codeSii": "39",
    "month": 7,
    "year": 2014,
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "count": 1,
    "totalNetAmount": 15132.0,
    "totalTaxAmount": 2875.0,
    "totalAmount": 18007.0,
    "totalExemptAmount": 0.0,
    "taxes": [
      {
        "taxId": 1,
        "taxName": "IVA",
        "taxAmount": 2875.0
      }
    ],
    "details": [
      {
        "itemLedgerAccount": "",
        "totalNetAmount": 15132.0
      }
    ],
    "documentId": 10384,
    "documentNumber": 9094
  }
]
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
  "emissionDate": "1309478400",
  "expirationDate": "1309478400",
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
  "urlPdf": "https://app.bsale.cl/view/613/e46554f50e44.pdf",
  "client": {
    "href": "https://api.bsale.cl/v1/clients/7.json",
    "id": "7"
  },
  "urlXml": " ",
  "exemptAmount": "134702.4",
  "href": "https://api.bsale.cl/v1/documents/10145.json",
  "city": "Puerto Montt",
  "totalAmount": "134702.4",
  "urlTimbre": "https://s3.amazonaws.com/bsale/imaginexti/timbres/T34_F1760.png",
  "number": 1760,
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/2.json",
    "id": "2"
  },
  "address": "Av. Juan Soler Manfredini 41 1801",
  "token": "e46554f50e44",
  "emissionDate": "21309478400",
  "municipality": "Puerto Montt",
  "state": 0,
  "expirationDate": "1309478400",
  "id": 10145,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "userId": 1,
  "taxAmount": "0.0",
  "netAmount": "134702.4"
}
```
