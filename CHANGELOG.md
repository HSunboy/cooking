# CHANGELOG
## [v1.5.3] 2017.5.23
- cooking: fix is_installed.js

## [v1.5.2] 2017.5.8
- cooking: disable host check

## [v1.5.1] 2017.4.28
- cooking: fix is_installed.js

## [v1.5.0] 2017.2.9
- cooking: 配置文件支持传入数组
```js
var cooking = require('cooking')

module.exports = [
  cooking.set({
    entry: { web: './src/entry.js' },
    devServer: true
  }).resolve(),
  cooking.set({
    entry: { weex: './src/entry.js' },
    template: false
  }).resolve()
]
```

## [v1.4.1] 2017.2.6
- 锁定 extract-text-webpack-plugin 的版本为 beta4

## [v1.4.0] 2017.1.19
- 升级到 webpack 2.2.0

## [v1.3.2] 2017.1.16
- 兼容 webpack rc4

## [v1.3.1] 2017.1.9
- cooking: 修复不符合 webpack-dev-server 的参数（例如 extractCSS）导致报错

## [v1.3.0] 2017.1.6
- cooking: 支持指定 `static` 目录，会自动拷贝 `static` 到输出的目录下。 [为什么需要 static](https://github.com/vuejs-templates/webpack/blob/master/docs/static.md)

用法：
```js
{
  "static": true, // 默认拷贝 static 目录
  "static": "assets" // 自定义静态资源目录
  "static": ["docs", "assets"] // 多个静态资源目录
}
```

## [v1.2.12] 2016.12.21
- cooking: build 出错后正确执行 `exit(1)`
- cooking: 增加版本提示

## [v1.2.11] 2016.12.20
- cooking: 修复开发模式下无法自定义 sourceMap

## [v1.2.10] 2016.12.15
- cooking: 修复 hints 配置错误

## [v1.2.9] 2016.12.15
- cooking-cli: 升级到 webpack rc

## [v1.2.8] 2016.12.14
- cooking-cli: 升级到 webpack beta28

## [v1.2.7] 2016.12.13
- cooking: 出错状态为 1

## [v1.2.6] 2016.12.12
- cooking
  - 修复插件无法读取 cooking 版本号
  - 更改默认 host 为 `0.0.0.0`
- cooking-cli
  - 修复插件无法读取 cooking 版本号

## [v1.2.5] 2016.11.25
- cooking
  - 修复 dev server 默认配置

## [v1.2.4] 2016.11.24
- cooking-cli
  - 修复 remove/update 从旧版升级后无法使用，提示 `Only supports npm, yarn`
- cooking
  - 支持 webpack-dev-server beta11, #111

## [v1.2.3] 2016.11.21
- cooking-cli
  - 修复 Yarn 全局安装后 watch/build 无法使用, #108

## [v1.2.2] 2016.11.20
- cooking-cli
  - 修复 Yarn 全局安装时无法正确执行, #108
  - 新增 license 文件
- cooking
  - 全局安装提示错误(万年坑)
  - 新增 license 文件


## [v1.2.1] 2016.11.19
- cooking
  - 修复 publicPath 无法设置空字符串的问题
- cooking-cli
  - 修复 yarn 全局安装时提示指令不存在的问题

## [v1.2.0] 2016.11.13
- cooking-cli:
  - 支持 yarn，通过 `cooking config pm yarn` 将包管理设置成 yarn 即可
  - 支持 webpack 2 新版配置规则
  - postcss 升级到 ^1.0.0，推荐使用 `postcss` [配置文件进行配置](https://github.com/postcss/postcss-loader#usage)，原先的 postcss 仍然有效

## [v1.1.4] 2016.10.13
- cooking:
  - 去掉全局安装 cooking 的提示
  - 去掉重复依赖

## [v1.1.3] 2016.10.08
- cooking:
  - 锁定 webpack beta.22 版本

## [v1.1.2] 2016.10.02
- cooking:
  - watch 时增加 NamedModulesPlugin
  - 新增 `env` 选项，设置 definePlugin。不填时会自动设置 process.env.NODE_ENV，如果传入字符串会覆盖原来的 NODE_ENV，传入对象会和原来的配置合并
  - 修复 postcss 参数问题

## [v1.1.1] 2016.09.20
- cooking:
  - 修复 postcss 传函数时无法获取 `webpack` 参数
- cooking-cli
  - 锁定 webpack 版本号 beta22

## [v1.1.0] 2016.09.19
- cooking-cli: 修复 NODE_PATH 匹配顺序，用户配置放在最后

## [v1.0.11] 2016.09.18
 - cooking-cli: 修复 update 指令，能直接更新到最新版本
 - cooking: 只有一个配置文件时当做单配置处理（之前都是传入数组配置）

## [v1.0.10] 2016.09.16
 - cooking-cli: 加载插件时会读取本地安装的插件

## [v1.0.9] 2016.09.15
 - cooking
  - 升级 `is-global-exec`

## [v1.0.8] 2016.09.15
- cooking
  - 修复 全局安装的提示不正确，替换用 is-global-exec 检测是否是当做全局命令行工具使用

## [v1.0.7] 2016.09.14
- cooking-cli
  - 修复 watch 无法传参数

## [v1.0.6] 2016.09.14
- cooking
  - 修复 chunk 为 true 时指定的路径

## [v1.0.5] 2016.09.14
- cooking-cli
  - 修复 watch/build 无法传参数

## [v1.0.4] 2016.09.12
- cooking-cli
  - 修复 windows 下无法使用

## [v1.0.3] 2016.09.12
- cooking: 全局安装提示改成只提示不抛异常

## [v1.0.2] 2016.09.12
- 新增 chunk 为 true 的选项，会设置打包所有引用到的 package 到 vendor 文件中，并打包一份 manifest。[例子](https://github.com/vuejs-templates/webpack/blob/dist/template/build/webpack.prod.conf.js#L62-L81)
- cooking: 新增阻止全局安装的警告提示

## [v1.0.1] 2016.09.11
- 修复 plugin 无法设置的问题

## [v1.0.0] 2016.09.11
- 修复 postcss 选项配置出错的问题
- 修复 clear 在开发模式也会执行的问题

## [v1.0.0-rc.3] 2016.09.06
- 修复 cooking-cli 的依赖
- update/import/remove 支持传入多个参数

## [v1.0.0-rc.2] 2016.09.05
- 将 cooking 拆分成 `cooking-cli` 和 `cooking`(runtime) 两个部分，以后可以全局或者本地安装 cooking
- 新增 alias、externals 配置项

## [v1.0.0-beta.1] 2016.7.26
- 修复 postcss 选项

## [v1.0.0-beta] 2016.7.05
- 使用 webpack 2.1-beta
- 新增 postcss 及 postcss 选项设置
- 优化 extend 选项，支持 `['plugin', ['plugin', options]]` 的方式传入参数
- 修复 css 的 sourceMap

## [v0.6.1] 2016.8.15
- 修复 安装测试指令失败的问题
- 修复 读取配置文件内容不正确

## [v0.6.0] 2016.8.14
- 新增 测试功能 [文档](http://cookingjs.github.io/test.html)

## [v0.5.8] 2016.7.26
- 无更新，纯属为了修复手贱错发了 beta

## [v0.5.7] 2016.7.21
- 升级 webpack-hud，修复了 devServer.log 开启时部分 Android 访问页面空白

## [v0.5.6] 2016.7.01
- 新增 sourceMap 支持 boolean 和 string 填 true 将使用 `#source-map`，开发模式下默认还是 `#eval-source-map`
- 修复 build 情况下出现 `a dependency to an entry point is not allowed` 的错误

## [v0.5.5] 2016.6.29
- 修复 Windows 下打包的资源路径

## [v0.5.4] 2016.6.14
- 继续修复 publicPath 的问题

## [v0.5.3] 2016.6.14
- 修复 build 时 publicPath 未生效

## [v0.5.2] 2016.6.14
- 修复 chunk 为字符串类型时编译的结果不正确

## [v0.5.1] 2016.6.14
- 修复 不开启 devServer 的 watch 会报错

## [v0.5.0] 2016.6.12
- 用 ES6 重构

## [v0.4.9] 2016.6.10
- 新增 template 支持传入数组


## [v0.4.8] 2016.6.05
- 修复 不能省略 `.json` 后缀的问题
- 修复 watch 时 format 参数无效
- 修复 chunk 的 `hash` 应该用 `chunkhash`

## [v0.4.7] 2016.6.02
- 新增 权限错误会有提示，去掉了之前 `禁止使用 sudo` 的方式，支持使用 `sudo` 执行

## [v0.4.6] 2016.6.01 🎁
- 修复 CommonChunkPlugin 传 names 参数无效的问题
- 修复 未设置 devServer.publicPath 时应该采用 publicPath 选项的值
- 新增 build 时支持 `--output-public-path` 选项

## [v0.4.5] 2016.5.24
- 修复 extractCSS 的 hash 值
- 修复 插件安装目录移到用户目录下(`~/.cooking`)，避免每次升级都需要重新安装依赖

## [v0.4.4] 2016.5.21
- 修复 windows 下无法正常使用 [#30](https://github.com/ElemeFE/cooking/issues/30)
- 修复 锁定 webpack 版本为 0.13.0

## [v0.4.3] 2016.5.19
- 新增 开启 dev server 时默认支持将日志显示在页面上 `derServer: { log: true }`
- 更新 升级 webpack 到 0.13.x

## [v0.4.2] 2016.5.13
- 正式发布
