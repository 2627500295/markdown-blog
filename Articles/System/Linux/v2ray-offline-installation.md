# V2ray 离线安装

```bash
mkdir tmp && cd tmp

wget https://github.com/v2fly/v2ray-core/releases/download/v4.43.0/v2ray-linux-64.zip

unzip v2ray-linux-64.zip

mkdir -p /usr/local/etc/v2ray/

mkdir -p /usr/local/share/v2ray

mv ./systemd/system/v2ray.service /etc/systemd/system/v2ray.service

mv config.json /usr/local/etc/v2ray/

mv v2{ray,ctl} /usr/local/bin/

mv {geosite,geoip}.dat /usr/local/share/v2ray

cd .. && rm -r tmp

systemctl daemon-reload

systemctl enable v2ray

systemctl start v2ray
```
