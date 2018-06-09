# 使用 kubectl 切换命名空间

## 介绍

命名空间很方便，因为您可以将 Pod、Services、Deployments、StatefulSets 等分组为同一集群中的虚拟集群。

这里总结一下如何使用 kubectl 命令切换和处理 Namespace。

## 临时切换命名空间

如果要为每个执行命令切换命名空间，请使用`-n` 或 `--namespace` 该选项。

```BASH
# 将 namespace 切换为 website
$ kubectl --namespace website get all
```

## 永久切换命名空间

更改连接上下文中的默认命名空间。

```BASH
# 将上下文的默认命名空间更改为 "mynamespace"
$ kubectl config set-context --current --namespace=website

# 检查命名空间
$ kubectl config view | grep namespace:
```

## 为特定的命名空间准备 kubectl 命令

在同一个集群中使用多个 Namespace 时，您不想永久切换，而是希望经常切换到特定的 Namespace。

在这种情况下，使用带有特定命名空间的 kubectl 命令可能会很有用。

```BASH
alias ksite="kubectl --namespace website"
```

用法和普通的 kubectl 命令一样

```BASH
ksite get all
```

## 参考

- [命名空间](https://kubernetes.io/zh/docs/concepts/overview/working-with-objects/namespaces/)