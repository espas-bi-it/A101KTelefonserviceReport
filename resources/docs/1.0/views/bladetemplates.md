# Blade Templates

---

- [Explanation](#section-1)
- [Blade Basics](#section-2)
- [Displaying Data](#section-3)
- [Layouts and Components](#section-4)
- [References](#section-5)

<a name="section-1"></a>
## Explanation

Blade templates in Laravel are a powerful and expressive way to build dynamic web pages.


<a name="section-2"></a>
## Blade Basics

 - Blade is the templating engine included with Laravel.
 - Unlike some PHP templating engines, Blade doesn’t restrict you from using plain PHP code in your templates.
 - All Blade templates are compiled into plain PHP code and cached, adding minimal overhead to your app.
 - Blade files use the <code>.blade.php</code> extension and are typically stored in the <code>resources/views</code> directory.

<a name="section-3"></a>
## Displaying Data







- You can display data passed to Blade views using curly braces: 
```php
{{ $variable }}
```


- Echo statements are automatically sanitized to prevent XSS attacks.
- You can also echo results of any PHP function within Blade templates.

<a name="section-4"></a>
## Layouts and Components

- Blade allows you to create reusable layouts and components.
- Layouts define the overall structure of your pages.
- Components encapsulate UI elements for reuse.


You can extend layouts and include partial views:
- <code> include('partials.header')</code> to include partial views.
- <code>extends('layouts.app')</code> to extend a layout.

<a name="section-5"></a>
## References

[Blade Templates in Laravel 11](https://laravel.com/docs/11.x/blade#main-content)
