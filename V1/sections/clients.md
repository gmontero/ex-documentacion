Obtener colección de clientes
-----------------------------

* `GET /v1/clients.json` retornara todos los clientes.

####Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, si no se envia el limit es 25.
- *offset*, permite paginar los items de una respuesta JSON, si no se envia el offset es 0.
- *fields*, solo devolver atributos especificos de un recurso
- *expand*, permite expandir instancias y colecciones.
- *code*, Permite filtrar por rut del cliente.
- *firstname*, filtra los clientes por nombre.
- *lastname*, filtra los clientes por apellido.
- *email*, filtra los clientes por email.
- *paymenttypeid*, recupera los clientes con forma de pago.
- *salesconditionid*, recupera los clientes por la condicion de venta.
- *state*, boolean (0 o 1) indica si los clientes estan activos(0) inactivos (1).

####Ejemplos

* `GET /v1/clients.json?limit=10&offset=0`
* `GET /v1/clients.json?fields=[firstname,lastname]`
* `GET /v1/clients.json?code=1-9`
* `GET /v1/clients.json?paymenttypeid=1`
* `GET /v1/clients.json?expand=[contacts,payment_type]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/clients.json",
  "count": 112,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/clients/65.json",
      "id": 65,
      "firstName": "a",
      "lastName": "sa",
      "code": "92.341.000-7",
      "phone": "",
      "company": "a sa",
      "note": "",
      "facebook": "",
      "twitter": "",
      "hasCredit": 1,
      "maxCredit": "10000.0",
      "state": 1,
      "activity": "Sin Giro",
      "city": "",
      "municipality": "",
      "address": "",
      "companyOrPerson": 0,
      "sendDte": 0,
      "prestashopClienId": 0,
      "contacts": {
        "href": "https://api.bsale.cl/v1/clients/65/contacts.json"
      }
    },
    {
      "href": "https://api.bsale.cl/v1/clients/102.json",
      "id": 102,
      "firstName": "Adriana",
      "lastName": "Talhouk",
      "code": "",
      "phone": "",
      "company": "Adriana Talhouk",
      "note": null,
      "facebook": null,
      "twitter": "",
      "hasCredit": 1,
      "maxCredit": "10000.0",
      "state": 0,
      "activity": "Sin Giro",
      "city": "",
      "municipality": "",
      "address": "",
      "companyOrPerson": 0,
      "sendDte": 0,
      "prestashopClienId": 0,
      "contacts": {
        "href": "https://api.bsale.cl/v1/clients/102/contacts.json"
      }
    }
  ]
}
```
Obtener un cliente
------------------

* `GET /v1/clients/55.json` retornara un cliente específico.

####Parametros

- *expand*, permite expandir instancias y colecciones.

####Ejemplos

* `GET /v1/clients/55.json?expand=[contacts,payment_type]`

####Respuesta
```json
{
  "href": "https://api.bsale.cl/v1/clients/80.json",
  "id": 80,
  "firstName": "juanito",
  "lastName": "mena",
  "code": "",
  "phone": "",
  "company": "juanito mena",
  "note": null,
  "facebook": null,
  "twitter": "",
  "hasCredit": 1,
  "maxCredit": "10000.0",
  "state": 0,
  "activity": "Sin Giro",
  "city": "",
  "municipality": "",
  "address": "",
  "companyOrPerson": 0,
  "sendDte": 0,
  "prestashopClienId": 0,
  "contacts": {
    "href": "https://api.bsale.cl/v1/clients/80/contacts.json"
  }
}
```
Obtener colección de contactos de un cliente.
---------------------------------------------

* `GET /v1/clientes/55/contacts.json`
```json
{
  "href": "https://api.bsale.cl/v1/clients/4/contacts.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "https://api.bsale.cl/v1/clients/4/contacts/31.json",
      "id": 31,
      "firstName": "Andres",
      "lastName": "Villanueva",
      "phone": "2220936",
      "email": "a.villanueva@gmail.cl"
    },
    {
      "href": "https://api.bsale.cl/v1/clients/4/contacts/32.json",
      "id": 32,
      "firstName": "Juana ",
      "lastName": "Jeldres",
      "phone": "2220928",
      "email": "recepcion@gmail.cl"
    }
  ]
}
```
Obtener un de contacto de un cliente.
-------------------------------------

