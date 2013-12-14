If the programming language let's do you something, it doesn't mean you should
------------

Correct code is not always good code.

[PENDING]

Take this c++ code as an example. It's completely valid code, will compile, and some times run, without problems:

    int array[10]; 
    array[0] = 45; 
    array[4] = 12; 
    array[10] = 8; //will not give an error  
    
    //Even though outside of the bounds of the declared array, 
    //it will try assign to the memory space anyway


In this particular case, the programmer has a lot of control over memory management. This simple mistake can lead to memory issues further down the road.  Learn the inner workings and quirks of the language you're using.