# Preparing a Windows 7 machine for the Labs

If you are using Windows 10, the preferred environment for the labs is to use `Windows Subsystem for Linux`. Follow the instructions at the link below to set up your Windows 10 workstation for the lab exercises.

[Setting up Windows 10 for the lab exercises](https://ibm-cloud-academy.github.io/set_up_windows10.html)


This document provides the steps to install the software required to begin the exercises on a Windows 7 machine.  Exceptions have been noted for Windows 8 and Windows 10. The sequence is as follows:

1. Install cURL
2. Install the IBM Cloud Developer Tools
3. Install Java JDK 1.8
4. Add JAVA_HOME variable to the System PATH
5. Install Gradle
6. Install node.js
7. Install Cygwin

## Step 1:  Install curl
1. Create a folder named:  __C:\curl__.
2. Go to http://curl.haxx.se/download.html and download the zip file for the Win64 version of cURL:
Scroll to the __Win64-Generic__ section.  Locate the latest Win64 ia64 zip version with SSL support. Click the version number to start the download.
3. Save the zip file.
4. Unzip the downloaded zip file.  Move __curl.exe__ to __C:\curl__.
5. Go to http://curl.haxx.se/docs/caextract.html  and download the digital certificate file named __cacert.pem__.
6. Move __cacert.pem__ to __C:\curl__.  Rename the file __curl-ca-bundle.crt__.
7. Add __C:\curl__ to the Windows PATH environment variable so the curl command is available from any location at the command prompt.
8. Verify that the installation is complete. Open a command prompt and enter `curl https://www.google.com`. The request returns the html in the command window.

## Step 2: Install the IBM Cloud Developer Tools

1. Follow the instructions at [Getting started with the IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview) to install the IBM Cloud Developer Tools.

## Step 3: Install Java JDK 1.8

1. In a browser, open https://www.oracle.com
2. In the list of menu options, click __Downloads and Trials__.
3. Click __Java for Developers__.
4. In the list, look for the newest version that starts with __Java SE 8__. At the time of writing, the newest version was Java SE 8u171. In that section, click the __DOWNLOAD__ button under __JDK__ (Note: your minor version may be different)
5. In the section that lists installation files for the various operating systems, click the __Accept License Agreement__ radio button at the top.
6. Select the .exe file for Windows x64 (__jdk-8u171-windows-x64.exe__).  The file is downloaded to the machine's Download directory.
7. Run the Windows executable.  Navigate to the Download directory. Double click __jdk-8u171-windows-x64.exe__.
8. At the Welcome screen, click __Next__.
9. Accept the features to install.  Accept the default install location __C:\Program Files\Java\jdk1.8.0_171__.  Click __Next__.
10. Upon successful installation, click __Close__.
11. Verify that the installation was successful.  Open a command prompt.  Change directories to __C:\Program Files\Java\jdk1.8.0_171__. You should see 6 directories, 6 files, and 2 zip files.

## Step 4: Add JAVA_HOME variable to the System PATH  

Add JAVA_HOME to the Path by editing an environment variable.

1. Add or modify the __JAVA_HOME__ environment variable to the value __C:\Program Files\Java\jdk1.8.0_171__ (or whatever version you installed).
2. Add __JAVA_HOME__ to the end of the __Path__ system variable.
3. Close the Environment Variables window.
4. Restart the computer.
5. Verify that your installation of Java is recognized. Open a command prompt and type:
`java -version`.
6. You should see information about the Java version, Java runtime, and Java HotSpot.

## Step 5: Install gradle
1. In your browser, go to https://gradle.org/install/.
2. Follow the instructions for Windows installation. For most users, the instructions in the __Install manually__ section will be the easiest to follow.

## Step 6:  Install node.js
1. Go to https://nodejs.org/en/
2. There are two versions listed. Download the recommended version, which will be an msi installer file.
3. Run the msi file and install with the default options.
4. Verify the installation. At a command prompt, type `node -v`. The response is a version number.
5. Type `npm -v`. The response is a version number, along with a notice about any updates that are available.

## Step 7: Install Cygwin

There are certain times in the labs where the way that Windows interprets quote characters makes it easier for you to issue those commands from a Linux shell. You can have that Linux shell available by installing Cygwin.

1. Open a browser to https://www.cygwin.com/
2. Under the Current Cygwin DLL version heading, click to download the latest Windows 64 bit installation exe file.
3. Run the installation exe file and follow the prompts to install Cygwin.

This completes the setup tasks for Windows.
