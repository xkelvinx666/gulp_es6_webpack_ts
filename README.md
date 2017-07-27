# gulp_es6_webpack_ts
本Demo用于本人一周内学习，webpack及gulp整合，实现不基于框架的真正的模块化与工程化

尽量使用json加载配置文件，让gulpfile.js和webpack.config.js的配置高度复用。同时整理了工程化的思路

在本项目中使用个人式的敏捷开发

完成entry文件的自动扫描,在private的config和public的config中自动加载entry

在gulp中原生调用webpack，可能会遇到异步的问题

gulp 中无法使用nodejs方式在多入口情况下进行HMR，会发生无法找到对应更新问题，多入口还有可导致整个页面全局刷新，为了实现HMR即只用了webpack-dev-server命令行

偶然间看到了在browser sync 中的middleware调用webpack dev middleware 的 issues https://github.com/BrowserSync/browser-sync/issues/246,试了下，还真的成功调用起来了

将结构分成以页面为文件夹，独立文件不在放在一起了，降低耦合和误操作的可能

同时重构page的读取方式，也使用自动读取