### Tasks
1. Create a simple file and do `ls -ltr` to see the details of the files [refer to Notes](https://github.com/LondheShubham153/90DaysOfDevOps/tree/master/2023/day06/notes)

Each of the three permissions are assigned to three defined categories of users. The categories are:

- owner — The owner of the file or application.
- "chown" is used to change the ownership permission of a file or directory.
- group — The group that owns the file or application.
- "chgrp" is used to change the group permission of a file or directory.
- others — All users with access to the system. (outised the users are in a group)
- "chmod" is used to change the other users permissions of a file or directory.

  As a task, change the user permissions of the file and note the changes after `ls -ltr`
A)
    chmod 600 file

2. Write an article about File Permissions based on your understanding from the notes.
A)  file permissions are 
    read 
    write 
    execute 
    sudo to give file same permissions as owner 
    . to give access to other uses or groups
    4 2 1 order for read write execute
    chmod, chgrp, chown to change permissions
    t for sticky bit to avoid deletion by other users
    /etc/fstab to know acl permissions are given or not
    getfacl, setfacl to know acl permissions
        -m for modify -ugo for user group othrt
    d for directory

3. Read about ACL and try out the commands `getfacl` and `setfacl`
A) they are used to set and get to know about the ACL permissions for other users or groups and denoted by .and given -m for modify -ugo for user grp others