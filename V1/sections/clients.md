Obtener colección de clientes
-----------------------------

* `GET /v1/clients.json` retornara todos los clientes.

```json
{
  "href": "http://api.bsale.cl/v1/clients.json",
  "count": 112,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/clients/65.json",
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
        "href": "http://api.bsale.cl/v1/clients/65/contacts.json"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/clients/102.json",
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
        "href": "http://api.bsale.cl/v1/clients/102/contacts.json"
      }
    }
  ]
}
```

Obtener un cliente
------------------

* `GET /v1/clients/55.json` retornara un cliente específico.

```json
{
  "href": "http://api.bsale.cl/v1/clients/80.json",
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
    "href": "http://api.bsale.cl/v1/clients/80/contacts.json"
  }
}
```

Obtener colección de contactos de un cliente.
---------------------------------------------

* `GET /v1/clientes/55/contacts.json`

```json
{
  "href": "http://api.bsale.cl/v1/clients/4/contacts.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/clients/4/contacts/31.json",
      "id": 31,
      "firstName": "Andres",
      "lastName": "Villanueva",
      "phone": "2220936",
      "email": "a.villanueva@gmail.cl"
    },
    {
      "href": "http://api.bsale.cl/v1/clients/4/contacts/32.json",
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
  "href": "http://api.bsale.cl/v1/clients/4/contacts/31.json",
  "id": 31,
  "firstName": "Andres",
  "lastName": "Villanueva",
  "phone": "2220936",
  "email": "a.villanueva@gmail.cl"
}
```

Obtener cantidad de clientes.
-------------------------------------

* `GET /v1/clients/count.json`

```json
{
  "count": 66
}
```

Obtener cantidad de clientes.
-------------------------------------

* `GET /v1/clients/count.json`

```json
{
  "count": 66
}
```

Eliminar un cliente virtualmente (desactivarlo).
------------------------------------------------

* `DELETE /v1/clients/30.json` cambia el estado del cliente.

```json
{
  {
    "href": "http://api.bsale.cl/v1/clients/30.json",
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
      "href": "http://api.bsale.cl/v1/payment_types/2.json",
      "id": "2"
    },
    "sale_condition": {
      "href": "http://api.bsale.cl/v1/sale_conditions/1.json",
      "id": "2"
    },
    "contacts": {
      "href": "http://api.bsale.cl/v1/clients/30/contacts.json"
    }
  }
```