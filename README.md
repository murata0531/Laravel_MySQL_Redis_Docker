# Laravel_MySQL_Redis_Docker

# 環境

Laravel 8

MySQL 5.7

PHP 7.4

Redis

Apache 2.4

# 構築

`app`ディレクトリを`repository`ディレクトリへ移動

コンテナ立ち上げ

```
$ docker-compose up -d --build
```
laravel初期化
```
$ docker-compose run --rm web_php74 bash

$ cp .env.example .env

$ php artisan key:generate

$ composer install

$ php artisan migrate:fresh
```



## mysqlコンテナ
```
$ docker-compose exec db bash
```

## Laravelコンテナ
```
$ docker-compose run --rm web_php74 bash
```
