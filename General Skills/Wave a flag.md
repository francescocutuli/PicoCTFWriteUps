# Wave a flag

### Tags : `#picoctf2021` `#generalskills`

> 10 points

#### AUTHOR : SYREAL

## Description

Can you invoke help flags for a tool or binary? `This program` has extraordinarily helpful information...

## Solution

Dowload the program :

``` bash
$ wget <url>

warm                                               100%[=================>]
```

Check the file types :

``` bash
$ file warm

warm: ELF 64-bit LSB pie executable [...]
```

This is an executable file. Change the permissions and run `warm`.

``` bash
$ chmod +x warm
```

```
$ ./warm

Hello user! Pass me a -h to learn what I can do!
```

```
$ ./warm -h

Oh, help? I actually don't do much, but I do have this flag here: 
picoCTF{c3ns0r3d}
```