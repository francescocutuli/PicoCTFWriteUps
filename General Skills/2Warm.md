# 2Warm

### Tags : `#picoctf2019` `#generalskills`

> 50 points

#### AUTHOR : SANJAY C/DANNY TUNITIS

## Description

Can you convert the number `<number_dec>` (base 10) to binary (base 2)?

## Solution

Make a solver script :

``` bash
$ nano solver.py
```

``` python
# solver.py
number =              # add <number_dec>
print(''.join(['picoCTF{', bin(number)[2:], '}']))
```

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run the script :

``` bash
$ python solver.py

picoCTF{c3ns0r3d}
```