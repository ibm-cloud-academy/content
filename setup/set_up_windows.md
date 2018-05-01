# Preparing Windows environment

This document provides the steps to install the software required to begin the exercises on a Windows machine.  The instructions were written for a Windows 7 Professional machine.  Exceptions have been noted for Windows 8 and Windows 10. The sequence is as follows:

1.	Install Java JDK 1.8
2.	Edit the JAVA_HOME variable and edit the system PATH
3.	Install GIT
4.	Install cURL
5.	Install node.js
6.	Install API Connect
7.	Install Docker
8.	Install cloudfoundry CLI
9.	Install the IBM Container plugin for cloudfoundry

## Part 1: Install Java JDK 1.8

1.	In a browser, open https://www.oracle.com
2.	In the list of menu options, hover over __Downloads and Trials__.
3.	Click __Developer Downloads__. Under the Java section, click __Java SE__.
4.	Under the Java SE 8u144 section, click the __DOWNLOAD__ button under JDK (Note: your minor version may be different)
5.	In the section entitled Java SE Development Kit 8u144, click __Accept License Agreement__.
6.	Select the .exe file for Windows x64 (__jdk-8u144-windows-x64.exe__).  The file is downloaded to the machine’s Download directory.
7.	 Run the Windows executable.  Navigate to the Download directory. Double click jdk-8u111-windows-x64.exe
8.	At the Welcome screen, click Next.
9.	Accept the features to install.  Accept the default install location C:\Program Files\Java\jdk1.8.0_144\.  Click Next.
10.	Upon successful installation, click Close.
11.	Verify that the installation was successful.  Open a command prompt.  Change directories to C:\Program Files\Java\jdk1.8.0_144\. You should see 6 directories, 6 files, and 2 zip files.

## Part 2:  Edit the system PATH.  

Add JAVA_HOME to the Path by editing an environment variable.

1.	Add or modify the JAVA_HOME environment variable to C:\Program Files\Java\jdk1.8.0_144
2.	Add JAVA_HOME to the end of the Path system variable.
3.	Close the Environment Variables window.
4.	Restart the computer.
5.	Verify that your installation of Java is recognized. Open a command prompt and type:
java –version
6.	You should see information about the Java version, Java runtime, and Java HotSpot.

## Part 3:  Install GIT (Your version number might be newer)
1.	Download GIT for Windows from https://git-scm.com/download/win
2.	Run the executable named Git-2.1.1.0-64-bit.exe
3.	Read the GNU General Public License and click Next.
4.	Accept the installation location.  Click Next.
5.	Accept the default components for installation.  Click Next.
6.	Create a shortcut.  Click Next.
7.	Adjust the PATH environment by selecting the option labeled Use Git from the Windows Command Prompt.  Click Next.
8.	Configure the line ending conversions by selecting Checkout Windows-style, commit Unix-style line endings. Click Next.
9.	Select Use MinTTY as the terminal emulator with Git Bash.  Click Next.
10.	Keep the default extra options Enable file system caching and Enable Git Credential Manager.  Click Next.
11.	Do not select any experimental options.  Click Install.
12.	Click Finish.
13.	Open a command prompt and change to C:\Program Files\Git\bin.  Type git --version
14.	You should see the response git version 2.11.windows.1

## Part 4:  Install cURL
1.	Create a folder named:  C:\curl
2.	Go to http://curl.haxx.se/download.html and download the following the zip file for the Win64 version of cURL:
Scroll to the Win64-Generic section.  Locate the latest Win64 ia64 zip version with SSL support. Click the version number to start the download.
3.	Save the zip file
4.	Unzip the downloaded zip file.  Move curl.exe to C:\curl
5.	Go to http://curl.haxx.se/docs/caextract.html  and download the digital certificate file named cacert.pem.
6.	Move cacert.pem to C:\curl.  Rename the file curl-ca-bundle.crt.
7.	Add C:\curl to the Windows PATH environment variable so the curl command is available from any location at the command prompt.
8.	Verify the installation is complete. Open a command prompt and enter curl https://www.google.com. The request returns the html in the command window.

## Part  5:  Install node.js (Your version number might be newer)
1.	Go to https://nodejs.org/en/
2.	There are two versions listed. Download the recommend version.
3.	Start the Windows installer package for node-v6.9.2-x64.msi.  Click Run.
4.	At the Welcome window, click Next.
5.	Accept the end-user license agreement. Click Next.
6.	Accept the destination folder.  Click Next.
7.	Accept any custom setup options. Click Next.
8.	Click Install.
9.	Click Finish when notified the installation was successful.
10.	Verify the installation.  At a command prompt, enter npm version
11.	You should see a JSON object like the following:


## Part  6:  Install API Connect

Use npm to install API Connect.
1.	Open a command prompt. Type npm install -g apiconnect.  This installation takes several minutes to complete.  You can ignore any warnings about deprecated packages.

## Part  7:  Install Docker (Your version number might be newer)

### For Windows 10
Install Docker for Windows.  Follow https://docs.docker.com/docker-for-windows   for specific directions.

If you have 64 bit Windows 7 or higher, follow these directions to install Docker with Toolbox.

