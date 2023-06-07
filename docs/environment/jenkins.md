---
layout: default
title: Install Jenkins
parent: Environment
nav_order: 5
---

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<p align="center"><img alt="jenkins_logo" src="/assets/images/jenkins/jenkins_logo.png" width="140"/></p>

# Introduction to Jenkins

Jenkins is an open-source continuous integration/continuous delivery and deployment (CI/CD) automation software DevOps tool written in the Java programming language. It supports the complete development life cycle of software from building, testing, documenting the software, deploying, and other stages of the development life cycle.

# Jenkins Installation

<span style="color:red">**Note:**</span> <span style="color:blue">Please have Python version as 3.8 above, you can check your Python version by running “python” command in PowerShell or Terminal. If upgrade is needed please follow the Python installation guide in this link:</span> https://cityuseattle.github.io/docs/environment/python/

    a. Install java and Git on your laptop if you don’t have it already installed.
    b. Jenkins released two types of versions. Long-term support (LTS) a which is a stable one and Regular release (Weekly). We will install the Stable one (LTS)
    c. Check the [Hardware and Software requirement](https://www.jenkins.io/doc/book/installing/linux/#prerequisites) for your Operating System before jenkins installation

# 2.1 Using Docker

Docker is an open-source containerization platform used for developing, shipping, and running applications in lightweight virtualized environments called containers. It is used as a software development platform for developing distributed applications to separate from the infrastructure and to deliver the software quickly. 
Follow the requirement and detail installation [here](https://docs.docker.com/engine/install/).

a)	Install and run Docker Desktop on Mac

Note:- Jump to section V if we have already installed Docker on HOS02, otherwise follow all steps
    I.	Download Docker from [here](https://docs.docker.com/desktop/install/mac-install/) based on your Mac chip and follow the steps.
    ![docker_1](/assets/images/jenkins/docker_1.png)
    II.	Double-click <span style="color:blue">Docker.dmg</span> to open the installer and drag the Icon to the Application folder
    ![docker_2](/assets/images/jenkins/docker_2.png)
    III.	Double-click the <span style="color:blue">Docker.app</span> in the Applications folder to start Docker
    ![docker_3](/assets/images/jenkins/docker_3.png)
    IV.	Docker open and you can continue installation
    ![docker_4](/assets/images/jenkins/docker_4.png)
b)	Install and run Docker on Window

<span style="color:red">**Note**</span>:- <span style="color:blue">Jump to section V if we have already installed Docker on HOS02, otherwise follow all steps.</span>

    V.	Download Docker from [here](https://docs.docker.com/desktop/install/windows-install/) for your Window
    ![docker_5](/assets/images/jenkins/docker_5.png)
    VI.	Double-click Docker Desktop Installer.exe to run the installer.
    ![docker_6](/assets/images/jenkins/docker_6.png)
(Optional) If Windows Docker desktop takes long time after default installation/restart:
 Start button > type "powershell" > click "Windows PowerShell"
type following:

    wsl --update
    wsl --list --online
    wsl --install -d Ubuntu-20.04
    Close everything and restart Docker desktop again


# 3. Jenkins integration with GitHub

<span style="color:red">**Note:-**</span> <span style="color:blue">We need Docker Hub, and GitHub account. Please create docker Hub account just like GitHub.</span>

Jenkin is a free, open-source, and a powerful application that enables continuous integration and continuous delivery of projects on any platform. It can be integrated with a variety of testing and deployment technologies, and remote repository like GitHub.

    a.	First let’s create a GitHub repository in your GitHub account. Click on “New  repository”    and create new repository called “jenkinsPractice”. 

<span style="color:red">**Note:-**</span> <span style="color:blue">You can create a new flask app OR you can copy the created app from HOS02 into this jenkinsPractice repository</span>.
    ![docker_7](/assets/images/jenkins/docker_7.png)
    b.	Jenkins provides an official docker image. However, to create a pipeline with the ‘docker build’ command, the image needs to include docker as shown below. Based on Jenkins official image, we will create a new image with docker installed.
    ![docker_8](/assets/images/jenkins/docker_8.png)
    During the process, we will use docker-compose command, which triggers the ‘docker build’ command and starts the newly built image. Open terminal/ cmd or any editor in HOS03 folder (your working directory), and create a Dockerfile. Type the following to create a Jenkins Docker Image (<span style="color:red">**Note:**</span> <span style="color:blue">Dockerfile is provided, you can copy and paste it here or you can create your own</span>)
    ![docker_9](/assets/images/jenkins/docker_9.png)
    c.	Next, create a docker-compose.yml file in HOS03 folder to make easy the process of Docker image creation. Type the following code inside yml file.(<span style="color:red">**Note:**</span> <span style="color:blue">docker-compse.yml is provided, you can copy and paste it here or you can create your own</span>)
    ![docker_10](/assets/images/jenkins/docker_10.png)
    Now, the Docker volume called myjenkins is created to /var/Jenkins_home directory inside the Docker container. In addition, looking at volumes content, we can see that Jenkins server data (Jenkins-data) is stored in the current working folder(HOS03/Jenkins/jenkins-data). If it needs to be at a certain path, you can change it to some other directory within your machine.

    d.	Type the following code to run the Created Docker image in your directory
    ![docker_11](/assets/images/jenkins/docker_11.png)
Go to the bottom of the running Docker image to get the password. We can get the admin password from <span style="color:blue">/var/Jenkins_home/initialAdminPassword</span>
    ![docker_12](/assets/images/jenkins/docker_12.png)
    e.	Next, run http://localhost:8080 into your browser to set up Jenkins after the above Jenkins file is executed.
    ![docker_13](/assets/images/jenkins/docker_13.png)
    f.	Next, Install the suggested Jenkins Plugins using the following steps
    ![docker_14](/assets/images/jenkins/docker_14.png)
    g.	Next, wait for the completion all the installation. It will take some time depending on the number of plugins.¬¬
    ![docker_15](/assets/images/jenkins/docker_15.png)
    ![docker_16](/assets/images/jenkins/docker_16.png)
    h.	Next create admin user and password if you want to, otherwise you can skip it
    ![docker_17](/assets/images/jenkins/docker_17.png)
    ![docker_18](/assets/images/jenkins/docker_18.png)
    i.	The next step is creating new Jenkins Pipeline. Click on the New Item and follow the stapes
    ![docker_19](/assets/images/jenkins/docker_19.png)
    j.	Type “Jenkins_Project” on the Enter an Item name, and the select Pipeline from the list
    ![docker_20](/assets/images/jenkins/docker_20.png)
    k.	Select Poll SCM from the list under Build Triggers, and set a schedule as * * * * * which will poll the SCM repository every minutes. Note that webhook can be configured in GitHub if the Jenkins server domain is exposed and accessible by the public.
    ![docker_21](/assets/images/jenkins/docker_21.png)
    l.	Next, select <span style="color:blue">***“Pipeline script from SCM”***</span> option in the Pipeline section. Select <span style="color:blue">***Git***, insert <span style="color:blue">***URL***</span> of the SCM repository. It is optional to add credentials.
    <span style="color:blue">**Note**</span>: You need to add your own repository. You may need to get authentication if you add GitHub repository of third party like City University GitHub repository. 
    Click save button to save it.
    ![docker_22](/assets/images/jenkins/docker_22.png)
    m.	Click “+ Add”/”Jenkins” button. Complete creating credentials using Username and Password for docker hub(https://hub.docker.com/). Note that the ID is used Jenkinsfile in step “O” line number 4.
    ![docker_23](/assets/images/jenkins/docker_23.png)
    ![docker_24](/assets/images/jenkins/docker_24.png)
In addition, GitHub credential is needed for Jenkins to communicate with GitHub without warning.
    •	Click “ + Add” / ”Jenkins” button again to add SSH credential 
    •	Select Kind: "SSH Username with private key", ID: something unique, Username: your git account user name, Private Key: click "Enter directly" and paste the private key
    •	Note that you should already have GitHub key pairs since you have been using GitHub. For example, from terminal you can execute, “cat /Users/{User dir}/.ssh/id_rsa” to get the private key contents.
    •	The ID will be used for step “O” Jenkinsfile line number 11.
    •	click "Add" to close popup
    ![docker_25](/assets/images/jenkins/docker_25.png)
    ![docker_26](/assets/images/jenkins/docker_26.png)
    n.	Next, go to <span style="color:blue">*Manage Jenkins -> Plugin Manager*</span> to install <span style="color:blue">“CloudBees Docker Build and Publish”</span> and <span style="color:blue">“Docker Pipeline”</span> to build and push the Docker image to Docker Hub. You can type in search space if you can’t see it in the list. Note that there are several plugins that have CloudBees as prefix. Make sure you select one with “Build and Publish”.
    ![docker_27](/assets/images/jenkins/docker_27.png)
    o.	Created “<span style="color:blue">Jenkinfile</span>” and type the following code to add a Jenkinsfile script once the above plugin has been installed.
    ![docker_28](/assets/images/jenkins/docker_28.png)
    p.	 The last step is testing whether it works or not. Commit changes to the GitHub (jenkinspractice app) to test and see if Jenkins can access the GitHub repository and Jenkinsfile. If it is successful in the completion of the job, we can see the Docker image in your Docker Hub repository and in Jenkins as follow.
    ![docker_29](/assets/images/jenkins/docker_29.png)
    ![docker_30](/assets/images/jenkins/docker_30.png)
    * <span style="color:red">**Note**</span>: This is not mandatory but if you desire to clean up, you need to do the followings:
        * Stop the docker-compose shell by giving the interrupt command (ctrl+c) and execute the below commands:
            * docker stop jenkins-container
            * docker rm jenkins-container
            * docker images #this will list images with tags/versions
            * docker rmi {jenkins image name}:{version of the image}
        * Jenkins server data (Jenkins-data) is stored in the current working folder(HOS03/Jenkins/jenkins-data). Delete the folder.
