如果我们在childScope直接对parentScope中的属性进行写操作
![](http://ww4.sinaimg.cn/large/006pZUF1jw1fbjgbwi2cnj30ax0aowfr.jpg)

我们会发现在childScope中会创建新的同名属性，然后赋值，也就是说不进行原型链的查找，也不影响parentScope中的属性

如果我们在childScope直接对parentScope中对象的某个属性进行写操作

![](http://ww1.sinaimg.cn/large/006pZUF1jw1fbjgi0fdrcj308c01edfv.jpg)

运行结果

childScope

![](http://ww4.sinaimg.cn/large/006pZUF1jw1fbjgodvcwgj305k01ymx4.jpg)

只剩下aFuncton aNumber aString了

parentScope

![](http://ww1.sinaimg.cn/large/006pZUF1jw1fbjgqkc3kqj305m067jrn.jpg)

aFuncton aNumber aString还是原来的值，而anArray与anObject对应的属性值被更改，
也就是说，直接在子作用域中修改父作用域中对象（必须为对象）的某个属性时，还是会查找原型链，修改的是父作用域下对应对象属相的值，
子作用域下不会创建相同的对象。

