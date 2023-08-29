What will you do when you install the SharePoint Server? run the Configuration wizard. You can do this using the GUI or the command line. This article will introduce the PSconfig.exe command and how to use it to configure the SharePoint Server.
There are four steps to complete this task:
1. configure the sharepoint farm
```
psconfig.exe -cmd configdb -create -server <database server> -database <database name> -user <user name> -password <password> -passphrase <passphrase>
```
replace the <database server> with the name of the database server, <database name> with the name of the database, <user name> with the name of the user, <password> with the password of the user, and <passphrase> with the passphrase for the farm.

2. restart the Sharepoint Timer Service
```
net stop SPTimerV4
net start SPTimerV4
```

3. upgrade the SharePoint Products
```
psconfig.exe -cmd upgrade -inplace b2b -wait -force
```

4. complete other configuration tasks