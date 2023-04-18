---
title: Promise学习笔记
date: '2023-04-18'
tags: ['javascript', 'promise']
summary:
---

<TOCInline toc={props.toc} exclude="Overview" toHeading={3} />

## 复习准备：函数对象与实例对象

1.函数对象：将函数作为对象使用时，简称为函数对象 2.实例对象：new 构造函数或类产生的对象， 我们称之为实例对象

```javascript
//函数对象
function Person(name, age) {
  this.name = name
  this.age = age
}
Person.a = 1 //将Person看成一个对象
const p1 = new Person('老刘', 18) //p1是Person的实例对象
console.log(p1)
```

## 复习准备：同调函数，以及同步，异步回调函数的使用

```javascript
/* 
			前序知识：什么是回调？---我们定义的，我们没有调用，最终执行了。

				1.同步的回调函数: 
							理解: 立即在主线程上执行, 不会放入回调队列中。
							例子: 数组遍历相关的回调函数 
				2.异步的回调函数: 
							理解: 不会立即执行, 会放入回调队列中以后执行
							例子: 定时器回调 / ajax回调 
    */

//演示同步的回调函数
let arr = [1, 3, 5, 7, 9]
arr.forEach((item) => {
  console.log(item)
})
console.log('主线程的代码')

//演示异步的回调函数
setTimeout(() => {
  console.log('@')
}, 2000)
console.log('主线程')
```

## Promise 的介绍

1.Promise 不是回调，是一个内置的构造函数，是程序员自己 new 调用的。  
2.new Promise 的时候，要传入一个回调函数，它是同步的回调，会立即在主线程上执行，它被称为 executor 函数  
3.每一个 Promise 实例都有 3 种状态：初始化(pending)、成功(fulfilled)、失败(rejected)  
4.每一个 Promise 实例在刚被 new 出来的那一刻，状态都是初始化(pending)  
5.executor 函数会接收到 2 个参数，它们都是函数，分别用形参：resolve、reject 接收  
1.调用 resolve 函数会：  
(1).让 Promise 实例状态变为成功(fulfilled)  
(2).可以指定成功的 value。  
2.调用 reject 函数会：  
(1).让 Promise 实例状态变为失败(rejected)  
(2).可以指定失败的 reason。
代码样例如下：

```javascript
//创建一个Promise实例对象
const p = new Promise((resolve, reject) => {
  reject('ok')
})
console.log('@', p) //一般不把Promise实例做控制台输出
```

## Promise 的基本使用

```javascript
const p = new Promise((resolve, reject) => {
  //模拟一个异步任务
  /* setTimeout(()=>{
            resolve('我是成功的数据')
        },2000) */

  //真正开启一个异步任务
  const xhr = new XMLHttpRequest()
  xhr.onreadystatechange = () => {
    if (xhr.readyState === 4) {
      //readyState为4代表接收完毕，接收的可能是：服务器返回的成功数据、服务器返回的错误
      if (xhr.status === 200) resolve(xhr.response)
      else reject('请求出错')
    }
  }
  xhr.open('GET', 'https://api.apiopen.top/getJoke')
  xhr.responseType = 'json'
  xhr.send()
})

p.then(
  (value) => {
    console.log('成功了1', value)
  }, //成功的回调-异步
  (reason) => {
    console.log('失败了1', reason)
  } //失败的回调-异步
)
console.log('@')
```

## 封装一个简单的 ajax(纯回调)

