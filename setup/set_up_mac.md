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
9. Install Docker  
10. Install Bluemix (IBM Cloud) CLI  
11. Install the IBM Container Service plugins
12. Install Kubernetes kubectl CLI

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

### Step 7: Verify that curl is installed
1. Type
`curl http://www.google.com`
2. Verify that the response is the HTML for the Google page.  
**NOTE**: If the response is �The document has moved�, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.
3. If you do not have curl installed, you can get it from the Mac App Store (http://macappstore.org/curl), or you can find various version binaries and source code at https://curl.haxx.se/download.html .

### Step 8: Install node.js
1. Type  
	`brew install node `
2. Verify the installation:  
`node -v`  
The response is the version number (for example, v4.2.6).
3. Type  
`npm -v`  
Again, the response is the version number.

### Step 9: Install Docker
1. In a browser, open   
[https://docs.docker.com/docker-for-mac/](https://docs.docker.com/docker-for-mac/)
2. In the left pane, click `Install Docker for Mac`.
3. Click the button `Download from Docker Store`.
4. Follow the instructions on the web page to install Docker and make sure it is running.

### Step 10: Install the IBM Cloud Bluemix CLI
1. In a browser, go to https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html
2. Click the installer for MacOS and follow the instructions to install the Bluemix CLI.
3. Type `bx -v` to return the version number.

### Step 11: Install the IBM Container Service plugins
There are two plugins associated with the IBM Cloud Container Service that you will need for the labs. They are the plugin for the container service itself (`bx cs` commands) and the plugin for the container registry (`bx cr` commands).
1. Type  
`bx plugin install container-service -r Bluemix`
`bx plugin install container-registry -r Bluemix`
2. Check that the plugins are installed by typing
`bx plugin list`

### Step 12: Install the Kubernetes kubectl CLI
1. type
`brew install kubectl`
More information can be found at https://kubernetes.io/docs/tasks/tools/install-kubectl.

This completes the setup tasks to perform the hands-on labs on your MacOS native environment.
