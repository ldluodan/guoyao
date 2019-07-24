### 在浏览器上安装 Vue Devtools工具
##### 第一步: 首先在github下载devtools源码，地址：https://github.com/vuejs/vue-devtools


##### 第二步：下载好后进入vue-devtools-master工程 执行cnpm install, 下载依赖，然后执行npm run build，编译源程序。


##### 第三步：编译完成后，目录结构如下 修改shells、chrome目录下的mainifest.json 中的persistant为true


##### 第四步：打开谷歌浏览器的设置--->扩展程序，并勾选开发者模式  然后将刚刚编译后的工程中的shells目录下，chrome的整个文件夹直接拖拽到当前浏览器中，并选择启用，即可将插件安装到浏览器。


##### 第五步：打开一个已有的vue项目，运行项目，然后在浏览器中--->设置--->更多工具--->开发者工具，进入调试模式：


##### 第六步：发现vue.js is not detected 需要允许访问文件网址

