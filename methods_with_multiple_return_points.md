Use multiple return points on methods in favor of arrow code
------------
You might remember those non garbage-collector days, when every method needed to cleanup after itself. Therefore the need to retain program flow until the cleanup and single exit point at the end. 

Garbage collected languages like Java and C# take care of cleaning up for you ([mostly](http://msdn.microsoft.com/en-us/library/system.idisposable.aspx "mostly")). That leaves you with room to enhance the clarity of your code and avoid nested if statements or needlessly long execution paths maintainers of your code need to keep. It is not uncommon to find code resembling the code below.


	//c# code
	decimal ApplyInterestRate(AgeBracket ageBracket, bool isMarried) 
	{
		decimal result = 0.0;
		if(ageBracket == AgeBracket.FreshMeat) 
		{
			//..some code
			result = someVariable;
			
			//...more code
			result = someOtherVariable;
		}
		else if(ageBracket == AgeBracket.YoungDude) 
		{
			//...some code
			result = someOtherOtherVariable;
		}
		else if(ageBracket == AgeBracket.OldGuy)
		{
			//...some code
			result = someOtherOtherVariable;
		}
		else 
		{
			result = 0.0;
		}
		return result;
	}

Converting this single exit method to a multiple exit method would allow for more clarity and a better stated intent of the processing being done. Every block would benefit from an independent return as it is already suggested by the code structure. Like so:

	//c# code
	decimal ApplyInterestRate(AgeBracket ageBracket, bool isMarried) 
	{
		if(ageBracket == AgeBracket.FreshMeat) 
		{
			//..some code
			return someVariable;
			
			//...more code
			return someOtherVariable;
		}
		
		if(ageBracket == AgeBracket.YoungDude) 
		{
			//...some code
			return someOtherOtherVariable;
		}
		
		if(ageBracket == AgeBracket.OldGuy)
		{
			//...some code
			return someOtherOtherVariable;
		}
		
		return 0.0;
	}

Also by using this practice, methods that are doing too much would pop more easily and allow you to refactor into smaller methods with more atomic operations.


_References_

* [Thou Shalt Have One Exit Point Per Subroutine](http://www.secretgeek.net/monkey_exit.asp)

* [Should a function have only one return statement?](http://stackoverflow.com/questions/36707/should-a-function-have-only-one-return-statement)

* [Multiple Exit Points](http://www.theregister.co.uk/2007/12/04/multiple_exit_wounds/)

* [Flattening Arrow Code](http://www.codinghorror.com/blog/2006/01/flattening-arrow-code.html)