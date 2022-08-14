<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>漂亮的导航栏动画效果</title>
<style> 
*{

    margin: 0;
    padding: 0;
}

body{
    height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #333;
}

.tabbar{

    position: relative;
    width: 350px;
    height: 70px;
}

.tabbar ul{

    display: flex;
}

.tabbar ul li{
    list-style: none;
    width: 70px;
    height: 70px;
    position: relative;
    z-index: 1;

}


.tabbar ul li a{

    display: flex;
    justify-content: center;
    align-items: center;

    flex-direction: column;
    color: #fff;
    text-align: center;
}

.tabbar ul li a .icon{
    line-height: 70px;
    font-size: 30px;

    transition: 0.5s;
}
.tabbar ul li a .text{

    position: absolute;
    font-size: 12px;
    bottom: 13px;

    transition: 0.5s;

    transform: scale(0);
}

.tabbar ul li.active a .icon{
    font-size: 23px;

    transform: translateY(-10px);
}

.tabbar ul li.active a .text{

    transform: scale(1);
}

.active-bg{
    position: absolute;
    left: 0;
    top: 0;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    /* --c,--cc为CSS中的自定义属性,通过var函数可对其调用 */
    background-color: var(--c);
    box-shadow: 0 10px 15px var(--cc);
    transition: 0.5s;
}

/* 分别为每一个.active-bg设置颜色,阴影,位移 */
.tabbar ul li:nth-child(1).active ~ .active-bg{
    --c:#ffa502;
    --cc:#ffa50299;
    left: 0;
}
.tabbar ul li:nth-child(2).active ~ .active-bg{
    --c:#ff6348;
    --cc:#ff634899;
    left: calc(1 * 70px);
}
.tabbar ul li:nth-child(3).active ~ .active-bg{
    --c:#2ed573;
    --cc:#2ed57399;
    left: calc(2 * 70px);
}
.tabbar ul li:nth-child(4).active ~ .active-bg{
    --c:#1e90ff;
    --cc:#1e90ff99;
    left: calc(3 * 70px);
}
.tabbar ul li:nth-child(5).active ~ .active-bg{
    --c:#ff6b81;
    --cc:#ff6b8199;
    left: calc(4 * 70px);
}
</style>
     <link href="https://cdn.bootcdn.net/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
</head>
<body>
    <div class="tabbar">
        <ul>
            <li class="item active">
                <a href="#">
                    <span class="icon">
                        <i class="fa fa-home" aria-hidden="true"></i>
                    </span>
                    <span class="text">首页</span>
                </a>
            </li>
            <li class="item">
                <a href="#">
                    <span class="icon">
                        <i class="fa fa-heart" aria-hidden="true"></i>
                    </span>
                    <span class="text">动态</span>
                </a>
            </li>
            <li class="item">
                <a href="#">
                    <span class="icon">
                        <i class="fa fa-plus-circle" aria-hidden="true"></i>
                    </span>
                    <span class="text">发布</span>
                </a>
            </li>
            <li class="item">
                <a href="#">
                    <span class="icon">
                        <i class="fa fa-bell" aria-hidden="true"></i>
                    </span>
                    <span class="text">消息</span>
                </a>
            </li>
            <li class="item">
                <a href="#">
                    <span class="icon">
                        <i class="fa fa-user" aria-hidden="true"></i>
                    </span>
                    <span class="text">我的</span>
                </a>
            </li>
            <div class="active-bg"></div>
        </ul>
    </div>
    <script>
        let items = document.querySelectorAll(".item");
        //设置当前选中样式的方法
        function setActive(){
            //es6表达遍历所有.item元素,移除active样式
            items.forEach((item)=>{
                item.classList.remove("active");
            })
            this.classList.add("active");
        }
        items.forEach((item)=>{
            item.addEventListener("click",setActive);
        })
    </script>
</body>
</html>
