# Creating your first Laravel [View](https://laravel.com/docs/8.x/views#creating-and-rendering-views "Laravel Database: Views")

You may create a view by placing a file with the .blade.php extension in your application's resources/views directory. The .blade.php extension informs the framework that the file contains a Blade template. Blade templates contain HTML as well as Blade directives that allow you to easily echo values, create "if" statements, iterate over data, and more.

Artisan does not have a command for creating views, but you can install a dependency from Github. [This](https://github.com/svenluijten/artisan-view "Artisan: Views") will allow you to give the following PowerShell commands:

1. In Windows PowerShell run the following command to install this package via composer:

    <span style="color:red; font-weight:bold;">
        <pre>composer require sven/artisan-view --dev</pre>
    </span>

2. Run these commands in Windows PowerShell to create a view template: 
   * the first command will create a view file inside of <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder;
   * the second command will create a view file in a subdirectory of <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder;
   * the third command will create a view file inside <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder with the ".html" extension;
   * the forth command will create a view file in a subdirectory of <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder with ".html" extension;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:view index</pre>
        <pre>php artisan make:view subdirectoryOfViews.index</pre>
        <pre>php artisan make:view index --extension=html</pre>
        <pre>php artisan make:view subdirectoryOfViews.index --extension=html</pre>
    </span>

3. Run these commands in Windows PowerShell to delete a view template: 
   * the first command will delete a view file inside of <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder;
   * the second command will delete a view file in a subdirectory of <span style="font-style:italic; font-weight:bold;">root > resources > views </span> folder;

    <span style="color:red; font-weight:bold;">
        <pre>php artisan scrap:view index</pre>
        <pre>php artisan scrap:view subdirectoryOfViews.index</pre>
    </span>