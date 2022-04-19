# Laravel [Rename Table](https://laravel.com/docs/8.x/migrations#renaming-and-dropping-tables "Laravel Migrations: Rename Table")

The table method on the Schema facade may be used to rename existing tables. Like the create method, the table method accepts two arguments: the current name and the new name of a particular table you wish to rename to.

1. Create a rename migration and add the PHP rename method inside <span style="font-style:italic; font-weight:bold;">up()</span> method:
   * the first command will create a migration with the role of renaming a table from the database;
   * the <span style="font-style:italic; font-weight:bold;">rename()</span> method will change the name of a particular table from the database;
   
    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:migration rename_table_test_table</pre>
        <pre>Schema::rename($fromCurrentTableName, $toNewTableName);</pre>
    </span>

# Laravel [Delete Table](https://laravel.com/docs/8.x/migrations#renaming-and-dropping-tables "Laravel Migrations: Delete Table")

The table method on the Schema facade may be used to drop existing tables. Like the create method, the table method accepts one argument: the name of the table you wish to drop.

1. Create a rename migration and add the PHP drop method inside <span style="font-style:italic; font-weight:bold;">up()</span> method:
   * the first command will create a migration with the role of renaming a table from the database;
   * the <span style="font-style:italic; font-weight:bold;">rename()</span> method will change the name of a particular table from the database;
   
    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:migration delete_table_test_table</pre>
        <pre>Schema::drop($tableName);</pre>
    </span>

# Laravel [Rename Table Column](https://laravel.com/docs/8.x/migrations#renaming-columns "Laravel Migrations: Rename Column Table")

To rename a column, you may use the renameColumn method provided by the schema builder blueprint. Before renaming a column, ensure that you have installed the doctrine/dbal library via the Composer package manager:

1. Install the <span style="font-style:italic; font-weight:bold;">doctrine/dbal library</span>, create a rename migration and add the PHP drop method inside <span style="font-style:italic; font-weight:bold;">up()</span> method:
   * the first command will install doctrine/dbal library;
   * the second command will create a migration with the role of renaming a column from a certain table in the database;
   * the <span style="font-style:italic; font-weight:bold;">renameColumn()</span> method will change the name of a particular column from a table in the database;
   
    <span style="color:red; font-weight:bold;">
        <pre>composer require doctrine/dbal</pre>
        <pre>php artisan make:migration rename_column_table_test_table</pre>
        <pre>Schema::table('table_test', function (Blueprint $table) {
           $table->renameColumn('id_bigIncrements', 'new_id_column_name');
        });</pre>
    </span>

# Laravel [Change Column Attributes](https://laravel.com/docs/8.x/migrations#updating-column-attributes "Laravel Migrations: Change Column Attributes")

The change method allows you to modify the type and attributes of existing columns. For example, you may wish to increase the size of a string column. To see the change method in action, let's increase the size of the name column from 25 to 50. To accomplish this, we simply define the new state of the column and then call the change method:

1. Create a change migration and add the PHP change method inside <span style="font-style:italic; font-weight:bold;">up()</span> method:
   * the <span style="font-style:italic; font-weight:bold;">change()</span> method will change the attribute and the type of a certain column from the database;
   
    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:migration change_attribute_column_table_test_table</pre>
        <pre>Schema::table('table_test', function (Blueprint $table) {
           $table->string('longText', 255)->change();
        });</pre>
    </span>