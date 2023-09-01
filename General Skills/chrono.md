# chrono

### Tags : `#picoctf2023` `#generalskills` `linux`

> 100 points

#### AUTHOR :  MUBARAK MIKAIL

## Description

How to automate tasks to run at intervals on linux servers?

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
$ cat /etc/crontab

picoCTF{c3ns0r3d}
```

Also the flag is here :

``` bash
$ cat challenge/metadata.json

{... , 'picoCTF{c3ns0r3d}', ...}
```


