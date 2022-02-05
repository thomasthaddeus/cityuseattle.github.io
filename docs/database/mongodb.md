---
layout: default
title: Install MongoDB
parent: Database
---

# Install MongoDB
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

 1. TOC
{:toc}

---

* Version numbers may not match with the most current version at the time of writing. If given the option to choose between stable release (long-term support) or most recent, please select the **stable release** rather than the beta-testing version.
* There might be subtle discrepancies along with the steps. Please **use your best judgment** while going through this cookbook-style tutorial to complete each step.

# For Windows Users

> This section is based on the [official MongoDB documentation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/).

This tutorial only applies to **64-bit versions** of Windows Server 2019 / Windows 10 / Windows Server 2016 on **x86_64 architecture**. For other Windows platforms, please do your personal research first, and if you really can't find a solution ask your TA to find a solution with you.

Disable Hyper-V if you want to install MongoDB on Windows using VirtualBox.

## Install MongoDB Community Edition

Follow these steps to install MongoDB Community Edition using the MongoDB Installer wizard.

 1. Download the MongoDB Community `.msi` installer from the [MongoDB Download Center](https://www.mongodb.com/try/download/community?tck=docs_server).

    > Please keep the `.msi` installer after installation, this file is also used for uninstallation.

     1. In the **Version** dropdown, select the **newest** version of MongoDB to download.  
        (As of Feb 4, 2022, the latest version is `5.0.6`.)
     2. In the **Platform** dropdown, select `Windows`.
     3. In the **Package** dropdown, select `msi`.
     4. Click **Download**.

    ![mongodb_download_center](/assets/images/database/mongodb/mongodb_download_center.png)

 2. Run the MongoDB installer.

    For example, from the Windows Explorer/File Explorer:

     1. Go to the directory where you downloaded the MongoDB installer (`.msi` file). By default, this is your `Downloads` directory.
     2. Double-click the `.msi` file.

    ![mongodb_installer](/assets/images/database/mongodb/mongodb_installer.png)

 3. Follow the MongoDB Community Edition installation wizard.

    The wizard steps you through the installation of MongoDB and MongoDB Compass.

     1. Choose Setup Type

        You can choose either the **Complete** or **Custom** setup type. **Please select *Complete***.

        > The **Complete** setup option installs MongoDB and the MongoDB tools to the default location.
        > The **Custom** setup option allows you to specify which executables are installed and where.

        ![installer_choose_setup_type](/assets/images/database/mongodb/installer_choose_setup_type.png)

     2. Service Configuration

        Starting in MongoDB 4.0, you can set up MongoDB as a Windows service during the install or just install the binaries. Here let's set it as a Windows service, and the MongoDB service will be started after successful installation.

         1. Select `Install MongoD as a Service`.
         2. Select `Run the service as Network Service user`.
         3. Other options are kept as default.
         4. Click `Next`.

        ![installer_service_configuration](/assets/images/database/mongodb/installer_service_configuration.png)

        > If you choose `Run the service as a local or domain user`, in order to use it in your current Windows local account, you need to keep the **Account Domain** as `.`; **Account Name** as your current account name; **Account Password** as your the password for the current account (yes, the username and password you use to log in to Windows). For a detailed explanation of these options, please read [here](https://stackoverflow.com/questions/52068925/what-does-it-mean-to-install-mongodb-as-a-service) and the [official documentation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/#follow-the-mongodb-edition-installation-wizard).

     3. (Optional but recommended) To have the wizard install [MongoDB Compass](https://www.mongodb.com/products/compass), select `Install MongoDB Compass` (Default). MongoDB Compass is a graphical user interface (GUI) for MongoDB.

        ![install_mongodb_compass](/assets/images/database/mongodb/install_mongodb_compass.png)

     4. When ready, click `Install`.

        ![install_confirm](/assets/images/database/mongodb/install_confirm.png)

## Install Tools

### Install `mongosh`

The `.msi` installer does not include [mongosh][]. Follow the [mongosh installation instructions](https://docs.mongodb.com/mongodb-shell/install/) to download and install the shell separately.

### Install MongoDB Database Tools

> This section is based on the [official MongoDB documentation][mongodb-database-tools-doc].

The MongoDB Database Tools are a collection of command-line utilities for working with a MongoDB deployment. The Database Tools include binaries `mongodump`, `mongorestore`, `bsondump`, `mongoimport`, `mongoexport`, `mongostat`, `mongotop`, and `mongofiles`.

If you are missing these tools, please refer to [here](https://docs.mongodb.com/database-tools/installation/installation-windows/) to install them. It is recommended to use the **Zip Archive** method to install, put the files in the `bin` folder in the compressed package into the MongoDB installation path, which is located in `C:\Program Files\MongoDB\Server\5.0\bin\` by default.

![install_db_tools_zip_archive](/assets/images/database/mongodb/install_db_tools_zip_archive.png)

![db_tools_unzip](/assets/images/database/mongodb/db_tools_unzip.png)

# For macOS Users

> This section is based on the [official MongoDB documentation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/).

Use this tutorial to install MongoDB 5.0 Community Edition on macOS using the third-party Homebrew package manager. MongoDB 5.0 Community Edition supports macOS 10.14 or later.

> If you are using an older version of macOS, please install an older version of MongoDB Community. Please do your own research on how to install it, or use the version drop-down menu in the upper left corner of the [current MongoDB document](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) to select the documentation for that version.

## Install MongoDB Community Edition

 1. macOS does not include the Homebrew brew package by default. First you need to install Homebrew, follow the steps of [this tutorial]({{ site.baseurl }}{% link docs/tools/homebrew.md %}) to install Homebrew.

    Type the following in the terminal to update Homebrew.

    ```shell
    $ brew update
    ```

 2. Tap the [MongoDB Homebrew Tap](https://github.com/mongodb/homebrew-brew) to download the official Homebrew formula for MongoDB and the Database Tools, by running the following command in your macOS Terminal:

    ```shell
    $ brew tap mongodb/brew
    ```

    If you have already done this for a previous installation of MongoDB, you can skip this step.

 3. To install MongoDB, run the following command in your macOS Terminal application:

    ```shell
    $ brew install mongodb-community@5.0
    ```

    > Alternatively, you can specify a previous version of MongoDB if desired. You can also maintain multiple versions of MongoDB side by side in this manner.
    >
    > If you have previously installed an older version of the formula, you may encounter a ChecksumMismatchError. To resolve, see [Troubleshooting ChecksumMismatchError](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/#std-label-troubleshooting-checksumerror).

## Run MongoDB Community Edition

Follow these steps to run MongoDB Community Edition. These instructions assume that you are using the default settings.

You can run MongoDB as a macOS service using brew, or you can run MongoDB manually as a background process. It is recommended to run MongoDB as a macOS service, as doing so sets the correct system ulimit values automatically (see [ulimit settings](https://docs.mongodb.com/manual/reference/ulimit/#std-label-ulimit-settings) for more information).

* To run MongoDB (i.e. the [`mongod`][mongod] process) **as a macOS service**, run:

  ```shell
  $ brew services start mongodb-community@5.0
  ```

  To stop a [`mongod`][mongod] running as a macOS service, use the following command as needed:

  ```shell
  $ brew services stop mongodb-community@5.0
  ```

* To run MongoDB (i.e. the [`mongod`][mongod] process) **manually as a background process**, run:

  * For macOS running Intel processors:

    ```shell
    $ mongod --config /usr/local/etc/mongod.conf --fork
    ```

  * For macOS running on [Apple M1 processors](https://support.apple.com/en-us/HT211814):

    ```shell
    $ mongod --config /opt/homebrew/etc/mongod.conf --fork
    ```

    To stop a [`mongod`][mongod] running as a background process, connect to the [`mongod`][mongod] using [mongosh][], and issue the [`shutdown`](https://docs.mongodb.com/manual/reference/command/shutdown/) command as needed.

Both methods use the mongod.conf file created during the install. You can add your own MongoDB [configuration options](https://docs.mongodb.com/manual/reference/configuration-options/) to this file as well.

> **macOS Prevents mongod From Opening**
>
> macOS may prevent [`mongod`][mongod] from running after installation. If you receive a security error when starting [`mongod`][mongod] indicating that the developer could not be identified or verified, do the following to grant [`mongod`][mongod] access to run:
>
> * Open System Preferences
> * Select the Security and Privacy pane.
> * Under the General tab, click the button to the right of the message about [`mongod`][mongod], labelled either **Open Anyway** or **Allow Anyway** depending on your version of macOS.

To verify that MongoDB is running, perform one of the following:

* If you started MongoDB **as a macOS service**:

  ```shell
  $ brew services list
  ```

  You should see the service `mongodb-community` listed as `started`.

* If you started MongoDB **manually as a background process**:

  ```shell
  $ ps aux | grep -v grep | grep mongod
  ```

  You should see your `mongod` process in the output.

You can also view the log file to see the current status of your `mongod` process: `/usr/local/var/log/mongodb/mongo.log`.

### Connect and Use MongoDB

To begin using MongoDB, connect mongosh to the running instance. From a new terminal, issue the following:

```shell
$ mongosh
```

> **macOS Prevents mongosh From Opening**
>
> macOS may prevent [`mongosh`][mongosh] from running after installation. If you receive a security error when starting [`mongosh`][mongosh] indicating that the developer could not be identified or verified, do the following to grant [`mongosh`][mongosh] access to run:
>
> * Open System Preferences
> * Select the Security and Privacy pane.
> * Under the General tab, click the button to the right of the message about [`mongosh`][mongosh], labelled either **Open Anyway** or **Allow Anyway** depending on your version of macOS.

For information on CRUD (Create, Read, Update, Delete) operations, see:

* [Insert Documents](https://docs.mongodb.com/manual/tutorial/insert-documents/)
* [Query Documents](https://docs.mongodb.com/manual/tutorial/query-documents/)
* [Update Documents](https://docs.mongodb.com/manual/tutorial/update-documents/)
* [Delete Documents](https://docs.mongodb.com/manual/tutorial/remove-documents/)

## Using the MongoDB Database Tools

Starting in MongoDB 4.4.1, installing MongoDB via `brew` also installs the MongoDB Database Tools.

The [MongoDB Database Tools][mongodb-database-tools-doc] are a collection of command-line utilities for working with a MongoDB deployment, including data backup and import/export tools like [`mongoimport`](https://docs.mongodb.com/database-tools/mongoimport) and [mongodump](https://docs.mongodb.com/database-tools/mongodump) as well as monitoring tools like [`mongotop`][mongotop].

Once you have installed the MongoDB Server in the steps above, the Database Tools are available directly from the command line in your macOS Terminal application. For example you could run [`mongotop`][mongotop] against your running MongoDB instance by invoking it in your macOS Terminal like so:

```shell
$ mongotop
```

It should start up, connect to your running [`mongod`][mongod], and start reporting usage statistics.

See the [MongoDB Database Tools Documentation][mongodb-database-tools-doc] for usage information for each of the Database Tools.

<!-- # FAQs -->

# Resources

* What is MongoDB?: <https://docs.mongodb.com/upcoming/#what-is-mongodb->
* Install MongoDB: <https://docs.mongodb.com/guides/server/install/>
* Install MongoDB Community Edition on Windows: <https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/>
* Install MongoDB Community Edition on macOS: <https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/>
* The MongoDB Database Tools Documentation: <https://docs.mongodb.com/database-tools/>


[mongod]: <https://docs.mongodb.com/manual/reference/program/mongod> "Doc for mongod"
[mongosh]: <https://docs.mongodb.com/mongodb-shell> "Doc for mongosh"
[mongotop]: <https://docs.mongodb.com/database-tools/mongotop> "Doc for mongotop"
[mongodb-database-tools-doc]: <https://docs.mongodb.com/database-tools/> "MongoDB Database Tools Documentation"