# SCSS

## 命令编译
单文件编译：

```
sass <要编译的Sass文件路径>/style.scss:<要输出CSS文件路径>/style.css
```

多文件编译：

```
sass sass/:css/
```
将项目中“sass”文件夹中所有“.scss”(“.sass”)文件编译成“.css”文件，并且将这些 CSS 文件都放在项目中“css”文件夹中。

缺点及解决方法：

开启“watch”功能，这样只要你的代码进行任保修改，都能自动监测到代码的变化，并且给你直接编译出来：

```
sass --watch <要编译的Sass文件路径>/style.scss:<要输出CSS文件路径>/style.css
```

##输出方法

在编译的时候带上参数“ --style nested”:

1. 嵌套输出方式 nested
2. 展开输出方式 expanded  
3. 紧凑输出方式 compact 
4. 压缩输出方式 compressed