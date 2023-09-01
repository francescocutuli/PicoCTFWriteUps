# Lets Warm Up

### Tags : `#picoctf2019` `#generalskills`

> 50 points

#### AUTHOR : SANJAY C/DANNY TUNITIS

## Description

If I told you a word started with `<number_hex>` in hexadecimal, what would it start with in ASCII?

## Solution

Make a script to get the flag :

``` bash
$ nano solver.py
```

``` python
# solver.py
number =              # add <number_hex>
print(''.join(['picoCTF{', chr(number), '}']))
```

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run the script :

``` bash
$ python solver.py

picoCTF{c3ns0r3d}
```