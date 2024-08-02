Maven is considered a project management tool that is primarily used in the Java ecosystem (You can build non Java apps with it also). It allows you to manage the build cycle of software projects.

The use cases are the following:

Building and packaging Java applications.
Managing libraries and other dependencies.
Generating documentation and other reports.
Continuous integration and continuous deployment (in conjunction with tools like Jenkins).
Facilitating collaboration by providing a standardized project structure and build process.
Maven also has Build Lifecycles: Clean Lifecycle, Default Lifecycle and Site Lifecycle.

As a DevOps engineer, we mostly work with the Default lifecycle. This lifecycle consist of:

validate: Validates the project structure and verifies if all necessary information is available.
compile: Compiles the project's source code.
test: Runs unit tests against compiled source code.
package: Packages the compiled code into a distributable format (e.g., JAR, WAR).
install: Installs the package into the local repository for use as a dependency in other projects (.m2).
deploy: Deploys the package to a remote repository for sharing with other developers or environments (Push to Nexus).
The most common commands associated with this lifecycle are as follows:

mvn compile: Compiles the project's source code.
mvn test: Runs unit tests against compiled code.
mvn package: Packages the compiled code into a distributable format.
mvn install: Installs the package into the local repository.
mvn deploy: Deploys the package to a remote repository.
mvn site: Generates project documentation and reports.
mvn site-deploy: Deploys the generated documentation to a remote web server.
mvn clean: Executes the clean phase, deleting any previous build outputs.
An important file we should be aware of:
pom.xml files — (Project Object Model) This is a very important file due to the fact it hold information in regards to project metadata, application dependencies, plugins, build profiles, repository info, build lifecycle configurations, project relationships, distribution management (where your artifact is going to be deployed to) and reporting (configuration for generating reports like test reports, code coverage, API documentation).
If configured properly we should be inside of the EC2 right now.

We need to update the packages before we doing anything else. change to the root user then run the following commands:

sudo su

sudo apt-get update -y
After the packages install we need to install Java:

sudo apt install openjdk-11-jre -y
And finally we can install Maven:

sudo apt-get install maven -y
After both installs are complete we can verify that they are installed and see what version is present:

java -version

mvn -version
