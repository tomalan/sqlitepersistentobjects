# Introduction #

There are some unit tests for the project based on the [Google Toolbox for the Mac](http://code.google.com/p/google-toolbox-for-mac/wiki/iPhoneUnitTesting)

# Details #

There is an Xcode project in the [Tests](http://code.google.com/p/sqlitepersistentobjects/source/browse/#svn/trunk/Tests) directory.

If you open that project and **Build** it, some tests will be run.

If **Build and Go**, it seems more tests will be run...

Not sure if I am reading the output correctly, but it seems that currently 2 tests are failing, although there are also 4 errors, but that could be just logging...:
```
Test Case '-[TestSavingAndLoading testShouldMakeDirtyAndSaveAllModifiedPropertiesWhenObjectHasBeenModifiedAfterSaving]' failed (0.261 seconds).

Test Case '-[TestDeleting testShouldDeleteObjectAndCascade]' failed (0.693 seconds).
```

Need to add some more here...