# 使用 TypeScript 来书写 Webpack 配置 (流程)

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

## Webpack 配置

### 安装 Webpack

```
yarn add -D webpack webpack-cli @types/node @types/webpack
```

### 使用 TypeScript 书写配置

#### 安装 TypeScript

```
yarn add -D typescript ts-node
```

#### 配置 tsconfig.json

```javascript
// https://schemastore.azurewebsites.net/schemas/json/tsconfig.json

{
  "compilerOptions": {
    // 基准目录
    "baseUrl": "./src",

    // 模块名路径映射列表
    "paths": {
      "@/*": ["*"]
    },

    // 输出目录
    "outDir": "./dist",

    // 目标
    "target": "es5",

    // 模块类型
    "module": "commonjs",

    // ES 7 Decorator
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,

    // Source Map
    "inlineSourceMap": true,

    // ES6 导入
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,

    // JSON 导入 (2.9+)
    // "resolveJsonModule": true,

    // 包含库文件
    "lib": ["es7", "dom"],

    // JSX 解析方式
    "jsx": "react",

    // 模块处理方式
    "moduleResolution": "node",

    // 更漂亮的错误输出
    "pretty": true,

    // 生成定义文件
    "declaration": false,

    // 信息显示语言
    "locale": "zh-cn",


    //
    // 检查
    //

    // 严格检查
    "strict": true,

    // 以严格模式解析并为每个源文件生成 "use strict"语句
    "alwaysStrict": true,

    // 隐式 "any" 类型输出错误
    "noImplicitAny": true,

    // 严格 NULL 检查
    "strictNullChecks": true,

    // 禁用函数参数双向协变检查
    "strictFunctionTypes": true,

    // 类中初始化属性严格检查
    "strictPropertyInitialization": true,

    // 带隐式 "any" 的 "this" 表达式输出错误
    "noImplicitThis": true,

    // 若有未使用的局部变量则抛错
    "noUnusedLocals": true,

    // 若有未使用的参数则抛错
    "noUnusedParameters": true,

    // 不是函数的所有返回路径都有返回值时报错
    "noImplicitReturns": true,

    // 报告 switch 语句中遇到 fallthrough 情况的错误
    "noFallthroughCasesInSwitch": true,

    // 禁用在函数类型里对泛型签名进行严格检查
    "noStrictGenericChecks": false,

    // 不报告执行不到的代码错误
    "allowUnreachableCode": false,

    // 不报告未使用的标签错误
    "allowUnusedLabels": false,

    // 禁止对同一个文件的不一致的引用
    "forceConsistentCasingInFileNames": false,

    // 阻止对对象字面量的额外属性检查
    "suppressExcessPropertyErrors": false,

    // 阻止 --noImplicitAny 对缺少索引签名的索引对象报错
    "suppressImplicitAnyIndexErrors": false
  },

  // 排除
  "exclude": [
    "node_modules",
    "package",
    "build",
    "dist",
    "acceptance-tests",
    "webpack",
    "jest",
    "src/setupTests.ts"
  ],
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

#### TSLint

##### 安装 TSLint 和 第三方规则

```javascript
yarn add -D tslint tslint-react tslint-microsoft-contrib tslint-loader
```

##### tslint.json

```javascript
{
  "extends": [
    "tslint:latest",
    "tslint-react",
    "tslint-microsoft-contrib"
  ],
  "rules": {
    // 禁用控制台
    "no-console": [
      true,
      "log",
      "error",
      "debug",
      "info",
      "time",
      "timeEnd",
      "trace"
    ],

    // 不允许在项目的package.json中导入未列为依赖项的模块
    "no-implicit-dependencies": [
      true,
      "dev"
    ],

    // 禁止无副作用的导入
    "no-import-side-effect": false,

    // 禁止导入任何子模块
    "no-submodule-imports": [true, "@"],

    // class名, 文件同名
    "class-name": true,

    // 接口名, 需要添加前缀 I 来分区 class 和 interface
    "interface-name": [
      true,
      "always-prefix"
    ],

    // 行最大长度 160 字符
    "max-line-length": [
      true,
      160
    ],

    // 类成员显式可见性声明
    "member-access": [
      true,
      "check-accessor",
      "check-constructor",
      "check-parameter-property"
    ],

    // 成员排序
    "member-ordering": [
      true,
      {
        "order": "fields-first"
      }
    ],

    // 不允许ES6样式模块中的默认导出
    "no-default-export": false,

    // 禁止空的 interface
    "no-empty-interface": true,

    // 禁用 jsdoc 中的类型注释
    "no-redundant-jsdoc": true,

    // 禁用 require
    "no-require-imports": false,

    // 不要将`this`的成员赋值给局部变量
    "no-this-assignment": false,

    // 导入排序
    "ordered-imports": [
      true,
      {
        "import-sources-order": "any",  // 导入源排序
        "named-imports-order": "any"    // 导入命名排序
      }
    ],

    // 需要类型定义
    "typedef": [
      true,
      "call-signature",
      "arrow-call-signature",
      "parameter",
      "arrow-parameter",
      "property-declaration",
      "variable-declaration",
      "member-variable-declaration"
    ],

    // 变量名
    "variable-name": [
      true,
      "ban-keywords",
      "check-format",
      "allow-leading-underscore",
      "allow-pascal-case"
    ],

    // 需要 JSDoc 注释
    "missing-jsdoc": false,

    // 对齐
    "align": [
      true,
      "parameters",
      "arguments",
      "statements"
    ],

    // 禁止一个或多个空白行
    "no-consecutive-blank-lines": [
      true,
      1
    ],

    // 禁止尾随空格
    "no-trailing-whitespace": true,

    // 一行
    "one-line": [
      true,
      "check-open-brace",
      "check-catch",
      "check-else",
      "check-finally",
      "check-whitespace"
    ],

    // 单引号
    "quotemark": [
      true,
      "single",
      "jsx-double",
      "avoid-escape"
    ],

    // 括号内空格
    "space-within-parens": true,

    // 尾随逗号
    "trailing-comma": [
      true,
      {
        "singleline": "never",
        "multiline": "never"
      }
    ],

    // 要求或禁止空白的类型定义
    "typedef-whitespace": [
      true,
      {
        "call-signature": "nospace",
        "index-signature": "nospace",
        "parameter": "nospace",
        "property-declaration": "nospace",
        "variable-declaration": "nospace"
      },
      {
        "call-signature": "onespace",
        "index-signature": "onespace",
        "parameter": "onespace",
        "property-declaration": "onespace",
        "variable-declaration": "onespace"
      }
    ],

    // 空格
    "whitespace": [
      true,
      "check-branch",
      "check-decl",
      "check-operator",
      "check-module",
      "check-preblock",
      "check-separator",
      "check-type",
      "check-typecast"
    ],

    // 禁止使用特定的功能或全局方法
    "ban": false,

    // 对齐
    "jsx-alignment": true,

    // 禁止在 JSX 内给事件绑定 this
    "jsx-no-bind": true,

    // 禁止在 JSX 书写多行 JavaScript
    "jsx-no-multiline-js": true,

    // JSX 大括号空格
    "jsx-curly-spacing": [
      true,
      "always"
    ],

    // 禁止保留字 keywords
    "no-reserved-keywords": false,

    // 禁止自增递增和递减
    // https://github.com/airbnb/javascript/issues/540
    "no-increment-decrement": true,

    // 导出名和文件名一致, 首字母大写
    "export-name": false,

    // 函数名 (React 部分生命周期函数名就不符合 TSLint 规范)
    "function-name": false,

    // 导入名
    "import-name": false,

    // 禁止多行字符
    "no-multiline-string": true,

    // 禁止从相对路径导入
    "no-relative-imports": false,

    // 标题
    "react-a11y-titles": false,
  }
}
```

### 解析应用层

#### 安装 TS Loader

```
yarn add -D ts-loader
```

### 配置合并

```bash
yarn add -D webpack-merge @types/webpack-merge
```

### 清理目录

```bash
yarn add -D clean-webpack-plugin @types/clean-webpack-plugin
```

### 复制文件

```bash
yarn add -D copy-webpack-plugin @types/copy-webpack-plugin
```

### 处理 HTML

```bash
yarn add -D html-webpack-plugin @types/html-webpack-plugin add-asset-html-webpack-plugin
```

### 开发服务器

```bash
yarn add -D webpack-dev-server webpack-serve
```

### 处理样式

#### 处理 CSS

```bash
yarn add -D style-loader css-loader postcss-loader postcss
```

##### PostCSS

.postcssrc.js

```javascript
// https://github.com/michael-ciniawsky/postcss-load-config

