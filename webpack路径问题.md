## webpack 路径问题  和引入导出的关系

+ ### context

context 是 webpack 编译时的基础目录，入口起点（entry）会相对于此目录查找。
默认值为当前目录，webpack设置 context 默认值代码 
``` js
this.set("context", process.cwd());

```
#### process.cwd()即webpack运行所在的目录（等同package.json所在目录)

```js 
path.resolv（'./src'）// 返回的当前文件的的绝对路径加上后面的路劲
```

+ ###   export 和 export  default  的区别

export  和export  default  均可以导出常量 函数  文件 模块   

```js
 //a.js
export const str = "blablabla~";
export function log(sth) { 
  return sth;
}
//b.js
import { str, log } from 'a'; //也可以分开写两次，导入的时候带花括号



//export default
//a.js
const str = "blablabla~";
export default str;
对应的导入方式：

//b.js
import str from 'a'; //导入的时候没有花括号


```

 在文件和模块中 export 和import   在文件中可以出现多个; export default 只能出现一个   
