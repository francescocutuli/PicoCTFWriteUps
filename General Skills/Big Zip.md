# Big Zip

### Tags : `#picogimexclusive` `#generalskills`

> 100 points

#### AUTHOR :  LT 'SYREAL' JONES

## Description

Unzip this archive and find the flag.

- `Download zip file`

## Solution

Download the file :

``` bash
$ wget <url>

big-zip-files.zip                                  100%[=================>]
```

Extract the `.zip` file :

``` bash
$ unzip big-zip-files.zip

Archive:  big-zip-files.zip
   creating: big-zip-files/
   extracting: big-zip-files/jpvaawkrpno.txt  
   inflating: big-zip-files/oxbcyjsy.txt  
   [...]
```

Move to `big-zip-files` directory an use `grep` command to search for the flag file : 

``` bash
$ cd big-zip-files
```

``` bash
$ grep -r 'picoCTF{.*}'

<file_path> : picoCTF{c3ns0r3d}
```