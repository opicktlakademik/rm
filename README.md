# BPOM Dashboard

### Installation
Install the dependencies and devDependencies.
```sh
$ cd [project dir]
$ composer install
$ composer dumpautoload
```
### Setup
- Edit .env 
--- Set APP_NAME
--- Set APP_URL
--- Set DB Connection
--- Set ASSET_URL (if necessary) 
--- Set .htaccess (as needed)

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
