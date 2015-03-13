# Introduction #

This topic relates to a typical edit screen scenario, you bring up the screen filled with data from a persistent object, user makes changes, code updates the object (in memory, not saved yet), but then the user cancels the edit and we wish to revert to the object the way it was before...

# Details #

To handle this, all persistent objects have a
**revert** method and ways to check if any data has been altered.