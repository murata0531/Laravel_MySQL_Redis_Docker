# Laravel_MySQL_Redis_Docker

# 環境

Laravel 8

MySQL 5.7

PHP 7.4

Redis

Apache 2.4

# 構築

```
$ docker-compose up -d --build
```

## mysqlコンテナ
```
$ docker-compose exec db bash
```

## Laravelコンテナ
```
$ docker-compose run --rm web_php74 bash
```
