---
layout: default
title: Install ubuntu
parent: Tools
---

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Ubuntu is a complete Linux operating system, freely available with both community and professional support. This document will show you how to install Ubuntu on your machine MacOS and Windows. 


# Install Ubuntu on MacOS (For Apple Silicon Valley)


If you're using Apple Silicon Valley([Check if you're using Apple Silicon Valley]({{ site.baseurl }}{% link docs/common/applem1.md %})
), you need to install another tools like `multipass` to get Ubuntu on it. 


### Download Multipass

Go to the [Multipass download page](https://multipass.run) and download the latest version of Mutipass. When the page is written, the current released version is 1.8.1.

![](/assets/images/ubuntu/applem1_1.png)

### Install Multipass

![](/assets/images/ubuntu/applem1_2.png)

### Start and Launch a Ubuntu Instance

After you install multipass, you will get multipass command in your machine. Execute `multipass launch` command to start and launch a new Ubuntu instance.

![](/assets/images/ubuntu/applem1_3.png)

### Enter your Ubuntu instance

After launching a new Ubuntu instance, you can execute `multipass shell {Your Instance Name}` to enter Ubuntu.


![](/assets/images/ubuntu/applem1_4.png)


### More Multipass Commands

[Multipass Home Page](https://multipass.run)

---

# Install Ubuntu on Windows 10

## 1. Install Ubuntu LTS from Microsoft Store

Open the Microsoft Store and search Ubuntu on the search bar. Some Ubuntu apps will come up. Click the latest version of Ubuntu. Till now, the latest version is Ubuntu 20.04 LTS.

![Ubuntu_windows10](/assets/images/ubuntu/windows10_1.png)

Click the “Get” button to install it. It would take a few minutes depending on your Internet speed.

![Ubuntu_windows10](/assets/images/ubuntu/windows10_2.png)


## 2. Initial your Ubuntu

After installing Ubuntu on your Windows10, open it. It will do some initial work for the first time.

![Ubuntu_windows10](/assets/images/ubuntu/windows10_3.png)


After a few minutes, enter your Ubuntu OS username and password as you wish. For example, mark or mike.

![Ubuntu_windows10](/assets/images/ubuntu/windows10_4.png)

If you can see a similar window like this, you have install Ubuntu OS successfully.

![Ubuntu_windows10](/assets/images/ubuntu/windows10_5.png)


---


# Install Ubuntu on MacOS and Windows (Not for Apple Silicon Valley and Windows10)

If you're using Windows10, please see [Install Ubuntu on Widnows 10]({{ site.baseurl }}{% link docs/tools/ubuntu.md %})

## What you will need

1. VirtualBox (If you don't have VirtualBox installed, please follow this [link]({{ site.baseurl }}{% link docs/tools/virtualbox.md %}) to install it.)

2. Internet Connection

3. Ubuntu ISO file

## Get started

### Download Ubuntu ISO

Go the [Download Ubuntu Desktop](https://ubuntu.com/download/desktop) and choose to download the latest version of Ubuntu OS image.

![Ubuntu_download](/assets/images/ubuntu/ubuntu_download_1.png)

The file would be more than 3 GB which will take for a while. You can download it to `~/Downloads` folder or anywhere you know. We will use it later.


### Open your VirtualBox in your machine.

![virtualbox_installing](/assets/images/virtualbox/virtualbox_homepage.png)


### Click the "New" button, choose to install Ubuntu

- Input your Ubuntu OS name

- Choose the Linux Type

- Choose the Ubuntu_64 version 

![Ubuntu_new_1](/assets/images/ubuntu/ubuntu_new_1.png)

Then, click "Continue".


### Choose Memory Size

The memory size will influence the performance of your Ubuntu. You can just use the recommended memory size. Don't need to change it. 

![Ubuntu_new_2](/assets/images/ubuntu/ubuntu_new_2.png)

Then click "Continue".

### Create Hard Disk

The hard disk is used for storing data inside your Ubuntu OS. Choose the "Create a virtual hard disk now" and click "Create".

![Ubuntu_new_3](/assets/images/ubuntu/ubuntu_new_3.png)

### Choose Hard Disk File Type

You don't need to change it. Just use defualt option "VDI (VirtualBox Disk Image)" and click "Continue".

![Ubuntu_new_4](/assets/images/ubuntu/ubuntu_new_4.png)


### Choose Storage on Physical Hard Disk

Just use "Dynamically allocated" that will save the storage on your machine. Then click "Continue".

![Ubuntu_new_5](/assets/images/ubuntu/ubuntu_new_5.png)


### Choose File Location and Size

We will store all the data produced from Ubuntu data to the `~/VirtualBox VMs/` directory. Just use the default path. Then click "Create".

![Ubuntu_new_6](/assets/images/ubuntu/ubuntu_new_6.png)


### Attach ISO file

If everything works, you would see you Ubuntu OS has been installed. However, we still cannot boot Ubuntu OS. We need to attach the IOS file that we downloaded before.

![Ubuntu_new_7](/assets/images/ubuntu/ubuntu_new_7.png)

Click that "Settings" button. Select `Storage->Contorller: IDE -> Empty` and click that blue button. Then click "choose a disk file".

![Ubuntu_new_8](/assets/images/ubuntu/ubuntu_new_8.png)


After attching ISO file to your Ubuntu, Click "OK" button. Then go back to VitualBox dashboard and click "Start".

![Ubuntu_new_9](/assets/images/ubuntu/ubuntu_new_9.png)


If no other problems, you have successfully installed Ubuntu on your machine.