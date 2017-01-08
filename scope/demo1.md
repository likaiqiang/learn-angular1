demo1运行结果

![](http://ww3.sinaimg.cn/large/006pZUF1jw1fbjfmwtzk6j30b00cxab7.jpg)

和js的原型继承一样，childScope中并没用aString aNumber aObject aArray aFunction这些属性，这些属性在parentScope中，如果在childScope中直接访问这些属性，会像js的原型链一样一直往上找，直到$rootScope

修改demo1，让它输出parent中的某个值

![](http://ww2.sinaimg.cn/large/006pZUF1jw1fbjfz3fggoj307z01aweh.jpg)

执行结果
![](http://ww1.sinaimg.cn/large/006pZUF1jw1fbjfzt4syyj30da02974b.jpg)

他访问到了父作用域中的值