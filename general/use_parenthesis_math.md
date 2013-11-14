Use of parentheses to group mathematical expressions
------------

This makes the expressions easier to read and allow the developer to control the operator precedence at his will.

Consider this expression without parentheses:

**a * b + c / d – 4**

and the equivalent with parentheses:

**(a * b) + (c / d) – 4**

Both expressions perform exactly the same computation, but the meaning of the second one is clearer, since parentheses are used.

Expressions (like the two above) are evaluated by following the rules of precedence. The above expressions are the same. So from a technical point of view, you do not need parentheses. However, including parentheses makes the order of evaluation explicit to the person maintaining your code (even you).

_References_

* http://www.devarticles.com/c/a/Cplusplus/C-Plus-Plus-Programming-Tips/