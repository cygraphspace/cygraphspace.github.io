# Overview
GraphSpace Java Client is a Java Client library for the GraphSpace REST API. It simplifies the process of authentication, request construction, and response parsing for Java developers using the GraphSpace API.

# Why use GraphSpace Java Client?
GraphSpace Java Client allows a user to import and upload the network from GraphSpace with a few lines of code. Moreover, the user need not know the details of the REST API to use this module. It is very easy to integrate this library into a user’s software pipeline.

# Who uses  GraphSpace Java Client?
The potential audience for graphspace_python includes biologists, computer scientists and data scientists.

# Note
This library currently does not allow you to create graphs from scratch. In case you need more functionlity, it is recommended to use [python client](https://graphspace-python.readthedocs.io) instead.

# Installation
Get the GraphsSpace Java Client jar file from [here](https://github.com/Murali-group/CyGraphSpace/blob/develop/apps/javaclient-0.0.1.jar)

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

## [Tutorial](/graphspace-java-client/tutorial.md)

## [API Reference](https://rishabhsethi.com/cygraphspacejavadoc)
