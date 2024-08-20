
# Laravel Locale change and localized url Middleware

Laravel localized middleware and locale changing

## App\Http\Kernel.php

    protected $routeMiddleware = [
        other middlewares
        'localized' => \App\Http\Middleware\Localized::class,
        ]

## Usage/Examples

```php
Route Usage
Route::middleware('localized')->get('/{locale}/about', [MainController::class, 'about'])->name('about');

Controller Usage

public function about($locale)
    {
        //do the stuff with locale
        return view('about');
    }


Blade Usage
<a href="{{ route('about', ['locale' => app()->getLocale()]) }}">About</a>

```

