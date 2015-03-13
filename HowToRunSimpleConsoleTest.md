# Introduction #

There is a simple console (aka command line) test app [see code here](http://code.google.com/p/sqlitepersistentobjects/source/browse/trunk/#trunk/Sample%20Code/SimpleConsoleText), this topic covers how to build and run it.

# Details #

What do we have:
  * There are persistent classes like Post and PostComment.
  * There is the main.m that runs the little test.

To Build the app:
  * You need the tool **cmake**, so download/install etc that first.
  * First you need to generate the makefile, do this with this command run in the SimpleConsoleText directory
    * cmake CMakeLists.txt
      * Alternatively (or just a tip) add the option **-G Xcode** to get an Xcode project built. Beware dont forget to turn off "Load symbols lazily" in Xcode preferences, otherwise the breakpoints do not get found
  * This should create a file called **Makefile** for you.
  * Now run **make** to use this file to build the console app.
  * This should give you an executable called **ConsoleTest**

To Run the app:
  * just type **./ConsoleTest** at the command line - you should get output similar to this:
```
* Removing DB
* Creating test objects
Confirmed not in DB yet
Confirmed object in DB now
2009-02-21 08:05:52.015 ConsoleTest[4715:10b] Object of type 'PostInvalid' seems to be uninitialised, perhaps init does not call super init.
* DB schema is:
CREATE TABLE post (pk INTEGER PRIMARY KEY, title TEXT, text TEXT);
CREATE TABLE post_category (pk INTEGER PRIMARY KEY, title TEXT);
CREATE TABLE post_comment (pk INTEGER PRIMARY KEY, title TEXT, post TEXT);
CREATE TABLE post_invalid (pk INTEGER PRIMARY KEY, text TEXT);

* Entries in table post
pk          title        text      
----------  -----------  ----------
1           Test post 1  text      
2           Test post 2  text      

* Entries in table post_comment
pk          title                post      
----------  -------------------  ----------
1           Comment 1 to Post 2  Post-2    

* Requested objects for class Post, 2 returned:
	<Post.1 Test post 1>
	<Post.2 Test post 2>
* Showing PostComment objects related to Post
	<Post.1 Test post 1>
	<Post.2 Test post 2>
		<PostComment.1 Comment 1 to Post 2>
```