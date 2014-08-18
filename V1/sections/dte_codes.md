Obtener colección de codigos tributarios
----------------------------------------

* `GET /v1/coins.json` retornara todas los codigos tributarios.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre del codigo tributario.
- *codesii*, filtra por codigo tributario.
- *state*, boolean (0 o 1) indica si las monedas estan activas(0) inactivas(1).

####Ejemplos

* `GET /v1/dte_codes.json?limit=10&offset=0`
* `GET /v1/dte_codes.json?fields=[name,codesii,state]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/dte_codes.json",
  "count": 38,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/dte_codes/28.json",
      "id": 28,
      "name": "AWB (Air Will Bill)",
      "codeSii": "AWB (Air Will Bill)",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/27.json",
      "id": 27,
      "name": "B/L (Conocimiento de embarque)",
      "codeSii": "B/L (Conocimiento de embarque)",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/35.json",
      "id": 35,
      "name": "Boleta",
      "codeSii": "Boleta",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/10.json",
      "id": 10,
      "name": "Boleta Electrónica",
      "codeSii": "Boleta Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/1.json",
      "id": 1,
      "name": "Boleta Exenta",
      "codeSii": "Boleta Exenta",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/11.json",
      "id": 11,
      "name": "Boleta Exenta Electrónica",
      "codeSii": "Boleta Exenta Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/30.json",
      "id": 30,
      "name": "Carta de Porte",
      "codeSii": "Carta de Porte",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/33.json",
      "id": 33,
      "name": "Certificado de Depósito Bolsa Prod. Chile",
      "codeSii": "Certificado de Depósito Bolsa Prod. Chile",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/22.json",
      "id": 22,
      "name": "Contrato",
      "codeSii": "Contrato",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/38.json",
      "id": 38,
      "name": "Declaración de Ingreso (DIN)",
      "codeSii": "Declaración de Ingreso (DIN)",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/26.json",
      "id": 26,
      "name": "DUS",
      "codeSii": "DUS",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/36.json",
      "id": 36,
      "name": "Factura",
      "codeSii": "Factura",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/2.json",
      "id": 2,
      "name": "Factura de Compra",
      "codeSii": "Factura de Compra",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/12.json",
      "id": 12,
      "name": "Factura de Compra Electrónica",
      "codeSii": "Factura de Compra Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/17.json",
      "id": 17,
      "name": "Factura de Exportación Electrónica",
      "codeSii": "Factura de Exportación Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/8.json",
      "id": 8,
      "name": "Factura Electrónica",
      "codeSii": "Factura Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/37.json",
      "id": 37,
      "name": "Factura Exenta",
      "codeSii": "Factura Exenta",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/9.json",
      "id": 9,
      "name": "Factura No Afecta o Exenta Electrónica",
      "codeSii": "Factura No Afecta o Exenta Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/25.json",
      "id": 25,
      "name": "Ficha ChileCompra",
      "codeSii": "Ficha ChileCompra",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/15.json",
      "id": 15,
      "name": "Guía de Despacho",
      "codeSii": "Guía de Despacho",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/16.json",
      "id": 16,
      "name": "Guía de Despacho Electrónica",
      "codeSii": "Guía de Despacho Electrónica",
      "state": 0
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/5.json",
      "id": 5,
      "name": "Liquidación",
      "codeSii": "Liquidación",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/6.json",
      "id": 6,
      "name": "Liquidación Factura",
      "codeSii": "Liquidación Factura",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/7.json",
      "id": 7,
      "name": "Liquidación-Factura Electrónica",
      "codeSii": "Liquidación-Factura Electrónica",
      "state": 1
    },
    {
      "href": "https://api.bsale.cl/v1/dte_codes/29.json",
      "id": 29,
      "name": "MIC/DTA",
      "codeSii": "MIC/DTA",
      "state": 1
    }
  ],
  "next": "https://api.bsale.cl/v1/dte_codes.json?limit=25\u0026offset=25"
}
```
Obtener un codigo tributario
----------------------------

* `GET /v1/dte_codes/8.json` retornara una moneda específica.

####Respuesta
```json
  "href": "https://api.bsale.cl/v1/dte_codes/8.json",
  "id": 8,
  "name": "Factura Electrónica",
  "codeSii": "Factura Electrónica",
  "state": 0
}
```