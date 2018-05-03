## Preparing a Windows machine for the Labs

This document provides the steps to install the software required to begin the exercises on a Windows machine.  The instructions were written for a Windows 7 Professional machine.  Exceptions have been noted for Windows 8 and Windows 10. The sequence is as follows:

1.	Install Java JDK 1.8
2.	Add JAVA_HOME variable to the System PATH
3.  Install Gradle
4.	Install GIT
5.	Install cURL
6.	Install node.js
7.	Install Docker
8.	Install IBM Cloud (Bluemix) CLI
9.	Install the IBM Container Service plugins
10. Install the Kubernetes kubectl CLI
11. Install the MYSQL client
12. Install Cygwin


### Step 1: Install Java JDK 1.8

1.	In a browser, open https://www.oracle.com
2.	In the list of menu options, click __Downloads and Trials__.
3.	Click __Java for Developers__.
4.	In the list, look for the newest version that starts with __Java SE 8__. At the time of writing, the newest version was Java SE 8u171. In that section, click the __DOWNLOAD__ button under __JDK__ (Note: your minor version may be different)
5.	In the section that lists installation files for the various operating systems, click the __Accept License Agreement__ radio button at the top.
6.	Select the .exe file for Windows x64 (__jdk-8u171-windows-x64.exe__).  The file is downloaded to the machine's Download directory.
7.	 Run the Windows executable.  Navigate to the Download directory. Double click __jdk-8u171-windows-x64.exe__.
8.	At the Welcome screen, click __Next__.
9.	Accept the features to install.  Accept the default install location __C:\Program Files\Java\jdk1.8.0_171__.  Click __Next__.
10.	Upon successful installation, click __Close__.
11.	Verify that the installation was successful.  Open a command prompt.  Change directories to __C:\Program Files\Java\jdk1.8.0_171__. You should see 6 directories, 6 files, and 2 zip files.

### Step 2: Add JAVA_HOME variable to the System PATH  

Add JAVA_HOME to the Path by editing an environment variable.

1.	Add or modify the __JAVA_HOME__ environment variable to the value __C:\Program Files\Java\jdk1.8.0_171__ (or whatever version you installed).
2.	Add __JAVA_HOME__ to the end of the __Path__ system variable.
3.	Close the Environment Variables window.
4.	Restart the computer.
5.	Verify that your installation of Java is recognized. Open a command prompt and type:
`java -version`.
6.	You should see information about the Java version, Java runtime, and Java HotSpot.

### Step 3: Install gradle
1. In your browser, go to https://gradle.org/install/.
2. Follow the instructions for Windows installation. For most users, the instructions in the __Install manually__ section will be the easiest to follow.

### Step 4:  Install GIT (Your version number might be newer)
1.	Download GIT for Windows from https://git-scm.com/download/win
2.	Find the latest executable for your version of Windows. At the time of writing, this was  __Git-2.17.0-64-bit.exe__
3.	Read the GNU General Public License and click __Next__.
4.	Accept the installation location.  Click __Next__.
5.	Accept the default components for installation.  Click __Next__.
6.	Create a shortcut.  Click __Next__.
7.	Adjust the PATH environment by selecting the option labeled __Use Git from the Windows Command Prompt__.  Click __Next__.
8.	Configure the line ending conversions by selecting __Checkout Windows-style__, commit __Unix-style__ line endings. Click __Next__.
9.	Select __Use MinTTY as the terminal emulator with Git Bash__.  Click __Next__.
10.	Keep the default extra options __Enable file system caching__ and __Enable Git Credential Manager__.  Click __Next__.
11.	Do not select any experimental options.  Click __Install__.
12.	Click __Finish__.
13.	Open a command prompt and change to __C:\Program Files\Git\bin__.  Type `git --version`
14.	You should see the response `git version 2.17.windows.1`

### Step 5:  Install curl
1.	Create a folder named:  __C:\curl__.
2.	Go to http://curl.haxx.se/download.html and download the zip file for the Win64 version of cURL:
Scroll to the __Win64-Generic__ section.  Locate the latest Win64 ia64 zip version with SSL support. Click the version number to start the download.
3.	Save the zip file.
4.	Unzip the downloaded zip file.  Move __curl.exe__ to __C:\curl__.
5.	Go to http://curl.haxx.se/docs/caextract.html  and download the digital certificate file named __cacert.pem__.
6.	Move __cacert.pem__ to __C:\curl__.  Rename the file __curl-ca-bundle.crt__.
7.	Add __C:\curl__ to the Windows PATH environment variable so the curl command is available from any location at the command prompt.
8.	Verify that the installation is complete. Open a command prompt and enter `curl https://www.google.com`. The request returns the html in the command window.

