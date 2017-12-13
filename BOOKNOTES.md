# Final-CSCI-2461-70
##*Attendence*
######Dates:
8/23 present 
8/30 present 
9/9 present 
9/20 present 
9/27 present 
10/4 present 
10/11 present 
10/18 present 
10/25 present 
11/1 present 
11/8 present 
11/15 present 
11/22 present 
11/29 present 
12/6 present 
12/13 present 

# Booknotes 
Chapter 1 | chapter 2 
Angela Griffin  
CSCI 2461  
8/25/17 
 
Chapter one notes: 
Lever and level – Classification or grouping. 
0110.0001.1011 are states. 
4 General System Areas.  
Process  
Memory  
Device Drivers  
System calls  
Context Switch – The act of one process giving up control of the CPU to another process.  
Page Table – The implementation of a memory address map.  
 
Fork () - kernel creates identical copy of the process. 
Ex| cel () - Kernel states the program replacing the current process. 
Kernel space- Is the area only the Kernel can access. Where all the work gets done.  
User space – refers to the parts of main memory that the user processes can access. If in User world and system crashes not a big deal. But if the system crashes in Kernel world you will lose everything and disrupt the entire system.  
The Kernel's Subdivisions 
System calls 
Process Management 
Memory Management  
Device Drivers 
User space refers to the memory for the entire collection of running process real action of Unix happens here.  | Angela G 
Csci2461  
Chapter 2 book notes  
9/4/17  
Basic Commands & Directory Hierarchy 
The Bourne shell: /bin/sh. 
Shell- is a program that runs commands like the one that users enter also a small programming environment.  
Shell scripts- text files that contain a sequence of shell commands. 
/bin/sh. Every version of linux. 
Cats- simply outputs that contains one or more files. 
I/O streams to read and write data. Process read data from the input streams and write data to output streams.  
Standard output = stdout 
Standard input = stdin 
Standard error 
Ls- list contents of the directory 
-l = detailed ( long )  
-f = display file type information  
Cp = copies files  
Mv = move remains a file, also move a number of files to a different directory. 
Dir = directory 
Touch = creates a file if already created then becomes modified.  
Rm = remove or delete a file. 
Echo = prints arguments to standard output.  
Directory Hierarchy starts with /  
/ = root directory 
/ = path or pathname 
/usr 
.. = identify as the parent of the directory  
. = refers to the current directory.  
A path not starting with / is called relative path 
Cd = current directory  
Mkdir = creates a new dir 
Rmdir = removes the dir 
Rm –f = deletes all files and subdirectories and its contents. 
-r = recursive delete 
-f = forces the delets operation 
Globbing = simple patterns to file and directory names. 
*= matches any number of arbitrary characters  
Expression = the shell subdirectories all matching file names. 
-I = case sensitive matches 
-v = inverts the search prints all that don’t match. 
Less = comes in handy when files are too long.  
Space bar = forward 
B – skip back 1 page 
q- quit 
diff = differences between two text files 
head= shows first 10 lines of a file 
tail = shows last 10 lines of a file.  
Sort = lines of text files in alphanumeric order. 
Password = change password  
( .  ) = dot file 
Shell variables = contains values of text strings assign value to shell var  
Vi = text editor  
Man = manual pages  
-k = search by keyword 
Info = looks further 
>= redirectgion character 
>>= redirection of syntax 
TTY = terminate device where the process is running. 
STAT= statues, what its doing and where is the memory.  
TIME = amount of CPU time mins and seconds that the process has used so far.  
Ps x – all running process 
Ps ax – all process running on the system 
Ps u – more detailed info on process 
Ps w- full command names 
Kill = terminate process 
-stop = process still in memory  
Permissions: read, write, execute 
g- group 
-r – get rid of 
Absolute- sets all permissions bits at once.  

