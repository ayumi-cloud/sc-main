## What's New in Laravel 8

Six months after Laravel 7, on September 8th, 2020, Laravel 8 was officially released — right on schedule. As always, the new version of the free, open-source PHP web framework comes with some exciting additions and a lot of quality improvements. In this article, we will make sure to go over the essential features of Laravel 8.

Table of Contents:

Additions in Laravel 8
Laravel Jetstream
Models Directory
Model Factory Classes
Dynamic Blade Components
Job Batching
Migration Squashing
Time Testing Helpers
Improvements in Laravel 8
Improved Maintenance Mode
Routing Namespace Updates
Improved Rate Limiting
Artisan serve Improvements
Event Listener Improvements
Tailwind Pagination Views

### Additions in Laravel 8

Starting with the additions in Laravel 8, we have Laravel Jetstream, job batching, new app/models directory, etc. Let’s skip the small talk and go right to the point.

### Laravel Jetstream

Laravel Jetstream is a new, beautifully designed application scaffolding for Laravel. It replaces and improves upon the UI scaffolding of previous versions of the PHP web framework. Laravel Jetstream includes login, registration, two-factor authentication, email verification, session management, optional team management, and API support via Laravel Sanctum. Those features make Laravel Jetstream a fitting starting point for your projects.  

Jetstream is designed via Tailwind CSS, offering you a choice between Inertia or Lifewire scaffolding.

### Models Directory

Due to the community’s overwhelming demand, the default Laravel application scaffolding now has an app/Models directory. It’s to be the new home for Eloquent models, and all relevant generator commands are now updated to assume that models exist within that app/Models directory (if it exists). If the directory doesn’t exist, Laravel will assume that your models need to be placed within the app directory.

### Model Factory Classes

Eloquent model factories can be qualified as improvements, but we decided to put them in the additions that come with Laravel 8. We do that because Eloquent model factories are now completely re-written as class-based factories, in addition to being improved by having first-class relationship support. Thanks to the `HasFactory` trait that is now available on generated models, the model factory may be used in the following way:

```php
use App\Models\User;

User::factory()->count(50)->create();
```

Model factories are now simple PHP classes, and thus state transformations can be written as class methods. What’s more, you have the ability to include any additional helper classes that you need for your Eloquent model.

So, in case your User model has a suspended state that modifies one of its default attribute values, you may define your state transformations using the base factory’s state method. You have the option to name your state method as you prefer. It’s a typical PHP method, after all:

```php
/**
 * Indicate that the user is suspended.
 *
 * @return \Illuminate\Database\Eloquent\Factories\Factory
 */
public function suspended()
{
    return $this->state([
        'account_status' => 'suspended',
    ]);
}
```

After defining the state transformation method, you may use it like so:

```php
use App\Models\User;

User::factory()->count(5)->suspended()->create();
```

As we already mentioned, Laravel 8’s model factories include first class support for relationships, and thus in case the User model has a posts relationship method, you can just  run the following code if you wish to generate a user with three posts:

```php
$users = User::factory()
            ->hasPosts(3, [
                'published' => false,
            ])
            ->create();
```

