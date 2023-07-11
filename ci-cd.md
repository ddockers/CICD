# CI/CD - Continupus Integration and Continuous Delivery

## What is CI/CD?
**Continuous Integration** is the process of frequently building and testing new code changes.

**Continuous Delivery** is the process of deploying new versions of an application frequently.

## Software development lifecycle
- Plan
- Design
- Develop
- Test
- Deploy

## Why Jenkins?
Jenkins facilitates CI/CD by automating the above processes for software development.

Jenkins has plugins that help it to integrate with software like GitHub and AWS.

It is a self-contained Java program and can run on all main operating systems.

![Jenkins pipeline diagram](https://i.imgur.com/LayMK6i.png)


## Other tools that can be used for CICD
There are many tools available for CI/CD other than Jenkins. Some of the popular ones include:

- **Travis CI**: A hosted continuous integration service used to build and test software projects hosted at GitHub and Bitbucket.
- **CircleCI**: A cloud-based CI/CD platform that automates build, test, and deployment processes.
- **GitLab CI/CD**: A tool built into GitLab for software development through the continuous methodologies: Continuous Integration (CI) and Continuous Deployment (CD).
- **Bamboo**: A continuous integration server from Atlassian.

## Why build a pipeline?
A pipeline can help to:

- Automate the build process
- Automate the testing process
- Automate the deployment process
- Ensure that each step in the process is completed successfully before moving on to the next step
- Provide visibility into the status of each step in the process

## Business value?
- **Faster time to market**. CI/CD helps to speed up the software development process, which means that new features and updates can be delivered to customers more quickly.
- **Higher quality software**. By automating the build, test, and deployment processes, CI/CD helps to ensure that software is of high quality and free from bugs.
- **Reduced costs**. By automating the software development process, CI/CD helps to reduce the costs associated with manual testing and deployment.
- **Improved collaboration**. CI/CD encourages collaboration between developers, testers, and operations teams, which can help to improve communication and reduce errors.


# Jenkins
In Jenkins we can build, test and deploy software in a testing environment.

![My Jenkins diagram](https://i.imgur.com/pO7TtlX.png)

1. Go to Jenkins home and select *New Item*
2. Give a name, select *Freestyle project* and click ok
3. Scroll to *Build* and select *Execute shell*. Enter test code, for example `uname -a`
![Build shell](https://i.imgur.com/jsT1U8H.png)
![Imgur](https://i.imgur.com/bmRt9Yv.png)
4. Select *Build Now* and wait for the build to start
5. Select *Console output* to see if the code was successful