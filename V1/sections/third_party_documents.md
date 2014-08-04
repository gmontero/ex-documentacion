Obtener colección de documentos de tercero
------------------------------------------

* `GET /v1/third_pary_documents.json` retornara todas las monedas.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *emissiondate*, filtra documentos por la fecha de emision.
- *codesii*, filtra por el codigo tributario del documento.
- *clientcode*, permite filtrar por rut del cliente.
- *year*, boolean permite filtrar por año del documento.
- *month*, permite filtrar por mes del documento.

####Ejemplos

* `GET /v1/third_pary_documents.json?limit=10&offset=0`
* `GET /v1/third_pary_documents.json?fields=[emissiondate,number,totalAmount]`
* `GET /v1/third_pary_documents.json?year=2014`
* `GET /v1/third_pary_documents.json?codesii=31`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/third_pary_documents.json",
  "count": 269,
  "limit": 3,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/third_pary_documents/38.json",
      "id": 38,
      "codeSii": "34",
      "emissionDate": 1330657200,
      "number": 1179981,
      "clientCode": "89862200-2",
      "clientActivity": "LAN AIRLINES S.A.",
      "exemptAmount": 66488.0,
      "netAmount": 66488.0,
      "iva": 19.0,
      "ivaAmount": 0.0,
      "ivaOutOfTimeAmount": 0.0,
      "specificTaxCode": null,
      "specificTaxAmount": "0",
      "additionalTaxAmount": null,
      "ivaNotRecoverableAmount": 0.0,
      "totalAmount": 66488.0,
      "bookType": "compra",
      "reportedSii": 0,
      "thirdSii": 0,
      "month": 4,
      "year": 2012,
      "specificTaxRate": null,
      "canceled": 0,
      "ivaAmountWithheld": 0.0,
      "addBook": 1,
      "urlPdf": null,
      "fixedAssetAmount": 0.0,
      "liquidationCode": null,
      "commissionTotalNetAmount": 0,
      "commissionTotalExemptAmount": 0,
      "commissionTotalIvaAmount": 0,
      "docsCount": 0
    },
    {
      "href": "https://api.bsale.cl/v1/third_pary_documents/39.json",
      "id": 39,
      "codeSii": "34",
      "emissionDate": 1330657200,
      "number": 1180016,
      "clientCode": "89862200-2",
      "clientActivity": "LAN AIRLINES S.A.",
      "exemptAmount": 47488.0,
      "netAmount": 47488.0,
      "iva": 19.0,
      "ivaAmount": 0.0,
      "ivaOutOfTimeAmount": 0.0,
      "specificTaxCode": null,
      "specificTaxAmount": "0",
      "additionalTaxAmount": null,
      "ivaNotRecoverableAmount": 0.0,
      "totalAmount": 47488.0,
      "bookType": "compra",
      "reportedSii": 0,
      "thirdSii": 0,
      "month": 4,
      "year": 2012,
      "specificTaxRate": null,
      "canceled": 0,
      "ivaAmountWithheld": 0.0,
      "addBook": 1,
      "urlPdf": null,
      "fixedAssetAmount": 0.0,
      "liquidationCode": null,
      "commissionTotalNetAmount": 0,
      "commissionTotalExemptAmount": 0,
      "commissionTotalIvaAmount": 0,
      "docsCount": 0
    },
    {
      "href": "https://api.bsale.cl/v1/third_pary_documents/40.json",
      "id": 40,
      "codeSii": "34",
      "emissionDate": 1330657200,
      "number": 1179882,
      "clientCode": "89862200-2",
      "clientActivity": "LAN AIRLINES S.A.",
      "exemptAmount": 60488.0,
      "netAmount": 60488.0,
      "iva": 19.0,
      "ivaAmount": 0.0,
      "ivaOutOfTimeAmount": 0.0,
      "specificTaxCode": null,
      "specificTaxAmount": "0",
      "additionalTaxAmount": null,
      "ivaNotRecoverableAmount": 0.0,
      "totalAmount": 60488.0,
      "bookType": "compra",
      "reportedSii": 0,
      "thirdSii": 0,
      "month": 4,
      "year": 2012,
      "specificTaxRate": null,
      "canceled": 0,
      "ivaAmountWithheld": 0.0,
      "addBook": 1,
      "urlPdf": null,
      "fixedAssetAmount": 0.0,
      "liquidationCode": null,
      "commissionTotalNetAmount": 0,
      "commissionTotalExemptAmount": 0,
      "commissionTotalIvaAmount": 0,
      "docsCount": 0
    }
  ]
}
```
Obtener un documentos de tercero
--------------------------------

* `GET /v1/third_pary_documents/38.json` retornara una moneda específica.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/third_pary_documents/38.json",
  "id": 38,
  "codeSii": "34",
  "emissionDate": 1330657200,
  "number": 1179981,
  "clientCode": "89862200-2",
  "clientActivity": "LAN AIRLINES S.A.",
  "exemptAmount": 66488.0,
  "netAmount": 66488.0,
  "iva": 19.0,
  "ivaAmount": 0.0,
  "ivaOutOfTimeAmount": 0.0,
  "specificTaxCode": null,
  "specificTaxAmount": "0",
  "additionalTaxAmount": null,
  "ivaNotRecoverableAmount": 0.0,
  "totalAmount": 66488.0,
  "bookType": "compra",
  "reportedSii": 0,
  "thirdSii": 0,
  "month": 4,
  "year": 2012,
  "specificTaxRate": null,
  "canceled": 0,
  "ivaAmountWithheld": 0.0,
  "addBook": 1,
  "urlPdf": null,
  "fixedAssetAmount": 0.0,
  "liquidationCode": null,
  "commissionTotalNetAmount": 0,
  "commissionTotalExemptAmount": 0,
  "commissionTotalIvaAmount": 0,
  "docsCount": 0
}
```