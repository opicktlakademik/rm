# BPOM Dashboard

### Commit Note 27/03/2020 17:47
- Add migrations and seeders
- Add user level
- Before going any further, please make sure everything is ok by running command as follow

```sh
$ cd [project dir]
$ composer install
$ php artisan config:cache
```

- Change data_product.price data type. in order to be able run the migration run command below

```sh
$ cd [project dir]
$ php artisan migrate --path=database/migrations/2020_03_27_093945_drop_column_price.php
$ php artisan migrate --path=database/migrations/2020_03_27_094143_add_column_price_after_delete.php
```
- Add roles table.  to run the migration hit command below

```sh
$ cd [project dir]
$ php artisan migrate --path=database/migrations/2020_03_27_095211_create_roles_table.php
```

- Add role_code column to users. Run the migration command as follow
```sh
$ cd [project dir]
$ php artisan migrate --path=database/migrations/2020_03_27_100751_add_role_code_column_to_users_table.php
```

- Roles Seeder
```sh
$ cd [project dir]
$ php artisan db:seed --class=RolesSeeder
```

- Super Admin Level Seeder
```sh
$ cd [project dir]
$ php artisan db:seed --class=AdminSeeder
```

- Operator Level Seeder
```sh
$ cd [project dir]
$ php artisan db:seed --class=OperatorSeeder
```

### Commit Note 27/03/2020 00:00
- Add migrations
- Before migrating don't forget to run

```sh
$ cd [project dir]
$ composer install
```

### Installation
Install the dependencies and devDependencies.
```sh
$ cd [project dir]
$ composer install
$ composer dumpautoload
```
### Setup ENV
- Set CRAWLER_URL
- Set APP_NAME
- Set APP_URL
- Set DB Connection
- Set ASSET_URL (if necessary) 
- Set .htaccess (as needed)

### Migration
Laravel default
- 2014_10_12_000000_create_users_table.php (users table)
- 2014_10_12_100000_create_password_resets_table.php  (password resets table)
- 2019_08_19_000000_create_failed_jobs_table.php (failed jobs table)

Main migration. This migration is necessary and must be run

| Table             | Migration                                             |
| ----------------- |:-----------------------------------------------------:|
| marketplace       | 2020_03_11_130324_create_marketplace_table.php        |
| stores            | 2020_03_23_120816_create_stores_table.php             |
| keywords          | 2020_03_23_121707_create_keywords_table.php           |
| products          | 2020_03_23_130727_create_products_table.php           |
| data_product      | 2020_03_23_131548_create_data_products_table.php      |
| status            | 2020_03_23_204221_create_status_table.php             |
| links             | 2020_03_23_204420_create_links_table.php              |
| reported_products | 2020_03_23_204727_create_reported_products_table.php  |


note:
- if error occurs during migration, please empty your database first.
- Alternative 2: run migration by specifying the file. (it can be found under: project/database/migrations/)
    ```sh
    $ cd [project dir]
    $ php artisan migrate --path=/database/migrations/fileName.php
    ```
- alternative 3: rollback migration and migrate again
    ```sh
    $ cd [project dir]
    $ php artisan migrate:rollback
    $ php artisan migrate
    ```
- alternative 4: refresh the migration by running
    ```sh
    $ cd [project dir]
    $ php artisan migrate:refresh
    ```
