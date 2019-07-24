### uni-app列表详情 网络请求 模板语法 打开页面 页面传参


#### ulistMedia//列表模板布局


```
<view class="uni-list">
	<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in news" :key="index" 
	@tap="openinfo" :data-newsid="item.post_id">
		<view class="uni-media-list">
			<image class="uni-media-list-logo" :src="item.author_avatar"></image>
			<view class="uni-media-list-body">
				<view class="uni-media-list-text-top">{{item.title}}</view>
				<view class="uni-media-list-text-bottom uni-ellipsis">{{item.created_at}}</view>
			</view>
		</view>
	</view>
</view>
```
###### ctrl+d是删掉整行的意思
###### 输入ureq可以直接展出整段请求代码
###### :data-变量名称的方式去进行附加数据的传递 传递新闻列表每个列表的id 由于是动态属性 前面加:  :data-newsid="item.post_id" post_id:新闻id
###### @tap="openinfo" 是指页面跳转到某个页面的方法

#### ulistMedia//列表脚本

```
onLoad() {
	uni.request({
		url: 'http://unidemo.dcloud.net.cn/api/news',
		method: 'GET',
		data: {},
		success: res => {
			this.news = res.data;
		},
		fail: () => {},
		complete: () => {}
	});
},
```

```
methods: {
	openinfo(e){//打开详情页面的方法
	    console.log(e);//详情页所传的e
		var newsid = e.currentTarget.dataset.newsid;				//跳转到详情页面需要一个新闻id
		//打印出来newsid
	    //console.log(newsid);//新闻id已经知道了；下面主要跳转传递
		uni.navigateTo({
			url: '../info/info?newsid='+newsid
		});
	}
},
```
#### ulistMedia//详情模板布局

```
<view class="content">
	<view class="title">{{title}}</view>
	<view class="art-content">
		<rich-text class="richText" :nodes="strings"></rich-text>
	</view>
</view>
```

#### ulistMedia//详情脚本

```
onLoad:function(e){
			console.log(e);
			uni.request({
				url: 'http://unidemo.dcloud.net.cn/api/news/36kr/'+e.newsid,
				method: 'GET',
				data: {},
				success: res => {
					console.log(res);
					this.title=res.data.title;
					this.strings=res.data.content;//content是接口出来的html字符串
				},
				fail: () => {},
				complete: () => {}
			});
		},
```

```
rich-text
 :nodes="strings/array "
```
