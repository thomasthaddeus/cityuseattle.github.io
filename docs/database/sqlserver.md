---
layout: default
title: Install ms sqlserver
parent: Database
nav_order: 3
---

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<p align="center">
<img src="/assets/images/sqlserver/sql_server_logo.png" />
</p>

## Before You Start

* Version numbers may not match with the most current version at the time of writing. If given the option to choose between stable release (long-term support) or most recent, please choose the stable release rather than beta-testing version.
* This tutorial targets Windows users and MacOS users.
* There might be subtle discrepancies along the steps. Please use your best judgement while going through this cookbook style tutorial to complete each step.
* For your working directory, use your course number. This tutorial may use a different course number as an example.  
* The directory path shown in screenshots may be different from yours.
* If you are not sure what to do or confused with any steps:
  1. Consult the resources listed below.  
  2. If you cannot solve the problem after a few tries, ask a TA for help.

## Learning Outcomes

Students will be able to:

* Create and connect to Microsoft SQL Server Database

## Resources

* YouTube Tutorial  - <https://youtu.be/DhAl4rdrzoA>
* Microsoft SQL Server Management Studio Download: <https://www.microsoft.com/en-us/download/details.aspx?id=14630>

---

* [Download a SQL Server](#Download-a-sql-server)
* [Download a SQL Client](#download-a-sql-client)
* [Connect to the Microsoft SQL Server Database](#connect-to-the-microsoft-sql-server-database)
* [Import a sample database to Microsoft SQL Server](#import-a-sample-database-to-microsoft-sql-server)
  * [AdventureWorks sample database backup copy](#adventureWorks-sample-database-backup-copy)
  * [Install to SQL Server](#install-to-sql-server)

---

# Download a SQL Server

 1. Go to the Microsoft Download Center - <https://www.microsoft.com/en-us/sql-server/sql-server-downloads> and download the latest developer version for your machine
    ![](/assets/images/sqlserver/sql_server_download_page.png)

 2. Once, the download is completed, run the downloaded exe and choose Basic for installation type.

    ![](/assets/images/sqlserver/sql_server_install_page.png)

 3. Continue with the installation and  once the installation is complete , click Close.

    ![](/assets/images/sqlserver/sql_server_install_successfully.png)

 4. To verify the SQL server instance, Click Windows +R and type services.msc and click Ok. You should be able to see SQL Server instance running. Make a note of the sql server instance that you just created.

    SQL server is that an instance is a copy of the sqlservr.exe executable that runs as an operating system service.

    ![](/assets/images/sqlserver/win_run.png)

    ![](/assets/images/sqlserver/win_services_msc.png)

# Download a SQL Client

 1. Go to the Microsoft Download Center - [Microsoft SQL Server Management Studio Express page](https://aka.ms/ssmsfullsetup) and download the latest version for your machine

    ![](/assets/images/sqlserver/ssms_install.png)

    ![](/assets/images/sqlserver/ssms_install_success.png)

# Connect to the Microsoft SQL Server Database

 1. Once you have completed your download, install, and open the program and enter the following in the dialog box:

    ![](/assets/images/sqlserver/connect_sql_server.png)

    * **Server type:** Select Database Engine
    * **Hostname:** Select server name as local
    * **Authentication:** Select Windows Authentication 

 2. Click connect and you will be connected to the database. The SQL server management studio should appear like this:

    ![](/assets/images/sqlserver/ssms_ui.png)

# Import a sample database to Microsoft SQL Server

## AdventureWorks sample database backup copy

To get the OLTP downloads of AdventureWorks, go to this [link](https://docs.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver15). You can choose any, in my example, I choose AdventureWorks2017.bak version. 

![](/assets/images/sqlserver/download_backup_files_page.png)

## Install to SQL Server

### Restore backup

Follow the below steps to restore a backup of your database using SQL Server Management Studio.

 1. Open SQL Server Management Studio and connect to the target SQL Server instance.

 2. Right-click on the Databases node, and select Restore Database.

    ![](/assets/images/sqlserver/ssms_restore_db_dropdown.png)

 3. Select Device and click the ellipses (...)

    ![](/assets/images/sqlserver/ssms_restore_db_page.png)

 4. In the dialog Select backup devices, click Add, navigate to the database backup in the filesystem of the server, and select the backup. Click OK.

    ![](/assets/images/sqlserver/ssms_select_backup_devices.png)

 5. If needed, change the target location for the data and log files, in the Files pane. Note that it is best practice to place data and log files on different drives.

    ![](/assets/images/sqlserver/ssms_locate_backup_file_selector.png)

    ![](/assets/images/sqlserver/ssms_select_backup_devices_after.png)

 6. Click OK. This will initiate the database restore. After it completes, you will have the AdventureWorks database installed on your SQL Server instance.

    ![](/assets/images/sqlserver/ssms_restore_db_page_2.png)

    ![](/assets/images/sqlserver/ssms_restore_db_success.png)

    ![](/assets/images/sqlserver/ssms_after_restore_db.png)
