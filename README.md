# Pre Flight Response for Laravel #

This is middleware made for laravel to handle Pre Flight Response sent randomly by browser when XMLHttpRequest is called for security measure.

## Installation ##

You can simply **Download the Release**

### Download the Release

You can download the package in its entirety. The [Releases](https://github.com/hymns/preflight-middleware/releases) page lists all stable versions. Download any file with the name `preflight-middleware-[RELEASE_NAME].zip` for a package including this library and its dependencies (if any).

Uncompress the zip file you download, and copy the `PreFlightResponse.php` file to middleware folder `app/Http/Middleware/`.

Then in the `app/Http/Kernel.php` file. Add the Middleware you just copied to
the global middleware array.

```php
protected $middleware = [
    \App\Http\Middleware\PreFlightResponse::class,
];
```
That's all! Your laravel application now correctly response to AJAX preflight request with the OPTIONS method by response with status code 200.