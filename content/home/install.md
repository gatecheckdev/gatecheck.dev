---
title: "Install"
weight: 20
draft: true
---
## Root Key 

The root key must be injected at build time to prevent tampering.
Gate Check can be used without a root key which is suggested for singular tennant environments.

```console
export GC_ROOT_KEY=<public key in Base64>
go build -ldflags="-X 'main.RootPublicKeyB64=$GC_ROOT_KEY'" -o /Users/bacchus/go/bin/gatecheck .
```

### Generate Keys

The key format is PKCS#1 ASN.1 PEM .
This is a standard format so the public and private key can be created outside of Gate Check.

1. Generate a Root Public and Private Key using Gate Check CLI
  - Keep your private key secure! This is what you will use to create certificates
2. Convert the public key to Base64
3. Clone the project source code
4. Build Gate Check CLI and inject the Root Public Key via Environment Variable

```console
go run github.com/gatecheckdev/gatecheck-cli keygen .
export GC_ROOT_KEY=$(cat gatecheck_rsa.pub | base64)
git clone github.com/gatecheckdev/gatecheck-cli
cd gatecheck-cli
go build -ldflags="-X 'main.RootPublicKeyB64=$GC_ROOT_KEY'" -o /<target path>/gatecheck .
```
