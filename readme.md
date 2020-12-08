https://github.com/Eun/DisableMonitor
https://dev.to/equiman/iterm2--oh-my-zsh--powerlevel9k-best-terminal-combination-for-geeks-58l5

https://dev.to/equiman/setup-macos-for-development-3kc2


```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew tap homebrew/cask-fonts

brew update
brew upgrade
brew cleanup

brew doctor
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"

sudo chown -R $(whoami) /usr/local/opt
sudo chown -R $(whoami) /usr/local/share
sudo chown -R $(whoami) /usr/local/lib
brew cask install visual-studio-code

brew install git
rm '/usr/local/bin/git-cvsserver'
brew link --overwrite git
brew install git-lfs
git lfs install

brew cask install iterm2 

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

git clone https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/nobeans/zsh-sdkman.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/sdkman

brew install zsh-history-substring-search
brew install zsh-syntax-highlighting
brew install z
brew install tree
chsh -s /bin/zsh

DEFAULT_USER="$USER"

ZSH_THEME="powerlevel10k/powerlevel10k"
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(history)
POWERLEVEL9K_SHORTEN_DIR_LENGTH=1

ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern cursor root line)
ZSH_HIGHLIGHT_PATTERNS=('rm -rf *' 'fg=white,bold,bg=red')

plugins=(
  brew
  git
  gradle
  ng
  npm
  yarn
  zsh-autosuggestions
  osx
  sdkman
  history-substring-search
)

alias x="exit"
alias sz="source ~/.zshrc"
alias hc="history -c"
alias hg="history | grep "

#Include Z
if command -v brew >/dev/null 2>&1; then
  # Load rupa's z if installed
  [ -f $(brew --prefix)/etc/profile.d/z.sh ] && source $(brew --prefix)/etc/profile.d/z.sh
fi

```
