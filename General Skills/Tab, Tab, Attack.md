# Tab, Tab, Attack

### Tags : `#picoctf2021` `#generalskills`

> 20 points

#### AUTHOR : SYREAL

## Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames :
`Addadshashanammu.zip`

## Solution

Download the file :

``` bash
$ wget <url>

Addadshashanammu.zip                               100%[=================>]
```

Extract the `.zip` file :

``` bash
$ unzip Addadshashanammu.zip

Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   [...]
```

You can use tab completion by typing the initial letters of a directory or file name and pressing the Tab key. This will automatically complete the name or suggest options if there are multiple matches, saving you time and effort when dealing with long directory structures and filenames.

``` bash
$cd Addadshashanammu/ <Press TAB>
```

Run :

``` bash
$ ./fang-of-haynekhtnamet

*ZAP!* picoCTF{c3ns0r3d}
```