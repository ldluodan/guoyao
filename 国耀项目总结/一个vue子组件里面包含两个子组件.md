#### 一个vue里面包含两个子组件
##### 1.user组件视图

```
<template>
    <!--所有的内容要被根节点包含起来 -->
    <div id="user">
       <div class="user">
         <div class="left">
           <ul>
             <li>
               <router-link to="/user/useradd">增加用户</router-link>
             </li>
             <li>
               <router-link to="/user/userlist">用户列表</router-link>
            </li>
          </ul>
         </div>
         <div class="right">
           <router-view></router-view>
         </div>
       </div>
    </div>
</template>
```

##### 2.配置路由视图

```
import UserAdd from '../components/User/UserAdd.vue';
import UserList from '../components/User/UserList.vue';
```

```
{

 path:'/user',
 component: User,
 children:[
   {path:'useradd',component: UserAdd},

   {path:'userlist',component: UserList}
  
 ]
 
},
```

```
<template>
    <!--所有的内容要被根节点包含起来 -->
    <div id="adduser">
        增加用户
    </div>
</template>
```

```
<template>
    <!--所有的内容要被根节点包含起来 -->
    <div id="adduser">
       用户列表
    </div>
</template>
```


