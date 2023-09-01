# Static ain't always noise

### Tags : `#picoctf2021` `#generalskills`

> 20 points

#### AUTHOR : SYREAL

## Description

Can you look at the data in this binary: `static`. This `BASH script` might help!

## Solution

Download the files :

``` bash
$ wget <url> <url>

static                                             100%[=================>]
ltdis.sh                                           100%[=================>]
```

Check the file types :

``` bash
$ file -i static ltdis.sh

static:   application/x-pie-executable; charset=binary
ltdis.sh: text/x-shellscript; charset=us-ascii
```

So, you have a shell script file `ltdis.sh` and an executable file `static`.

Change files permissions :

``` bash
$ chmod +x static ltdis.sh
```

As suggested by the description, the shell script should help us look inside the `static` executable.

``` bash
$./ltdis.sh static

Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
```

Excellent! The `ltdis.sh` successfully disassembled the `static` executable. It has generated two output files for further analysis:

```
static.ltdis.x86_64.txt
```

<details>
<summary>File description :</summary>
<br>
This file contains the disassembled instructions, allowing us to explore the underlying assembly code and understand the program's functionality.
</details>

```
static.ltdis.strings.txt
```

<details>
<summary>File description :</summary>
<br>
This file stores the extracted strings from the binary file, along with their corresponding file offsets. These strings can serve as valuable clues or hints, shedding light on the purpose of the executable. 
</details>

To find the flag, use the `grep` command like this to display only substrings that match the pattern `'picoCTF{.*}'`, which represents the flag format, in the `static.ltdis.strings.txt` file :

```bash
$ grep -o 'picoCTF{.*}' static.ltdis.strings.txt

picoCTF{c3ns0r3d}
```
