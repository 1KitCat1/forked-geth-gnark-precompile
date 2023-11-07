# Bootstrapping private ethereum


## Docker

```bash
docker compose up
```

## CLI

Ensure you are in project root directory and build geth.

```bash
cd ..
make geth

export GETH=$(pwd)/build/bin
export PATH=$PATH:$GETH
```

Launch geth in dev mode for remix development.

```bash
geth --http \
 --http.corsdomain="https://remix.ethereum.org" \
 --http.api web3,eth,debug,personal,net \
 --vmdebug \
 --datadir dev-edition/devnode/ \
 --dev console
```

### Account

For development node is initialized with an account of known private key, 
which will also receive block reward in clique consensus.

```bash
geth account import -password ./account/password ./account/pkey
```