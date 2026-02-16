# Backup these directories before reinstall

- GitHub, Desktop, Downloads

## [install Homebrew](https://brew.sh/index)

```bash
brew analytics off
```

## brew install cask first part

```bash
brew update
```

```bash
brew install --cask google-chrome 1password font-fira-code
```

```bash
brew cleanup
```

## brew install first part

```bash
brew install git
```

## [install Zim](https://github.com/zimfw/zimfw)

```bash
vi ~/.zimrc
```

```plaintext
zmodule romkatv/powerlevel10k

# common alias alias
zmodule ohmyzsh/ohmyzsh -f 'plugins/common-aliases' -s 'plugins/common-aliases/common-aliases.plugin.zsh'
# docker-compose alias
zmodule ohmyzsh/ohmyzsh -f 'plugins/docker-compose' -s 'plugins/docker-compose/docker-compose.plugin.zsh'
# command line vi mode
zmodule ohmyzsh/ohmyzsh -f 'plugins/vi-mode' -s 'plugins/vi-mode/vi-mode.plugin.zsh'
# this plugin defines the z command that tracks your most visited directories and allows you to access them with very few keystrokes
zmodule ohmyzsh/ohmyzsh -f 'plugins/z' -s 'plugins/z/z.plugin.zsh'
```

## [install powerlevel10k font](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#meslo-nerd-font-patched-for-powerlevel10k)

## setup .ssh

```bash
mkdir .ssh
```

## (optional) create new ssh key

```bash
ssh-keygen -t rsa -b 4096
```

```bash
pbcopy < ~/.ssh/id_rsa
```

- create new vault to 1password

## setup .ssh config

```bash
vi ~/.zshrc
```

```plaintext
export SSH_AUTH_SOCK=~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock
```

```bash
mkdir -p ~/.1password && ln -s ~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock ~/.1password/agent.sock
```

- export jianminhuang.pub & opennet.pub from 1password
- open 1password Developer SSH Agent

```bash
chmod 400 ~/.ssh/jianminhuang.pub
```

```bash
chmod 400 ~/.ssh/opennet.pub
```

```bash
vi ~/.ssh/config
```

```plaintext
Host *
    ServerAliveInterval 60
    IdentityAgent ~/.1password/agent.sock

# Jian-Min-Huang GitHub
Host jianminhuang
    HostName github.com
    User git
    IdentityFile ~/.ssh/jianminhuang.pub
    IdentitiesOnly yes

# OpenNet GitHub
Host opennet
    HostName github.com
    User git
    IdentityFile ~/.ssh/opennet.pub
    IdentitiesOnly yes
```

## setup vim

```bash
cd ~ && git clone jianminhuang:Jian-Min-Huang/.vim.git
```

```bash
cd ~ && ln -s ~/.vim/.vimrc .
```

```bash
cd ~ && ln -s ~/.vim/.vscodevimrc .
```

```bash
cd ~ && ln -s ~/.vim/.ideavimrc .
```

```bash
vi ~/.vim/plugin/airline.vim
```

```bash
:PlugInstall
```

## brew install cask second part

```bash
brew update
```

```bash
brew install --cask obs slack dropbox sourcetree postman alfred orbstack setapp jetbrains-toolbox tunnelblick discord figma mongodb-compass redisinsight visual-studio-code@insiders dbeaver-community claude codex cursor raycast claude-code vlc
```

```bash
brew cleanup
```

## brew install second part

```bash
brew update
```

```bash
brew install cmake awscli jq wrk gh opencc copilot-cli
```

```bash
brew cleanup
```

## Setapp

- ...

## [SDKMAN!](https://sdkman.io/install)

```bash
sdk list java
```

```bash
sdk install java xxx
```

```bash
sdk list maven
```

```bash
sdk install maven xxx
```

## [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

```bash
nvm ls-remote --lts
```

```bash
nvm install xxx
```

```bash
nvm alias default xxx
```

## [install uv](https://docs.astral.sh/uv/#installation)

## AppStore

- line
- xcode

