# HashingJobApp

### Tags : `#beginnerpicomini2022` `#generalskills` `#hashing` `#nc` `#shell` `#python`

> 100 points

#### AUTHOR : LT 'SYREAL' JONES

## Description

If you want to hash with the best, beat this test!
`nc <host> <port>`

## Solution

Connect using netcat :

``` bash
$ nc <host> <port>

Please md5 hash the text between quotes, excluding the quotes: '<string>'
Answer: 
```

You can use a commandline tool or web app like like [CyberChef](https://gchq.github.io/CyberChef/) to hash text.

## OR

Make a script to get the flag :

``` bash
$ nano solver.py
```

``` python
# solver.py
import re
import socket
import hashlib

host = ''        # Add the actual <host>
port =           # Add the actual <port>

def get_text_within_quotes(data):
    match = re.search(r"'([^']*)'", data)
    if match:
        return match.group(1)
    return None

def calculate_md5_hash(text):
    md5_hash = hashlib.md5(text.encode()).hexdigest()
    return md5_hash

def send_and_receive(s, message):
    s.sendall(message.encode())
    response = s.recv(1024).decode()
    return response

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((host, port))

    while True:
        data = s.recv(1024).decode()
        
        if 'picoCTF' in data:
            flag = re.findall('picoCTF{.*}', data)
            print("TADA! " + flag[0])
            break

        get_text = get_text_within_quotes(data)
        if not get_text:
            print("Error: Failed to extract text within quotes")
            break

        md5_hash = calculate_md5_hash(get_text)

        response = send_and_receive(s, md5_hash + '\n')
```

* Press `<CTRL + O>` (the letter "O," not zero) to write the changes to the file.
* Press `<ENTER>` to confirm.
* Press `<CTRL + X>` for exit nano.

Run the script :

``` bash
$ python solver.py

picoCTF{c3ns0r3d}
```
