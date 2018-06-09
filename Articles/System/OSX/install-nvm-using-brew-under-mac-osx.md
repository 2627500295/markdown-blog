# Mac OSX 下使用 brew 安装 nvm

## 安装

```bash
brew install nvm
```

## 设置

```bash
cat << EOF >> ~/.zprofile

# NVM
export NVM_NODEJS_ORG_MIRROR="https://npm.taobao.org/mirrors/node"
export NVM_DIR="\$HOME/.nvm"
[ -s "\$(brew --prefix nvm)/nvm.sh" ] && . "\$(brew --prefix nvm)/nvm.sh"
[ -s "\$(brew --prefix nvm)/etc/bash_completion.d/nvm" ] && . "\$(brew --prefix nvm)/etc/bash_completion.d/nvm"
EOF
```
