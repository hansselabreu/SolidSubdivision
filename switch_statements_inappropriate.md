Your switch statement may be inappropriate
------------

If you have a switch statement like the following:

    switch (type) {
    	case TypesEnum.Type1:
    	    // code that handles Type1 stuff...
    	    break;
    	case TypesEnum.Type2:
    	    // code that handles Type2 stuff...
    	    break;
    	case TypesEnum.Type3:
    	    // code that handles Type3 stuff...
    	    break;
    	// ... several more cases...
    }

Then it might be wrong. Why?

* It might be violating object-oriented "open/closed" principle. It states that
  classes should be open for extension, but closed for modification. If in the
  future you have to handle another special case, you would have to modify the
  source file.
* It can be a pain to read. In a two-or-three-cases switch statement with a 
  relatively small number of lines per case, it might not hurt. Consider a 5-to-10
  one. It is highly likely that you would need to scroll up and down to be able 
  to read it fully.
* In high correlation with the previous two points, maintainability might be hindered.

**Go ahead and refactor to patterns**

[Strategy pattern](http://www.oodesign.com/strategy-pattern.html) is **probably** your best
bet. In short, what you do is to isolate the distinct algorithms into separate classes that
share a common interface. If you then combine them into some form of Factory, you are doing wonders. 
If you need to cover more cases, you would just need to add a new Algorithm class.

The example below shows how it may be used:

    dictionary[type].Run();


Disclaimer: like everything in Software Engineering, this is not a [Silver Bullet](http://www.cs.nott.ac.uk/~cah/G51ISS/Documents/NoSilverBullet.html).
A switch statement might not an anti pattern in every situation. And if it is, depending on the exact situation, a better solution might be out there.
Be critical.