 0-current_working_directory:This script prints the absolute path name of the current working directory.
1-listit :This script displays the contents list of the current directory, including directories and files.
2-bring_me_home:This script changes the working directory to the user's home directory.
3-listfiles:This script displays the contents of the current directory in a long format.
 4-listmorefiles:This script displays the contents of the current directory, including hidden files, in a long format.
5-listfilesdigitonly:This script displays the contents of the current directory in a long format, with user and group IDs displayed numerically. 
 6-firstdirectory:This script creates a directory named my_first_directory in the /tmp/ directory. It uses the mkdir command to create the directory.
7-movethatfile:This script moves the file named betty from the /tmp/ directory to the /tmp/my_first_directory/ directory. It uses the mv command to perform the file move operation.
8-firstdelete:This script deletes the file named betty located in the /tmp/my_first_directory directory. It uses the rm command to remove the file.
9-firstdirdeletion:This script deletes the directory named my_first_directory located in the /tmp directory. It uses the rmdir command to remove the directory.
10-back:This script changes the working directory to the previous directory. It uses the cd - command to navigate back to the previous directory.
11-lists:This script lists all files in the current directory, the parent directory, and the /boot directory in long format, including hidden files. It uses the ls -la command to list files with detailed information, where -l enables long format listing and -a includes hidden files.
12-file_type:This script uses the file command with the file path /tmp/iamafile as an argument. The file command is used to determine the file type and provides information about the file.
13-symbolic_link:This script uses the ln command with the -s option to create a symbolic link. The source file is /bin/ls, and the target link name is __ls__.
14-copy_html:This script uses the cp command with the following options:

-r: Recursively copies directories and their contents.
-u: Copies only when the source file is newer than the destination file or when the destination file does not exist.
--update: Skips copying files that are newer in the destination directory.

