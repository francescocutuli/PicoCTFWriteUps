# Glitch Cat

### Tags : `#beginnerpicomini2022` `#generalskills` `#nc` `#shell` `#python`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Our flag printing service has started glitching!
`$ nc <host> <port>`

## Solution

Connect using netcat :

``` bash
$ nc <host> <port>

'picoCTF{' + chr(0x63) + chr(0x33) + chr(0x6e) + chr(0x73) + chr(0x30) + chr(0x72) + chr(0x33) + chr(0x64) + '}'
```

The flag is being printed using a combination of hexadecimal and  ASCII values. To obtain the actual flag, you can use the `chr()` function in Python to convert these hexadecimal values to their corresponding characters.

Open a `Python interpreter` and execute the code  : 

``` bash
$ python

Python <version> (main, <date>, <time>) [GCC <version>] on linux
Type "help", "copyright", "credits" or "license" for more information.

>>> 'picoCTF{' + chr(0x63) + chr(0x33) + chr(0x6e) + chr(0x73) + chr(0x30) + chr(0x72) + chr(0x33) + chr(0x64) + '}'

'picoCTF{c3ns0r3d}'
```