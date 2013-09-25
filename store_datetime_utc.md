When storing Date/DateTime always do UTC
------------

You're working on your app, and you need to store the last time your user logged in. Oh that's just `DateTime.Now()` and store that in the database right? **Wrong!**

* You may have many users, from different places and time zones. Using anything other than UTC leads to ambiguities. specifically when doing queries that involve retrieving a log of sorted user actions. 
* Daylight savings rules change from time to time and country to country.
* You may change your hosting provider, which could be located on another time zone different than the previous one. 

Storing datetime values in UTC is the only sensible answer to all of these issues. If you have visitors from different parts of the globe, then ask them in which Timezone they're in, and make your site/app translate the UTC date to their local time to provide a better experience (just don't try to detect it automatically, as this will be unreliable). 

_References:_
* [Ian Mercer - DateTime values should always be stored in UTC](http://blog.abodit.com/2010/02/datetime-values-should-always-be-stored-in-utc)
* [4 guys from rolla - Using UTC to store Date/Time values](http://www.4guysfromrolla.com/articles/081507-1.aspx)
* [Stack Overflow - UTC Vs. Offset](http://stackoverflow.com/questions/4715620/storing-datetime-utc-vs-storing-datetimeoffset)
