# Creating your first Laravel [Models](https://laravel.com/docs/8.x/eloquent#generating-model-classes "Laravel Database: Models")

Laravel includes Eloquent, an object-relational mapper (ORM) that makes it enjoyable to interact with your database. When using Eloquent, each database table has a corresponding "Model" that is used to interact with that table. In addition to retrieving records from the database table, Eloquent models allow you to insert, update, and delete records from the table as well.

1. Run this command in Windows PowerShell to create a model: 
   * this command will create a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model User</pre>
    </span>

2. Run this command in Windows PowerShell to create a model and a migration: 
   * this command will create a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder and a migration file inside <span style="font-style:italic; font-weight:bold;">root > database > migrations</span> folder;
   * the second command is the shorthand of the first line;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model Flight --migration</pre>
        <pre>php artisan make:model Flight -m</pre>
    </span>

3. Run this command in Windows PowerShell to create a model and a factory: 
   * this command will create a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder and a factory file inside <span style="font-style:italic; font-weight:bold;">root > database > factories</span> folder;
   * the second command is the shorthand of the first line;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model Flight --factory</pre>
        <pre>php artisan make:model Flight -f</pre>
    </span>

4. Run this command in Windows PowerShell to create a model and a seeder: 
   * this command will create a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder and a seeder file inside <span style="font-style:italic; font-weight:bold;">root > database > seeders</span> folder;
   * the second command is the shorthand of the first line;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model Flight --seed</pre>
        <pre>php artisan make:model Flight -s</pre>
    </span>

5. Run this command in Windows PowerShell to create a model and a controller: 
   * this command will create a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder and a controller file inside <span style="font-style:italic; font-weight:bold;">app > http > controllers</span> folder;
   * the second command is the shorthand of the first line;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model Flight --controller</pre>
        <pre>php artisan make:model Flight -c</pre>
    </span>

6. Run this command in Windows PowerShell to create all the above files in the same time: 
   * this command will create the following files:
     * a model file inside <span style="font-style:italic; font-weight:bold;">app > models</span> folder;
     * a migration file inside <span style="font-style:italic; font-weight:bold;">root > database > migrations</span> folder;
     * a factory file inside <span style="font-style:italic; font-weight:bold;">root > database > factories</span> folder;
     * a seeder file inside <span style="font-style:italic; font-weight:bold;">root > database > seeders</span> folder;
     * a controller file inside <span style="font-style:italic; font-weight:bold;">app > http > controllers</span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:model Flight -mc</pre>
        <pre>php artisan make:model Flight -msc</pre>
        <pre>php artisan make:model Flight -mfsc</pre>
    </span>