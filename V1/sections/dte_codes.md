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
  "href": "http://localhost:9292/v1/dte_codes.json",
  "count": 38,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://localhost:9292/v1/dte_codes/28.json",
      "id": 28,
      "name": "AWB (Air Will Bill)",
      "codeSii": 809,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/27.json",
      "id": 27,
      "name": "B/L (Conocimiento de embarque)",
      "codeSii": 808,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/35.json",
      "id": 35,
      "name": "Boleta",
      "codeSii": 35,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/10.json",
      "id": 10,
      "name": "Boleta Electrónica",
      "codeSii": 39,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/1.json",
      "id": 1,
      "name": "Boleta Exenta",
      "codeSii": 38,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/11.json",
      "id": 11,
      "name": "Boleta Exenta Electrónica",
      "codeSii": 41,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/30.json",
      "id": 30,
      "name": "Carta de Porte",
      "codeSii": 811,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/33.json",
      "id": 33,
      "name": "Certificado de Depósito Bolsa Prod. Chile",
      "codeSii": 814,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/22.json",
      "id": 22,
      "name": "Contrato",
      "codeSii": 803,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/38.json",
      "id": 38,
      "name": "Declaración de Ingreso (DIN)",
      "codeSii": 914,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/26.json",
      "id": 26,
      "name": "DUS",
      "codeSii": 807,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/36.json",
      "id": 36,
      "name": "Factura",
      "codeSii": 30,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/2.json",
      "id": 2,
      "name": "Factura de Compra",
      "codeSii": 45,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/12.json",
      "id": 12,
      "name": "Factura de Compra Electrónica",
      "codeSii": 46,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/17.json",
      "id": 17,
      "name": "Factura de Exportación Electrónica",
      "codeSii": 110,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/8.json",
      "id": 8,
      "name": "Factura Electrónica",
      "codeSii": 33,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/37.json",
      "id": 37,
      "name": "Factura Exenta",
      "codeSii": 32,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/9.json",
      "id": 9,
      "name": "Factura No Afecta o Exenta Electrónica",
      "codeSii": 34,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/25.json",
      "id": 25,
      "name": "Ficha ChileCompra",
      "codeSii": 806,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/15.json",
      "id": 15,
      "name": "Guía de Despacho",
      "codeSii": 50,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/16.json",
      "id": 16,
      "name": "Guía de Despacho Electrónica",
      "codeSii": 52,
      "state": 0
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/5.json",
      "id": 5,
      "name": "Liquidación",
      "codeSii": 103,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/6.json",
      "id": 6,
      "name": "Liquidación Factura",
      "codeSii": 40,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/7.json",
      "id": 7,
      "name": "Liquidación-Factura Electrónica",
      "codeSii": 43,
      "state": 1
    },
    {
      "href": "http://localhost:9292/v1/dte_codes/29.json",
      "id": 29,
      "name": "MIC/DTA",
      "codeSii": 810,
      "state": 1
    }
  ],
  "next": "http://localhost:9292/v1/dte_codes.json?limit=25\u0026offset=25"
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
  "codeSii": "33",
  "state": 0
}
```