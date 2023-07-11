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

An **agent node** is a worker node that executes all the steps mentioned in a job. When you create a job, you have to assign an agent to it. Every agent has a label as a unique identifier. When you trigger a job from the master, the actual execution happens on the agent node that is configured in the job1.

A **master node** is the central controlling machine that manages and monitors all the agent nodes. It is responsible for scheduling jobs, assigning agents to jobs, and monitoring agents

A **webhook** is a user-defined HTTP callback that allows lightweight, event-driven communication between two APIs. They are usually triggered by some event, such as pushing code to a repository or a comment being posted to a blog1. Webhooks are used by a wide variety of web apps to receive small amounts of data from other apps, but webhooks can also be used to trigger automation workflows in GitOps environments

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

If the code doesn't execute, the developer can correct it before deployment.

If the code does execute but there are bugs in testing, it can be sent back to the developer to correct. 

If the code executes and it passes testing, it is ready to be deployed.

![My Jenkins diagram](https://i.imgur.com/pO7TtlX.png)

1. Go to Jenkins home and select *New Item*
2. Give a name, select *Freestyle project* and click ok
3. Scroll to *Build* and select *Execute shell*. Enter test code, for example `uname -a`
![Build shell](https://i.imgur.com/jsT1U8H.png)
![Imgur](https://i.imgur.com/bmRt9Yv.png)
4. Select *Build Now* and wait for the build to start
5. Select *Console output* to see if the code was successful

## CI with the Sparta app
1. Create a new freestyle project
![Imgur](https://i.imgur.com/PXWYGGy.png)
2. Link to the GitHub repo by adding the HTTPS link
3. Go to *Source code management* and add the SSH link to the repo
4. The below error appears. Fear not!
![Error](https://i.imgur.com/0n29bwO.png)
5. In *Credentials* select `jenkins` and *Add*
![Imgur](https://i.imgur.com/wvaPOWi.png)
6. Enter the below info and add private key
![Enter key](https://i.imgur.com/D3ETNkx.png)
7. Change branch to `main`
![Main branch](https://i.imgur.com/fcsWZiB.png)
8. Office 365 connector settings
[Imgur](https://i.imgur.com/siXtSbx.png)
9.  Select the below in IBuild environments
![Imgur](https://i.imgur.com/TUcqXRO.png)
10.  Enter below commands in execute shell
![Imgur](https://i.imgur.com/sgVPti5.png)