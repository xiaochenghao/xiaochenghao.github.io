Homebrew Homebrew源代码仓库 
替换源地址: cd "$(brew --repo)" git remote set-url origin https://mirrors.ustc.edu.cn/brew.git 
重置为官方地址: cd "$(brew --repo)" git remote set-url origin https://github.com/Homebrew/brew.git 

Homebrew Bottles Homebrew预编译二进制软件包 
在运行brew, 前设置环境变量HOMEBREW_BOTTLE_DOMAIN，值为https://mirrors.ustc.edu.cn/homebrew-bottles 
替换源地址: 
bash: echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile source ~/.bash_profile 
zsh: echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zshrc source ~/.zshrc

Homebrew Core Homebrew核心软件仓库 
替换源地址: cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core" git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git 
重置为官方地址: cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core" git remote set-url origin https://github.com/Homebrew/homebrew-core 

Homebrew Cask Homebrew cask软件仓库,提供macOS应用和大型二进制文件 
替换源地址: cd "$(brew --repo)"/Library/Taps/homebrew/homebrew-cask git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-cask.git 
重置为官方地址: cd "$(brew --repo)"/Library/Taps/homebrew/homebrew-cask git remote set-url origin https://github.com/Homebrew/homebrew-cask
