## Preparing a macOS machine for the Labs
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
10. Install IBM Cloud (Bluemix) CLI  
11. Install the IBM Container Service plugins
12. Install the Kubernetes kubectl CLI
13. Install the MYSQL client

### Step 1: Install Xcode
1.	In a browser search engine, type `xcode` and select [Xcode on the Mac App Store - iTunes Apple]( https://itunes.apple.com/ca/app/xcode/id497799835?mt=12).  
2. Click the link __View in Mac App Store__.
3. Click the __Get__ button.
4. It changes to an __Install App__ button. Click it again.  
NOTE: The download is approximately 4.5GB. It may take a long time.
5. Verify the installation. Open __Xcode__, select __File > New > Playground__. Create the playground and verify that you see the string __Hello, playground__.

### Step 2: Install Homebrew
1. In your browser, go to `https://brew.sh/`. Follow the installation instructions on the web site.
2. Verify the installation by typing  
`brew help`  
You should see a list of usage examples.

### Step 3: Install Java JDK 1.8
1.	In a browser, open https://www.oracle.com
2.	In the list of menu options, click __Downloads and Trials__.
3.	Click __Java for Developers__.
4.	In the list, look for the newest version that starts with __Java SE 8__. At the time of writing, the newest version was Java SE 8u171. In that section, click the __DOWNLOAD__ button under __JDK__ (Note: your minor version may be different)
5.	In the section that lists installation files for the various operating systems, click the __Accept License Agreement__ radio button at the top.
6. Select the __Mac OS X x64__ file (jdk-8u171-macosx-x64.dmg or newer).  
7. Double-click the downloaded file to open it.
8. Double-click the package to unpack it. Follow the default installation instructions.
9. Verify that the installation was successful by typing  
`java` in a terminal window.
You should see a list of usage options.

### Step 4: Create JAVA_HOME environment variable
1. Open bash_profile in an editor:  
`$ vi ~/.bash_profile`
2. Add the following line to the bottom of the file:  
`export JAVA_HOME=$(/usr/libexec/java_home)`
3. __Save__ and __close__ the file.  
4. In the terminal window, type  
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
**NOTE**: If the response is __The document has moved__, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.
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

### Step 10: Install the IBM Cloud (Bluemix) CLI
1. In a browser, go to https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html
2. Click the installer for MacOS and follow the instructions to install the IBM Cloud CLI.
3. Type `bx -v` to return the version number.

### Step 11: Install the IBM Cloud Container Service plugins
There are two plugins associated with the IBM Cloud Container Service that you will need for the labs. They are the plugin for the container service itself (`bx cs` commands) and the plugin for the container registry (`bx cr` commands).
1. Type  
`bx plugin install container-service -r Bluemix`<br>
`bx plugin install container-registry -r Bluemix`
2. Check that the plugins are installed by typing
`bx plugin list`

### Step 12: Install the Kubernetes kubectl CLI
1. type
`brew install kubectl`
More information can be found at https://kubernetes.io/docs/tasks/tools/install-kubectl.

### Step 13: Install the MYSQL client
The easiest way to do this is to just install the full MYSQL product, then use the client from it. You should install MYSQL version 5.7.
1. Type
`brew install mysql@5.7`
