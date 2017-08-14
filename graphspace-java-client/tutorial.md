# Tutorial

### Import GraphSpace

```
import org.graphspace.javaclient.Client
```

### Connecting to GraphSpace

To connect to GraphSpace, create a new instance using your username and password.

```
Client client = new Client();
client.authenticate(username, password);
```

In case you want to use a different host, you can connect by specifying the host.

```
Client client = new Client();
client.authenticate(hostUrl, username, password);
```

### Fetching a graph from GraphSpace

To import a graph from GraphSpace by graph's name use the *getGraphByName* method.

```
JSONObject graph = client.getGraphByName(graphName);
```

To import a graph from GraphSpace by graph's id use the *getGraphById* method.

```
JSONObject graph = client.getGraphById(graphId);
```

### Fetching all personal graphs from GraphSpace

To import all your personal graphs from GraphSpace, use the *getMyGraphs* method.
You can set the limit for number of graphs that should be imported.
You can also offset the search of graphs by setting the offset parameter.

To search graphs based on names, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around your search term, for example, %searchTerm%

Similarly, to search graphs based on tags, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around the tag name, for example, %tagName%

```
JSONObject response = client.getMyGraphs(graphNames, tagsList, limit, offset);
```

### Fetching all shared graphs from GraphSpace

To import all graphs shared among the groups you are a part of, you can use the *getSharedGraphs* method.
You can set the limit for number of graphs that should be imported.
You can also offset the search of graphs by setting the offset parameter.

To search graphs based on names, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around your search term, for example, %searchTerm%

Similarly, to search graphs based on tags, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around the tag name, for example, %tagName%

```
JSONObject response = client.getSharedGraphs(graphNames, tagsList, limit, offset);
```

### Fetching all public graphs from GraphSpace

To import all public graphs from GraphSpace, use the *getPublicGraphs* method.
You can set the limit for number of graphs that should be imported.
You can also offset the search of graphs by setting the offset parameter.

To search graphs based on names, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around your search term, for example, %searchTerm%

Similarly, to search graphs based on tags, you can pass an ArrayList (graphNames). To do a wildcard search, add
<em>%</em> around the tag name, for example, %tagName%

```
JSONObject response = client.getPublicGraphs(graphNames, tagsList, limit, offset);
```

### Saving a graph on GraphSpace

To export a graph to GraphSpace use the *postGraph* method

```
client.postGraph(graphJSON, styleJSON);
```

### Updating a graph on GraphSpace

To update an existing graph on GraphSpace use the *updateGraph* method

```
client.updateGraph(name, ownerEmail, graphJSON, isPublic);
```

You can also change the access level of a graph. You can make a graph public or private.

### Making a graph public on GraphSpace

```
client.makeGraphPublic(graphName);
```

### Making a graph private on GraphSpace

```
client.makeGraphPrivate(graphName);
```

### Deleting a graph on GraphSpace

To delete a graph, use deleteGraph method

```
client.deleteGraph(graphName);
```

### Fetching a graph layout from GraphSpace

You can import individual layout for a particular graph by using graph's and layout's id. To do this, use the *getGraphLayout* method

```
JSONObject layout = client.getGraphLayout(graphId, layoutId, ownerEmail);;
```

### Fetching all personal layouts for a graph

To import all your personal layouts for a graph, use the *getMyGraphLayouts* method.
You can also use limit and offset parameters to limit your search.

```
Layouts.getMyGraphLayouts(graphId, limit, offset);
```

### Fetching all shared layouts for a graph

To import all shared layouts for a graph, use the *getSharedGraphLayouts* method.
You can also use limit and offset parameters to limit your search.

```
Layouts.getSharedGraphLayouts(graphId, limit, offset);
```

### Saving a graph layout on GraphSpace

To export a layout to GraphSpace use the *postGraphLayout* method
Give the layout a name and pass it as a parameter.

```
client.postGraphLayout(graphId, layoutName, positionsJSON, styleJSON, isGraphShared);
```

### Updating a graph layout on GraphSpace

Update an existing layout on GraphSpace using the *updateGraphLayout* method

```
client.updateGraphLayout(graphId, layoutId, layoutName, positionsJSON, styleJSON, isGraphShared);
```

### Deleting a graph layout on GraphSpace

You can delete a layout using graph's and layout's ID.

```
client.deleteGraphLayout(graphId, layoutId);
```

### Fetch a group from GraphSpace

To import a group from GraphSpace using group's name, use *getGroup* method

```
client.getGroup(groupName);
```
### Fetch all groups of which you're the ownerEmail

You can import all groups owned by you by using *getMyGroups* method

```
client.getMyGroups(limit, offset);
```

### Fetch all groups of which you're a member

To import groups where you're a member, use the *getAllGroups* method

```
client.getAllGroups(limit, offset);
```

### Post a group to GraphSpace

You can import a group to GraphSpace using the *postGroup* method where group is a GSGroup object

```
client.postGroup(group);
```

### Delete a group from GraphSpace

To delete a group from GraphSpace, use the *deleteGroup* method
client.deleteGroup(groupName, groupId);

### Get members of a group

To get all the members of a group use the *getGroupMembers* method

```
client.getGroupMembers(groupName, groupId, group);
```

### Add a member to a group

To add a member to a group, use the *addGroupMember* method

```
client.addGroupMember(memberEmail, groupName, groupId, group);
```
### Delete a member from a group

To delete a member from a group, use the *deleteGroupMember* method

```
client.deleteGroupMember(memberId, member, groupName, groupId, group);
```

### Get graphs belonging to a group

To import all graphs belonging to a group, use the *getGroupGraphs* method

```
client.getGroupGraphs(groupName, groupId, group);
```

### Share a graph with a group

You can share a graph with a group using the *shareGraph* method

```
client.shareGraph(graphName, graphId, graph, groupName, groupId, group);
```

### Un-Share a graph with a group

You can un-share a previously shared graph with a group use the *unshareGraph* method

```
client.unshareGraph(graphName, graphId, graph, groupName, groupId, group);
```
