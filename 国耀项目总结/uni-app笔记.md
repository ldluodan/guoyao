#### 使用代码块直接创建组件模板
#####  标签内输入 ulist 回车

```
<view class="uni-list">
    <view class="uni-list-cell">
        <view class="uni-list-cell-navigate uni-navigate-right" v-for="(item,index) in list" :key="index">
            {{item.value}}
        </view>
    </view>
</view>
```
##### 在 script 标签内输入 uShowToast 回车

```
uni.showToast({
    title: '',
    mask: false
    duration: 1500
});
```
##### <text>\n横向布局</text>

```
\n代表span布局
```
