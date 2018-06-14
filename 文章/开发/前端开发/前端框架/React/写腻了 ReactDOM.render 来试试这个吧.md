# 写腻了 ReactDOM.render 来试试这个吧

## 安装

```bash
yarn add github:2627500295/render
```

OR

```
npm install github:2627500295/render
```

## 使用

入口 `index.js`

### 旧写法

```
import React from 'react';
import ReactDOM from 'react-dom';
import Root from '@/containers/Root';

ReactDOM.render(<Root />, document.getElementById('app'));
```

### 新写法

```
import render from '@microld/render';
import Root from '@/containers/Root';
render()(Root);
```

### 自定义挂载元素

```
import render from '@microld/render';
import Root from '@/containers/Root';

const MountElement = document.getElementById('root');
render(MountElement)(Root);
```

### 渲染方式

```
import { hydrate } from '@microld/render';
import Root from '@/containers/Root';
hydrate()(Root);
```

### 自定义 Rander

```
import render from '@microld/render';
import ReactDOM from 'react-dom';
import Root from '@/containers/Root';
render(null, ReactDOM.hydrate)(Root);
```

## 实现

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

let appElement = document.getElementById('app');
let rootElement = document.getElementById('root');

/**
 * 创建挂载元素
 *
 * @returns {HTMLDivElement} MountElem 挂载元素
 */
function createMountElement() {
  let MountElem = document.getElementById('appRoot');

  if (MountElem === void 0 || MountElem === null) {
    MountElem = document.createElement('div');
    MountElem.setAttribute('id', 'appRoot');
    document.body.insertBefore(MountElem, document.body.childNodes[0]);
  }

  return MountElem;
}

/**
 * 获取挂载元素
 *
 * @param {HTMLDivElement} MountElem 挂载元素
 * @returns {HTMLDivElement} 挂载元素
 */
function getMountElement(MountElem = appElement) {
  if (MountElem === void 0 || MountElem === null) {
    if (rootElem !== void 0 && rootElem !== null) {
      MountElem = rootElem
    }

    MountElem = createMountElement();
  }

  return MountElem;
}

/**
 * Render
 *
 * @param {HTMLDivElement} MountElement 挂载元素
 * @param {ReactDOM.Renderer} Renderer 渲染方式
 * @returns {Function}
 */
function render(MountElement = appElement, Renderer = ReactDOM.render) {
  if (Renderer === void 0 || Renderer === undefined) {
    Renderer = ReactDOM.render;
  }

  return (WrapperComponent) => {
    Renderer(React.createElement(WrapperComponent, null), getMountElement(MountElement));
  };
}

/**
 * Hydrate
 *
 * @param {HTMLDivElement} MountElement 挂载元素
 * @param {ReactDOM.Renderer} Renderer 渲染方式
 * @returns {Function}
 */
export function hydrate(MountElement, Renderer = ReactDOM.hydrate) {
  return render(MountElement, Renderer);
}

export default render;
```