1.	You must have virtualization enabled on your machine.  This might be an issue if you are running Windows 10.  However, if you are running Windows 7 or Windows 8, you must read and follow one set of these directions.

	### Windows 8 or 8.1
	Choose Start > Task Manager.  Navigate to the Performance tab.  Under CPU, you should see Virtualization: Enabled.
	If virtualization is not enabled, then follow the manufacturers documentation.  The steps to configure BIOS settings are specific to the hardware you have. It varies from one hardware manufacturer to another, and, even different models from the same manufacturer can have different steps.  Refer to the documentation or website for your hardware make and model.  Or, you can check on the Intel website for guidance from Intel about their VT-x product technology.
	### Windows 7
	You should check your system’s BIOS to see if hardware virtualization is enabled. If it is not enabled, enable it through the BIOS.
	You must run the Microsoft Hardware-Assisted Virtualization Detection Tool which can be found at `https://www.microsoft.com/en-us/download/details.aspx?id=592`

	a.	Download the MHAVDT.  Be sure to select havdetectiontool.exe and the user guide.
	b.	Run the detection tool by clicking havdetectiontool.exe
	c.	Accept the license agreement.  Click Next.
	d.	You should see a message This computer is configured with hardware-assisted virtualization.
	e.	Select No, I don’t want to send data.  Click OK.

2.	Follow https://docs.docker.com/engine/installation/windows/  and scroll down to the Docker Toolbox section.
3.	Click the link for Docker Toolbox  https://www.docker.com/products/docker-toolbox
4.	Click Download (be sure to click the Windows option, not the Apple option)
5.	Scroll down and find the Downloads section.  Click the latest DockerToolbox-1.12.3.exe version.
6.	Open the exe and save the file
7.	Run the DockerToolbox-1.12.3.exe
8.	At the Welcome screen, click Next. You can clear the checkbox to help improve Docker Toolbox.
9.	Accept the default destination folder.  Click Next.
10.	Accept the list of components.  Click Next.
11.	Accept the additional tasks (shortcut, add docker binaries to PATH, and upgrade Boot2Docker VM).  Click Next.
12.	Review settings and click Install.
13.	Clear the checkbox to view shortcuts.  Click Finish.
14.	Verify your docker installation.
	a.	From the Start Menu, navigate to All Programs >  Docker.
	b.	Click Docker Quickstart Terminal
	c.	There a number preliminary steps and downloads that must happen. Wait for a message indicating the interactive shell can start and the $ prompt is available.
	d.	Type docker run hello-world.
	e.	You should see a response starting Hello from Docker!
## Part  8: Install the Bluemix CLI
1.	Open a browser to https://console.bluemix.net/docs/cli/reference/bluemix_cli/all_versions.html#bluemix-cli-installer-downloads
2.	Scroll to the right to see the Windows downloads, and click the link for the latest Windows 64 bit
3.	Download and run the installer exe file.

## Part  9: Install the IBM Container Service plugins for the Bluemix CLI
1.	Open a browser to https://plugins.ng.bluemix.net/ui/repository.html
2.	Download and install the win64 plugins for container-registry and container-service.

## Part 10: Install the MYSQL Client
1. Open a browser to https://dev.mysql.com/downloads/mysql/
2. Download the ZIP Archive version of the latest Windows 64 bit MYSQL Installer. It shoud be approximately 320 MB.
3. When the ZIP archive is downloaded, extract it to the directory of your choice.
4. You will only need the mysql.exe executable. From the bin subdirectory under your extraction directory, move or copy the mysql.exe file to any directory in your PATH.

## Part 11: Install WebSphere Liberty Profile

1. Open a browser to https://developer.ibm.com/wasdev/downloads/download-latest-stable-websphere-liberty-runtime/
2. Click the link to download the latest stable version of the Liberty Web Profile. It will be a ZIP archive file.
3. Extract the ZIP archive wherever you want. You could extract it from the C:\ directory. It will create a directory whose name starts with wlp.

## Part 12: Install Eclipse

The labs are written to the Neon version of Eclipse. Since the behavior of Eclipse can vary with newer versions like Oxygen, we suggest that you install the Neon version, at least to use for the lab exercises.

1. Open a browser to https://www.eclipse.org/downloads/packages/release/neon/3
2. Click to download the Windows 64 bit version of Eclipse IDE for Java EE Developers. This will download a ZIP archive file.
3. Extract the ZIP archive file wherever you wish. You could extract it from the C:\ directory. It will create a directory called eclipse. You might want to make a shortcut for the eclipse.exe file in your Windows Task Bar.

## Part 13: Install Websphere Liberty and Bluemix developer tools for Eclipse

1. Use the eclipse.exe executable to start Eclipse. Click to close the Welcoem panel.
2. Open a browser to https://developer.ibm.com/wasdev/downloads/#asset/tools-WebSphere_Developer_Tools_for_Eclipse_Neon
3. Drag and drop the __Install__ button for WebSphere Application Server Liberty onto the Eclipse Toolbar, then follow the prompts to install the WebSphere Liberty tools.  
4. In Eclipse, under the Help menu, click __Eclipse Marketplace__. Search for __Bluemix__. Install the __IBM Eclipse Tools for Bluemix__.

## Part 14: Install Cygwin

There are certain times in the labs where the way that Windows interprets quote characters makes it easier for you to issue those commands from a Linux shell. You can have that Linux shell available by installing Cygwin.

1. Open a browser to https://www.cygwin.com/
2. Under the Current Cygwin DLL version heading, click to download the latest Windows 64 bit installation exe file.
3. Run the installation exe file and follow the prompts to install Cygwin.

## This completes the setup of your workstataion.
