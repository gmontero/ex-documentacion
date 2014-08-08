Obtener colección de pagos
--------------------------

* `GET /v1/payments.json` retornara todos los pagos realizados.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *recorddate*, Permite filtrar por fecha del pago.
- *state*, boolean (0 o 1) indica si los pagos estan activos(0) inactivos(1).

####Ejemplos

* `GET /v1/payments.json?limit=10&offset=0`
* `GET /v1/payments.json?recorddate=1393642800,`
* `GET /v1/payments.json?expand=[office,payment_type]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/payments.json",
  "count": 1926,
  "limit": 4,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/payments/950.json",
      "id": 950,
      "recordDate": null,
      "amount": "68643.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "https://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/payments/951.json",
      "id": 951,
      "recordDate": null,
      "amount": "281494.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "https://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/payments/957.json",
      "id": 957,
      "recordDate": null,
      "amount": "52637.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "https://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/payments/958.json",
      "id": 958,
      "recordDate": null,
      "amount": "22837.0",
      "checkDate": null,
      "checkNumber": null,
      "checkAmount": "0",
      "state": 0,
      "payment_type": {
        "href": "https://api.bsale.cl/v1/payment_types/1.json",
        "id": "1"
      },
      "office": {
        "href": "https://api.bsale.cl/v1/offices/2.json",
        "id": "2"
      }
    }
  ]
}
```
Obtener un pago
---------------

* `GET /v1/payments/950.json` retornara un pago específico.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/payments/950.json",
  "id": 950,
  "recordDate": null,
  "amount": "68643.0",
  "checkDate": null,
  "checkNumber": null,
  "checkAmount": "0",
  "state": 0,
  "payment_type": {
    "href": "https://api.bsale.cl/v1/payment_types/1.json",
    "id": "1"
  },
  "office": {
    "href": "https://api.bsale.cl/v1/offices/2.json",
    "id": "2"
  }
}
```
Obtener pagos agrupados por forma de pago
-----------------------------------------

* `GET /v1/payments/group_payment_types.json` retornara todos los pagos realizados.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *recorddate*, Permite filtrar por fecha del pago.
- *codesii*, Código documento basado en los identificadores del SII, pueden ser varios separados por coma.
- *documentid*, filtra por documento.
- *officeid*, filtra por sucursal.
- *paymenttypeid*, filtra por forma de pago.

####Ejemplos

* `GET /v1/payments/group_payment_types.json?limit=10&offset=0`
* `GET /v1/payments/group_payment_types.json?recorddate=1393642800,`

####Respuesta
```json
[
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 40906.0,
    "paymentTypeId": 1,
    "paymentTypeName": "Efectivo",
    "paymentLedgerAccount": null,
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 1,
    "isCreditMemo": 0,
    "codesii": "35",
    "officeId": 1,
    "officeName": "Puerto Varas",
    "officeCostCenter": "",
    "details": [

    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 174592.0,
    "paymentTypeId": 1,
    "paymentTypeName": "Efectivo",
    "paymentLedgerAccount": null,
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 1,
    "isCreditMemo": 0,
    "codesii": "39",
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "details": [

    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 75204.0,
    "paymentTypeId": 2,
    "paymentTypeName": "Tarjeta de Crédito",
    "paymentLedgerAccount": null,
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 0,
    "isCreditMemo": 0,
    "codesii": "35",
    "officeId": 1,
    "officeName": "Puerto Varas",
    "officeCostCenter": "",
    "details": [
      {
        "name": "Nº Comprobante",
        "value": ""
      }
    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 54328.0,
    "paymentTypeId": 2,
    "paymentTypeName": "Tarjeta de Crédito",
    "paymentLedgerAccount": null,
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 0,
    "isCreditMemo": 0,
    "codesii": "39",
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "details": [
      {
        "name": "Nº Comprobante",
        "value": ""
      }
    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 816873.0,
    "paymentTypeId": 4,
    "paymentTypeName": "Crédito",
    "paymentLedgerAccount": "",
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 1,
    "isCash": 0,
    "isCreditMemo": 0,
    "codesii": "33",
    "officeId": 1,
    "officeName": "Puerto Varas",
    "officeCostCenter": "",
    "details": [

    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 16373.0,
    "paymentTypeId": 5,
    "paymentTypeName": "Cheque",
    "paymentLedgerAccount": "",
    "isCheck": 1,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 0,
    "isCreditMemo": 0,
    "codesii": "39",
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "details": [
      {
        "name": "Banco",
        "value": ""
      },
      {
        "name": "Número",
        "value": ""
      }
    ]
  },
  {
    "recordDate": 1396494000,
    "paymentTypeTotalAmount": 32658.0,
    "paymentTypeId": 6,
    "paymentTypeName": "Tarjeta de Débito",
    "paymentLedgerAccount": "",
    "isCheck": 0,
    "isCreditNote": 0,
    "isClientCredit": 0,
    "isCash": 0,
    "isCreditMemo": 0,
    "codesii": "39",
    "officeId": 2,
    "officeName": "Los Angeles",
    "officeCostCenter": "",
    "details": [
      {
        "name": "N Operacion",
        "value": ""
      }
    ]
  }
]
```


Obtener cantidad de pagos.
--------------------------

* `GET /v1/payments/count.json`
```json
{
  "count": 1926
}
```
