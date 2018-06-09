# Terminal Proxy

## 别名方案

### 设置别名

在终端输入 `echo $SHELL` 获取当前使用的终端。

如果你是在用 `zshell`, 在 `.zshrc` 内加入以下代码。
如果你是在用 `bash`, 在 `.bashrc` 内加入以下代码。

```bash
alias allproxy=" \
  ALL_PROXY=socks5://127.0.0.1:7890 \
  HTTP_PROXY=http://127.0.0.1:7890 \
  HTTPS_PROXY=http://127.0.0.1:7890 \
"

alias setproxy=" \
  export \
    ALL_PROXY=socks5://127.0.0.1:7890 \
    HTTP_PROXY=http://127.0.0.1:7890 \
    HTTPS_PROXY=http://127.0.0.1:7890 \
"

alias delproxy=" \
  unset \
    ALL_PROXY \
    HTTP_PROXY \
    HTTPS_PROXY \
"
```

### 使用方法

**allproxy**

```
$ allproxy curl -sSL ip.mehost.cn
```

**setproxy & delproxy**

```
$ setproxy
$ curl -sSL ip.mehost.cn
$ delproxy
```
