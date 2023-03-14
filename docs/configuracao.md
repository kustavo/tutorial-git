# Configuração

O comando `git config` define as configurações a serem usadas pelo git.

```bash
# Nome do usuário.
git config user.name "<nome usuario>"
# Email do usuário.
git config user.email "<email-usuario>"
# Editor padrão.
git config core.editor "<editor>"
# Define o arquivo que irá conter a lista de arquivos ignorados.
git config core.excludesfile ~/.gitignore
# Ferramenta de merge padrão.
git config merge.tool "<ferramenta>"
# Local da chave SSH
git config core.sshCommand "ssh -i <caminho-completo>/<arquivo-chave-privada>"

# Opções:
# --local | Define as configurações localmente (local default ".git/config").
# --global | Define as configurações globalmente para o usuário corrente (local default "~/.gitconfig").
# --system | Define as configurações globalmente para todos os usuários  (local default "/etc/gitconfig"). 
```

## Listar configurações

Para ver as configurações definidas, podemos executar o comando abaixo:

```bash
git config --list

# Opções:
# --local | Configurações definidas no escopo local.
# --global | Configurações definidas no escopo global.
# --system | Configurações definidas no escopo de sistema.
```

## Arquivo de configuração

As configurações do git são armazenadas em arquivos de configuração, seja no escopo local, global ou de sistema.

Todo repositório local git possui o arquivo de configuração `.git/config` onde podemos ver e definir as configurações manualmente para cada repositório.

Para abrir o arquivo de configuração de cada escopo, podemos executar o comando abaixo:

```bash
git config -e

# Opções:
# --local | Abre o arquivo de configuração local.
# --global | Abre o arquivo de configuração global.
# --system | Abre o arquivo de configuração de sistema.
```

No arquivo de configuração local `.git/config`, por exemplo, podemos definir os dados de usuário e chave SSH específica para um determinado projeto:

```ini
[core]
    repositoryformatversion = 0
    filemode = false
    bare = false
    logallrefupdates = true
    symlinks = false
    ignorecase = true
    sshCommand = "ssh -i C:/Users/gustavo/projetos/ssh-private-key"
[remote "origin"]
    url = git@github.com:usuario/tutorial-git.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
    remote = origin
    merge = refs/heads/main
[user]
    name = Gustavo Araújo
    email = usuario@gmail.com
```

## Referências

- <https://git-scm.com/docs/git-config>
