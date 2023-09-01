# fixme2.py

### Tags : `#beginnerpicomini2022` `#generalskills` `#python`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Fix the syntax error in the Python script to print the flag.
`Download Python script`

## Solution
Download the file :

``` bash
$ wget <link>

fixme2.py                                          100%[=================>]
```

Exec python script : 

``` bash
$ python fixme2.py

  File "fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

It's a `SyntaxError`, add a `=` in line 22. 

``` 
$ nano fixme1.py
```

Make the changes and :

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run :

``` bash
$ python fixme2.py

That is correct! Here's your picoCTF{c3ns0r3d}
```