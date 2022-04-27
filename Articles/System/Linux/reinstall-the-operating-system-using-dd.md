# 使用 `dd` 重新安装操作系统

&nbsp;

## 使用

```bash
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') \
--debian "11.1.0" \
--ver "amd64" \
--password "__PASSWORD__" \
-firmware \
--auto
```

如果 `Github` 过慢, 请使用 `jsdelivr` 与 `fastgit` 方案加速。

- https://raw.fastgit.org/MoeClub/Note/master/InstallNET.sh

- https://cdn.jsdelivr.net/gh/MoeClub/Note@master/InstallNET.sh

&nbsp;

## 选项

### DNS

--ip-dns

腾讯云内网 DNS

cat <<EOF > /etc/resolv.conf 
nameserver 183.60.83.19
nameserver 183.60.82.98
EOF

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

&nbsp;

## 示例

### 腾讯云国内内网

```bash
bash <(wget --no-check-certificate -qO- "https://cdn.jsdelivr.net/gh/MoeClub/Note@master/InstallNET.sh") \
--debian "11.3.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
--mirror "http://mirrors.tencentyun.com/debian/" \
--ip-dns "183.60.82.98" \
-firmware \
--auto
```

### 国内
            
```bash
bash <(wget --no-check-certificate -qO- "https://cdn.jsdelivr.net/gh/MoeClub/Note@master/InstallNET.sh") \
--debian "11.3.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
--mirror "http://mirrors.ustc.edu.cn/debian/" \
-firmware \
--auto
```

### iON / Oracle
  
> `Oracle` 系统请选择 `Ubuntu`

```bash
bash <(wget --no-check-certificate -qO- "https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh") \
--debian "11.3.0" \
--ver "amd64" \
--password "__PASSWORD__"  \
-firmware \
--auto
```
