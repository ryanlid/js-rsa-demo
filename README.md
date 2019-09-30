# JavaScript RSA 加密解密示例


[Demo](https://js-rsa.funs.app/)

## Introduction

| 示例 | 路径 | 依赖 | 已知问题 |
| --- | --- | --- | --- |
|node-rsa|[./src/views/node-rsa.vue](./src/views/node-rsa.vue)|[node-rsa](https://github.com/rzcoder/node-rsa)|解密速度较慢|
|rsaencrypt|[./src/views/rsaencrypt.vue](./src/views/rsaencrypt.vue)|[jsencrypt](https://github.com/travist/jsencrypt) [rsaencrypt](https://github.com/lsqswl/rsaencrypt)|字符较长时会出现 null 乱码|
|jsencrypt|[./public/jsencrypt.html](./public/jsencrypt.html)|待填写（之前从网络复制而来，未记录来源)|字符较长时会出现奇怪的乱码|

## Development

```
yarn install
yarn run serve
```

or

```
npm install
npm run serve
```

> Lints and fixes files

```
yarn run lint
```

https://github.com/ryanlid/js-rsa-demo
