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
