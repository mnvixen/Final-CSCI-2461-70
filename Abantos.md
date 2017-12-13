Angela Griffin 
11/6/2017 
CSCI-2461 
Package Management Notes 
 
Sudo apt-get  
Used acptool –replacement of apmtool. For laptop users. 
Used afflib- dpg- on-disk format for storing complete forensic information: sudo apt-get install afflib-dbg, allows files to be digitally signed, chain-of-custody and long-term file integrity. Allows disk images containing privacy sensitive material to be stored on the Internet. Posix stricpting (Linux coding). 
Used balsa-dbg: get sudo apt-get install balsa-dbg. Mail client from GNOME desktop. Supports both POP3 and IMAP.  
Used cython3-dbg: sudo apt-get install cython-dbg. Libraries built against versions of Python configured with pydebug. Allows python configuration. 
; /etcldibbler/client.conf w/new version. DHCPv6 clients: sudo apt-get install dibbler-client 
Used sudo apt-get install DVd+rw-tools-dbp 
Used sudo apt-get update 
Used sudo apt-get install build-essential [ press tab twice] save files and execute.  
Used sudo apt-get install enigma 

 
Elive Linux System Administrator 
 
1. Boot process and Troubleshooting 
 
    1. ls (The ls command in grub will list the different partitions that are available. ) 
    2. set root=(hd0,3) this declares your boot partition. 
 
2. System logging commands 
       Linux loggs by default are in /var/log 
       Use less or cat to read logs, less is preferred 
 
3. Disk Management and File System.  
 
   sudo fdisk -l 
   sudo parted -l 
 
4. Managing users and group 
   useradd vs adduser 
 
5. Linux Networking 
   sudo ifconfig interface  
    
   sudo ifup int_name 
   sudo ifdown int_name 
 
6. Processes and Job Management 
    ps –aux 
    top 
 
 
 
7. Creating Viewing and Editing files 
   Nano, Pico, Joe 
   or more powerful ones like vi 
 
 
8. Installing and Updating Software Packages 
        sudo apt-get update 
        sudo apt-get install 
        sudo dpkg -i pack.deb 
         
 
    
 
10. Network Storage and Management 
    nfs and smb 
 
11. Service Configuration 
       service ssh start 
       service ssh stop 
 
12. Shell script 
    remember bash shell scripts files always start with 
    #!/bin/bash 
    you run them with ./fileName or sh fileName 
   
 
13. General task 
 
    cd ~  --go back to home directory 
    cd ..  go back up one level 
    cd -  go back to previous directory 
 
    pwd  find out where you're at 
    ls   list current directory contents 
    mkdir create a directory/folder 
    rmdir delete an empty directory 
    rm -r delete a directory with contents 
    cp    copy file or directory 
    cat   read file contents 
    grep search for file contents 
    find search for a file anywhere in the system 
    
    Angela Griffin  
11/6/2017 
CSCI-2461-70 
Debian 6.1 - 6.2 
 
6.1 Complete (re)build 
You must first install build-essential 
-referred to section 4.1 control 
For: 1. build-Depends  
              2. build-Depends-indep 
Next you: issue command 
 $ dpkg-buildpackage -us –uc 
This command makes full binary and source packages 
Commands:  
Debian/rules clean = cleans 
Dpkg-source –b = builds source pkg 
Debian/rulesbuild = builds programs 
Fakeroot debian/rules binary = builds binary pkg 
.dsc = makes .dsc files 
Dpkg = gen changes = changes .change files 
After:  
Give private GPG key to .dsc and .changes files use command debsign, enter secret pass phrase twice. 
-gentoo_0.9.12.orig.tar.gz 
Parent directory 
-gentoo_0.9.12-1.dsc 
Source code generated from the control file  
-gentoo_0.9.12-1debian.tar.gz  
Contains debian directory contents  
-gentoo_0.9.12-1_i386.deb 
Complete binary package  
-gentoo_0.9.12-1_i386.changes 
All changes made in current package revision 
GPG signature – proof that files are really yours, using public GPG key.  
 
6.2 AutoBuilder  
Archetecture: ensures installation 
Commands issued:  
 Clean 
Build 
fakeroot debian/rules binary-arch 
Sign cource .dsc file using gpg 
Create and sign the upload, changes file 
 
