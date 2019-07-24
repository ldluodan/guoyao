## 新闻列表视图

```
<!-- 新闻列表到新闻详情的aid传参开始-->
<router-link :to="'/content/'+item.aid">
  {{key}}--{{item}}
</router-link>
```

## 新闻详情视图(前提是需要获取动态路由传值列表页面的aid)

```
 var aid=this.$route.params.aid;
```

```
mounted(){
        // console.log(this.$route.params);//获取动态路由传值
        var aid=this.$route.params.aid;
        //调用请求数据的方法
        this.requestData(aid);
    },
```

```
 methods:{
        requestData(aid){
            //get请求汝故意哦跨域的话 后台java php 里面要允许跨域请求
           var api='http://www.phonegap100.com/appapi.php?a=getPortalArticle&aid='+aid; 
           this.$http.get(api).then((response)=>{
                console.log(response);
                this.list=response.body.result[0];
           },(err)=>{
                console.log(err)
           })
        }
    }
```
