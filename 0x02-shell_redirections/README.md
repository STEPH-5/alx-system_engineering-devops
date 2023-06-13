 0-hello_world:When you execute the script ./0-hello_world, it will print "Hello, World" followed by a new line to the standard output.
1-confused_smiley:When you execute the script ./1-confused_smiley, it will display "(Ôo)'" on the standard output.
2-hellofile:When you execute the script ./display_passwd.sh, it will display the content of the /etc/passwd file on the standard output.
3-twofiles:When you execute the script ./display_files.sh, it will display the content of both the /etc/passwd and /etc/hosts files on the standard output, without any separator between them.
4-lastlines:When you execute the script ./4-lastlines, it will display the last 10 lines of the /etc/passwd file on the standard output.
5-firstlines:When you execute the script ./5-firstlines, it will display the first 10 lines of the /etc/passwd file on the standard output.
 6-third_line:When you execute the script ./6-third_line, it will display the third line of the file iacta on the standard output. The script uses the head and tail commands to extract the third line from the file.
8-cwd_state:When you run the script (./8-cwd_state), it will execute the ls -la command and redirect the output to the ls_cwd_content file. After running the script, you can verify the contents of the file using cat ls_cwd_content.
9-duplicate_last_line:When you run the script, it will use the sed command to extract the last line of the file iacta and append it to the end of the file.
10-no_more_js: When you run the script, it will use the find command to locate all regular files (-type f) with a .js extension (-name "*.js") in the current directory and its subfolders, and then delete them using the -delete option.
11-directories:This script counts the number of directories and sub-directories in the current directory, excluding the current and parent directories. It excludes hidden directories and outputs the total count.
12-newest_files:The ls -lt command lists all files in the current directory, sorted by modification time in descending order.
head -n 10 selects the first 10 lines (i.e., the 10 newest files).
13-unique:The script utilizes the sort command to sort the words in alphabetical order and then pipes the sorted words to the uniq -u command, which filters out the duplicate lines and prints only the unique lines.
14-findthatword:The purpose of this script is to search for lines in the file /etc/passwd that contain the pattern "root" and display those lines.
15-countthatword:The purpose of this script is to search for lines in the file /etc/passwd that contain the pattern "bin" and count the number of such lines.
16-whatsnext:The purpose of this script is to search for lines in the file /etc/passwd that contain the pattern "root" and display those lines along with the 3 lines that follow them
17-hidethisword:The purpose of this script is to search for lines in the file /etc/passwd that do not contain the pattern "bin" and display those lines.
 18-letteronly:The purpose of this script is to search for lines in the file /etc/ssh/sshd_config that start with a letter.
20-hiago:The purpose of this script is to remove all instances of the letters 'c' and 'C' from the input text. The tr command is used with the -d option to delete those characters.
21-reverse:The purpose of this script is to reverse the input text. The rev command is used to reverse the characters in the input.

To use the script, save it in a file named 21-reverse, make it executable (chmod +x 21-reverse), and then you can pipe input text into it, as shown in the example:

bash
Copy code
echo "Reverse" | ./21-reverse
Running this command will output the reversed text, which in this case is "esreveR".





User
Write a script that displays all users and their home directories, sorted by users.

Based on the the /etc/passwd file
julien@ubuntu:/tmp/0x02$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false
systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false
systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false
systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false
syslog:x:104:108::/home/syslog:/bin/false
_apt:x:105:65534::/nonexistent:/bin/false
messagebus:x:106:110::/var/run/dbus:/bin/false
uuidd:x:107:111::/run/uuidd:/bin/false
lightdm:x:108:114:Light Display Manager:/var/lib/lightdm:/bin/false
whoopsie:x:109:116::/nonexistent:/bin/false
avahi-autoipd:x:110:119:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/bin/false
avahi:x:111:120:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/bin/false
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/bin/false
colord:x:113:123:colord colour management daemon,,,:/var/lib/colord:/bin/false
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/var/run/speech-dispatcher:/bin/false
hplip:x:115:7:HPLIP system user,,,:/var/run/hplip:/bin/false
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/bin/false
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
julien:x:1000:1000:Julien Barbier,,,:/home/julien:/bin/bash
guillaume:x:1001:1001:,,,:/home/guillaume:/bin/bash
betty:x:1002:1002::/home/betty:
julien@ubuntu:/tmp/0x02$
julien@ubuntu:/tmp/0x02$ ./22-users_and_homes 
_apt:/nonexistent
avahi-autoipd:/var/lib/avahi-autoipd
avahi:/var/run/avahi-daemon
backup:/var/backups
betty:/home/betty
bin:/bin
colord:/var/lib/colord
daemon:/usr/sbin
dnsmasq:/var/lib/misc
games:/usr/games
gnats:/var/lib/gnats
guillaume:/home/guillaume
hplip:/var/run/hplip
irc:/var/run/ircd
julien:/home/julien
kernoops:/
lightdm:/var/lib/lightdm
list:/var/list
lp:/var/spool/lpd
mail:/var/mail
man:/var/cache/man
messagebus:/var/run/dbus
news:/var/spool/news
nobody:/nonexistent
proxy:/bin
pulse:/var/run/pulse
root:/root
rtkit:/proc
saned:/var/lib/saned
speech-dispatcher:/var/run/speech-dispatcher
sync:/bin
sys:/dev
syslog:/home/syslog
systemd-bus-proxy:/run/systemd
systemd-network:/run/systemd/netif
systemd-resolve:/run/systemd/resolve
systemd-timesync:/run/systemd
usbmux:/var/lib/usbmux
uucp:/var/spool/uucp
uuidd:/run/uuidd
whoopsie:/nonexistent
www-data:/var/www
julien@ubuntu:/tmp/0x02$ 
Repo:

