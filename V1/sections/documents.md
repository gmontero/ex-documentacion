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

Para crear una factura electrónica, se debe enviar un Json con la siguiente esctructura.
```json
{
  "documentTypeId": 8,          # Identificador del tipo del documento, se debe enviar el que pertenece a factura electrónica.
  "officeId": 1,                # Sucursal donde se emite el documento.
  "emissionDate": 1407715200,   # Fecha de emision del documento, se envia en integer GMT.
  "expirationDate": 1407715200, # Fecha vencimiento del documento, se envia en integer GMT.
  "declareSii": 1,              # Si se desea declarar el documento se envia 1 en caso contrario 0.
  "priceListId": 18,            # Identificador de la lista de precio, si no se envia usara la por defecto de la sucursal.
  "payments": [
    {
      "paymentTypeId": 1,       # Identificador de la forma de pago.
      "amount": 70000,          # Monto de la forma de pago.
      "recordDate": 1407715200  # Fecha del pago, se envia en integer GMT..
    }
  ],
  "details": [
    {
      "variantId":1,            # Identificador de la variante, si se utiliza glosa dinamica no se debe enviar.
      "netUnitValue": 53975,    # Valor neto.
      "quantity": 1,            # cantidad.
      "taxId": "[1,2]",         # Identificadores de los impuesto a utilizar.
      "comment": "Producto 1"   # Glosa dinamica.
      "discount": 0             # % de descuento.
    }
  ],
  "client": {
    "code": "1-9",              # Rut cliente.
    "city": "Puerto Varas",     # Ciudad.
    "company": "Imaginex",      # Razon social.
    "municipality": "comuna",   # Comuna.
    "activity": "giro",         # Giro empresa.
    "address": "direccion"      # Direccion.
  }
}
```
####Respuesta
```json
{
  "urlXml": " ",
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/8.json",
    "id": "8"
  },
  "urlTimbre": "http://s3.amazonaws.com/bsale/imaginex/timbres/T33_F930.png",
  "userId": 1,
  "emissionDate": 1407643200,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "taxAmount": 20511.0,
  "number": 930,
  "href": "https://api.bsale.cl/v1/documents/11558.json",
  "urlPdf": "http://app.bsale.cl/view/339/e850a3beb02b.pdf",
  "expirationDate": 1407643200,
  "city": "puerto varas",
  "netAmount": 53975.0,
  "exemptAmount": 0.0,
  "id": 11558,
  "municipality": "comuna",
  "token": "e850a3beb02b",
  "client": {
    "href": "https://api.bsale.cl/v1/clients/211.json",
    "id": "211"
  },
  "address": "direccion,
  "state": 0,
  "totalAmount": 74486.0
}
```
