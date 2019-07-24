
```
<template>
  <div id="app">
    <!-- 使用路由 -->
    <div class="nav">
      <!--使用router-link组件来导航 -->
      <!-- 通过传入to属性指定链接-->
      <!-- router-link会默认渲染成一个a标签 -->
      <ul>
        <li><router-link to="/home">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
      </ul>
    </div>
    <!-- 路由匹配到的组件将渲染到这里-->
    <div>
      <router-view></router-view>
    </div>
    <!-- 要使用路由我们首先要在 router/index.js 文件中创建路由并配置路由映射 ，并通过export输出router到main.js文件中-->
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
body{
 background-color: #f8f8ff;
 font-family: 'Avenir', Helvetica, Arial, sans-serif;
 color: #2c3e50;
}
 
 
.nav{
 position: fixed;
 width: 108px;
 left: 40px;
}
.nav ul{
list-style: none;
 margin: 0;
 padding: 0;
}
.nav ul li{
 width: 108px;
 height: 48px;
 line-height: 48px;
border:1px solid #dadada;
text-align: center;
}
.nav ul li a{
 text-decoration: none;
}
 
.main{
 height: 400px;
 margin-left: 180px;
 margin-right: 25px;
}
 
</style>


```
