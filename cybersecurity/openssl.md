cryptographic library that implements the SSL and TLS protocols

#### decrypt .enc file with a key in any usual key format
```
openssl pkeyutl -decrypt -inkey key.pem -in file.enc -out decrypted_file.txt
```
- `pkeyutl -decrypt`: decrypt file with a key
- `-inkey`: keyfile input. example: key.txt, key.pem, key.key ...
	- `-inkey <keyfile>`. example: `-inkey key.txt`
- `-in`: encrypt file input
	- `-in <encrypt-file>`. example: `-in file.enc`
- `-out`: output file after decrypt file
	- `-out <filename.txt>`. example: `-out decrypt.txt`