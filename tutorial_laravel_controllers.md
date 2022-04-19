# Creating your first Laravel [Controller](https://laravel.com/docs/8.x/controllers "Laravel Database: Controllers")

Instead of defining all of your request handling logic as closures in your route files, you may wish to organize this behavior using "controller" classes. Controllers can group related request handling logic into a single class. For example, a UserController class might handle all incoming requests related to users, including showing, creating, updating, and deleting users. By default, controllers are stored in the <span style="font-style:italic; font-weight:bold;">app > http > controllers</span> directory.

1. Run this command in Windows PowerShell to create a controller: 

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">  (create simple controller):</span> php artisan make:controller UserController
    <span style="color:white; font-weight:normal;">(create resource controller):</span> php artisan make:controller UserController --resource</pre>
    </span>

2. C.R.U.D. operations stands for: CREATE, READ, UPDATE and DELETE. A resource controller will use the following methods and can be used also when creating an API:
   * <span style="font-style:italic; font-weight:bold;">index()</span> to display all the records from a table;
   * <span style="font-style:italic; font-weight:bold;">create()</span> to display a form that is used for creating a new record in a certain table;
   * <span style="font-style:italic; font-weight:bold;">store()</span> to store the newly created record in a certain table;
   * <span style="font-style:italic; font-weight:bold;">show()</span> to display a particular record from the database using the id of that record;
   * <span style="font-style:italic; font-weight:bold;">edit()</span> to display a form that is used for editing and existing record in a certain table;
   * <span style="font-style:italic; font-weight:bold;">update()</span> to store the edited record in the database;
   * <span style="font-style:italic; font-weight:bold;">destroy()</span> to delete a particular record from the database using the id of that record;