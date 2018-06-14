# HTML 5 Api 获取位置定位

本来是有一个自己也封装过一个的, 可是, 看了一下, 没有它个这好, 这个对错误都做了返回处理。

然后, 在苹果 Safari 下, http 不能获取地址位置, 只有 https 协议才能获取。

## 取自饿了么

```javascript
/**
 * 获取地理位置定位(饿了么)
 *
 * @returns {object} 返回定位信息
 */
export default function getLocation() {
  if (navigator.geolocation) {
    return new Promise((resolve, reject) => {
      navigator.geolocation.getCurrentPosition(
        (position) => {
          if (!position) {
            reject({ name: 'BROWSER_MODE_PERMISSON_FAILED' });
          }

          resolve(position);
        },
        reject,
        {
          // timeout: 20000,
          maximumAge: Infinity,
          enableHighAccuracy: false
        }
      );
    });
  }

  Promise.reject();
}
```

## 自写方法

```javascript
/**
 * 获取地理位置定位
 *
 * @returns {object} 返回经度和纬度
 */
export default function position() {
  let promise = new Promise((resolve, reject) => {
    navigator.geolocation.getCurrentPosition(
      (position) => {
        const { latitude, longitude } = position.coords;

        resolve({ latitude, longitude });
      },
      (error) => reject(error)
    );
  });

  return promise;
}
```
