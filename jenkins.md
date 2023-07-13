# Jenkins

## CI Steps

## CI Merge

## CD Steps

# Building a Jenkins Server on AWS
1. Create EC2 instance with Ubuntu 18.04LTS
2. Ensure rule is set up for TCP from port 8080
![Imgur](https://i.imgur.com/NsHm8mL.png)
3. SSH into EC2 and update
```
sudo apt update
```
4. Install required dependencies - Java 8 or above.
Go to <https://pkg.jenkins.io/debian-stable/> to get the install packages.
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
```

5. Install Jenkins


```sudo apt-get update
  sudo apt-get install fontconfig openjdk-11-jre
  sudo apt-get install jenkins
```
6. Check to see if Java exists and if Jenkins is running
```
java -version

sudo systemctl status jenkins
```
7. Start and enable Jenkins
```
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
