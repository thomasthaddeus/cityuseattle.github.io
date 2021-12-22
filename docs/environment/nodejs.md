---
layout: default
title: Install nodejs and npm
parent: Environment
nav_order: 3
---

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<p align="center">
<img alt="python_logo" src="/assets/images/node/nodejs_npm_logo.png"/>
</p>

## Key Concepts

* This tutorial explains how to install Node.js and NPM through the installer. If you need to install through the package manager, please refer to this tutorial: <https://nodejs.org/en/download/package-manager/>
* Downloading and installing Node.js and npm - <https://docs.npmjs.com/downloading-and-installing-node-js-and-npm>
* About Node.js: "As an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications." - <https://nodejs.org/en/about/>
* Node.js on Wikipedia - <https://en.wikipedia.org/wiki/Node.js>
* Node.js website - <https://nodejs.org/>
* NPM Documentation - <https://docs.npmjs.com/>



---

* [Section 1: Checking your version of NPM and Node.js](#section-1-checking-your-version-of-npm-and-nodejs)
* [Section 2: Using a Node installer to install Node.js and NPM](#section-2-using-a-node-installer-to-install-nodejs-and-npm)

---

# Section 1: Checking your version of NPM and Node.js

 1. To see if you already have Node.js and NPM installed and to check the installed version, run the following commands in your Terminal:

    ```bash
    $ node -v
    $ npm -v
    ```

# Section 2: Using a Node installer to install Node.js and NPM

 1. If you're using MacOS or Windows, use one of the installers from the Node.js download page.  
    Open <https://nodejs.org/en/download/> then download the latest version of the Node.js installable archive file.  
    Be sure to install the version labeled long-term support (**LTS**).  
    (As of Sep 22, 2021, the latest Node.js LTS version is 14.17.6 which includes NPM 6.14.15)  

    ![](/assets/images/node/nodejs_download_page.png)

 2. Install Node.js

    ![](/assets/images/node/installing_win.png)

    ↑Windows, ↓MacOS

    ![](/assets/images/node/installing_mac.png)

 3. Please re-execute [Section 1](#section-1-checking-your-version-of-npm-and-nodejs) to verify the installation was successful.
