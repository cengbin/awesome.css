### Stylus的特征
* 冒号可选
* 分号可选
* 逗号可选
* 括号可选
* 变量
* 插值
* 混合书写
* 算术
* 强制类型转换
* 动态导入
* 条件
* 迭代
* 嵌套选择
* 父级参考
* 变量函数调用
* 词法作用域
* 内置函数(>25)
* 内部语言函数
* 压缩可选
* 图像内联可选
* 可执行Stylus
* 健壮的错误报告
* 单行和多行注释
* CSS字面量
* 字符转义
* TextMate捆绑
* 以及其他更多

## 真与假
Stylus近乎一切都是true, 包括有后缀的单位，甚至0%, 0px等都被认作true.  
不过，0在算术上本身是false.  
表达式（或“列表”）长度大于1被认为是真。

true例子：

```
0%
0px
1px
-1
-1px
hey
'hey'
(0 0 0)
('' '') 
```

false:

```
0 
null
false
''
```

## 其余参数(Rest Params)
参数们：arguments变量可以实现表达式的精确传递，包括逗号等等。这可以弥补args...参数的一些不足，见下面的例子：

```
box-shadow(args...)
  -webkit-box-shadow args
  -moz-box-shadow args
  box-shadow args
#login
  box-shadow #ddd 1px 1px, #eee 2px 2px 
//结果并非称心如意：
#login {
  -webkit-box-shadow: #ddd 1px 1px #eee 2px 2px;
  -moz-box-shadow: #ddd 1px 1px #eee 2px 2px;
    box-shadow: #ddd 1px 1px #eee 2px 2px;
}
//逗号给忽略了。我们现在使用arguments重新定义这个混合书写。
box-shadow()
  -webkit-box-shadow arguments
  -moz-box-shadow arguments
  box-shadow arguments
body
  box-shadow #ddd 1px 1px, #eee 2px 2px
//于是，一下子雨过天晴了：
body {
  -webkit-box-shadow: #ddd 1px 1px, #eee 2px 2px;
  -moz-box-shadow: #ddd 1px 1px, #eee 2px 2px;
  box-shadow: #ddd 1px 1px, #eee 2px 2px;
}
```

##### 注意事项
* 自定义的mixin名字不能与css属性名字一样。（mixin名会覆盖css属性名）