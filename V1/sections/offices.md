Obtener colección de sucursales
-------------------------------

* `GET /v1/offices.json` retornara todas las sucursales.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *name*, Permite filtrar por nombre de las sucursales.
- *address*, filtra por direccion dde las sucursales.
- *country*, filtra por pais de las sucursales.
- *city*, filtra por ciudad de las sucursales.
- *municipality*, filtra por comuna de las sucursales.
- *costcenter*, filtra centro de costo de las sucursales.
- *state*, boolean (0 o 1) indica si las sucursales estan activas(0) inactivas (1).

####Ejemplos

* `GET /v1/offices.json?limit=10&offset=0`
* `GET /v1/offices.json?fields=[name,address,costcenter]`
* `GET /v1/offices.json?state=0`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/offices.json",
  "count": 4,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/offices/2.json",
      "id": 2,
      "name": "Casa Matriz - Puerto Varas",
      "description": "",
      "address": "Direccion de la sucursal",
      "latitude": "",
      "longitude": "",
      "isVirtual": 0,
      "country": "",
      "municipality": "",
      "city": "",
      "zipCode": "",
      "costCenter": "",
      "state": 0,
      "imagestionCellarId": 0
    },
    {
      "href": "https://api.bsale.cl/v1/offices/3.json",
      "id": 3,
      "name": "Casa Matriz Pto. Varas en ($)",
      "description": "",
      "address": "Direccion de la sucursal",
      "latitude": "",
      "longitude": "",
      "isVirtual": 0,
      "country": "",
      "municipality": "",
      "city": "",
      "zipCode": "",
      "costCenter": "",
      "state": 1,
      "imagestionCellarId": 0
    },
    {
      "href": "https://api.bsale.cl/v1/offices/4.json",
      "id": 4,
      "name": "Internacional",
      "description": "",
      "address": "",
      "latitude": "",
      "longitude": "",
      "isVirtual": 0,
      "country": "",
      "municipality": "",
      "city": "",
      "zipCode": "",
      "costCenter": "",
      "state": 0,
      "imagestionCellarId": 0
    },
    {
      "href": "https://api.bsale.cl/v1/offices/1.json",
      "id": 1,
      "name": "Tienda Online",
      "description": "",
      "address": "",
      "latitude": "",
      "longitude": "",
      "isVirtual": 1,
      "country": null,
      "municipality": "",
      "city": null,
      "zipCode": null,
      "costCenter": "",
      "state": 1,
      "imagestionCellarId": 0
    }
  ]
}
```
Obtener una sucursal
--------------------

* `GET /v1/offices/1.json` retornara una sucursal específica.

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/offices/1.json",
  "id": 1,
  "name": "Tienda Online",
  "description": "",
  "address": "",
  "latitude": "",
  "longitude": "",
  "isVirtual": 1,
  "country": null,
  "municipality": "",
  "city": null,
  "zipCode": null,
  "costCenter": "",
  "state": 1,
  "imagestionCellarId": 0
}
```
Cantidad de sucursales
----------------------

* `GET /v1/offices/count.json`
```json
{
  "count": 4
}
```
Crea una sucursal
-----------------

* `POST /v1/offices.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "longitude": "",
  "zipCode": "000000",
  "name": "Imaginex",
  "latitude": "",
  "isVirtual": 0,
  "address": "Santa Rosa 402",
  "country": "Chile",
  "municipality": "Puerto Varas",
  "city": "Puerto Varas",
  "costCenter": "25",
  "description": "Oficina"
}
```
####Respuesta
```json
{
  "zipCode": "000000",
  "longitude": "",
  "state": 0,
  "latitude": "",
  "name": "Imaginex",
  "isVirtual": 0,
  "href": "https://api.bsale.cl/v1/offices/5.json",
  "address": "Santa Rosa 402",
  "id": 5,
  "city": "Puerto Varas",
  "municipality": "Puerto Varas",
  "country": "Chile",
  "costCenter": "25",
  "description": "Oficina",
  "imagestionCellarId": 0
}
```
Modifica una sucursal
---------------------

* `PUT /v1/offices/5.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "id":"97",
  "name": "Imaginex TI",
  "address": "Santa Rosa 402 oficina B" 
}
```
####Respuesta
```json
{
  "zipCode": "000000",
  "longitude": "",
  "state": 0,
  "latitude": "",
  "name": "Imaginex TI",
  "isVirtual": 0,
  "href": "https://api.bsale.cl/v1/offices/5.json",
  "address": "SSanta Rosa 402 oficina B",
  "id": 5,
  "city": "Puerto Varas",
  "municipality": "Puerto Varas",
  "country": "Chile",
  "costCenter": "25",
  "description": "Oficina",
  "imagestionCellarId": 0
}
```
Eliminar una sucursal virtualmente (desactivar)
-----------------------------------------------

* `DELETE /v1/offices/5.json` cambia el estado de la sucursal.
```json
{
  "zipCode": "000000",
  "longitude": "",
  "state": 1,
  "latitude": "",
  "name": "Imaginex TI",
  "isVirtual": 0,
  "href": "https://api.bsale.cl/v1/offices/5.json",
  "address": "SSanta Rosa 402 oficina B",
  "id": 5,
  "city": "Puerto Varas",
  "municipality": "Puerto Varas",
  "country": "Chile",
  "costCenter": "25",
  "description": "Oficina",
  "imagestionCellarId": 0
}
```