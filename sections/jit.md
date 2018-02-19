## PHP 8?

### Currently depends on JIT compiler <!-- .element: class="fragment" -->

--

### Just-in-time (JIT) compilation

* Combination of Ahead-of-time (AOT) compilation and interpretation
* Brings best of both: <!-- .element: class="fragment" -->
    * speed of compiled code
    * flexibility of interpretation
* Brings worst of both: <!-- .element: class="fragment" -->
    * overhead of an interpreter
    * additional overhead of compiling
* All .NET languages, Lua, Java, C++, Python, more...<!-- .element: class="fragment" -->

--

### Why JIT?

* Code of PHP 7 is not a bottleneck anymore
* Disclaimer: JIT is not a silver bullet
    * short living processes of PHP are not ideal for JIT

--

### Status

* Dmitry Stogov is working on JIT for PHP
* Info: http://news.php.net/php.internals/95531

![status](images/twitter-jit-release-date.png)

Troll @SaraMG being troll... <!-- .element: class="fragment" -->
