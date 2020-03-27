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
