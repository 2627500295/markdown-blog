# 使用 Babel 来书写 Webpack 配置流程

## 安装应用层

### 安装 React

```bash
yarn add react react-dom @types/react @types/react-dom prop-types @types/prop-types
```

### 安装 React Router

```bash
yarn add react-router react-router-dom histyory @types/react-router @types/react-router-dom @types/histyory
```

### 安装 Reach Router

```bash
yarn add @reach/router @types/reach__router
```

### 安装 Redux

```bash
yarn add redux react-redux @types/react-redux redux-saga @types/redux-saga
```

### 安装 Mobx

```bash
yarn add mobx mobx-react
```

### 安装 className 处理模块

```bash
yarn add classnames @types/classnames
```

### 安装 Mockjs

```bash
yarn add mockjs @types/mockjs
```

### 安装 axios

```bash
yarn add axios @types/axios
```

&nbsp;

## 配置 Webpack

### 安装 Webpack

```
yarn add -D webpack webpack-cli @types/node @types/webpack
```

### 使用 Babel 书写配置

#### 安装 Bebel

```bash
yarn add -D @babel/core @babel/preset-env @babel/polyfill @babel/plugin-transform-modules-commonjs
```

#### Babel Cli 工具

```
yarn add -D @babel/cli @babel/node @babel/register
```

#### 配置 .babelrc

```javascript
{
  "presets": [
    ["@babel/preset-env", {"targets": {"ie": 9, "uglify": true}, "useBuiltIns": false, "modules": false}],
    "@babel/preset-react"
  ],
  "plugins": [
    "@babel/plugin-proposal-decorators",
    "@babel/plugin-transform-modules-commonjs",
    ["@babel/plugin-transform-regenerator", {"async": false}],
    "@babel/plugin-syntax-dynamic-import",
    "@babel/plugin-transform-destructuring",
    ["@babel/plugin-proposal-object-rest-spread", {"useBuiltIns": true}],
    "@babel/plugin-transform-parameters",
    ["@babel/plugin-transform-runtime", {"helpers": false, "polyfill": false, "regenerator": true}],
    "@babel/plugin-proposal-class-properties",
    ["@babel/plugin-transform-react-jsx", {"useBuiltIns": true}],
    "@babel/plugin-transform-react-jsx-source",
    "@babel/plugin-transform-react-jsx-self"
  ],
  "env": {
    "development": {
      "plugins": [["react-hot-loader/babel",{"esm":true}]]
    }
  }
}
```

#### 配置 jsconfig.json

```javascript
{
  "compilerOptions": {
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true
  }
}
```

#### 用 Prettier 来自动格式化代码

##### 安装 Prettier

```
yarn add -D prettier prettier-stylelint prettier-tslint
```

##### .prettierrc.js

```javascript
// https://prettier.io/docs/en/configuration.html

module.exports = {
  // 120字后折行
  printWidth: 120,

  // 制表符
  tabWidth: 2,

  // 使用制表符, 否则使用空格
  useTabs: false,

  // 单引号
  singleQuote: true,

  // 尾随逗号 <none|es5|all>
  trailingComma: 'none',

  // 括号两边添加空格
  bracketSpacing: true,

  // jsx 把 > 放置在最后一行末尾
  jsxBracketSameLine: false,

  // 语法解析 <babylon|flow|typescript|postcss|json|graphql|markdown>
  parser: 'flow',

  // 末尾添加分号
  semi: true,

  // 箭头函数参数始终放置圆括号 <avoid|always>
  arrowParens: 'always',

  // 多行 (Markdown) <always|never|preserve>
  proseWrap: 'preserve',
};
```

#### 代码检查

```
yarn add -D eslint babel-eslint eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-flowtype eslint-plugin-react eslint-config-airbnb-base@latest
```


&nbsp;

### 使用 TypeScript 书写配置

```
yarn add -D typescript ts-node @types/node @types/webpack
```

### 解析应用层

#### EAMCScript

##### 安装 Babel Loader 和 Babel 插件

```
yarn add -D babel-loader@next @babel/preset-react @babel/plugin-proposal-class-properties @babel/plugin-transform-react-jsx @babel/plugin-transform-react-jsx-source @babel/plugin-transform-react-jsx-self @babel/plugin-proposal-decorators @babel/plugin-transform-destructuring @babel/plugin-proposal-object-rest-spread @babel/plugin-transform-runtime @babel/plugin-transform-regenerator @babel/plugin-syntax-dynamic-import @babel/plugin-transform-parameters
```

##### .babelrc



##### 代码检查

```
yarn add -D eslint babel-eslint eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-flowtype eslint-plugin-react eslint-config-airbnb-base
```

#### TypeScript

##### 安装 TS Loader

```
yarn add -D ts-loader
```

##### 代码检查

```
yarn add -D tslint tslint-react tslint-microsoft-contrib
```


## HTML

```bash
yarn add -D html-webpack-plugin add-asset-html-webpack-plugin
```

## 开发服务器

```bash
yarn add -D webpack-dev-server webpack-serve
```

## 解析样式

```
yarn add -D style-loader css-loader postcss-loader postcss
yarn add -D less-loader sass-loader stylus-loader less node-sass stylus
```

### 抽取样式

```
yarn add -D mini-css-extract-plugin extract-text-webpack-plugin@next
```

### 压缩样式

```bash
yarn add -D optimize-css-assets-webpack-plugin uglifyjs-webpack-plugin
```

## 文件处理

```bash
yarn add -D file-loader url-loader
```

## 其它

```
yarn add -D clean-webpack-plugin copy-webpack-plugin
```

## 参考

[选项](https://webpack.docschina.org/configuration/#选项)

[Configuration](https://webpack.js.org/configuration/#options)

[optimization](https://webpack.js.org/configuration/optimization/)


@babel/plugin-proposal-decorators 装饰器
@babel/plugin-transform-destructuring 赋值解构 let { className, children } = this.props;
@babel/plugin-proposal-object-rest-spread 对象扩展运算 { ...props }
@babel/plugin-transform-runtime 垫片
@babel/plugin-transform-regenerator ES6 generator 支持
@babel/plugin-syntax-dynamic-import 动态导入

@babel/proposal-export-default 导出默认 export v from 'xxx'

@babel/plugin-proposal-nullish-coalescing-operator ??操作符
@babel/plugin-proposal-optional-chaining ?.操作符 (Optional Chaining)
@babel/plugin-proposal-pipeline-operator |> 管道操作符 (The Pipeline Operator) https://github.com/tc39/proposal-pipeline-operator
@babel/plugin-transform-parameters 函数参数默认值及扩展运算符
