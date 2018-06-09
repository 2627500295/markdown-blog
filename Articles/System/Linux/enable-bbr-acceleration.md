# 开启 BBR 加速

## 修改系统变量

```bash
cat << EOF >> /etc/sysctl.conf
net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr
EOF
```

## 保存生效

```bash
sysctl -p
```

## 校验

```bash
sysctl net.ipv4.tcp_available_congestion_control
```

返回值为 `net.ipv4.tcp_available_congestion_control = bbr cubic reno`

```bash
lsmod | grep bbr
```

返回值为 `tcp_bbr 20480 3`
