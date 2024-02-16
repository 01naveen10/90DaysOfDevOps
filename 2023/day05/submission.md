### Tasks

1. You have to do the same using Shell Script i.e using either Loops or command with start day and end day variables using arguments -

So Write a bash script create directories.sh that when the script is executed with three given arguments (one is the directory name and second is start number of directories and third is the end number of directories ) it creates a specified number of directories with a dynamic directory name.
A)
#!/bin/bash

file="$1"
s="$2"
e="$3"

for (( i=s ; i <= $e ; i++ ));
do
        mkdir -p "${file}_${i}"
done


2.  Create a Script to backup all your work done till now.
A)
#!/bin/bash

src=./imp_files
tgt=./backups

cur_time=$(date "+%Y-%m-%d-%H-%M-%S")

bckup=$tgt/$cur_time.tgz
echo "backing up ..."

tar czf $bckup $src

echo "backup complete"

3.  Read About Cron and Crontab, to automate the backup Script
A) cron to schedule scripts to run at a time crontab is the file to execute those files

4.  Read about User Management and Let me know on Linkedin if you're ready for Day 6.
A) sudo usermod  useradd  -l -r etc


5.  Create 2 users and just display their Usernames
A) sudo useradd jj kk
    cat /etc/psswd
