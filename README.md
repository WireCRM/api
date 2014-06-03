WireCRM
======
Онлайн CRM система для малого бизнеса


Примеры работы с API сервиса
=====

```php
//Пример получения списка организаций

$url = 'https://wirecrm.com/api/accounts';
$apikey = 'paste api key';

$headers = array(
	"Content-Type: application/json",
	"X-API-KEY: " . $apikey
);

$handle = curl_init(); 
curl_setopt($handle, CURLOPT_URL, $url);
curl_setopt($handle, CURLOPT_HTTPHEADER, $headers);
curl_setopt($handle, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);

$data = curl_exec($handle);
curl_close($handle);

$array = json_decode($data);

echo '<pre>';
print_r($array);
```
