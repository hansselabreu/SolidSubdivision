# Keep it DRY

Don't Repeat Yourself or it's acronym DRY, is a really important principle in software development. The DRY principle states:

>Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

That means that all the knowledge involved in the application may only occur exactly once in your entire system. That's it, not twice nor three times, only **ONCE**. 

Try to avoid repetition at all cost. Dry also leads to readable maintainable code. For example, if you're using jQuery in your app, you could have some code written like this:

```
$('#someDiv').hide();

var value = $('#someInput').val();
// Some More Code ...
$('#someInput').val('');


$('#someDiv').show();
```

You could DRYup this code a little by just doing something like this:

```
var someDiv = $('#someDiv'),
	someInput = $('#someInput');

someDiv.hide();

var value = someInput.val();
// Some More Code ...
someInput.val('');


someDiv.show();
```
That simple change could not only improve your entire application performance, it also improves it's readability and the way the app is maintained.

This principle it's well known because it appear on the book [The Pragmatic Programmer](http://www.amazon.com/gp/product/020161622X/ref=as_li_ss_tl/?ie=UTF8&linkCode=as2&camp=1789&creative=390957&creativeASIN=020161622X) by Andy Hunt and Dave Thomas
