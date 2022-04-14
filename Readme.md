### Listar GPG's cadastradas

```bash
gpg --list-secret-key --keyid-form LONG
```

### Execute para criar key

```bash
gpg --full-generate-key
```

### Selecionar tipo de key - (1)

```bash
gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
  (14) Existing key from card
Your selection? 1
```

### Inserir tamanho da key - (4096)

```bash
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? (3072) 4096
```

<<<<<<< HEAD
### Inserir por quanto tempo essa key será valida - (1y)[1 ano]
=======
### Inserir por quanto tempo essa key será valida - (1y)
>>>>>>> 89c24ce5c32619fbf7aef8d31b7220a65bb53500

```bash
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 1y
```

### Confirmar seleção - (y)

```bash
Key expires at sex 14 abr 2023 16:33:40 -03
Is this correct? (y/N) y
```

### Inserir mesmo Nome cadastrado no Git

Não sabe qual? Execute no terminal `git config --list`

```bash
GnuPG needs to construct a user ID to identify your key.

Real name: Igor de Souza Bezerra
```

### Inserir mesmo Email cadastrado no Git

```bash
Email address: igor.souza1.bezerra@gmail.com
```

<<<<<<< HEAD
### Confirmar dados - (o)
=======
### Confirmar dados
>>>>>>> 89c24ce5c32619fbf7aef8d31b7220a65bb53500

```bash
GnuPG needs to construct a user ID to identify your key.

Real name: Igor de Souza Bezerra
Email address: igor.souza1.bezerra@gmail.com
Comment:
You selected this USER-ID:
    "Igor de Souza Bezerra <igor.souza1.bezerra@gmail.com>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? o
```

### Inserir uma senha

### Pegar o id da key com o comando

```bash
gpg --list-secret-key --keyid-form LONG
```

sec rsa4096/`7A3151RT72895350`

### Execute

```bash
gpg --armor --export 7A3151RT72895350
```

```bash
-----BEGIN PGP PUBLIC KEY BLOCK-----

mQINBGJYeJwBEADP4Wx2cErJb6Mb62aC1YO0iqniiR8Y+JTy2n6l9T6OnTExOcz2
6xsZ+ZX8P1xF+WFMo5VjlOza1Wc6Bocf1PCFE7Y9mp/KSH36EKda5nuJouyiX/J8
B/Sr/GEzfoALbm+UMzH3+C1s5LVhuSGKuMNG4HNk38ZFpi/bD82m1vtKSUh4pfqj
ZxfBihUg3HAt4HOwIvRGUah1Q13gMHozD+Ph6nytfcpoEWqlpkKShNVoILsKpTB9
dRGl+91hUFRAAtIgi56+qEAmHpgTY9QvLaTft8MqBnJXyue+qdbfzMCZelw95kWe

```

### Copie a chave publica e adicione no Github em Settings -> SSH and GPG Keys -> New GPG key

### Adicionar GPG nas configurações globais do git

```bash
git config --global user.signingkey 7A3151RT72895350
```

### Adicionar no `.bashrc` ou `.zshrc` a seguinte linha

```bash
export GPG_TTY=$(tty)
```

### Por fim para assinar os commits por padrão execute

```bash
git config --global commit.gpgsign true
```

```bash
git config --global tag.gpgSign true
```
