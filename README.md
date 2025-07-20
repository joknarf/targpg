# targpg
tar command extended with gpg encryption/decryption with password-file

Unlike `gpgtar` or other tools, just use `targpg` exactly like `tar` with all features and standard options of tar.
`gpgtar` is just using tar -I options for `gpg` crypt/decrypt as a compression/decompression command.
The only first option must be `-p <password-file>`

## usage

```
targpg -p <password-file> <tar command options>
```

## examples

```
$ targpg -p ~/.mypass cvf secrets.tgp secrets --exclude=.git
$ targpg -p <(echo $pass) cvf secrets.tgp secrets --exclude=.git
$ targpg -p <(echo $pass) xvf secrets.tgp
```
