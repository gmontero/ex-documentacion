Obtener colección de tipos de documento
---------------------------------------

* `GET /v1/document_types.json` retornara todos los tipos de documento.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del tipo de documento.
- *codesii*, filtra por el codigo tributario del tipo de documento.
- *ledgeraccount*, filtra por la cuenta contable del tipo de documento.
- *booktypeid*, filtra por el tipo de libro que pertenece.
- *state*, boolean (0 o 1) indica si los tipos de documento estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/document_types.json?limit=10&offset=0`
* `GET /v1/document_types.json?fields=[codesii,ledgeraccount,state]`
* `GET /v1/document_types.json?expand=[book_type]`
* `GET /v1/document_types.json?codesii=33`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/document_types.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/document_types/2.json",
      "id": 2,
      "name": "FACTURA EXENTA O NO AFECTA ELECTRONICA",
      "initialNumber": 1,
      "codeSii": "34",
      "isElectronicDocument": 1,
      "breakdownTax": 1,
      "use": 0,
      "isSalesNote": 0,
      "isExempt": 1,
      "restrictsTax": 0,
      "useClient": 1,
      "messageBodyFormat": "",
      "thermalPrinter": 1,
      "state": 0,
      "copyNumber": 2,
      "isCreditNote": 0,
      "continuedHigh": 0,
      "ledgerAccount": null,
      "ipadPrint": 0,
      "ipadPrintHigh": "0",
      "book_type": {
        "href": "https://api.bsale.cl/v1/book_types/1.json",
        "id": "1"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/document_types/3.json",
      "id": 3,
      "name": "NOTA CREDITO ELECTRONICA",
      "initialNumber": 43,
      "codeSii": "61",
      "isElectronicDocument": 1,
      "breakdownTax": 1,
      "use": 1,
      "isSalesNote": 0,
      "isExempt": 0,
      "restrictsTax": 0,
      "useClient": 1,
      "messageBodyFormat": "",
      "thermalPrinter": 1,
      "state": 0,
      "copyNumber": 0,
      "isCreditNote": 1,
      "continuedHigh": 0,
      "ledgerAccount": null,
      "ipadPrint": 0,
      "ipadPrintHigh": "0",
      "book_type": {
        "href": "https://api.bsale.cl/v1/book_types/1.json",
        "id": "1"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/document_types/1.json",
      "id": 1,
      "name": "NOTA VENTA",
      "initialNumber": 1,
      "codeSii": "",
      "isElectronicDocument": 0,
      "breakdownTax": 1,
      "use": 0,
      "isSalesNote": 1,
      "isExempt": 0,
      "restrictsTax": 0,
      "useClient": 1,
      "messageBodyFormat": null,
      "thermalPrinter": 1,
      "state": 0,
      "copyNumber": 3,
      "isCreditNote": 0,
      "continuedHigh": 0,
      "ledgerAccount": null,
      "ipadPrint": 0,
      "ipadPrintHigh": "0"
    }
  ]
}
```
Obtener un tipo de documento
----------------------------

* `GET /v1/document_types/1.json` retornara un tipo de libro específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/document_types/1.json?expand=[book_type]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/document_types/1.json",
  "id": 1,
  "name": "NOTA VENTA",
  "initialNumber": 1,
  "codeSii": "",
  "isElectronicDocument": 0,
  "breakdownTax": 1,
  "use": 0,
  "isSalesNote": 1,
  "isExempt": 0,
  "restrictsTax": 0,
  "useClient": 1,
  "messageBodyFormat": null,
  "thermalPrinter": 1,
  "state": 0,
  "copyNumber": 3,
  "isCreditNote": 0,
  "continuedHigh": 0,
  "ledgerAccount": null,
  "ipadPrint": 0,
  "ipadPrintHigh": "0"
}
```
Cantidad de tipos de libro
----------------------------------

* `GET /v1/document_types/count.json`
```json
{
  "count": 3
}
```