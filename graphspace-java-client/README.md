# Overview
GraphSpace Java Client is a Java Client library for the GraphSpace REST API. It simplifies the process of authentication, request construction, and response parsing for Java developers using the GraphSpace API.

# Why use GraphSpace Java Client?
GraphSpace Java Client allows a user to import and upload the network from GraphSpace with a few lines of code. Moreover, the user need not know the details of the REST API to use this module. It is very easy to integrate this library into a user’s software pipeline.

# Who uses  GraphSpace Java Client?
GraphSpace was incepted to make sharing of graphs among systems biologists easier, thus enabling greater collaboration.

However, GraphSpace has matured into a much broader tool and is agnostic about the type of graph shared. Today, GraphSpace is used by Biologists, Computer Scientists as well
as Data Scientists to share varied types of graphs. Have a look at some of the graphs [here](http://www.graphspace.org/graphs)

# Note
The GraphSpace Java Client library is currently very limited as it was created with different goals. Currently, it does not support
creating graphs from the ground up. In case you need more functionlity, it is recommended to use [python client](https://graphspace-python.readthedocs.io) instead.
Please file an [issue](http://github.com/Murali-group/CyGraphSpace/issues) if you'd like us to implement any feature.

# Installation
Get the GraphsSpace Java Client jar file from [here](https://github.com/Murali-group/CyGraphSpace/blob/develop/apps/GraphSpaceJavaClient-1.0.0.jar)

### For Maven Projects

- Save the jar file in the **{basedir}/lib** directory.

- Then, in pom.xml file of your maven project, add the following dependency.

```
<dependency>
    <groupId>org.graphspace</groupId>
    <artifactId>javaclient</artifactId>
    <version>1.0.0</version>
</dependency>
```
- Then add **maven-install-plugin** and set the **graphspace-java-client path**.

```
<plugins>
    ...
    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-install-plugin</artifactId>
        <version>2.5.2</version>
        <executions>
            <execution>
            <id>install-external</id>
            <phase>clean</phase>
            <configuration>
                <file>${basedir}/lib/GraphSpaceJavaClient-1.0.0.jar</file>
                <repositoryLayout>default</repositoryLayout>
                <groupId>org.graphspace</groupId>
                <artifactId>javaclient</artifactId>
                <version>1.0.0</version>
                <packaging>jar</packaging>
                <generatePom>true</generatePom>
            </configuration>
            <goals>
                <goal>install-file</goal>
            </goals>
            </execution>
        </executions>
    </plugin>
    ...
</plugins>`
```
<br/>

### Building jar from source
You can also build the jar file from source. To do this, get the code from [here](https://github.com/Murali-group/CyGraphSpace/tree/develop/GraphSpaceJavaClient).

If you don't have eclipse installed, download it from [here](http://www.eclipse.org/downloads/) first. Eclipse is not required but is recommended.

> Note: You'll need Java 8 or above to run GraphSpaceClient.

* Import GraphSpaceJavaClient folder into eclipse as a maven project. To do this,

    1. Go to File>Import.
    1. Select Maven>Existing Maven Projects
    1. Select the GraphSpaceJavaClient folder

> In case you wish to develop on GraphSpaceJavaClient, it is recommended that you fork the repo first so that git is pointed to your personal repository.

* Right click pom.xml file and select "Run As>Maven Install". The created jar file after the build process will be located inside the target directory.

* If you are developing the library, you can use the prewritten tests inside the tests package to test your modified methods.

## [Tutorial](/graphspace-java-client/tutorial.md)

## [API Reference](https://cygraphspace.github.io/javaclientdocs/)
