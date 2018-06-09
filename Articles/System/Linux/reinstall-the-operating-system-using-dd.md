# 使用 `dd` 重新安装操作系统

## 使用

```bash
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') \
--debian "11.1.0" \
--ver "amd64" \
--password "__PASSWORD__" \
-firmware \
--auto
```

## 选项

### DNS

--ip-dns

### 架构

--ver amd64 | arm64

### 系统

--debian
--centos
--ubuntu

### 密码

--password

### 额外驱动

-firmware

### mirror

--mirror

### 自动

--auto

## 示例

```bash
bash <(wget --no-check-certificate -qO- "https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh") \
--debian "11.1.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
--mirror "https://mirrors.cloud.tencent.com/debian/" \
-firmware \
--auto
```

```bash
bash <(wget --no-check-certificate -qO- "https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh") \
--debian "11.1.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
--mirror "https://mirrors.cloud.tencent.com/debian/" \
--ip-dns "183.60.83.19" \
--ip-addr "10.0.16.3" \
--ip-gate "10.0.16.1" \
--ip-mask "255.255.252.0" \
-firmware \
--auto
```

```bash
bash <(wget --no-check-certificate -qO- "https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh") \
--debian "11.1.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
--mirror "https://mirrors.cloud.tencent.com/debian/" \
--ip-dns "183.60.83.19" \
--ip-addr "10.0.12.12" \
--ip-gate "10.0.12.1" \
--ip-mask "255.255.252.0" \
-firmware \
--auto
```
