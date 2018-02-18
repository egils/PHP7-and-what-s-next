## Most likely coming...

--

### Null Coalescing Assignment Operator

* ``??=`` to allow "if null" assignment
* Voted ``yes`` but missed PHP 7.3 train

```php
$nullableVariable = $nullableVariable ?? 'default';
// Instead of repeating variables with long names, the equal coalesce operator is used
$$nullableVariable ??= 'default';
```

--

### Flexible Heredoc and Nowdoc

* Closing marker can be indented
* New line is no longer required after the closing marker

```php
public function doStuff() {
    echo(<<<END
      a
     b
    c
    END);
}
/*
  a
 b
c
*/
```

--

### Operator functions

* PHP's built-in operators work functions!

```php
'+'($a, $b)     $a + $b	
'-'($a, $b)     $a - $b	
'*'($a, $b)     $a * $b	
'/'($a, $b)     $a / $b	
'==='($a, $b)   $a === $b	
'!='($a, $b)    $a != $b	
'<>'($a, $b)    $a <> $b	
'!=='($a, $b)   $a !== $b	
'<'($a, $b)     $a < $b	
'>'($a, $b)     $a > $b	
'<='($a, $b)    $a <= $b	
'>='($a, $b)    $a >= $b	
'<=>'($a, $b)   $a <=> $b

// Adds the numbers in $terms together (equivalent to array_sum())
$sum = array_reduce($terms, '+', 0);
```
