#angularjs 某些指令会创建基于原型继承的作用域（后续整理）

# angularjs中directive的scope作用域存在以下情况
## 1、创建与父作用域完全共享的scope
![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbk667yvycj30ld021mxn.jpg)


![](http://ww4.sinaimg.cn/large/006pZUF1gw1fbk68nsogcj30bz0a3761.jpg)

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbk6by8fhkj30fs064wfg.jpg)

scope默认为false

浏览器运行结果

![](http://ww4.sinaimg.cn/large/006pZUF1gw1fbk6dovxezj309v0a7t9y.jpg)
与父作用域共享了作用域
## 2、创建基于原型继承的scope

![](http://ww4.sinaimg.cn/large/006pZUF1gw1fbk6fy526mj30fs066756.jpg)

scope为true

浏览器运行结果

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbk6h7fvrnj30bb06fwf7.jpg)

再看parent

![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbk6idj67bj30bl08vq4a.jpg)


可见创建了基于原型继承的scope

## 3、以下几种方式不会创建基于原型继承的scope，也就是说会创建独立作用域。
### 1、‘@’
![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbkb0zeuirj30l201tdgb.jpg)

![](http://ww2.sinaimg.cn/large/006pZUF1gw1fbkb1wd2xaj30d9084gn5.jpg)

![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbkbnzy7lvj30lj09c409.jpg)

浏览器运行结果

![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbkbpeqg1aj30ae02rwen.jpg)

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbkbq44rpsj30cc08gmy4.jpg)

基于原型继承访问父作用域上的属性

![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbkbry79zuj308x00qglj.jpg)

![](http://ww2.sinaimg.cn/large/006pZUF1gw1fbkbsb573rj304h00n3y9.jpg)

直接通过$parent 访问父作用域上的属性

![](http://ww2.sinaimg.cn/large/006pZUF1gw1fbkbti9r01j30bd00qweg.jpg)

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbkbtubrngj301p00k0sh.jpg)

基于原型继承直接更改父作用域的非对象属性

![](http://ww1.sinaimg.cn/large/006pZUF1gw1fbkc5b63cjj30790210ss.jpg)

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbkc5ykr6sj30af08b3zg.jpg)

结果直接在自己的作用域下创建相同的属性，不会影响父作用域

基于原型继承直接更改父作用域的对象属性

![](http://ww3.sinaimg.cn/large/006pZUF1gw1fbkca8t7ibj30fw054wfd.jpg)

直接报错，他根本不会去查找原型链


总的来说：用“@”方式创建的作用域与父作用域之间是单向绑定，只能读取父作用域下的属性，不能修改。

## 2、‘=’

作用域的属性与父作用域的属性进行双向绑定，任何一方的修改均影响到对方。

## 3、‘&’

作用域把父作用域的属性包装成一个函数，从而以函数的方式读写父作用域的属性，包装方法是$parse，详情请见[API-$parse](https://docs.angularjs.org/api/ng/service/$parse)；

2和3有时间再研究吧，累死了。。。


