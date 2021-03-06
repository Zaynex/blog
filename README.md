# 他山之石

记录阅读过的不错的文章。
## 2020.05.30
【Canvas】
- [提高 HTML5 画布性能] (https://www.html5rocks.com/zh/tutorials/canvas/performance/)

## 2020.03.28
【工程化】【ESLint】【Typescript】
- [Using ESLint and Prettier in a TypeScript Project](https://www.robertcooper.me/using-eslint-and-prettier-in-a-typescript-project)

## 2020.03.24
【AST】【Babel】
- [Understanding ASTs by Building Your Own Babel Plugin](https://www.sitepoint.com/understanding-asts-building-babel-plugin/)

关于 AST、Babel 插件，其实也没有那么深奥，后续可以按照作者的思路写一个类似 immer 的操作。

## 2020.03.23
- [Steps to Develop Global State for React With Hooks Without Context](https://blog.axlight.com/posts/steps-to-develop-global-state-for-react/)

不用 context 实现全局状态管理。可以少套用一层 Provider。

## 2020.03.21

新增计划:

1. 写一些关于思维导图布局 以及多种布局方式的实现， 业务中抽离出 svg 的绘制库。

2. 基于 Electron 的直播客户端设计(包含通信的 sdk，crash 监控，信令同步的客户端实现以及数据持久化方案）

3. canvas协同白板的设计

4. 学习编译原理


## 2019.09.08 - 2019.09.14
- [React hooks: not magic, just arrays](https://medium.com/@ryardley/react-hooks-not-magic-just-arrays-cd4f1857236e)

读后感：所有 hooks 的内部原理其实是将所有的 hook 中的 值 和 setter function 分别存入到两个数组中，通过下标一一对应。

## 2019.10.27 - 2019.11.3
- [When node.js is the wrong tool for the job](https://medium.com/@jongleberry/when-node-js-is-the-wrong-tool-for-the-job-6d3325fac85c)

nodejs 适合的场景
只是简单的数据库 CURD，没有复杂的 CPU 计算。

- 开发速度快（假设团队所有人都会 JavaScript 的话）。也许用 Go 或者 Rust 会让服务响应更快，但 Node.js 可以让开发人员更快。因此很多公司选择后者。交付是第一位。

node 的劣势
本质问题： 单进程单线程导致的。

- 缓存问题：假设我们有一个服务，将其服务的数据存在内存中（LRU Cache）。由于 Node.js 不是多线程，在实际需求场景中，需要开多个 Node 进程。如果我们开个 4 个实例，一个实例需要一个 CPU 内核。因此，每个 Server 会产生 4 份内存。这是对缓存的巨大浪费。

- 超出带宽限制

- 处理中等规模数据：现在可以放到 worker 进程中处理数据（如 JSON.parse）。

已经应该有很多解决方案了。 (Node Cluster)
