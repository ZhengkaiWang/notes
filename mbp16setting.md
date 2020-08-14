## 新MacBook pro 设置

### 一：homebrew安装
1. Git代理设置 
```
$ git clone —global http.proxy 'socks5://127.0.0.1:7891'
$ git clone —global https.proxy 'socks5://127.0.0.1:7891'
```
设置保存在 　~/.gitconfig
 2. 终端代理设置
```
$ nano ~/.zshrc
# write in proxy list
alias proxy='export  all_proxy=socks5://127.0.0.1:7891'
alias unproxy='unset all_proxy'
$ source ~/.zshrc
$ proxy
```
3. 安装brew
```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
``` 

### 二：zsh安装（macOS默认zsh终端）
1. Oh-my-zsh
```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
之前的.zshrc会转存到.zshrc.pre-oh-my-zsh
```
$ brew install autojump
$ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
.zshrc plugin中加入autojump zsh-autosuggestion zsh-syntax-highlighting
2. zsh主题配置
https://github.com/romkatv/powerlevel10k#oh-my-zsh
```
git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
Set ZSH_THEME="powerlevel10k/powerlevel10k" in ~/.zshrc.
```
brew tap homebrew/cask-fonts
brew cask install font-hack-nerd-font
```
在iterm2中设置字体
3. 配置sublime app打开文件
在.zshrc中加入
```
alias sublime='open -a /Applications/Sublime\ Text.app'
```