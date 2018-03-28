### Here is a step-by-step procedure to integrate SonarQube with Jenkins to run unit test cases and publish results to SonarQube.
#### Installation
1. Install the SonarQube Scanner for Jenkins via the Jenkins Update Center.
2. Configure your SonarQube server(s):

      a. Log into Jenkins as an administrator and go to Manage Jenkins > Configure System.
      
      b. Scroll down to SonarQube configuration section, click on Add SonarQube, and add the values you're prompted for.
      
#### Use
##### Global Configuration
This step is mandatory if you want to trigger any of your SonarQube analyses with the SonarQube Scanner. You can define as many scanner instances as you wish. Then for each Jenkins job, you will be able to choose with which launcher to use to run the SonarQube analysis.

1. Log into Jenkins as an administrator and go to Manage Jenkins > Global Tool Configuration.

2. Scroll down to the SonarQube Scanner configuration section and click on Add SonarQube Scanner. It is based on the typical Jenkins tool auto-installation. You can either choose to point to an already installed version of SonarQube Scanner (uncheck 'Install automatically') or tell Jenkins to grab the installer from a remote location (check 'Install automatically').

##### Job Configuration
1. Configure the project, and scroll down to the Build section. 

2. Add the SonarQube Scanner build step to your build.

3. Configure the SonarQube analysis properties. You can either point to an existing sonar-project.properties file or set the analysis properties directly in the Analysis properties field.
