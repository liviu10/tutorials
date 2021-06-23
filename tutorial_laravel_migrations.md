# Creating your first Laravel [Migrations](https://laravel.com/docs/8.x/migrations "Laravel Database: Migrations")

Migrations are like version control for your database, allowing your team to define and share the application's database schema definition. The migrations files are stored in <span style="font-style:italic; font-weight:bold;">root > databases > migrations</span>. The newly created migration file will contain a PHP class with two methods - <span style="font-style:italic; font-weight:bold;">up()</span> and <span style="font-style:italic; font-weight:bold;">down()</span>. The first one is the actual table schema that is going to be used to create the table in the database. The second one will drop the schema if the table is already created in the database.

1. Run these commands in Windows PowerShell to create migrations: 
   * the first command will create a migration file inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the second command will create a migration file in a subdirectory of <span style="font-style:italic; font-weight:bold;">migrations</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:migration create_users_table</pre>
        <pre>php artisan make:migration create_table1_table --path "/database/migrations/subdirectoryInMigrations"</pre>
    </span>

2. Run these commands in Windows PowerShell to execute the newly created migrations:
   * the first command will execute all the migrations inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the second command will execute a single migration inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the third command will execute all the migrations from a subdirectory inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan migrate</pre>
        <pre>php artisan migrate --path=/database/migrations/2021_01_30_181511_create_table3_table.php</pre>
        <pre>php artisan migrate --path=/database/migrations/subdirectoryInMigrations</pre>
    </span>

3. Run these commands in Windows PowerShell to check the status of your migrations:
   * the first command will check the status of all your migrations inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the second command will check the status of all your migrations from a subdirectory inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan migrate:status</pre>
        <pre>php artisan migrate:status --path "/database/migrations/subdirectoryInMigrations"</pre>
    </span>

4. Run these commands in Windows PowerShell to rollback / reset your migrations:
   * the first command will rollback all your migrations inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the second command will rollback a certain number of migrations inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the third command will reset all your migrations inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the forth command will rollback all your migrations from a subdirectory inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the fifth command will rollback a certain number of migrations from a subdirectory inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;
   * the sixth command will reset all your migrations from a subdirectory inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan migrate:rollback</pre>
        <pre>php artisan migrate:rollback --step=5</pre>
        <pre>php artisan migrate:reset</pre>
        <pre>php artisan migrate:rollback --path "/database/migrations/test"</pre>
        <pre>php artisan migrate:rollback --step=5 --path "/database/migrations/test"</pre>
        <pre>php artisan migrate:reset --path "/database/migrations/test"</pre>
    </span>