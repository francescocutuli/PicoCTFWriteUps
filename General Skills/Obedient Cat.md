# Obedient Cat

### Tags : `#picoctf2021` `#generalskills`

> 5 points

#### AUTHOR : SYREAL

## Description

This file has a flag in plain sight (aka "in-the-clear").
`Download flag`.

## Solution

First, download the flag file :

``` bash
$ wget <url>

flag                                               100%[=================>]
```

Now, you can determine the file type using the command `file` :

``` bash
$ file flag

flag: ASCII text
```

  
You can read the file since it is in ASCII text format with the command :

```
$ cat flag

picoCTF{c3ns0r3d}
```