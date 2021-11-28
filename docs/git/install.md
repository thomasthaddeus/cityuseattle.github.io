---
layout: default
title: Install Git
parent: Git
nav_order: 2
---



{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


# Install git on MacOS

* [Section 1: Checking your version of Git](#section-1-checking-your-version-of-git)
* [Section 2: Using brew package manager to install Git](#section-2-using-brew-package-manager-to-install-git)
* [Section 3: First-time Git setup](#section-3-first-time-git-setup)

---

### Section 1: Checking your version of Git

 1. Open a new Terminal, type and run the following command to see if you already have Git installed and check the installed version:

   ```shell
   $ git --version
   ```

   ![git_version_output](/assets/images/git_version_output.png)

 2. If you got an error and Git is not recognized by your machine, then follow [Section 2](#section-2-using-brew-package-manager-to-install-git) to install it.

### Section 2: Using brew package manager to install Git

 1. There are several options for installing Git on macOS. Note that any non-source distributions are provided by third parties and may not be up to date with the latest source release.  
   In this tutorial, we will use homebrew, a package manager in macOS, to install Git. If you don't like to use homebrew, you can follow <https://git-scm.com/download/mac> to install Git in other way.  
   Note: if you encounter problems while installing Git using another way, TA may not be able to solve your problem.

 2. Follow the steps in the link <https://sourabhbajaj.com/mac-setup/Homebrew/> to install homebrew if you don't already have it. For more information about what brew can do, visit the following link <https://brew.sh/>

 3. Let us install Homebrew. Open the terminal and type the following

    ```shell
    $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    ```

    ![install_brew_output](/assets/images/install_brew_output.png)

 4. If it asks you to press RETURN to continue, then press RETURN/Enter button.

    ![installing_brew_output](/assets/images/installing_brew_output.png)

 5. Then choose **Install**

    ![xcode_command](/assets/images/xcode_command.png)

 6. After the installation is done, type the following in the terminal to install Git

    ```shell
    $ brew install git
    ```

 7. Please re-execute [Section 1](#section-1-checking-your-version-of-git) to verify the installation is successful.

### Section 3: First-time Git setup

 1. **First of all**, if you encounter any problems in this section, please read the official GitHub tutorial first, which can solve most of your problems. <https://docs.github.com/en/authentication/connecting-to-github-with-ssh>

 2. The first thing you should do when you install Git is to set your username and email address. This is important because every Git commit uses this information, and it's immutably baked into the commits you start creating:  
    Note: replace `<username>` to your GitHub username, and `<email>` to the email address you used to register GitHub.  

    ```shell
    $ git config --global user.name "<username>"
    $ git config --global user.email <email>
    ```

    If you want to know more about git config command, you can see here <https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup>

 3. Enter `ls -al ~/.ssh` to see if existing SSH keys are present:

    ```shell
    $ ls -al ~/.ssh
    # Lists the files in your .ssh directory if they exist
    ```

    Check the directory listing to see if you already have a public SSH key. By default, the filenames of the public keys are one of the following:

    * id_rsa.pub
    * id_ecdsa.pub
    * id_ed25519.pub

 4. If you don't have an existing public and private key pair, type the following command, and generate a new SSH Key. Note: replace `<email>` to the email address you used to register GitHub.

    ```shell
    $ ssh-keygen -t ed25519 -C "<email>"
    ```

    Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:

    ```shell
    $ ssh-keygen -t rsa -b 4096 -C "<email>"
    # Example output:
    Generating public/private ed25519 key pair.
    Enter file in which to save the key (/home/your mac username/.ssh/id_ed25519):  #  Please press Enter to keep the default save path.
    Created directory '/home/your mac username/.ssh'.
    Enter passphrase (empty for no passphrase):	# You can enter the password, but Git  will ask you to enter this password every time you connect to the remote server  (GitHub). If you choose to use a password, you can use ssh-agent to avoid  re-entering the password in a short time. If you are using your own computer, it  is recommended to keep it empty (press Enter directly).
    Enter same passphrase again:
    Your identification has been saved in /home/your mac username/.ssh/id_ed25519.
    Your public key has been saved in /home/your mac username/.ssh/id_ed25519.pub.
    The key fingerprint is:
    ```

 5. Print the id_rsa.pub, then please select and copy the output.

    ```shell
    $ cat ~/.ssh/id_ed25519.pub
    ```

    If you are using RSA algorithm, please type:

    ```shell
    $ cat ~/.ssh/id_rsa.pub
    ```

 6. Visit GitHub, in the upper-right corner of any GitHub page, click your profile photo, then click **Settings**.

    ![github_settings_dropdown_menu](/assets/images/github_settings_dropdown_menu.png)

 7. Then select the "*SSH and GPG keys*" section along the left-hand side. From there, click the "*New SSH key*" button.

    ![github_ssh_setting_page](/assets/images/github_ssh_setting_page.png)

 8. In the "*Title*" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

 9. Paste the contents of your `~./ssh/id_ed25519.pub` (or `~/.ssh/id_rsa.pub`) public-key file into the "*Key*" field and click "*Add key*".

    ![github_add_ssh_key](/assets/images/github_add_ssh_key.png)

10. If prompted, confirm your GitHub password.

    ![github_confirm_pw](/assets/images/github_confirm_pw.png)

11. To test your SSH connection, enter the following in your terminal:

    ```shell
    $ ssh -T git@github.com
    # You may see a warning like this:
    The authenticity of host 'github.com (IP ADDRESS)' can't be established.
    RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
    Are you sure you want to continue connecting (yes/no)?
    ```

12. Verify that the fingerprint in the message you see matches [GitHub's RSA public key fingerprint](https://docs.github.com/en/github/authenticating-to-github/githubs-ssh-key-fingerprints). If it does, then type `yes` and press enter:

    ```text
    Hi your_GitHub_username! You've successfully authenticated, but GitHub does not provide shell access.
    ```

13. Verify that the resulting message contains your GitHub username. If you receive a "permission denied" message, see "[Error: Permission denied (publickey)](https://docs.github.com/en/articles/error-permission-denied-publickey)".



# Install git on Windows

### Section 1: Installing Git for Windows

 1. Visit <https://git-scm.com/download/win> and click on "Git for Windows Setup."

    ![git_downloads_page](/assets/images/git_downloads_page.png)

 2. Open the file that was downloaded.

 3. Choose yes to allow Git installation on your PC.

    ![user_account_control](/assets/images/user_account_control.png)

 4. Go through the installation and choose the default option.

    ![install_license](/assets/images/install_license.png)

 5. For this one, we will choose the last option to give us extra commands to use.

    ![path_env](/assets/images/path_env.png)

 6. For the rest of the installation, choose the default options. 

 7. Uncheck View Release Notes because we do not need it.

    ![install_completing](/assets/images/install_completing.png)

### Section 2: Testing the Git installation

Once the installation is completed, open the cmd

 1. In the search bar, type cmd, and choose Command Prompt.

    ![win_search](/assets/images/win_search.png)

 2. In the cmd, type git --version, you will see git version 2.27.0.

    ![git_version_output](/assets/images/git_version_output.png)

 3. **_Note: If you got the following error_**

    ![git_path_env_error](/assets/images/git_path_env_error.png)

    **Then**, you need to add the PATH of Git into the Environment Variables

 4. In the cmd, type "`where git`"

    ![where_git_output](/assets/images/where_git_output.png)

 5. Copy the first one and add it to the environment variables.  
    To open the environment variables in the search bar, type environment variables and choose Edit system environment variables.

    ![sys_path_env_editer_search](/assets/images/sys_path_env_editer_search.png)

 6. Choose Environment Variables.

    ![sys_properties](/assets/images/sys_properties.png)

 7. In the System Variables, choose Path, then select Edit Button.

    ![env_var_page](/assets/images/env_var_page.png)

 8. Choose New, then Paste the Git location that you copied from the cmd.

    ![add_new_path_env_var](/assets/images/add_new_path_env_var.png)

 9. **Close the cmd**, then open it one more time and type `git --version` to make sure that the Git installed successfully.

### Section 3: First-time Git setup

 1. **First of all**, if you encounter any problems in this section, please read the official GitHub tutorial first, which can solve most of your problems. <https://docs.github.com/en/authentication/connecting-to-github-with-ssh>

 2. The first thing you should do when you install Git is to set your username and email address. This is important because every Git commit uses this information, and it's immutably baked into the commits you start creating:  
    Note: replace `<username>` to your GitHub username, and `<email>` to the email address you used to register GitHub.  

    ```shell
    $ git config --global user.name "<username>"
    $ git config --global user.email <email>
    ```

    If you want to know more about git config command, you can see here <https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup>

 3. Enter `ls -al ~/.ssh` to see if existing SSH keys are present:

    ```shell
    $ ls -al ~/.ssh
    # Lists the files in your .ssh directory if they exist
    ```

    Check the directory listing to see if you already have a public SSH key. By default, the filenames of the public keys are one of the following:

    * id_rsa.pub
    * id_ecdsa.pub
    * id_ed25519.pub

 4. If you don't have an existing public and private key pair, type the following command, and generate a new SSH Key. Note: replace `<email>` to the email address you used to register GitHub.

    ```shell
    $ ssh-keygen -t ed25519 -C "<email>"
    ```

    Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:

    ```shell
    $ ssh-keygen -t rsa -b 4096 -C "<email>"
    # Example output:
    Generating public/private ed25519 key pair.
    Enter file in which to save the key (/home/your mac username/.ssh/id_ed25519):  #  Please press Enter to keep the default save path.
    Created directory '/home/your mac username/.ssh'.
    Enter passphrase (empty for no passphrase):	# You can enter the password, but Git  will ask you to enter this password every time you connect to the remote server  (GitHub). If you choose to use a password, you can use ssh-agent to avoid  re-entering the password in a short time. If you are using your own computer, it  is recommended to keep it empty (press Enter directly).
    Enter same passphrase again:
    Your identification has been saved in /home/your mac username/.ssh/id_ed25519.
    Your public key has been saved in /home/your mac username/.ssh/id_ed25519.pub.
    The key fingerprint is:
    ```

 5. Print the id_rsa.pub, then please select and copy the output.

    ```shell
    $ cat ~/.ssh/id_ed25519.pub
    ```

    If you are using RSA algorithm, please type:

    ```shell
    $ cat ~/.ssh/id_rsa.pub
    ```

 6. Visit GitHub, in the upper-right corner of any GitHub page, click your profile photo, then click **Settings**.

    ![github_settings_dropdown_menu](/assets/images/github_settings_dropdown_menu.png)

 7. Then select the "*SSH and GPG keys*" section along the left-hand side. From there, click the "*New SSH key*" button.

    ![github_ssh_setting_page](/assets/images/github_ssh_setting_page.png)

 8. In the "*Title*" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

 9. Paste the contents of your `~./ssh/id_ed25519.pub` (or `~/.ssh/id_rsa.pub`) public-key file into the "*Key*" field and click "*Add key*".

    ![github_add_ssh_key](/assets/images/github_add_ssh_key.png)

10. If prompted, confirm your GitHub password.

    ![github_confirm_pw](/assets/images/github_confirm_pw.png)

11. To test your SSH connection, enter the following in your terminal:

    ```shell
    $ ssh -T git@github.com
    # You may see a warning like this:
    The authenticity of host 'github.com (IP ADDRESS)' can't be established.
    RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
    Are you sure you want to continue connecting (yes/no)?
    ```

12. Verify that the fingerprint in the message you see matches [GitHub's RSA public key fingerprint](https://docs.github.com/en/github/authenticating-to-github/githubs-ssh-key-fingerprints). If it does, then type `yes` and press enter:

    ```text
    Hi your_GitHub_username! You've successfully authenticated, but GitHub does not provide shell access.
    ```

13. Verify that the resulting message contains your GitHub username. If you receive a "permission denied" message, see "[Error: Permission denied (publickey)](https://docs.github.com/en/articles/error-permission-denied-publickey)".
