# Apache-maven-wrapper

We use this so that the system on which our maven project runs does not require maven inatalled.

# Prequisite

In order to create maven wrapper
 - developer should have maven installed (mvn -v or mvn --version)
 - go to project root directory
 - run mvn -N io.takari:maven:wrapper [-Dmaven=3.6.0]
 
It will create mvnw.cmd file
Now we can use mvnw.cmd in place of mvn to run maven commands as

mvnw.cmd --version // it is ame as mvn --version
