# From-ES2015-To-Babel-Preset-Env

由于 `ES6+` 在不同浏览器，不同版本的支持程度不同，因此出现了各种 `plugin` 去编译转换 `es6 to es5`. 如 `babel-preset-es2015` `babel-preset-es2016` ...  
而随着发展 `babel-preset-env` 产生了，它 `统一综合` 了上边提到的语法转化插件，提供了统一管理不同浏览器、版本、环境等的配置，这样我们就能根据自已的需要（`根据需要支持的浏览器、版本、环境、语法转换到什么程度`）进行自定义，根据配置自动确定需要的plugin和polyfill.  

而目前 `babel` 最新版本为 `7` ，在这个版本中babel放在了npm private scope 中(作用域)，所有7的插件都有`@babel/`前缀，而这个在 `babel6`中是没有的，因此使用时需要主要判断使用的是 *6还是7*  

**env** 是不包含 `stage-x` 的，需要的话需要自己配置安装，而stage的插件命名也添加了`-proposal`，标明这个插件是建议提案中的，随时会改动，不一定会出现在规范中.

下边对 [`@babel/preset-env`](https://babeljs.io/docs/en/babel-preset-env) 进行简单介绍.


## @babel/preset-env 主要参数

- targets
- targets.node
- targets.browsers
- spec : 启用更符合规范的转换，但速度会更慢，默认为 false
- loose：是否使用 loose mode，默认为 false
- modules：将 ES6 module 转换为其他模块规范，可选 "adm" | "umd" | "systemjs" | "commonjs" | "cjs" | false，默认为 false
- debug：启用debug，默认 false
- include：一个包含使用的 plugins 的数组
- exclude：一个包含不使用的 plugins 的数组
- useBuiltIns：为 polyfills 应用 @babel/preset-env ，可选 "usage" | "entry" | false，默认为 false

## stage-x

`stage-0` 包含 `stage-1` 包含 `stage-2` 包含 `stage-3` 包含 `stage-4`

## 参考

- [Babel](https://babeljs.io/docs/en/)
- [Upgrade to Babel 7](https://babeljs.io/docs/en/v7-migration)
- [一文带你了解babel-preset-env](https://www.jianshu.com/p/000c2670672b)
- [babel-loader中preset的各个参数es2015 react stage-0 env的含义](https://www.crifan.com/babel_loader_preset_para_es2015_react_stage_0_env/)
- [babel-polyfill VS babel-runtime VS babel-preset-env](https://juejin.im/post/5aefe0a6f265da0b9e64fa54)
- [babel-preset-env升级迁移完全指北](https://blog.5udou.cn/blog/babel-preset-envSheng-Ji-Qian-Yi-Wan-Quan-Zhi-Bei-70)
- [原生ES-Module在浏览器中的尝试](https://www.cnblogs.com/jiasm/p/9160691.html)
- [升级到Babel 7的经验](https://segmentfault.com/a/1190000016541105)
- [tc39 | proposals, stage 规范草案仓库](https://github.com/tc39/proposals)
- [如何区分Babel中的stage-0,stage-1,stage-2以及stage-3（一）](https://www.cnblogs.com/flyingzl/p/5501247.html)
- [如何区分Babel中的stage-0,stage-1,stage-2以及stage-3（二）](https://www.cnblogs.com/flyingzl/p/5504203.html)
- [再见，babel-preset-2015](https://zhuanlan.zhihu.com/p/29506685)
