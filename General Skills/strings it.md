# strings it

### Tags : `#picoctf2019` `#generalskills`

> 100 points

#### AUTHOR : SANJAY C/DANNY TUNITIS

## Description

Can you find the flag in `file` without running it?

## Solution

Download the file :

``` bash
$ wget <url>

strings                                            100%[=================>]
```


Once you have the file downloaded, use the `strings` command to extract readable strings from it and combine it with `grep` to search for the flag :

``` bash
$ strings strings | grep -o 'picoCTF{.*}'

picoCTF{c3ns0r3d}
```

This command will display only the substrings that match the pattern `'picoCTF{.*}'`, which represents the flag format. Look for the flag among the extracted strings.