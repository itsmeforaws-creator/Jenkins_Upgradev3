# Hello World Plugin Demo
Build a simple "Hello, World" plugin using a template.


# Install Java and Maven 
-- Java is Already Installed


## Install Maven
Download Maven Tar from https://maven.apache.org/download.cgi
Unzip tar - tar -xvzf <file_name>
move to /opt -- mv apache-maven****** /opt/


# Add the following lines to the user profile file (.profile).
M2_HOME='/opt/apache-maven-******' /opt/apache-maven-3.9.4
PATH="$M2_HOME/bin:$PATH"
export PATH

Relaunch the terminal or execute source .profile to apply the changes.
Execute mvn -version command


# Create a local folder for the source code:
mkdir -p hello-world
cd hello-world


# Create a plugin from the Jenkins templates:
mvn -U archetype:generate -Dfilter="io.jenkins.archetypes:"

| Part                  | Meaning                |
| --------------------- | ---------------------- |
| mvn                   | Maven tool             |
| -U                    | Force update           |
| archetype:generate    | Create project         |
| -Dfilter              | Filter templates       |
| io.jenkins.archetypes | Jenkins templates only |

Breakdown
mvn
Runs Apache Maven (a tool for building Java projects)
-U
Forces Maven to download the latest updates (no old cached data)
archetype:generate
Used to create a new project from a template
-Dfilter="io.jenkins.archetypes:"
Filters the templates and shows only Jenkins-related templates
🔸 What happens when you run it?
Maven fetches the latest templates
It shows only Jenkins project templates
You choose one (like a Jenkins plugin template)
Maven generates a ready-to-use project for you
-----------------------------------
Quick meaning of others (so you know)
1 → empty-plugin
👉 Blank project (no example)
❌ Not good for beginners
2 → global-configuration-plugin
👉 For plugins with settings in Jenkins UI
3 → global-shared-library
👉 For Jenkins Pipeline shared libraries
3 → hello-world-plugin ✅ (Best for beginners)
5 → scripted-pipeline
👉 For testing pipeline scripts
6 → theme-plugin
👉 For changing Jenkins UI theme

mvn verify
mvn package

if fail then install following:
sudo apt install openjdk-17-jdk -y
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
mvn clean install

Move .hpi file from targets to Jenkins Plugin Directory
Retstart the Jenkins Service

LogIn Jenkins and follow below steps -

- New freestyle job
- Add "Hello World" build step
- Run, check console
