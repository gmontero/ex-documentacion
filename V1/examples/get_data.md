GET con PHP
----------
```php
        <?php
            $url='https://api.bsale.cl/v1/clients.json';
            $access_token='tutokendeacceso';


            // Initialize the cURL session with the request URL
            $session = curl_init($url);


            // Tell cURL to return the request data
            curl_setopt($session, CURLOPT_RETURNTRANSFER, true);

            // Set the HTTP request authentication headers
            $headers = array(
                'access_token: ' . $access_token
            );
            curl_setopt($session, CURLOPT_HTTPHEADER, $headers);

            // Execute cURL on the session handle
            $response = curl_exec($session);

            // Close the cURL session
            curl_close($session);

            //Esto es sólo para poder visualizar lo que se está retornando
            print_r($response);
        ?>
```