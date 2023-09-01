# First Find

### Tags : `#picogimexclusive`#generalskills`

> 100 points

#### AUTHOR :  LT 'SYREAL' JONES

## Description

Unzip this archive and find the file named 'uber-secret.txt'

- `Download zip file`

## Solution

Download the file :

``` bash
$ wget <url>

files.zip                                          100%[=================>]
```

Extract the `.zip` file :

``` bash
$ unzip files.zip

Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
   [...]
```

You can manually browse through the extracted files or use the `find` command for a quicker search.

``` bash
$ find files -name "uber-secret.txt"

files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

Read the file :

``` bash
$ cat <all_path>/uber-secret.txt

picoCTF{c3ns0r3d}
```