# fixme1.py

### Tags : `#beginnerpicomini2022` `#generalskills` `#python`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

Fix the syntax error in this Python script to print the flag.
`Download Python script`

## Solution

Download the file :

``` bash
$ wget <link>

fixme1.py                                          100%[=================>]
```

Exec python script : 

``` bash
$ python fixme1.py

  File "fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
    ^
IndentationError: unexpected indent
```

It's a `IndentationError`, go to line 20 and delete the 2 white space before the `print(` .

``` 
$ nano fixme1.py
```

Make the changes and:

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

 Run :

``` bash
$ python fixme1.py

That is correct! Here's your picoCTF{c3ns0r3d}
```