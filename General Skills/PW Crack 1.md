# PW Crack 1

### Tags : `#beginnerpicomini2022` `#generalskills`  `#passwordcracking`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Can you crack the password to get the flag?Download the password checker `here` and you'll need the encrypted `flag` the same directory too.

## Solution

Download the files :

``` bash
$ wget <url> <url>

level1.py                                          100%[=================>]
level1.flag.txt.enc                                100%[=================>]
```

Read and analyze the script :

```bash
$ vim level1.py
```

> Type `:q`  and press `<Enter>` to exit Vim.

```python
# level1.py
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

flag_enc = open('level1.flag.txt.enc', 'rb').read()


def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "<correct_password>"):
				    ^^^^^^^^^^^^^^^^^^^
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
    

level_1_pw_check()
```

By examining the script, you can observe that the user-entered password is compared to a string within an `if` statement.**This means that the correct password is explicitly written in the script itself**. When the entered password matches the comparison string, the condition evaluates to `True`. Consequently, the encrypted flag is decrypted using the `str_xor` function with the correct password, and the decrypted flag is printed.

``` bash
$ python level1.py

Please enter correct password for flag: <correct_password>
Welcome back... your flag, user:
picoCTF{c3ns0r3d}
```