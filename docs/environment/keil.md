---
layout: default
title: Install Keil IDE
parent: Environment
nav_order: 4
---

# Install Keil µVision 5 ARMs assembly IDE
{: .no_toc }

<p align="center"><img alt="keil_logo" src="//assets/images/install_keil/keil_logo.png"/></p>

## Before You Start
{: .no_toc }

* Version numbers may not match with the most current version at the time of writing. If given the option to choose between stable release (long-term support) or most recent, please select the stable release rather than the beta-testing version.
* This tutorial targets Windows users and macOS users.
* There might be subtle discrepancies along with the steps. Please use your best judgment while going through this cookbook-style tutorial to complete each step.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# For macOS Users

Unfortunately, Keil® MDK is not available for Mac devices at the time of creating this document. For this reason, we have deployed an AWS server that hosts this software. To access this server, download the `Microsoft Remote Desktop` from the App Store. Request the IP address, and your username and password from the instructor and TA for the entire quarter.

# For Windows Users

Keil® MDK is the most comprehensive software development solution for Arm®-based microcontrollers and includes all components that you need to create, build, and debug embedded applications. Additional information can be found in the official website [here](https://www2.keil.com/mdk5/uvision/). This software is provided by ARM. To download the Development Kit, browse [here](https://www2.keil.com/mdk5/) and click on the `Download MDK`. You will be required to fill in the form and follow the instructions to install the latest version of Keil µVision as shown below:

![keil_download_page](/assets/images/install_keil/keil_download_page.png)

> Keil will collect user data during the download and installation process, please fill in as you like.

![keil_install_process_path](/assets/images/install_keil/keil_install_process_path.png)

> In the `Do you want to install this device software?` dialog box that pops up during the installation process, please check the `Always trust software from "ARM Ltd" (A).` option, and click `Install`.

When you finish the installation, Keil's Pack Installer will pop up automatically. Please wait for all loading/upgrades at the bottom of the page to complete. When there is no progress bar or Ready is displayed, you can close the window.

![keil_pack_installer_updating](/assets/images/install_keil/keil_pack_installer_updating.png)

![keil_pack_installer_ready](/assets/images/install_keil/keil_pack_installer_ready.png)

If you have successfully installed Keil, running Keil will have the following display.

![keil_start_page](/assets/images/install_keil/keil_start_page.png)

![keil_default_editor](/assets/images/install_keil/keil_default_editor.png)

# Install the Pack You Need

The following steps will demonstrate how to install the packages you need through Keil's own package installer. This section will take the installation of the `STM32F4` device as an example.

 1. First, you need to find and open the package installer that comes with Keil. There are two ways:

     1. Open Keil and find and click the `Pack Installer` button in the main interface.

        ![keil_pack_installer_btn](/assets/images/install_keil/keil_pack_installer_btn.png)

     2. Find Keil_v5 installation path. Usually in the path `C:/Keil_v5/UV4/`.

        ![keil_v5_path](/assets/images/install_keil/keil_v5_path.png)

        Open `PackInstaller.exe`.

        ![open_pack_installer](/assets/images/install_keil/open_pack_installer.png)

 2. Waiting.

    ![keil_pack_installer_loading](/assets/images/install_keil/keil_pack_installer_loading.png)

 3. Search the pack you need. Here use `STM32F411` as an example.

    ![search](/assets/images/install_keil/search.png)

 4. Click `STM32F4 Series`, then install `Keil::STM32F4xx_DFP`.

    ![install_pack](/assets/images/install_keil/install_pack.png)

# Resource

* Keil Downloads: <https://www.keil.com/download/product/>
