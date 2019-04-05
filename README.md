# apache-maven

1. Normally, we use lifecycle phase with mvn command as,

mvn space-separated-phase(s) [options]
eg mvn clean install -DskipTests  

2. but it can also execute plugin goals. The usage description of mvn is

mvn  <plugin>:<goal> [options] 
eg mvn clean:clean  

3. We can use help goal to list the PLUGIN goals.
To list goals of maven-compiler-plugin use following command.

> mvn compiler:help

4. To list all the plugin(s) and its goals for a PHASE , use 
mvn help:describe -Dcmd=<phase>
