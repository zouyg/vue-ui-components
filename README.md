# 轱辘 - 一个 Vue UI 组件

[![Build Status](https://travis-ci.org/zouyg/vue-ui-components.svg?branch=master)](https://travis-ci.org/zouyg/vue-ui-components)

## 介绍

这是一个初学者在学习vue过程中做的一个UI框架，希望对你有用。

## 开始使用

1. CSS 样式

    使用本框架前，请在 CSS 中开启border-box
    ```
    *, *::before, *::after { box-sizing: border-box; }
    ```
    IE 8 及以上浏览器都支持此样式。

    ```
    html {
        --button-height: 32px;
        --font-size: 14px;
        --button-bg: white;
        --button-active-bg: #eee;
        --border-radius: 4px;
        --color: #333;
        --border-color: #999;
        --border-color-hover: #666;
    }
    ```
    你还需要设置默认颜色等变量（后续会改为SCSS变量）

    IE 15及以上， chrome， firefox, android4.6及以上 浏览器支持此样式，

2. 安装 gulu
```
npm i --save gulu-zouyg-1
```
3. 引入 gulu
```
    import {Button, ButtonGroup, Icon} from 'gulu-zouyg-1'
    import 'gulu-zouyg-1/dist/index.css'

    export default {
        name: "App",
        components: {
            HelloWorld,
            'g-button': Button,
            'g-icon': Icon
        }
    }
```

## 文档

## 提问

## 变更记录

## 联系方式

## 贡献代码