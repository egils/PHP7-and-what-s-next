## What to expect in PHP 7.3

--

### Allow a trailing comma in function calls

```php
unset(
    $foo,
    $bar,
    $baz, // <--- Look here!
);
```

--

### JSON_THROW_ON_ERROR

* New option flag value for ``json_decode()`` and ``json_encode()``
* Will trow exception on error (no more random ``null``!)


```php
json_decode("{", false, 512, JSON_THROW_ON_ERROR);
json_encode("\x80", JSON_THROW_ON_ERROR);
```
