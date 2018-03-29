### Prerequisite
The only prerequisite for running SonarQube is to have Java (Oracle JRE 8 or OpenJDK 8) installed on your machine.

*(warning) Note: On Mac OS X it is highly recommended to install Oracle JDK 8 instead of the corresponding Oracle JRE since the JRE installation does not fully set up your Java environment properly. See [this post](https://stackoverflow.com/questions/15624667/mac-osx-java-terminal-version-incorrect) for more information.*

### Hardware Requirements
1. The SonarQube server requires at least 2GB of RAM to run efficiently and 1GB of free RAM for the OS.
2. The amount of disk space you need will depend on how much code you analyze with SonarQube. As an example, SonarCloud the public instance of SonarQube, has more than 30 millions lines of code under analysis with 4 years of history. SonarCloud is currently running on a Amazon EC2 m4.large instance, using about 10 Gb of drive space. It handles 800+ projects having roughly 3M open issues. SonarCloud is running on PostgreSQL 9.5 and it is using about 15Gb of drive space.
3. SonarQube must be installed on hard drives that have excellent read & write performance. Most importantly, the "data" folder houses the Elasticsearch indices on which a huge amount of I/O will be done when the server is up and running. Great read & write hard drive performance will therefore have a great impact on the overall SonarQube server performance.

### Supported Platforms

##### Java
The SonarQube Java analyzer is able to analyze any kind of Java source files regardless of the version of Java they comply to. But SonarQube analysis and the SonarQube Server require specific versions of the JVM.

* Oracle JRE - 8
* OpenJDK - 8

##### Database
* PostgreSQL - 8.x, 9.x
* Microsoft SQL Server - 2014, 2016
* Oracle - 11G, 12C, XE Editions
* MySQL - 5.6, 5.7

##### Web Browser
* Microsoft Internet Explorer - IE11
* Microsoft Edge - Latest
* Mozilla Firefox - Latest
* Google Chrome - Latest
* Safari - Latest