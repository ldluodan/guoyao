#### 使用swiper时踩过的坑（解决一个网页使用多个swiper冲突问题）
##### 1、如果一个页面中要使用多个轮播图（用swiper实现）,最好的方法，也是最不容易出错的方法是，加一个类名和swiper-container同级的类。，然后初始化swiper时用这个新增加的类，不要用swiper-container，如下示例：

```
 <div class="swiper-container banner_swiper">
    <div class="swiper-wrapper">
        <div class="swiper-slide" >
            <div class="banner_txt">
                <span class="position_info">前法官+前检察官</span>
                <h2 class="name_info">刑事律师的办案组合</h2>
                <p class="detail_info">宣言以及律所实力经验展示内容部分占位符，我们竭诚为您服务</p>
                <span class="consult_us">咨询我们</span>
            </div>
            <img src="/criminal_img/banner.png"/>
        </div>
    </div>
```
##### 初始化的时候：

```
 var mySwiper = new Swiper ('.banner_swiper', {
        direction: 'horizontal',
        // loop: true,
        paginationClickable :true,
        navigation: {
            nextEl: '.banner_info .swiper-button-prev',
            prevEl: '.banner_info .swiper-button-next',
        },
        pagination: {
            el: '.banner_back_img .swiper-pagination',
            clickable :true
        },
        speed:300,
        // autoplay : true,
        effect : 'slide',
        // thumbs: {
        //     swiper: galleryThumbs,
        // },
```
##### 2、如果你仔细看了我上面的代码，会发现我在添加分页器和前进后退按钮的时候也给前面加了一个类名，个人认为是有必要的，因为如果不加的话，同一个页面中使用两次swiper的时候就会出现，点击其中一个前进后退按钮的时候，另外一个轮播图居然也奇迹般的在运动，原因也很简单，如果我们只是单单写一个

```
navigation: {
    nextEl: '.swiper-button-prev',
    prevEl: '.swiper-button-next',
}
```

```
那其实就相当于我们在写css样式的时候，他会找到所有了类名为swiper-button-prev的元素，所以就会出现，点击别的轮播图的前进后退按钮，当前的这个轮播图也随着运动;所以我们最好是加一个父级的类名，这样的话，就告诉swiper对象，控制他的前进后退按钮具体是哪一个
```
##### 3、前进后退按钮和分页器其实是可以不放在swiper-container容器中的，或者说是可以随便放的，放在任何你想要放的地方都是可以的。只要在初始化的时候关联一下即可，如下示例：


```
 <div class="work_process_control">
            <h3 class="title">我们能为您做的</h3>
            <p class="info">我们的刑辩律师能为您的亲人做什么？</p>
            <div class="swiper-pagination"></div>//分页器
        </div>
        <div class="swiper-container process_swiper">
            <div class="swiper-wrapper">
                <div class="swiper-slide" >
                    <div class="process_item">
                        <h2 class="process_title"><span>1.</span>审判阶段（包括一审程序、二审程序）</h2>
                        <p class="process_line"></p>
                        <p class="process_content">复制所有的案卷材料，变更强制措施申请，参加一审案件的开庭审理，提出无罪或者罪轻的辩护意见，撰写上诉状，参加二审案件的开庭审理，提出辩护意见等。</p>
                    </div>
                </div>
            </div>
            <!--<div class="swiper-button-prev"></div>&lt;!&ndash;左箭头&ndash;&gt;-->
            <!--<div class="swiper-button-next"></div>&lt;!&ndash;右箭头&ndash;&gt;-->
            <div class="process_mark"></div>
        </div>
```
##### 看上面的代码，我的分页器并没有放在swiper-container 中，而是放在另外一个work_process_control中，关联也很简单


```

var workProcess = new Swiper('.process_swiper',{
    direction : 'vertical',
    loop: true,
    autoplay: {
        disableOnInteraction: false,
    },
    paginationClickable :true,
    pagination: {
        el: '.work_process_control .swiper-pagination',
        clickable :true,
        renderBullet: function (index, className) {
            return '<span class="' + className + '">' + (index + 1) + '</span>';
        },
    },
    navigation: {
        nextEl: '.process_swiper .swiper-button-next',
        prevEl: '.process_swiper .swiper-button-prev',
    },
    loopedSlides: 2,
    slidesPerView : 2,
    spaceBetween : 40,
})
```
##### 4.监听点击前进后退按钮，做一些操作：mySwiper.navigation.nextEl.onclick = function(){}

```
 mySwiper.navigation.nextEl.onclick = function(){
            let index = mySwiper.activeIndex
      $('.banner_back_img').find('.banner_detail').eq(index).show()
      $('.banner_back_img').find('.banner_detail').eq(index).siblings('.banner_detail').hide()
        $(this).addClass('btn_active')
        $('.banner_back_img .swiper-button-next').removeClass('btn_active')
    }
    mySwiper.navigation.prevEl.onclick = function(){
        let index = mySwiper.activeIndex
        $('.banner_back_img').find('.banner_detail').eq(index).show()
        $('.banner_back_img').find('.banner_detail').eq(index).siblings('.banner_detail').hide()
        $(this).addClass('btn_active')
        $('.banner_back_img .swiper-button-prev').removeClass('btn_active')
    }
```
##### 5.关于swiper自动轮播的图片,加了autoplay 属性/但是当用户操作swiper之后，默认会停止自动轮播。 disableOnInteraction 默认为true：停止。如果设置为false，用户操作swiper之后自动切换不会停止，每次都会重新启动autoplay。
操作包括触碰，拖动，点击pagination等。

```

autoplay: {
        disableOnInteraction: false,
    }
```
##### 6、鼠标移入，轮播暂停，鼠标移出，轮播继续

```

mySwiper.el.onmouseover = function(){
    mySwiper.autoplay.stop();
}
// //鼠标覆盖停止自动切换与隐藏前进后退按钮
mySwiper.el.onmouseout = function(){
    mySwiper.autoplay.start();
}
```
