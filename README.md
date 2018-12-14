# RECYCLEBIN
## ABOUT
A recyclebin function to replace the 'rm' command.
When the function is enabled, everytime you use 'rm' command to delete file, it would move it to the ~/.trash folder. And use 'rr' to list or recovery files in recyclebin. 
## INSTALL
1. Download or Git clone
2. cp rcyclebin.sh /etc/profile.d/
3. source /etc/profile
4. rcyclbin enable 
5. rcyclbin disable # to cancelled the function
## USAGE
```
>> rm -h
Usage: rm [-fh] file1 [file2 ...]
          -h for usage
          If '-f' used, then the script will exec 
          real 'rm' command with full command directly
       rr -l to see file in recyclebin
>> rr -h
Usage:     -h for help
           -l to list record in recyclebin
           append file number that listed to recovery
```

Expamle:
```
[nzk@xxxx ~]$ touch testa testb
[nzk@xxxx ~]$ rm testa testb
Are you sure to delete the files to recyclebin?[y/n]y
testa      delete to rcycbin
testb      delete to rcycbin
[nzk@xxxx ~]$ rr -l
---List for recycle bin---
1:      testa from /home/nzk  as testa_2018-12-14_20:48:45
2:      testb from /home/nzk  as testb_2018-12-14_20:48:45
[nzk@xxxx ~]$ rr 1
Are u sure to recovery testa to /home/nzk?[y/n]y
testa has been resotred to /home/nzk
[nzk@xxxx ~]$
```

