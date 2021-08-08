# Creating your first Laravel [Migrations](https://laravel.com/docs/8.x/migrations "Laravel Database: Migrations")

Migrations are like version control for your database, allowing your team to define and share the application's database schema definition. The migrations files are stored in <span style="font-style:italic; font-weight:bold;">root > databases > migrations</span>. The newly created migration file will contain a PHP class with two methods - <span style="font-style:italic; font-weight:bold;">up()</span> and <span style="font-style:italic; font-weight:bold;">down()</span>. The first one is the actual table schema that is going to be used to create the table in the database. The second one will drop the schema if the table is already created in the database.

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">                 (create a migration file):</span> php artisan make:migration create_users_table
<span style="color:white; font-weight:normal;">       (migration file with specific path):</span> php artisan make:migration create_table1_table --path "/database/migrations/subdirectoryInMigrations"
<span style="color:white; font-weight:normal;">             (execute all migration files):</span> php artisan migrate
<span style="color:white; font-weight:normal;">   (execute migrations with specific path):</span> php artisan migrate --path=/database/migrations/2021_01_30_181511_create_table3_table.php
<span style="color:white; font-weight:normal;">    (execute migrations from subdirectory):</span> php artisan migrate --path=/database/migrations/subdirectoryInMigrations
<span style="color:white; font-weight:normal;">                  (check migration status):</span> php artisan migrate:status
<span style="color:white; font-weight:normal;">(check migration status from subdirectory):</span> php artisan migrate:status --path "/database/migrations/subdirectoryInMigrations"
<span style="color:white; font-weight:normal;">                  (rollback all migration):</span> php artisan migrate:rollback
<span style="color:white; font-weight:normal;">   (rollback migrations a number of steps):</span> php artisan migrate:rollback --step=5
<span style="color:white; font-weight:normal;">                     (reset all migration):</span> php artisan migrate:reset</pre>
</span>