# Preparing a Windows 10 machine for the Labs

Windows 10 includes a feature called Windows Subsystem for Linux. This allows you to run a pure Linux operating system, without needing a virtual machine or a special shell like `Cygwin` or `git bash`. This the best way to run the lab steps, and to run a cloud development environment in general, on Windows 10. You have the choice of various Linux distributions to install. This document describes installing Ubuntu. The sequence is as follows:

1. Enable Windows Subsystem for Linux
2. Install the Ubuntu app
3. Configure Ubuntu
4. Install curl
5. Install IBM Cloud Developer Tools
6. Install & Configure Java  
7. Install node.js  

If you are using an older version of Windows, like Windows 7, follow the instructions at the link below to set up your workstation for the lab exercises.

[Setting up Windows 7 for the lab exercises](https://ibm-cloud-academy.github.io/set_up_windows7.html)

## Step 1: Enable Windows Subsystem for Linux
1. Right-click on the __Start__ menu and click on __Settings__.
2. In the Search window, type `Turn Windows Features On Or Off` and click on that item. 
3. Check the box for __Windows Subsystem for Linux__.
4. Follow the directions and restart if requested.

## Step 2: Install the Ubuntu app

1. Open a browser and go to the Microsoft Store at `https://www.microsoft.com/en-us/store`. Search for and install the __Ubuntu__ app. This will install the latest stable version of Ubuntu. When this document was written, the version was `18.0.4`.
2. Follow the prompts to install Ubuntu.
3. When the installation is finished, the __Install__ button will change to say __Launch__. Click the __Launch__ button to start Ubuntu.

## Step 3: Configure Ubuntu

1. When Ubuntu launches for the first time, it will ask you for a user name. This will be the root user for your Ubuntu system. Enter the user name of your choice.
2. When prompted, enter and confirm a password for your user.
3. After this, the basic installation and configuration of Ubuntu is complete and you are at a command prompt. Enter `pwd` to find your location in the filesystem. You should be at `/home/<username>`.
4. That is all the configuration you need to do. If you are interested in more information about Windows Subsystem for Linux, a useful setup guide can be found at `https://github.com/michaeltreat/Windows-Subsystem-For-Linux-Setup-Guide/blob/master/readmes/02_WSL_Ubuntu_setup.md` .

The remaining steps are all performed in the Windows Subsystem for Linux session, and are the same as the Linux setup steps.

## Step 4: Install curl

1. Update all the component installation packages for your operating system.

		sudo apt-get update && sudo apt-get dist-upgrade
		
2. Run the following command (At the message __Do you want to continue__, type __Y__):  

		sudo apt-get install curl
		
3. When the installation is complete, verify that it was successful by typing  

		curl https://www.google.com
4. Verify that the response is HTML for the Google home page.  
__NOTE__: If the response is __The document has moved__, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.

## Step 5: Install the IBM Cloud Developer Tools

1. Follow the instructions at [Getting started with the IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview) to install the IBM Cloud Developer Tools.

## Step 6: Install & Configure Java

1.	From your command line, enter the following command:

		sudo apt-get install openjdk-8-jdk
		export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
		export PATH=$PATH:$JAVA_HOME/bin
		
2. To make these definitions persist over new sessions and reboots, enter your environment variable definitions into your profile.
   
		sudo vi /etc/profile
		
   Add the following statements to the end of the file, and save and close it.
   
		export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
		export PATH=$PATH:$JAVA_HOME/bin
   
## Step 7: Install node.js
Ubuntu includes Node.js in its default repositories.  The version that was used for this installation was __4.2.6__. Your version might be different.

1. Install it by typing the __apt install__ command (At the message __Do you want to continue__, type __Y__):  

		sudo apt install nodejs
		
2. Verify the installation:  

		node -v  js
		
3. The response is the version number (for example, v4.2.6).
4. Install the Node Package Manager (npm) (at the message __Do you want to continue__, type __Y__):  

		sudo apt install npm
		
5. Verify the installation:  

		npm version
		
6. You should see a JSON object similar to this:  
```
{ npm: '3.5.2',
  ares: '1.10.1-DEV',
  http_parser: '2.5.0',
  icu: '55.1',
  modules: '46',
  node: '4.2.6',
  openssl: '1.0.2g-fips',
  uv: '1.8.0',
  v8: '4.5.103.35',
  zlib: '1.2.8' }
```
