# Pre Flight Response for Laravel #

This is middleware made for laravel to handle Pre Flight Response sent randomly by browser when XMLHttpRequest is called for security measure.

## Installation ##

You can download the package in its entirely. The [Releases](https://github.com/hymns/preflight-middleware/releases) page lists all stable versions. Download any file with the name `preflight-middleware-[RELEASE_NAME].zip` for a package including this library and its dependencies (if any).

Uncompress the zip file you download, and copy the `PreFlightResponse.php` file to middleware folder `app/Http/Middleware/`.

## Laravel ##

Then in the `app/Http/Kernel.php` file. Add the Middleware you just copied to
the global middleware array.

```php
protected $middleware = [
    ...
    \App\Http\Middleware\PreFlightResponse::class,
];
```

## Lumen ##

In the `bootstrap/app.php` file. Register the middleware you just copied to the global middleware array.

```php
$app->middleware([
    ...
    \App\Http\Middleware\PreFlightResponse::class,
]);
```

That's all! Your laravel or lumen application now correctly response to AJAX preflight request with the OPTIONS method by response with status code 200.