Chapter 3 | chapter 4 | chapter 5 | chapter 6 & 7 | Chapter 8 & 9 | chapter 10 
Angela Griffin 
csci2461
Chapter 3 booknotes
udev system. enable users space programs to automaticall configure and use devices.
Device nodes- I/O interface process files. 
File device characters 
- b = block, - c = character, - p = pipe, - s = socket
* programs access data from a block device in fixed chunks 
*character devices work with all data streams.
*Pipe devices- use charaters devices with another process at the other end of the I/O stream instead of a kernel driver.
sockets- are special purpose interface that are frequenlty used for interprocess communication.
Base path for sys = /sys/devices
short cuts :/sys/block of a fixed size.
dd options include: 
- if = file - input file
- of = file - the output file
- bs = size - the block size ex.s bs = 1k and bs = 1024
count = num - total number of blocks to copy
skip = num - skip past the first number blocks in the input file or stream and do not copy them to the output. 
command mount = check output
sd = hard disk ( SCSI, small computer system interface ) 
scsils = list scsi contents
Terminals- are devices for moving characters between a user process and an I/O device, usually for text output to a terminal server. 
serial ports- /dev/ttys*
paraellel ports- /dev/1p0, and /dev.1p1
audio devices- /devv/snd; /dev/dsp/dev/audio
mknod- creates one device
MAKEDEV- creates groups of devices
devtmps- problem of device avaiablitiy during boot.  
| CSCI 2461-70 Griffin, A.N. 2017-9-11 
Chapter 4 book notes 
Disk and file systems 
Layer 1 – Partitions = subdivisions of the whole disk. Place on partition table.  
Layer 2 – Filesystem = data of files 
MBR Master Boot Records 
Parted = a text base tool that supports both MBR and GPT  
Gparted = a graphical version of parted  
Pdisk = the traditional text based Linux disk partioning table. Does not support GPT. 
Gdisk = a version of fdisk that supports GPT but not MBR 
Primary partition = is a normal subdivision of the disk  
Partition  
Dmesg 
Udevadm = kernel event changed 
Blockdev 
Ssd = solid state disk 
VFS = virtual file system  
File system types: ext4, ext3, ISO 9660, FAT, HFS, ext2  
Mkfs utility – can create many types of file system. Super block back numbers 
Mounting – process of attaching files.  
mount point – place in current sys dir hierarchy where the file system will be attached  
Mount  
-t = type option 
Unmount = detach file system 
UUID = universal unique identifier 
Blkid 
Sync  
-r option = mounts file system in read only 
-n option = ensures that mount does not try to update the system runtime mount database. 
Exec, noexc = enables or disables set uid programs  
Ro = mounts file systems in read only mode 
Rw = mounts file systems in read and write mode 
Df 
Du –s = turns on summary mode 
Fsck = checks file system 
-p = fixes problems automatically 
-n = check file system without modification 
-b = num replace the computed superblock backups number without destroying data. 
Debugs = tools allow you to look through the files on a file system in read only mode. 
Swapping = disk area used to store memory pages. 
Mkswap dev = puts a swap signature on the partition 
Swapoff = remove a swap partition of file from the kernels active pool | CSCI 2461-70 Griffin, A.N. 2017-9-11 
Ch. 5 book notes 
Boot Process 
BIOS, or boot firmware loads and runs boot loader 
Boot loader finds kernel image on disk, loads it into memory and starts it.  
The kernel initializes the device and its drivers 
The kernel mounts the root file system 
The kernel starts a program called init with a process ID of 1. This point is the user space start. 
Init sets the rest of the system processes in motion. 
At some point init starts a process allowing you to log in, usually at the end or near the end of the boot. 
Kernel initialization and boot option order 
CPU inspection 2. Memory inspection 3. device bus discovery 4. device discovery 5. auxiliary kernel subsystem setup 6. root file system mount 7. user space start 
Kernel parameters = tells the kernel how it should start. Use /proc/cmdline 
Root parameter = instructs the kernel to mount the root file system in read only mode upon user space start.  
Boot loader = starts the kernel 
Select multiple kernels 
Switch between kernel parameters  
Allows users to manually edit kernel images name and parameters 
Provides support for booting other OS.  
Types of boot loader 
Grub, Core boot, Lilo, SysLinux 
Grub = file system navigating that allows for much easier kernel iamge and configuration selection. 
To activate press and hold shift when you BIOS or firmware startup screen appears first. 
Press e to view the boot loader configuration commands for the default boot option 
Unux – while in grub grub.cfg = central configuration file 
.mod suffix = loadable modules  
Grub – mk config  | CSCI 2461-70 Griffin A.N. 2017-9-19 
 
Chapter 6 book notes 
Init = first user space process where CPU and memory ready for normal system operation 
User space start order 
Init 
Essential low level service such as udevd and syslogd 
Network configuration 
Mid and high level 
Login prompts GUI's and other high-level applications 
 
Init main purpose is to start and stop the essential service processes on the system, and more. 
3 Major Implementations of init 
Sytem v int- not in common use. 
Sysemd – the standard init for all mainstream Linux distributions 
Upstart- The init on Ubuntu installations prior to version 15.04 
Android = BSD init  
Systemd 
Goal orientated  
Satisfies the dependencies and resolves the target  
Defer the start of a service until it is absolutely needed.  
Upstart  
Reactionary 
Receive events, based on events, runs jobs that turn produce more events, runs more jobs. 
A script run a deamon program which detaches itself from the script and runs auto-enormously  
Both systemd and upstart offer some system V background compatibility. Both support the concept of run levels.  
Who –r = check your systems run level  
Run level purpose = (Becoming out of date )  
System startup 
Shutdown 
Single user mode 
Console mode states 
Types of init and versions  
/usr/lib/systemd ; /etc/systemd = systemd 
/etc/init (.conf) files = upstart 
/etc/inittab = system V init 
 
Systemd incorprates Unix service such as 
Cron  
Inetd 
Systemd Boot Process 
Systemd loads its config 
Systemd determines its boot goal, usually ( default. Target ) 
Systemd determines all dependencies of default boot goal 
Systemd activates the dependencies and the boot goal 
After boot, systemd react to system events, and activate additional components.  
Systemd can also mount filesystems, monitor network sockets, runtimes and more.  
Unit types 
Service units 
Mount unit 
Target units 
Types of Dependency 
Requires- strict 
Wants – activation only 
Requisite – must already be active 
Conflicts – negative dependencies 
Before = current unit will active before the listed units 
After = the current unit activates after the listed units. 
 
