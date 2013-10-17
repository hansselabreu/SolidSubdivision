Use assert() in your code
------------

From Code Complete 2: "_Use error-handling for conditions you expect to occur; use assertions for conditions that should never occur._" 

An assertion statement specifies a condition that you expect to be true at a point in your program. If that condition is not true, the assertion fails, a message is written to the standard error device and abort is called, terminating the program execution.

Assertions should only be in your development code and should be removed from your production code. This can be achieved by simpling including the line #define NDEBUG before the inclusion of the <assert.h> header.

**Unit tests are not a replacement for assertions.***

_References_

* [assert](http://www.cplusplus.com/reference/cassert/assert/)