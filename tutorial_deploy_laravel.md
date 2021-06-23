# Deploying a laravel project on live server (primary domain or subdomain):
Zip the project you want to deploy and upload it to the hosting server.
Create an .htaccess file in your root folder and paste in the following lines:

    <IfModule mod_rewrite.c>
        RewriteEngine On
        RewriteCond %{REQUEST_URI} !^/public/
        RewriteRule ^(.*)$ /public/$1 [L,QSA]
    </IfModule>

This will silently rewrite all you base URIs to the public folder. Even all Headers, for example the HTTP Authorization Header, and all optional URI parameters will silently be passed on the public folder as well.

After uploading your project to the live server, DO NOT DO THE FOLLOWING:
* rename the server.php file from the root folder to index.php;
* copy the .htaccess file from the public folder to the root folder;

This will expose your .env file.