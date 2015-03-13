# Introduction #

This page gives you some clues on how to setup your classes if you have a parent/child relationship in your persistent objects.

# Details #

  * The short answer - see the [code](http://code.google.com/p/sqlitepersistentobjects/source/browse/#svn/trunk/Sample%20Code/SimpleConsoleText)  :)
    * The sample code found in the link above contains 2 related objects, not really parent/child, **Post** and **PostComment**.  The PostComment has a link to a Post object.  Saving the PostComment will trigger the related Post object to be saved too - although thats not currently demonstrated in **main.m**.

  * The long answer...
    * Setup your parent and child objects as you need - {A} collections of children in the parent (if needed) and {B} links from the child to the parent (if needed) or both.
    * Your code will need to ensure those links/collections are maintained when adding/removing/changing the relationships
    * Now to save the whole hierarchy, just call the save method on the parent (assuming the children are reachable from the parent, ie style {A} above).  If style {A} is not used but has style {B}, then calling save on the child will also save the parent.
  * If you don't have either style {A} or {B} then you have a case that I have not thought about :( - please edit the wiki/add a comment - thanks.