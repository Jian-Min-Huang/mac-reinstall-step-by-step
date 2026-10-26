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

```text
zmodule romkatv/powerlevel10k

# common alias alias
zmodule ohmyzsh/ohmyzsh -f 'plugins/common-aliases' -s 'plugins/common-aliases/common-aliases.plugin.zsh'
# git alias
zmodule ohmyzsh/ohmyzsh -f 'plugins/git' -s 'plugins/git/git.plugin.zsh'
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

## (optional) create new rsa ssh key

```bash
ssh-keygen -t rsa -b 4096 -C "abc@xyz.com"
```

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

- create new vault to 1password

## (optional) create new ed25519 ssh key

```bash
ssh-keygen -t ed25519 -C "abc@xyz.com" -f ~/.ssh/id_ed25519
```

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

- create new vault to 1password

## setup .ssh config

```bash
vi ~/.zshrc
```

```bash
echo 'export SSH_AUTH_SOCK=~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock' >> ~/.zshrc
```

```bash
mkdir -p ~/.1password && ln -s ~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock ~/.1password/agent.sock
```

- export opennet.pub from 1password
- open 1password Developer SSH Agent

```bash
chmod 400 ~/.ssh/opennet.pub
```

```bash
vi ~/.ssh/config
```

```text
Host *
    ServerAliveInterval 60

# Redis Bastion
Host redis-bastion
    HostName 172.31.71.172
    User vincent.huang
    IdentityAgent ~/.1password/agent.sock
    IdentityFile ~/.ssh/opennet.pub
    IdentitiesOnly yes

Host github.com
    User git
    IdentityAgent none
    IdentitiesOnly yes
    UseKeychain yes
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
brew install --cask obs slack dropbox sourcetree postman alfred orbstack setapp jetbrains-toolbox tunnelblick discord figma mongodb-compass redisinsight visual-studio-code@insiders dbeaver-community claude codex raycast claude-code vlc visual-studio-code lm-studio chatgpt lens tailscale-app jump-desktop-connect
```

```bash
brew cleanup
```

## brew install second part

```bash
brew update
```

```bash
brew install cmake awscli jq wrk gh opencc agent-browser eza yt-dlp trash tig
```

```bash
brew tap atlassian/homebrew-acli
```

```bash
brew install acli
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
nvm install --lts=krypton
```

```bash
nvm alias default xxx
```

## [PI Agent](https://pi.dev/docs/latest/quickstart)

## [install uv](https://docs.astral.sh/uv/#installation)

## AppStore

- line

## disable ssh password login

```bash
sudo vi /etc/ssh/sshd_config.d/01-keyonly.conf
```

```text
PubkeyAuthentication yes
PasswordAuthentication no
KbdInteractiveAuthentication no
AuthenticationMethods publickey
```

```bash
sudo /usr/sbin/sshd -t
```

```bash
sudo /usr/sbin/sshd -T | grep -Ei 'pubkeyauthentication|passwordauthentication|kbdinteractiveauthentication|authenticationmethods'
```

## .gitconfig

```text
[includeIf "hasconfig:remote.*.url:git@github.com:Jian-Min-Huang/**"]
    path = ~/.gitconfig-personal
[includeIf "hasconfig:remote.*.url:git@github.com:PureFuncInc/**"]
    path = ~/.gitconfig-personal
[includeIf "hasconfig:remote.*.url:git@github.com:Vincent-Huang-OpenNet/**"]
    path = ~/.gitconfig-opennet
[includeIf "hasconfig:remote.*.url:git@github.com:opennetltd/**"]
    path = ~/.gitconfig-opennet
```

```text
[user]
	name = Vincent Huang
	email = yfr.huang@hotmail.com

[core]
	sshCommand = ssh -i ~/.ssh/github_personal_ed25519.pub -o IdentitiesOnly=yes
```

```text
[user]
	name = Vincent Huang
	email = vincent.huang@opennet.tw

[core]
	sshCommand = ssh -i ~/.ssh/github_opennet_ed25519.pub -o IdentitiesOnly=yes
```
