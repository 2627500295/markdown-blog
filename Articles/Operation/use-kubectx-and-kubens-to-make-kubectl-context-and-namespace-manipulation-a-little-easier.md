# 使用 kubectx 和 kubens 使 kubectl 上下文和命名空间操作更容易一些

每天我开始使用 k8s 并输入 kubectl 命令。有两点我觉得有点麻烦。

- 我不知道有关上下文的命令（我手动做过 `kubectl get contexts` 之类事情）

- 为每个命令指定命名空间（`-n website`　或 `--namespace website`）很麻烦。

我从网上看到了 `kubectx` 和 `kubens`，这些工具可以让这些烦恼变得更容易一些，所以我将分享它们。

## 安装

在 Mac 上, 您可以使用 `Homebrew` 命令来安装它。

```BASH
$ brew install kubectx
```

就一条命令, 就能让你同时使用 `kubectx` 和 `kubens` 这两个命令。

其它各种安装方法，请参考 [README.md](https://github.com/ahmetb/kubectx#installation) 了解详细信息。

## 我不知道有关上下文相关的信息

`kubectx` 命令很方便。

### 显示上下文列表

```BASH
$ kubectx

spartanhost:seattle
tencent:beijing
tencent:shanghai
```

当前上下文以与其他上下文不同的颜色显示。

### 上下文切换

```BASH
$ kubectx tencent:shanghai

Switched to context "tencent:shanghai"
```

## 为每个命令指定命名空间很麻烦

事实上，每次只使用 kubectl 命令都可以省略指定命名空间。您可以使用以下命令切换默认命名空间，该命令将使用 `-n` 或 `--namespace` 不使用选项。

```BASH
$ kubectl config set-context --current --namespace=(namespace名)
```

（参考）[使用 kubectl 切换命名空间](./use-kubectl-to-switch-namespaces.md)

但是，对于说我不记得有关上下文的命令的我来说，障碍很高。

`kubens` 所以请改用该命令。

### 显示命名空间列表

```BASH
$ kubens

default
kube-system
kube-public
kube-node-lease
cert-manager
website
across
```

`kubectx` 同样，当前的命名空间也会以不同的颜色显示。

### 命名空间切换

```bash
$ kubens website

Context "tencent:beijing" modified.
Active namespace is "website".
```