```javascript
  /*
		定义一个sendAjax函数，对xhr的get请求进行封装：
				1.该函数接收4个参数：url(请求地址)、data(参数对象)、success(成功的回调)、error(失败的回调)
  */
	function sendAjax(url,data,success,error){
		//实例xhr
		const xhr = new XMLHttpRequest()
		//绑定监听
		xhr.onreadystatechange = ()=>{
			if(xhr.readyState === 4){
				if(xhr.status >= 200 && xhr.status < 300) success(xhr.response);
				else error('请求出了点问题');
			}
		}
		//整理参数
		let str = ''
		for (let key in data){
			str += `${key}=${data[key]}&`
		}
		str = str.slice(0,-1)
		xhr.open('GET',url+'?'+str)
		xhr.responseType = 'json'
		xhr.send()
	}

	sendAjax(
		'https://api.apiopen.top/getJoke',
		{page:1,count:2,type:'video'},
		response =>{
			console.log('第1次成功了',response);
			sendAjax(
				'https://api.apiopen.top/getJoke',
				{page:1,count:2,type:'video'},
				response =>{
					console.log('第2次成功了',response);
					sendAjax(
						'https://api.apiopen.top/getJoke',
						{page:1,count:2,type:'video'},
						response =>{
							console.log('第3次成功了',response);
						},
						err =>{console.log('第3次失败了',err);}
					)
				},
				err =>{console.log('第2次失败了',err);}
			)
		err =>{console.log('第1次失败了',err);}
	)
		},

```

## 封装一个简单的 ajax

```javascript
/*
		定义一个sendAjax函数，对xhr的get请求进行封装：
				1.该函数接收两个参数：url(请求地址)、data(参数对象)
				2.该函数返回一个Promise实例
							(1).若ajax请求成功,则Promise实例成功,成功的value是返回的数据。
							(2).若ajax请求失败,则Promise实例失败,失败的reason是错误提示。
  */
function sendAjax(url, data) {
  return new Promise((resolve, reject) => {
    //实例xhr
    const xhr = new XMLHttpRequest()
    //绑定监听
    xhr.onreadystatechange = () => {
      if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.status < 300) resolve(xhr.response)
        else reject('请求出了点问题')
      }
    }
    //整理参数
    let str = ''
    for (let key in data) {
      str += `${key}=${data[key]}&`
    }
    str = str.slice(0, -1)
    xhr.open('GET', url + '?' + str)
    xhr.responseType = 'json'
    xhr.send()
  })
}

const x = sendAjax('https://api.apiopen.top/getJoke', { page: 1, count: 2, type: 'video' })
x.then(
  (data) => {
    console.log('成功了', data)
  },
  (reason) => {
    console.log('失败了', reason)
  }
)
```

## Promise 的几个关键问题

### 1.如何改变一个 Promise 实例的状态?

(1)执行 resolve(value): 如果当前是 pending 就会变为 fulfilled  
(2)执行 reject(reason): 如果当前是 pending 就会变为 rejected  
(3)执行器函数(executor)抛出异常: 如果当前是 pending 就会变为 rejected

### 2.改变 Promise 实例的状态和指定回调函数谁先谁后?

1.都有可能, 正常情况下是先指定回调再改变状态, 但也可以先改状态再指定回调  
 2.如何先改状态再指定回调?  
 延迟一会再调用 then()  
 3.Promise 实例什么时候才能得到数据?  
 如果先指定的回调, 那当状态发生改变时, 回调函数就会调用, 得到数据  
 如果先改变的状态, 那当指定回调时, 回调函数就会调用, 得到数据

### 3.Promise 实例.then()返回的是一个【新的 Promise 实例】，它的值和状态由什么决定?

1.简单表达: 由 then()所指定的回调函数执行的结果决定  
 2.详细表达:  
 (1)如果 then 所指定的回调返回的是非 Promise 值 a:  
 那么【新 Promise 实例】状态为：成功(fulfilled), 成功的 value 为 a  
 (2)如果 then 所指定的回调返回的是一个 Promise 实例 p:  
 那么【新 Promise 实例】的状态、值，都与 p 一致  
 (3)如果 then 所指定的回调抛出异常:  
 那么【新 Promise 实例】状态为 rejected, reason 为抛出的那个异常

### 4.Promise 如何串连多个异步任务? -------- 通过 then 的链式调用

### 5.中断 promise 链:

(1)当使用 promise 的 then 链式调用时, 在中间中断, 不再调用后面的回调函数。
(2)办法: 在失败的回调函数中返回一个 pendding 状态的 Promise 实例。

