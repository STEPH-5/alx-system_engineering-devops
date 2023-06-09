0-iam_betty:This script assumes that the user "betty" already exists on the system, as mentioned in the requirements.
1-who_am_i:When you run the script (./1-who_am_i), it will output the effective username of the current user.
2-groups:When you run the script (./2-groups), it will output all the groups the current user is a member of, separated by spaces.
3-new_owner:When you run the script with superuser privileges (sudo ./3-new_owner), it will change the owner of the "hello" file to the user "betty".
4-empty:When you run the script (./4-empty), it will create a new empty file called "hello" in the current directory.
5-execute:When you run the script (./5-execute), it will add execute permission to the owner of the file "hello" in the current directory.
6-multiple_permissions:When you run the script (./6-multiple_permissions), it will modify the permissions of the file "hello" as described.
7-everybody:When you run the script (./7-everybody), it will add execution permission to the owner, group owner, and other users for the file "hello" in the current directory.
8-James_Bond:When you run the script (./8-James_Bond), it will set the permissions for the file "hello" as specified: no permission for the owner and group owner, and read, write, and execute permissions for other users.9-John_Doe:When you run the script (./9-John_Doe), it will set the mode of the file "hello" as specified: -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello.
10-mirror_permissions:When you run the script (./10-mirror_permissions), it will set the mode of the file "hello" to match the mode of the file "olleh".
