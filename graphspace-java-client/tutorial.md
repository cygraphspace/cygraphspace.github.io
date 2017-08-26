# Tutorial

### Import GraphSpace

```
import org.graphspace.javaclient.Client
```

### Connecting to GraphSpace

To connect to GraphSpace, create a new instance using your username and password.

```
GraphSpaceClient client = new GraphSpaceClient(username, password);
```

In case you want to use a different host, you can connect by specifying the host.

```
GraphSpaceClient client = new GraphSpaceClient(hostUrl, username, password);
```

In case you are behind HTTP/HTTPS proxy, you can specify the proxy to make the appropriate connection.

```
client.setProxy(proxyHost, proxyPort)
```

To make sure you are connected to GraphSpace and correctly authenticated, use the *isAuthenticated* method.

```
client.isAuthenticated()
```

## Graph Methods

### Fetching a graph from GraphSpace

To import a graph from GraphSpace by graph's name use the *getGraph* method with the name.

```
JSONObject graph = client.getGraph(graphName);
```

To import a graph belonging to some other user from GraphSpace by graph's name use the *getGraph* method with the graph name and the owner's email.

```
JSONObject graph = client.getGraph(graphName, ownerEmail);
```

To import a graph from GraphSpace by graph's id use the *getGraph* method with graph's id.

```
JSONObject graph = client.getGraph(graphId);
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

In case you want to do an open search without restricting to particular names or tags, you can get the graphs by specifying just the limit and offset.
```
JSONObject response = client.getMyGraphs(limit, offset);
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

In case you want to do an open search without restricting to particular names or tags, you can get the graphs by specifying just the limit and offset.
```
JSONObject response = client.getSharedGraphs(limit, offset);
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

In case you want to do an open search without restricting to particular names or tags, you can get the graphs by specifying just the limit and offset.

```
JSONObject response = client.getPublicGraphs(limit, offset);
```

### Saving a graph on GraphSpace

To export a graph to GraphSpace use the *postGraph* method.

To do this, you need to specify the graph Json and the style Json for the graph.

You'll also need to specify if you want to make graph public or private.


```
client.postGraph(graphJson, styleJson, isGraphPublic);
```

### Updating a graph on GraphSpace

To update a graph to GraphSpace use the *updateGraph* method.

To do this, you need to specify the graph Json and the style Json for the graph.

You'll also need to specify if you want to make graph public or private.

```
client.updateGraph(name, graphJson, styleJson, isGraphPublic);
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

## Layout methods

### Fetching a graph layout from GraphSpace

You can import individual layout for a particular graph using graph's and layout's id. To do this, use the *getGraphLayout* method

```
JSONObject layout = client.getGraphLayout(graphId, layoutId);;
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
client.postGraphLayout(graphId, layoutName, positionsJson, styleJson, isGraphShared);
```

### Updating a graph layout on GraphSpace

Update an existing layout on GraphSpace using the *updateGraphLayout* method

```
client.updateGraphLayout(graphId, layoutName, positionsJSON, styleJSON, isGraphShared);
```

### Deleting a graph layout on GraphSpace

You can delete a layout using graph's and layout's ID.

```
client.deleteGraphLayout(graphId, layoutId);
```

## Group Methods

### Fetch a group from GraphSpace

To import a group from GraphSpace using group's name, use *getGroup* method

```
client.getGroup(groupName);
```

### Fetch all groups of which you're the owner

You can import all groups owned by you by using *getMyGroups* method
Use limit to limit your search to a certain number of results. Use offset to offset the results.

```
client.getMyGroups(limit, offset);
```

### Fetch all groups of which you're a member

To import groups where you're a member, use the *getAllGroups* method
Use limit to limit your search to a certain number of results. Use offset to offset the results.

```
client.getAllGroups(limit, offset);
```

### Post a group to GraphSpace

You can export a group to GraphSpace using the *postGroup* method where group is a Group object. You need to first create a group with name and description.

```
Group group = new Group(name, description);
client.postGroup(group);
```


### Update an existing group on GraphSpace

To update an existing group on GraphSpace, use the *updateGroup* method. To use this method, you first need to get the group from GraphSpace using group's name or group ID.

```
> Group group = new Group(groupId);  or Group group = new Group(groupName);
Then make changes to the group. For example,
> group.setName(newName);
Finally, update the group.
> group.updateGroup();

```

### Delete a group from GraphSpace

To delete a group from GraphSpace, use the *deleteGroup* method.

To delete a group using group's ID:

```
client.deleteGroup(groupId);
```

To delete a group using group's name:

```
client.deleteGroup(groupName);
```

### Get members of a group

To get all the members of a group use the *getGroupMembers* method.

You'll first need to get the group from GraphSpace using getGroup method with groupName or groupId.

```
Group group = client.getGroup(groupName); or Group group = client.getGroup(groupId);
client.getGroupMembers(group);
```

### Get member from a group

To get a member of a group use the *getGroupMember* method using the member's email.

You'll first need to get the group from GraphSpace using getGroup method with groupName or groupId.

```
Group group = client.getGroup(groupName); or Group group = client.getGroup(groupId);
client.getGroupMember(group, memberEmail);
```

### Add a member to a group

To add a member to a group, use the *addGroupMember* method.

You'll first need to get the group from GraphSpace using getGroup method with groupName or groupId.

```
> Group group = client.getGroup(groupName); or Group group = client.getGroup(groupId);
Then, you need to create a member object with the member's email.
> Member member = new Member(memberEmail);
Finally, add the member to the group.
> client.addGroupMember(group, member);
```

### Delete a member from a group

To delete a member from a group, use the *deleteGroupMember* method.

You'll first need to get the group from GraphSpace using getGroup method with groupName or groupId.

```
> Group group = client.getGroup(groupName); or Group group = client.getGroup(groupId);
Then, you need to get the member object from the group.
> Member member = client.getGroupMember(group, memberEmail);
Finally, delete the member from the group.
> client.deleteGroupMember(group, member);
```

### Get graphs belonging to a group

To import all graphs belonging to a group, use the *getGroupGraphs* method.

You'll first need to get the group from GraphSpace using getGroup method with groupName or groupId.

```
Group group = client.getGroup(groupName); or Group group = client.getGroup(groupId);
client.getGroupGraphs(group);
```

### Share a graph with a group

You can share a graph with a group using the *shareGraph* method.

To do this, you first need to fetch the group and the graph from GraphSpace using graphId or graphName and groupId or groupName.

```
Graph graph = client.getGraph(graphId); or Graph graph = client.getGraph(graphName);
Group group = client.getGroup(groupId); or Group group = client.getGroup(groupName);
client.shareGraph(group, graph)

```

### Un-Share a graph with a group

Subsequently, you can un-share a graph with a group using the *unshareGraph* method.

To do this, you first need to fetch the group and the graph from GraphSpace using graphId or graphName and groupId or groupName.

```
Graph graph = client.getGraph(graphId); or Graph graph = client.getGraph(graphName);
Group group = client.getGroup(groupId); or Group group = client.getGroup(groupName);
client.unshareGraph(group, graph)

```
