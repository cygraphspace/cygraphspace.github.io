# Missing Functionality

### 1. Style Import

As pointed out above, because of the various problems in implementing a reliable solution for this feature, this functionality is not yet released with the stable version of the app.

This is in works in a separate branch and might be available in future releases.

### 2. Sharing Graph and adding tags

Sharing graph and adding tags was previously implemented but later removed because the mentor didn't like the UI and a better UI needs to be thought of for this functionality.

### 3. User authentication persistent across sessions

There is a trivial method to store user's data persistently across sessions as listed [here](http://wiki.cytoscape.org/Cytoscape_3/AppDeveloper/Cytoscape_3_App_Cookbook#How_to_use_CyProperty_to_save_values_across_sessions.3F).
However, this doesn't seem to work as the values reset in the next session.

A probable reason is that there is a bug in the current version of Cytoscape since the sample app provided by Cytoscape to showcase this functionality also faces similar problem.
