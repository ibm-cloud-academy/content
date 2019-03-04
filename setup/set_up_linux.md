# Preparing a Linux machine or virtual machine for the Labs
This document provides the steps to install the software necessary for the lab exercises on a Linux machine. It can also be used to set up the software on a VMware Linux virtual machine.

If you are working with a native Linux machine and not a virtual machine, you can start with Step 4. You can also skip to Step 4 if you want to work with an existing Ubuntu virtual machine image.

1. Install VMware
2. Download the Ubuntu Operating System  
3. Create a virtual machine
4. Install curl
5. Install IBM Cloud Developer Tools
6. Install Java JDK 1.8  
7. Create JAVA_HOME environment variable  
8. Install node.js  
9. Install the MYSQL client

If you are going to create a Linux virtual machine on a Windows host, verify the following:  
1. make sure you have at least 22GB of available disk space (20GB for virtual disk and 2GB for the Ubuntu iso image).  
2. Make sure IntelVT-X is enabled . For example, on a Lenovo Thinkpad W530, in the BIOS select __Security > Virtualization > Enable Intel VT-X__.

## Step 1: Install VMware

1. In a browser, open [http://www.vmware.com/]( http://www.vmware.com).  
2. From the left navigation bar, Click the __DOWNLOADS__ link.
3. In the new window, click the link for __Workstation Pro__.
4. You see two download options, one for Windows 64-bit and one for Linux 64-bit. From the appropriate option, click __Go to Downloads__.
5. Download the installation file.
6. Install the VMware product with the default options.

## Step 2: Download the Ubuntu Operating System

1. In a browser, open [https://releases.ubuntu.com/16.04]( https://releases.ubuntu.com/16.04).
2. Click the __64-bit PC (AMD64) desktop image__ link.
3. Save the .iso file anywhere that is convenient. The file size is approximately 1.5 GB.

## Step 3: Create a virtual machine
You use the Ubuntu iso file as the OS in the VMware image. You create a new virtual machine, and point it to the iso file you just downloaded.

1. If VMware Workstation is not open, open it now.  
2. On the Home page, click the icon to Create a New Virtual Machine.  
3. In the dialog that opens, accept the default selection (__Typical__) and click __Next__.  
4. Click __Browse__ and search for the iso file.  
5. Select the iso file and click __Open__. If there is no problem with your downloaded file, you see the message __Ubuntu 64-bit 16.04.4 detected__.  
__NOTE:__ If there is a problem, you see the message __Cannot read this file__, and the __Next__ button is not active. Verify your download.  
6. Click __Next__.  
7. Enter the following information:

  + Full name: __IBMCloudCourse__  
  + User name: __localuser__  
  + Password: __passw0rd__ (and confirm)

8. Click __Next__.  
9. For default name type __microservices__.   
10. You can change the default location now if you want. Alternatively (as the comment in the dialog says) you can modify this later, when the virtual machine has been created.  
11. Click __Next__.  
12. If you are sure that this virtual image will not be moved to another computer, you can choose to store it as a single file (thus improving performance).  
13. Click __Next__.  
14. Verify the information shown in the summary, then click __Finsh__.  
15. Wait while the virtual machine is installed (files copied, language packs, and so on).   There will be several progress bars.
16. When prompted, enter the password.  
17. Remove some icons from the desktop that are not required for the exercises (there may be others; for clarity, remove what is not needed). Right-click and select __Unlock from Launcher__ :

  + LibreOffice Writer
  + LibreOffice Calc
  + LibreOffice Impress
  + Ubuntu Software
  + Amazon
  + FloppyDisk

18. Click the __Search your computer__ icon and type '__t__' in the search field.  
19. Click the __Terminal__ icon and verify that the Terminal opens.  
20. In the navigation bar to the left, right-click the __Terminal__ icon and select __Lock to Launcher__.  
21. Type __exit__ in the Terminal window. When it closes, verify that the icon remains on the navigation bar.  

The rest of the instructions apply to the image you have just created if you did that, or your native Linux operating system. Thus, 'In a browser...' means a browser on the image or on your native Linux system.

## Step 4: Install curl

1. Run the following command (At the message __Do you want to continue__, type __Y__):  
`sudo apt-get install curl`
2. When the installation is complete, verify that it was successful by typing  
`curl https://www.google.com`
3. Verify that the response is HTML for the Google home page.  
__NOTE__: If the response is __The document has moved__, then curl was successfully installed, but the url is not correct. According to your geography, you need to change the extension.

## Step 5: Install the IBM Cloud Developer Tools

1. Follow the instructions at: 
https://cloud.ibm.com/docs/cli/index.html#overview
to install the IBM Cloud Developer Tools.

## Step 6: Install Java JDK 1.8

1.	In a browser, open https://www.oracle.com
2.	In the list of menu options, click __Trials and Downloads__.
3.	Click __Java for Developers__.
4.	In the list, look for the newest version that starts with __Java SE 8__. At the time of writing, the newest version was Java SE 8u171. If your version is newer, make the appropriate adjustment in the commands that follow. In that section, click the __DOWNLOAD__ button under __JDK__ (Note: your minor version may be different)
5.	In the section that lists installation files for the various operating systems, click the __Accept License Agreement__ radio button at the top.
6. Select the __tgz__ file for Linux 64-bit (jdk-8u171-linux-x64.tar.gz).  
7. __Save__ the file.  

You now have the compressed file on your image. The next step is to move it to the correct location and unzip it.  

1. Create a directory for the file. In the Terminal, type the following:  
`sudo mkdir /usr/local/java`
2. Change to the download directory:  
`cd ~/Downloads`
3. You copy recursively (-r) the file in this directory to the location you want:  
`sudo cp -r jdk-8u171-linux-x64.tar.gz /usr/local/java`
4. Change to the new java directory:  
`cd /usr/local/java`
5. Verify that the tar.gz file was copied:  
`ls`
5. Unzip the file:  
`sudo tar xvf jdk-8u171-linux-x64.tar.gz`
6. Verify that the extraction was successful:  
`cd jdk1.8.0_171`  
`ls`  
You should see several directories, files, and zip files.

## Step 7: Create JAVA_HOME environment variable
You add JAVA_HOME to the PATH by editing the profile file.  

1. Open the __/etc/profile__ file in an editor:  
`sudo gedit /etc/profile`
2. __Add__ these lines to the bottom of the file:  
`JAVA_HOME=/usr/local/java/jdk1.8.0_111`  
`PATH=$JAVA_HOME/bin:$PATH`  
`export JAVA_HOME`  
`export PATH`  
3. __Save__ and __close__ the profile file.  

The final step is to provide the information about the new PATH to the system. You do this with three update-alternative commands for Java, javac, and javaws:  

1. Update the java information (the final argument is the priority):  
`sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.8.0_171/jre/bin/java" 1`
2. Update the compiler information:  
`sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.8.0_171/bin/javac" 1`
3. Update the javaws information:  
`sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/local/java/jdk1.8.0_171/bin/javaws" 1`
4. Verify that your installation of Java is recognized. Type:  
`java -version`
5. You should see information about the java version, Java runtime, and Java HotSpot.

## Step 8: Install node.js
Ubuntu includes Node.js in its default repositories.  The version that was used for this installation was __4.2.6__. Your version might be different.

1. Install it by typing the __apt install__ command (At the message __Do you want to continue__, type __Y__):  
	`sudo apt install nodejs-legacy`
2. Verify the installation:  
`node -v`  js
3. The response is the version number (for example, v4.2.6).
4. Install the Node Package Manager (npm) (at the message __Do you want to continue__, type __Y__):  
`sudo apt install npm`
5. Verify the installation:  
`npm version`
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

## Step 9: Install the MYSQL client
You can install MYSQL version 5.7 client using apt.
1. Type
`sudo apt install mysql-client-5.7`

This completes the setup tasks for Linux.
