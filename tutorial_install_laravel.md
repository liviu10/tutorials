# <a name="top"></a>Laravel Tutorials - Table of Contents:
[<h3>1. Install Laravel v8.0</h3>](#install_laravel)
[<h3>2. Configure Environment Settings</h3>](#configure_env_settings)
[<h3>3. Install Laravel Vue Spa</h3>](#install_laravel_vue_spa)
[<h3>4. Install Laravel Breeze & Inertia</h3>](#install_laravel_breeze_and_inertia)
[<h3>5. Install Laravel Fortify</h3>](#install_laravel_fortify)
[<h3>6. Install Laravel Jetstream</h3>](#install_laravel_jetstream)
[<h3>7. Install NPM and NodeJS server</h3>](#install_npm)
[<h3>8. Install Bootstrap v5.0 & SASS</h3>](#install_bootstrap_sass)
[<h3>9. Install PurgeCSS</h3>](#install_purge_css)
   <br>

## <a name="install_laravel"></a>Install Laravel 8 Framework [&#8593; top](#top)

To install [Laravel Framework](https://laravel.com/docs/8.x/installation "Laravel v8 - Web Application Framework for PHP") you just need to open Windows PowerShell and type in one of the following commands (you can install Laravel Framework either locally as a single project dependency or globally):

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">      (create a new project):</span> composer create-project laravel/laravel example-app
<span style="color:white; font-weight:normal;">(new project in current dir):</span> composer create-project laravel/laravel ./
<span style="color:white; font-weight:normal;">  (install laravel globally):</span> composer global require laravel/installer
<span style="color:white; font-weight:normal;">      (create a new project):</span> laravel new example-app</pre>
</span>

## <a name="configure_env_settings"></a>Configure the environment settings [&#8593; top](#top)

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

## <a name="install_laravel_vue_spa"></a>Install Laravel Vue SPA [&#8593; top](#top)

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

## <a name="install_laravel_breeze_and_inertia"></a>Install Laravel Breeze & Inertia [&#8593; top](#top)

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

## <a name="install_laravel_fortify"></a>Install Laravel Fortify [&#8593; top](#top)

[Laravel Fortify](https://laravel.com/docs/8.x/fortify#installation "Laravel Fortify") is a frontend agnostic authentication backend implementation for Laravel. Fortify registers the routes and controllers needed to implement all of Laravel's authentication features, including login, registration, password reset, email verification, and more.

1. In Windows PowerShell run the following command to install Fortify via composer:

    <span style="color:red; font-weight:bold;">
        <pre>composer require laravel/fortify</pre>
    </span>

2. In Windows PowerShell run the this command to publish Fortify's actions to your app/Actions directory, which will be created if it does not exist.

    <span style="color:red; font-weight:bold;">
        <pre>php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"</pre>
    </span>

3. In Windows PowerShell run the following command after creating the database:

    <span style="color:red; font-weight:bold;">
        <pre>php artisan migrate</pre>
    </span>

4. Open <span style="font-style:italic; font-weight:bold;">FortifyServiceProvider.php</span> from <span style="font-style:italic; font-weight:bold;">Root > App > Providers</span> and add the following lines inside the <span style="font-style:italic; font-weight:bold;">boot()</span> method to create the login form with it's functionalities:

    <span style="color:red; font-weight:bold;">
        <pre>use App\Models\User;<br>use Illuminate\Support\Facades\Hash;<br>use Illuminate\Support\Facades\Validator;</pre>
    </span>

    <span style="color:red; font-weight:bold;">
        <pre>Fortify::loginView(fn () => view('auth.login'));</pre>
    </span>

    <span style="color:red; font-weight:bold;">
        <pre>Fortify::authenticateUsing(function (Request $request) {
        $user = User::where('email', $request->email)->first();
        if ($user &&
            Hash::check($request->password, $user->password)) {
            return $user;
        }
    });</pre>
    </span>

    <span style="color:red; font-weight:bold;">
        <pre>Fortify::registerView(fn () => view('auth.register'));</pre>
    </span>

5. Open <span style="font-style:italic; font-weight:bold;">app.php</span> from <span style="font-style:italic; font-weight:bold;">Root > config</span> and add the following line inside the <span style="font-style:italic; font-weight:bold;">providers</span> array key to register Fortify PHP class:

    <span style="color:red; font-weight:bold;">
        <pre>App\Providers\FortifyServiceProvider::class,</pre>
    </span>

## <a name="install_laravel_jetstream"></a>Install Laravel Jetstream [&#8593; top](#top)

[Laravel Jetstream](https://jetstream.laravel.com/2.x/introduction.html "Laravel Jetstream") is a beautifully designed application starter kit for Laravel and provides the perfect starting point for your next Laravel application. Jetstream provides the implementation for your application's login, registration, email verification, two-factor authentication, session management, API via Laravel Sanctum, and optional team management features.

1. In Windows PowerShell run the following command to install Jetstream via composer:

    <span style="color:red; font-weight:bold;">
        <pre>composer require laravel/jetstream</pre>
    </span>

2. In Windows PowerShell run the following command to install Jetstream Livewire library via php artisan:

    <span style="color:red; font-weight:bold;">
        <pre>php artisan jetstream:install livewire</pre>
    </span>

## <a name="install_npm"></a>Install Node.js and npm [&#8593; top](#top)

To install [Node.js](https://nodejs.org/en/ "Node.js - JavaScript runtime built") you just need to download and install it as a regular Windows executable file. Node package manager (npm) is installed together with Node.js. Bellow is a [list](https://docs.npmjs.com/cli/v7/commands "NPM - CLI Commands") of commonly use NPM commands:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">     (check node.js version):</span> node --version
<span style="color:white; font-weight:normal;">         (check npm version):</span> npm --version
<span style="color:white; font-weight:normal;">      (list of npm commands):</span> npm --help
<span style="color:white; font-weight:normal;">        (check dependencies):</span> npm audit
<span style="color:white; font-weight:normal;">           (install updates):</span> npm audit fix --force
<span style="color:white; font-weight:normal;">(check for missing packages):</span> npm doctor
<span style="color:white; font-weight:normal;">           (clear npm cache):</span> npm cache clear</pre>
</span>



## <a name="install_bootstrap_sass"></a>Install Bootstrap v5.0 & SASS [&#8593; top](#top)

To install [Bootstrap Framework](https://getbootstrap.com/docs/5.0/getting-started/download/ "Bootstrap v5.0 - Frontend Framework") and [SASS](https://sass-lang.com/install "SASS - CSS Pre-processor") you just need to open Windows PowerShell and:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">(install Bootstrap package):</span> composer require twbs/bootstrap:5.1.0
<span style="color:white; font-weight:normal;">    (globally install SASS):</span> npm install --global sass
<span style="color:white; font-weight:normal;"> (compile SCSS to CSS file):</span> sass --watch "pathToSCSSFile/main-styles.scss" "pathToCSSFile/main-styles.css"</pre>
</span>


## <a name="install_purge_css"></a>Install PurgeCSS [&#8593; top](#top)

To install [PurgeCSS](https://purgecss.com/CLI.html#installation "PurgeCSS - Tool to remove unused CSS") you just need to open Windows PowerShell and:

1. Run the following command to enable execution of policies and avoid receiving an error that says "execution of scripts is disabled on this system" - [more here](https://stackoverflow.com/questions/4037939/powershell-says-execution-of-scripts-is-disabled-on-this-system).

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">   (enable execution policy):</span> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
    <span style="color:white; font-weight:normal;"> (restrict execution policy):</span> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine</pre>
    </span>

2. Run the following commands to install PurgeCSS as global project dependency to purge unused CSS styles or to uninstall the purgecss package:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (globally install purgecss):</span> npm install --global purgecss
    <span style="color:white; font-weight:normal;">  (purge unused css command):</span> purgecss --css pathToCSSFiles/main-styles.css --content pathToHTMLFiles/index.html --output pathToOutputCSSFiles/purged_styles.css
    <span style="color:white; font-weight:normal;">(uninstall purgecss package):</span> npm uninstall --global purgecss</pre>
    </span>


