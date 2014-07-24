Obtener colección de formas de pago
-----------------------------------

* `GET /v1/payment_types.json` retornara todos los tipos de producto.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso.
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre de la forma de pago.
- *ledgeraccount*, cuenta contable de la forma de pago
- *state*, boolean (0 o 1) indica si las formas de pago estan activas(0) inactivas(1).

####Ejemplos

* `GET /v1/payment_types.json?limit=10&offset=0`
* `GET /v1/payment_types.json?fields=[name,ledgeraccount]`
* `GET /v1/payment_types.json?state=0`

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/payment_types.json",
  "count": 3,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/payment_types/3.json",
      "id": 3,
      "name": "Abono de Cliente",
      "isVirtual": 0,
      "isCheck": 0,
      "maxCheck": 0,
      "isCreditNote": 0,
      "isClientCredit": 0,
      "isCash": 0,
      "isCreditMemo": 1,
      "state": 0,
      "maxClientCuota": 0,
      "ledgerAccount": null
    },
    {
      "href": "http://api.bsale.cl/v1/payment_types/2.json",
      "id": 2,
      "name": "Credito Factura",
      "isVirtual": 0,
      "isCheck": 0,
      "maxCheck": null,
      "isCreditNote": 0,
      "isClientCredit": 1,
      "isCash": 0,
      "isCreditMemo": 0,
      "state": 0,
      "maxClientCuota": 0,
      "ledgerAccount": null
    },
    {
      "href": "http://api.bsale.cl/v1/payment_types/1.json",
      "id": 1,
      "name": "Deposito en Cuenta Corriente",
      "isVirtual": 1,
      "isCheck": 0,
      "maxCheck": null,
      "isCreditNote": 0,
      "isClientCredit": 0,
      "isCash": 0,
      "isCreditMemo": 0,
      "state": 0,
      "maxClientCuota": 0,
      "ledgerAccount": null
    }
  ]
}
```
Obtener una forma de pago
-------------------------

* `GET /v1/payment_types/1.json` retornara una forma de pago específica.

####Respuesta
```json
{
  "href": "http://api.bsale.cl/v1/payment_types/1.json",
  "id": 1,
  "name": "Deposito en Cuenta Corriente",
  "isVirtual": 1,
  "isCheck": 0,
  "maxCheck": null,
  "isCreditNote": 0,
  "isClientCredit": 0,
  "isCash": 0,
  "isCreditMemo": 0,
  "state": 0,
  "maxClientCuota": 0,
  "ledgerAccount": null
}
```
Cantidad de formas de pago.
--------------------------

* `GET /v1/payment_types/count.json`
```json
{
  "count": 3
}
```