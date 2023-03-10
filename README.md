# Get Public IP

A PHP function to retrieve the public IP address of the server.

```php
function getPublicIP()
{
    $curl = curl_init();
    curl_setopt($curl, CURLOPT_URL, 'http://httpbin.org/ip');
    curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
    $output = curl_exec($curl);
    curl_close($curl);
    $ip = json_decode($output, true);
    return $ip['origin'];
}
```
# Explanation
The function ```getPublicIP``` uses the PHP cURL library to retrieve the public IP address of the server. The cURL library is used to make HTTP requests from the server to the specified URL. In this case, the URL  ```http://httpbin.org/ip```  is used to retrieve the public IP address.

The function sets several options for the cURL request using the ```curl_setopt``` function. The CURLOPT_URL option is set to the URL ```http://httpbin.org/ip``` to specify the URL for the request. The ```CURLOPT_RETURNTRANSFER``` option is set to 1 to return the response from the request as a string, rather than outputting it directly.

The ```cURL``` request is executed using the ```curl_exec``` function, and the result is stored in the $output variable. The ```cURL``` request is then closed using the ```curl_close``` function.

The ```$output``` variable is then decoded using the ```json_decode``` function, which converts the JSON string into a PHP associative array. The public IP address is stored in the origin key of the array, and is returned by the function.
