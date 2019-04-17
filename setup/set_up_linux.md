# Preparing a Linux machine for the Labs
This document provides the steps to install the software necessary for the lab exercises on a Linux machine. The instructions are written using an Ubuntu system.

1. Install curl
2. Install IBM Cloud Developer Tools
3. Install Java JDK 1.8  
4. Create JAVA_HOME environment variable  
5. Install node.js  

## Step 1: Install curl

1. Update all the component installation packages for your operating system.

		sudo apt-get update && sudo apt-get dist-upgrade
		
2. Run the following command (At the message __Do you want to continue__, type __Y__):  

		sudo apt-get install curl
		
3. When the installation is complete, verify that it was successful by typing  

		curl https://www.google.com
4. Verify that the response is HTML for the Google home page.  
__NOTE__: If the response is __The document has moved__, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.

## Step 2: Install the IBM Cloud Developer Tools

1. Follow the instructions at [Getting started with the IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview) to install the IBM Cloud Developer Tools.

## Step 3: Install & Configure Java

1.	From your command line, enter the following command:

		sudo apt-get install openjdk-8-jdk
		export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
		export PATH=$PATH:$JAVA_HOME/bin
		
2. To make these definitions persist over new sessions and reboots, enter your environment variable definitions into your profile.
   
		sudo vi /etc/profile
		
   Add the following statements to the end of the file, and save and close it.
   
		export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
		export PATH=$PATH:$JAVA_HOME/bin
   
## Step 4: Install node.js
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
