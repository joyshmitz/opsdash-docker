# OpsDash Dockerfile

Это Dockefile для простой настройки [OpsDash] (https://www.opsdash.com) -сервера с докером.

## Установка и настройка

- Создайте учетную запись на [OpsDash] (https://www.opsdash.com).
- Файл сервера в `dep`-каталог `dep/opsdash-server_1.12.2_amd64.deb`.
- Перед запуском сервера OpsDash вы должны отредактировать файл конфигурации на /etc/opsdash/server.cfg, по крайней мере, чтобы убедиться, что настройки по умолчанию приемлемы.
- Агент скачать здесь `https://packages.rapidloop.com/downloads/opsdash-agent_1.12.2_amd64.deb`
- Перед запуском агента необходимо отредактировать файл конфигурации агента в `/etc/opsdash/agent.cfg`.

## Создание и запуск в докере

Создайте образ докера:

```bash
docker build -t opsdash-server .
```

Запускаем контейнер:

```bash
docker run -d -p 8086:8086 -p 6273:6273 -p 6273:6273/udp opsdash-server
```

## Запуск с помощью docker-compose

```bash
docker-compose -p opsdash-server build
docker-compose -p opsdash-server up
```