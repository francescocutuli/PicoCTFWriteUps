# Bases

### Tags : `#picoctf2019` `#generalskills`

> 100 points

#### AUTHOR : SANJAY C/DANNY TUNITIS

## Description

What does this `<sting>` mean? I think it has something to do with bases.

## Solution

The given code `<sting>` appears to be in Base64 format. To decode it, we can use the `base64` command with the `-d` option.

``` bash
$ echo "<string>" | base64 -d

picoCTF{c3ns0r3d}
```
