## webpack 路径问题

+ ### context

context 是 webpack 编译时的基础目录，入口起点（entry）会相对于此目录查找。
默认值为当前目录，webpack设置 context 默认值代码 
``` js
this.set("context", process.cwd());

```
#### process.cwd()即webpack运行所在的目录（等同package.json所在目录)