With the idea to ease the upgrade process, the [laravel/legacy-factories](https://github.com/laravel/legacy-factories) package was released to offer support for the previous iteration of model factories within Laravel 8.x.

There are a lot more features included in Laravel’s re-written factories. If you wish to learn about them, go ahead and visit the official [database testing documentation](https://laravel.com/docs/8.x/database-testing#creating-factories).

### Dynamic Blade Components

There may be times when you need to render a component but be unaware of which exact component has to be rendered until runtime. In such cases, Laravel 8 now offers the option to use its built-in `dynamic-component` in order to render the component that’s based on a runtime value or variable:

```html
<x-dynamic-component :component="$componentName" class="mt-4" />
```

If you want to learn more about Blade components, you can consult the official [Blade documentation](https://laravel.com/docs/8.x/blade#components).

### Job Batching

The job batching feature that Laravel 8 provides will allow you to execute a batch of jobs with ease. Additionally, you can perform a type of action after your chosen jobs are done executing. The main use of job batching is in combination with completion callbacks. You may use the `then`, `catch`, and `finally` methods in order to define completion callbacks for your batch. Each of those callbacks would receive an `Illuminate\Bus\Batch` instance when invoked.

For examples and more thorough information around Job Batching, consider visiting the [official queue documentation](https://laravel.com/docs/8.x/queues#job-batching).

### Migration Squashing

While building your application, you may accumulate an increasing number of migrations over time. That accumulation could potentially lead to the migration directory becoming overloaded with hundreds of migrations. If you use PostgreSQL or MySQL, with Laravel 8, you now have the option to “squash” all migrations into a single SQL file. Execute the `schema:dump` command when you wish to get started with the process:

```php
php artisan schema:dump
// Dump the current database schema and prune all existing migrations...
php artisan schema:dump --prune
```

After you execute the command above, Laravel will write a “schema” file to your database/schema directory. That will make it so when you attempt to migrate your database without any other migrations being executed, Laravel will first execute the schema file’s SQL. Afterward, the framework will continue executing all remaining migrations, which were not part of that schema dump.

### Time Testing Helpers

While testing, you may sometimes have to modify time returned by helpers such as now or `Illuminate\Support\Carbon::now()`. With Laravel 8, you now have helpers that offer you manipulation of the current time like so:

```php
public function testTimeCanBeManipulated()
{
    // Travel into the future...
    $this->travel(5)->milliseconds();
    $this->travel(5)->seconds();
    $this->travel(5)->minutes();
    $this->travel(5)->hours();
    $this->travel(5)->days();
    $this->travel(5)->weeks();
    $this->travel(5)->years();

    // Travel into the past...
    $this->travel(-5)->hours();

    // Travel to an explicit time...
    $this->travelTo(now()->subHours(6));

    // Return back to the present time...
    $this->travelBack();
}
```

### Improvements in Laravel 8

We are finished covering the most significant additions to Laravel 8, now let’s continue with the improvements that come with this new version of the framework.

### Improved Maintenance Mode

In previous Laravel releases, the `php artisan down` maintenance mode feature could be bypassed. You can do that by using an “allow list” of IP addresses allowed to access the application. That feature is now removed with the purpose of having a simpler “secret” / token solution.

In maintenance mode, you may now use the `secret` option to specify a maintenance mode bypass token like so:

```php
php artisan down --secret="182302b-364a-4a88-ada1-bb72d5a62135"
```

After you have placed the application in maintenance mode, you have the ability to navigate to the application URL that matches this token, and Laravel will issue a maintenance mode bypass cookie to your browser:

```php
https://example.com/182302b-364a-4a88-ada1-bb72d5a62135
```

After you access this hidden route, you will be redirected to the / route of the application. When the cookie has been issued to your browser, you will have the capability to browse the application normally (as if it wasn’t in maintenance mode).

### Routing Namespace Updates

In previous Laravel releases, there was a `$namespace` property to go with the `RouteServiceProvider`. Said property’s value would be automatically prefixed onto controller route definitions and calls to the `action` helper / `URL::action` method. In Laravel 8.x, that property is null by default, which means the framework will do no automatic namespace prefixing. So, in new Laravel 8.x applications, controller route definitions are to be defined using standard PHP callable syntax:

```php
use App\Http\Controllers\UserController;

Route::get('/users', [UserController::class, 'index']);
```

Calls to the action related methods should use the same callable syntax:

```php
action([UserController::class, 'index']);

return Redirect::action([UserController::class, 'index']);
```

In case you prefer the Laravel 7.x style controller route prefixing, all you have to do is simply add the $namespace property into your application’s `RouteServiceProvider`.

### Improved Rate Limiting

With Laravel 8, the rate limiter feature is now augmented with additional flexibility and power, while continuing to maintain backward compatibility with the previous release’s throttle middleware API.

Rate limiters are defined using the `RateLimiter` facade’s `for` method. The `for` method accepts a rate limiter name and a Closure that returns the limit configuration. The configuration should apply to routes that are assigned this rate limiter:

```php
use Illuminate\Cache\RateLimiting\Limit;
use Illuminate\Support\Facades\RateLimiter;
RateLimiter::for('global', function (Request $request) {
    return Limit::perMinute(1000);
});
```

Because rate limiter callbacks receive the incoming HTTP request instance, you may build the appropriate rate limit dynamically and based on the incoming request or the authenticated user:

```php
RateLimiter::for('uploads', function (Request $request) {
    return $request->user()->vipCustomer()
                ? Limit::none()
                : Limit::perMinute(100);
});
```

In some cases, you may choose to segment rate limits by an arbitrary value. For example, you may want to allow users to access a specific route 100 times per minute per IP address. To accomplish this, you have to use the `by` method while building your rate limit:

```php
RateLimiter::for('uploads', function (Request $request) {
    return $request->user()->vipCustomer()
                ? Limit::none()
                : Limit::perMinute(100)->by($request->ip());
});
```

Rate limiters may be attached to routes or route groups using the throttle [middleware](https://laravel.com/docs/8.x/middleware). It accepts the name of the rate limiter you want to assign to the route:

```php
Route::middleware(['throttle:uploads'])->group(function () {
    Route::post('/audio', function () {
        //
    });
    Route::post('/video', function () {
        //
    });
});
```

If you are interested in more information about rate limiting, go visit the official [routing documentation](https://laravel.com/docs/8.x/routing#rate-limiting).

### Artisan serve Improvements

Another improvement with Laravel 8 is for the Artisan `serve` command. Now it has automatic reloading whenever environment variable changes are detected within the local .env file. Prior to Laravel 8, the command had to be manually stopped and restarted.

### Event Listener Improvements

Closure based event listeners are also improved with the new version of the framework. Those may now be registered by simply passing the Closure to the `Event::listen` method. Laravel inspects the Closure to determine the specific type of event the listener handles:

```php
use App\Events\PodcastProcessed;
use Illuminate\Support\Facades\Event;
Event::listen(function (PodcastProcessed $event) {
    //
});
```

Additionally, Closure based event listeners can be marked as queueable by using the `Illuminate\Events\queueable` function:

```php
use App\Events\PodcastProcessed;
use function Illuminate\Events\queueable;
use Illuminate\Support\Facades\Event;
Event::listen(queueable(function (PodcastProcessed $event) {
    //
}));
```

Similar to queued jobs, you have the option to use the `onConnection`, `onQueue` and `delay` methods to customize the execution of the queued listener:

```php
Event::listen(queueable(function (PodcastProcessed $event) {
    //
})->onConnection('redis')->onQueue('podcasts')->delay(now()->addSeconds(10)));
```

If you wish to handle anonymous queued listener failures, you have the capability to provide a Closure to the `catch` method while defining the `queueable` listener:

```php
use App\Events\PodcastProcessed;
use function Illuminate\Events\queueable;
use Illuminate\Support\Facades\Event;
use Throwable;
Event::listen(queueable(function (PodcastProcessed $event) {
    //
})->catch(function (PodcastProcessed $event, Throwable $e) {
    // The queued listener failed...
}));
```

### Tailwind Pagination Views

Last but not least, the Laravel paginator has now been updated to use the `Tailwind CSS` framework by default. Tailwind CSS framework is a highly customizable, low-level CSS framework. It provides all the needed building blocks for building various designs without having opinionated styles that you have to fight in order to override. It goes without a doubt — Bootstrap 3 and 4 views are still available.

## Conclusion

With each new release, Laravel becomes more and more comprehensive. After Laravel 6, the framework follows semver and releases a major version every six months. Laravel definitely keeps making things easier when it comes to creating web applications and we can’t wait for the next release, even though we just got that fresh Laravel 8.
