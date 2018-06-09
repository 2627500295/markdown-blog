# Debian 切换软件存储库(源)

## Debian 11 换源

### 腾讯源

#### 内网

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.tencentyun.com/debian/ bullseye main
deb-src http://mirrors.tencentyun.com/debian/ bullseye main
deb http://mirrors.tencentyun.com/debian-security bullseye-security main
deb-src http://mirrors.tencentyun.com/debian-security bullseye-security main
deb http://mirrors.tencentyun.com/debian/ bullseye-updates main
deb-src http://mirrors.tencentyun.com/debian/ bullseye-updates main
EOF
```

注意: 使用内网源, 需要设置为指定 DNS 解析

```bash
cat <<EOF > /etc/resolv.conf
nameserver 183.60.83.19
nameserver 183.60.82.98
EOF

#### 外网

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.tencent.com/debian/ bullseye main
deb-src http://mirrors.tencent.com/debian/ bullseye main
deb http://mirrors.tencent.com/debian-security bullseye-security main
deb-src http://mirrors.tencent.com/debian-security bullseye-security main
deb http://mirrors.tencent.com/debian/ bullseye-updates main
deb-src http://mirrors.tencent.com/debian/ bullseye-updates main
EOF
```

### 阿里云

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.aliyun.com/debian/ bullseye main
deb-src http://mirrors.aliyun.com/debian/ bullseye main
deb http://mirrors.aliyun.com/debian-security bullseye-security main
deb-src http://mirrors.aliyun.com/debian-security bullseye-security main
deb http://mirrors.aliyun.com/debian/ bullseye-updates main
deb-src http://mirrors.aliyun.com/debian/ bullseye-updates main
EOF
```

### 华为云

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.huaweicloud.com/debian/ bullseye main
deb-src http://mirrors.huaweicloud.com/debian/ bullseye main
deb http://mirrors.huaweicloud.com/debian-security bullseye-security main
deb-src http://mirrors.huaweicloud.com/debian-security bullseye-security main
deb http://mirrors.huaweicloud.com/debian/ bullseye-updates main
deb-src http://mirrors.huaweicloud.com/debian/ bullseye-updates main
EOF
```

### 中科大源

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.ustc.edu.cn/debian/ bullseye main
deb-src http://mirrors.ustc.edu.cn/debian/ bullseye main
deb http://mirrors.ustc.edu.cn/debian-security bullseye-security main
deb-src http://mirrors.ustc.edu.cn/debian-security bullseye-security main
deb http://mirrors.ustc.edu.cn/debian/ bullseye-updates main
deb-src http://mirrors.ustc.edu.cn/debian/ bullseye-updates main
EOF
```

### 网易云

```bash
cat <<EOF > /etc/apt/sources.list
deb http://mirrors.163.com/debian/ bullseye main
deb-src http://mirrors.163.com/debian/ bullseye main
deb http://mirrors.163.com/debian-security bullseye-security main
deb-src http://mirrors.163.com/debian-security bullseye-security main
deb http://mirrors.163.com/debian/ bullseye-updates main
deb-src http://mirrors.163.com/debian/ bullseye-updates main
EOF
```

