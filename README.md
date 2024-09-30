# Deploying-A-Java-Based-Project-On-Tomcat

# PREREQUISITES

Servers
- jenkins Server (Freestyle Project)- Maven, Publish Over SSH
- Tomcat Server- Java, Tomcat

# Step 1: Installing Jenkins On AWS EC2 Instance

- Launch an EC2 instance
- For the Security Group, add Port 8080
- Use SSH to connect to the instance on your Gitbash
- Install Jenkins using the jenkins doc from jenkins.io
- Log in to Jenkins through your web browser

# Step 2: Installing Tomcat On AWS EC2 Instance

- Launch an EC2 Instance using the same keypair and security group of the jenkins server
- Use SSH to connect to the instance on your Gitbash
- Install Java with the following command below

sudo yum install java-17-amazon-corretto-devel

- Install Tomcat using the code below

wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.95/bin/apache-tomcat-9.0.95.tar.gz

tar -xvzf apache-tomcat-9.0.95.tar.gz

cd apache-tomcat-9.0.95

cd bin

./startup.sh

- test that the tomcat server is running on your browser by using your public Ip Address

# Step 3: Configuring Jenkins

- go to jenkins-manage jenkins-plugins-available plugins, then search for Publish over ssh and install it
- go to manage jenkins-tools-maven installation-for the name give it Maven and save
- go back to the homepage and click on new item, give it a name and select freestyle project
- go to the project created, go to General, for description give it a name, click the checkbox for Discard old builds, put 30 for days to keep builds then put 2 for Max of builds to keep
- for source code management select Git then under repositories put the link copied from Github,
- for Build Environment click the checkbox for Delete workspace before build starts
- for Build Steps select invoke top-level Maven Targets then for Maven Version select Maven
- then for Goals select compile, Add another Build Steps, select invoke top-level Maven Targets then select Maven under the Maven Version then for Goals put package then click save
- Then click on Build Now
