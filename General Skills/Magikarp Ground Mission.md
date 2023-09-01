# Magikarp Ground Mission

### Tags : `#picoctf2021` `#generalskills`

> 30 points

#### AUTHOR : SYREAL

## Description

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. 
Login via `ssh` as `<username>` with the password, `<password>`

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

After successful login, you will see the welcome message and the command prompt indicating that you are in the instance's shell.

You can start by listing the files and directories in the current directory :

```bash
<username>@<instace>$ ls

1of3.flag.txt  instructions-to-2of3.txt
```

You can see the presence of the file `1of3.flag.txt` and `instructions-to-2of3.txt`.
Read the contents of the files: 

```
<username>@<instace>$ cat *

picoCTF{c3n
Next, go to the root of all things, more succinctly `/`
```

Next, you are instructed to navigate to the root directory `/`.
You can change the directory using the `cd` command :

```bash
<username>@<instace>$ cd /
```

After moving to the root directory, you can list its contents :

```bash
<username>@<instace>$ ls

2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt


<username>@<instace>$ cat 2of3.flag.txt instructions-to-3of3.txt

s0
Lastly, ctf-player, go home... more succinctly `~`
```

Finally, go back to the home directory using the shorthand notation `~` :

```
<username>@<instace>$ cat ~/3of3.flag.txt 

r3d}
```

Combine the partial flags obtained from each step to form the complete flag :

```
picoCTF{c3ns0r3d}
```