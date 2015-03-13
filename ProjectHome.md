Wouldn't it be nice if your Objective-C data objects just knew how to save and load themselves? It'd be nice if you could just call "save" and trust that your object would save itself properly somewhere, and that when you wanted to load it back in, you could just call a class method to retrieve the object or objects you wanted?

Well, now you can. This project uses the objective-C runtime to implement a pattern similar to ActiveRecord, but driven by the object's properties rather than the tables in the database.

The objects are completely self-contained - you do not need to write SQL or even create a SQLite file. You just subclass an existing class, and your model objects inherit the ability to load and save themselves from the database.