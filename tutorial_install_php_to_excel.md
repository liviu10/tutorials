create a new export file via powershell with the following command: 

# Install Maatwebsite/Excel Package

To install [Maatwebsite/Excel Package](https://github.com/Maatwebsite/Laravel-Excel "Maatwebsite/Excel Package - Web package for exporting database information to Excel or CSV") you just need to open Windows PowerShell and type in the following command:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">   (enable gd extension):</span> enable extension = gd in php.ini
<span style="color:white; font-weight:normal;">(install office package):</span> composer require phpoffice/phpspreadsheet
<span style="color:white; font-weight:normal;"> (install excel package):</span> composer require maatwebsite/excel
<span style="color:white; font-weight:normal;">   (root\config\app.php):</span> register provider class in providers array: Maatwebsite\Excel\ExcelServiceProvider::class
<span style="color:white; font-weight:normal;">   (root\config\app.php):</span> register excel class in aliases array: 'Excel' => \Maatwebsite\Excel\Facades\Excel::class
<span style="color:white; font-weight:normal;">(publish vendor package):</span> php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider" --tag=config
<span style="color:white; font-weight:normal;">    (create export file):</span> php artisan make:export NameOfTheModelExport --model=App\Models\NameOfTheModel</pre>
</span>