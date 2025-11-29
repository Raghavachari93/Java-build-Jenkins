Project 12 – Jenkins Freestyle Job for Java Build

This project demonstrates how to configure Jenkins to build a Java Maven application from GitHub using a Freestyle Job.

🚀 Prerequisites

Install the following:

Java JDK

Maven

Git

Jenkins

GitHub account

📌 1. Install Java
sudo apt update
sudo apt install openjdk-17-jdk -y


Check version:

java -version

📌 2. Install Maven
sudo apt install maven -y


Check version:

mvn -version

📌 3. Install Git
sudo apt install git -y
git --version

📌 4. Install Jenkins

Add Jenkins repo:

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null


Install:

sudo apt update
sudo apt install jenkins -y


Start Jenkins:

sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins


Get the initial admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword


Open Jenkins in the browser:

http://localhost:8080

📌 5. Clone Your Java Project
git clone https://github.com/Raghavachari93/-Java-build-Jenkins.git
cd -Java-build-Jenkins

📌 6. Build the Project Manually
mvn clean package test


Check JAR file:

ls target

📌 7. Configure Jenkins Freestyle Job
Source Code Management → Git
Repository URL: https://github.com/Raghavachari93/-Java-build-Jenkins.git
Branch: */main

Build Step → Maven Goals
clean package test

Post-build Action → Archive Artifacts
target/*.jar

✔ Build the Job

Click Build Now.

You should see:

Maven build success

Tests passed

Archived JAR file

🎉 Project Completed!

This project demonstrates the fundamentals of Jenkins continuous integration using a simple Java Maven app.



✅ 1. Install Java (JDK)
Ubuntu / Linux
sudo apt update
sudo apt install openjdk-17-jdk -y

Check version
java -version

✅ 2. Install Maven
Ubuntu / Linux
sudo apt install maven -y

Check version
mvn -version

✅ 3. Install Jenkins
Add Jenkins repo + key:
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

Install:
sudo apt update
sudo apt install jenkins -y

✅ 4. Start Jenkins Service
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

✅ 5. Get Jenkins Admin Password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword


Use this to unlock Jenkins in the browser:

👉 http://YOUR-SERVER-IP:8080

or
👉 http://localhost:8080

✅ 6. Install Git
sudo apt install git -y

Check Git:
git --version
