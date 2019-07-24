
```
<view class="good_details">
    <view class='label'>
      <view class='tag_content active' wx:for='{{list.clinicDisease}}' wx:for-item='item'>{{list.clinicDisease}}</view>
    </view>
  </view>
```

```
.label{
  padding: 20rpx 30rpx 0rpx 30rpx;
  width:100%;
  display: flex;
  flex-wrap: wrap;
}
.tag_content{
  display: block;
  text-align: center;
  color: #4d4d4d;
  height:32rpx;
  line-height: 30rpx;
  font-size: 30rpx;
  padding: 10rpx 20rpx 10rpx 20rpx;
  border-radius: 10rpx;
  width:auto;
  margin: 0rpx 30rpx 20rpx 0rpx;
  background-color: #f1f1f1;
}
.active{
  background-color: #e3f7ff;
  color: #0fa8f7;
}
.good_details{
    background-color: #fff;
    height:175rpx;
    width:100%;
    border-top:1rpx solid #f5f5f5;
    padding-top: 12rpx;
}
```
