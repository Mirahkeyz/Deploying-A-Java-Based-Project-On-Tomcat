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

https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.95/bin/apache-tomcat-9.0.95.tar.gz
