[![Joknarf Tools](https://img.shields.io/badge/Joknarf%20Tools-Visit-darkgreen?logo=github)](https://joknarf.github.io/joknarf-tools)
[![Build and Release Packages](https://github.com/joknarf/targpg/actions/workflows/release.yml/badge.svg)](https://github.com/joknarf/targpg/actions/workflows/release.yml)
[![bash](https://img.shields.io/badge/shell-bash%20-blue.svg)]()
[![bash](https://img.shields.io/badge/OS-Linux%20|%20macOS%20|%20SunOS%20...-blue.svg)]()
[![Licence](https://img.shields.io/badge/licence-MIT-blue.svg)](https://shields.io/)

# targpg
tar command extended with gpg encryption/decryption with password-file

> * Unlike `gpgtar` or other tools, just use `targpg` exactly like `tar` with all features and standard options of tar.  
> * `targpg` is just using `tar` `-I` options for `gpg` crypt/decrypt as a compression/decompression command.
> * The first option must be `-p <password-file>`

use `targpg.compat` if your tar command does not accept `-I <command>` but only `-I <prog>`

## pre-requisites

* bash
* gnu tar
* gpg

## usage

```
targpg [-p <password-file>] <tar command options>
```
if no `-p` option as first argument, will be prompted for password if using tty

## examples

```
$ targpg -p ~/.mypass cvf secrets.tgp --exclude=.git secrets
$ targpg -p <(echo "$pass") cvf secrets.tgp --exclude=.git secrets 
$ targpg -p <(echo "$pass") xvf secrets.tgp
$ targpg xfv secrets.tgp
Password:
```
