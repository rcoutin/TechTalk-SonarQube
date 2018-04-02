# SonarQube 

Sonarqube is a Continuous Inspection framework that provides insight on the Code Quality characteristics of source code. It performs static analysis on code to detect bugs, code smells, duplicated code and security vulnerabilities, and provides descriptive review comments automatically. Its vast array of plugins adds support for a variety of programming languages and integration to a majority of DevOps platforms.

Here are some of the features that Sonarqube offers - 

**Centralized Dashboard** - An interface that provides a unified status of the projects code quality trends.    
**QualityGate** - Customize parameters that gauge the quality of code, as per your organizational thresholds.  
**External Integration** - Sonarqube integrates well with several popular Build Systems like Maven, Gradle and Ant, and Continuous Integration Engines like Jenkins, Travis CI, AppVeyor and more.    
**REST API** - Sonarqube's web API can be used to automatically provision a SonarQube project and also monitor the scanning process.  

### Benefits
* **Fast and Scalable:** You can easily scale the SonarCloud as the size of the project grows. No hassels for the user since it is entirely on the cloud and it automatically handles scalability.  
* **Thousands of rules:** Thanks to powerful static code analyzers, you can monitor an array of rules and can easily track down bugs and other quality issues.
* **Deep code analysis:** SonarCloud can explore all your source files, whether in branches or pull requests, to reach a green quality gate and promote the build. This makes it really handy to use in huge teams where each team commits to a separate branch, so that the code can be properly analyzed before it can be merged into the master branch.
* **Support for 16 languages:** It supports a variety of languages like Java, JS, C#, C/C++, Objective-C, TypeScript, Python, ABAP, PLSQL, T-SQL etc, so it is pretty flexible and can be appied over an array of projects.  

### Limitations
* **Cost:** Its greatest con is its plugins cost in regards to certain languages, as well as the cost of licensing the enterprise model. Developers who produce millions of lines of code a year will be shelling out up to $62,000 per year to use the software, depending on output, and costs per year for huge, high availability database applications could reach $1 million per year
* **SonarQube is not a build tool:** There are several tools out there like Maven, Ant, Gradle etc. that do a perfect job on that field. SonarQube expects that before you analyze a project it has been already compiled and built by your favorite build tool.

### What it is not!

* **SonarQube is not a code coverage tool:** It is integrated with the most popular test coverage tools like JaCoCo, Cobertura, PHPUnit etc. but it does not compute code coverage itself. It reads pre-generated unit test report files and displays them in an extremely convenient dasboard.
* **SonarQube is not a code formatter:** It is not allowed to modify your code in any way. However, you can get formatting suggestions by enabling the CheckStyle, CPPCheck, ScalaStyle rules you want to follow.
* **SonarQube is not a continuous integration system to run your nightly builds:** You can integrate it with the most popular CI Engines to apply Continuous Inspection but it’s not their replacement.

### Components

SonarQube offers the following components that can be mixed and matched as per user requirements.

1) **SonarQube Server** 

The SonarQube server acts as an in-depth, yet user-friendly, dashboard for viewing code quality characteristics of projects. Internally, it is a collection of backend servers that enable developers, managers to visualize quality snapshots and configure the SonarQube instance. It consists of a Search Server based on ElasticSearch to back searches from the UI, and a Compute Engine Server in charge of processing code analysis reports and saving them in the SonarQube Database. The database also stores the configuration of the SonarQube instance (security, plugins settings, etc.) and the quality snapshots of projects, views, etc.
   
Additionally, the server may also contain multiple **SonarQube Plugins**, including language, SCM, integration, authentication, and governance plugins. The REST API is also exposed by the server. 
 
These components are readily available to the user as a package from the [download page](https://www.sonarqube.org/downloads/)

2) **SonarCloud** 

SonarCloud is a cloud-based alternative to the SonarQube server. It has all the features that the SonarQube server has to offer in addition to the minimal overhead of maintenance. SonarCloud is free for use with public repositories. 

3) **SonarQube Scanner** 

The SonarQube Scanner is the underlying computation engine that performs the static analysis of code. The above servers rely on data from the scanner. This scanner could be downloaded as a stand-alone application or used as a plugin on your Build / Continuous Integration Servers.

