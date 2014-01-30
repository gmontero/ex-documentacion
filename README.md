# Bsale



## Introducción
El equipo de Bsale a puesto a disposición de la comunidad de desarrolladores  una API, la cual permite acceder  a un conjunto de métodos orientados a facilitar la integración, desde sistemas externos hacia bsale.
Estos  métodos permitirán obtener información desde bsale o enviar información  hacia la aplicación, así por ejemplo se puede  obtener  la lista de productos, generar notas de venta, obtener los documentos generados, etc..
Esta API permite llamadas del tipo REST y utiliza JSON para el envíos y recepción de información.


## Mandar un Request.

Para hacer una llamada a la API, la URL a utilizar debe ser http://api.bsale.cl/api/, seguido del nombre del método solicitado. En este sentido se  debe notar que los métodos están agrupados en sub carpetas, por lo que al nombre del método se el debe anteponer el nombre de la carpeta, así por ejemplo si se requiere obtener la lista de los documentos generados en bsale (lista de factura, boletas etc..) la llamada será:

http://api.bsale.cl/api/documents/search

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
       $url='http://localhost:3000/api/documents/sales/search/';
        //Guarda los filtros de la solicitud en un arrego, el cual debe ser guardado en formato JSON
      $data=json_encode(Array(emission_date_start => '2014-01-02', code_sii=>'33', emission_date_end=>'2014-01-2'));
        //Se conforma el arrego con las variables POST que se mandarán en el Request 
        $fields = array(

                        'access_token' => '09133626ffa3718dfedpolb58be12f7c120ba880cfcfea',
                        'data' => $data                    
				);
        // Se inicializa la llamda CURL, 
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch,CURLOPT_POST, 1);
        curl_setopt($ch,CURLOPT_POSTFIELDS, $fields);
        // Variable en la que se guarda el response
        $response=curl_exec($ch);
        curl_close($ch);

        //Esto es sólo para poder visualizar lo que se está retornando
        print_r($response);
        ?>
    </body>
</html>

```


## Secciones

* [Documentos](https://github.com/gmontero/API-Bsale/blob/master/sections/documentos.mkd)

* [Productos, variantes](https://github.com/gmontero/API-Bsale/blob/master/sections/productos.mkd)

