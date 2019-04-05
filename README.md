Maven is - at its heart - a plugin execution framework, all work is done by plugins. Looking for a specific goal to execute?

- Build plugins will be executed during the build and they should be configured in the <build></build> element from the POM.
- Reporting plugins will be executed during the site generation and they should be configured in the <reporting></reporting> element from the POM. 

To see the most up-to-date list browse the Maven central repository (https://repo.maven.apache.org/maven2/org/apache/maven/plugins/)

1. Normally, we use lifecycle phase with mvn command as,

> mvn space-separated-phase(s) [options]
> eg mvn clean install -DskipTests  

2. but it can also execute plugin goals. The usage description of mvn is

> mvn  <plugin-prefix>:<goal> [options] 
> eg mvn clean:clean  

# Note:
> mvn compiler:compile
In the above example, compiler:compile, the compiler is plugin-prefix of maven-compiler-plugin and 
compile is the goal name. We can get the prefix of all plugins from Maven Plugin Directory(http://maven.apache.org/plugins/index.html).

# Another Note

- When we invoke a goal directly, Maven executes just that goal, 
<br/>whereas when we invoke a lifecycle phase all the phases up to that phase are executed.
<br/> mvn clean is similer to > mvn clean:pre-clean && mvn clean:clean && mvn clean:post-clean  

- Only in some specific cases, it make sense to invoke plugin goal directly. For example, help goal of plugin is always invoked directly. Apart from help goal, there are some specific plugins whose goals are invoked directly and two such examples are: maven-archetype-plugin and maven-help-plugin. We cover these two plugins bit later.


3. We can use help goal to list the PLUGIN goals.
To list goals of maven-compiler-plugin use following command.

> mvn compiler:help

4. To list all the plugin(s) and its goals for a PHASE , use 
> mvn help:describe -Dcmd=<phase>

# Reference
 - http://www.codetab.org/tutorial/apache-maven/plugins/maven-lifecycle-goals/
