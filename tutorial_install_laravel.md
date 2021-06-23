# Install Laravel 8 Framework

To install [Laravel Framework](https://laravel.com/docs/8.x/installation "Laravel v8 - Web Application Framework for PHP") you just need to open Windows PowerShell and type the following command:

1. In Windows PowerShell run the following command to install Laravel as a single project dependency:

    <span style="color:red; font-weight:bold;">
        <pre>composer create-project laravel/laravel example-app</pre>
    </span>
  
2. In Windows PowerShell run the following commands to install Laravel as a global project dependency:

    <span style="color:red; font-weight:bold;">
        <pre>composer global require laravel/installer</pre>
        <pre>laravel new example-app</pre>
    </span>

# Configure the environment settings

After the installation process is finished, make sure to configure the following variables in the <span style="font-style:italic;font-weight:bold;">.env</span> file from the root of your projects' directory:

1. Refers to what kind of database server you application will connect to. In this case it's a MySQL server:

    <span style="color:red; font-weight:bold;">
        <pre>DB_CONNECTION=mysql</pre>
    </span>

2. Refers to the URL address used for viewing you web application. In this case it's http:\\127.0.0.1 or http:\\localhost\example-app

    <span style="color:red; font-weight:bold;">
        <pre>DB_HOST=127.0.0.1</pre>
    </span>

3. Refers to the port that the database server will use

    <span style="color:red; font-weight:bold;">
        <pre>DB_PORT=3306</pre>
    </span>

4. Refers to the name of you database

    <span style="color:red; font-weight:bold;">
        <pre>DB_DATABASE=example-app</pre>
    </span>

5. Refers to the username that you are using to connect to a particular database.

    <span style="color:red; font-weight:bold;">
        <pre>DB_USERNAME=root</pre>
    </span>

6. Refers to the password that you are using to connect to a particular database. In this case it's blank; no password is needed to make the connection.

    <span style="color:red; font-weight:bold;">
        <pre>DB_PASSWORD=</pre>
    </span>