Systemd configuration files are spread among many directories across the system  
System unit directory 
System configuration directory  
SShd.service = secure shell login shows use of variables 
$OPTIONS – are options that you can pass to ssh when you activate the unit with systemtl 
$MAINPID – is the trained process of the service 
Specifier = is another variable like feature often found in unit files (% )  
Task jobs – with a clear end 
Service jobs – have no defend stop 
Abstract job – exist only in Upstart and start nothing by themselves. But they are sometimes used as management tools for other jobs. | CSCI 2461-70 Griffin, A.N. 2017-09-27 
Chapter 8 book notes  
3 basic hardware resources  
CPU 
Memory 
I/O 
Ps command - kist running on your system at a particular time. 
Top command 
Spacebar = updates display immediately 
M = sort by current resident memory usage  
I = sort by total cumulative CPU usage 
P = sort by currant CPU usage ( the default )  
U = display only one users process 
F= selects different statistics to display 
? = display a usage summary for all top commands 
Atop, htop 
Lsof = list open files and the process using them. 
Cwd = current working directory 
System call – is a privileged operation that a user space process to ask the kernel to perform such as opening and reading data from a file.  
 Strace utility prints all the systen calls that a process makes  
 
Open = opens a file  
-l = signals and error 
Missing files are the most common problem with Unix programs  
1 trace = tracks shared library calls 
Threads = Linux process that are divided. 
All threads inside a single process share their system resources and some memory. 
Single thread – a process with one thread  
Multithread – a process with more than one thread  
Starting thread is called the main thread.  
Threads start faster than processes  
Top –p = monitor one or more specific processes over time  
User time – the number of seconds that the CPU has spent running the programs own code 
System time- How much time the kernel spends doing the process work 
Elapsed time – the total time it took to run the process from start to finish including the time that the CPU spent doing other tools 
Priority – which is a number between –20 and 20  
Nice value NI – gives a hint to the kernel  
Renice  - changes the nive value  
The load average – is the average number of processes currently ready to run.  
Trash – rapidly snap memory for processes to and from the desk. 
Pages – kernell assist the MMu by breaking the memory used by processes into smaller chunks  

CSCI 2461-70 Griffin A.N. 2017-09-2 
Chapter 9 book notes  
Network layer – stack on top of each other in order to form a computer system 
Packets – a computer transmits data over a network in small chunks. 
Consists of two parts headers and payload 
Network Layer  
Application layer 
Transport Layer  
Network of Internet Layer 
Physical layer 
Subnet – is a connected group of hosts with IP address in some sort of order. 
Ping – sends ICMP echo's request packets to a host that ask a recipient host to return the packet to the sender.  
Ifconfing command – outputs include the Internet and the Physical layer.  
Kernel = network interface  
Deleting routes  
Ex. Route del –net default  
Adding routes  
Ex. Route add –net 192.168.45.0/24 gw 10.23.2.44 
OpenWRT netifd Network management 
The second configuration level is a more specific list of connections: hardware device, and additional physical and network configuration parameters.  
 Dhclient = to get Internet layer config tools from locally attached physical network.  
General config directory for Network Manager is usually /etc/networkmanager. 
/etc/host 
Resolv.conf 
 
Local host  
Transport layer: TCP, UDP, and services | CSCI 2461-70 Griffin, A.N. 2017-10-04 
Clients connect to corresponding network server. 
Config file – controls behavior of a server  
Syslog = mesasge logging   
Transport layer = TCP , UDP, protocols  
TCP - two way data streams – port 80 
e. telenet www.wikipedia.org 80 
GET/ HTTP/1.0 
HTTP = hyper text Transfer Protocol 
Curl command 
Debugging output 
Sends header request 
Talks to the OS 
2 byte chunks in the middle signifies the end of the headers in HTTP 
Network servers 
Interact with the network ports  
Ex. Http, apache, apache2 : web browser 
      Sshd: secure shell daemon 
     Postfix, qmail, sendmail: mail servers 
     Cupsd: print server 
     Nfsd, mountd: nertwork filesystem ( file sharing )  
     Rpcbind: remote procedure call ( RPC ) portmap service daemon 
Fork () creates a new child process, which are responsible for the new connection,  
Child = worker process, terminates when the connection is closed. 
SSH 
Standard for remote access to Unix Machine 
Allows secure shell logins 
Remote program execution  
Simple filesharing 
Encrypts passwords, tunnel other network connections. 
Use key for host authentication  
Sshd = configure file and host key 
Host key – 3 host key set 
1 key for protovol version 1 
2 keys for protocol 2 
Each set has a public key 
Ssh – gen key – helps you create  a key 
Ssh_known_host = contains public keys from other host. 
