# Bsale



## Introducción
El equipo de Bsale a puesto a disposición de la comunidad de desarrolladores  una API, la cual permite acceder  a un conjunto de métodos orientados a facilitar la integración, desde sistemas externos hacia bsale.
Estos  métodos permitirán obtener información desde bsale o enviar información  hacia la aplicación, así por ejemplo se puede  obtener  la lista de productos, generar notas de venta, obtener los documentos generados, etc..
Esta API permite llamadas del tipo REST y utiliza JSON para el envíos y recepción de información.


## Mandar un Request.

Para hacer una llamada a la API, la URL a utilizar debe ser http://app.bsale.cl/api/, seguido del nombre del método solicitado. En este sentido se  debe notar que los métodos están agrupados en sub carpetas, por lo que al nombre del método se el debe anteponer el nombre de la carpeta, así por ejemplo si se requiere obtener la lista de los documentos generados en bsale (lista de factura, boletas etc..) la llamada será:

http://app.bsale.cl/api/documents/search

Noten que la carpeta "Documents" están todos los métodos asociados al manejo de documentos.

## Seguridad

Para autenticar un request se utiliza la autenticación básica de http, mediante el envío  de un token, el cual deberá acompañar cada llamada.
Dado que que la API se encuentra en estado "Beta", el token deberá ser solicitado al equipo de bsale (crojas@imaginex.cl).
De esta manera dentro de las variables POST de la llamada se deberá agregar "access_token", con el token de acceso entregado.
Es importante notar que este token es único para cada empresa-usuario, y el movimiento quedará asociado al usuario relacionado con el "access_token" entregado.

Por ejemplo si se requiere obtener la lista de docuemntos generados para el día 19-10-2013 de todas las sucursulas la llamada debería  ser:

```php
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title></title>
    </head>
    <body>
        <?php
        $url='http://http://app.bsale.cl/api/documents/sales/search';
        $data=json_encode(Array(emission_date => '2013-10-19'));
        $fields = array(
                        'access_token' => urlencode('09133626ffa3718dfedb58be12f7cba880cfcfea'),
                        'data' => urlencode($data)
                        
				);
        foreach($fields as $key=>$value) { $fields_string .= $key.'='.$value.'&'; }
        rtrim($fields_string, '&'); 
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch,CURLOPT_POST, count($fields));
        curl_setopt($ch,CURLOPT_POSTFIELDS, $fields_string);

        $response=curl_exec($ch);
        curl_close($ch);


        print_r($response);
        php?>
    </body>
</html>
```


## Secciones

* [Productos, variantes](https://github.com/gmontero/API-Bsale/blob/master/sections/productos.mkd)

### Autentificación

Para poder acceder a la API se necesita un access token entregado por bsale, este token es unico para cada empresa.

```
PTP0EDLAMATGNV8Q81EZGEZMLZ9UJYR
```

### Haciendo una petición

una vez obtenido el access token se puede realizar una peticion a la API de bsale con el metodo POST de la siguente forma:

```
http://api.bsale.cl/api/documents/sales?access_token='token_empresa'
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
