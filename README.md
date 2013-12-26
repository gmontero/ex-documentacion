# Bsale

La API de Bsale esta implementada JSON a través de HTTP, en etapa de desarrollo.

## Introducción

Con la API de Bsale, se podra acceder a los distintos recursos de del sistema, como los productos, variantes, documentos etc.

## Secciones

### [Prestashop](https://github.com/gmontero/API-Bsale/blob/master/sections/prestashop.mkd)

### Autentificación

Para poder acceder a la API se necesita un access token entregado por bsale, este token es unico para cada empresa.

```
PTP0EDLAMATGNV8Q81EZGEZMLZ9UJYR
```

### Haciendo una petición

una vez obtenido el access token se puede realizar una peticion a la API de bsale con el metodo POST de la siguente forma:

```
http://api.bsale.cl/api/documents/sales?access_token='token de la empresa'
```

La respuesta de Bsale llegara en formato JSON:

```
[
  {
    "emission_date": "2013-11-04",
    "send_status": "0",
    "read_date": "0000-00-00",
    "recipients": "",
    "client_email": "",
    "is_credit_note": "0",
    "client_id": 0,
    "coin_id": "1",
    "iva_amount": "3495",
    "salesman_name": "Demo Bsale",
    "client_name": "Sin Cliente",
    "salesman_id": 2,
    "total_attachments": "0",
    "total_amount": 21890.0,
    "tax_amount": 3495.0,
    "has_received": "0",
    "document_id": 1984,
    "client_code": "",
    "office_id": 2,
    "document_type_id": 1,
    "coin_symbol": "$",
    "is_sales_note": "0",
    "office_destination_id": "0",
    "document_type_name": "Boleta",
    "total_round": "0",
    "document_use": "0",
    "link_xml": null,
    "decimal_currency": "0",
    "observations": "0",
    "forwarding_recipients": "",
    "payment": "0",
    "is_shipping": "0",
    "exempt_amount": 0.0,
    "office_destination": "",
    "office_cost_center": "",
    "send_id": "0",
    "expiration_date": "2013-11-04",
    "document_state": 0,
    "office_name": "Casa Matriz",
    "total_debt": "0",
    "code_sii": "",
    "send_date": "0000-00-00",
    "net_amount": 18395.0,
    "shipping_type_name": "",
    "adicional_tax_amount": "0",
    "details": [
      {
        "cart_item_id": 7056,
        "total_amount": 9990.0,
        "unit_amount": 8394.95798319328,
        "tax_amount": 1595.0,
        "item_cost_center": null,
        "discount_percentage": 0.0,
        "item_sku": "7450071009359",
        "item_ledger_account": null,
        "quantity": 1.0,
        "item_name": "polera brillo ",
        "exempt_amount": 0,
        "office_cost_center": "",
        "tax_percentage": "0.19",
        "allows_decimal": "0",
        "net_amount": 8395.0,
        "exchange_rate": 1.0
      },
      {
        "cart_item_id": 7057,
        "total_amount": 11900.0,
        "unit_amount": 10000.0,
        "tax_amount": 1900.0,
        "item_cost_center": "",
        "discount_percentage": 0.0,
        "item_sku": "69823238017480",
        "item_ledger_account": "",
        "quantity": 1.0,
        "item_name": "Polera Blanca ",
        "exempt_amount": 0,
        "office_cost_center": "",
        "tax_percentage": "0.19",
        "allows_decimal": "0",
        "net_amount": 10000.0,
        "exchange_rate": 1.0
      }
    ],
    "is_electronic_document": "0",
    "link_pdf": "",
    "document_number": 2503659
  }
]

```