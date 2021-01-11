# OpsDash Dockerfile

Это Dockefile для простой настройки [OpsDash] (https://www.opsdash.com) -сервера с докером.

## Установка и настройка

- Создайте учетную запись на [OpsDash] (https://www.opsdash.com).
- Войдите в OpsDash и загрузите текущий файл `.dep` для сервера в каталог` dep` (вы можете загрузить файл, только если вы вошли в систему). На момент написания это `dep / opsdash-server_1.2.2_amd64.deb`.
- Измените конфигурацию в `server.cfg` под свои нужды.

## Запуск с докером

Создайте образ докера:

Баш
docker build -t opsdash-server .
``

Запускаем контейнер:

Баш
docker run -d -p 8086:8086 -p 6273:6273 -p 6273:6273/udp opsdash-server
``

## Запуск с помощью docker-compose

``
docker-compose -p opsdash-server build
docker-compose -p opsdash-server up
``