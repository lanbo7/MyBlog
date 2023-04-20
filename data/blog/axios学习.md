---
title: axios学习
date: '2023-04-18'
tags: ['javascript','axios']
summary:
---
<TOCInline toc={props.toc} exclude="Overview" toHeading={3} /> 
## 准备工作：请求方式：query和params的区别

query的请求方式的URL:
http://localhost:8080/login?name=123&&password=123   
params请求方式的URL:
http://localhost:8080/login/123/123


## axios的基本使用
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>axios的基本使用</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn1">点我获取所有人</button><br/><br/>
		<button id="btn2">点我获取某个人</button>
		<input id="person_id" type="text" placeholder="请输入一个人的id"><br/><br/>
		<button id="btn3">点我添加一个人</button>
		<input id="person_name" type="text" placeholder="请输入名字">
		<input id="person_age" type="text" placeholder="请输入年龄"><br/><br/>
		<button id="btn4">点我更新一个人</button>
		<input id="person_update_id" type="text" placeholder="请输入一个人的id">
		<input id="person_update_name" type="text" placeholder="请输入名字">
		<input id="person_update_age" type="text" placeholder="请输入年龄"><br/><br/>
		<button id="btn5">点我删除一个人</button>
		<input id="person_delete_id" type="text" placeholder="请输入删除的id">
		<!-- 
				1.axios调用的返回值是Promise实例。
				2.成功的值叫response，失败的值叫error。
				3.axios成功的值是一个axios封装的response对象，服务器返回的真正数据在response.data中
				4.携带query参数时，编写的配置项叫做params
				5.携带params参数时，就需要自己手动拼在url中
		 -->

		<script type="text/javascript" >
			//获取按钮
			const btn1 = document.getElementById('btn1')
			const btn2 = document.getElementById('btn2')
			const btn3 = document.getElementById('btn3')
			const btn4 = document.getElementById('btn4')
			const btn5 = document.getElementById('btn5')
			const personId = document.getElementById('person_id')
			const personName = document.getElementById('person_name')
			const personAge = document.getElementById('person_age')
			const personUpdateId = document.getElementById('person_update_id')
			const personUpdateName = document.getElementById('person_update_name')
			const personUpdateAge = document.getElementById('person_update_age')
			const personDeleteId = document.getElementById('person_delete_id')

			//获取所有人---发送GET请求---不携带参数
			btn1.onclick = ()=>{
				//完整版
				/* axios({
					url:'http://localhost:5000/persons', //请求地址
					method:'GET',//请求方式
				}).then(
					response => {console.log('请求成功了',response.data);},
					error => {console.log('请求失败了',error);}
				) */

				//精简版
				axios.get('http://localhost:5000/persons').then(
					response => {console.log('请求成功了',response.data);},
					error => {console.log('请求失败了',error);}
				)
			}
			
			//获取所某个人---发送GET请求---携带query参数
			btn2.onclick = ()=>{
				//完整版
				/* axios({
					url:'http://localhost:5000/person',
					method:'GET',
					params:{id:personId.value} //此处写的是params，但携带的是query参数
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				) */

				//精简版
				axios.get('http://localhost:5000/person',{params:{id:personId.value}}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
			
			//添加一个人---发送POST请求---携带json编码参数 或 urlencoded编码
			btn3.onclick = ()=>{
				//完整版
				/* axios({
					url:'http://localhost:5000/person',
					method:'POST',
					data:{name:personName.value,age:personAge.value}//携带请求体参数（json编码）
					//data:`name=${personName.value}&age=${personAge.value}`//携带请求体参数（urlencoded编码）
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				) */

				//精简版
				axios.post('http://localhost:5000/person',`name=${personName.value}&age=${personAge.value}`).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}

			//更新一个人---发送PUT请求---携带json编码参数 或 urlencoded编码
			btn4.onclick = ()=>{
				//完整版
				/* axios({
					url:'http://localhost:5000/person',
					method:'PUT',
					data:{
						id:personUpdateId.value,
						name:personUpdateName.value,
						age:personUpdateAge.value
					}
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				) */

				//精简版
				axios.put('http://localhost:5000/person',{
					id:personUpdateId.value,
					name:personUpdateName.value,
					age:personUpdateAge.value
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
			
			//删除一个人---发送DELETE请求---携带params参数
			btn5.onclick = ()=>{
				axios({
					url:`http://localhost:5000/person/${personDeleteId.value}`,
					method:'DELETE',
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
		</script>
	</body>
</html>
```

## axios的常用配置项

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>2_axios常用配置项</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我获取所有人</button><br/><br/>
		<button id="btn2">点我获取测试数据</button><br/><br/>
		<button id="btn3">点我获取笑话信息</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')
			const btn2 = document.getElementById('btn2')
			
			//给axios配置默认属性
			axios.defaults.timeout = 2000
			axios.defaults.headers = {school:'atguigu'}
			axios.defaults.baseURL = 'http://localhost:5000'

			btn.onclick = ()=>{
				axios({
					url:'/persons', //请求地址
					method:'GET',//请求方式
					//params:{delay:3000},//配置query参数
					//data:{c:3,d:3},//配置请求体参数(json编码)
					//data:'e=5&f=6',//配置请求体参数(urlencoded编码)
					//timeout:2000,//配置超时时间
					//headers:{school:'atguigu'} //配置请求头
					//responseType:'json'//配置响应数据的格式(默认值)
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
		
			btn2.onclick = ()=>{
				axios({
					url:'/test1', //请求地址
					method:'GET',//请求方式
					//timeout:2000,//配置超时时间
					//headers:{school:'atguigu'} //配置请求头
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
			
			btn3.onclick = ()=>{
				axios({
					url:'https://api.apiopen.top/getJoke'
				})
			}
		</script>
	</body>
</html>
```
## axios的create方法
````html

<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>3_axios.create方法</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<!-- 
				axios.create(config)
						1. 根据指定配置创建一个新的axios, 也就是每个新axios都有自己的配置
						2. 新axios只是没有取消请求和批量发请求的方法, 其它所有语法都是一致的
						3. 为什么要设计这个语法?
								需求: 项目中有部分接口需要的配置与另一部分接口需要的配置不太一样
		-->
		<button id="btn">点我获取所有人</button><br/><br/>
		<button id="btn2">点我获取测试数据</button><br/><br/>
		<button id="btn3">点我获取笑话信息</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')
			const btn2 = document.getElementById('btn2')
			const btn3 = document.getElementById('btn3')

			const axios2 = axios.create({
				timeout:3000,
				//headers:{name:'tom'},
				baseURL:'https://api.apiopen.top'
			})

			//给axios配置默认属性
			axios.defaults.timeout = 2000
			axios.defaults.headers = {school:'atguigu'}
			axios.defaults.baseURL = 'http://localhost:5000'

			btn.onclick = ()=>{
				axios({
					url:'/persons', //请求地址
					method:'GET',//请求方式
					//params:{delay:3000},//配置query参数
					//data:{c:3,d:3},//配置请求体参数(json编码)
					//data:'e=5&f=6',//配置请求体参数(urlencoded编码)
					//timeout:2000,//配置超时时间
					//headers:{school:'atguigu'} //配置请求头
					//responseType:'json'//配置响应数据的格式(默认值)
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
		
			btn2.onclick = ()=>{
				axios({
					url:'/test1', //请求地址
					method:'GET',//请求方式
					//timeout:2000,//配置超时时间
					//headers:{school:'atguigu'} //配置请求头
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
			
			btn3.onclick = ()=>{
				axios2({
					url:'/getJoke',
					method:'GET'
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}
		</script>
	</body>
</html>
````
## axios的拦截器
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>4_axios中的拦截器</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我获取所有人</button><br/><br/>
		<!-- 
				axios请求拦截器
					1.是什么？
							在真正发请求前执行的一个回调函数
					2.作用：
							对所有的请求做统一的处理：追加请求头、追加参数、界面loading提示等等
				
				axios响应拦截器
					1.是什么？
							得到响应之后执行的一组回调函数
					2.作用：
							若请求成功，对成功的数据进行处理
							若请求失败，对失败进行统一的操作
		-->
		<script type="text/javascript" >
			const btn = document.getElementById('btn')

			//请求拦截器
			axios.interceptors.request.use((config)=>{
				console.log('请求拦截器1执行了');
				if(Date.now() % 2 === 0){
					config.headers.token = 'atguigu'
				}
				return config
			})

			//响应拦截器
			axios.interceptors.response.use(
				response => {
					console.log('响应拦截器成功的回调执行了',response);
					if(Date.now() % 2 === 0) return response.data
					else return '时间戳不是偶数，不能给你数据'
				},
				error => {
					console.log('响应拦截器失败的回调执行了');
					alert(error);
					return new Promise(()=>{})
				}
			)
			
			btn.onclick = async()=>{
				const result = await axios.get('http://localhost:5000/persons21')
				console.log(result);
			}
		</script>
	</body>
</html>
```
## axios取消请求1
```html

<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>5_axios中取消请求</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我获取测试数据</button><br/><br/>
		<button id="btn2">取消请求</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')
			const btn2 = document.getElementById('btn2')
			const {CancelToken} = axios //CancelToken能为一次请求“打标识”
			let cancel

			btn.onclick = async()=>{
				axios({
					url:'http://localhost:5000/test1?delay=3000',
					cancelToken:new CancelToken((c)=>{ //c是一个函数，调用c就可以关闭本次请求
						cancel = c
					})
				}).then(
					response => {console.log('成功了',response.data);},
					error => {console.log('失败了',error);}
				)
			}

			btn2.onclick = ()=>{
				cancel()
			}

			
		</script>
	</body>
</html>
```
## axios取消请求2
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>6_axios中取消请求2</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我获取测试数据</button><br/><br/>
		<button id="btn2">取消请求</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')
			const btn2 = document.getElementById('btn2')
			const {CancelToken,isCancel} = axios //CancelToken能为一次请求“打标识”
			let cancel

			btn.onclick = async()=>{
				if(cancel) cancel()
				axios({
					url:'http://localhost:5000/test1?delay=3000',
					cancelToken:new CancelToken((c)=>{ //c是一个函数，调用c就可以关闭本次请求
						cancel = c
					})
				}).then(
					response => {console.log('成功了',response.data);},
					error => {
						if(isCancel(error)){
							//如果进入判断，证明：是用户取消了请求
							console.log('用户取消了请求，原因是：',error.message);
						}else{
							console.log('失败了',error);
						}
					}
				)
			}

			btn2.onclick = ()=>{
				cancel('任性，就是不要了')
			}

			
		</script>
	</body>
</html>
```

## axios取消请求3
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>7_axios中取消请求3</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我获取测试数据</button><br/><br/>
		<button id="btn2">取消请求</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')
			const btn2 = document.getElementById('btn2')
			const {CancelToken,isCancel} = axios //CancelToken能为一次请求“打标识”
			let cancel

			axios.interceptors.request.use((config)=>{
				if(cancel) cancel('取消了')
				config.cancelToken = new CancelToken((c)=> cancel= c)
				return config
			})

			axios.interceptors.response.use(
				response => {return response.data},
				error => {
					if(isCancel(error)){
						//如果进入判断，证明：是用户取消了请求
						console.log('用户取消了请求，原因是：',error.message);
					}else{
						console.log('失败了',error);
					}
					return new Promise(()=>{})
				}
			)

			btn.onclick = async()=>{
				const result = await axios.get('http://localhost:5000/test1?delay=3000')
				console.log(result);
			}

			btn2.onclick = ()=>{
				cancel('任性，就是不要了')
			}

			
		</script>
	</body>
</html>
```
## axios批量发送请求
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8" />
		<title>8_axios批量发送请求</title>
		<script type="text/javascript" src="./js/axios.min.js"></script>
	</head>
	<body>
		<button id="btn">点我批量发送请求</button><br/><br/>
		<script type="text/javascript" >
			const btn = document.getElementById('btn')

			btn.onclick = async()=>{
				axios.all([
					axios.get('http://localhost:5000/test1'),
					axios.get('http://localhost:5000/test2?delay=3000'),
					axios.get('http://localhost:5000/test3'),
				]).then(
					response => {console.log(response);},
					error => {console.log(error);}
				)
			}
		</script>
	</body>
</html>
```
