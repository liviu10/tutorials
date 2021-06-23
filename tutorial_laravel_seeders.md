# Creating your first Laravel [Seeders](https://laravel.com/docs/8.x/seeding "Laravel Database: Seeders")

Laravel includes the ability to seed your database with test data using seed classes. All seed classes are stored in the <span style="font-style:italic; font-weight:bold;">root > databases > seeders</span> directory.

1. Run this command in Windows PowerShell to create seeders: 
   * this command will create a migration file inside <span style="font-style:italic; font-weight:bold;">migrations</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:seeder UserSeeder</pre>
    </span>

2. Open <span style="font-style:italic; font-weight:bold;">DatabaseSeeder.php</span> file from <span style="font-style:italic; font-weight:bold;">root > databases > seeders</span> directory and add all your seeders PHP script inside <span style="font-style:italic; font-weight:bold;">run()</span> method: 

    <span style="color:red; font-weight:bold;">
        <pre>$this->call([
        UserSeeder::class,
        PostSeeder::class,
        CommentSeeder::class,
    ]);</pre>
    </span>

3. Run these commands in Windows PowerShell to seed the database:
   * the first command will execute all the seeders from <span style="font-style:italic; font-weight:bold;">DatabaseSeeder.php</span>;
   * the second command will execute a certain seeder class;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan db:seed</pre>
        <pre>php artisan db:seed --class=UserSeeder</pre>
    </span>

4. Run this command in Windows PowerShell to re-run the migrations and seeding:
   * this command is useful for completely re-building your database;
   
    <span style="color:red; font-weight:bold;">
        <pre>php artisan migrate:fresh --seed</pre>
    </span>

5. Run this command in Windows PowerShell to drop all your tables from the database:
   * this command will completely erase all your tables from the database;
   
    <span style="color:red; font-weight:bold;">
        <pre>php artisan db:wipe</pre>
    </span>