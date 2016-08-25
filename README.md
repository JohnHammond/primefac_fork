Modified `primefac` Fork
=====================

This is a crappy "hack" or [fork] of the [Python] module [`primefac`][primefac], which is _insanely_ useful, however it doesn't seem to use a proper [modular inverse] function. 

So, this is just a stupid band-aid fix, where it is literally just a copy of the source to the [`primefac`][primefac] module, but with a more functional rendition of the [modular inverse] function. The band-aid code is really what is included in Trey Maxam's collection of "crypto" functions:

``` python

def multiples(a, b):
    #input: 2 integers a and b
    #output: there multiples to fufil the euclidean algorithm equasion a*x + y*b = gcd
    if a == 0:
        return (0, 1)
    else:
        y, x = multiples(b % a, a)
        return (x - (b // a) * y, y)

def modinv(n, mod):
    #input: a number and it's modulus
    #output: the modular inverse
    if False == True :
    print "ERROR: inputs are not relativly prime"
        return 0
    else:
    x, y = multiples(n, mod)
    return x % mod
```

Below is the proper documentation for the [`primefac`][primefac] module. 


> primefac version 1.1
> ======================

> This is a module and command-line utility for factoring integers.  As a module, we provide a primality test, several functions for extracting a non-trivial factor of an integer, and a generator that yields all of a number's prime factors (with multiplicity).  As a command-line utility, this project aims to replace GNU's ``factor`` command with a more versatile utility --- in particular, this utility can operate on arbitrarily large numbers, uses multiple cores in parallel, uses better algorithms, handles input in reverse Polish notation, and can be tweaked via command-line flags.


> What's New in v1.1
> ==================

> Bugfixes:

>  - In version 1.0.0, when neither ``gmpy`` nor ``gmpy2`` could be imported, ``legendre`` was not defined properly and errors were thrown.  This is fixed in version 1.1.

> New features:

>  - A new function ``factorint`` is added with the same argument structure as the ``primefac`` generator, minus the ``verbose`` option.  This collates ``primefac``'s output into a dict with the prime factors as the keys and their multiplicities as the data.  For example, ``factorint(5040)`` returns ``{2:4, 3:2, 5:1, 7:1}``.
>  - 
>  __Author__: lucasbrown.cit
>  
> __Maintainer__: lucasbrown.cit
> 
> __Home Page__: https://pypi.python.org/pypi/primefac
> 
> __License__: MIT 


[Python]: http://python.org/
[primefac]: https://pypi.python.org/pypi/primefac
[fork]: https://en.wikipedia.org/wiki/Fork_(software_development)
[modular inverse]: https://en.wikipedia.org/wiki/Modular_multiplicative_inverse