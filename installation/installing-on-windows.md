---
description: Installation steps for a Windows system.
---

# Installing on Windows

## Install on Windows 10+

Installing on windows is very straight forward but you will need to do a handful of things to ensure your environment is setup correctly. There is a lot to cover when installing Athena but these instructions cover nearly everything you need to do in a Windows Environment to get Athena running.

Read them carefully, read them twice, and double check your steps.

### Read this First

This happens all the time where people don't understand that `<` & `>` are placeholders for you to fill out the rest. Remove the `<` & `>` if you see it.

**EXAMPLE**

```
git pull <your_url_here>
```

**REPLACEMENT**

```
git pull https://someurl.com/blah/blah
```

## Dependencies

You will need to install, setup, or create accounts for all of the links that are in this section.

*   [Download and Install GIT](https://git-scm.com/downloads)

    * Used to pull down and push up code changes to your repositories.


*   [Download and Install NodeJS 18+](https://nodejs.org/en/download/current/)

    * A runtime that runs JavaScript code.


*   [Download and Install MongoDB Community Server](https://www.mongodb.com/try/download/community)

    * A NoSQL Database that is fast and easy.


*   [Download and Install VSCode](https://code.visualstudio.com/download)

    * An integrated development environment for writing code and getting suggestions as you write code.


*   [Create a GitHub Account](https://github.com/)

    * GitHub will let you privately store a modified version of the Athena codebase.


* [Download Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-us\&gl=US)
  * Great for inputting commands like the ones you will see in this tutorial. Highly recommended to install and pin it to your desktop somewhere.

## Setup SSH Key

Github has really good [SSH Setup Instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) but they may not be entirely clear for newer developers. If you are comfortable with normal documentation give the above link a try. Make sure to select the `windows` tab.

### Open Git Bash

Git Bash is something that should come with GIT by default. Enter `Git Bash` in your windows search to open it.

![](https://thumbs.gfycat.com/SeveralSleepyBarracuda-size\_restricted.gif)

### Create the SSH Key

Enter the following in a terminal:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

It may ask you for a password. Hitting enter twice will automatically default to `no password`.

### Start ssh-agent

Enter the following in a terminal:

```
eval "$(ssh-agent -s)"
```

_It should respond with 'Agent pid XYZ'_

### Add the SSH Key

Enter the following in a terminal:

```
ssh-add ~/.ssh/id_ed25519
```

### Add the SSH Key to Github

It is highly recommended you follow the Github instructions for the rest of this tutorial. They cover / update how to add SSH keys very well.

Enter the following in a terminal:

```
cat ~/.ssh/id_ed25519.pub
```

**Copy** the text printed from `ssh-ed25519` all the way to your email.

![id\_ed25519.pub key copy example](https://i.imgur.com/NPjcWhW.png)

Navigate to your GitHub settings and the `SSH and GPG keys` section.

Click on `New SSH Key`

![Click New SSH Key to add it to your GitHub.](https://i.imgur.com/VyCobd5.png)

Give the key a name, and paste the public key into the larger text box.

## Ensure MongoDB Running as a Service

MongoDB does not have to be installed locally but if it is this is an important step. Open your Task Manager and ensure that you see MongoDB running as a service.

![](https://i.imgur.com/2Osus8S.png)

## Port Forwarding

At the very least you will need to open port 7788 for your main server if you are exposing it to the outside world. This means that if you want other users to join your server, you have to expose this port. Otherwise, you'll need to purchase a VPS or dedicated server. If you are doing this for development purposes then you do not need to port forward.

You may need to Forward Ports in your Server Panel, Router, etc. If you are running Athena on a server it is likely you will need to add 7788 to an additional Firewall somewhere in your server providers panel.

You will need to open the following ports in your **Windows Firewall** and **Router**.

* 7788

Here's a `.bat` script that will open both ports in your **Windows Firewall.**

```
ECHO OFF

echo Opening 7788 for TCP
netsh advfirewall firewall add rule name="alt:V-7788-IN-TCP" dir=in action=allow protocol=TCP localport=7788
netsh advfirewall firewall add rule name="alt:V-7788-OUT-TCP" dir=out action=allow protocol=TCP localport=7788

echo Opening 7788 for UDP
netsh advfirewall firewall add rule name="alt:V-7788-IN-UDP" dir=in action=allow protocol=UDP localport=7788
netsh advfirewall firewall add rule name="alt:V-7788-OUT-UDP" dir=out action=allow protocol=UDP localport=7788

pause
```

If you need additional help with port forwarding in your router you should check out this[ Port Forward Website](https://portforward.com/router.htm) where you can find instructions for your router based on brand.

_You can verify that ports have been opened successfully after you setup the rest of Athena._

## Setup Private Repo

Open a Windows Terminal such as command line or powershell. The author personally recommends [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab) from the Microsoft Store.

Enter the following in a terminal:

```bash
git clone https://github.com/Stuyk/altv-athena --bare altv-athena-bare
```

Create a new private repistory on Github. Let's call it altv-athena-private

![](https://i.imgur.com/y1Lxqwn.png)

Copy your URL from github.

![](https://i.imgur.com/Dd7Zrke.png)

Enter the following in a terminal:

```bash
cd altv-athena-bare
```

Then you are going to mirror the bare repository to your private mirror.

Which means you will have a private copy of Athena's code base on your private GitHub.

Enter the following in a terminal:

```bash
git push --mirror your_github_url_here
```

Delete the bare repository folder you have just created.

### Set Private Repo Main Branch to Master

This is important and **DO NOT SKIP THIS STEP**.&#x20;

You will need to visit **your GitHub** and find the newly created repository in your `repositories` section on your profile. You will then click on it, and go to settings.

![Your GitHub repository settings for a mirrored Athena repository.](https://i.imgur.com/FXae1k2.png)

![Switching the main branch to master.](https://i.imgur.com/czfpchr.png)

### Download from Private Repo

Clone the new repository you created from Github.

You can find the new repository you created in your Github profile's repository section.

Enter the following in a terminal:

```bash
git clone the_url_from_your_private_github_repo
```

### Enter the Directory

You need to navigate into the directory to run the next few commands.

Enter the following in a terminal:

```bash
cd your_repo_name
```

### Add Upstream

Add the upstream of the original Athena repository.

This step must be done any time you need re-clone your repository.

```bash
git remote add upstream https://github.com/Stuyk/altv-athena
git remote set-url --push upstream DISABLE
```

### Pushing updates

When you make changes to the code base you can push it by doing:

```
git add .
git commit -m "Whatever You Changed"
git push origin master
```

## Installing Dependencies

This installs all NodeJS packages and dependencies that help run the server.

```
npm install
```

## Installing Server Files

From this point forward you can simply run this `npm` command to update dependencies.

```
npm run update
```

## Starting the Server

**Hey Listen,** normally you start the server through altv-server.exe but **we do not do that with Athena**. There are other programs that run along-side Athena that allow it to function. You will need to run one of the commands below.

### Update the server.cfg

Do not modify the server.cfg, yes you are reading this correctly.

Instead, you should do the following.

Open 1 of the 3 configuration(s) in the `configs` folder.

You should see any of the following configurations:

* dev.json
* devtest.json
* prod.json

Edit all of these but remember this very important rule.

Do not change 'host' because 0.0.0.0 is correct.

### Production Mode

This is the mode you should use when you are having users connect.

Enter the following in a terminal:

```
npm run windows
```

### Development Test Mode

This is the mode you should use when you are having a limited set of users connect with `debug` mode on.

Enter the following in a terminal:

```
npm run devtest
```

### Development Mode

This is the mode you should use when you want to work on making changes. Limited to 1 user joining at a time. This should be used for all your major development. This is the fastest way to develop your game mode and requires the least amount of compile time to test things.

Enter the following in a terminal:

```
npm run dev
```

## Checking Ports

Check if the ports are currently open **while the server is running**. Check port `7788`.

[Check Ports with YouGetSignal](https://www.yougetsignal.com/tools/open-ports/)

## Connecting

Remember to get the [https://altv.mp/](https://altv.mp) client and connect.

### What IP to use?

If you are running this on your local machine you should connect to `127.0.0.1:7788` or `0.0.0.0:7788` if it does not work.

If you are running this on an external server you should connect to the server's IP address.

## Successful Installation

A successful installation and bootup will look like the following:

![](https://i.imgur.com/F05NiT6.png)