GitHub repository: alx-system_engineering-devops
Directory: 0x02-shell_redirections
File: 22-users_and_homes
ChatGPT
Certainly! Here's the script that displays all users and their home directories, sorted by users:

Script: 22-users_and_homes

bash
Copy code
#!/bin/bash

# This script displays all users and their home directories, sorted by users

awk -F: '{print $1 ":" $6}' /etc/passwd | sort
The purpose of this script is to extract the username and home directory information from the /etc/passwd file and display them in alphabetical order by username. The awk command is used to extract the desired fields (username and home directory) from each line of the file, and the sort command is used to sort the output.

To use the script, save it in a file named 22-users_and_homes, make it executable (chmod +x 22-users_and_homes), and then run it:

bash
Copy code
./22-users_and_homes
Running this command will display the usernames and their corresponding home directories, sorted by usernames, just like the example output you provided.





User
Write a command that finds all empty files and directories in the current directory and all sub-directories.

Only the names of the files and directories should be displayed (not the entire path)
Hidden files should be listed
One file name per line
The listing should end with a new line
You are not allowed to use basename, grep, egrep, fgrep or rgrep
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$ ls -laR
.:
total 64
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 .
drwxrwxr-x 7 ubuntu ubuntu 4096 Sep 29 21:36 ..
-rwxrwxr-x 1 ubuntu ubuntu   56 Feb  8  2016 0-commas
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 0-commas-checks
-rwxrwxr-x 1 ubuntu ubuntu   48 Feb  8  2016 1-empty_casks
-rwxrwxr-x 1 ubuntu ubuntu   68 Feb  8  2016 2-gifs
-rwxrwxr-x 1 ubuntu ubuntu   47 Feb  8  2016 3-directories
-rwxrwxr-x 1 ubuntu ubuntu   41 Feb  8  2016 4-zeros
-rwxrwxr-x 1 ubuntu ubuntu   43 Feb  8  2016 5-rot13
-rwxrwxr-x 1 ubuntu ubuntu   25 Feb  8  2016 6-odd
-rwxrwxr-x 1 ubuntu ubuntu   73 Feb  8  2016 7-sort_rot13
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:46 ........gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:47 ..hello.gif
drwxrwxr-x 2 ubuntu ubuntu 4096 Oct  7 00:41 javascript
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:48 Kris_is_awesome :)
-rw-rw-r-- 1 ubuntu ubuntu   14 Feb  8  2016 Makefile
-rw-rw-r-- 1 ubuntu ubuntu   69 Feb  8  2016 quote
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:24 Rona_napping.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  6 23:59 root.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Mar 24  2016 ..something
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 test_dir
-rwxrwxr-x 1 ubuntu ubuntu   54 Feb  8  2016 test.var

./0-commas-checks:
total 16
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..
-rw-rw-r-- 1 ubuntu ubuntu 1361 Feb  8  2016 28-check.php
-rw-rw-r-- 1 ubuntu ubuntu  481 Feb  8  2016 28-check.php~

./javascript:
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Oct  7 00:41 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..

./test_dir:
total 12
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 docker.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 file.sh
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 .horrible_selfie.gif
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 photos
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 README.md

./test_dir/photos:
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 cat.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 index.html
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 main.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 rudy_rigot.gif
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$ ./100-empty_casks
Rona_napping.gif
javascript
root.gif
..something
Kris_is_awesome :)
..hello.gif
file.sh
docker.gif
README.md
index.html
main.gif
cat.gif
rudy_rigot.gif
.horrible_selfie.gif
........gif
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$
Repo:

GitHub repository: alx-system_engineering-devops
Directory: 0x02-shell_redirections
File: 100-empty_casks
ChatGPT
Certainly! Here's the command that finds all empty files and directories in the current directory and all sub-directories:

Command: find . -type d -empty -printf '%f\n' ; find . -type f -empty -printf '%f\n'

Explanation:

find . -type d -empty finds all empty directories (-type d) starting from the current directory (.) and the -empty option ensures that only empty directories are matched.

-printf '%f\n' is used to print only the names of the directories (%f) followed by a newline (\n).

find . -type f -empty finds all empty files (-type f) starting from the current directory (.) and the -empty option ensures that only empty files are matched.

-printf '%f\n' is used to print only the names of the files (%f) followed by a newline (\n).

To use this command, open a terminal, navigate to the directory where you want to search for empty files and directories, and then run the command:

bash
Copy code
find . -type d -empty -printf '%f\n' ; find . -type f -empty -printf '%f\n'
The command will search for empty directories and empty files recursively in the current directory and its subdirectories. The names of the empty directories and files will be displayed, with one name per line.






22-users_and_homes:The purpose of this script is to extract the username and home directory information from the /etc/passwd file and display them in alphabetical order by username.    
