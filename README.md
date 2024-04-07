# Backup these directories before reinstall
* GitHub, Desktop, Downloads

# [install Homebrew](https://brew.sh/index)
```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> ~/.zprofile
```
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```
```bash
brew analytics off
```

# brew install cask first part
```bash
brew update
```
```bash
brew tap homebrew/cask-fonts
```
```bash
brew install --cask google-chrome iterm2 1password 1password-cli font-fira-code
```
```bash
brew cleanup
```

# [setup iTerm2 dracula theme](https://github.com/dracula/iterm/blob/master/INSTALL.md)
* change iterm2 Color Presets -> import
* change iterm2 Color Presets -> Darcula
* change iterm2 Text Font

# brew install first part
```bash
brew install git
```

# [install Zim](https://github.com/zimfw/zimfw)
```bash
vi ~/.zimrc
```
```
zmodule romkatv/powerlevel10k

zmodule ohmyzsh/ohmyzsh -f 'lib' -s 'lib/clipboard.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/copybuffer' -s 'plugins/copybuffer/copybuffer.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/common-aliases' -s 'plugins/common-aliases/common-aliases.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/copypath' -s 'plugins/copypath/copypath.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/docker-compose' -s 'plugins/docker-compose/docker-compose.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/emoji' -s 'plugins/emoji/emoji.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/git' -s 'plugins/git/git.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/gitfast' -s 'plugins/gitfast/gitfast.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/kubectl' -s 'plugins/kubectl/kubectl.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/sudo' -s 'plugins/sudo/sudo.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/vi-mode' -s 'plugins/vi-mode/vi-mode.plugin.zsh'
zmodule ohmyzsh/ohmyzsh -f 'plugins/z' -s 'plugins/z/z.plugin.zsh'
```

# setup .ssh
```bash
mkdir .ssh
```

# (optional) create new ssh key
```bash
ssh-keygen -t rsa -b 4096
```
```bash
pbcopy < ~/.ssh/id_rsa
```
* create new vault to 1password

# [setup .ssh config](https://developer.1password.com/docs/ssh)
```bash
vi ~/.zshrc
```
```
export SSH_AUTH_SOCK=~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock
```
```bash
mkdir -p ~/.1password && ln -s ~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock ~/.1password/agent.sock
```
* export jianminhuang.pub & opennet.pub from 1password
* open 1password Developer SSH Agent
```bash
chmod 400 ~/.ssh/jianminhuang.pub
```
```bash
chmod 400 ~/.ssh/opennet.pub
```
```bash
vi ~/.ssh/config
```
```
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

# setup vim
```bash
cd ~ && git clone jianminhuang:Jian-Min-Huang/.vim.git
```
```bash
cd ~ && ln -s ~/.vim/.vimrc .
```
```bash
cd ~ && ln -s ~/.vim/.ideavimrc .
```
```bash
vi ~/.vimrc
```
```
:PlugInstall
```

# brew install cask second part
```bash
brew update
```
```bash
brew install --cask slack dropbox sourcetree postman alfred orbstack setapp jetbrains-toolbox tunnelblick discord figma mongodb-compass obsidian
```
```bash
brew cleanup
```

# Setapp
* ...

# [SDKMAN!](https://sdkman.io/install)
```bash
sdk list java
```
```bash
sdk install xxx
```

# [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
```bash
nvm ls-remote --lts
```
```bash
nvm install xxx
```
```bash
nvm alias default xxx
```
