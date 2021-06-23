create a new export file via powershell with the following command: 

# Install Maatwebsite/Excel Package

To install [Maatwebsite/Excel Package](https://github.com/Maatwebsite/Laravel-Excel "Maatwebsite/Excel Package - Web package for exporting database information to Excel or CSV") you just need to open Windows PowerShell and type the following command:

1. To install Maatwebsite/Excel Package you need to install the following prerequisites:

    <span style="color:red; font-weight:bold;">
        <pre>enable extension = gd in php.ini</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>composer require phpoffice/phpspreadsheet</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>composer require maatwebsite/excel</pre>
    </span>
  
2. Register the provider by adding the following lines in root > config > app.php:

    <span style="color:red; font-weight:bold;">
        <pre>in providers array: Maatwebsite\Excel\ExcelServiceProvider::class</pre>
        <pre>in aliases array: 'Excel' => \Maatwebsite\Excel\Facades\Excel::class</pre>
    </span>

3. In Windows PowerShell, publish the package with the following command:

    <span style="color:red; font-weight:bold;">
        <pre>php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider" --tag=config</pre>
    </span>

4. In Windows PowerShell, make a new export PHP class:

    <span style="color:red; font-weight:bold;">
        <pre>php artisan make:export NameOfTheModelExport --model=App\Models\NameOfTheModel</pre>
    </span>