### Step 6:  Install node.js
1. Go to https://nodejs.org/en/
2. There are two versions listed. Download the recommended version, which will be an msi installer file.
3. Run the msi file and install with the default options.
4. Verify the installation. At a command prompt, type `node -v`. The response is a version number.
5. Type `npm -v`. The response is a version number, along with a notice about any updates that are available.

### Step 7:  Install Docker

#### Step 7a - Enabling Virtualization

You must have virtualization enabled on your machine for Docker to work.  This must be done before you install Docker. There are instructions below for Windows 10, Windows 8 and Windows 7.

##### Windows 10

Virtualization can be enabled in the BIOS. There are instructions for Windows 10 and other versions at this location https://docs.microsoft.com/en-us/virtualization/.

##### Windows 8 or 8.1
1. Choose __Start > Task Manager__.  
2. Navigate to the __Performance__ tab.  Under __CPU__, you should see __Virtualization: Enabled__.
3. If virtualization is not enabled, then follow the manufacturers documentation.  The steps to configure BIOS settings are specific to the hardware you have. It varies from one hardware manufacturer to another, and, even different models from the same manufacturer can have different steps.  Refer to the documentation or website for your hardware make and model.  You can also check on the Intel website for guidance from Intel about their VT-x product technology.

##### Windows 7
1. You should check your system BIOS to see if hardware virtualization is enabled. If it is not enabled, enable it through the BIOS.
2. Run the Microsoft Hardware-Assisted Virtualization Detection Tool which can be found at `https://www.microsoft.com/en-us/download/details.aspx?id=592`

  - Download the MHAVDT.  Be sure to select __havdetectiontool.exe__ and the __User Guide__.
  -	Run the detection tool by clicking __havdetectiontool.exe__
  -	Accept the license agreement.  Click __Next__.
  - You should see a message __This computer is configured with hardware-assisted virtualization__.
  - Select __No, I don't want to send data__.  Click __OK__.

#### Step 7b - Installing Docker

If you have 64 bit Windows 7 or higher, follow these directions to install Docker with Toolbox.
1. Install Docker for Windows.  Follow https://docs.docker.com/docker-for-windows for specific directions.
2.	Go to https://docs.docker.com/engine/installation/windows/  and scroll down to the __Docker Toolbox__ section.
3.	Click the link for __Docker Toolbox__  https://www.docker.com/products/docker-toolbox
4.	Click __Download__ (be sure to click the Windows option, not the Apple option)
5.	Scroll down and find the __Downloads__ section.  Click the latest __DockerToolbox exe__ version and download it.
6.	Run the __DockerToolbox exe__ file and accept the default options.
7.	Verify your docker installation.
	- From the Start Menu, navigate to __All Programs >  Docker__.
	-	Click __Docker Quickstart Terminal__.
	-	There are a number of preliminary steps and downloads that must happen. Wait for a message indicating the interactive shell can start and the $ prompt is available.
	-	Type `docker run hello-world`.
	-	You should see a response starting with __Hello from Docker!__

### Step 8: Install the IBM Cloud (Bluemix) CLI
1. In a browser, go to https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html
2. Click the installer for Windows 64 bit and follow the instructions to install the IBM Cloud CLI.
3. Type `bx -v` to return the version number.

### Step 9: Install the IBM Cloud Container Service plugins
There are two plugins associated with the IBM Cloud Container Service that you will need for the labs. They are the plugin for the container service itself (`bx cs` commands) and the plugin for the container registry (`bx cr` commands).
1. Type  
`bx plugin install container-service -r Bluemix`<br>
`bx plugin install container-registry -r Bluemix`
2. Check that the plugins are installed by typing
`bx plugin list`

### Step 10: Install the Kubernetes kubectl CLI
1. In your browser, go to  https://kubernetes.io/docs/tasks/tools/install-kubectl. There are several package managers you can choose from to install the Kubernetes CLI, including Chocolatey and PowerShell Gallery. Follow the instructions on the page to install kubectl.

### Step 11: Install the MYSQL Client
1. Open a browser to https://dev.mysql.com/downloads/mysql/
2. Download the ZIP Archive version of the Windows 64 bit MYSQL 5.7 Installer. It should be approximately 320 MB.
3. When the ZIP archive is downloaded, extract it to the directory of your choice.
4. You will only need the mysql.exe executable. From the bin subdirectory under your extraction directory, move or copy the mysql.exe file to any directory in your PATH.

### Step 12: Install Cygwin

There are certain times in the labs where the way that Windows interprets quote characters makes it easier for you to issue those commands from a Linux shell. You can have that Linux shell available by installing Cygwin.

1. Open a browser to https://www.cygwin.com/
2. Under the Current Cygwin DLL version heading, click to download the latest Windows 64 bit installation exe file.
3. Run the installation exe file and follow the prompts to install Cygwin.

This completes the setup tasks for Windows.
