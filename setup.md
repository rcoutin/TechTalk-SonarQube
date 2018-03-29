### Get Started in Two Minutes
1. Unzip - let's say in "C:\sonarqube" or "/etc/sonarqube", the SonarQube distribution once it's downloaded. ([Download Page](http://www.sonarsource.org/downloads/))

2. Start the SonarQube server:
```
# On Windows, execute:
C:\sonarqube\bin\windows-x86-xx\StartSonar.bat
 
# On other operating system, execute:
/etc/sonarqube/bin/[OS]/sonar.sh console
```
3. Log in to http://localhost:9000 with System Administrator credentials (admin/admin) and follow the tutorial to analyze your first project.

### After the install - Analyzing Source Code

Once the SonarQube platform has been installed, you're ready to install an analyzer and begin creating projects. A project is created in the platform automatically on its first analysis. However, if you need to set some configuration on your project before its first analysis, you have the option of provisioning it.

##### Scope of Analysis: Types of Files and Data
SonarQube can perform analysis on [20+ different languages](https://docs.sonarqube.org/display/PLUG/Plugin+Library). The outcome of this analysis will be quality measures and issues (instances where coding rules were broken). However, what gets analyzed will vary depending on the language:

On all languages, "blame" data will automatically be imported from supported SCM providers. Git and SVN are supported automatically. Other providers require [additional plugins](https://docs.sonarqube.org/display/PLUG/Plugin+Library).
On all languages, a static analysis of source code is performed (Java files, COBOL programs, etc.)
A static analysis of compiled code can be performed for certain languages (.class files in Java, .dll files in C#, etc.)
A dynamic analysis of code can be performed on certain languages.

##### During Analysis
During analysis, data is requested from the server, the files provided to the analysis are analyzed, and the resulting data is sent back to the server at the end in the form of a report, which is then analyzed asynchronously server-side.

Analysis reports are queued, and processed sequentially, so it is quite possible that for a brief period after your analysis log shows completion, the updated values are not visible in your SonarQube project. However, you will be able to tell what's going on because an icon will be added next to the project name. Mouse over it for more detail (and links if you're logged in with the proper permissions.)

##### Running Analysis
First, you should install the plugin(s) for the language(s) of the project to be analyzed, either by a direct download or through the update center.

Then, you need to choose an analysis method. The following are available:

* [SonarQube Scanner for MSBuild](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+MSBuild): Launch analysis of .Net projects
* [SonarQube Scanner for Maven](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Maven): Launch analysis from Maven with minimal configuration
* [SonarQube Scanner for Gradle](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Gradle): Launch Gradle analysis
* [SonarQube Scanner for Ant](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Ant): Launch analysis from Ant
* [SonarQube Scanner For Jenkins](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner+for+Jenkins): Launch analysis from Jenkins
* [SonarQube Scanner](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner): Launch analysis from the command line when none of the other analyzers is appropriate  
