Clientes
--------

Los clientes .

Obtener colección de clientes
-----------------------------

* `GET /v1/clients.json` will return all active projects.

```json
{
  "href": "http://api.bsale.cl/v1/clients.json",
  "count": 2,
  "limit": 25,
  "offset": 0,
  "items": [
    {
      "href": "http://api.bsale.cl/v1/clients/55.json",
      "id": 55,
      "firstName": "Adriana",
      "lastName": "Rodriguez",
      "code": "1-9",
      "phone": "+52 (442) 2229621",
      "company": "Lees Lab, S.A. de C.V.",
      "note": "",
      "facebook": "",
      "twitter": "",
      "hasCredit": 1,
      "maxCredit": "1000000.0",
      "state": 0,
      "activity": "Desarrollo de Proyectos de Ingenier�a",
      "city": "Queretaro MX",
      "municipality": "Queretaro",
      "address": "Av. Del Parque N�104, Col. Vista Alegre 76090",
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
        "href": "http://api.bsale.cl/v1/clients/55/contacts.json"
      }
    },
    {
      "href": "http://api.bsale.cl/v1/clients/40.json",
      "id": 40,
      "firstName": "Alternattiva S.A.",
      "lastName": "-",
      "code": "79777010-8",
      "phone": "",
      "company": "Alternattiva S.A. -",
      "note": "",
      "facebook": "",
      "twitter": "",
      "hasCredit": 1,
      "maxCredit": "99000000.0",
      "state": 0,
      "activity": "Servicios",
      "city": "Santiago",
      "municipality": "�u�oa",
      "address": "Alcalde Jorge Monckeberg 77",
      "companyOrPerson": 0,
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
        "href": "http://api.bsale.cl/v1/clients/40/contacts.json"
      }
    }
  ]
}

```

Obtener un cliente
------------------

* `GET /v1/clients/55.json` will return all active projects.

```json
{
  "href": "http://api.bsale.cl/v1/clients/55.json",
  "id": 55,
  "firstName": "Adriana",
  "lastName": "Rodriguez",
  "code": "1-9",
  "phone": "+52 (442) 2229621",
  "company": "Lees Lab, S.A. de C.V.",
  "note": "",
  "facebook": "",
  "twitter": "",
  "hasCredit": 1,
  "maxCredit": "1000000.0",
  "state": 0,
  "activity": "Desarrollo de Proyectos de Ingenier�a",
  "city": "Queretaro MX",
  "municipality": "Queretaro",
  "address": "Av. Del Parque N�104, Col. Vista Alegre 76090",
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
    "href": "http://api.bsale.cl/v1/clients/55/contacts.json"
  }
}  

```