Lee Vang 
Chapter 6.3 debuild command 
Debuild command is the tool that users can create all the necessary files under the Debian package. debuild can run along with dpkg-buildpackage command. After running this type of command, debian will carry the lintian for checking any unwanted and bug file. For user to rebuild a new user account, use the debian command alone. For user to clean the source tree, use the $ debuild clean command. 
Pbuilder package 
6.4 
Allen Zarr   
Debian pbuilder packaging is a procedure driven system, it is a significant aid in determining whether a given build issue is a bug in the implementation of the builder or a problem with the package being built to have multiple implementations of a build system. In order to maintain this, the leading build systems must all have strong backers supporting them, in the essence of collaborative competition towards ensuring that we have the most correct available implementations of policy. 
So precisely which packages are pulled to satisfy build-dependencies or how they are pulled, the precise mechanism by which the various targets in debian/rules are called, may differ, causing some slight differences in behavior in very specific cases for certain packages. Most of the time this represents a bug in one or the other implementation, and sometimes reflects a lack of clarity in packaging policy in any case, behavior changes ought to be resolved. 
            However, from my understanding is that pbuilder development initially focused on the needs of the develop as end-user and sbuild development initially focused on the needs of build and archive administrator’s. Recently, these focuses have switched, as people have built archive management systems based on pbuilder, and more helpful developer tools using sbuild 
In summary, pbilder and sbuilder are best tools administrators are comfortable using for the sort of work they do in the Linux world. 
 
 
Yee leng Xiong 
6.5 Git-buildpacking Command and Similar 
Requirement: 
If using code management system (VCS) 
git-buildpackage: a suite to help with Debian packages in Git repositories. 
svn-buildpackage: helper programs to maintain Debian packages with Subversion. 
cvs-buildpackage: a set of Debian package scripts for CVS source trees. 
This makes merging and cherry-picking upstream patches easier. 
Git-buildpackes is becoming poplar for developers to manage Debian. 
 
This link below will show you what is new in the patches and what will be in the upcoming patches. http://alioth.debian.org/ 
Structure: 
 main for Debian package source tree. 
upstream for upstream source tree. 
pristine-tar for upstream tarball generated by the --pristine-tar option. 
Formatting: 
Theses commands automate packing activites 
git-import-dsc(1): import a previous Debian package to a Git repository. 
git-import-orig(1): import a new upstream tar to a Git repository. 
git-dch(1): generate: the Debian changelog from Git commit messages. 
git-buildpackage(1): build Debian packages from a Git repository. 
git-pbuilder(1): build Debian packages from a Git repository using pbuilder/cowbuilder. 
Process: 
Building Debian Packages with git-buildpackage (/usr/share/doc/git-buildpackage/manual-html/gbp.html) 
 
6.6. Quick rebuild 
Awil B. 
With a large package, you may not want to rebuild from scratch every time while you're tuning details in debian/rules. For testing purposes, you can make a .deb file without rebuilding the upstream sources like this[75]: 
$ fakeroot debian/rules binary 
Or simply do the following to see if it builds or not: 
$ fakeroot debian/rules build 
 
Chapter 6.7  
Roxanne  
of Debian’s Command hierarchy is sort of like a social structure but for commands and controls. The commands displayed within chapter 6.7 are used to construct many packages together, in order to combine into one big command. Although there is a certain rank between the commands, every command holds its own purpose and duty; some basic commands are used to back up and uphold the structure of the whole package for higher level commands. Commands are used to build, move and complete a task at hand quickly and easily. There many commands are still being worked and many are complicated to work with on different systems. You’ll sometimes reach restricted updates that will prevent you from configuring or stabilizing you package. Whether you use high level or basic commands they both are there to ensure a steady process of building a package. That will conclude chapter 6.7 notes on Debian’s Command Hierarchy. 



Angela Griffin  
11/6/2017 
CSCI-2461-70 
Debian 6.1 - 6.2 
 
6.1 Complete (re)build 
You must first install build-essential 
-referred to section 4.1 control 
For: 1. build-Depends  
              2. build-Depends-indep 
Next you: issue command 
 $ dpkg-buildpackage -us –uc 
This command makes full binary and source packages 
Commands:  
Debian/rules clean = cleans 
Dpkg-source –b = builds source pkg 
Debian/rulesbuild = builds programs 
Fakeroot debian/rules binary = builds binary pkg 
.dsc = makes .dsc files 
Dpkg = gen changes = changes .change files 
After:  
Give private GPG key to .dsc and .changes files use command debsign, enter secret pass phrase twice. 
-gentoo_0.9.12.orig.tar.gz 
Parent directory 
-gentoo_0.9.12-1.dsc 
Source code generated from the control file  
-gentoo_0.9.12-1debian.tar.gz  
Contains debian directory contents  
-gentoo_0.9.12-1_i386.deb 
Complete binary package  
-gentoo_0.9.12-1_i386.changes 
All changes made in current package revision 
GPG signature – proof that files are really yours, using public GPG key.  
 
