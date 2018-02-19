## Generics?!?!!!

--

```php
class Entry<ValueType> {
    // ...
    public function set(ValueType $value): void {
        $this->value = $value
    };
    public function get(): ValueType {
        return $this->value
    };
}

(new Entry<int>())->set(1);
(new Entry<string>())->set('test');
```

--

![Dunno](images/dunno.gif)

--

<iframe width="750" height="500" src="https://externals.io/message/92394" frameborder="0"></iframe>

--

![status](images/twitter-generics-status.png)

--

![status](images/twitter-mock.png)


