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

## 3、