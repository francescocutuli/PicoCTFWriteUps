# Nice netcat...

### Tags : `#picoctf2021` `#generalskills`

> 15 points

#### AUTHOR : SYREAL

## Description

There is a nice program that you can talk to by using this command in a shell :
`$ nc <host> <port>`, but it doesn't speak English...

## Solution

Connect with `netcat` : 

``` bash
$ nc <host> <port>

112
105
99
[...]
```

It seems like the server is sending a sequence of decimal numbers.
You can convert these decimal numbers to ASCII characters using Python.
Use an editor or from the command line use this:

``` bash
$ nano solver.py
```

``` python
# solver.py
numbers = [112, 105, 99, ...] # Add the complete sequence of numbers
message = ''.join(chr(num) for num in numbers)
print(message)
```

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run the script :

``` bash
$ python solver.py

picoCTF{c3ns0r3d}
```