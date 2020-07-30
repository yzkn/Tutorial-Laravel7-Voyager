# Tutorial-Laravel7-Voyager

---

## MySQLサーバーでDB・ユーザーを用意

```sql
create database lara7voydb;

-- MySQLのバージョンが新しければ下の1文のコメントアウトを解除した文のみでOK
create user 'lara7voyuser'@'localhost' identified by 'lara7voypw';
grant all on lara7voydb.* to `lara7voyuser`@`localhost`; -- identified by 'lara7voypw';
```

## Laravelプロジェクトを用意

```ps
$ composer global require laravel/installer
$ laravel new Tutorial-Laravel7-Voyager
```

### 初期設定

- `.env`

```
APP_NAME=Laravel

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=lara7voydb
DB_USERNAME=lara7voyuser
DB_PASSWORD=lara7voypw
```

- `config/app.php`

```
    'timezone' => 'Asia/tokyo',

    'locale' => 'ja',
```

## Voyagerのインストール

```ps
$ cd .\Tutorial-Laravel7-Voyager\
$ composer require tcg/voyager
$ php artisan voyager:install
$ php artisan voyager:admin admin@example.net --create
```

```

 Enter the admin name:
 > Admin

 Enter admin password:
 >

 Confirm Password:
 >

Creating admin account
The user now has full access to your site.
```

```ps
$ php artisan serve
```

http://localhost:8000/admin にアクセス
