# SonarQube 

Sonarqube is a Continuous Inspection framework that provides insight on the Code Quality characteristics of source code. It performs static analysis on code to detect bugs, code smells and security vulnerabilities, and provides descriptive review comments automatically. Its vast array of plugins adds support for a variety of programming languages and integration to a majority of DevOps platforms.

Here are some of the features that Sonarqube offers - 

**Centralized Dashboard** - An interface that provides a unified status of the projects code quality trends.  
**QualityGate** - Customize parameters that gauge the quality of code, as per your organizational thresholds.  
**External Integration** - Sonarqube integrates well with several popular Build Systems like Maven, Gradle and Ant, and Continuous Integration Engines like Jenkins, Travis CI, AppVeyor and more.  
**REST API** - Sonarqube's web API can be used to automatically provision a SonarQube project and also monitor the scanning process.

### Benefits
* **Fast and Scalable:** You can easily scale the SonarCloud as the size of the project grows. No hassels for the user since it is entirely on the cloud and it automatically handles scalability.  
* **Thousands of rules:** Thanks to powerful static code analyzers, you can monitor an array of rules and can easily track down bugs and other quality issues easily.
* **Deep code analysis:** SonarCloud can explore all your source files, whether in branches or pull requests, to reach a green quality gate and promote the build. This makes it really handy to use in huge teams where each team commits to a separate branch, so that the code can be properly analyzed before it can be merged into the master branch.
* **Cloud CI Integrations:** Execution of an analysis can be easily scheduled from Cloud CI tools like Travis, Jenkins and AppVeyor.  
* **Support for 16 languages:** It supports a variety of languages like Java, JS, C#, C/C++, Objective-C, TypeScript, Python, ABAP, PLSQL, T-SQL etc, so it is pretty flexible and can be appied over an array of projects.  

### Limitations
* **Cost:** Its greatest con is its plugins cost in regards to certain languages, as well as the cost of licensing the enterprise model. Developers who produce millions of lines of code a year will be shelling out up to $62,000 per year to use the software, depending on output, and costs per year for huge, high availability database applications could reach $1 million per year
* **SonarQube is not a build tool:** There are several tools out there like Maven, Ant, Gradle etc. that do a perfect job on that field. SonarQube expects that before you analyze a project it has been already compiled and built by your favorite build tool.
* **SonarQube is not a code coverage tool:** It's integrated with the most popular test coverage tools like JaCoCo, Cobertura, PHPUnit etc. but it doesn’t compute code coverage itself. It reads pre-generated unit test report files and displays them in an extremely convenient dasboard.
* **SonarQube is not a code formatter:** It’s not allowed to modify your code in any way. However you can get formatting suggestions by enabling the CheckStyle, CPPCheck, ScalaStyle rules you want to follow.
* **SonarQube is not a continuous integration system to run your nightly builds:** You can integrate it with the most popular CI Engines to apply Continuous Inspection but it’s not their replacement.

### Setup
Sonarqube consists of 4 components:
1. One **SonarQube Server** starting 3 main processes:
    * a Web Server for developers, managers to browse quality snapshots and configure the SonarQube instance
    * a Search Server based on Elasticsearch to back searches from the UI
    * a Compute Engine Server in charge of processing code analysis reports and saving them in the SonarQube Database
2. One **SonarQube Database** to store:
    * the configuration of the SonarQube instance (security, plugins settings, etc.)
    * the quality snapshots of projects, views, etc.
3. Multiple **SonarQube Plugins** installed on the server, possibly including language, SCM, integration, authentication, and governance plugins
4. One or more **SonarQube Scanners** running on your Build / Continuous Integration Servers to analyze projects

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