Sonarqube requirements are briefly mentioned [here](./requirements.md).
Sonarqube step-by-step installation guide is available [here](./setup.md).

## Integrating SonarQube with various CI Engines
### 1. Analyzing with SonarQube Scanner for Jenkins
For integrating SonarQube Scanner for Jenkins, we use the SonarQube Scanner for Jenkins 2.6.1. This plugin lets you centralize the configuration of SonarQube server connection details in Jenkins global configuration. Then you can trigger SonarQube analysis from Jenkins using standard Jenkins Build Steps to trigger analysis with:
* SonarQube Scanner
* SonarQube Scanner for Maven
* SonarQube Scanner for MSBuild

Once the job is complete, the plugin will detect that a SonarQube analysis was made during the build and display a badge and a widget on the job page with a link to the SonarQube dashboard as well as quality gate status. 

[Here](https://github.ncsu.edu/rcoutin/SonarQube/blob/master/SonarQubeWithJenkins.md) you can find a step-by-step procedure to integrate SonarQube with Jenkins to run unit test cases and publish results to SonarQube.

### 2. Analyzing with SonarQube Scanner for Maven
This analyzer is recommended to launch analysis on Java Maven project.

**Compatibility**: Maven 3.x

**Prerequisites**:
* Maven 3.x
* SonarQube is already [installed](https://docs.sonarqube.org/display/SONAR/Installing+the+Server)
* At least the minimal version of Java supported by your SonarQube server is in use (Java 8 for latest LTS)
* The language plugins for each of the languages you wish to analyze are installed
* You have read [Analyzing Code Source](https://docs.sonarqube.org/display/SONAR/Analyzing+Source+Code). 

**Initial Setup**
Edit the settings.xml file, located in $MAVEN_HOME/conf or ~/.m2 or /etc/maven/, to set the plugin prefix and optionally the SonarQube server URL.

Example: 
```
<settings>
    <pluginGroups>
        <pluginGroup>org.sonarsource.scanner.maven</pluginGroup>
    </pluginGroups>
    <profiles>
        <profile>
            <id>sonar</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <!-- Optional URL to server. Default value is http://localhost:9000 -->
                <sonar.host.url>
                  http://myserver:9000
                </sonar.host.url>
            </properties>
        </profile>
     </profiles>
</settings>
```

**Analyzing a Maven Project**
Analyzing a Maven project consists of running a Maven goal: sonar:sonar in the directory where the pom.xml file sits.
```
mvn clean verify sonar:sonar
  
# In some situation you may want to run sonar:sonar goal as a dedicated step. Be sure to use install as first step for multi-module projects
mvn clean install
mvn sonar:sonar
```
### 3. Continuous Inspection with TravisCI 

TravisCI offers a SonarCloud plugin that allows for static code analysis on every commit, thus enabling Continuous Inspection. This integration also enables automatic review comments in pull requests.

A brief summary of steps have been outlined below with links to detailed documentation

* **Setup SonarCloud**   
   * Register to SonarCloud at www.sonarcloud.io  
   * Create an Organization, note its name and key  
   * Create a [User authentication token](https://sonarcloud.io/account/security) on SonarCloud and keep it handy  
* [**Enable Travis Integration**](https://docs.travis-ci.com/user/sonarcloud/)  
   * Create a .travis.yml file : This tells Travis that the SonarCloud addon has to be used and what parameters it needs.  
   * Create a sonar-project.properties file to configure the scanner properties like project-key and project-name
* [**Enable Pull Request reviews**](https://docs.travis-ci.com/user/sonarcloud/#Analysis-of-internal-pull-requests)  
   * Create a new GitHub account for the bot that SonarCloud will use to comment on Pull Requests and add it as a collaborator on your project. 
   * Obtain a [Personal Access Token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) from the Developer Settings and set access permissions.   
   * Login to SonarCloud; Configure the Pull Request settings

**Limitations**  
* The current version can only scan Internal pull requests. External Pull Requests will be added in future versions. 
* Since the TravisCI SonarCloud addon communicates directly to the host 'www.sonarcloud.io' it is challenging to add a custom SonarQube server. This means private repositories have to be scanned at a cost, on SonarCloud instead of your own SonarQube instance.
