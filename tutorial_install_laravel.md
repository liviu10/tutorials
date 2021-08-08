# Install Laravel 8 Framework

To install [Laravel Framework](https://laravel.com/docs/8.x/installation "Laravel v8 - Web Application Framework for PHP") you just need to open Windows PowerShell and type in one of the following commands (you can install Laravel Framework either locally as a single project dependency or globally):

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">    (create a new project):</span> composer create-project laravel/laravel example-app
<span style="color:white; font-weight:normal;">(install laravel globally):</span> composer global require laravel/installer
<span style="color:white; font-weight:normal;">    (create a new project):</span> laravel new example-app</pre>
</span>

# Install Laravel Vue SPA

To install [Laravel Vue SPA](https://github.com/cretueusebiu/laravel-vue-spa "Laravel Vue SPA - A Laravel-Vue SPA starter kit") you just need to open Windows PowerShell and type in the following commands (this starter kit comes with Laravel v8, VueJS v2 and Bootstrap v4.6):

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">      (create the project):</span> composer create-project --prefer-dist cretueusebiu/laravel-vue-spa
<span style="color:white; font-weight:normal;">  (database conn. details):</span> check the last topic of this tutorial
<span style="color:white; font-weight:normal;">(generate php artisan key):</span> php artisan key:generate
<span style="color:white; font-weight:normal;"> (generate JSON WEB token):</span> php artisan jwt:secret
<span style="color:white; font-weight:normal;"> (run database migrations):</span> php artisan migrate
<span style="color:white; font-weight:normal;">             (install NPM):</span> npm install
<span style="color:white; font-weight:normal;">   (compile assets - dev.):</span> npm run development -- --watch
<span style="color:white; font-weight:normal;">  (compile assets - prod.):</span> npm run production -- --watch</pre>
</span>

# Install Laravel Breeze & Inertia

To install [Laravel Breeze](https://laravel.com/docs/8.x/starter-kits "Laravel Breeze - A Laravel starter kit") and [Inertia](https://laravel.com/docs/8.x/starter-kits "Laravel Breeze - A Laravel starter kit") you just need to open Windows PowerShell and type in the following commands:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">    (create a new project):</span> composer create-project laravel/laravel example-app
<span style="color:white; font-weight:normal;">  (database conn. details):</span> check the last topic of this tutorial
<span style="color:white; font-weight:normal;">  (install breeze package):</span> composer require laravel/breeze --dev
<span style="color:white; font-weight:normal;"> (install inertia package):</span> composer require inertiajs/inertia-laravel
<span style="color:white; font-weight:normal;">          (install breeze):</span> php artisan breeze:install
<span style="color:white; font-weight:normal;"> (run database migrations):</span> php artisan migrate
<span style="color:white; font-weight:normal;">             (install NPM):</span> npm install
<span style="color:white; font-weight:normal;">  (install NPM inertia v2):</span> npm install @inertiajs/inertia @inertiajs/inertia-vue
<span style="color:white; font-weight:normal;">   (compile assets - dev.):</span> npm run dev</pre>
</span>

# Configure the environment settings

After the installation process is finished, make sure to configure the following variables in the <span style="font-style:italic;font-weight:bold;">.env</span> file from the root of your projects' directory:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">(database connection type):</span> DB_CONNECTION=mysql
<span style="color:white; font-weight:normal;">    (database URL address):</span> DB_HOST=127.0.0.1
<span style="color:white; font-weight:normal;">    (database port number):</span> DB_PORT=3306
<span style="color:white; font-weight:normal;">           (database name):</span> DB_DATABASE=example-app
<span style="color:white; font-weight:normal;">       (database username):</span> DB_USERNAME=root
<span style="color:white; font-weight:normal;">       (database password):</span> DB_PASSWORD=</pre>
</span>
