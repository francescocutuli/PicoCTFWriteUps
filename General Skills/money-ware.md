# money-ware

### Tags : `#picoctf2023` `#generalskills` `#osint`

> 100 points

#### AUTHOR :  JUNI19

## Description

Flag format: picoCTF{Malwarename}
The first letter of the malware name should be capitalized and the rest lowercase.Your friend just got hacked and has been asked to pay some bitcoins to `<BTC_Address>`. He doesn’t seem to understand what is going on and asks you for advice. Can you identify what malware he’s being a victim of?

## Solution
  
To identify the name of the malware, you should analyze the provided BTC address and gather any information that is available.

The BTC address itself does not directly provide information about the malware. However, you can use Open Source Intelligence (OSINT) techniques to gather more information.

Here's what you can do:

Visit [chainabuse.com](https://www.chainabuse.com/).
Go to the "View Reports" section on the website.
Search for the BTC address in question.

Once you find the report, read through it to obtain any relevant information.

If you come across an interesting report, it may redirect you to the Avira blog, which describes the ransomware and reveals its name. The name of this ransomware will be the flag or the identifying information you're looking for.

