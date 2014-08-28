Estructura de un documento
--------------------------
Al realizar una peticion HTTP, el servicio retornara la siguiente estructura:

```json
{
  /* Url del documento (String). */
  "href": "https://api.bsale.cl/v1/documents/382.json",

  # Identificador unico del documento (Integer).
  "id": 382,

  # Fecha de emision del documento (Integer).
  "emissionDate": 1350604800,

  # Fecha de vencimiento del documento (Integer).
  "expirationDate": 1350604800,

  # Folio del documento (Integer).
  "number": 1,

  # Monto total del documento (Float).
  "totalAmount": 14280.0,

  # Monto neto del documento (Float).
  "netAmount": 12000.0,

  # Monto de impuestos del documento (Float).
  "taxAmount": 2280.0,

  # Monto exento del documento (Float).
  "exemptAmount": 0.0,

  # Url de la firma de un documento (String).
  "urlTimbre": null,

  # Url publica para visualizar el documento (String).
  "urlPublicView": "http://app.bsale.cl/view/2/439d299fb053",

  # Url del pdf del documento (String).
  "urlPdf": "http://app.bsale.cl/view/2/439d299fb053.pdf",

  # Token unico del documento (String).
  "token": "439d299fb053",

  # Estado del documento indica si el documento esta activo(0) o inactivo (1) (Boolean).
  "state": 0,

  # Identificador unico del usuario que emite el documento (Integer).
  "userId": 2,

  # Respaldo del documento electronico (String).
  "urlXml": null,

  # Direccion del Documento
  "address": null,

  "municipality": null,
  "city": null,
  "informedSii": 1,
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/1.json",
    "id": "1"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  },
  "references": {
    "href": "https://api.bsale.cl/v1/documents/382/references.json"
  },
  "document_taxes": {
    "href": "https://api.bsale.cl/v1/documents/382/document_taxes.json"
  },
  "details": {
    "href": "https://api.bsale.cl/v1/documents/382/details.json"
  }
}
```

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
  "count": 2939,
  "limit": 3,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/documents/382.json",
      "id": 382,
      "emissionDate": 1350604800,
      "expirationDate": 1350604800,
      "number": 1,
      "totalAmount": 14280.0,
      "netAmount": 12000.0,
      "taxAmount": 2280.0,
      "exemptAmount": 0.0,
      "urlTimbre": null,
      "urlPublicView": "http://app.bsale.cl/view/2/439d299fb053",
      "urlPdf": "http://app.bsale.cl/view/2/439d299fb053.pdf",
      "token": "439d299fb053",
      "state": 0,
      "userId": 2,
      "urlXml": null,
      "address": null,
      "municipality": null,
      "city": null,
      "informedSii": 1,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      },
      "references": {
        "href": "https://api.bsale.cl/v1/documents/382/references.json"
      },
      "document_taxes": {
        "href": "https://api.bsale.cl/v1/documents/382/document_taxes.json"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/documents/382/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/documents/404.json",
      "id": 404,
      "emissionDate": 1351036800,
      "expirationDate": 1351036800,
      "number": 1,
      "totalAmount": 14280.0,
      "netAmount": 0.0,
      "taxAmount": 0.0,
      "exemptAmount": 0.0,
      "urlTimbre": null,
      "urlPublicView": "http://app.bsale.cl/view/2/ad0496679450",
      "urlPdf": "http://app.bsale.cl/view/2/ad0496679450.pdf",
      "token": "ad0496679450",
      "state": 0,
      "userId": 20,
      "urlXml": null,
      "address": null,
      "municipality": null,
      "city": null,
      "informedSii": 1,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/3.json",
        "id": "3"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      },
      "references": {
        "href": "https://api.bsale.cl/v1/documents/404/references.json"
      },
      "document_taxes": {
        "href": "https://api.bsale.cl/v1/documents/404/document_taxes.json"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/documents/404/details.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/documents/421.json",
      "id": 421,
      "emissionDate": 1351641600,
      "expirationDate": 1351641600,
      "number": 1,
      "totalAmount": 5117000.0,
      "netAmount": 4300000.0,
      "taxAmount": 817000.0,
      "exemptAmount": 0.0,
      "urlTimbre": null,
      "urlPublicView": "http://app.bsale.cl/view/2/f806d6a6ae73",
      "urlPdf": "http://app.bsale.cl/view/2/f806d6a6ae73.pdf",
      "token": "f806d6a6ae73",
      "state": 0,
      "userId": 2,
      "urlXml": null,
      "address": "San Francisco 402, jj perez 7248",
      "municipality": "Santiago",
      "city": "Santiago",
      "informedSii": 2,
      "document_type": {
        "href": "https://api.bsale.cl/v1/document_types/4.json",
        "id": "4"
      },
      "client": {
        "href": "https://api.bsale.cl/v1/clients/7.json",
        "id": "7"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      },
      "references": {
        "href": "https://api.bsale.cl/v1/documents/421/references.json"
      },
      "document_taxes": {
        "href": "https://api.bsale.cl/v1/documents/421/document_taxes.json"
      },
      "details": {
        "href": "https://api.bsale.cl/v1/documents/421/details.json"
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
  "href": "https://api.bsale.cl/v1/documents/382.json",
  "id": 382,
  "emissionDate": 1350604800,
  "expirationDate": 1350604800,
  "number": 1,
  "totalAmount": 14280.0,
  "netAmount": 12000.0,
  "taxAmount": 2280.0,
  "exemptAmount": 0.0,
  "urlTimbre": null,
  "urlPublicView": "http://app.bsale.cl/view/2/439d299fb053",
  "urlPdf": "http://app.bsale.cl/view/2/439d299fb053.pdf",
  "token": "439d299fb053",
  "state": 0,
  "userId": 2,
  "urlXml": null,
  "address": null,
  "municipality": null,
  "city": null,
  "informedSii": 1,
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/1.json",
    "id": "1"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  },
  "references": {
    "href": "https://api.bsale.cl/v1/documents/382/references.json"
  },
  "document_taxes": {
    "href": "https://api.bsale.cl/v1/documents/382/document_taxes.json"
  },
  "details": {
    "href": "https://api.bsale.cl/v1/documents/382/details.json"
  }
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
Obtener referencias de un documento
-----------------------------------

* `GET /v1/documents/11561/references.json`
```json
{
  "href": "https://api.bsale.cl/v1/documents//references.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/documents/11561/references/5.json",
      "id": 5,
      "referenceDate": 1407643200,
      "number": "123",
      "reason": "Orden de Compra 123",
      "dte_code": {
        "href": "https://api.bsale.cl/v1/dte_codes/20.json",
        "id": "20"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/documents/11561/references/6.json",
      "id": 6,
      "referenceDate": 1407643200,
      "number": "456",
      "reason": "Guia despacho 456",
      "dte_code": {
        "href": "https://api.bsale.cl/v1/dte_codes/15.json",
        "id": "15"
      }
    }
  ]
}
```
Obtener una referencia de un documento
--------------------------------------

* `GET /v1/documents/11561/references/5.json`
```json
{
  "href": "https://api.bsale.cl/v1/documents/11561/references/5.json",
  "id": 5,
  "referenceDate": 1407643200,
  "number": "123",
  "reason": "Orden de Compra 123",
  "dte_code": {
    "href": "https://api.bsale.cl/v1/dte_codes/20.json",
    "id": "20"
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
  "references": [                        # Documentos de referencia de un documento, es opcional
      {
        "number": 123,                   # Folio de la referencia.
        "referenceDate": 1407715200,     # Fecha del documento de referencia.
        "reason": "Orden de Compra 123", # Razon del documento
        "codeSii": 801                   # Codigo tributario del documento de referencia.
      }
  ],
  "dynamicAttributes": [                 # atributos dinamicos, es opcional
    {
      "description": "098",              # Valor del atributo
      "dynamicAttributeId": 17           # Identificador del atributo dinamico
    },
    {
      "description": "nombre",
      "dynamicAttributeId": 18
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
  "urlTimbre": "http://s3.amazonaws.com/bsale/timbres/T33_F933.png",
  "client": {
    "href": "https://api.bsale.cl/v1/clients/211.json",
    "id": "211"
  },
  "address": "direccion valida",
  "token": "a1a3291afd78",
  "userId": 1,
  "exemptAmount": 0.0,
  "office": {
    "href": "https://api.bsale.cl/v1/offices/1.json",
    "id": "1"
  },
  "urlXml": " ",
  "expirationDate": 1407643200,
  "municipality": "puerto montt",
  "netAmount": 53975.0,
  "totalAmount": 74486.0,
  "document_type": {
    "href": "https://api.bsale.cl/v1/document_types/8.json",
    "id": "8"
  },
  "taxAmount": 20511.0,
  "number": 933,
  "href": "https://api.bsale.cl/v1/documents/11561.json",
  "emissionDate": 1407643200,
  "urlPdf": "http://app.bsale.cl/view/339/a1a3291afd78.pdf",
  "id": 11561,
  "references": {
    "href": "https://api.bsale.cl/v1/documents/11561/references.json"
  },
  "city": "puerto montt",
  "state": 0
}
```
