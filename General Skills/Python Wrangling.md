# Python Wrangling

### Tags : `#picoctf2021` `#generalskills`

> 10 points

#### AUTHOR : SYREAL

## Description

Python scripts are invoked kind of like programs in the Terminal... Can you run `this Python script`
using `this password` to get `the flag`?

## Solution

First,  download the required files :

``` bash
$ wget <url> <url> <url>

ende.py                                            100%[=================>]
flag.txt.en                                        100%[=================>]
pw.txt                                             100%[=================>]
```

Exec the Python script :

``` bash
$ python ende.py

Usage: ende.py (-e/-d) [file]
```

Get more info using -h parameter : 

``` bash
$ python ende.py -h

Usage: ende.py (-e/-d) [file]
Examples:
  To decrypt a file named 'pole.txt', do: '$ python ende.py -d pole.txt'
```

Finally : 

``` bash
$ cat pw.txt

<secret_password>                                      [COPY]
```

``` bash
$ python ende.py -d flag.txt.en

Please enter the password:<secret_password>            [PASTE]                       
picoCTF{c3ns0r3d}

```