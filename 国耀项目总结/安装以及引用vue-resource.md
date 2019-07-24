
```
1.安装与引用
NPM：$ npm install vue-resource --save

/*引入Vue框架*/
import Vue from 'vue'
/*引入资源请求插件*/
import VueResource from 'vue-resource'

/*使用VueResource插件*/
Vue.use(VueResource)

```

```
[vue/require-v-for-key] Elements in iteration expect to have 'v-bind:key' directives.
```

```
<li v-for="item in list">
<li v-for="item in list" :key="item">

```

```
Vue报错——“Trailing spaces not allowed”
```

```
VUE初写小项目问题之命令行报错：Expected indentation of 4 spaces but found 6
```

```
解决方法:
想换回4个空格，才知道是项目初始时，默认安装ESLint（ESLint是一个语法规则和代码风格的检查工具，可以用来保证写出语法正确、风格统一的代码）的原因，关闭ESLint方法：
在vue项目中找到build文件夹 --> webpack.base.conf.js --> module
--------------------- 
```