module.exports = {
  plugins: {
    'postcss-flexbugs-fixes': {},
    'postcss-import': {},
    'autoprefixer': {
      'browsers': [
        '> 1%',
        'last 4 versions',
        'Firefox ESR',
        'not ie <= 9'
      ]
    }
  }
}
```

#### 处理增强样式表

```bash
yarn add -D less-loader sass-loader stylus-loader less node-sass stylus
```

#### 样式抽取

```bash
yarn add -D mini-css-extract-plugin @types/mini-css-extract-plugin extract-text-webpack-plugin@next @types/extract-text-webpack-plugin
```

#### 样式压缩

```bash
yarn add -D uglifyjs-webpack-plugin @types/uglifyjs-webpack-plugin optimize-css-assets-webpack-plugin @types/optimize-css-assets-webpack-plugin
```

## 参考

[Configuration Languages](https://webpack.js.org/configuration/configuration-languages/#typescript)

[Configuration](https://webpack.js.org/configuration/)

[Output](https://webpack.js.org/configuration/output/)

[Resolve](https://webpack.js.org/configuration/resolve/)

[DevServer](https://webpack.js.org/configuration/dev-server/)

[SplitChunksPlugin](https://webpack.js.org/plugins/split-chunks-plugin/)

[MiniCssExtractPlugin](https://webpack.js.org/plugins/mini-css-extract-plugin/)

[ExtractTextWebpackPlugin](https://webpack.js.org/plugins/extract-text-webpack-plugin/)

[UglifyjsWebpackPlugin](https://webpack.js.org/plugins/uglifyjs-webpack-plugin/)