* `GET /v1/clientes/4/contacts/31.json`
```json
{
  "href": "https://api.bsale.cl/v1/clients/4/contacts/31.json",
  "id": 31,
  "firstName": "Andres",
  "lastName": "Villanueva",
  "phone": "2220936",
  "email": "a.villanueva@gmail.cl"
}
```
Cantidad de clientes.
-----------------------------

* `GET /v1/clients/count.json`
```json
{
  "count": 66
}
```
Crea un cliente.
--------------------

* `POST /v1/clients.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "facebook": "",
  "municipality": "Las Condes",
  "phone": "66287196",
  "activity": "Venta de ropa",
  "city": "Santiago",
  "maxCredit": 100000,
  "hasCredit": 1,
  "lastName": "Muñoz",
  "note": "Cliente premiun",
  "firstName": "Marcela",
  "company": "Particular",
  "address": "Los trigales 372",
  "email": "mmunoz@.email.cl",
  "twitter": "",
  "code": "2-7"
}
```
####Respuesta
```json
{
  "companyOrPerson": 0,
  "address": "Los trigales 372",
  "lastName": "Muñoz",
  "sendDte": 0,
  "city": "Santiago",
  "state": 0,
  "twitter": "",
  "firstName": "Marcela",
  "id": 67,
  "municipality": "Las Condes",
  "maxCredit": 100000.0,
  "note": "Cliente premiun",
  "phone": "66287196",
  "contacts": {
    "href": "https://localhost:9292/v1/clients/67/contacts.json"
  },
  "prestashopClienId": 0,
  "activity": "Venta de ropa",
  "hasCredit": 1,
  "facebook": "",
  "company": "Particular",
  "code": "2-7",
  "href": "https://localhost:9292/v1/clients/67.json"
}
```
Modifica un cliente.
--------------------

* `PUT /v1/clients/67.json`

Se debe enviar un Json con la siguiente esctructura.
```json
{
  "id": "67",
  "facebook": "",
  "municipality": "Puerto Montt",
  "phone": "66287196",
  "activity": "Venta de ropa",
  "city": "Puerto Montt",
  "maxCredit": 100000,
  "hasCredit": 1,
  "lastName": "Muñoz",
  "note": "Cliente premiun",
  "firstName": "Marcela",
  "company": "Particular",
  "address": "Los trigales 372",
  "email": "mmunoz@.email.cl",
  "twitter": ""
}
```
####Respuesta
```json
{
  "companyOrPerson": 0,
  "address": "Los trigales 372",
  "lastName": "Muñoz",
  "sendDte": 0,
  "city": "Puerto Montt",
  "state": 0,
  "twitter": "",
  "firstName": "Marcela",
  "id": 67,
  "municipality": "Puerto Montt",
  "maxCredit": 100000.0,
  "note": "Cliente premiun",
  "phone": "66287196",
  "contacts": {
    "href": "https://localhost:9292/v1/clients/67/contacts.json"
  },
  "prestashopClienId": 0,
  "activity": "Venta de ropa",
  "hasCredit": 1,
  "facebook": "",
  "company": "Particular",
  "code": "2-7",
  "href": "https://localhost:9292/v1/clients/67.json"
}
```
Eliminar un cliente virtualmente (desactivar).
----------------------------------------------

* `DELETE /v1/clients/30.json` cambia el estado del cliente.
```json
{
  "href": "https://api.bsale.cl/v1/clients/30.json",
  "id": 30,
  "firstName": "Andres",
  "lastName": "Vasquez",
  "code": "1-9",
  "phone": "220800",
  "company": "Servicios varios",
  "note": "",
  "facebook": "",
  "twitter": "",
  "hasCredit": 1,
  "maxCredit": "9100",
  "state": 1,
  "activity": "",
  "city": "Puerto Montt",
  "municipality": "Puerto Montt",
  "address": "Avda. Diego Portales 100",
  "companyOrPerson": 1,
  "sendDte": 0,
  "prestashopClienId": 0,
  "payment_type": {
    "href": "https://api.bsale.cl/v1/payment_types/2.json",
    "id": "2"
  },
  "sale_condition": {
    "href": "https://api.bsale.cl/v1/sale_conditions/1.json",
    "id": "2"
  },
  "contacts": {
    "href": "https://api.bsale.cl/v1/clients/30/contacts.json"
  }
}
```