```javascript
function sendAjax(url, data) {
  return new Promise((resolve, reject) => {
    //实例xhr
    const xhr = new XMLHttpRequest()
    //绑定监听
    xhr.onreadystatechange = () => {
      if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.status < 300) resolve(xhr.response)
        else reject('请求出了点问题')
      }
    }
    //整理参数
    let str = ''
    for (let key in data) {
      str += `${key}=${data[key]}&`
    }
    str = str.slice(0, -1)
    xhr.open('GET', url + '?' + str)
    xhr.responseType = 'json'
    xhr.send()
  })
}
//发送第1次请求
sendAjax('https://api.apiopen.top/getJoke', { page: 1 })
  .then(
    (value) => {
      console.log('第1次请求成功了', value)
      //发送第2次请求
      return sendAjax('https://api.apiopen.top/getJoke2', { page: 1 })
    },
    (reason) => {
      console.log('第1次请求失败了', reason)
      return new Promise(() => {})
    }
  )
  .then(
    (value) => {
      console.log('第2次请求成功了', value)
      //发送第3次请求
      return sendAjax('https://api.apiopen.top/getJoke', { page: 1 })
    },
    (reason) => {
      console.log('第2次请求失败了', reason)
      return new Promise(() => {})
    }
  )
  .then(
    (value) => {
      console.log('第3次请求成功了', value)
    },
    (reason) => {
      console.log('第3次请求失败了', reason)
    }
  )
```

### 6.promise 错误穿透:

(1)当使用 promise 的 then 链式调用时, 可以在最后用 catch 指定一个失败的回调,  
(2)前面任何操作出了错误, 都会传到最后失败的回调中处理了  
备注：如果不存在 then 的链式调用，就不需要考虑 then 的错误穿透。

```javascript
//另一个例子演示错误的穿透
const p = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject(-100)
  }, 1000)
})
p.then(
  (value) => {
    console.log('成功了1', value)
    return 'b'
  },
  (reason) => {
    throw reason
  } //底层帮我们补上的这个失败的回调
)
  .then(
    (value) => {
      console.log('成功了2', value)
      return Promise.reject(-108)
    },
    (reason) => {
      throw reason
    } //底层帮我们补上的这个失败的回调
  )
  .catch((reason) => {
    throw reason
  })

function sendAjax(url, data) {
  return new Promise((resolve, reject) => {
    //实例xhr
    const xhr = new XMLHttpRequest()
    //绑定监听
    xhr.onreadystatechange = () => {
      if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.status < 300) resolve(xhr.response)
        else reject(`请求出了点问题`)
      }
    }
    //整理参数
    let str = ''
    for (let key in data) {
      str += `${key}=${data[key]}&`
    }
    str = str.slice(0, -1)
    xhr.open('GET', url + '?' + str)
    xhr.responseType = 'json'
    xhr.send()
  })
}
//利用错误的穿透避免多次指定失败的回调
sendAjax('https://api.apiopen.top/getJoke2', { page: 1 })
  .then(
    (value) => {
      console.log('第1次请求成功了', value)
      //发送第2次请求
      return sendAjax('https://api.apiopen.top/getJoke', { page: 1 })
    }
    // reason => {console.log('第1次请求失败了',reason);return new Promise(()=>{})}
  )
  .then(
    (value) => {
      console.log('第2次请求成功了', value)
      //发送第3次请求
      return sendAjax('https://api.apiopen.top/getJoke', { page: 1 }, 3)
    }
    // reason => {console.log('第2次请求失败了',reason);return new Promise(()=>{})}
  )
  .then(
    (value) => {
      console.log('第3次请求成功了', value)
    }
    // reason => {console.log('第3次请求失败了',reason);return new Promise(()=>{})}
  )
  .catch((reason) => {
    console.log(reason)
  })
```

## Promise 的优势

