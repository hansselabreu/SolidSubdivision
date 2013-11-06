#When using boolean variables, correlate it's name with [positive logic]

While working on a team project (or some really old code) you may encounter something like this:

 ```javascript
//javascript code
var isVisible = true; //boolean variable

if (!isVisible) {
	//some code here
	$('#someDiv').show();
}
 ```

Here, you will be showing #somediv as long as the variable **isVisible** is false. 
It will be easier and more convenient to your teammates to use [positive logic] instead:

```javascript
//javascript code
var isVisible = true; //boolean variable

if (isVisible) {
	//some code 
	$('#someDiv').show();
}
 ```

That way, you maintain a semantic relationship with your code.

###Resources: 
* [http://msdn.microsoft.com/en-US/library/aa629483.aspx](http://msdn.microsoft.com/en-US/library/aa629483.aspx)
* [http://www.c2.com/cgi/wiki?RefactorNegateIf](http://www.c2.com/cgi/wiki?RefactorNegateIf)

####Stackoverflow related question
* [http://stackoverflow.com/questions/5372898/why-should-i-use-positive-logic-in-an-if-block](http://stackoverflow.com/questions/5372898/why-should-i-use-positive-logic-in-an-if-block)

[positive logic]: http://en.wiktionary.org/wiki/positive_logic