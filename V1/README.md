Bsale API
---------
[RESTful] API desarrollada para el sistema Bsale, los servicios solo trabajan con [JSON].

Convenciones de la API
-----------------------------
* Peticiones sobre https
* Usar sustantivos, no verbos.
* Dos urls base por recurso "/clients.json", "clients/1.json"
* Siempre usar el nombre del recurso en plural.
* Enviar la url del rucurso.
* Respuesta JSON en camelCase
* respuesta JSON en ingles.
* Manejo de versiones en la url.
* Manejo de errores y estados.
* Paginacion de la respuesta JSON.
* Permitir acceder a las asociones de un recurso a traves de la variable expand en una sola peticion.
* Permitir devolver solo los atributos requeridos a traves de la variable fields.
* Las fechas se trabaja como enteros por ejemplo 1388545200 corresponde a la fecha '2014-01-01'.

Mandar un Request
-----------------
Las peticones son RESTful por lo que se debe especificar el metodo a utilzan GET, PUT, POST, DELETE, ademas se debe enviar
en la cabecera del request el token de acceso que permite la autentificacion en la API.

```sh
curl -i -H "access_token: tutokendeacceso" -X GET http://api.bsale.cl/v1/clients.json
```

Documentacion
-------------
* [Clientes.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/clients.md)
* [Condiciones de venta.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/sale_conditions.md)
* [Descuentos.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/discounts.md)
* [Documentos.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/documents.md)
* [Documentos de terceros.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/third_party_documents.md)
* [Formas de pago.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/payment_types.md)
* [Impuestos.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/taxes.md)
* [Listas de precio.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/price_lists.md)
* [Monedas.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/coins.md)
* [Pagos.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/payments.md)
* [Productos.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/products.md)
* [Stocks.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/stocks.md)
* [Sucursales.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/offices.md)
* [Tipos de documento.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/document_types.md)
* [Tipos de libro.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/book_types.md)
* [Tipos de producto.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/product_types.md)
* [Variantes.](https://github.com/gmontero/API-Bsale/blob/master/V1/sections/variants.md)

[RESTful]:http://es.wikipedia.org/wiki/Representational_State_Transfer
[JSON]:http://www.json.org/