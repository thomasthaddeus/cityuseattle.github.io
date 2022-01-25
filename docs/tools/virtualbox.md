---
layout: default
title: Install virtualbox
parent: Tools
---

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

 1. TOC
{:toc}

---


# Install VirtualBox on MacOS (No Apple Silicon Valley Support)

**If you're using Apple Silicon Valley, VirtualBox may not work well. You will need to find alternatives.**

[Check if you're using Apple Silicon Valley]({{ site.baseurl }}{% link docs/common/applem1.md %})

 1. Open the [VirtualBox download page](https://www.virtualbox.org/wiki/Downloads), then choose the latest version and click "OS X hosts"

    ![virtualbox_download_page](/assets/images/virtualbox/virtualbox_download_page.png)

 2. Once you get the downloaded install package, click on it and you will see the image below. Click on VirtualBox.pkg. In the next several steps, you will see some questions during the installation process. Just click "Allow", "Continue" and "Done". That's it.

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_installing.png)

 3. Open the installed VirtualBox. If you can see the image below, congrats! It installed successfully!

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_homepage.png)

 4. To avoid VirtualBox complaining about the kernel driver in the future, i.e. the error is shown below, you must explicitly allow VirtualBox to load, in the MacOS system preferences, within the first 30 minutes after VirtualBox is installed.

    ![kernel_driver_not_installed](/assets/images/virtualbox/kernel_driver_not_installed.png)

    Go to System Preferences / Security & Privacy.

    ![macos_sys_preferences_security_privacy](/assets/images/virtualbox/macos_sys_preferences_security_privacy.png)

    Click "Allow" in the window that appears.

    ![macos_allow_loading](/assets/images/virtualbox/macos_allow_loading.png)

    This Allow button section shows up only after first 30 minutes after the installation of VirtualBox. If you have this error and don’t see the button, uninstall VirtualBox, remove its belongings (there are usually some files left) and install it once again, then check this button again.

# Install VirtualBox on Windows

 1. Open the [VirtualBox download page](https://www.virtualbox.org/wiki/Downloads), then choose the latest version and click "Windows hosts"

    ![virtualbox_download_page](/assets/images/virtualbox/virtualbox_windows_homepage.png)

 2. Once you get the downloaded install package, click on it and you will see the image below. Click on VirtualBox-xxxxx-Win.exe. In the next several steps, you will see some questions during the installation process. 

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install.png)

    Click "Next".

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install_1.png)

    Click "Next".

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install_2.png)

    Click "Yes".

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install_3.png)

    Click "Install". After that, it may take a while, so please be patient. During the installation process it will ask for your permission. Click "Allow" or "Yes" to complete the installation.

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install_4.png)

    Click "Finish".

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_install_5.png)

 3. Open the installed VirtualBox. If you can see the image below, congrats! It installed successfully!

    ![virtualbox_installing](/assets/images/virtualbox/virtualbox_windows_home.png)

# Next

Now you have successfully installed VirtualBox in your machine. If you want to add any Linux distribution inside the VirtualBox like:

* [Ubuntu]({{ site.baseurl }}{% link docs/tools/ubuntu.md %})
* [Kali Linux]({{ site.baseurl }}{% link docs/tools/kali_virtualbox.md %})
