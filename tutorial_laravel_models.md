# Creating your first Laravel [Models](https://laravel.com/docs/8.x/eloquent#generating-model-classes "Laravel Database: Models")

Laravel includes Eloquent, an object-relational mapper (ORM) that makes it enjoyable to interact with your database. When using Eloquent, each database table has a corresponding "Model" that is used to interact with that table. In addition to retrieving records from the database table, Eloquent models allow you to insert, update, and delete records from the table as well.

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">                                    (create model):</span> php artisan make:model User
<span style="color:white; font-weight:normal;">                      (create model and migration):</span> php artisan make:model Flight --migration
<span style="color:white; font-weight:normal;">                        (create model and factory):</span> php artisan make:model Flight --factory
<span style="color:white; font-weight:normal;">                           (create model and seed):</span> php artisan make:model Flight --seed
<span style="color:white; font-weight:normal;">                            (model and controller):</span> php artisan make:model Flight --controller
<span style="color:white; font-weight:normal;">                 (model, migration and controller):</span> php artisan make:model Flight -mc
<span style="color:white; font-weight:normal;">         (model, migration, seeder and controller):</span> php artisan make:model Flight -msc
<span style="color:white; font-weight:normal;">(model, factory, migration, seeder and controller):</span> php artisan make:model Flight -mfsc</pre>
</span>