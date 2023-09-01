# Warmed Up

### Tags : `#picoctf2019` `#generalskills`

> 50 points

#### AUTHOR : SANJAY C/DANNY TUNITIS

## Description

What is  `<number_hex>` (base 16) in decimal (base 10)?

## Solution

Make a solver script :

``` bash
$ nano solver.py
```

``` python
# solver.py
number = ''  # add <number_hex>
print(''.join(['picoCTF{', str(int(number, base=16)), '}']))
```

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run the script :

``` bash
$ python solver.py

picoCTF{c3ns0r3d}
```