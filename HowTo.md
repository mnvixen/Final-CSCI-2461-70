How to: 
Show experience with the Linux command line 
In your Front Matter Page, Start with the Item (Question, Exercise, Project) Number and your Expected Points. 
Use the following as guidelines for headers and content as appropriate. 
Under a “Command” (C.) header, put the short name followed by the long name from the manual. Copying directly from the book is acceptable. 
Under the “Description” (D.) header provide a short but informative explanation of the command. Cite your sources. 
Under a “Output” (O.) header, show output from the command with various flags 
Under the “Reference” (R.) header, provide references to the operation of the command 
The following provides an example. 
C.1 – 1 pt 
df “display free disk space” 
D.1 – 1 pt 
“The df utility displays statistics about the amount of free disk space on the specified filesystem or on the filesystem of which file is a part.” [1] 
O.1 – 1 pt 
mjh at neutron in ~ 
$ df -h 
Filesystem Size Used Avail Capacity iused ifree %iused Mounted on 
/dev/disk1 112Gi 105Gi 6.5Gi 95% 1701960 4293265319 0% / 
R.1 – 1 pt 
Debian 7.7 Manual Page [1] 
1. Torbjorn Granlund, David MacKenzie, and Paul Eggert "man page for df (debian section 1)" GNU coreutils 8.12.197-032bb., September 2011. Accessed September 5, 2017. url:www.unix.com/man-page/debian/1/df/ 