优势：
1.  指定回调函数的方式更加灵活: 
旧的:  必须在启动异步任务前指定  
promise:  启动异步任务  =>  返回 promie 对象  =>  给 promise 对象绑定回调函数(甚至可以在异步任务结束后指定)  
2.  支持链式调用,  可以解决回调地狱问题  
(1)什么是回调地狱：  
回调函数嵌套调用,  外部回调函数异步执行的结果是嵌套的回调函数执行的条件  
(2)回调地狱的弊病：  
代码不便于阅读、不便于异常的处理  
(3)一个不是很优秀的解决方案：then 的链式调用  
(4)终极解决方案：  
async/await（底层实际上依然使用 then 的链式调用）

## async 和 await 的使用

```javascript
const p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('a')
  }, 1000)
})
const p2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('一些错误')
  }, 2000)
})
const p3 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('c')
  }, 4000)
})

;(async () => {
  try {
    const result1 = await p1
    console.log(result1)
    const result2 = await p2
    console.log(result2)
    const result3 = await p3
    console.log(result3)
  } catch (error) {
    console.log(error)
  }
})()

/*
	//测试async
 	async	function demo(){
		const result = await p1
		console.log(result);
	}
	demo()
*/
```

## await 的使用

```javascript

		return new Promise((resolve,reject)=>{
			//实例xhr
			const xhr = new XMLHttpRequest()
			//绑定监听
			xhr.onreadystatechange = ()=>{
				if(xhr.readyState === 4){
					if(xhr.status >= 200 && xhr.status < 300) resolve(xhr.response);
					else reject(`请求出了点问题`);
				}
			}
			//整理参数
			let str = ''
			for (let key in data){
				str += `${key}=${data[key]}&`
			}
			str = str.slice(0,-1)
			xhr.open('GET',url+'?'+str)
			xhr.responseType = 'json'
			xhr.send()
		})
	}

	(async()=>{
			try {
				const result1 = await sendAjax('https://api.apiopen.top/getJoke',{page:1})
				console.log('第1次请求成功了',result1);
				const result2 = await sendAjax('https://api.apiopen.top/getJoke',{page:1})
				console.log('第2次请求成功了',result2);
				const result3 = await sendAjax('https://api.apiopen.top/getJoke',{page:1})
				console.log('第3次请求成功了',result3);
			} catch (error) {
				console.log(error);
			}
	})()

```

## await 的原理：

    	 若我们使用async配合await这种写法：
         1.表面上不出现任何的回调函数
         2.但实际上底层把我们写的代码进行了加工，把回调函数“还原”回来了。
         3.最终运行的代码是依然有回调的，只是程序员没有看见。

# 宏队列与微队列

```javascript
/*
			宏队列:[宏任务1，宏任务2.....]
			微队列:[微任务1，微任务2.....]
			规则：每次要执行宏队列里的一个任务之前，先看微队列里是否有待执行的微任务
						1.如果有，先执行微任务
						2.如果没有，按照宏队列里任务的顺序，依次执行

**宏列队：**用来保存待执行的宏任务（回调），比如：定时器回调、DOM 事件回调、ajax 回调

**微列队：**用来保存待执行的微任务（回调），比如：promise的回调、MutationObserver 的回调

		*/
//代码一
setTimeout(() => {
  console.log('timeout')
}, 0)

Promise.resolve(1).then((value) => console.log('成功1', value))
Promise.resolve(2).then((value) => console.log('成功2', value))
console.log('主线程')

//代码二
/* setTimeout(()=>{
        console.log('timeout1')
      })
      setTimeout(()=>{
        console.log('timeout2')
      })

      Promise.resolve(1).then(
        value => console.log('成功1',value)
      )
      Promise.resolve(2).then(
        value => console.log('失败2',value)
      ) */

//代码三
setTimeout(() => {
  console.log('timeout1')
  Promise.resolve(5).then((value) => console.log('成功了5'))
})
setTimeout(() => {
  console.log('timeout2')
})

Promise.resolve(3).then((value) => console.log('成功了3'))
Promise.resolve(4).then((value) => console.log('失败了4'))
```
