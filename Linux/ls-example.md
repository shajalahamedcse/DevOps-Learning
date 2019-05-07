### Open Last Edited File Using ls -t

`ls -t` sorts the file by modification time, showing the last edited file first. `head -1` picks up this first file.

    $ vi first-long-file.txt
    $ vi second-long-file.txt
    
    $ vi `ls -t | head -1`
[Note: This will open the last file you edited (i.e second-long-file.txt)]



2. Display One File Per Line Using `ls -1`
To show single entry per line, `use -1 `option as shown below.


    $ ls -1
    
    bin
    boot
    cdrom
    dev
    etc
    home
    initrd
    initrd.img
    lib
    
    
    
3. Display All Information About Files/Directories Using ls -l
To show long listing information about the file/directory.


    $ ls -l
    -rw-r----- 1 ramesh team-dev 9275204 Jun 13 15:27 mthesaur.txt.gz
    
    
1st Character – File Type: First character specifies the type of the file.
In the example above the hyphen (-) in the 1st character indicates that this is a normal file. Following are the possible file type options in the 1st character of the ls -l output.
Field Explanation
– normal file
d directory
s socket file
l link file

Field 1 – File Permissions: Next 9 character specifies the files permission. Each 3 characters refers to the read, write, execute permissions for user, group and world In this example, -rw-r—– indicates read-write permission for user, read permission for group, and no permission for others.

Field 2 – Number of links: Second field specifies the number of links for that file. In this example, 1 indicates only one link to this file.
Field 3 – Owner: Third field specifies owner of the file. In this example, this file is owned by username ‘ramesh’.
Field 4 – Group: Fourth field specifies the group of the file. In this example, this file belongs to ”team-dev’ group.
Field 5 – Size: Fifth field specifies the size of file. In this example, ‘9275204’ indicates the file size.
Field 6 – Last modified date & time: Sixth field specifies the date and time of the last modification of the file. In this example, ‘Jun 13 15:27’ specifies the last modification time of the file.
Field 7 – File name: The last field is the name of the file. In this example, the file name is mthesaur.txt.gz.


4. Display File Size in Human Readable Format Using ls -lh
Use ls -lh (h stands for human readable form), to display file size in easy to read format. i.e M for MB, K for KB, G for GB.


$ ls -l
-rw-r----- 1 ramesh team-dev 9275204 Jun 12 15:27 arch-linux.txt.gz*

$ ls -lh
-rw-r----- 1 ramesh team-dev 8.9M Jun 12 15:27 arch-linux.txt.gz




5. Display Directory Information Using ls -ld
When you use “ls -l” you will get the details of directories content. But if you want the details of directory then you can use -d option as., For example, if you use ls -l /etc will display all the files under etc directory. But, if you want to display the information about the /etc/ directory, use -ld option as shown below.



$ ls -l /etc
total 3344
-rw-r--r--   1 root root   15276 Oct  5  2004 a2ps.cfg
-rw-r--r--   1 root root    2562 Oct  5  2004 a2ps-site.cfg
drwxr-xr-x   4 root root    4096 Feb  2  2007 acpi
-rw-r--r--   1 root root      48 Feb  8  2008 adjtime
drwxr-xr-x   4 root root    4096 Feb  2  2007 alchemist

$ ls -ld /etc
drwxr-xr-x 21 root root 4096 Jun 15 07:02 /etc




6. Order Files Based on Last Modified Time Using ls -lt
To sort the file names displayed in the order of last modification time use the -t option. You will be finding it handy to use it in combination with -l option.

$ ls -lt
total 76
drwxrwxrwt  14 root root  4096 Jun 22 07:36 tmp
drwxr-xr-x 121 root root  4096 Jun 22 07:05 etc
drwxr-xr-x  13 root root 13780 Jun 22 07:04 dev
drwxr-xr-x  13 root root  4096 Jun 20 23:12 root
drwxr-xr-x  12 root root  4096 Jun 18 08:31 home
drwxr-xr-x   2 root root  4096 May 17 21:21 sbin
lrwxrwxrwx   1 root root    11 May 17 20:29 cdrom -> media/cdrom
drwx------   2 root root 16384 May 17 20:29 lost+found
drwxr-xr-x  15 root root  4096 Jul  2  2008 var


7. Order Files Based on Last Modified Time (In Reverse Order) Using ls -ltr
To sort the file names in the last modification time in reverse order. This will be showing the last edited file in the last line which will be handy when the listing goes beyond a page. This is my default ls usage. Anytime I do ls, I always use ls -ltr as I find this very convenient.

