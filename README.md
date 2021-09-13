# php-basic-routing
A simple php routing class with parameter feature.

# How to use ?

Download the "index.php" file.
Create a new .htaccess file in root folder and add below lines :

```
RewriteEngine On

#website location
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d

RewriteRule ^(.+)$ index.php?uri=$1 [QSA,L]

```
Now in index.php, you can create routes :

```php

$route->add("ROUTE ADDRESS","PHP FILE LOCATION FOR THIS ROUTE");

//without parameter
$route->add("/download","download.php");

//with parameter
$route->add("/user/{id}","user.php");

//in user.php access id like this :
$params['id'];

//At the last of index.php file call notFound() method of Route for 404 error.
$route->notFound("404 PAGE LOCATION");

$route->notFound("404.php");

```

