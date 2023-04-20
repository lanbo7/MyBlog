---
title: javascript模块化开发
date: '2023-04-18'
tags: ['javascript']
summary:
---
<TOCInline toc={props.toc} exclude="Overview" toHeading={3} /> 

### 暴露的三种方式
1.分别暴露   
2.统一暴露   
3.默认暴露
## ES6模块化教程

### 暴露方式如下：
```javascript
//使用【分别暴露】
export const teacher1 = {name:'强哥',age:15}
export const teacher2 = {name:'歌神',age:17}

//使用【统一暴露】
const stu1 = {name:'王宇',age:18}
const stu2 = {name:'宇航',age:19}
export {stu1,stu2}

//使用【默认暴露】
export default {
	school:'尚硅谷',
	address:'宏福科技园',
	subjects:['前端','java','大数据']
}

```
### 引入方式如下：
```javascript
//引入多种暴露方式的模块
import module5,{teacher1,teacher2,stu1,stu2} from './module5'
console.log(module5);
console.log(teacher1);
console.log(teacher2);
console.log(stu1);
console.log(stu2);


```

