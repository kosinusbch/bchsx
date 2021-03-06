### Terms for clearweb *.bch.sx registrations

See [njalla terms of service](https://njal.la/tos/#term_4) section 4.

# BCH-DNS non-technical specification

BCH-DNS allows you to create, manage and update domain names and dns records on the Bitcoin Cash blockchain. If you register "bitcoinwallet", it will be accessible through bitcoinwallet.bch.sx and in the future just bitcoinwallet.bch.

## How does this work?

Each action is done on the blockchain through a OP_RETURN transaction. All changes are public, verifiable and auditable. The first person to register a domain keeps it for TBD.

## Actions

Content in quotes are a new pushdata. First pushdata is the protocol identifier registered for BCH DNS, second pushdata is version number 0(x) then up to 1296 different actions starting at 00-99 ending at 0A-ZZ, third is the domain you want to register or modify, fourth which is optional is the data to set. If left blank it will be deleted/unset. The first person to register the domain gets to keep it. Only confirmed (1-conf+) actions are considered valid.

This list will update regularly as more additions are supported. 00-0Z are reserved for domain-specific actions.

### 0x00 Register domain

`"0x04008080" "0x00" "bcash"`

### 0x01 Renew domain

`"0x04008080" "0x01" "bcash"`

### 0x02 Delete/Free domain

`"0x04008080" "0x02" "bcash"`

### 0x10 Set/update A record

`"0x04008080" "0x02" "bcash" "127.0.0.1"`

### 0x11 Set/update CNAME record

`"0x04008080" "0x03" "bcash" "example.com"`

## Avoiding and resolving conflics in domain registration

TBA