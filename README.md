# exp-plutus

Plutus experiments

Current tested plutus version: [v2021-09-10](https://github.com/input-output-hk/plutus/releases/tag/v2021-09-10) hash `f7466c86fe3afc593746e44257adbf7785f7cedb`

## Using this repo

### setup

**get the repo and dependencies**

`git clone --recursive git@github.com:mkungla/exp-plutus.git && cd exp-plutus`

**prepare nix**

```bash
curl -L https://nixos.org/nix/install | sh
. $HOME/.nix-profile/etc/profile.d/nix.sh
```

**prepare plutus env**

https://github.com/input-output-hk/plutus#cache-warning

```bash
sudo mkdir /etc/nix
sudo bash -c "cat > /etc/nix/nix.conf <<EOL
substituters        = https://hydra.iohk.io https://iohk.cachix.org https://cache.nixos.org/
trusted-public-keys = hydra.iohk.io:f/Ea+s+dFdN+3Y/G+FDgSq+a5NEWhJGzdjvKNGv0/EQ= iohk.cachix.org-1:DpRUyj7h7V830dp/i6Nti+NEO2/nhblbov/8MW7Rqoo= cache.nixos.org-1:6NCHdD59X431o0gWypbMrAURkbJ16ZPMQFGspcDShjY=
EOL"
```

**init nix shell first time**

first time it will take some time, if your nix cache is set up correctly further use is faster.

```
cd ./vendor/plutus && nix-shell
cabal update
```
## Start the playground

1. open new terminal

> server
```
cd ./vendor/plutus && nix-shell
cd ./plutus-playground-client 
plutus-playground-server
```

2. open new terminal

> client
```
cd ./vendor/plutus && nix-shell
cd ./plutus-playground-client 
npm start
```

## Resources

check: https://github.com/input-output-hk/plutus-pioneer-program
