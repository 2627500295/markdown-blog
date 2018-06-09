# Linux Security

## SSH 密钥

### 生成密钥对

```bash
ssh-keygen -t rsa -b 2048
```

## 禁止密码登录

```bash
sed -i "s/.*PasswordAuthentication.*/PasswordAuthentication no/g" /etc/ssh/sshd_config
```

## 强制 pubkey 登录

```bash
sed -i "s/.*PubkeyAuthentication.*/PubkeyAuthentication yes/g" /etc/ssh/sshd_config
```

## 禁用 Root 用户连接

```bash
sed -i "s/.*PermitRootLogin.*/PermitRootLogin no/g" /etc/ssh/sshd_config
```

## 禁止 X11 传输

```bash
sed -i "s/.*X11Forwarding.*/X11Forwarding no/g" /etc/ssh/sshd_config
```

## 重启 sshd

```bash
service sshd restart
```
