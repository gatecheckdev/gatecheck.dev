---
title: "User Guide"
weight: 4
---

## Create keys
Gate Check uses RSA keys for signing files.

Example:

```console
gatecheck keygen .
ls
gatecheck_rsa.pub
gatecheck_rsa
```

## Root Key

In order to provide the greatest degree of security, the *Root Public Key* must be injected into the source code at build time.

See install.md for more instructions on how to do this.
```console
export GC_ROOT_KEY=<public key>
go build -ldflags="-X 'main.RootPublicKeyB64=$GC_ROOT_KEY'" -o /Users/bacchus/go/bin/gatecheck .
```

