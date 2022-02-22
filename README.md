# WhatsApp Crypt14-15 Database Decrypter
Decrypts WhatsApp .crypt14 and .crypt15 files, **given the key file**.  
The key file is named "key" if the backup is crypt14 or  
"encrypted_backup.key" if the backup is crypt15 (encrypted E2E backups).  
The output result is either a SQLite database 
or a ZIP file (in case of wallpapers and stickers).  
This is the only thing this script does. 
Those who are looking for a complete suite for
WhatsApp forensics, check out [whapa.](https://github.com/B16f00t/whapa)

## Requirements:

**Remember to download the proto folder!**

Python 3.7 or more recent    
pycriptodome  
javaobj-py3  
protobuf  

Use:
 ```
              python -m pip install -r requirements.txt
 ```
  Or:
 ```
              python -m pip install pycryptodome javaobj-py3 protobuf
 ```

## Usage

 ```
usage: decrypt14_15.py [-h] [-f] [-nm] [-v] [keyfile] [encrypted] [decrypted]

Decrypts WhatsApp database backup files encrypted with Crypt14 or Crypt15

positional arguments:
  keyfile        The WhatsApp encrypted_backup key file. Default: encrypted_backup.key
  encrypted      The encrypted crypt15 or crypt14 database. Default: msgstore.db.crypt15
  decrypted      The decrypted output database file. Default: msgstore.db

options:
  -h, --help     show this help message and exit
  -f, --force    Makes errors non fatal. Default: false
  -nm, --no-mem  Does not load files in RAM, stresses the disk more. Default: load files into RAM
  -v, --verbose  Prints all offsets and messages
 ```  

## Not working / crash / etc

Please open an issue and attach:
1) Output of the program (both with and without --force)
2) Hexdump of keyfile
3) Hexdump of first 512 bytes of encrypted DB

### Not planned / wontfix

1) Support for encrypting
2) supporting older encryption formats (you can decrypt crypt12 files using `--force` )

### Where do I get the keyfile?
**Is it beyond the scope of this project to tell you how to get the key file.  
Issues asking for this will be closed as invalid.**  
Anyway, on rooted Android, you can just copy 
`/data/data/com.whatsapp/files/key` 
(or `/data/data/com.whatsapp/files/encrypted_backup.key` if backups are crypt15)

### Last tested version (don't expect this to be updated)
Stable: 2.22.4.74  
Beta: 2.22.5.13


### Stargazers over time

[![Stargazers over time](https://starchart.cc/ElDavoo/WhatsApp-Crypt14-Decrypter.svg)](https://starchart.cc/ElDavoo/WhatsApp-Crypt14-Decrypter)


###### Credits:
 Original implementation for crypt12: [TripCode](https://github.com/TripCode)    
 Some help at the beginning: [DjEdu28](https://github.com/DjEdu28)  
 Actual crypt14/15 implementation with protobuf: [ElDavoo](https://github.com/ElDavoo)
