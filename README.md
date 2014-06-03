WireCRM
====
Онлайн CRM система для малого бизнеса

https://wirecrm.com


Методы
======
GET - Чтение списка или конкретной записи

POST - Добавление записи

PUT - Обновление записи

DELETE - Удаление записи


Объекты
======
accounts - Организации

contacts - Контакты

deals - Сделки

activities - Активности

leads - Холодные контакты

cases - Обращения

sites - Сайты

expenses - Расходы

notes - Заметки

products - Товары и услуги


Api
======
Для работы необходимо получить API-ключ на странице https://wirecrm.com/profile.

Для авторизации достаточно передать этот ключ в заголовке "X-API-KEY".

```php
//Пример получения списка организаций c помощью API

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
