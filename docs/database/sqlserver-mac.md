---
layout: default
title: Install SqlServer on Mac
parent: Database
---

# Install MS SqlServer on Mac
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

 1. TOC
{:toc}


# Prerequisite

1. You're using Mac

2. You should have Docker installed (if not, please check this [link]({{ site.baseurl }}{% link docs/tools/docker.md %}) to install, and get back)


## Choose A Place on your Mac 

You can choose anywhere to store a docker-compose file. For example, 

 ![](/assets/images/database/sqlserver-mac/sqlserver-mac-1.png)


## Create docker-compose.yml

Type or copy the following code into it. Please take care of the indents (If you encounter any issue of the syntax of YML, please use this [Online YML Checker](https://yamlchecker.com/)) to help you.

[Optional] change the password to yours.

```yml
version:  "3"
services:
  mssql:
    image: mcr.microsoft.com/azure-sql-edge
    cap_add: [ 'SYS_PTRACE' ]
    environment:
      - "ACCEPT_EULA=1"
      - "MSSQL_SA_PASSWORD=YourPassword"
    ports:
      - "1433:1433"
    hostname: mssql
    volumes:
      - "mssql-azuresql-edge-data:/var/opt/mssql"
  
volumes:
    mssql-azuresql-edge-data:
    sqlpad-volume:
```


 ![](/assets/images/database/sqlserver-mac/sqlserver-mac-2.png)


## Generate your SqlServer Container

Open your terminal and switch to the path as same as your docker-compose.yml file. Type the following command.



```bash
docker-compose up
```

If everything goes well, you would see a similar outputs like me.

 ![](/assets/images/database/sqlserver-mac/sqlserver-mac-3.png)




# Connect to Sql Server

## Prerequisite

1. Installed Azure Data Studio

2. A Running Sql Server


## Open your Azure Data Studio


 ![](/assets/images/database/sqlserver-mac/sqlserver-mac-4.png)

## Click "Create a connection"

 ![](/assets/images/database/sqlserver-mac/sqlserver-mac-6.png)


## If everything goes well, you should see we connected sql server successfully.

![](/assets/images/database/sqlserver-mac/sqlserver-mac-7.png)