6.2 AutoBuilder  
Archetecture: ensures installation 
Commands issued:  
 Clean 
Build 
fakeroot debian/rules binary-arch 
Sign cource .dsc file using gpg 
Create and sign the upload, changes file 
 
Lee Vang 
Chapter 6.3 debuild command 
Debuild command is the tool that users can create all the necessary files under the Debian package. debuild can run along with dpkg-buildpackage command. After running this type of command, debian will carry the lintian for checking any unwanted and bug file. For user to rebuild a new user account, use the debian command alone. For user to clean the source tree, use the $ debuild clean command. 
Pbuilder package 
6.4 
Allen Zarr   
Debian pbuilder packaging is a procedure driven system, it is a significant aid in determining whether a given build issue is a bug in the implementation of the builder or a problem with the package being built to have multiple implementations of a build system. In order to maintain this, the leading build systems must all have strong backers supporting them, in the essence of collaborative competition towards ensuring that we have the most correct available implementations of policy. 
So precisely which packages are pulled to satisfy build-dependencies or how they are pulled, the precise mechanism by which the various targets in debian/rules are called, may differ, causing some slight differences in behavior in very specific cases for certain packages. Most of the time this represents a bug in one or the other implementation, and sometimes reflects a lack of clarity in packaging policy in any case, behavior changes ought to be resolved. 
            However, from my understanding is that pbuilder development initially focused on the needs of the develop as end-user and sbuild development initially focused on the needs of build and archive administrator’s. Recently, these focuses have switched, as people have built archive management systems based on pbuilder, and more helpful developer tools using sbuild 
In summary, pbilder and sbuilder are best tools administrators are comfortable using for the sort of work they do in the Linux world. 
 
 
Yee leng Xiong 
6.5 Git-buildpacking Command and Similar 
Requirement: 
If using code management system (VCS) 
git-buildpackage: a suite to help with Debian packages in Git repositories. 
svn-buildpackage: helper programs to maintain Debian packages with Subversion. 
cvs-buildpackage: a set of Debian package scripts for CVS source trees. 
This makes merging and cherry-picking upstream patches easier. 
Git-buildpackes is becoming poplar for developers to manage Debian. 
 
This link below will show you what is new in the patches and what will be in the upcoming patches. http://alioth.debian.org/ 
Structure: 
 main for Debian package source tree. 
upstream for upstream source tree. 
pristine-tar for upstream tarball generated by the --pristine-tar option. 
Formatting: 
Theses commands automate packing activites 
git-import-dsc(1): import a previous Debian package to a Git repository. 
git-import-orig(1): import a new upstream tar to a Git repository. 
git-dch(1): generate: the Debian changelog from Git commit messages. 
git-buildpackage(1): build Debian packages from a Git repository. 
git-pbuilder(1): build Debian packages from a Git repository using pbuilder/cowbuilder. 
Process: 
Building Debian Packages with git-buildpackage (/usr/share/doc/git-buildpackage/manual-html/gbp.html) 
 
6.6. Quick rebuild 
Awil B. 
With a large package, you may not want to rebuild from scratch every time while you're tuning details in debian/rules. For testing purposes, you can make a .deb file without rebuilding the upstream sources like this[75]: 
$ fakeroot debian/rules binary 
Or simply do the following to see if it builds or not: 
$ fakeroot debian/rules build 
 
Chapter 6.7  
Roxanne  
of Debian’s Command hierarchy is sort of like a social structure but for commands and controls. The commands displayed within chapter 6.7 are used to construct many packages together, in order to combine into one big command. Although there is a certain rank between the commands, every command holds its own purpose and duty; some basic commands are used to back up and uphold the structure of the whole package for higher level commands. Commands are used to build, move and complete a task at hand quickly and easily. There many commands are still being worked and many are complicated to work with on different systems. You’ll sometimes reach restricted updates that will prevent you from configuring or stabilizing you package. Whether you use high level or basic commands they both are there to ensure a steady process of building a package. That will conclude chapter 6.7 notes on Debian’s Command Hierarchy. 
