# PW Crack 3

### Tags : `#beginnerpicomini2022` `#generalskills` `#passwordcracking` `#hashing`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Can you crack the password to get the flag?Download the password checker `here` and you'll need the encrypted `flag` and the `hash` in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solution

Download the files :

``` bash
$ wget <url> <url> <url>

level3.py                                          100%[=================>]
level3.flag.txt.enc                                100%[=================>]
level3.hash.bin                                    100%[=================>]
```

Read and analyze the script :

``` bash
$ vim level3.py
```

> Type `:q`  and press `<Enter>` to exit Vim.

```python
# level3.py
import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)

    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["8799", "d3ab", ...]
```

Upon examining the script, notice that there is a list of 7 potential passwords stored in the `pos_pw_list` variable. The goal is to identify the correct password among these possibilities.

Make a script to get the flag :

``` bash
$ vim solver.py
```

``` python
# solver.py
import hashlib

def str_xor(secret, key):
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c, new_key_c) in zip(secret, new_key)])

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

def crack_password():
    pos_pw_list = ["8799", "d3ab", ...] # Add the complete sequence of 7 strings

    for password in pos_pw_list:
        password_hash = hash_pw(password)
        if password_hash == correct_pw_hash:
            decryption = str_xor(flag_enc.decode(), password)
            print("Correct password found:", password)
            print("Decrypted flag:", decryption)
            return

    print("Unable to find the correct password.")

crack_password()

```

* Press `<ESC>` to ensure you are in the command mode.
* Type `:wq` to save the changes and exit Vim. 
* Press `<Enter>` to execute the command.

Run the script :

``` bash
$ python solver.py

Correct password found: <correct_string>
Decrypted flag: picoCTF{c3ns0r3d}
``` 