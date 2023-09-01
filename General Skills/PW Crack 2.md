# PW Crack 2

### Tags : `#beginnerpicomini2022` `#generalskills`  `#passwordcracking`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Can you crack the password to get the flag?Download the password checker `here` and you'll need the encrypted `flag` in the same directory too.

## Solution

Download the files :

``` bash
$ wget <url> <url>

level2.py                                          100%[=================>]
level2.flag.txt.enc                                100%[=================>]
```

Read and analyze the script :

``` bash
$ vim level2.py
```

> Type `:q`  and press `<Enter>` to exit Vim.

```python
# level2.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0xff) + chr(0xff) + chr(0xff) + chr(0xff) ):
				   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")

level_2_pw_check()
```

Upon analyzing the script, you can observe that the user is prompted to enter a password, which is then compared to a string within an `if` statement. However, in this case, the correct password is not explicitly written in plain text. Instead, it is represented using a series of `chr` functions, which convert ASCII values to their corresponding characters.

The `Python interpreter` will help you to finde the correct password  : 

``` bash
$ python

Python <version> (main, <date>, <time>) [GCC <version>] on linux
Type "help", "copyright", "credits" or "license" for more information.

>>> chr(0xff) + chr(0xff) + chr(0xff) + chr(0xff)
'ÿÿÿÿ'
``` 

When the entered password matches the comparison string, the condition evaluates to `True`. Consequently, the encrypted flag is decrypted using the `str_xor` function with the correct password, and the decrypted flag is printed.

``` bash
$ python level2.py

Please enter correct password for flag: <correct_password>
Welcome back... your flag, user:
picoCTF{c3ns0r3d}
```