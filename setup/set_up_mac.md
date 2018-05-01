## Set up MAC OS X
This document provides the steps for installing the software required to begin the exercises on a Mac computer. The sequence is as follows:  
1. Install Xcode  
2. Install Homebrew  
3. Install Java 1.8  
4. Create JAVA_HOME environment variable
5. Install Gradle  
6. Install GIT  
7. Install curl  
8. Install node.js  
9. Install API Connect  
10. Install Docker  
11. Install Bluemix (IBM Cloud) CLI  
12. Install the IBM Container Service plugins
13. Install Kubernetes kubectl CLI

### Step 1: Install Xcode
1.	In a browser search engine, type xcode and select [Xcode on the Mac App Store - iTunes � Apple]( https://itunes.apple.com/ca/app/xcode/id497799835?mt=12).  
Note: This was the link title at the time of writing. You search *itunes* for the XCode download link.  
2. Click the Link View in Mac App Store.
3. Click the **Get** button.
4. It changes to an Install App button. Click it again.  
NOTE: The download is approximately 4.5GB. It may take a long time.
5. Verify the installation. Open Xcode, select **File > New > Playground**, then create the playground and verify that you see the string �Hello, playground�.

### Step 2: Install Homebrew
1. Got to `https://brew.sh/` to see find the current installation process.
2. Verify the installation by typing  
`brew help`  
You should see a list of usage examples.

### Step 3: Install Java JDK 1.8
1. Open a browser to [https://www.oracle.com]( https://www.oracle.com).  
2. In the list of menu options, hover over **Downloads** (if you cannot see it, reduce the zoom of the browser until it appears).  
3. Under *Popular Downloads* to the left, click **Java for Developers**.  
4. Click the download button for **Java Platform (JDK) 8u111** (Note: your minor version may be different).  
5. Under the section entitled Java SE Development Kit 8u111, click the button for **Accept License Agreement**.  
6. Select the Mac OS X file (jdk-8u111-macosx-x64.dmg).  
7. Double-click the downloaded file to open it.
8. Double-click the package to unpack it (follow the default instructions).
9. Verify that the installation was successful by typing  
`java`  
You should see a list of usage options.

### Step 4: Create JAVA_HOME environment variable
1. Open bash_profile in an editor:  
`$ vi ~/.bash_profile`
2. Add the following line to the bottom of the file:  
`export JAVA_HOME=$(/usr/libexec/java_home)`

3. **Save** and **close** the file.  
4. In the Terminal, type  
`$ source ~/.bash_profile`
5. Verify that it is set correctly by typing  
`$ echo $JAVA_HOME`  
You should see the full path to the jdk.
6. Verify that your installation of Java is recognized. Type:  
`java –version`  
You should see information about the java version, the runtime environment, and Java HotSpot.

### Step 5: Install Gradle
1. Type
` brew install gradle`

### Step 6: Verify that GIT is installed
1. Type  
`git –version`
2. Verify that the response is ‘git version 2.7.x’ (your version number may be later).
3. If git is not installed, go to https://git-scm.com/download/mac and follow the instructions to install it.

### Step 6: Verify that curl is installed
1. Type
`curl http://www.google.com`
2. Verify that the response is the HTML for the Google page.  
**NOTE**: If the response is �The document has moved�, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.

### Step 7: Install node.js
1.Type  
	`brew install node `
2. Verify the installation:  
`node �v`  
The response is the version number (for example, v4.2.6).
4. Type  
`npm -v`  
Again, the response is the version number.

### Step 8: Install API Connect
Use npm to install API Connect:  
1. Type ` npm install �g apiconnect`  
NOTE: This takes some time. You see some warnings about deprecations; you can ignore them.
2. Verify the installation by typing  
`apic �v`  
You are asked to accept the license, and to allow usage information to be collected. Take the default answers for these (�Yes� and �No�). You then see the version number.

### Step 9: Install Docker
1. In a browser, open   
[https://docs.docker.com/docker-for-mac/](https://docs.docker.com/docker-for-mac/)
2. Scroll down and click the button *Get Docker for Mac (stable)*
3. Open the downloaded file.
4. A window opens with two icons. Drag the left *Docker.app* icon onto the right *Applications* icon.
5. In the *Applications* directory, double-click Docker.app.
6. Verify that the whale icon is added to the status bar at the top of the screen.
7. Click the icon to verify that Docker is running.

### Step 10: Install cloudfoundry CLI
You install cloudfoundry using a package manager.
1. In a Terminal, type  
`$ brew tap cloudfoundry/tap`
2. Install:  
`$ brew install cf-cli`
3. In order to verify the installation, type  
`cf �v`  
The response shows the version number.

### Step 11: Install the IBM Container plugin for cloudfoundry
1. Use cloudfoundry to install the container plugin:  
`cf install-plugin https://static-ice.ng.bluemix.net/ibm-containers-mac`
2. Answer �**y**� to the question about the installation.
3. Verify that the installation was successful by typing  
`cf ic`  
NOTE: You may see the message *Authentication has expired.* If so, log back in with `cf login`.

This completes the setup for the Mac environment.
