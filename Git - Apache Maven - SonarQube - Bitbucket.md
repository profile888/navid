### Apache Maven Project

```
Install Apache Maven.
Configure the required environment variables (JAVA_HOME, MAVEN_HOME, and PATH).
Verify the installation by running the following command in the terminal or command prompt:
mvn -version

A successful installation should display the Maven version, Java version, and operating system information.
```


### After Creating a Java Project

```
From the project directory, the following Maven commands should execute successfully:

mvn -version
mvn compile
mvn clean
mvn test
mvn package

Expected outcomes:

mvn compile – Compiles the source code successfully.
mvn clean – Removes previously generated build files.
mvn test – Executes all test cases successfully.
mvn package – Creates the deployable artifact (JAR/WAR file).

Run the SonarQube analysis command and verify that all code quality recommendations, issues, and metrics appear in the SonarQube dashboard.
```


### Git Setup

```
Create and maintain a .gitignore file.
Create the Bitbucket Pipeline YAML file (bitbucket-pipelines.yml).
Initialize Git in the Java project directory:
git init
Add project files:
git add .
Commit the files:
git commit -m "Initial commit"
Obtain the repository URL from Bitbucket and connect the local repository:
git remote add origin <repository-url>
Push the code to Bitbucket:
git push -u origin main

or

git push -u origin master

depending on the default branch name.
```


### SonarQube

```
Install and Configure SonarQube.
Start the SonarQube server.
Verify that the SonarQube web interface is accessible.
Generate or obtain the Bitbucket Pipeline YAML configuration required for SonarQube integration.
Add the YAML file to the Java project directory.
Obtain the SonarQube project URL for reviewing code quality reports and recommendations.
```


### Bitbucket

```
Configure the pipeline using bitbucket-pipelines.yml.
Select the branches that should trigger pipeline execution.
Ensure all pipeline stages execute successfully, including:
Build
Unit Tests
Package
SonarQube Analysis
Verify that pipeline logs are generated for every execution.
Confirm that all jobs complete successfully and the results are visible in the Bitbucket Pipeline interface.



```
