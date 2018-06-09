小程序生成，在 app.json 中添加

```javascript
{
  "tabBar": {
    "color": "#666",
    "selectedColor": "#F15255",
    "backgroundColor": "#fff",
    "borderStyle": "block",
    "list": [
      {
        "pagePath": "pages/home/home",
        "text": "首页",
        "iconPath": "images/topbar/home.png",
        "selectedIconPath": "images/topbar/home-select.png"
      },
      {
        "pagePath": "pages/product/list",
        "text": "产品分类",
        "iconPath": "images/topbar/product.png",
        "selectedIconPath": "images/topbar/product-select.png"
      },
      {
        "pagePath": "pages/project/list",
        "text": "工程案例",
        "iconPath": "images/topbar/project.png",
        "selectedIconPath": "images/topbar/project-select.png"
      },
      {
        "pagePath": "pages/index/index",
        "text": "联系我们",
        "iconPath": "images/topbar/phone.png",
        "selectedIconPath": "images/topbar/phone-select.png"
      },
      {
        "pagePath": "pages/about/about",
        "text": "关于我们",
        "iconPath": "images/topbar/about.png",
        "selectedIconPath": "images/topbar/about-select.png"
      }
    ]
  }
}
```

模拟一个

```css
@font-face {
	font-family: "wechatApp";
	src: url("http://developer-enterprise.mehost.cn/wechatApp/font/wechat/iconfont.eot"); /* IE9*/
	src: url("http://developer-enterprise.mehost.cn/wechatApp/font/wechat/iconfont.eot#iefix")
			format("embedded-opentype"), /* IE6-IE8 */
			url("http://developer-enterprise.mehost.cn/wechatApp/font/wechat/iconfont.woff")
			format("woff"),
		url("http://developer-enterprise.mehost.cn/wechatApp/font/wechat/iconfont.ttf")
			format("truetype"), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
			url("http://developer-enterprise.mehost.cn/wechatApp/font/wechat/iconfont.svg#wechatApp")
			format("svg"); /* iOS 4.1- */
}

[class*="icon"] {
	display: inline-block;
}

[class*="icon"]::before {
	font-family: "wechatApp";
	font-style: normal;
	font-weight: 400;
	speak: none;
	text-decoration: inherit;
	text-align: center;
	font-variant: normal;
	text-transform: none;
	-webkit-font-smoothing: antialiased;
}

.icon-phone:before {
	content: "\b050";
}
.icon-about-select:before {
	content: "\b041";
}
.icon-about:before {
	content: "\b040";
}
.icon-project:before {
	content: "\b030";
}
.icon-project-select:before {
	content: "\b031";
}
.icon-product:before {
	content: "\b020";
}
.icon-product-select:before {
	content: "\b021";
}
.icon-home:before {
	content: "\b010";
}
.icon-home-select:before {
	content: "\b011";
}
.icon-phone-select:before {
	content: "\b051";
}
.icon-map:before {
	content: "\b060";
}
.icon-map-select:before {
	content: "\b061";
}

.navbar {
	position: fixed;
	bottom: 0;
	left: 0;
	right: 0;

	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	text-align: center;

	border-top: 1px solid #ccc;
	z-index: 99999;
}

.navbar .nav-menu-item {
	flex-basis: 0;
	flex-grow: 1;
	max-width: 100%;

	color: #666;
	padding: 5px 0;
}

.navbar .nav-menu-item:hover,
.navbar .nav-menu-item:focus {
	color: #f15255;
}

.navigator-hover {
	background-color: #fff !important;
}
.navbar .nav-menu-item:hover,
.navbar .nav-menu-item:focus,
.navbar .nav-menu-item:active .navbar .nav-menu-item:visited {
	color: #f15255;
	background-color: #fff !important;
}

.navbar .nav-menu-item .icon {
	display: block;

	font-size: 22px;
	line-height: 22px;

	margin-bottom: 5px;
}

.navbar .nav-menu-item text {
	display: block;
	height: 14px;
	font-size: 10px;
}
```

```html
<view class="navbar">
  <navigator url="pages/home/home" open-type="redirect" class="nav-menu-item">
    <view class="iconfont icon icon-home"></view>
    <text>首页</text>
  </navigator>
  <navigator url="pages/home/home" open-type="redirect" class="nav-menu-item">
    <view class="iconfont icon icon-product"></view>
    <text>产品</text>
  </navigator>
  <navigator url="pages/project/list" open-type="redirect" class="nav-menu-item">
    <view class="iconfont icon icon-project"></view>
    <text>案例</text>
  </navigator>
  <navigator url="tel:15971475022" class="nav-menu-item" bindtap="onCall">
    <view class="iconfont icon icon-phone"></view>
    <text>电话</text>
  </navigator>
  <navigator url="../../pages/about/about" class="nav-menu-item">
    <view class="iconfont icon icon-about"></view>
    <text>我们</text>
  </navigator>
</view>
```
