Don't use variable shadowing. It's evil
------------

Have you heard about [variable shadowing](http://en.wikipedia.org/wiki/Variable_shadowing)? It's when a variable in the current scope shadows the variable in the enclosing outer scope.

Here is an example in Python code taken from wikipedia:

    x = 1
    print(x) # OUTPUT: 1
     
    def f():
        x = 3
        print(x)
     
    f() # OUTPUT: 3(f shadows x, so print(x) refers to the value 3)
    print(x) # OUTPUT: 1 (the global x isn't affected by f)

This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

_References_

* [Wikipedia - Variable Shadowing](http://en.wikipedia.org/wiki/Variable_shadowing)
* [StackOverflow - Coffeescript thinks shadowing is a bad idea](http://stackoverflow.com/questions/15223430/why-is-coffeescript-of-the-opinion-that-shadowing-is-a-bad-idea)
* [leepoint.net Java Notes = Shadow variables are evil](http://www.leepoint.net/notes-java/data/variables/60shadow-variables.html)
* [Eric Lippert - Reading code is hard](http://blogs.msdn.com/b/ericlippert/archive/2004/06/14/155316.aspx)