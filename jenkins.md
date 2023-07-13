# Jenkins

## CI Steps

## CI Merge

## CD Steps

# Building a Jenkins Server on AWS
1. Create EC2 instance with Ubuntu 18.04LTS
2. Ensure rule is set up for TCP from port 8080
![Imgur](https://i.imgur.com/NsHm8mL.png)
3. Install required dependencies - Java 8 or above
```
sudo apt update

# install java
sudo apt install openjdk-17-jre
```
3. Install Jenkins
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update -y
sudo apt-get upgrade -y
```
4. Check to see if Java exists and if Jenkins is running
```
java -version

sudo systemctl status jenkins
```
