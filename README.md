# irmatool #

irmatool is a CLI tool providing various convenient [IRMA](https://www.irmacard.org) utilities. For this it uses [Gabi](https://github.com/mhe/gabi), a [Go](https://golang.org/) implementation of IRMA's cryptographic primitives. 

Supported and planned utilities:

- [X] Key generation
- [ ] Key check
- [ ] Basic issuance of credentials

Ideas for additional functionality? File an issue.

## Installation ##

Binaries will be provided in the future, but for now, install through go get:

    go get -u github.com/mhe/irmatool

## Usage ##

For information on how to use `irmatool`, issue the `help` command:

    irmatool help

This will output something like:
```
irmatool is a CLI tool providing various convenient IRMA utilities.

Usage:
  irmatool [command]

Available Commands:
  genkeypair  Generate an IRMA Issuer keypair.

Flags:
      --config string   config file (default is $HOME/.irmatool.toml)
  -t, --toggle          Help message for toggle

Use "irmatool [command] --help" for more information about a command.

```

## Example ##

Example invocation that generates a 1024 bit key pair that is valid for 6 months and 6 attributes. By default `irmatool` writes the private and public keys to `isk.xml` and `ipk.xml` respectively. 

    go run main.go genkeypair -l 1024 -a 6 -v 8M
    

