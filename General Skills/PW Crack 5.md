# PW Crack 5

### Tags : `#beginnerpicomini2022` `#generalskills` `#passwordcracking` `#hashing`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Can you crack the password to get the flag?Download the password checker `here` and you'll need the encrypted `flag` and the `hash` in the same directory too. Here's a `dictionary` with all possible passwords based on the password conventions we've seen so far.

## Solution

Download the files :

``` bash
$ wget <url> ... <url>

level5.py                                          100%[=================>]
level5.flag.txt.enc                                100%[=================>]
level5.hash.bin                                    100%[=================>]
dictionary.txt                                     100%[=================>]
```

Read and analyze the script :

``` bash
$ vim level5.py
```

> Type `:q`  and press `<Enter>` to exit Vim.

```python
# level5.py
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

flag_enc = open('level5.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level5.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_5_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_5_pw_check()
```

To find the correct password, you can utilize the provided `dictionary.txt` file containing potential passwords. You need to perform a dictionary attack by iterating over the passwords in the file and hashing each password using the `hash_pw()` function. Then compare the generated hash with the `correct_pw_hash` to identify the correct password.

Make a script to get the flag :

``` bash
$ vim solver.py
```

``` python
# solver.py
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

flag_enc = open('level5.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level5.hash.bin', 'rb').read()
dictionary = open('dictionary.txt','r').read().split()


def hash_pw(pw):
    pw_bytes = bytearray()
    pw_bytes.extend(pw.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def crack_password():
   
    for password in dictionary:
      pw_hash = hash_pw(password)
    
      if( pw_hash == correct_pw_hash ):
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
$  python solver.py

Correct password found: <correct_password>
Decrypted flag: picoCTF{c3ns0r3d}
``` 