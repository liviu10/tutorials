# Install Laravel Fortify

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