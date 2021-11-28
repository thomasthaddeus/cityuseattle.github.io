---
layout: default
title: Install vs code
parent: Tools
---


{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Install VS Code
* [Section 1: Installing VSCode](#section-1-installing-vscode)
* [Section 2: Making your development directory](#section-2-making-your-development-directory)

---

# Section 1: Installing VSCode

 1. Visit <https://code.visualstudio.com/>  

    ![vscode_page](/assets/images/vscode_page.png)

 2. Select a correct version for your operating system and download it.  
    For example, you can download Windows x64 for your Windows 10.  
    (As of 8/6/2021, you can download "VSCodeUserSetup-x64-1.59.0.exe")  

    ![vscode_download_btn_clicked](/assets/images/vscode_download_btn_clicked.png)

 3. Install VSCode.

    ![vscode_page](/assets/images/setup_vscode.png)
    ![vscode_page](/assets/images/completing_setup_vscode.png)


    ![vscode_ui](/assets/images/vscode_ui.png)

# Section 2: Making your development directory

 1. Go to "View" menu and select "Terminal" menu item for your Command Line Interface (CLI).

 2. Go to the root directory of your disk drive.  
    Create a working directory called "**CS624**" for your course and move to the directory.  
    The following commands under Windows will be used.

    ```shell
    $ cd \
    $ mkdir CS624
    $ cd CS624
    ```

    Windows

    ```cmd
    $ dir
    ```

    MacOS

    ```shell
    $ ls
    ```

    **References to create a directory:**

    For Windows:  
    <https://www.digitalcitizen.life/command-prompt-how-use-basic-commands>  
    <https://www.thomas-krenn.com/en/wiki/Cmd_commands_under_Windows>

    For Mac:  
    <https://www.cs.virginia.edu/diochnos/tips/terminal/basics.html>

 3. Clear your CLI.

    Windows

    ```bash
    $ cls
    ```

    MacOS

    ```bash
    $ clear
    ```

 4. Close the VSCode.  
    Go to "File" menu end select "Exit" menu item.