$ ls -ltr

total 76
drwxr-xr-x  15 root root  4096 Jul  2  2008 var
drwx------   2 root root 16384 May 17 20:29 lost+found
lrwxrwxrwx   1 root root    11 May 17 20:29 cdrom -> media/cdrom
drwxr-xr-x   2 root root  4096 May 17 21:21 sbin
drwxr-xr-x  12 root root  4096 Jun 18 08:31 home
drwxr-xr-x  13 root root  4096 Jun 20 23:12 root
drwxr-xr-x  13 root root 13780 Jun 22 07:04 dev
drwxr-xr-x 121 root root  4096 Jun 22 07:05 etc
drwxrwxrwt  14 root root  4096 Jun 22 07:36 tmp


8. Display Hidden Files Using ls -a (or) ls -A
To show all the hidden files in the directory, use ‘-a option’. Hidden files in Unix starts with ‘.’ in its file name.

$ ls -a
[rnatarajan@asp-dev ~]$ ls -a
.                             Debian-Info.txt
..                            CentOS-Info.txt
.bash_history                 Fedora-Info.txt
.bash_logout                  .lftp
.bash_profile                 libiconv-1.11.tar.tar
.bashrc                       libssh2-0.12-1.2.el4.rf.i386.rpm



It will show all the files including the ‘.’ (current directory) and ‘..’ (parent directory). To show the hidden files, but not the ‘.’ (current directory) and ‘..’ (parent directory), use option -A.

$ ls -A
Debian-Info.txt               Fedora-Info.txt
CentOS-Info.txt               Red-Hat-Info.txt
.bash_history                 SUSE-Info.txt
.bash_logout                  .lftp
.bash_profile                 libiconv-1.11.tar.tar
.bashrc                       libssh2-0.12-1.2.el4.rf.i386.rpm
[Note: . and .. are not displayed here]


9. Display Files Recursively Using ls -R
$ ls  /etc/sysconfig/networking
devices  profiles

$ ls  -R /etc/sysconfig/networking
/etc/sysconfig/networking:
devices  profiles

/etc/sysconfig/networking/devices:

/etc/sysconfig/networking/profiles:
default

/etc/sysconfig/networking/profiles/default:
To show all the files recursively, use -R option. When you do this from /, it shows all the unhidden files in the whole file system recursively.


10. Display File Inode Number Using ls -i
Sometimes you may want to know the inone number of a file for internal maintenance. Use -i option as shown below to display inone number. Using inode number you can remove files that has special characters in it’s name as explained in the example#6 of the find command article.

$ ls -i /etc/xinetd.d/
279694 chargen      279724 cups-lpd  279697 daytime-udp
279695 chargen-udp  279696 daytime   279698 echo



11. Hide Control Characters Using ls -q
To print question mark instead of the non graphics control characters use the -q option.

ls -q
12. Display File UID and GID Using ls -n
Lists the output like -l, but shows the uid and gid in numeric format instead of names.

$ ls -l ~/.bash_profile
-rw-r--r--  1 ramesh ramesh 909 Feb  8 11:48 /home/ramesh/.bash_profile
$ ls -n ~/.bash_profile
-rw-r--r--  1 511 511 909 Feb  8 11:48 /home/ramesh/.bash_profile

[Note: This display 511 for uid and 511 for gid]
13. Visual Classification of Files With Special Characters Using ls -F
Instead of doing the ‘ls -l’ and then the checking for the first character to determine the type of file. You can use -F which classifies the file with different special character for different kind of files.

$ ls -F
Desktop/  Documents/  Ubuntu-App@  firstfile  Music/  Public/  Templates/
Thus in the above output,

/ – directory.
nothing – normal file.
@ – link file.
* – Executable file
14. Visual Classification of Files With Colors Using ls -F
Recognizing the file type by the color in which it gets displayed is an another kind in classification of file. In the above output directories get displayed in blue, soft links get displayed in green, and ordinary files gets displayed in default color.

$ ls --color=auto
Desktop  Documents Examples firstfile Music  Pictures  Public  Templates  Videos
15. Useful ls Command Aliases
You can take some required ls options in the above, and make it as aliases. We suggest the following.

Long list the file with size in human understandable form.
alias ll="ls -lh"
Classify the file type by appending special characters.
alias lv="ls -F"
Classify the file type by both color and special character.
alias ls="ls -F --color=auto"
