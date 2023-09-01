# First Grep

### Tags : `#picoctf2019` `#generalskills`

> 100 points

#### AUTHOR : ALEX FULTON/DANNY TUNITIS

## Description

Can you find the flag in `file`? This would be really tedious to look through manually, something tells me there is a better way.

## Solution

Download the file :

``` bash
$ wget <url>

file                                               100%[=================>]
```

Use the `grep` command to display only the substrings that match the pattern `'picoCTF{.*}'`, which represents the flag format.

``` bash
$ grep -o 'picoCTF{.*}' file

picoCTF{c3ns0r3d}
```
