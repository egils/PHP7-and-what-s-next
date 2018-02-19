## Highly controversial...

--

### Pipe Operator

* Shell-like pipe chaining

```php
$dispatcher = getDispatcher(getRouter(getApp(buildDic(loadConfig()))), $request);
// or
$config = loadConfig();
$dic = buildDic($config);
$app = getApp($dic);
$router = getRouter($app);
$dispatcher = getDispatcher($router, $request);
```
vs. 
```php
$dispatcher = loadConfig()
  |> buildDic($$)
  |> getApp($$)
  |> getRouter($$)
  |> getDispatcher($$, $request);
``` 

--

### Traits with interfaces

```php
interface I {
    function foo();
}
 
trait T implements I {
    function foo() {}
}
 
class C {
    use T;
}

(new C()) instanceof I; // true!
```

--

### Arrow functions

* Pretty much comes from JavaScript :)

```php
$y = 1; 
$sumFunction = function (int $x) use ($y): int {
    return $x + $y;
};

$four = $sumFunction(3);
```
vs.
```php
$y = 1;
$sumFunction = fn(int $x): int => $x + $y;
$four = $sumFunction(3);
```

--

### Retry 

* Retry recoverable exceptions

```php
try {
    $obj = $this->s3->bucket('bucket-name')->object('key');
    $obj->upload_file($path);
} catch (AWS\S3\UploadException $e)
    retry;
}
```

```php
try {
    somethingSketchy();
} retry 3 (RecoverableException $e, $attempt) {
    echo "Failed doing sketchy thing on try #{$attempt}. Retrying...";
    sleep(1);
} catch (RecoverableException $e) {
    echo $e->getMessage();
}
```

--

### Class Friendship

* Friendly classes gets protected access!

```php
class Person
{
    friend HumanResourceReport;
    protected $name; // <- note PROTECTED
    // ...
}
class HumanResourceReport
{
    private $personName;
    public function __construct(Person $person) { 
        $this->personName = $person->name; 
    }
}
```

--

### Lexical Scope for Anonymous Classes

```php
$glow = 5;
$foo = new class use($glow) { };
```
Is functionally equivalent to:
```php
$glow = 5;
$foo = new class($glow) {
    private $glow;
    public function __construct($glow) {
        $this->glow = $glow;
    }
};
```




