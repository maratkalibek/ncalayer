# Работа с NCALayer

## Как работает NCALayer

NCALayer представляет из себя веб-сервер который слушает по адресу 127.0.0.1:13579.

## Функционал
- Выбор ключа
- Считывание данных с ключа
- Подписание данных (XML, бинарных данных)

## Запросы к NCALayer

### Открыть окно выбора ключа

Запрос
```
{
  'method': "browseKeyStore",
  'args': ['PKCS12', 'P12', '/home/marat/_WORK']
}
```
Ответ: Выбранный ключ
```
{"result":"/home/user/GOSTKZ.p12","errorCode":"NONE"}
{"errorCode":"NONE"}
```

### Список ключей в файле

Запрос
```
{
  'method': 'getKeys',
  'args': ['PKCS12', '/home/user/GOSTKZ.p12', '123456', 'ALL']
}
```
Ответ: список ключей в файле
```
{
  "result":"ГОСТ|ТЕСТ ТЕСТОВ|4b3fb466a47e79a92f282cdfa7b597a9064fb6f7|0bb6731d728439c4970e441a670689a55008e39f","errorCode":"NONE"}
```
