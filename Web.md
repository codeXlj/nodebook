# html/css

### 1. html部分 {#1-html部分}

``` javascript
一、） 锚点:  name只能加在a元素上，加在其他元素上不会生效。
    1.点击a跳转到a：
    <a href="#love">点我</a>
    <a href="" name="love">到这</a>
    2.点击a跳转到块级元素：
    <a href="#love">点我</a>
    <h1 id="love">到这</h1>
    3.实体字符:
     空格 &nbsp
     <  &lt
     >  &gt
    4.设置光标的样式   cursor:help/pointer
    5.设置层叠顺序    z-index = number
    7.火狐获取页面内容      ctrl+i
    9.python编码问题: 
        "code-runner.executorMap": {
                "python":"set PYTHONIOENCODING=utf8 && python"}
    
 *** 全局样式表内容:
    body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,fieldset,legend,input,textarea,button,p,
    blockquote,th,td {margin: 0;padding: 0}
    body{text-align: center;}
    ul,ol,li{list-style-type: none;} 
    input,button,img{border: none;vertical-align: middle;}
二、） 无序列表:
    <dl>
        <dt>主题</dt>
        <dd>描述</dd>
    </dl>
三、） align 单元格的水平对齐方式
    valign 单元格垂直对齐方式
    colspan 跨列 水平合并
    rowspan 跨行 垂直合并
四、）表单的提交:
    <form action="提交的地址" name="表单的名称" method="提交的方式"></form>
  ***所有的内容都需要建立在<form></form>标签中
    type = file 提交文件 （需要指明路径 enctype=？）
    type = hidden 隐藏提交的内容
    img
    1. 下拉列表:
    <select name="city" id="#">
        <option value="BJ">北京</option>
        <option value="SH">上海</option>
        <option value="HB">河北</option>
        <option value="TJ">天津</option>
    </select>
    * 可对内容进行分组在select标签中进行:  双标签: <optgroup label="组名"></optgroup> （组名只是加粗,不可选）
    2. 多行文本框:
        <textarea name="liuyan" id="#" cols="30" rows="10"></textarea>
    3. 关于表单的属性:
        type 输入的类型
        name 名称   value 值
        selected 配合option使用 （设置为默认选项）
        checked  配合radio和checkbox使用 （设置为默认选项）
        readonly 只读
        disable  禁用
    4. html5 常用新增类型
        邮箱: <input type="email">
        搜索: <input type="search">
        网址: <input type="url">
        数字: <input type="number" min="最小值" max="最大值" step="步长">
        范围(滑块): <input type="range" min="最小值" max="最大值" value="" step="">
        颜色: <input type="color">
        电话: <input type="tel">
        日期: <input type="date">
        周: <input type="week">
        月: <input type="month">
    5. html5 常用新增类型的属性
        placeholder="" 给予提示
        autofocus 自动聚焦
        required 设置为必填项
        multiple 用于给输入多个 邮箱、网址（中间需用逗号隔开）
        minlength 最小长度
        maxlength 最大长度

    1.视频
        <video src="">相当于alt</video>
        支持的格式: mp4、ogg(移动端)、webM(高清格式)
      属性:
        src 必要属性  路径
        autoplay 自动播放
        loop  循环播放
        controls  显示控制面板
        muted  初始静音
        poster 视频播放前显示一张图片
        height 高度
        width 宽度
    2.音频
    <audio src="">相当于alt</audio>
    支持的格式: mp3、o gg(移动端)、wav
      属性:
      src 必要属性 路径
      autoplay 自动播放
      loop 循环播放
      muted 初始静音
      controls 控制面板
      酷狗kgm转mp3  https://oiukaineshare.lanzoui.com/isuJJpu6lcj
   3.资源
      <source/>
```

### 2. css - 选择器 {#2-css---选择器}

``` javascript
1.外部样式表导入式:
      @import "" | @import url("") | link
      区别: import 先解析html再解析css 而link是同时解析
           import 不可以导入其他内容,而link可以 （可将link中rel属性值改为icon）
   2.选择器:
      1)基础选择器: ID选择器、类选择器、元素选择器、全局选择器、合并选择器
      选择器的优先级:
          行内样式 > ID选择器 > 类选择器 > 元素选择器 > 全局选择器
            1000      100       10         1
      2)关系选择器:
        ①后代选择器:
            选择器1   选择器2{}
            选中所有后代
        ②子代选择器:
            选择器1 > 选择器2{}
            选中所有子代
        ③相邻兄弟选择器:
            选择器1 + 选择器2{}
            平级 挨着后面的一个兄弟
        ④通用兄弟选择器:
            选择器1 ~ 选择器2{}
            平级 挨着后面的所有兄弟
     3)伪类选择器:
        :链接 表示一种状态
        ①:link 点击之前(只适用于a)
        ②:visited 点击之后(只适用于a)
        ③:hover 鼠标悬停(适用于所有元素)
        ④:active 鼠标按下(适用于所有元素)
        顺序: 先爱后恨 l_v_h_a_
     4)css3 新增伪类选择器:
        ①:first-child  第一个元素是、、、
        ②:last-child   最后一个元素是、、、
        ③:nth-child(number/even/odd/倍数)  第几个元素是、、、
         （even 偶数; odd 奇数; 2n、3n 倍数）
        ④:focus  获取焦点时的样式
        ⑤:checked  默认被选中时的样式 (配合单选按钮和复选按钮使用)
     *  设置整个元素的透明度：
         opacity: ; 取值为0-1
     5)伪对象选择器:  伪元素选择器
         ①插入文字和图片
         :before/::before{
            content:"";
         }
         :after/::after{
            content:"";
         }
        ②自定义插入内容:
        :before/::before{
            content:"";
            display:block;
            width:;
            height:;
            background-color:;
         }
         ③清除浮动:
         浮动元素的父元素::after{
            content:"";
            display:block;
            clear:both;
         }
```

### 3. css - 其他 {#3-css---其他}

``` javascript
3.文本的属性:
        text-align: left;
        text-decoration: underline | none;
        text-transform: uppercase(大写) | lowercase(小写) | capitalize(首字母大写)
        text-indent: 首行缩进 单位[px(绝对路径)、em(相对路径)、rem(相对路径)]
   4.字体的属性:
        font-family: Arial;    字体
        font-size: 17px;       大小
        color: #8000ff;        颜色
        font-style: italic;    样式
        font-weight: bold      加粗
   5.列表的属性:
        设置项目的符号: list-style-type: none`
        设置项目的符号为图片: list-style-image: url("路径")
   6.行高:
        设置一行的高度
        当行高等于高时 一行文字垂直居中
   7.背景属性:
        background-color: transparent(默认透明);
        颜色的取值:关键字、rgb、rgba（0,0,0,.5）a表示的是透明度、十六进制
     背景图片:
        background-image: url("")  默认是水平垂直平铺
        背景图片是否平铺:
        background-repeat: repeat | no-repeat | repeat-x | repeat-y
     背景图片的大小:
        background-size: x y (取值px、%、cover、contain)
     背景图片定位:
        background-position: x y (取值px、%、center、top、bottom、left、right、负值)
     背景图片固定:
        background-attachment: scroll(动 默认) | fixed(固定不动)
     背景属性的简写:
        background: 颜色、图片、平铺、大小、定位、固定
   8.内容溢出:
        overflow: hidden(溢出部分隐藏) | auto(溢出时显示滚动条) | scroll(一直显示滚动条)
   9.一行文字溢出时省略号显示:
        white-space: nowrap (文字在同一行中显示)
        overflow: hidden (溢出部分隐藏)
        text-overflow:ellipsis (文字溢出部分省略号显示)
   10.表格的属性:
        width height 宽和高
        background-image: url("")  背景图片
        text-align: ;   表格内容的水平对齐方式
        vertical-align: top | bottom | center  单元格内容的垂直对齐方式
        border-collapse: collapse 边框的折叠/隐藏(相当于cellspacing="0")
      字符之间的距离:
        letter-spacing: ; 可以取正值/负值
        vertical-align: ; 在td中-td内容的对齐方式  离开td-容器中元素和内容的对齐方式
   11.border 边框
        border-style: solid | dashed | dotted | double | none  必须属性 默认宽度为3px
                       实线     虚线      点线     双实线    不显示
        border-width: ;
        border-color: ;
        *简写: border: 1px solid red;
        单边属性:
            border-top/bottom/left/right: ;
                border-top-style/width/color: ;
            简写为: border-top: 1px solid red;
   12.padding 内边距 设置内容距边框的距离 (不能取负值和auto)
        padding: value; value可以取1-4个值
        单边:
        padding-top/bottom/left/right;
   13.margin  外边距  设置元素之间的距离  (可以取负值和auto)
        margin: value; value可以取1-4个值
        单边:
        margin-top/bottom/left/right;
        1) 块级元素水平居中:
            div{width: ; margin: 0,auto;}
        2) 垂直方向上外边距合并时 取较大值;
   14.块级元素和行内元素的区别:
        1)块级元素独占一行,行内元素在同一行显示
        2)块级元素的宽度默认为100%,行内元素默认宽度由内容撑开
        3)块级元素可以设置宽高,行内元素设置宽高不生效
        4)块级元素可以设置padding和margin的四周,行内元素只能设置padding和margin的左右
        5)布局时 块级元素可以包含块级元素和行内元素,行内元素一般不包含块级元素
        6)块级元素: div,p,h1-h6,hr,ul,li,ol,di,dt,dd,table,tr,td,th,form,header,nav,footer,aside,section,article...
        7)行内元素: a,img,video,audio,span,b,i,u,s,del,sup,sub,em,strong,input,button...
   15.居中:
        1)元素内容的水平居中
            text-align:center ;
        2)块级元素水平居中
            div{width: ; margin:0 auto; }
        3)一行文字垂直居中:(行高等于高)
            line-height: height
```

### 4. css - 盒模型 {#4-css---盒模型}

``` javascript
 17.盒模型:
        1)标准盒模型 w3c盒模型:
            ①组成部分:
            content+padding+border+margin
            ②实际宽度:
            width+padding+border+margin
        2)怪异盒模型 IE盒模型:
            ①组成部分:
            content+padding+border+margin
            ②实际宽度：
            width+margin
        3)标准盒模型和怪异盒模型转换:
            box-sizing:content-box; 默认值 标准盒模型
            box-sizing:border-box   怪异盒模型
        4)弹性盒模型  伸缩盒模型 flex box:
            在弹性盒模型中float和clear不生效
            1)作用:
                适应不同的屏幕大小,多用于移动端的布局;
            2)父元素的属性:
                ①开启弹性盒模型
                display:flex;
                开启弹性盒后,子元素默认水平排列;

                ②弹性盒的方向
                flex-direction:row/column/ row-reverse/column-reverse
                 row: 默认值 子元素水平排列
                 column: 子元素垂直排列
                 row-reverse: 子元素在水平方向上倒序排列
                 column-reverse: 子元素在垂直方向上倒序排列

                ③设置子元素在主轴的对齐方式:
                默认x为主轴,y为侧轴(flex-direction:row)
                当flex-direction:column时,y为主轴,x为侧轴
                justify-content:flex-start / flex-end / center /space-around / space-between
                 flex-start    默认值 弹性盒的开始
                 flex-end     弹性盒的结束
                 center   居中
                 space-around   两侧的距离是中间的一半
                 space-between    在子元素之间平均分配父元素剩下的空间,左右两端没有距离
                ④子元素在侧轴的对齐方式:
                algin-items:lex-start / flex-end / center
            3)子元素的属性:
            flex-grow:number
            设置子元素之间的比例 (一半设为1:1)
```

### 5. css - 浮动、动画、转换 {#5-css----浮动动画转换}

``` javascript
 18.浮动:
        1)原理:
        浮动后脱离流(排除到普通流之外)
        浮动后在页面不占据位置 (原位置不保留)
        浮动碰到父元素的边框或者浮动元素的边框就会停止
        浮动不会重叠
        浮动只有左右浮动
        浮动后所有元素转换为块级元素
        2)语法:
        float:left/right/none;
        3)排除浮动的影响:
            子元素浮动导致父元素坍塌,对后面的元素产生影响
          1)受影响的元素clear:left/right/both; (浮动元素的父元素高度仍未找到)
          2)给浮动元素的父元素加高  (高度已知)
        * 3)浮动元素的父元素加 overflow:hidden/auto; (自动找到)
          4)空div法:
            浮动元素后面加一个空div
            空div{clear:both;}
        * 5)伪对象法:
            浮动元素的父元素::after{content:""; display:block; clear:both;}
   18.display:
        每一个元素都自带display属性
        ①属性值:
        block     块级元素
        inline    行内元素
        inline-block   行内块 即在同一行显示,可以设置宽高
                       注:(行内块会识别代码之间的空白)
                       常见的行内块元素:img、video、audio、input、button
        none  隐藏  隐藏后不占据位置
        
   19.元素的定位: position
        1)属性值:
         ①static  静态定位 (默认值)
         ②relative   相对定位
           相对于自己原位置定位
           定位后原位置保留
           配合left/right/top/bottom移动
          应用场景:
           自己小范围移动;配合绝对定位使用
         ③absolute    绝对定位
          相对于已经定位的父元素定位 (相对定位、绝对定位、固定定位)
          如果父元素没有定位,逐级往上找,最后相对于body定位
          定位后原位置不保留
          配合left/right/top/bottom移动
          应用场景:
           形成独立的一层;
           推荐:给绝对定位的父元素加相对定位
         ④fixed      固定定位
         相对于浏览器窗口定位;
         定位后原位置不保留
         配合left/right/top/bottom移动
          应用场景:
           固定在页面某个位置
       2)在页面中不位置:
            ① float:left/right;
            ② display:none;
            ③ position:absolute;
            ④ position:fixed;
   20.圆角和阴影
       1)圆角:
        border-radius:;  取值:px / %  1-4值
         画圆:
        border-radius:50%
       2)盒阴影:
        box-shadow: 水平方向位置  垂直方向位置  模糊度  尺寸  颜色  位置
                      必须          必须      可选   可选  可选  可选
                      正负          正负      正值   正负        outset(默认) inset(在里面)
                    例子: 单个方向:box-shadow:0 10px 30px gold
                         四个方向:box-shadow:0 0 30px gold inset
       3)字阴影:
        text-shadow:水平方向位置  垂直方向位置  模糊度 颜色
                      必须         必须      可选  可选
                      正负         正负      正值
   21.浏览器的兼容性问题:
   厂商前缀:
   用于解决css3新特性的支持
          浏览器              内核              厂商前缀
           谷歌             blink内核           -webkit-
           苹果             webkit内核          -webkit-
           火狐             gecko内核           -moz-
           IE              trident内核          -ms-
           欧朋             blink内核            -o-
   22.背景渐变:
        1)线性渐变:
        background: linear-gradient(方向、颜色1、颜色2)
        方向默认为从上到下 to bottom
        例如: (to right / to right bottom / deg:弧度)
        background: linear-gradient(to right,red,blue)
        2)射线渐变 径向渐变 扇形渐变
        background: radial-gradient(渐变的中心点、渐变的形状、颜色1、颜色2)
        默认的渐变中心点在宽高的一半
        默认的渐变形状为椭圆
   23.转换:
        1)作用:
        使元素在位置或形状上发生一定的改变 (位移、旋转、缩放、倾斜)
        2)属性:
        transform:translate() rotate() scale() skew()
        3)属性值:
         ①位移 单位px:
         translate:(x,y);
         当只取一个值时,表示水平方向移动的距离
         当取两个值时,表示水平和垂直方向移动的距离
         取正值往右下移动,取负值时往左上移动
         transform:translateX/Y();
         ②旋转 单位deg弧度
         transform:rotate(30deg);
         取正值时顺时针旋转,负值时逆时针旋转
         transform:origin; 可以改变旋转的中心点,默认为宽高的一半
         注:位移和旋转同时存在时,位移在前旋转在后
         ③缩放 取值number:
         transform:scale(x,y);
         取值0~1 缩放
         取值>1  放大
         默认为1
         当只取一个值时表示等比例缩放
         当取两个值时表示水平方向和垂直方向
         ④倾斜 单位deg
         transform:skew(xdeg,ydeg)
         当取一个时表示水平方向的倾斜程度
         当取两个值表示水平和垂直方向
   23.过渡:
        1)作用:
         使元素从一个样式平滑过渡到另一个样式
         过渡必须要有触发事件(鼠标悬停、鼠标点击)
        2)属性:
         ①过渡的属性 必选:
         transition-property: ;
            可以过渡的属性:取值为颜色、取值为数值、转换transform、阴影box-shadow text-shadow、背景渐变
         简写为:all
         ②过渡的持续时间  单位 s/ms    必选 :
         transition-duration: ;
         ③过渡的速度变化类型:
         transition-timing-function: ;
          取值:
          ease 先加速后减速
          ease-in  加速
          ease-out  减速
          ease-in-out 先加速后减速
          linear   匀速
         ④延迟时间:
          transition-delay: ;
           可以取负值表示这段时间的效果直接跳过
     *** ⑤简写:
          transition:all 持续时间 速度变化类型 延迟时间;
   24.动画:
        1)动画和过渡的区别:
        动画是从一个样式到另一个样式,动画可以控制整个过程。
        过渡必须要有触发事件,动画可以没有
        2)定义动画:
        @（厂商前缀）keyframes name{0%{} 50%{} 100%{}}
        3)调用动画  关键帧动画:
        单个表示方法:
            animation-name: donghua;    动画的名称
            animation-duration: 4s;     持续时间
            animation-timing-function: linear;    速度变化类型
            animation-delay: 1s;        延续时间
            animation-iteration-count: 2;   播放次数
            animation-direction: alternate;   播放方向
            animation-fill-mode: forwards;    动画停在最后一帧
    *** 4)简写:
        animation:name（必选） 持续时间（必选）速度变化类型 延迟时间 播放次数（number/infinite）
                  播放方向（alternate 偶数次倒序播放） 动画停在最后一帧（forwards）;
   25.媒体查询: media query 响应式布局:
        作用:写一次样式适用于所有终端
        格式:@media screen and(min-width:768px) {}
        pc端 min-width:992px  ipad端 min-width:768 max-width:991  移动端 max-width:767px
```

### 6. 音频和视频 {#6-音频和视频}

``` javascript
     音频和视频的API方法：
	<audio src='' autoplay controls></audio>
        常用属性:
        autoplay	自动播放
        controls	显示控件
        currentTime	返回当前音频/视频的播放时间
        duration	    返回当前音频/视频的总时长
        ended		返回当前音频/视频是否播放结束
        paused		暂停状态  暂停 true  false播放
        src			音频/视频路径
        volume		设置音量

        常用事件：
        oncanplay	在用户可以开始播放视频/音频（audio/video）时触发   视频/音频（audio/video）在加载过程中，触发的
        ontimeupdate	当前音频/视频播放时间发生改变时触发   
        object.addEventListener("timeupdate", myScript); function myScript(){ }
        play()		播放
        pause()		暂停
```

### 7. 常见问题的处理 {#7-常见问题的处理}

``` javascript
七)、常见问题处理
    1.margin-top 问题:
        当第一个块级子元素设置margin-top时,父元素跟着一起下来
        解决方法:
        1)父元素加 overflow:hidden;  (找到跟位置)
        2)父元素或者子元素浮动
        3)父元素加 border:1px solid transparent;
        4)父元素加 padding-top:1px;
    2.排除浮动的影响:
        子元素浮动导致父元素坍塌,对后面的元素产生影响
        1)受影响的元素clear:left/right/both; (浮动元素的父元素高度仍未找到)
        2)给浮动元素的父元素加高  (高度已知)
      * 3)浮动元素的父元素加 overflow:hidden/auto; (自动找到)
        4)空div法:
          浮动元素后面加一个空div
          空div{clear:both;}
      * 5)伪对象法:
        浮动元素的父元素::after{content:""; display:block; clear:both;}
    3.居中问题:
        1)元素内容的水平居中  text-align:center;
        2)块级元素水平居中    margin:0 auto;
        3)一行文字垂直居中    行高等于高  line-height:height;
        4)多行内容垂直居中    padding:20px 0; (加在父元素身上)  margin:20px 0 (加在自己身上)
        5)子元素在父元素上水平居中
    4.注意:
    重排(回流): 元素的尺寸和位置发生变化会导致;
    重绘: 只改变元素的颜色等等;
```

### 8.移动端mate配置 {#8移动端mate配置}

``` 
<meta name="viewport" content="width=device-width, initial-scale=1.0,user-scalable=no,minimum-scale=1.0,maximum-scale=1.0" >
```

### 9.setting.json {#9settingjson}

``` javascript
{
  "git.path":"D:\\Git\\Git\\git-bash.exe",
  "workbench.editorAssociations": {
    "*.ipynb": "jupyter.notebook.ipynb"
  },
  "workbench.colorCustomizations": {
    "editor.background": "#18181b", //编辑区的背景颜色
    // "terminal.background": "#18181b", //终端的背景
    "editorGutter.background": "#1a1a1f", //行号的背景
    // "terminal.foreground": "#18181b", //终端的字体颜色
    // "sideBar.background": "#202024", //侧边栏背景
    "sideBar.background": "#18181b", //侧边栏背景
    "activityBar.background": "#18181b",   //活动栏背景
    "sideBarSectionHeader.background": "#18181b", //侧边栏选项背景
    "panel.background": "#18181b", //终端面板的背景颜色
    "titleBar.activeBackground": "#18181b", //窗口处于活动状态时的标题栏背景
    "editorGroupHeader.tabsBackground": "#18181b", //顶部活动栏
    "tab.inactiveBackground": "#18181b", //顶部活动栏未被激活的背景色
    "textLink.foreground": "#18181b", //开始页面的字体颜色
    // "foreground": "#ff0000",   //选项的背景
    // "editorLineNumber.foreground": "#ff0000",  //行号的颜色
    // "terminal.selectionBackground":"#ff0000"
    // "tab.border":"#6364b6"  ,  //顶部活动栏的分割线
    // "dropdown.foreground":"#ff0000"
    // "textLink.activeForeground":"#ff0000", //开始页面的字体悬停颜色
    // "dropdown.background":"#161821",  //下拉的背景
    // "menu.selectionForeground":"#ff0000",  //顶部菜单栏选中的颜色
    // "welcomePage.tileBackground":"#ff0000"
  },

  "editor.mouseWheelZoom": true,
  "files.autoSave": "onFocusChange",
  "editor.codeActionsOnSave": null,
  // "workbench.colorTheme": "Monokai",
  // "workbench.iconTheme": "material-icon-theme"
  "editor.tokenColorCustomizations": {
    "comments": "#85f7b6", // 注释
    // "keywords": "#f3b565", // 关键字
    // "variables": "#9810aa", // 变量名
    // "strings": "#86e4eb", // 字符串
    "functions": "#e2682f", // 函数名
    // "numbers": "#AE81FF", // 数字
    // "types": "#4da6c2",
    "textMateRules": [
      {
        "name": "Comment",
        "scope": [
          "comment",
          "comment.block",
          "comment.block.documentation",
          "comment.line",
          "comment.line.double-slash",
          "punctuation.definition.comment",
        ],
        "settings": {
          "fontStyle": "",
          // "foreground": "#8cf0b6",
          // "fontStyle": "italic", // 斜体 
          // 斜体下划线 "fontStyle": "italic underline",
          //  "fontStyle": "italic bold underline",   //斜体粗体下划线
        }
      },
    ]
  },
  "leetcode.endpoint": "leetcode-cn",
  "terminal.integrated.fontWeight": null,
  "explorer.confirmDelete": false,
  "code-runner.executorMap": {
    "python": "set PYTHONIOENCODING=utf8 && python"
  },
  "[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "workbench.iconTheme": "material-icon-theme",
  "[vue]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "cSpell.userWords": [
    "boxs",
    "echarts",
    "mavon"
  ],
  "editor.detectIndentation": false,
  "vetur.format.defaultFormatter.html": "js-beautify-html",
  "editor.quickSuggestions": {
    "strings": true
  },
  "editor.tabSize": 2,
  "html.hover.references": false,
  "css.hover.references": false,
  "less.hover.references": false,
  "scss.hover.references": false,
  "projectManager.git.baseFolders": [
    "A-Vue"
  ],
  "echarts-enhanced-completion.language": "中文",
  "bracket-pair-colorizer-2.depreciation-notice": false,
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "vscode.json-language-features"
  },
  "ctlorem.includeLanguages": "vue,javascript,python",
  "editor.fontSize": 21,
  "workbench.colorTheme": "Material Theme Darker",
  "terminal.integrated.fontSize": 18,
  "workbench.startupEditor": "none",
  "liveServer.settings.donotShowInfoMsg": true,
  "editor.inlineSuggest.enabled": true,
  // "terminal.integrated.shell.windows": "C:\\WINDOWS\\System32\\cmd.exe"
}
```

# javascript

### important

``` javascript
1.Object.freeze(变量名)    冻结变量 
2.
```

### 01. 原生js基础 {#01-原生js基础}

``` javascript
六)、javascript:
    组成部分:
      ECMAscript : 核心js
      DOM :        文档对象模型
      BOM :        浏览器对象模型
1.输出方式:
     1)输出到控制台:
     console.log()
     2)输出到网页中:
     document.write()
        html标签可以直接在js中应用
        document.write("<br/>")
        document.writer("<h1>一级标题</h1>")
     3)弹出警告框:
     window.alert() 简写为:alert()   注:alert()会阻止页面程序的运行
     4)变量的初始化  声明 赋值
        var 变量名 = 值
        let 变量名 = 值

     let和var的区别: ①只能在块级作用域下使用 ②没有声明提升
     5)常量:
         cost 常量名称 = 值
     6)严格模式:
         "use strict";
     7)模板字符串:
        `xxx${js语句}XXX`

2.js语法:
        1)区分大小写
        2)js以换行或分号结尾
        3)js会忽略多余空格
3.变量的命名规则:
        1) js区分大小写; a A
        2) 可以包含字母、数字、下划线、$
        3) 不能以数字开头
        4) 不能是js的关键字和保留字
        5) 多个单词使用驼峰命名法:
            小驼峰: useNameLast
            大驼峰: UseNameLast
    
```

### 02. js - 数据类型 {#02-js---数据类型}

``` javascript
4.数据类型:
        六大数据类型:
        number      数字类型
        string      字符串类型
        boolean     布尔类型
        undefined   未定义类型
        null        空类型
        object      对象类型
     1)number 数字类型:
        包含所有的数字(整数、浮点数、正数、负数、极大极小数),Infinity(分母为0),NaN(not a number)
		① num.toString(base)  可以直接得到对应的进制值
       	  base 的范围可以从 2 到 36。默认情况下是 10
		  123456..toString(36)  如果需要在一个数字上直接调用方法，需要加“..”
     2)string 字符串类型:
            在引号下包含的任意文本,单双引号都可以
        字符串之间可以相互嵌套,单引号中嵌套双引号,双引号中嵌套单引号
     3)boolean 布尔类型:
        true（真/对） flase（假/错）
     4)undefined 未定义类型:
        未定义类型表示数据类型不确定
        声明一个变量,没有赋值,默认值为undefined,数据类型为undefined
     5)null 空类型:
        null表示的数据类型确定为object
        null用来主动释放对象
         用typeof时返回的是object
     6)object 对象类型:
        大括号包含的一组值

     注: ①判断数据类型: typeof 变量名
         ②js拥有动态的数据类型
```

### 03. js - 运算符 {#03-js---运算符}

``` javascript
5.运算符:
     1)比较运算符:
        比较两个值的大小,返回的是布尔值,
        (> == < >= <= === !== !=)
        ==   等于,只判断数值
        ===  全等,判断数值和数值类型
     2)逻辑运算符:
        连接多个表达式,返回的是布尔值
        && 与   并且
        || 或   或者
        !  非   取反
        注: 逻辑与的优先级高于逻辑或
     3)算数运算符:
        + - * / %(取余 常用于判断奇偶数、倍数) ++ --
            + 运算遇到字符串时,直接进行字符串拼接,返回的是string类型
            - % * / 遇到字符串时,都转换成number类型进行计算,如果不能转换成数字,返回的是NaN,类型为number
            true=1 false=0
        (++ --
        前++和后++对于自己来说没有区别,都是+1
        前++是先+1,在赋值
        后++是先赋值,在+1)
     4)赋值运算符:
        = += -= *= /=
     5)条件运算符:
         3>2 ? "yes" : "no"
```

### 04. js - 结构 {#04-js---结构}

``` javascript
5.选择结构(分支结构):
        1)程序 = 数据 + 算法
            数据: 变量、数组、对象
            算法:
                顺序结构: 从上往下,从左到右
                分支结构: 根据不同的条件作出不同的判断
                循环结构: 重复执行相同的代码
        2)分支结构:
            单分支: if(条件){满足时输出的语句}
            双分支: if(条件){满足时输出的语句}else{不满足输出的语句}
            多分支: if(条件){输出语句}else if(条件){输出语句}...else{输出语句}
        3)switch语句: 使用该语句来选择多个代码块之一来执行
            switch(){
                case 条件;
                    console.log();
                    break;
                case 条件;
                    console.log();
                    break;
                default;
                    console.log();

            }
    
6.数据类型的转换:
        1)动态输入框:
            prompt("输入的是提示的内容",默认值)
            注: 默认值可以省略;返回的是string类型
        2)string类型转换为number类型:(强制转换)
            parseInt()    转换为整数,只取整数部分,不会四舍五入
            parseFloat()  转换为小数,只能识别一个小数点
        3)string类型转换为number类型:(隐式转换)
            - * / %   num-0  num*1
7.循环结构:
        1)for 循环:
            语法: for(循环变量;循环条件;循环规律){
                循环语句
        }
        2)do while:
            语法:
            do{
                循环体;
            }while(循环条件);
        3)while循环:
            语法:
            while(循环条件){
                循环体;
        }
```

### 05. js - 字符串 {#05-js---字符串}

``` javascript
8.字符串:
        string对象属性:
        length -字符串的长度
        string对象的方法:
        1)charAt()       -指定位置的字符;
        2)charCodeAt()   -指定位置的Unicode编码;
        3)concat()       -字符串的拼接 一般都用+;
        4)trim()         -清除字符串两边的空格;
        5)indexOf()/lastIndexOf()        -查询字符串（未找到时返回-1）;
        6)subString()/slice()/*subStr()  -提取字符串中两个指定的索引号之间的字符;
        7)toUpperCase()/toLawerCase()    -转大小写;
        8)split()         -分割 分割为数组;
        9)replace()       -替换;
        10)search()       -查找元素 ;
        11)startsWith("字符")/endsWith("字符")     -判断字符串是否以某个字符开头/结尾;
        12)repeat(次数)                            -将字符串重复指定的次数;
        13)padStart/padEnd(长度,"用来补位的字符")   -将字符串扩展到指定的长度;

        补充:
            字符串的编码:
                btoa(字符串)   -按照Base64的编码方式,对字符串进行编码;
                atob(字符串)   -按照Base64的编码方式,进行解码;
                encodeURIComponent(字符串)    -将非ASC||值转化为Base64编码;
                decodeURIComponent(字符串)    -将转码后的内容转化为非ASC||值;
```

### 06. js - 数组 {#06-js---数组}

**1.基本方法**

``` javascript
9.数组:
     1)数组的创建:
     字面量法:
          var 数组名 = [];
     new 方法:
          var 数组名 = new Array();
     2)数组对象的方法:
        ①数组的长度:
            arr.length  长度可以赋值;
        ②判断是否为数组:
            Array.isArray(数组名)  返回值为True/Flase;
        ③数组的拼接:
            concat(数组1,数组2,...)    /    `${内容}内容`;
        ④查找数组元素:
            arr.indexOf(数组元素);
            arr.lastIndexOf(数组元素);
        ⑤截取数据:
            arr.slice(起始位置的下标,结束位置的下标);
        ⑥增加删除数组元素1:
            ①尾部操作:
            增加: arr.push(数组元素1,数组元素2,);
            删除: arr.pop();
            ②尾部操作:
            增加: arr.unshift(数组元素1,数组元素2,);
            删除: arr.shift();
        ⑦增加删除修改数组元素2:  (改变原数组);
            增加:arr.splice(开始位置的下标,0,数组元素1,数组元素2...);
            删除:arr.splice(开始位置的下标,删除的个数) 返回的是被删除的元素;
            修改:arr.splice(开始位置的下标,修改的个数,数组元素1,数组元素2...) 返回的是被修改的元素;
        ⑧分隔数组:
            arr.join(分隔符);
        ⑨数组的排序:
            arr.sort()  默认为升序排列;
        ⑩数组的倒序:
            arr.reverse();
         从数组中过滤出符合条件的数组元素;返回的是一个新数组;
            arr.filter(function(var) {return 条件});
		⑦.数组的复制:
          	let arr = [1, 2, 3, 4, 5, 6];
          	console.log(arr.copyWithin(4,0,2));
        基础类型的赋值:赋值后没有任何联系;
            对象的引用:赋值后绑定一块;
        补充1:
            map():返回的是一个新数组,数组中的元素为原始数组元素调用函数后处理的值;
            arr.map(function(val,index,arr){return val*10});
        补充2:
            find():返回回调函数返回符合条件的第一个值;
            findIndex():返回回调函数符合条件的第一个值的下标;
        补充3:
            some():用于检测数组中的元素是否满足指定条件(由回调函数提供)返回True/False;
            every():检测数组中的所有元素都满足指定条件(回调函数提供);
            includes():检测数组中是否包含此元素  var.includes(检测的元素,开始检测的下标);
        补充4:
            reduce和reduceRight() 作为一个函数作为累加器,数组中的每个值从左到右开始缩减,最终计算为一个值;
            arr.reduce(function(prev,currentValue,cueerntIndex,arr){},初始值);
 
        13)数组的遍历:
        ①for(var i=0;i<arr.length;i++){}
        ②for in 方法: for(var i in arr){}
        ③for of 方法: for(var i of arr){} 指遍历值,没有下标
        ④forEach 方法: forEach(function(ele,index){})
```

**2.ES5新增方法**

``` javascript
①2个索引方法 -->查找数组中的元素
    arr.indexOf(数组元素);
    arr.lastIndexOf(数组元素);  

②5个迭代方法    -------------(这几个方法语法都一样，都不会改变原数组)
	filter(): 数组中过滤出符合条件的数组元素;返回的是一个新数组;
				arr.filter(function(var) {return 条件});

	map(): 指“映射”，方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
       			arr.map(function(val,index,arr){return val*10});		

	every():  判断数组中每一项都是否满足条件，只有所有项都满足条件，才会返回true。
                let arr = [1,2,3,4,5,6]
                let newArr1 = arr.every(function(x){x>3})
                console.log(newArr1);   //false
                let newArr2 = arr.every(x => x<7)
                console.log(newArr2);   //true	

	some():  判断数组中是否存在满足条件的项，只要有一项满足条件，就会返回true。
                let arr = [1,2,3,4,5,6]
                let newArr1 = arr.some(function(x){return x<4})
                console.log(newArr1);   //true
                let newArr2 = arr.some(x => x>7)
                console.log(newArr2);   //false
	forEach():  对数组进行遍历循环，这个方法没有返回值。jquery()也提供了相应的方法each()方法。
                let arr = [1,2,3,4,5,6]
                arr.forEach(x => {
                    console.log(x*2);
                })

③两个归并方法
    reduce()语法：arr.reduce(function(total , cur , index , arr){//do something}, initialValue)
    reduceRight()语法：arr.reduceRight(function(total , cur , index , arr){//do something}, initialValue)
        -total ：必需。初始值, 或者计算结束后的返回值。
        -cur ：必需。当前元素。
        -index ：可选。当前元素的索引。
        -arr：可选。当前元素所属的数组对象。
        
    用法:
        ar arr = [1,2,3,4,5];
        var result1 = arr.reduce(function(total,cur,index,arr){	
            console.log("total:"+total+",cur:"+cur+",index:"+index);
            return total+cur;
        });
        console.log("结果："+result1)
        // 输出
	    // total:1,cur:2,index:1
        // total:3,cur:3,index:2
        // total:6,cur:4,index:3
        // total:10,cur:5,index:4
        // 结果：15


        var result2 = arr.reduce(function(total,cur,index,arr){	
            console.log("total:"+total+",cur:"+cur+",index:"+index);
            return total+cur;
        },10);
        console.log("结果："+result2);
        // 输出
        // total:10,cur:1,index:0
        // total:11,cur:2,index:1
        // total:13,cur:3,index:2
        // total:16,cur:4,index:3
        // total:20,cur:5,index:4
        // 结果：25
```

**3.ES6新增方法**

``` javascript
1.查找元素 
    find():返回回调函数返回符合条件的第一个值;
    findIndex():返回回调函数符合条件的第一个值的下标;
```

### 07. js - 对象 {#07-js---对象}

``` javascript
10对象:
     1)获取对象的属性名（键）       object.keys(对象名称)
       获取对象的属性值             object.values(对象名称)
       获取对象的属性名（键）和值    object.entries(对象名称)
     2)in 关键字 ： 判断某个属性是否属于某个属性对象; 格式: "属性名称" in 对象名称
     3)Math对象的方法: 
        PI       属性获取圆周率;     Math.PI
        ceil     向上取整;           Math.ceil(数据)
        floor    向下取整;           Math.floor(数据)
        round    四舍五入;           Math.round(数据)
        pow      求次方;             Math.pow(x,y)
        max/min   最值;              Math.max/min(值1,值2,...)
        abs      绝对值;             Math.abs(数据)
        sqrt     算数平方根;         Math.sqrt(数据) 
    *** random   随机生成0-1的数     Math.random()
    ***          用于随机生成n-m间的值  
    ***          公式: parseInt(Math.random() * (最大值 +1 -最小值) + 最小值)
     4)创建日期时间对象:
        ①日期时间对象 = new Date()                    获取系统当前时间
        ②日期时间对象 = new Date("日期时间字符串")     将指定的字符串转换为标准格式

        var date = new Date();//创建日期时间
        var year = date.getFullYear();//获取年份
        var moth = date.getMonth();//获取月份  返回的是0-11  0表示一月份 11表示十二月份          
        var day = date.getDate();//获取天
        var time = date.getTime();//距离1970年1月1日0时0分0秒的毫秒值
        var week = date.getDay();//获取星期     返回0-6  0表示星期日
        var hour = date.getHours();//获取小时
        var minute = date.getMinutes();//获取分钟
        var second = date.getSeconds();//获取秒
        var res = date.toLocaleString();//包含日期和时间
        var res = date.toLocaleDateString();//包含日期
        var res = date.toLocaleTimeString();//包含时间
 5)异常捕获机制:
        try(){
            可能有问题的代码
        } catch(error) {
            错误的处理方式
        }
     6)变量的分类:
      全局变量和局部变量的区别:全局变量和局部变量重名时,要使用全局变量可以在变量名称前面加(window.或this.)
                             因为全局变量是给window对象绑定的属
     7)arguments对象的使用:
     作用:用来管理函数被调用时传递过来的实参;它是一个伪数组;
     包含两个属性:length、callee
        length属性:获取实参的个数;
        callee属性:获取arguments对象所在的函数,常于递归函数或匿名自执行函数结合使用;
     8)重载函数:
        在JavaScript中函数没有重载;如果函数名称相同,后面的函数会覆盖前面的函数。
     9)递归函数:
      ①求1-n的和:
      function fn(){
          if(n==1){
              return 1;
          } else{
              return arguments.callee(n-1) + n;
          }
      }
      ②斐波那契数列:
      function fn(){
          if(n==1 || n==2){
              return 1;
          } else{
              retrun arguments.callee(n-1) + (n-2);
          }
      }
```

### 08. js - 函数 {#08-js----函数}

``` javascript
10.函数:
     1)函数的创建:
     function 函数名(形式参数){
        函数体
     }
     var 函数名 = function(形式参数){
         函数体
     }
     2)匿名函数:
        匿名函数常于时间名称相结合;
        格式:  HTML元素.on事件名 = function(){};
     3)匿名自执行函数:
        无函数名称且不需要手动调用的函数
        格式:  (function(形参...){})(实参...);
```

### 09. js - DOM {#09-js---dom}

``` javascript
11.Dom 文档对象模型:
    document:
    对象都有的属性:  node.Type 1 / node.Name 2 / node.Value 3
     1)属性:
        document.title 标题
        document.location.href  路径
        元素.innerHTML    获取元素中的内容 （也可以将元素的内容重新赋值）
        window.location.reload(); 进行页面刷新
        $(document).ready(function(){})  进入页面就执行函数的调用

     2)获取和修改页面文本内容:  
        元素.innerHTML = "文本"
        元素.innerText = "文本"   (不解析标签)
        元素.value   在表单元素中使用;
        元素.text.content;  (不解析标签)
      
     3)选中页面元素: (注意：点语法不能直接操作class属性,应使用className)
        ① 通过Id选择器:
             document.getElementById("")
        ② 通过ClassName选择器:
             document.getElementsByClassName("")
        ③ 通过元素选择器:
             document.getElementsByTagName("")
        ④ 通过css选择器选中页面元素:
             document.querySelector(".?")      #获取符合条件的第一个元素
             document.querySelectorAll(".?")   #获取符合条件的所有元素
 
     4)操作页面的属性:
        ① 获取元素属性值:
            元素.getAttribute("属性名")	
			元素节点.属性名   --#不支持自定义属性
        ② 设置元素属性:
            元素.setAttribute("属性名","属性值")
			元素节点.属性名  = 属性值
        ③ 删除元素属性: 
            元素.removeAttribute("属性名")
        获取属性节点:
        ① 元素节点.getAttributes                (获取所有)
        ② 元素节点.getAttributeNode("属性名")   (获取某个)

     5)节点关系:
     页面中的节点不是孤立的,常见关系如下: (#注意--包含空白节点--前者获取到的是#text,后者是真正的内容;)
        ① childNodes  ------  children               父元素的所有子节点;
        ② firstChild  ------  firstElementChild      父元素的第一个子节点;
        ③ lastChild  ------  lastElementChild        父元素的左后一个子节点;
        ④ parentNode  ------  parentElement          父节点;
        ⑤ nextSibling  ------  nextElementSibling    下一个兄弟节点;
        ⑥ previousSibling  ------  previousElementSibling   前一个兄弟节点;
    
     6)页面中特殊节点的获取:
        ① html节点的获取:     document.documentElement;
        ② body节点的获取:     document.body;
        ③ head节点的获取:     document.head;
        ④ 获取或设置title属性:    document.title 或 document.title = 值;
        ⑤ 文档节点:               document（也可以用元素节点的ownerDocument）
        ⑥ 获取具有name属性的超连接   document.anchors;     
        ⑦ 获取页面中所有form的节点  document.forms; 
        ⑧ 获取页面中的所有img节点   document.images;
        ⑨ 获取页面中带有href属性的节点   document.links;
        ⑩ 获取页面中所有的script属性     document.doctype; 

      document 对象的属性:
        ① documentURL  文档的地址;
        ② URL           文档的属性;
        ③ domain         返回地址中的域名部分;
        ④ lastModified    返回上一次修改的时间;
     ***⑤ location   返回location对象,用来操作url地址;
            a. href属性:     获取和设置当前地址,实现页面的跳转;
            b. assign属性:    设置url的地址; （document.location.assign("url");
            注: ab两种属性都会产生浏览记录;
        ⑥ window.location = "url"      操作url地址;
        ⑦ readyState 返回页面的加载状态;
            a. loading       加载html 并解析;
            b. interactive   正在加载外部资源;
            c. complete      加载完成;

     7)Dom常用方法:
        ① insertBefore用法:
            作用: 将某个节点插入到目标节点的前面;
            格式: 父节点.insertBefore(新的节点,目标节点);
        ② removeChild用法:
            作用: 删除节点,（返回的被删除的节点;在内存中,并没有真正的删除）;
            格式: 父节点.removeChild(要删除的节点);
        ③ replaceChild用法:
            作用: 替换节点,（返回的是被替换的节点）;
            格式: 父节点.replaceChild(新的节点,旧的节点);
        ④ isEqualNode用法:
            作用: 判断两个节点是否相同;
            格式: 节点1.isEqualNode(节点2);
        ⑤ contains用法:
            作用: 判断某个节点是否包含另外的某个指定的节点;
            格式: 节点1.contains(可能包含的节点);
        ⑥ hasChildNode用法:
            作用: 判断是否有子节点;
            格式: 节点.hasChildNode();
        
     8)Dom常用属性:
        ① offsetParent属性:
            作用: 返回的是样式偏移时的参照物;
            格式: console.log(元素节点.offsetParent);
        ② offsetTop属性:
            作用: 距离偏移对象顶部的距离;
            格式: console.log(元素节点.offsetTop);
        ③ offsetLeft属性:
            作用: 距离偏移对象左边的距离;
            格式: console.log(元素节点.offsetLeft);

        ④ offsetWidth       返回元素的宽度(包含元素宽度、内边距和边框;不包含外边距;不受滚动条影响);
          offsetHeight      返回元素的高度(包含元素宽度、内边距和边框;不包含外边距;不受滚动条影响);
          clientWidth       返回元素的宽度(包含元素宽度、内边距;不包含外边距和边框;受滚动条影响);
          clientHeight      返回元素的高度(包含元素宽度、内边距;不包含外边距和边框;受滚动条影响);
          用法: a.如果获取页面窗口的宽高用clientWidth和clientHeight;如果获取元素的宽高用offsetWidth和offsetHeight;
                b.如果获取页面视口的宽高,需要用以下方式:
                var 变量名称 = document.documentElement.clientWidth || document.body.clientWidth;  （后者支持低版本IE）
                var 变量名称 = document.documentElement.clientHeight || document.body.clientHeight;  （后者支持低版本IE）
                
     9)设置style属性:
        行内样式:
            ① 元素.style.css属性 = "属性值"       
            ② 元素.style.cssText = "属性:属性值;属性:属性值;"   (#需要驼峰命名,会替换原有的属性和值)

            ③ 元素节点.style.setProperty("属性名","属性值");  设置css属性
              元素节点.style.getPropertyValue("属性名");       获取属性值  (#不需要驼峰命名)
              元素节点.style.removeProperty("属性名");          删除某个属性  (#不需要驼峰命名)
        内部样式和外部样式的操作:
            getComputedStyle方法: （低版本IE不支持）
            格式: window.getComputedStyle(元素节点,null);
            currentStyle属性: （低版本IE支持）
            格式: 元素节点.currentStyle;  返回样式表对象;

     10)创建页面元素:
        ① 创建元素:
             document.createElement("元素名")
        ② 创建文本节点:
             document.createTextNode("文本")
        ③ 创建属性:
             document.createAttribute("属性名")
        ④ 属性赋值:
             属性名.value = "属性值"
        ⑤ 设置属性节点:
             元素.setAttributeNode(属性名)
        ⑥ 作为子节点追加到页面:
            父节点.appendChild(子节点)
            document.body

     11)操作className:
        元素.className = "类名"
```

### 10. js - DOM - 事件 {#10-js---dom---事件}

``` javascript
12.事件:
     1)事件的添加:
        a.在HTML中添加事件:
            添加格式: <标签 on事件名 = "事件处理函数的名称（）/js代码"></标签>
            删除格式: 元素节点.removeAttribute("on事件名");
            this的使用;
        b.DOM0级事件处理程序:
            添加方式1: 元素节点.on事件名 = function() {};
            添加方式2: 元素节点.on事件名 = 事件处理函数名称;
            删除格式:  元素节点.on事件名 = null;
            this的使用: 在其对应的事件处理函数中直接使用this,这的this就是指向当前事件应用到的元素;
            注意: 一个元素有多个事件,后面的事件会覆盖前面的事件;
        b.DOM2级事件处理程序:(不适用于IE8及以下使用)
            添加方式: 元素节点.addEventListener(参数1,参数2,参数3);
            参数说明: 参数1: 事件名称;  
                     参数2: 时间处理函数（可匿名）; 
                     参数3: 事件流,true（事件捕获） false（默认,事件冒泡）;
            删除方式: 元素节点.removeEventListener(参数1,参数2,参数3);
            this的使用: 直接使用this,这个this就是指向当前事件应用到的元素;

            适用于IE的方法: 
            attachEvent方法:  （IE 11不能使用,用的是上面的的方法）
            添加方式: 元素节点.attachEvent("on+事件名称",事件处理函数);
            删除方式: 元素节点.detachEvent("on+事件名称",事件处理函数)
        
     2)事件流: （事件的执行顺序）
        a.事件冒泡: 从当前元素逐渐向外扩展  即由小到大 由内到外;
        b.事件捕获: 从根节点逐渐向当前元素扩展  即由大到小 由外到内;
    
     3)事件对象
        ① 事件对象的获取:
            a.谷歌浏览器: 事件对象被以实参的形式传递给事件处理函数;
            b.IE8以下版本: 使用window对象的event属性获取;
            获取事件对象的兼容写法为:
                元素节点.事件处理函数程序名称 = function(e){
                    e = e || window.event;
                    console.log(e);
                }
        ② 事件对象的常用属性:(都是用事件对象来调用)
            a.格式:  .type    获取事件的类型;
            b.altKey、shiftKey、ctrlKey  对应键盘上的值,如果按下则返回true;
            c.keyCode     当键盘事件被触发时返回,获取被按下键的键码值;
            d.screenX、screenY   获取鼠标点击时距离屏幕左侧和顶部的距离;
            e.clientX、clientY   获取鼠标点击时距离视口左侧和顶部的距离（不受滚动条的影响）;
            f.pageX、pageY      获取鼠标点击时距离页面左侧和顶部的距离（受滚动条的影响）;
            g.offsetX、offsetY  获取鼠标点击时距离自身左侧和顶部的距离; 
            h.currentTarget    表示当前谁身上的事件被触发;
            i.target     获取当前哪个元素被点击了(事件源);
              srcElement  同上,兼容IE8及以下版本;
        ③ 事件对象的常用方法:(都是用事件对象来调用)
            preventDefault方法:  
                a.作用:取消默认行为;低版本IE不支持;
                b.格式:事件对象.preventDefault();
                c.兼容性: 低版本IE可以用: 事件对象.returnValue = false;
            stopPropagation方法:
                a.作用:阻断冒泡;
                b.谷歌浏览器中: 事件对象.stopPropagation();
                c.IE浏览器器中: cancelBubble = true;
                d.兼容写法:     if e.stopPropagation == undefined ? cancelBubble = true : e.stopPropagation();
            setInterval方法:
                a.作用:用来设置定时器,在一定的时间内重复执行某个操作;
                b.格式:window.setInterval(重复执行的操作,时间间隔);
                 注:时间间隔是以毫秒为单位的 1s = 1000ms;
            clearInterval方法:
                a.作用:清除定时器,即停止setInterval的执行;
                b.格式:window.clearInterval(定时器的编号);
     
     9)事件执行:
        ① 写在html中:
            <标签 on事件名 = "js代码"></标签>
            eg: <button onclick="alert('恭喜你！喜提爱车')">点我啊！</button>
        ② 写下html和js中:
            html: <标签 on事件名 = "调用函数"></标签>
             eg: <button onclick="fu1()">点我啊！</button>
            js: 定义函数
             eg: function fu1(){alert("恭喜你！喜提爱车")}
        ③ 写在js中:
            元素.on事件名 = function(){执行的代码}
             eg:  <button id=box>点我啊！</button>
                     var but = document.getElementById("box")            #获取元素
                     but.onclick = function(){alert("恭喜你！喜提爱车")}   #绑定事件
     10)事件分类:
        1. 鼠标事件:
            onclick      点击事件
            ondblclick   双击鼠标
            onmouseup    鼠标释放
            onmousedown  鼠标按下
            onmouseenter 鼠标进入（不支持冒泡）
            onmouseleave 鼠标移出（不支持冒泡）
            onmouseover  鼠标进入（支持冒泡）  #父元素绑定了事件子元素可以继承
            onmouseout   鼠标移出（支持冒泡）
            onmousemove  鼠标移动
            oncontextmenu  右击事件 
        2. 表单元素事件:
            onfocus      获取焦点 
            onblur       失去焦点 
            oninput      只要给元素输入内容时就会触发
            onchange     元素发生变化（后失去焦点）时会触发
            onsubmit     点击提交按钮时被触发（加在form中）
            onreset      点击重置按钮时被触发（加在form中）
        3. 键盘事件:
            onkeydown    键盘按下时触发 
            onkeypress   键盘按下时触发 （不包含功能键）
            onkeyup      键盘释放时触发
        4. 滚动事件:
            onscroll     滚动事件
            常结合 scrollTop 和 scrollLeft 来使用
            scrollTop :当设置或者获取拉动滚动条时被卷上去内容的高度;
            scrollLeft :当设置或获取拉动滚动条时被卷到左边的内容的宽度;
                注意: 在设置或者获取窗口滚动条时,不能使用window.scrollTop,此时需要用document.documentElement.scrollTop ||document.body.scrollTop;
        5. 移动端事件:
            ontouchstart  当手指触摸到屏幕或指定的元素时触发;
            ontouchmove   当手指在屏幕或指定元素上移动时触发;
            ontouchend    当手指从屏幕上移开时触发;
 
            touches: TouchList {0: Touch, length: 1}           保存放在屏幕上的所有触摸点的所有信息;
            targetTouches: TouchList {0: Touch, length: 1}     保存和当其前元素相关的触摸点信息;
            changedTouches: TouchList {0: Touch, length: 1}    保存了由触摸点变化形成的信息;
     11)window对象:（用事件对象来调用）
        1.bubbles属性:用来判断当前事件是否支持事件冒泡 返回true支持,false不支持;
        2.eventPhase属性: 该属性的值为1、2、3;
           1表示是由于事件捕获引起的事件的执行
           2表示事件流中的当前元素
           3表示是由于事件冒泡引起的事件的执行
        3.button属性: 判断鼠标按下了哪个键;
           0表示按下左键
           1表示按下中间键
           2表示按下右键
        4.onload事件: 当文档中的所有节点都加载完毕后才会执行（例如网页中的图片的加载）;格式:window.onload
        5.DOMContentLoaded事件: 该事件和load事件类型,但执行的速度要比load早,该事件是在DOM渲染完毕后就会执行,
                                而load是在整个文档都加载完毕后执行,同时该事件需要addEventListener方法来添加;
        6.事件委托:事件委托也被称为事件代理,也就是将事件委托给祖先元素,利用事件冒泡机制和事件对象让该祖先元素下面的
                   所有后代元素具有同一类型的事件;     
     12)window对象的常用方法:(以下都是用window来调用)
        1.alert()      弹出警告框
        2.confirm()    弹出提示框 window.confirm("提示内容")
        3.prompt()     输入框
        4.isFinite()   判断参数是否为有限值
        5.isNaN()      判断是否为数字
        6.open()方法:
                格式: window.open("地址","窗口名称","窗口特性"); 
                    a. 都可以省略,省略后打开的是一个空白页面
                    b. 窗口特性也就是属性
                返回值: 返回的是一个新的窗口对象
        7.close()方法:
                作用: 关闭当前窗口
                格式: window.close()
        8.name属性:  也是window对象的一个属性,默认为空字符串,用来在不同的窗口间进行数据的传递;
        
     13)window对象和正则表达式:（用window来调用）
        1.innerWidth:  返回窗口文档显示区的宽度 即视口的宽度;
        2.innerHeight: 返回窗口文档显示区的高度 即视口的高度;
         一般获取视口的宽和高写法:
         document.documentElement.clientHeight || document.body.clientHeight || window.innerHeight;
                        pc端                                                         移动端
        3.js外部加载中常用的属性(script标签中的属性):
            a. defer属性:  在所有的DOM都加载完成后才执行js文件  相当于window.onload=function(){};
            b. async属性:  同时加载所有的结束文件  相当于计时器setInterval(function(){},1000);
        4.call() apply():
            作用: 调用方法,替换对象;
            call()的格式: 被借用函数名.借用的函数.call(借用函数,参数1,,参数2,,参数3);
            apply()的格式: 被借用函数名.借用的函数.apply(借用函数,[实参1,实参2,实参3]);
            注意: 借用来的函数不需要再调用;
     14)DocumentFragment方法:
            作用: 提升性能;
```

### 11. js - 正则 {#11-js---正则}

``` javascript
    15)正则表达式:
            1、字面量形式创建正则表达式: var 正则表达名称 = /表达式内容/修饰词;
            2、构建方法创建正则表达式: var 正则表达式名称 = new RegExp("表达式内容,"修饰词");




            3、test()方法:
                a.作用: 用来判断字符串是否符合正则表达式的格式,返回true和false;
                b.格式: 正则表达式.test(字符串);
               exec()的方法:
                a.格式: 正则表达式.exec(字符串);  有些类似于match();

            4.修饰词:
                i 表示不区大小写;
                g 表示全局搜索;
                ig 表示不区分大小写且全局搜索;

            5.正则表达式的构成:（普通字符、特殊字符）
                a.普通字符: 数字、字母、-;
                b.特殊字符（元字符）: 
                    ^ :表示以某个字符开头;
                    $ :表示以某个字符为结尾;

                    * :表示它前面的字符的个数为0到无穷;
                    + :表示它前面的字符的个数为1到正无穷;
                    ? :表示它前面的字符的个数为0到1;

                    {n} :表示它前面的字符的个数只能为n个, 如a{3}表示只能有3个a;
                    {n,m} :表示它前面的字符的个数为n-m个, 如a{1,3}表示a的个数为1-5个;
                    {n.} :表示它前面的字符个数为n到无穷多个, 如a{3.}表示a的个数为大于等于3个;
                c.转义字符:
                    反斜线 \;

                    \d: 表示任意一个数字;
                    \D: 表示任意一个非数字;
                    \w: 表示任意一个数字、字母、下划线;
                    \W: 表示任意一个非数字、字母、下划线;
                    \s: 表示任意一个空白字符,如空格、下划线;
                    \S: 表示任意一个非空白字符;
                    \b: 匹配单词的开头结尾;
                    \B: 匹配非单词的开头和结尾;
                d: 备选字符集:
                    [值1 值2 值3 值4] :中括号里面的值表示字符中可以匹配到的任意一个值;
                    [值1-值n] :表示值1-值n间的任意一个备选选项;
                    [^值1 值2 值3] :表示字符串中不可以包含中括号里面的任意一个值;

            6.贪婪模式和懒惰模式:
                贪婪模式: 如果正则表达式中有表示数量的特殊符号,如*、+、{n,m}等在匹配时会尽可能多的匹配字符; （默认）
                懒惰模式: 如果正则表达式中有表示数量的特殊符号,如*、+、{n,m}等在匹配时会尽可能少的匹配字符; （需要在数量词中加？）
         
         16)JSON:
                本质上就是字符串;
                1.JSON对象的方法:
                    parse():
                        作用:将JSON字符串转换为JS对象;
                        格式:window.JSON.parse(JSON字符串);
                    stringify():
                        作用:将JS对象转换为JSON对象;
                        格式:window.JSON.stringify(JS对象);
         17)面向对象:
                2.instanceof操作符:
                    a.作用:判断引用类型的数据的具体类型 返回true或false;
                    b.格式:数据 instanceof 类型;
                2.hasOwnProperty方法:
                    a.作用:判断某个属性为对象的私有属性,返回true或false;
                    b.格式:对象.hasOwnProperty("属性名称");

```

### 12. js - this使用场景 {#12-js---this使用场景}

``` javascript
13.this的常见使用场景:
        1.在文档中直接使用this,this指的是window对象;
        2.如果在全局变量或全局函数前面使用this,this代表的是window对象;
        3.如果是html事件处理程序,那么将this作为事处理函数的实参,传递事件处理函数,this代表的应用事件的元素;
        4.如果是DON0级事件处理程序,事件处理函数中的this代表应用事件的元素;
        5.如果是DOM2级事件处理程序,事件处理函数中的this代表应用事件的元素;
        6.在字面量形式创建的函数中,如果将this放在方法内,这个this代表的是当前的字面量对象;
        7.在构造方法中,如果将this放在属性名称前面,这个this代表的是构造方法创建出来的对象;
        8.如果将this放在原型中,它代表的是使用该原型的内容的对象;
        9.在借用构造方法继承时,call中的this代表的是下级构造方法创建的对象;
        10.如果在闭包中使用this,this代表的是window对象;
        11.间隔调用和延迟调用中的this代表的是window对象;
        12.自执行函数中this指向window;
```

### 13. js - jQuery {#13-js---jquery}

``` javascript
14.jQuery:
    1).
        1.jQuery对象与DOM对象的相互转换:
            jQuery对象转换为DOM对象: jQuery对象[下标];
            DOM对象转化为jQuery对象: $(DOM对象);
        2.text()方法:
            作用: 获取或设置jQuery对象的内容;
            格式: jQuery对象.text() 或 jQuery对象.text("内容");
          html()方法:
            作用: 获取或设置jQuery对象的内容;
            格式: jQuery对象.html() 或 jQuery对象.html("内容");
        3.val()方法:
            作用: 获取或设置表单元素的值;
            格式: 表单元素.val();
        4.attr()方法 prop()方法 removeAttr()方法 removeProp()方法:
            作用: 设置或修改属性:
            格式: Query对象.attr();  Query对象.prop();//多个属性时可以使用集合;
        5.addClass(),removeClass(),toggleClass()方法:
            作用: 添加类 删除类 有元素时删除无元素时添加;
            注意: 添加时,如果添加多个中间用空格隔开;

    2).内部部追加jQuery和外部追加jQuery   
        内部部追加jQuery:
            1.append() appendTo()方法:
                作用: 将jQuery对象以尾部追加的方式添加到容器中;
                格式: 容器.append("被添加的jQuery对象或者标签形成的字符串");
                    ("被添加的对象").appendTo("代表容器的jQuery对象或选择器");
              prepend() prependTo()方法:
                作用: 将jQuery对象以开头追加的形式添加到容器中;
                格式: 容器.prepend("被添加的jQuery对象");
                    ("被添加的对象").perpendTo("代表容器的jQuery对象或选择器");
        外部追加jQuery:
            1.after()和insertAfter()方法:
                作用: 在目标元素后面追加jQuery对象;
                格式: 目标元素.after(要插入的新的jQuery对象);
                      要插入的新的jQuery对象.insertAfter(目标元素);
            2.before()和insertBefore()方法:
                作用: 在目标元素后面追加jQuery对象;
                格式: 目标元素.before(要插入的新的jQuery对象);
                      要插入的新jQuery对象.insertBefore(目标元素);
        3)常用方法:
            1.empty()方法:
                作用: 清空某个容器下面的所有内容;
                格式: 容器.empty();
            2.remove()方法:
                作用: 删除某个jQuery对象;
                格式: 要被删除的jQuery对象.remove("选择器");
                注意: 该元素身上的事件也会被删除;
                
        4).事件的绑定:
            1.格式:
                jQuery对象.事件名称 (function(){});
            2.bind添加事件方法:
                a.格式（绑定一个事件时）: jQuery对象.bind("事件名称",function() {
                                            //执行的操作;
                                        });
                b.格式（绑定多个事件时,执行相同的操作）: jQuery对象.bind("事件名称1 事件名称2 事件名称3",function(){
                                                            //执行的操作;
                                                      });
                c.格式（绑定多个事件时,执行不同的操作）: jQuery对象.bind({
                                                            事件名称 : function(){},
                                                            事件名称 : function(){}
                                                      });
                d.格式（在元素绑定事件时,给它传递数据）: jQuery对象.bind("事件名称",数据,function(){});
              bing删除事件的方法:
                a.格式（删除所有的bing事件）: jQuery对象.unbind();
                b.格式（删除指定的bing事件）: jQuery对象.unbind("事件名称");
            
            3.delegate()方法:  （只能用c的形式来绑定）
                a.格式: 祖先元素.delegate(后代元素,事件名称,数据,function(){
                                    //执行的操作;
                                });
             delegate删除事件的方法:
                a.祖先元素.delegate("事件名称");
            4.on方法的添加方法:(事件委托)
                格式1: jQuery对象.on("事件名称",function(){});
                格式2: jQuery对象.on("事件名称1 事件名称2 事件名称3 function(){}");
                格式3: jQuery对象.on({
                    事件名称1 : function(){},
                    事件名称2 : function(){}
                    });
 
                作用: 给元素添加一次性事件:
                格式: jQuery对象.one("事件名称",function(){});
            6.hover方法:
                格式: jQuery对象.hover(function(){},function(){});
            7.clone()方法:
                作用: 克隆页面中的元素;
                格式: 要克隆的元素的.clone(true/false);false为默认值,表示不克隆元素的事件;
            8.parent() 方法:  //返回父节点
              parents()方法:   //返回所有的祖先节点;
              parentsUntil()方法:   //获取到指定位置的祖先节点;
              siblings()方法:    //获取所有的兄弟元素;
              next()方法:   //返回后一个兄弟元素;
              nextAll()方法:   //返回后面所有的兄弟元素;
              prev()方法:    //返回前一个兄弟元素;
              prevAll()方法:    //返回前面所有的兄弟元素;
              prevUntil()方法:   //返回前面指定位置的所有元素;
              first()方法:  //从jQuery对象集合中过滤出第一个jQuery对象;
              last()方法:    //从jQuery对象集合中过滤出最后一个jQuery对象;
              eq()方法:    //从jQuery对象集合中过滤出指定下标的jQuery对象;
              filter()方法:  //过滤出匹配指定选择器的jQuery对象,选择器之间用逗号隔开;
              addBack()方法: 
                    作用: 将目标元素添加到jQuery对象集合中;
                    示例: $("#box").nextAll().addBack();
              end()方法:
                    作用: 返回链式结构被破坏之前的那个jQuery对象;
                    示例: $("#box").next().end();
        5)jQuery的内置动画:
            1. show()  显示动画:  格式: jQuery对象.show("持续时间（毫秒）,function(){}"); 
            2. hide()  隐藏动画:  格式: jQuery对象.hide("持续时间（毫秒）,function(){}"); 
            3. toggle()  显示/隐藏动画:  格式: jQuery对象.toggle("持续时间（毫秒）,function(){}"); 
            4. slideUP()  向上滑动:  格式: jQuery对象.slideUp("持续时间（毫秒）,function(){}"); 
            5. slideDown()  向下滑动:  格式: jQuery对象.slideDown("持续时间（毫秒）,function(){}"); 
            6. slideToggle()  向上/下滑动:  格式: jQuery对象.slideToggle("持续时间（毫秒）,function(){}"); 
            7. fadeIn()      淡入已隐藏的元素-显示;
            8. fadeOut()    淡出显示的元素-隐藏
            9. fadeToggle()   淡入淡出切换;
            10.fadeTo()     渐变给定的不透明值;
        6)jQuery中的内置动画:
            animate()方法:
                作用: 自定义动画;
                格式: jQuery对象.animate(参数1,参数2,参数2,参数4);
                参数说明: 
                        参数1: 封装需要实现的样式;
                        参数2: 执行的时间(毫秒);
                        参数3: 执行的状态 linear(匀速) swing(慢-快-慢;默认);
                        参数4: 回调函数; 
            stop()方法:
                作用: 停止动画;
                格式: jQuery对象.stop(参数1,参数2);
                参数说明: 
                        参数1: 值为布尔值;默认为false  若为true(结束当前动画,删除之后的动画);
                        参数2. 值为布尔值;默认为false  若为true(结束当前动画,继续之后的动画);
            each()方法:
                    作用: 可以利用each方法对jQuery对象集合中的每个元素做单独的处理;
                    格式: jQuery,each(function(index,ele){
                            在函数内部对jQuery对象集合中的每个元素做单独的处理;
                    })
                    参数说明: 
                            index: 表示jQuery对象中的DOM对象的下标;
                            ele: 表示该集合元素中的DOM对象;
```

### 14. js - ajax - 原生js {#14-js---ajax---原生js}

``` javascript
3)ajax技术 (XMLHttpRequest):
    1.介绍: 是一种新的技术方案,不是新的技术;基于html/css/js语言;实现创建快速的动态页面,对页面进行局部刷新,而不是整个页面都刷新;
    2.用处: 
        a.登录注册时;
        b.下拉加载更多;
        c.页面的局部刷新;
        d.分页器;
    3.ajax模板:
        1.创建XHR对象;
            var xhr = new XMLHttpRequest();

            注意: 解决低版本IE的兼容性问题:
                    var xhr = null;
                    if(window.XMLHttpRequest){
                        xhr = new XMLHttpRequest();
                    }else{
                        //考虑低版本IE
                        xhr = new ActiveXObject("Microsoft.XMLHTTP");
                    }
        2.读取
            格式:  open("请求方式get/post","url","true/false") 默认true表示异步操作
        3.发送
            格式:  send()   
        4.监听函数
            格式:  
            xhr.onreadystatechange = function(){
                if(xhr.readyState == 4){    //响应数据
                    if(xhr.status == 200){     //http协议状态
                        console.log(xhr.responseText);   //返回的数据为字符串
                    }
                }
            }

        * get传参时: url地址栏中直接传递  
                     xhr.open("get","xxx?参数1=参数值&..." ); 
                     xhr.send();
        * post传参时: 不是url直接传递  是send(发送数据)  但发送前必须配置请求头
                    xhr.open("post","url",true);
                    var date = `...`;
                    xhr.setRequestHeader("Content-type","application/x-www-form-urlencoded;charset=utf-8");
                    xhr.send(date);

        注: xhr.readyState:
            0: 初始化xhr对象 未请求;
            1: 发送请求服务器;
            2: 服务器接收请求;
            3: 服务器处理请求;
            4: 服务器处理完毕,响应数据;
```

### 15. js - ajax - jQuery - 跨域 {#15-js---ajax---jquery---跨域}

``` javascript
 5.跨域 （即访问不同源的问题）:
        
            跨域项目: jQuery的请求方法:
                1.ajax方法:
                    $.ajax({
                        type:"",
                        url:"",
                        data:{},
                        success:function(res){
                            console.log(res);
                        }
                    })
                2.$.get方法:
                    $.get("url",{key:value,...},callback,type返回的数据类型json);
                3.$.getJSON方法:
                    $.getJSON("url",{key:value,...},callback);
                4.$.post()方法:
                    $.post("url",{key:value,...},callback,type返回的数据类型);

            同源策略: 也就是协议、域名、端口都一致;
            解决方案: 
                a.后台代理:(php代理);
                    格式: php代码: $res = file_get_contents("url");
                                    echo "$res";
                b.jsonp;
                c.cors资源共享;
                d.proxy反向代理;
                e.iframe(早期写法);


            百度的接口:  http://suggestion.baidu.com/su?cb=callback&wd=aa;
            
            蓝莓派接口: http://iwenwiki.com/api/blueberrypai/getIndexBanner.php;

            乐章接口:  http://iwenwiki.com/api/blueberrypai/getIndexMovement.php;

```

### 16. js - 跨域解决办法 {#16-js---跨域解决办法}

``` javascript
1).
    1.什么是跨域 什么情况下产生跨域？
        从当前的域下去访问其他的域下的资源,浏览器的同源策略出于安全考虑默认是不允许的是阻止的。

    2.同源策略？
        同源策略是 浏览器最核心的最基本的安全的功能。如果是同源的可以页面数据可以相互访问，非同源不允许
        同源策略即是 协议  域名  端口号 三个必须一致  有一个不同就跨域

    3.跨域解决方案 (重点)
        1.jsonp 
        2.cors 资源共享
        3.代理 proxy  (四阶段)
        4.iframe 

    4. php代理 
        $con=file_get_content('');  echo $con;

    5.jsonp实现原理 (重点)
        动态创建script标签,利用script标签的src属性可以访问浏览器上的任意资源，不存在跨域。所以我们让src访问服务器资源
        服务器接受请求 处理内容。前端需要定义函数接受后台返回的数据。

        备注：
            jsonp只有get请求 
            
    6.jsonp 实现 (掌握)
        1.script写法  ---百度案例
        2.jquery写法
            $.ajax({
                type:'get',
                url:'',
                data:{},
                dataType:'jsonp',
                jsonp:'后台接受的变量-函数名',
                jsonpCallback:'返回给前端的函数名-可以省略',
                success:callback
            })

    7.cors 资源共享 (掌握)  
```

### 17. js - cookies {#17-js---cookies}

``` javascript
cookies语法:
            特点: 需要网络, 大小为4kb左右, 可以设置过期时间(expires用于设置过期时间);
        1.存储: document.cookies = "key = value;expires = GTMString;path = /";
            key: 键明;
            value: 键值;
            expires: 过期时间  有效范围;
            GTMString: 格林尼治时间 
            path=/: 存储位置/根目录;

        注意: 过期时间: 不是当前是的时间,是国际时间,格林尼治时间;
                        当前时间.UTCString()
              存储信息: 如果是中文必须转码(转中文) 存储数据简单的数据类型;
                中文转码: encodeURLComponent(内容);
                中文解码: decodeURLComponent(内容);
```

### 18. js - localStorage {#18-js---localstorage}

``` javascript
localStorage语法:
            特点: 不需要网络, 存储大小为5M, 可永久存储;
        1. 设置: localStorage.setItem(key,value);
        2. 获取: localStorage.getItem(key);
        3. 移出: localStorage.removeItem(key);
        4. 清空: localStorage.clear();   清空所有

        注意: 存储的是复杂的数据类型,需要进行数据的处理;
            复杂的数据类型转化为字符串: JSON.Stringify();
            复杂的数据类型转化为对象: JSON.parse(); 
```

### 19. js - sessionStorage {#19-js---sessionstorage}

``` javascript
sessionStorage语法:
            特点: 不需要网络, 大小为5M, 会话存储关闭浏览器后会清空;
        1. 设置: sessionStorage.setItem(key,value);
        2. 获取: sessionStorage.getItem(key);
        3. 移出: sessionStorage.removeItem(key);
        4. 清空: sessionStorage.clear();   清空所有
```

### 20. js - canvas {#20-js---canvas}

``` javascript
canvas
基本绘制方式
    1.绘制矩形
            ctx.fillRect(x,y,w,h);
            描边：
            ctx.strokeRect(x,y,w,h)
            清空
            ctx.clearRect(x,y,w,h)

        2.绘制路径
            开始新路径
            ctx.beginPath()
            闭合路径
            ctx.closePath()
            描边
            ctx.stroke()
            填充
            ctx.fill()
            开始位置点
            ctx.moveTo(x,y)
            路径
            ctx.lineTo(x,y)
        3.颜色
            ctx.fillStyle='颜色'
            ctx.strokeStyle='颜色'
            ctx.lineWidth='大小'
        4.绘制圆
            ctx.arc(x,y,r,startAngle,endAngle,boolean)
            画圆后记得填充或是描边

        5.文字
            ctx.font='字体大小  字体种类'
            ctx.fillStyle='字体颜色'
            文字绘制：实心文字 描边文字  文字的位置是左下对齐
            ctx.fillText('文字',x,y)
            ctx.strokeText('文字',x,y)

        6.图片
            创建图片对象
            var img=new Image();
            img.src='图片路径';
            img.onload=function(){
                //绘制ctx.drawImage()
            }
            绘制语法
            ctx.drawImage(img,x,y)
            ctx.drawImage(img,x,y,img-width,img-height)
            ctx.drawImage(img,img-x,img-y,img-w,img-h,canvas-x,canvas-y,canvas-width,canvas-height);
        7.变形  
            ctx.save()
            ctx.restore() 
            平移 旋转  缩放
            ctx.translate(x,y)
            ctx.rotate(弧度)
            ctx.scale(x,y)
```

1.  

# PHP

### 1. php - 语法 {#1-php---语法}

``` php
1)数据类型:
    1.变量定义:
        $变量名 = 内容;
    2.查看数据类型:
        gettype($变量名);    
    2.数据类型: 
        String,boolean,integer,float,null,array,object;
    3.输出方法:
        a. ache: 简单的数据类型;
        b. var_dump(变量): 输出的是数据类型和内容;
        c. print_r(数组);   数组的输出;

    4.数组:
        a. $(数组名) = [];
        b. $(数组名) = array(key=>value.....);
        c. $(数组名) = [key=>value.....];
     数组的遍历:
        foreach(数组名 as $item每一项内容){echo $item};
        foreach(数组名 as $key=>$value){echo $key $value};
    5.区别:
        1.字符串与js的区别:
            a. js中自字符串的拼接用+,php用.;
            b. php中"" '',""先解析变量;''直接输出内容;
```

### 2. php - 连接数据库 {#2-php---连接数据库}

``` php
2)php连接数据库:
    1.创建连接
        格式: $mysqli_connect("域名","账号","密码","数据库的名字","端口号"); (端口号可以省略)
    2.设置编码
        格式: mysqli_query("连接的数据库","set names utf8");
    3.插入数据
        格式: $变量名 "insert into 表名("字段1","字段2"...) values("值","值"...)";
    4.执行sql语句
        格式: mysqli_query("连接的数据库","需要插入的数据");
    5.关闭数据库(只会在下面起到作用)
        格式: mysqli-close("连接的数据库");
    

    注意: 执行sql时:要处理数组时:
        if($res->num_rows>0){
            echo "查询成功";
            $arr = mysqli_fetch_all($res,MYSQLI_ASSOC);
            print_r($arr)};
```

# WX小程序开发

### 01. wx - 基础 {#01-wx---基础}

##### 1.wxml的导入方法 {#1wxml的导入方法}

-   imort的导入

    -   1.主要是导入的模板templete

    -   2.特点：不能进行递归导入

-   include引入

    -   1.将公共的wxml中的组件进行抽取到一个文件中

    -   2.特点：不能导入templete/wxs，可以进行递归导入

##### 2.wxs的使用 {#2wxs的使用}

-   1.直接在wxml中使用

    ``` javascript
    <wxs module="info" >
      var name = "张三"
      var sum = function(num1,num2) {
        return num1 + num2
      }

      // 必须导出 commonJs
      module.exports = {
        name:name,
        sum:sum
      }
    </wxs>

    <view>{{info.name}}</view>
    <view>{{info.sum(10,20)}}</view>
    ```

-   2.将wxs抽离在外部文件，在wxml进行引用

    ``` javascript
    1.外部文件：
    var name = "张三"
    var sum = function(num1,num2) {
      return num1 + num2
    }

    module.exports = {
      name:name,
      sum:sum
    }

    2.在wxml中的使用：
    <wxs src = "../../sources/test.wxs" module="info"></wxs>
    <view>{{info.name}}</view>
    <view>{{info.sum(10,20)}}</view>
    ```

##### 3.组件化开发 {#3组件化开发}

1）组件中数据的传递：

``` javascript
1.在组件中：
Component({
  properties: {
    //title:String,    //第一种方法
    title:{
      type:String,
      value:"我的默认的标题",
      observer:function(newVal,oldVal){     //当数据发生改变时被调用
        console.log(newVal,oldVal);
      }
    }
  },
})


2.使用时：
 + 在使用页面的json配置文件中引入组件
    {
      "usingComponents": {
        "cpn1":"/components/cpn1"
      }
    }
 + 在使用的页面中
    <cpn1 title="呵呵呵"></cpn1>
    <cpn1 title="嘿嘿嘿"></cpn1>
    <cpn1></cpn1>
```

##### 4. 组件与页面样式的相互影响 {#4-组件与页面样式的相互影响}

在**Components**对象中，传入一个**options**属性，其中**options**数字那个中有一个**styleIsolation**（隔离）属性，共有三个取值

-   **isolated**
    表示启用样式隔离，即组件内部的样式和使用时所在页面中的样式不会有影响
    （默认）

-   **apply-shared**
    表示页面中的样式会影响定义的组件，组件中的样式不会影响页面

-   **shared** 页面与定义的组件之间相互影响

示例：

``` javascript
Component({
   options:{
     styleIsolation:"apply-shared"
   }, 
})
```

##### 5.给组件传入样式 {#5给组件传入样式}

``` javascript
1.在组件的wxml中：
	<view class="title titleclass">{{title}}</view>
2.在组件中Components对象中：
    Component({
       externalClasses:['titleclass'], 
    })
3.使用组件的页面中：
    <cpn1 title="呵呵呵" titleclass="red"></cpn1>
    <cpn1 title="嘿嘿嘿" titleclass="green"></cpn1>
    <cpn1 titleclass="blue"></cpn1>
4.使用组件的页面wxss中：
    .blue{
      color: blue;
    }
    .red{
      color: red;
    }
    .green{
      color: green;
    }
```

##### 6.自定义事件传递数据 {#6自定义事件传递数据}

示例：使用自定义事件进行数据求和

``` javascript
1.在组件wxml中：
	<button bindtap="jiajia" >+1</button>
2.在组件js中：
    Component({
      methods: {
        jiajia(){
          this.triggerEvent("increment",{},{})
        }
      }
    })
3.在使用组件的页面json中引入：
    {
      "usingComponents": {
        "cpn2":"/components/cpn2/cpn2"
      }
    }
4.在使用组件的页面wxml中：
    <view>当前求和为：{{count}}</view>
    <cpn2 bind:increment="handalIncrement"></cpn2>
5.在使用组件的页面js中：
    Page({
      data: {
        count:0
      },
      handalIncrement(){
        this.setData({
          count:this.data.count+1
        })
      }
    })
```

``` javascript
微信小程序开发:
        1.vxss/css:
            text相当于span; view相当于div;
        2.引入外部样式表时格式: @import "相对路径";
    
        3.视图容器:
            页面布局: div a span img html ul li
            小程序布局: view text image

        3.wx:if="{{变量|表达式}}" wx:for="{{}}" wx:hidden="{{}}"; 

        4.模板传值: data="{{item}}" 接收时:{{item.value}} 
                    data="{{...item}}"  接收时:{{value}} 
        5.
                setTimeout({
                    //设置延时时间
                },"时间 毫秒");

                wx.request({
                    //请求接口
                });

                wx.scanCode({
                    //扫描二维码
                });

                module.exports = [{
                    //暴露接口
                }];

         **** 传值: ①navigator中传值:  src:"url?id=&mima="
                ②js中: wx.navigatorTo({
                    url:"url?id=&mima=";
                })
                ③bindtap绑定事件时  可以直接传参 data-="neirong";
            
            引入: 在wxml中引入:  <import src=""/>;
                  在wxss中引入:  @import "",
                  在js中引入:    var 变量名 = require("相对路径")
                
            时间的获取以及处理:(在js中) 
                var util = require("../../utils/util.js");
                var times1 = util.formatTime(new Date());
                var year = times.split(" ")[0].split("/");
                var time = times.split(" ")[1].split("/");
                console.log(times1);

            bindtap绑定事件时  可以直接传参 data-="neirong";



6.  "navigationStyle":"custom" 取消返回按钮
7.跳转tab页面:
	wx.redirectTo({
        url: '../index/index',
        fail(ex){
        	console.log(ex)//fail can not redirectTo a tabbar page"
        	wx.switchTab({
        	url: '../index/index',
           })
         }
    })
8.wx-json中常用配置:
	1. "navigationBarBackgroundColor": "#fff",   =>设置顶部标题颜色
	2. "enablePullDownRefresh": false,      =>禁止下拉刷新
	3. "navigationStyle":"custom",    =>自定义顶部标题背景文字(取消返回按钮)
	4. "disableScroll": true,   =>禁止滚动
    5. 
```

### 02. wx - 快捷操作 {#02-wx---快捷操作}

``` javascript
//小程序开发快捷操作
        1.查询所有数据
            .where({
                
                键:值
            }
            )

        3.查询指定数据
            .doc(
                键:值
            )

        3.添加数据
            .add({
                data:{
                    //添加数据
                }
            })

        4.修改数据
            .doc("id值")
            .update({
                data:{
                    //修改的数据
                }
            })

        5.删除数据
            .doc("id")
            .remove()

        6.对数据进行排序
            .orderBy("字段值",asc)   //b表示升序
            .orderBy("字段值",desc)   //b表示降序

        7.返回指定条数的数据(分页)
            .limit("数字")
            .skip("")   从第几个数据开始读(不包含当前数字)
            

        8. 云函数初始化

        在project.config.json中添加 "cloudfunctionRoot" : "/cloud";
```

### 03.wx - 登录注册忘记密码设计思路 {#03wx----登录注册忘记密码设计思路}

``` javascript
登录界面设计
一.登录:
1.输入框中的账号密码都不能为空，为空是终止并给予提示账号或密码不能为空
2.调用云数据库查询输入的账号是否存在，不存在时给予提示用户注册并终止
3.输入的账号密码和云数据库中的数据比对，有一个不正确就给予提示账号或者密码错误并终止

二.注册:
1.输入框中的账号密码都不能为空，为空是给予终止并提示账号密码不能为空
2.调用云数据库查询输入账号是否存在，存在时给予提示账号已存在，终止，并跳转至登录页面
3.判断输入的两次密码是否一致，不一致时给予用户提示并终止。
4.开始完成注册，调用云数据库将输入的账号和密码添加至云数据库中。
5.注册成功后给予用户提示注册成功。
6.最后可以跳转至登录页面。

三.忘记密码:
1.输入框中的账号密码都不能为空，为空是终止并给予提示账号密码不能为空
2.调用云数据库查询输入的账号是否存在，不存在时终止并给予用户提示账号不存在。
3.判断两次输入的密码是否一致，不一致时终止并给予提示。
4.获取用户的id或者openid，开始完成修改，调用云数据库通过id或openid修改对应用户的密码。
5.修改成功后给予用户提示重置成功。
6.最后可以跳转至登录页面

四.记住密码
1.取消记住密码时会自动取消勾选自动登录。

五.自动登录
1.勾选自动登录时会自动勾选记住密码。
```

### 04.云函数获取openid {#04云函数获取openid}

``` javascript
App({
 
  //初始化云环境
  onLaunch(){
    wx.cloud.init({
      env:"cloud1-8gum9jr66ef2f382"
    })
  }
})



 "cloudfunctionRoot":"/cloud",


在app.js中实现  和 project.config.json中
```

``` javascript
// 云函数入口文件
const cloud = require('wx-server-sdk')

cloud.init({
  env: cloud.DYNAMIC_CURRENT_ENV
})
// 云函数入口函数
exports.main = async (event, context) => {
  console.log(event);
//  return cloud.database().collection("tests")
//  .get()
}

在创建的云函数中的index.js中实现
```

### 05调用云函数的两种写法： {#05调用云函数的两种写法}

传统方法：
`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016172845116.png" alt="image-20211016172845116" style="zoom: 50%;" />`{=html}

第二种写法

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016173314274.png" alt="image-20211016173314274" style="zoom:50%;" />`{=html}

使用云开发的注意技巧

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016174454442.png" alt="image-20211016174454442" style="zoom: 50%;" />`{=html}

本地和云函数获取数据的方法:

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016175046937.png" alt="image-20211016175046937" style="zoom:50%;" />`{=html}

云函数数据获取和 数据库获取

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016175928446.png" alt="image-20211016175928446" style="zoom:50%;" />`{=html}

本地小程序直接调用数据库（这能修改自己创建的数据）

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016183653573.png" alt="image-20211016183653573" style="zoom: 50%;" />`{=html}

调用云函数更新商品价格

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016183811806.png" alt="image-20211016183811806" style="zoom:50%;" />`{=html}

### 使用云函数：

第一步:先创建云函数（文件名）

代码片段：

``` javascript
```

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016184157833.png" alt="image-20211016184157833" style="zoom:50%;" />`{=html}

第二步调用云函数进行修改

代码片段:

``` javascript
Page({
  onLoad(){
    //调用云环境
    wx.cloud.callFunction({
      name:"getDate",
      data:{a:1,b:2},
      success:res=>{
        console.log(res);
      },
      fail:err=>{
        console.log(err);
      }
    })
  }
})
```

`<img src="C:\Users\薛林杰\AppData\Roaming\Typora\typora-user-images\image-20211016184258383.png" alt="image-20211016184258383" style="zoom:50%;" />`{=html}

# 模块规范化

### 01. 基础 {#01-基础-1}

``` javascript
模块规范化
        js模块: 自执行函数必报  return...

        1.CommonJS:  即:node.js
            1.语法:
                暴露模块: module.exports = value / module.XXX = value
                            暴露的本质就是: exports
                引入模块: require("模块名/自定义的模块路径")
            2.用法:
                cd 进入对应目录后;
                在终端输入指令初始化模块  npm init;
                如需安装其他模块输入指令  npm install uniq --save;
                在终端中使用命令运行     node app.js
        2.AMD: 也就是requirejs
        3.ES6
        4.CMD: 淘宝,阿里的
        4.requireJS:
            文档:https://requirejs.org/docs/api.html
            1.使用步骤:
            创建目录结构:
                project
                    css
                     js
                        app  自己创建的js文件
                            index.js
                            data.js
                        libs 引入的js资源
                            require.js
                        main.js
                    index.html
                    ...
            2.下载requireJS文件
            3.引入js文件
               <script data-main="scripts/main" src="scripts/require.js"></script>
            注:网易音乐API:http://iwenwiki.com:3000/
            --------------------------------------------------------
            如果所导入的第三方资源不遵循ADM模块时 在main.js中:
                参考文档: https://requirejs.org/docs/api.html
                shim:{
                    bootstrap:{
                        deps:["","",""],      //当前资源所所依赖的其他库
                        exports:"bootstrap"    //导出的名字,与开头一致

                    }
                }
        
        
        5. 使用:
                AMD: 推崇依赖前置
                CMD: 推崇依赖就近
```

# Nodejs

### 01. 基础 {#01-基础-2}

-   ``` javascript
    1.node.js:
    		(非阻塞的io,优点:高并发特别好)
            1.node.js是一个名词,不是一种技术,它的技术语言是javascript
            它的目标是让js可以操作服务器,
            2.node.js特点:
                ①单线程
                ②非阻塞的I/O操作   (异步操作数据库)
                ③事件驱动
      ******3.node文件的运行: 在vscode中: node node文件名
                             win+R键
                             在对应文件夹中shift+鼠标右键 
                             在文件根目录中 直接在标签栏中输入 cmd
            4.终端安装cnpm
                    npm install -g cnpm --registry=https://registry.npm.taobao.org

    2.node的浏览端调试
    	 - node --inspect --inspect-brk server.js
    	 
    3.node进程管理工具  （使用时先全局安装）
         - supervisor
         - nodemon (本地进程管理)    (使用时全局安装: npm install nodemon -g)
         - forever
         - pm2
    ```

### 02. npm常用命令 {#02-npm常用命令}

``` javascript
1.npm view     包名 --versions      查询当前包的所有版本
2.npm install  包名@1 --save     安装当前包1.的最高版本
3.npm list     列表查询
```

### 03.上传自定义的模块 {#03上传自定义的模块}

``` javascript
1.注册npm仓库账号
2.上传包:
	-终端输入命令 npm adduser
    -依次输入账号密码以及邮箱(*邮箱需要验证)
	{	
        -（坑-- 镜像位置不正确,需要切换源）
        -查看当前源 npm config set registry
        -切换源 npm config set registry https://registry.npmjs.org
       	-终端输入命令 npm adduser
    	-再次依次输入账号密码以及邮箱(*邮箱需要验证)
    }
3.发布 npm publish
```

### 04.三方模块 {#04三方模块}

``` 
01.nodemailer     -->邮箱验证
02.
```

### 05.nodemailer发送邮箱的使用 {#05nodemailer发送邮箱的使用}

``` javascript
"use strict";
const nodemailer = require("nodemailer");

// let transporter = nodemailer.createTransport({
// host: "smtp.163.com",
// port: 465,
// secure: true, // true for 465, false for other ports
// auth: {
//     user: "x709500@163.com",    //发送方的邮箱地址 
//     pass: "XMKTLEUDZWNRUBKW",    //验证码 
// },
// });

//   // send mail with defined transport object
// let obj=({
//     from: '"Fred Foo 👻" <x709500@163.com>', // sender address
//     to: "2806247140@qq.com",
//     // to: "bar@example.com, baz@example.com", // list of receivers
//     subject: "Hello ✔", // Subject line    
//     text: "Hello world? 以梦为马,不负韶华！", // plain text body
//     // html: "<b>Hello world?</b>", // html body
// });


// transporter.sendMail(obj)



function sendMailer(mail,title,content){
    let transporter = nodemailer.createTransport({
        host: "smtp.163.com",
        port: 465,
        secure: true, // true for 465, false for other ports
        auth: {
            user: "x709500@163.com",    //发送方的邮箱地址 
            pass: "XMKTLEUDZWNRUBKW",    //验证码 
        },
        });
        
          // send mail with defined transport object
        let obj=({
            from: '"Fred Foo 👻" <x709500@163.com>', // sender address
            to: `${mail}`,
            // to: "bar@example.com, baz@example.com", // list of receivers
            // subject: "Hello ✔", // Subject line    
            subject: `${title}`,
            text:`${content}`, // plain text body
            // html: "<b>Hello world?</b>", // html body
        });
        
        
        transporter.sendMail(obj,(err,data)=>{
            if(err){
                console.log("邮箱发送失败");
            }else{
                console.log(data);
            }
        })
        
}

module.exports = sendMailer;





异步请求时:
   return new Promise((resolve,reject)=>{
            transporter.sendMail(obj,(err,data)=>{
            if(err){
                reject();
            }else{
                resolve();
            }
        })

            // if(err){
            //     console.log("邮箱发送失败");
            // }else{
            //     console.log(data);
            // }
        })


```

# Express框架

### 01.使用方法 {#01使用方法}

``` javascript
1.Express框架:
基于Node.js 平台,快捷、开放、极简的web开发框架
安装步骤: 
1)创建一个目录,并进入此目录
2)通过nmp init 命令创建一个package.json文件
3)安装Express,并将其保存依赖到此文件夹中
npm/cnpm install express --save
4)执行文件  node node文件名
5)使用get传参时可使用
const url = require("url")
var str = url.parse(req.url,true)    //url.parse("地址","是否转对象")
var dataUrl = str.query
6)使用post传参时  --使用到中间件
var bodyParser=require('body-parser');
app.use(bodyParser.urlencoded({
    extended:true
}))
7)访问时遇到跨域时:
cors资源共享
//解决跨域
router.all("*",function(req,res,next){
    //设置允许跨域的域名，*代表允许任意域名跨域
    res.header("Access-Control-Allow-Origin","*");
    //允许的header类型
    res.header("Access-Control-Allow-Headers","content-type");
    //跨域允许的请求方式 
    res.header("Access-Control-Allow-Methods","DELETE,PUT,POST,GET,OPTIONS");
    if (req.method.toLowerCase() == 'options')
        res.send(200); //让options尝试请求快速结束
    else
        next();
})
2.可以使用以下方法阻拦路由的继续执行
app.use("/",(req,res,next)=>{
    next();  //表示可以继续执行
})

3.终止链式调用的执行 -->手动抛出一个错误
throw new Error("手动终止");

```

### 02. express传参 -3种方法 {#02-express传参--3种方法}

``` javascript
const express=require('express');
const app=express();

//post中间件
var bodyParser=require('body-parser')
//应用中间件
app.use(express.urlencoded({ extended: true })) 


//1.get参数传递
app.get('/news',(req,res)=>{
    var codeId=req.query.id;//直接获取参数 get请求 {} 
    // console.log(id);
    res.send({
        msg:'新闻',
        id:codeId
    })

})


//2.post 参数
app.post('/login',(req,res)=>{
    var uname=req.body.username;
    var mima=req.body.password;

    res.send({
        uname:uname,
        mima:mima
    })
})

//3.restful API get传递参数的一种方式
//知乎：get参数:https://www.zhihu.com/question/397426376/mima/123 
//   参数：xxxx/id/xxx/mima/xxx
//传统的get参数： xxxx?uname=qq&mima=123
app.get('/zhihu/question/:question/mima/:mima',(req,res)=>{
    //接受参数： req.params['question']  req.params['mima']
    //备注：
    //第一种：获取方式
    // var question=req.params['question'];
    // var mima=req.params['mima'];
    //第二种: 获取方式
    var question=req.params.question
    var mima=req.params.mima

    res.send({
        question:question,
        mima:mima
    })

})

app.listen(3000,()=>[
    console.log(3000)
])
```

### 03. express访问时遇到跨域 {#03-express访问时遇到跨域}

``` javascript
//解决跨域
router.all("*",function(req,res,next){
//设置允许跨域的域名，*代表允许任意域名跨域
res.header("Access-Control-Allow-Origin","*");
//允许的header类型
res.header("Access-Control-Allow-Headers","content-type");
//跨域允许的请求方式 
res.header("Access-Control-Allow-Methods","DELETE,PUT,POST,GET,OPTIONS");
if (req.method.toLowerCase() == 'options')
res.send(200); //让options尝试请求快速结束
else
next();
})
```

### 04. express连接数据库操作 {#04-express连接数据库操作}

``` javascript
//连接数据库
const mysql=require('mysql');
//连接数据 
/**语法：
 * mysql.createConnection({
     host:'',//域名 本地地址
     user:"",数据库的账号
     password:"",数据库的密码
     database:""数据库
     port:"3306" 数据库端口号  默认不写
})
 */
const client=mysql.createConnection({
    host:'localhost',
    user:'root',
    password:"",
    database:"2002"
})

//查询语句
const sql="select * from userinfo";

//执行sql语句
//语法：  client.query(sql,callback) 
client.query(sql,function(err,result){
    if(err){
        console.log('操作失败');
        return;
    }else{
        console.log(result);
    }
})
```

### 05.post请求时的中间件 {#05post请求时的中间件}

``` javascript
//使用中间键   在路由之前引入

var bodyParser = require('body-parser')
app.use(bodyParser.urlencoded({ extended: false }))
app.use(bodyParser.json())
```

### 06.Promise异步请求 {#06promise异步请求}

![](C:\Users\%E8%96%9B%E6%9E%97%E6%9D%B0\AppData\Roaming\Typora\typora-user-images\image-20211110142725551.png)

### 07.nodemailer邮箱模块 {#07nodemailer邮箱模块}

``` javascript
"use strict";
const nodemailer = require("nodemailer");

// let transporter = nodemailer.createTransport({
// host: "smtp.163.com",
// port: 465,
// secure: true, // true for 465, false for other ports
// auth: {
//     user: "x709500@163.com",    //发送方的邮箱地址 
//     pass: "XMKTLEUDZWNRUBKW",    //验证码 
// },
// });

//   // send mail with defined transport object
// let obj=({
//     from: '"Fred Foo 👻" <x709500@163.com>', // sender address
//     to: "2806247140@qq.com",
//     // to: "bar@example.com, baz@example.com", // list of receivers
//     subject: "Hello ✔", // Subject line    
//     text: "Hello world? 以梦为马,不负韶华！", // plain text body
//     // html: "<b>Hello world?</b>", // html body
// });


// transporter.sendMail(obj)



function sendMailer(mail,title,content){
    let transporter = nodemailer.createTransport({
        host: "smtp.163.com",
        port: 465,
        secure: true, // true for 465, false for other ports
        auth: {
            user: "x709500@163.com",    //发送方的邮箱地址 
            pass: "XMKTLEUDZWNRUBKW",    //验证码 
        },
        });
        
          // send mail with defined transport object
        let obj=({
            from: '"Fred Foo 👻" <x709500@163.com>', // sender address
            to: `${mail}`,
            // to: "bar@example.com, baz@example.com", // list of receivers
            // subject: "Hello ✔", // Subject line    
            subject: `${title}`,
            text:`${content}`, // plain text body
            // html: "<b>Hello world?</b>", // html body
        });
        
        
        transporter.sendMail(obj,(err,data)=>{
            if(err){
                console.log("邮箱发送失败");
            }else{
                console.log(data);
            }
        })
        
}

module.exports = sendMailer;





异步请求时:
   return new Promise((resolve,reject)=>{
            transporter.sendMail(obj,(err,data)=>{
            if(err){
                reject();
            }else{
                resolve();
            }
        })

            // if(err){
            //     console.log("邮箱发送失败");
            // }else{
            //     console.log(data);
            // }
        })


```

### 08.注册api {#08注册api}

``` javascript
//注册接口
var updateCodes = {};

wxRouter.post("/reg",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.body);
    var nicheng = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    var code = req.body.code;
    if(user!="" && psd !=""){
        if(nicheng==""){
            return res.send({"err":-1,"msg":"昵称不能为空"})
        }
        if(code==""){
            return res.send({"err":-1,"msg":"验证码不能为空"})
        }
        console.log("66",codes);
        console.log("67",codes[user]);
        console.log("68",code);
        var sql1 = `select * from wx where username= "${user}"` ;
        getQuery(sql1,(result)=>{
            // res.send(result);
            if(result==false){
                if(codes[user] != code){
                    res.send({"err":-1,"msg":"验证码不正确"});
                    return;
                }
                var sql2 = `insert into wx(nicheng,username,password) values("${nicheng}","${user}","${psd}")`;
                getQuery(sql2,(result)=>{
                    res.send({"err":1,"msg":"注册成功"});
                    console.log("成功注册",result);
                })
            }else{
                // console.log("result1",result1);
                res.send({"err":-3,"msg":"账号已存在"});
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})
```

### 09.忘记密码api {#09忘记密码api}

``` javascript
var updateCodes = {};
//忘记密码接口
wxRouter.post("/update",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.body);
    // var name = req.body.nicheng;
    
    var user = req.body.username;
    var psd = req.body.password;
    var code = req.body.code;
    if(user!="" && psd !=""){
        // if(nicheng==""){
        //     return res.send({"err":-1,"msg":"昵称不能为空"})
        // }
        if(code==""){
            return res.send({"err":-1,"msg":"验证码不能为空"})
        }
        console.log(codes);
        console.log(code);
        console.log(codes[user]);
        var sql1 = `select * from wx where username= "${user}"` ;
        getQuery(sql1,(result)=>{
            // res.send(result);
            console.log(result);
            if(result==false){
                res.send({"err":-1,"msg":"账号不存在"});
            }else{
                if(codes[user] != code){
                    res.send({"err":-2,"msg":"验证码不正确"});
                    return;
                }
                var sql2 = `update wx set password = "${psd}" where username = "${user}"` ;
                // update 表名 set 字段名1 = "值1",字段名2 = "值2", where 字段名 = "值";
                getQuery(sql2,(result)=>{
                    res.send({"err":1,"msg":"修改密码成功"});
                    console.log("成功修改密码",result);
                })
                // console.log("result1",result1);
                
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})
```

### 10.登录api {#10登录api}

``` javascript
wxRouter.post("/login",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // var name = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    
    if(user!="" && psd !=""){
        var sqls = `select * from wx where username = "${user}"` ;
        // var sqls = "select * from userInfo";

        getQuery(sqls,(result)=>{
            // res.send(result);
            if(result==false){
                res.send({"err":-1,"msg":"账号不存在,请前往注册"});
            }else{
                var sql5 = `select * from wx where username = "${user}" and password = "${psd}"`
                getQuery(sql5,(result2)=>{
                    if(result2==false){
                        res.send({"err":-2,"msg":"账号或密码错误"});
                    }else{  
                        res.send({"err":1,"msg":"登录成功"});
                        console.log("成功登录",result2);
                    }
                })
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})
```

### 11.邮箱验证码发送api {#11邮箱验证码发送api}

``` javascript
//发送邮箱验证码
wxRouter.post("/getMail",(req,res)=>{   //1565965166@qq.com
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    var mail = req.body.mail;
    var code="";
    for(var i=0;i<6;i++){
        code+= parseInt(Math.random()*10)
    }
    sendMailer(mail,code)
    .then((msg)=>{
        codes[mail] = code
        res.send({"err":1,"msg":"验证码发送成功"});
    })
    .catch((err)=>{
        res.send({"err":-1,"msg":"验证码发送失败"})
    })
})
```

### 12.发送邮箱(封装) {#12发送邮箱封装}

``` javascript
const nodemailer = require("nodemailer");

function sendMailer(mail,code){
    let transporter = nodemailer.createTransport({
        host: "smtp.163.com",
        port: 465,
        secure: true, // true for 465, false for other ports
        auth: {
            user: "x709500@163.com",    //发送方的邮箱地址 
            pass: "XMKTLEUDZWNRUBKW",    //验证码 
        },
        });
        
          // send mail with defined transport object
        let obj=({
            from: '"Fred Foo 👻" <x709500@163.com>', // sender address
            to: `${mail}`,
            // to: "bar@example.com, baz@example.com", // list of receivers
            // subject: "Hello ✔", // Subject line    
            subject: "Hello ✔",
            text:`【安和网】你的验证码: ${code},请勿泄漏,有效时间3分钟！`, // plain text body
            // html: "<b>Hello world?</b>", // html body
        });

        return new Promise((resolve,reject)=>{
            transporter.sendMail(obj,(err,data)=>{
            if(err){
                reject();
            }else{
                resolve();
            }
        })
            // if(err){
            //     console.log("邮箱发送失败");
            // }else{
            //     console.log(data);
            // }
        })
        
}

module.exports = sendMailer;
```

### 13.静态资源目录的使用 {#13静态资源目录的使用}

``` javascript
1.在主js文件中引入使用
	const path = require("path")
    app.use("/public",express.static(path.join(__dirname,"./static")))
                                                           表示指向的文件
                                                           
```

### 14.multer上传文件使用 {#14multer上传文件使用}

#### 前端

**1.利用ajax**

``` javascript
  $("form").submit(function(e){
        e.preventDefault();

        const formData= new FormData($("form")[0])
        console.log(formData);
        $.ajax({
                url:"http://localhost:3000/wxFile/upload",
                method:"POST",
                processData:false,
                contentType:false,
                data:formData,
                success(res){
                    console.log(res);
                    if(res.err==0){
                        console.log("图片上传成功");
                        // $("img").attr("src",`http://localhost:3000${res.img}`)

                        alert("图片上传成功")
                    }else{
                        alert("图片上传失败")
                    }
                }
            })
    })
```

#### 后端

-   **安装 npm i multer \--save**

-   **使用步骤**

-   **配置:**

-   **single方法是专门接收单文件的 （一个名称配一个文件）**

-   **array方法是专门接收多文件的 （一个名称配多个文件）**

-   **field方法是专门接收多个文件的
    （涉及到多个文件需要标志好,即在配置中使用数组加对象的形式）**

-   **在后面的路由处理函数中: 接收单文件 （req.file) ；
    接收多文件(req.files)**

-   ``` javascript
    const router = require("express").Router();
    const multer = require("multer");
    const path = require("path")

    //multer生成一个接收器,将接收到的文件直接存在指定的目录中
    const storage = multer.diskStorage({
        destination: function (req, file, cb) {
          cb(null, './uploads/')   // 路径 
        },
        filename: function (req, file, cb) {
            console.log(file);
          const uniqueSuffix = Date.now() + '-' + Math.round(Math.random() * 1E9)  
          const typeImg = path.extname(file.originalname)    //直接获取文件的后缀
          cb(null, file.fieldname + '-' + uniqueSuffix + typeImg)
        }
      })
      
    const fileUpload = multer({ storage: storage })



    //在需要的路由中进行配置
    router.post("/upload",fileUpload.single("nihao"),(req,res)=>{
    	 console.log(req.file);
        let {filename,size,mimetype}  =req.file
        let fileType = ["jpg","jpeg","webp","png"] 
        if(size>5000000) return res.send({code:400,msg:"图片上传失败:图片过大,请重新上传"})
        if(size>5555555) return res.send({code:400,msg:"图片上传失败:图片过大,请重新上传"})
        if(fileType.indexOf(mimetype.split("/")[1]) == -1) return res.send({code:401,msg:"图片上传失败:文件类型错误,请重新上传"})
        let path = `/public/static/images/${filename}`
        res.send({code:200,msg:"图片上传成功",url:path})
        })
    ```

    //完整路由代码

``` javascript
const express = require("express");
const fileRouter = express.Router();
const multer = require("multer");


let upload = multer({
    storage: multer.diskStorage({
        destination: function (req, file, cb) {
            //指定文件路径
            cb(null, './static/images');
        },
        filename: function (req, file, cb) {
            //指定文件名
            // console.log(file);
            var times = (new Date()).getTime() + parseInt(Math.random() *999);
            var typeInfos = file.originalname.split(".");
            var typeInfo = typeInfos[typeInfos.length-1];
            cb(null, `${times}.${typeInfo}`);
        }
    })
});


//单个文件上传
fileRouter.post('/upload', upload.single('singleFile'), (req, res) => {    //进行post传参时,key为singleFile
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
       
    console.log(req.file);
    let {size,mimetype,filename} = req.file;      
    var fileType = ["jpg","jpeg","webp","png","gif"];    //支持上传的文件类型

    if(size>111377000){
        return res.send({err:-1,msg:"文件过大"});
    }else if(fileType.indexOf(mimetype.split("/")[1]) == -1){
        return res.send({err:-1,msg:"文件类型错误"});
    }else{
        //http://localhost:3000/public/images/1636970483666.jpg
        var urls = `/public/images/${filename}`;
        res.send({err:0,msg:"上传成功",img:urls});
    }
});

module.exports = fileRouter;
```

### 15.cors资源共享解决跨域 {#15cors资源共享解决跨域}

``` javascript
 1.在后台路由处设置请求头
  res.setHeader("Access-Control-Allow-Origin","*");
  res.setHeader("Access-Control-Allow-Methods", "*");
  res.setHeader("Access-Control-Allow-Headers",  "*");
 2.安装cors三方插件
 	-> npm i cors
    -> const cors = require("cors")
	-> 在路由引入之前
	-> app.use(cors)
```

### 16.token验证 {#16token验证}

-   ##### **为什么需要token**

    `=> http 无状态`

    `=> session 无法跨服务器`

    `=> cors跨域后cookies无法使用`

-   ##### **token是什么**

    `=> 三段式的加密字符串`

    `=> 第一段和第三段是不可逆加密`

    `=> 第二段是base64可逆加密`

-   ##### **jwt**

    `=> **jsonwebtoken**`

    `=> 专门生成token和解析token的一个插件`

-   ##### 使用jwt

     1. 下载: npm i jsonwebtoken

     2. 导入；

     3. 使用:

    => 生成 jwt.sign( 保存的信息，口令，参数 )

    -\> 保存的信息 (为对象)

    -\> 口令: 加密口令，加密时混入消息使用，解密时还需要此口令

    -\> 参数: 是一个对象 expiresIn： 过期时间，单位秒 (\"1d\")

    => 解密 jwt.verify( 解析的token，口令，回调函数)

    -\> token: 必须是一个指定的token

    -\> 口令: 必须是加密时的口令

    -\> 回调函数: 接收结果

    => 前端进行本地存储，携带在请求头中传入后端

    ``` javascript
    1.原生js: xhr.setReruestHeaders（"authorization" : token）
    2.query： beforeSend:function(request){
        			request.setRequestHeader("authorization",token)
    		  },
    ```

    后端接收 req.headers

    ``` javascript
    jwt.sign("保存的信息(对象)"， 口令 , 参数 )   参数一般为: {expieseIn: 单位秒}
    jwt.verify("解析的token" ， 口令 ， 回调函数)
    ```

### 17.apidoc {#17apidoc}

``` javascript
1.apidoc.json配置文件内容:
	{
    "name": "食谱管理api",
    "version": "1.1.1",
    "description": "apiDoc basic example",
    "title": "api",
    "url" : "https://xxx.helloxlj.top"
  	}
```

### 18.11-12代码 {#1811-12代码}

``` javascript
const express = require("express");
const router = express.Router();
const getQuery = require("../util/mysql");

const sendMailer = require("../util/mail"); 


var codes = {};
//测试接口
router.get("/",(req,res)=>{
    res.send("欢迎访问")
})



//查询所有接口
router.get("/select",(req,res)=>{
    var sql = "select * from userInfo"
    getQuery(sql,(result)=>{
        res.send(result)
    })
})



//注册接口
router.post("/reg",(req,res)=>{
    // console.log(req.body);
    var name = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    // var code = req.body.code;

    if(user!="" && psd !=""){
        // console.log(codes);
        // console.log(code);
        // console.log(codes[user]);
        // if(codes[user]!= code){
        //     return res.send({"err":1,"msg":"验证码错误"})
        // };
        var sql1 = `select * from userInfo where username = ${user}`;
        getQuery(sql1,(result1)=>{
            res.send(result);
            if(result1==false){
                var sql2 = `insert into userInfo(nicheng,username,password) values("${name}","${user}","${psd}")`;
                getQuery(sql2,(result2)=>{
                    res.send({"err":1,"msg":"注册成功"});
                    console.log("成功注册",result2);
                })
            }else{
                // console.log("result1",result1);
                res.send({"err":-1,"msg":"账号已存在"});
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})



//登录接口
router.post("/login",(req,res)=>{
    // var name = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    
    if(user!="" && psd !=""){
        var sql1 = `select * from userInfo where username = ${user}`;
        getQuery(sql1,(result1)=>{
            // res.send(result);
            if(result1==false){
                res.send({"err":-1,"msg":"账号不存在,请前往注册"});
            }else{
                var sql2 = `select * from userInfo where username = ${user} and password = ${psd}`;
                getQuery(sql2,(result2)=>{
                    if(result2==false){
                        res.send({"err":-1,"msg":"账号或密码错误"});
                    }else{  
                        res.send({"err":1,"msg":"登录成功"});
                        console.log("成功登录",result2);
                    }
                })
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})



//发送邮箱验证码
router.post("/getMail",(req,res)=>{
    var mail = req.body.mail;
    var code="";
    for(var i=0;i<6;i++){
        code+= parseInt(Math.random()*10)
    }
    sendMailer(mail,code)
    .then((msg)=>{
        codes[mail] = code;
        res.send({"err":1,"msg":"验证码发送成功"});
    })
    .catch((err)=>{
        res.send({"err":-1,"msg":"验证码发送失败"})
    })
})


module.exports = router;
```

# Markdown

### 01.基本使用 {#01基本使用}

```` markdown
### markdown的使用
1.标题:
    # 标题1
    ## 标题2
2.代码块:
    ```
     console.log("你好生活");
    ```
3.引用
	> 内容的引用
4.列表
    + 列表1
    + 列表2
        + 信息1
        - 信息1
        + 信息1
    + 列表3
    + 列表4
5.点击链接
[官网链接](https://www.baidu.com)
````

# ES6

### 01.解构赋值 {#01解构赋值}

``` javascript
// 1.数值的解构
    const arr = ["你","真","搞","笑"];
    let [a1,a2,a3,a4] = arr;
    console.log(a1);
    console.log(a2);
    console.log(a3);
    console.log(a4);


//2. 对象赋值
    const obj = {
        name : "你好",
        age : 18,
        speak : function(){
            console.log("我会说英语");
        }
    }

    let {namename,age,speak} = obj;
    console.log(name);
    console.log(age);
    console.log(speak);
    speak();
```

### 02.扩展运算符 {#02扩展运算符}

![](C:\Users\%E8%96%9B%E6%9E%97%E6%9D%B0\AppData\Roaming\Typora\typora-user-images\image-20211115103847343.png)

### 03.js的数据类型 {#03js的数据类型}

``` javascript
// USONB    you are so niubility

    u: undefined
    s: string symbol
    o: object
    n: null number
    b: boolean
```

### 04.为symbol创建对象属性 {#04为symbol创建对象属性}

![](C:\Users\%E8%96%9B%E6%9E%97%E6%9D%B0\AppData\Roaming\Typora\typora-user-images\image-20211115143832776.png)

### 06.ES6模块化 {#06es6模块化}

**1.初识**

-   AMD 和 CMD 适用于浏览器端的 JavaScript 模块化

-   CommonJs 适用于服务器端的 JavaScript 模块化

**2.ES6模块化基本语法**

1.  ***默认导出 与 默认导入***

    -   默认导出：export default { 默认导出的成员 }

    -   默认导入：import 接收名称 from \"模块标识符\"

    -   注意：每个模块中只允许使用唯一的一次 export default;

2.  ***按需导出 与 按需导入***

    -   按需导出：export let s1 = 10

    -   按需导入：import { s1 } from \"模块标识符\"

    -   注意：每个模块中可以使用多次按需导出

3.  ***直接导出 与 直接导入***

    -   直接导入即执行代码 import \"模块标识符\"

### 07.webpack {#07webpack}

**4个现代化：**\
**模块化；**

**组件化；**

**规范化；**

**自动化；**

`早先的前端工程化：gulp 、grunt`

`现今的前端工程化：webapck、vite、parcel`

**1.在项目中的安装与使用**

-   创建目录（包含src\--\>index.js），执行 `npm init -y`
    命令，初始化包管理配置文件 package.json

-   执行 `npm install webpack webpack-cli -D` 命令，安装webpack相关的包

-   在项目根目录中，创建名为 `webpack.config.js` 的webpack配置文件

-   在webpack配置文件中，初始化如下基本配置:

    ``` javascript
    module.exports = {
    	mode: "development"   //mode 用来指定构建模式
    }
    ```

-   在package.json配置文件中的scripts节点下，新增dev脚本如下:

    ``` javascript
    "scripts":{
    	"dev":"webpack"  //script节点下的脚本，可以通过npm run 执行
    }
    ```

-   在终端中执行 `npm run dev` 命令，启动webpack进行项目打包

**2.配置打包的入口与出口**

***webpack的4.X版本中默认的约定:***

-   打包的`<span style="color:red">`{=html}入口文件文件为`</span>`{=html}
    src -\> index.js

-   打包的`<span style="color:red">`{=html}输入文件文件为`</span>`{=html}
    dist -\> main.js

***如果需要更改打包文件的入口与出口，可在 webpack.config.js
中增加如下配置：***

``` javascript
const path = require("path");  // 导入 node.js中操作路径的模块
module.exports = {
    entry:path.join(__dirname,"./src/index.js"),  //打包入口文件的路径
    output:{
        path:path.join(__dirname,"./dist"),    //输出文件的存放路径
        filename:"buldle.js"      //输出文件的名称
    }
}
```

***3.配置webpack自动打包的功能***

-   运行 `npm install webpack-dev-server -D`
    命令，安装支持项目自动打包的工具

-   修改package.json -\> scripts 中的 dev 命令如下:

    ``` javascript
    "scripts":{
    	"dev":"webpack-dev-server"  //script节点下的脚本，可以通过npm run 执行
    }
    "scripts":{
    	"dev":"webpack-dev-server --open"  //script节点下的脚本，可以通过npm run 执行
    }  //自动打开
    "scripts":{
    	"build":"webpack --mode production"  //script节点下的脚本，可以通过npm run 执行
    }  //项目进行打包和发布
    ```

-   将src -\> index.html 中，script脚本的引用路径修改为 \"/buldle.js\"

-   运行 `npm run dev` 命令，重新进行打包

-   在浏览器中访问 <http://localhost:8080> 地址，查看自动打包效果

`<span style="color:red">`{=html}注意访问时如果出现Cannot GET
/则需要在webpack.config.js中配置以下内容`</span>`{=html}

``` javascript
 devServer:{
        //新版本不支持contentBase,应添加这一段话，显示目录
        static:{
            directory:__dirname
        },
        open:true,   	//配置自动打开浏览器
 },
```

***4.配置 html-webpack-plugin 生成预览页面***

-   运行 `npm install html-webpack-plugin -D`
    命令，安装生成预览页面的插件

-   修改webpack.config.js文件头部区域,添加如下配置信息

    ``` javascript
    //导入生成浏览页面的插件，得到一个构造函数
    const HtmlWebPack = require("html-webpack-plugin");
    const htmlPlugin = new HtmlWebPack({   // 创建插件的实例对象
        template:"./src/index.html",    //指定要用到的模板文件
        filename:"index.html"  //指定生成文件的名称,该文件存放于内存中，在目录不显示
    })
    ```

-   修改webpack.config.js文件向外暴露的配置对象，新增如下配置节点

    ``` javascript
    module.exports = {
        plugins:[ htmlPlugin ]  // plugins数组是 webpack 打包期间会使用到的一些插件列表
    }
    ```

------------------------------------------------------------------------

# js补充

### 1.显式原型与隐式原型 {#1显式原型与隐式原型}

-   **每个构造函数都有一个
    prototype属性，且返回的是一个空的Object属性。（显式原型）**

-   **每个构造函数都有一个 \--proto\-- 属性（隐式原型）**

### 2.instanceof的使用 {#2instanceof的使用}

-   **A instance of B**

-   判断**实例对象A的隐式原型**是否等于**构造函数B的显式原型**， 返回
    **true** or **false**

### 3.Symobl {#3symobl}

-   **`Symbol` 是唯一标识符的基本类型**

-   **Symbol 是使用带有可选描述（name）的 `Symbol()` 调用创建的**。

-   **Symbol 总是不同的值，即使它们有相同的名字。如果希望同名的 Symbol
    相等，应该使用全局注册表：`Symbol.for(key)`
    返回（如果需要的话则创建）一个以 `key` 作为名字的全局 Symbol。使用
    `Symbol.for` 多次调用 `key` 相同的 Symbol 时，返回的就是同一个
    Symbol**。

1.`toString()` `description`

``` javascript
let id1 = Symbol("id")
let id2 = Symbol("id")
// alert(id1)    //报错。Symbol不会被隐式转换，
console.log(id1.toString());  // Symbol(id) //转化为字符串
console.log(id1.description);  //id      //获取到描述

let user = {
    name:"张三",
}

let id = Symbol('age')
user[id] = "22",

console.log(user.name);
```

2.在字面量中使用Symbol时，需要使用中括号

``` javascript
let id = Symbol('age')
let user = {
    name:"张三",
    [id]:22
}
console.log(user);   //{name: '张三', Symbol(age): 22}
```

3.Symbol不参与for in的循环

``` javascript
let hobby = Symbol("hobby")
let user =  {
    name:"张三",
    age:12,
    [hobby]:"学习"
}

console.log(user);   //{name: '张三', age: 12, Symbol(hobby): '学习'}
for(key in user){
    console.log(key);  
}
alert(user[hobby])  //可以访问到 
```

1.  从注册表中读取（不存在则创建）Symbol，使用 `Symbol.for(key)`

``` javascript
let id1 = Symbol.for("123")   
let id2 = Symbol.for("123")
console.log(id1);     //Symbol(123)
console.log(id2);     //Symbol(123)
console.log(id1==id2);   //true
```

1.  对于全局 Symbol，不仅有 `Symbol.for(key)` 按名字返回一个
    Symbol，还有一个反向调用：`symbol.keyFor(sym)`，它的作用完全反过来：通过全局
    Symbol 返回一个名字。 对于非全局的返回undefined

``` javascript
let id1 = Symbol("id")
let id2 = Symbol.for("age")
let id3 = Symbol.for("name")

console.log(Symbol.keyFor(id1));   //非全局的返回undefined
console.log(Symbol.keyFor(id2));   //age
console.log(Symbol.keyFor(id3));   //name
```

6.Symbol 不是 100%
隐藏的。有一个内置方法**Object.getOwnPropertySymbols(obj)**
允许我们获取所有的 Symbol。

``` javascript
let age = Symbol("age")
let hobby = Symbol("hobby")
let user = {
    name:'张三',
    [age]:12,
    [hobby]:"学习"
}
console.log(user);  //{name: '张三', Symbol(age): 12, Symbol(hobby): '学习'}
let res = Object.getOwnPropertySymbols(user)
console.log(res);   //[Symbol(age), Symbol(hobby)]
console.log(user[res[0]]); //12
```

### 4.Set {#4set}

`<span style="color:red">`{=html}`Set` 是一个特殊的类型集合 －
"值的集合"（没有键），它的每一个值只能出现一次。`</span>`{=html}

**1.Set中的方法：**

-   `new Set(iterable)` ------ 创建一个 `set`，如果提供了一个 `iterable`
    对象（通常是数组），将会从数组里面复制值到 `set` 中。

-   `set.add(value)` ------ 添加一个值，返回 set 本身

-   `set.delete(value)` ------ 删除值，如果 `value`
    在这个方法调用的时候存在则返回 `true` ，否则返回 `false`。

-   `set.has(value)` ------ 如果 `value` 在 set 中，返回
    `true`，否则返回 `false`。

-   `set.clear()` ------ 清空 set。

-   `set.size` ------ 返回元素个数。

``` javascript
// let arr = [1,2,3,1,1]  
// console.log(arr)   //可以重复 [1, 2, 3, 1, 1]

// let arr = new  Set([1,4,5,1,2,3])
// console.log(arr);   // 不可重复{1, 4, 5, 2, 3}

let arr = new Set()
arr.add(1)
arr.add(3)
arr.add(4)
arr.add(1)
console.log(arr); //{1, 3, 4}

//获取长度
console.log(arr.size)  //3

//删除指定内容
console.log(arr.delete(1))  //有返回值 true or false
console.log(arr);  //{3, 4}

//清空所有
arr.clear()
console.log(arr); //{size: 0}


// 遍历set
let set = new Set([1,22,3,42])
for(let x of set){
    console.log(x);
}

// eg:实现去重(数据类型的转换)
let set1 = new Set([4,5,6,23,4,5,6])
let res = new Set([...set1]) 
console.log(res);   //{4, 5, 6, 23}


//并集、交集、差集
let a = new Set([1,2,4,5,12,22])
let b = new Set([1,3,4,8,10,22])

//1.并集
console.log(new Set([...a],[...b]));
//2.交集
console.log(new Set([...a].filter(item=>b.has(item))));  //{1, 4, 22}
//3.差集
console.log(new Set([...a].filter(item=>!b.has(item))));  //{2, 5, 12}
```

### 5.WeakSet {#5weakset}

-   与`Set`相比，`WeakSet`
    只能是**对象的集合**，而不能是任何类型的任意值。

-   `WeakSet`持弱引用：集合中对象的引用为弱引用。
    如果没有其他的对`WeakSet`中对象的引用，那么这些对象会被当成垃圾回收掉。
    这也意味着WeakSet中没有存储当前对象的列表。 正因为这样，`WeakSet`
    是不可枚举的。

------------------------------------------------------------------------

### 6.Map {#6map}

`<span style="color:red">`{=html}[Map]()
是一个带键的数据项的集合，就像一个 `Object` 一样。 但是它们最大的差别是
`Map` 允许任何类型的键（key）。`</span>`{=html}

**1.Map中的方法**

-   `new Map()` 创建map集合

-   `map.set(key,value)` 存储数据

-   `map.get(key)` 根据键得到值，没有返回undefined

-   `map.delete(key)` 删除指定内容

-   `map.has(key)` 判断键是否存在 返回true或false

-   `map.clear()` 清空所有

-   `map.size` 返回当前的个数

**2.Map数据类型与普通的obj转换**

-   `new Map(Object.entries(obj))` obj=>Map

-   `Object.fromEntries(objMap)` Map=>obj

``` javascript
let obj ={ 
    name:"张三",
    age:33
}

console.log(Object.entries(obj));    //[Array(2), Array(2)]

let objMap = new Map(Object.entries(obj))   //将对象转化为map集合
console.log(objMap);     //{'name' => '张三', 'age' => 33}

let newObjMap = Object.fromEntries(objMap)   //将Map类型的数据转化为普通的obj对象
console.log(newObjMap);     //{name: '张三', age: 33}
```

``` javascript
let map = new Map([["name","123"]])
map.set("张三","lisi")
// console.log(map.has("name1"))  //判断是否存在该属性
// map.delete("name")       //删除指定内容，有返回值
// map.clear()              //清空所有
// console.log(map.size)     //得到长度
// console.log(map.keys());    //得到所有键
// console.log(map.values());    //得到所有值
// console.log(map.entries());    //得到所有键值对
for(let key of map){
    // console.log(key);     // 遍历每一项
}

console.log([...map]);    //展开后为数组
console.log(map);
```

### 7.WeakMap {#7weakmap}

-   与`Map`相比，`WeakMap` 键只能是**引用类型**。

### 8.闭包 {#8闭包}

-   内部函数总是可以访问其所在的外部函数中声明的变量和参数

-   作用：1.读取函数内部的变量，2.可以让这些变量的值始终保持在内存中

-   注意点：闭包会使得函数中的变量都被保存在内存中，内存消耗很大，不能滥用闭包，否则会造成网页的性能问题，解决：退出函数之前，将不使用的局部变量全部删除。

-   `例子1 可以得到上一层函数中的变量`

``` javascript
function getName(){
    let name = "张三"
    return function(){
        return name
    }
}

let res = getName()
console.log(res());
```

-   `例子2 使用闭包返回数组中的元素 (4-11之间的数)`

``` javascript
let arr = [1,3,4,5,11,7,8,12,3]
function getMiddle(a,b){
    return function(v){
        return v>=a && v<=b
    }
}
console.log(arr.filter(getMiddle(4,11)));
```

-   `例子3 计时器中使用闭包来获取独有变量`

``` javascript
<style>
    button{
        position: absolute;
    }
</style>

<button>点我移动</button>
<button>点我移动+1+1</button>

let btn = document.querySelectorAll("button");
btn.forEach(function (item) {
    let left = 0;
    let bind = false;
    item.addEventListener("click", function () {
        if (!bind) {
            bind = true;
            setInterval(function () {
                item.style.left = left++ + "px";
            }, 100);
        }
    });
});
```

-   `例子4 使用闭包导致内存泄漏问题解决`

``` javascript
<div>张三</div>
<div>李四</div>

let divs = document.querySelectorAll("div")
divs.forEach(item=>{
    let res = item.innerHTML
    item.addEventListener("click",()=>{
        console.log(res);
        //console.log(item);  //会将节点保留在内存中
    })
    item = null
})
```

### 9.call、apply、bind {#9callapplybind}

-   **call()、apply()、bind() 都是用来重定义 this 的！**

`例子1`

``` javascript
var name = "KangKang",
    age = 19;
let obj = {
    name: "张三",
    ObjAge: this.age,
    show: function () {
        // console.log(this);      //指向obj
        console.log(this.name, this.age);
    },
};

console.log(obj.ObjAge);      //19
obj.show();       //张三  undefined

----------------------------------------------------------------
var p = { name: "KangKang", age: 19 };
let obj = {
    name: "张三",
    ObjAge: this.p.age,
    show: function () {
        // console.log(this);  //指向obj
        console.log(this.name, this.age);
    },
};

// console.log(obj.ObjAge); //19
// obj.show(); //张三  undefined
obj.show.call(p); //KangKang 19
```

`例子2 call()、apply()、bind() 都是用来重定义 this 这个对象的`

``` javascript
var name = "KangKang",
    age = 19;
let obj = {
    name: "张三",
    ObjAge: this.age,
    show: function () {
        // console.log(this);  //指向obj
        console.log(this.name, this.age);
    },
}

var brr = {
    name:"huawei",
    age:666
}

obj.show.call(brr)
obj.show.apply(brr)
obj.show.bind(brr)()  //bind返回的是函数
```

`例子3 call 、bind 、 apply 传参情况下`

``` javascript
var name = "KangKang",
    age = 19;
let obj = {
    name: "张三",
    ObjAge: this.age,
    show: function (a,b) {
        // console.log(this);  //指向obj
        console.log(this.name, this.age,a,b);
    },
}

var brr = {
    name:"huawei",
    age:666
}

obj.show.call(brr,"任正非","深圳")        //huawei 666 任正非 深圳
obj.show.apply(brr,["任正非","深圳"])     //huawei 666 任正非 深圳
obj.show.bind(brr,"任正非","深圳")()      //huawei 666 任正非 深圳
// obj.show.bind(brr,["任正非","深圳"])()    //huawei 666 ['任正非', '深圳'] undefined
```

### 10.浅拷贝 {#10浅拷贝}

-   在复制时复制的是新的内存地址，而不是指向同一个内存地址

`例子1  引用的是同一个内存地址`

``` javascript
let obj = {
    name:"张三",
    age:12,
}

let res = obj

console.log(res);  //{name: '张三', age: 12}
console.log(obj);    //{name: '张三', age: 12}

res.name="李四"
console.log(res);  //{name: '李四', age: 12}
console.log(obj);     //{name: '李四', age: 12}
```

`例子2  浅拷贝--方法一--赋值`

``` javascript
let obj = {
    name:"张三",
    age:20,
}

let res = {
    name:obj.name,
    age:obj.age
}

console.log(obj);  //{name: '张三', age: 20}
console.log(res);  //{name: '张三', age: 20}

res.name="李四"
console.log(obj);  //{name: '张三', age: 20}
console.log(res);  //{name: '李四', age: 20}
```

`例子3  浅拷贝--方法二--遍历`

``` javascript
let obj = {
    name: "张三",
    age: 20,
};

let res = {};
for (let key in obj) {
    res[key] = obj[key];
}

console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '张三', age: 20}

res.name = "李四";
console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '李四', age: 20}
```

`例子4 浅拷贝--方法二--展开语法{...变量名}`

``` javascript
let obj = {
    name: "张三",
    age: 20,
};

let res = { ...obj };

console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '张三', age: 20}

res.name = "李四";
console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '李四', age: 20}
```

`例子5  浅拷贝--方法四--对象的合并-Object.assign()`

``` javascript
let obj = {
    name: "张三",
    age: 20,
};

let res = Object.assign({}, obj);

console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '张三', age: 20}

res.name = "李四";
console.log(obj); //{name: '张三', age: 20}
console.log(res); //{name: '李四', age: 20}
```

### 11.深拷贝 {#11深拷贝}

`例子1  内层的对象同样引用的是同一个内存地址(浅拷贝只对第一层内起作用)`

``` javascript
内层的对象同样引用的是同一个内存地址(浅拷贝只对第一层内起作用)
let obj = {
    name:"张三",
    hobby:{
        play:"games",
        listen:"music"
    }
}

let res = {
    name:obj.name,
    hobby:obj.hobby
}

console.log(JSON.stringify(res,null,2));
console.log(JSON.stringify(obj,null,2));

res.hobby.play = "football"
console.log(JSON.stringify(res,null,2));  //值会发生改变
console.log(JSON.stringify(obj,null,2));  //值会发生改变
```

`例子2  深拷贝--方法-递归遍历`

``` javascript
深拷贝--方法-递归遍历
let obj = {
    name: "张三",
    hobby: {
        play: "games",
        listen: "music",
    },
};
function deepCopy(data) {
    let res = {};
    for (let key in data) {
        res[key] =
            typeof data[key] == "object" ? deepCopy(data[key]) : data[key];
    }
    return res;
}

let hh = deepCopy(obj)
hh.hobby.play = "football";
console.log(JSON.stringify(hh, null, 2));    //值会发生改变
console.log(JSON.stringify(obj, null, 2));
```

`例子3   深拷贝--方法-递归遍历-最终`

``` javascript
// 深拷贝--方法-递归遍历-最终
let obj = {
    name: "张三",
    hobby: {
        play: "games",
        listen: "music",
    },
    arr: [],
};
function deepCopy(data) {
    // let res = {};
    // for (let key in data) {
    // res[key] =
    //     typeof data[key] == "object" ? deepCopy(data[key]) : data[key];
    // }
    let res = data instanceof Array ? [] : {};
    //console.log(res);
    for (let [k, v] of Object.entries(data)) {
        res[k] = typeof v == "object" ? deepCopy(v) : v;
    /    console.log(res);
    }
    return res;
}

let hh = deepCopy(obj);
hh.hobby.play = "football";
// hh.arr.push("123123")   //报错，不是一个函数
hh.arr.push(123123);
console.log(JSON.stringify(hh, null, 2)); //值会发生改变
console.log(JSON.stringify(obj, null, 2));

// 结果：
/*
    {
      "name": "张三",
      "hobby": {
        "play": "football",
        "listen": "music"
      },
      "arr": [
        123123
      ]
    }

    {
      "name": "张三",
      "hobby": {
        "play": "games",
        "listen": "music"
      },
      "arr": []
    }
*/
```

### 12.对象的特征 {#12对象的特征}

`1.Object.getOwnPropertyDescriptor(user,'name')  //得到某一个属性的状态`

`2.Object.getOwnPropertyDescriptors(user)  //得到全部属性的状态`

-   **writable:true, //是否允许赋值（默认false）**

-   **enumerable:true, //是否可以枚举**

-   **configurable:true, //是否可以被修改和删除**

``` javascript
let user = {
    name:"张三",
    age:21
}

// let res = Object.getOwnPropertyDescriptor(user,'name')  //得到某一个属性的状态
// Object.getOwnPropertyDescriptors(user) //得到全部属性的状态
let res = JSON.stringify(CCCC,null,2)  
console.log(res);

//向对象中添加一个属性
Object.defineProperty(user,"hobby",{
    value:"游戏",
    // writable:true,   //是否允许赋值（默认false）
    // enumerable:true,   //是否可以枚举
    configurable:true,    //是否可以被修改和删除
})

user.hobby= '学习'
// delete user.hobby
console.log(user);
for(let [k,v] of Object.entries(user)){
    console.log(k,v);    //enumerable:true时可以遍历到hobby
}
```

`Object.preventExtensions() 禁止添加属性`

``` javascript
let user = {
    name:"张三",
    age:21
}
user.hobby = "游戏"
console.log(user);   //{name: '张三', age: 21, hobby: '游戏'}

Object.preventExtensions(user)

user.address="河南"
console.log(user);   //{name: '张三', age: 21, hobby: '游戏'}
```

`Object.seal() 不可添加、修改、删除、重新定义特征`

`Object.isSealed() 判断对象是否被封闭`

``` javascript
//封闭属性 Object.seal() 不可添加、删除、重新定义特征
//Object.isSealed() 判断对象是否被封闭
let user = {
    name: "张三",
    age: 21,
};

console.log(JSON.stringify(Object.getOwnPropertyDescriptors(user),null,2));

Object.seal(user)
console.log(Object.isSealed(user));   //判断对象是否被封闭

console.log(JSON.stringify(Object.getOwnPropertyDescriptors(user),null,2));
```

`Object.freeze() 不可添加、修改、删除、重新定义特征 作用范围比seal广`

`Object.isFrozen() 判断对象是否被冻结`

``` javascript
//冻结属性 Object.freeze() 不可添加、修改、删除、重新定义特征 作用范围比seal广
//Object.isFrozen() 判断对象是否被冻结
let user = {
    name: "张三",
    age: 21,
};

console.log(JSON.stringify(Object.getOwnPropertyDescriptors(user),null,2));

Object.freeze(user)
console.log(Object.isFrozen(user));   //判断对象是否被冻结

console.log(JSON.stringify(Object.getOwnPropertyDescriptors(user),null,2));
```

### 13.访问器 {#13访问器}

`例子1`

``` javascript
//未使用访问器之前
let obj = {
    name:"张三",
    age:21,
    show(value){
        console.log(value)
    }
}
obj.show("哈哈")

//使用访问器
let obj = {
    name:"张三",
    age:21,
    set show(value){
        console.log(value)
    }
}
obj.show = "嘻嘻"
```

`例子2 访问器伪造属性 --（计算属性）`

``` javascript
//访问器伪造属性 --（计算属性）
let obj = {
    list:[
        {name:"xiaomi",price:2100},
        {name:"iphone",price:3100},
        {name:"华为",price:4100},
    ],
    get price(){
        return this.list.reduce((total,item)=>total+item.price,0)
    }
}

console.log(obj.price);   //9300
obj.price = 8888          //修改无效
console.log(obj.price);   //9300
```

`例子3 使用访问器批量设置属性`

``` javascript
//使用访问器批量设置属性
let obj = {
    name: "KangKang",
    age: 10,
    set show(value) {
        [this.name, this.age] = value.split(",");
    },
    get Info() {
        return `${this.name}---${this.age}`;
    },
};

obj.show = "李四,22";
console.log(obj.Info); //李四---22
```

### 14.proxy {#14proxy}

`1.数组通过代理拦截`

``` javascript
let obj = [
    {
        title:"机会是留给有准备的人",
        name:"Mysql"
    },
    {
        title:"以梦为马，不负韶华",
        name:"Web前端"
    },
    {
        title:"刚好，让你更好",
        name:"Java"
    },
]

let proxy = new Proxy(obj,{
    get(array,key){
        console.log(array[key]);
        let len = 5
        array[key].title = array[key].title.length>len?array[key].title.substr(0,len):array[key].title
        return array[key]
    }
})

console.log(proxy[0]);
```

`2.proxy实现数据的双向绑定`

``` javascript
<input type="text" v-model="content" />
<h4 v-bind="content">显示中...</h4>
<hr />
<input type="text" v-model="title" />
<input type="text" v-model="title" />
<h4 v-bind="title">显示中...</h4>

function Test() {
    let proxy = new Proxy(
        {},
        {
            get(obj, prop) {},
            set(obj, prop, value) {
                // console.log(obj, prop, value);
                document
                    .querySelectorAll(`[v-model='${prop}']`)
                    .forEach((item) => {
                    item.value = value;
                });
                document
                    .querySelectorAll(`[v-bind='${prop}']`)
                    .forEach((item) => {
                    item.innerHTML = value;
                });
            },
        }
    );

    this.info = function () {
        let els = document.querySelectorAll("[v-model]");
        els.forEach((item) => {
            item.addEventListener("keyup", function () {
                proxy[this.getAttribute("v-model")] = this.value;
            });
        });
    };
}

new Test().info();
```

### 15.构造函数 {#15构造函数}

##### 15.1 关于实例成员和静态成员 {#151-关于实例成员和静态成员}

``` javascript
function User(name,age){
	//实例成员
    this.name = name
    this.age = age
}
//静态成员
User.hobby = "游戏"

console.log(User.name);  //User  实例成员无法通过构造函数直接访问 
console.log(User.hobby);  //游戏  

let user = new User("张三",21)
console.log(user.name);    //张三  通过实例对象可以访问到实例成员
console.log(user.age);     //21
```

##### 15.2 关于每个实例中的方法是否都是共享 {#152-关于每个实例中的方法是否都是共享}

-   **实例1 如果直接在构造函数中定义的方法不共享**

``` javascript
//实例1 如果直接在构造函数中定义的方法不共享
function User(){
    this.show = function(){
        console.log("show")
    }
}

let user1 = new User()   
let user2 = new User()
user1.show()   //show
user1.show()   //show
console.log(user1.show === user2.show );   //false

//## 通过构造函数创建的实例,每次生成的实例实际上都是一个新得内存空间。同时还会导致大量的内存浪费
```

-   **实例2 在构造函数的原型中定义的方法可以实现共享**

``` javascript
function User(){}

User.prototype.show = function(){
    console.log("show");
}

let user1 = new User()   
let user2 = new User()
user1.show()   //show
user1.show()   //show
console.log(user1.show === user2.show );   //true
```

##### 15.3 new一个新对象的过程 {#153--new一个新对象的过程}

\(1\) 创建一个空对象 user`{}`\
(2) 为 user准备原型链连接 `user.__proto__ = User.prototype`\
(3) 重新绑定this，使构造函数的this指向新对象 `User.call(this)`\
(4) 为新对象属性赋值 `user.name`\
(5) 返回this `return this`，此时的新对象就拥有了构造函数的方法和属性了

### 16. 原型 {#16-原型}

-   原型的作用：实现方法共享，不会导致反复的开辟空间存储方法

### 17.原型链 {#17原型链}

-   解释：原型与原型层层相链接的过程即为原型链。

-   原型的查找方式： 当前-原型-Object-报错

-   原型的构造器：原型的构造器指向构造函数

-   ``` javascript
    function User(){}

    let user1 = new User()
    console.log(user1.__proto__.constructor === User);  //true
    console.log(User.prototype.constructor === User);  //true
    ```

-   一般不允许直接改变原型`prototype`指向

`改变原型指向，会使原生的方法都没了，所以Array、String这些内置的方法是不允许改变原型指向的。如果改变了，就会报错。`

``` javascript
//未改变
Array.prototype.getSum = function(arr){
    return arr.reduce((t,item)=>{
        return t+=item 
    },0)
}

let arr1 = [1,2,3,4,5,6,7,9,9,10]
let arr = new Array()
console.log(arr.getSum(arr1));  //56

//改变
Array.prototype = {
    getSum(arr){
        return arr.reduce((t,item)=>{
            return t+=item 
        },0)
    }
}
let arr1 = [1,2,3,4,5,6,7,9,9,10]
let arr = new Array()
console.log(arr.getSum(arr1));    //报错
```

### 18.类 {#18类}

##### 18.1类和构造函数 {#181类和构造函数}

``` javascript
//使用类
class User{
    constructor(name){
        this.name = name
    }
    show(){
        console.log("user-show()");
    }
    get(){
        console.log("get()--"+this.name);
    }
    test(arg){
        console.log("test()--"+arg);
    }
}
console.dir(User);        
let user = new User("张三")
console.log(user.name);       //张三
user.get();                  //get()--张三
console.log(User.prototype.constructor === User);   //true
user.test("better")    //test()--better
console.log(User.prototype);    //{constructor: ƒ, show: ƒ, get: ƒ}

//使用构造函数
function Admin(name){
    this.name = name
}
Admin.prototype.show = function(){
    console.log("Admin-show()");
}
Admin.prototype.get = function(){
    console.log("get()--"+this.name);
}
Admin.prototype.test = function(arg){
    console.log("test()--"+arg);
}


console.dir(Admin);
let a = new Admin("李四")            
a.show();           //Admin-show()
a.get()             //get()--李四
a.test("good")             //test()--good
console.log(Admin.prototype.constructor === Admin);   //true
console.log(Admin.prototype)    //{show: ƒ, get: ƒ, test: ƒ, constructor: ƒ}
```

##### 18.2 类中的方法不能进行遍历 {#182-类中的方法不能进行遍历}

``` javascript
//在构造函数中可以直接遍历原型上的方法
function User(name){
    this.name = name
}
User.prototype.show = function(){
    console.log("show()");
}

console.dir(User);
console.log(JSON.stringify(Object.getOwnPropertyDescriptor(User.prototype,"show"),null,2));  
/*
    {
      "writable": true,
      "enumerable": true,
      "configurable": true
    }
    */
let user = new User("张三")
for(let item in user){
    if(user.hasOwnProperty(item)){
        console.log(item);      //name
    }
}


//在类中可以不能直接遍历原型上的方法
class Son{
    constructor(name){
        this.name = name
    }
    show(){
        console.log("show()");
    }  
}

console.dir(Son);    //{constructor: ƒ, show: ƒ}
console.log(JSON.stringify(Object.getOwnPropertyDescriptor(Son.prototype,"show"),null,2))
/* {
      "writable": true,
      "enumerable": false,
      "configurable": true
    } */
let son = new Son("李四")
for(let x in son){
    console.log(x);     //name
}
```

##### 18.3 静态属性和静态方法 {#183-静态属性和静态方法}

**18.3.1 使用够构造函数定义实例成员和静态成员/属性和静态方法**

``` javascript
function User(name,age){
    this.name = name
    this.age =age
}
User.hobby = "游戏"   //静态属性
User.show = function(){
    console.log("静态方法--show()")
}
User.prototype.show = function(){  
    console.log("prototype--show()")
}

let user = new User("张三",12)
console.log(user.age);       //12
console.log(User.hobby);    //游戏
console.log(user.hobby);   //undefined
user.show();   //prototype--show()
User.show();   //静态方法--show()
```

**18.3.2 使用类定义实例成员和静态成员/属性和静态方法**

``` javascript
class User {
    constructor(name,age){
        this.name = name
        this.age = age
    }

    //静态属性
    static hobby = "抽烟"
    //静态属性
    static create(...args){
        return new User(...args)
    }

    //静态方法
    static show(){
        console.log("静态方法--show()");
    }

    show(){
        console.log("prototype--show()");
    }
}

let user = User.create("李四",22)
console.log(user);   //User {name: '李四', age: 22}
console.log(User.hobby);    //抽烟
let u1 = new User()
u1.show();    //prototype--show()
User.show()    //静态方法--show()
```

### 19.正则 {#19正则}

``` javascript
1.| 选择符
2.[]和() 原子组    --[]匹配其中任意一个,()匹配其中连续
```

### 20.继承 {#20继承}

#### 1.通过构造函数进行继承 {#1通过构造函数进行继承}

-   也就是通过call，apply等实现
    即\-\--**被继承的构造函数.call(this,参数1，参数2\....)**

-   需要注意此时该构造函数所具有的原型属性不会被继承

``` javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.hobby = "学习"
Person.prototype.speak = function(){
    console.log("speak");
}

function Student(name,age,student,teacher){
    Person.call(this,name,age)
    this.student = student
    this.teacher = teacher
}

let s = new Student("张三",21,"学生","Mr Xue")
console.log(s);   //Student {name: '张三', age: 21, student: '学生', teacher: 'Mr Xue'}

//使用构造函数不能继承原型中具有的属性和方法
console.log(s.hobby);   //undefined
s.speak()  //报错 
```

#### 2.通过原型链继承 {#2通过原型链继承}

-   **需要继承构造函数.prototype = new 被继承的构造函数的一个实例对象**

-   需要注意原型链继承，会导致下级原型中的constructor指向发生改变
    ，解决方法：**需要继承的构造函数.prototype.constructor =
    需要继承的构造函数**

``` javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.hobby = "学习";
Person.prototype.speak = function () {
    console.log("speak");
};

function Student(student, teacher) {
    this.student = student;
    this.teacher = teacher;
}

Student.prototype = new Person();
Student.prototype.constructor = Student;
let s = new Student("学生", "Mr Xue");
console.log(s);
console.log(Student.prototype);
s.speak(); //speak
```

#### 3.组合继承 {#3组合继承}

-   通过构造函数和原型链实现组合继承

``` javascript
function Person(name,age,gender){
    this.name = name;
    this.age = age;
    this.gender = gender
}

Person.prototype.hobby  = "学习"
Person.prototype.speak = function(){
    console.log("I Can Speak");
}


function Student(name,age,gender,study,teacher){
    Person.call(this,name,age,gender)   //通过构造函数实现继承
    this.study = study;
    this.teacher = teacher
}

//通过原型链实现继承
Student.prototype = new Person()
Student.prototype.constructor = Student

let s1 = new Student("张三",21,"男","web前端","Mr Li")
console.log(s1);   //Student {name: '张三', age: 21, gender: '男', study: 'web前端', teacher: 'Mr Li'}
s1.speak()      //I Can Speak
```

### 21.工厂模式 {#21工厂模式}

-   工程模式可以批量创建js对象，提高了可复用性，但是不能区分类型

``` javascript
function createStudent(name,age,gender){
    let obj = {}
    obj.name  = name
    obj.age = age
    obj.gender = gender
    obj.speak = function(){
        console.log(obj.name+ " - "+obj.age+" - "+obj.gender);
    }

    return obj
}
let s1 = createStudent("张三",31,"男")
console.log(s1);  //{name: '张三', age: 31, gender: '男', speak: ƒ}
let s2 = createStudent("李四",19,"女")
console.log(s2);  //{name: '李四', age: 19, gender: '女', speak: ƒ}
```

### 22.高阶函数 {#22高阶函数}

1.若函数A，接收的参数是一个函数，那该函数就是高阶函数

2.若函数A，调用后的返回值仍然是一个函数，那该函数就可以称之为高阶函数

### 23.函数的柯里化 {#23函数的柯里化}

通过函数调用继续返回函数的方式，实现多次接收最后统一处理的函数编码形式

# git

### 1.区域 {#1区域}

-   **工作区**

-   **暂存区**

-   **版本库**

### 2.对象 {#2对象}

-   **git对象**

-   **树对象**

-   **提交对象**

### 3.常用命令 {#3常用命令}

  命令                                                含义                           备注
  --------------------------------------------------- ------------------------------ ------
  git config \--global user.name \"nihao\"                                           
  git config \--global user.email <x709500@163.com>                                  
  git config \--list                                                                 
  git \--version                                      当前git版本                    
  clear                                               清空                           
  echo \"nihao\" \| echo \"nihao\" \> test.txt        控制台输出/创建文件夹          
  ll                                                  当前目录下的子文件平铺控制台   
  git init                                            初始化本地仓库                 

### 4.高层命令 {#4高层命令}

  命令                       含义                                     备注
  -------------------------- ---------------------------------------- ------
  git init                   初始化仓库                               
  git status                 查看文件的状态                           
  git diff                   查看哪些文件修改还未暂存                 
  git diff \--staged         查看哪些文件修改以及被暂存了，还未提交   
  git log                    查看提交的历史记录                       
  git log \--online          查看提交的历史记录（精简）               
  git add ./                 将修改添加到暂存区（未跟踪时进行跟踪）   
  git commit                 进入git编辑器                            
  git commit -a              跳过暂存区                               
  git commit -a -m 注释      跳过暂存区并提交到版本库                 
  git commit -m 注释         将暂存区并提交到版本库                   
  git reset \--hard 版本号   穿梭                                     

### 5.分支指令: {#5分支指令}

  命令                  含义                         备注
  --------------------- ---------------------------- ------
  git branch 分支名     创建分支名                   
  git branch -v         查看分支                     
  git checkout 分支名   切换分支                     
  git merge 分支名      把指定的分支合并到当前分支   

### 6.远程仓库的操作 {#6远程仓库的操作}

  命令                               含义                                                       备注
  ---------------------------------- ---------------------------------------------------------- ------
  git remote -v                      查看当前所有远程地址别名                                   
  git remote add 别名 远程地址       另起别名                                                   
  git push 别名 分支                 推送本地分支上的内容到回远程仓库                           
  git clone 远程地址                 将远程仓库的内容克隆到本地                                 
  git pull 远程地址别名 远程分支名   将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并   
  git tag -a v-1.1.1 -m \"注释\"     生成版本                                                   
  git push origin \--tags            提交版本至远程仓库                                         

**7.ssh免密登录：\$ ssh-keygen -t rsa -C <x709500@163.com>**

**8..gitignore的忽略配置**

``` javascript
.DS_Store
node_modules
/dist


# local env files
.env.local
.env.*.local

# Log files
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*

# Editor directories and files
.idea
.vscode
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?
```

9.本地上传远程仓库的命令

``` gas
echo "# Miraitowa-serve" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/codeXlj/Miraitowa-serve.git
git push -u origin main




git remote add origin https://github.com/codeXlj/Miraitowa-serve.git
git branch -M main
git push -u origin main
```

**注：推送时出现**\
fatal: unable to access \'<https://github.com/codeXlj/Miraitowa.git/>\':
Failed to connect to 127.0.0.1 port 31181 after 2059 ms: Connection
refused

**解决方法：**

git config \--global http.proxy

git config \--global \--unset http.proxy

# 常用三方库

### 小程序

#### 1.富文本html2wxml {#1富文本html2wxml}

-   **html2wxml**

-   `https://gitee.com/matols/html2wxml#https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Ficindy%2FwxParse`

### Vue {#vue-1}

#### 1.图片的懒加载 {#1图片的懒加载}

-   **vue-lazyload** `https://www.npmjs.com/package/vue-lazyload`

#### 2.进度条nprogress {#2进度条nprogress}

-   **nprogress** `https://www.npmjs.com/package/nprogress`

#### 3.函数的防抖与节流 {#3函数的防抖与节流}

-   **lodash** `https://www.lodashjs.com/docs/lodash.debounce`

-   防抖：前面的所有触发都被取消，最后一个执行在规定的时间之后才会执行，也就是说如果连续快速的触发，只会执行一次

-   节流：在规定的时间内不会重复执行回调，只有超出规定的时间后才会执行，把频繁触发变为少量触发

-   简单的来说防抖和节流：

    -   防抖：用户操作很频繁，但只会执行一次
        `_.debounce(func, [wait=0], [options=])`

    -   节流：用户操作很频繁，把频繁触发变为少量触发
        `_.throttle(func, [wait=0], [options=]`

#### 4.表单验证vee-validate {#4表单验证vee-validate}

**vee-validate 基本使用**

-   第一步：插件安装与引入\
    **cnpm i vee-validate\@2 \--save** 安装的插件安装2版本的

``` javascript
import VeeValidate from 'vee-validate'
import zh_CN from 'vee-validate/dist/locale/zh_CN'   // 引入中文 message
Vue.use(VeeValidate)
```

-   第二步：提示信息

``` javascript
VeeValidate.Validator.localize('zh_CN', {
messages: {
    ...zh_CN.messages,
    is: (field) => `${field}必须与密码相同` // 修改内置规则的 message，让确认密码和密码相同
    },
    attributes: { // 给校验的 field 属性名映射中文名称
    phone: '手机号',
    code: '验证码',
    password:'密码',
    password1:'确认密码',
    isCheck:'协议'
    }
})
```

-   第三步：基本使用

``` javascript
 <input
    placeholder="请输入你的手机号"
    v-model="phone"
    name="phone"
    v-validate="{ required: true, regex: /^1\d{10}$/ }"
    :class="{ invalid: errors.has('phone') }"
  />
  <span class="error-msg">{{ errors.first("phone") }}</span>

const success = await this.$validator.validateAll(); //全部表单验证

//自定义校验规则
//定义协议必须打勾同意
VeeValidate.Validator.extend('agree', {
validate: value => {
return value
},
getMessage: field => field + '必须同意'
})
```

#### 5.二维码插件qrcode {#5二维码插件qrcode}

展示二维码\-\-\--qrcode插件\
通过qrCode.toDataUrl方法，将字符串转换为加密的在线二维码链接，通过图片进行展示。\
moment.js\
swiper.js\
nprogress.js\
qrcode.js

#### 6. vue解决首屏加载缓慢问题 {#6-vue解决首屏加载缓慢问题}

**1.客户端**：

``` javascript
1.安装依赖：
	npm install compression-webpack-plugin @5 -S

2.在vue.config.js中配置以下内容
    const CompressionPlugin = require('compression-webpack-plugin');
    configureWebpack: {
        plugins: [
            new CompressionPlugin({
                algorithm:'gzip',
                test:/\.(js|css|woff|woff2|svg)$/,  // 要压缩的文件
                threshold:10240, // 压缩超过10k的数据
                deleteOriginalAssets:false, // 不删除压缩前的文件，如果浏览器不支持Gzip，则会加载源文件
                minRatio:0.8 // 压缩比大于0.8的文件将不会被压缩
            })
        ],
    },
```

**2.服务端**

``` javascript
1.安装依赖：
	npm install compression
    
2.在app.js中引入以下内容
    var compression = require('compression');   // 引入compresssion
    //const app = express()
    app.use(compression()); 
```

#### 7.vue3使用全局事件总线 {#7vue3使用全局事件总线}

``` javascript
import mitt from 'mitt'
const emitter = mitt()
export default emitter
```

# Vue {#vue-2}

### imporant

#### 1.vue中路由路由的传参 {#1vue中路由路由的传参}

-   字符串写法

-   模板字符串

-   对象 this.\$router.push({name：\"/search\",params:{name:\"张三\"}})

#### 2.parmas和query传参的注意点 {#2parmas和query传参的注意点}

-   params
    属于路径的一部分，传参时**必须先占位**，**跳转时只能使用name**

-   query 不属于路径分一部分，类似于get传参 ？name=12&age=12

-   在使用params参数时，配置中进行了**占位而不传递参数**会导致路径错误
    。解决：在配置中**占位后加？**

-   在使用params参数时，如果**传入的为空**也会导致路径错误。
    解决：this.\$router.push({name：\"/search\",params:{name:\"\" **\|\|
    undefined**}})

#### 3.路由组件可以传递props：三种写法 {#3路由组件可以传递props三种写法}

-   布尔值写法：props ：true

-   对象写法 ：props ：{}

-   函数写法：props ：function( \$route ){ return { name :
    this.\$route.name} }

#### 4.常用 {#4常用}

**1:属性修饰符.sync，可以实现父子数据同步。**\
以后在elementUI组件中出现，实现父子数据同步。

**2$attrs与$listeners \-\-\--vue-helper 父子组件通信**\
$attrs：组件实例的属性，可以获取到父亲传递的props数据（前提子组件没有通过props接受）
$listeners：组件实例的属性，可以获取到父亲传递自定义事件（对象形式呈现）

**3:$children与$parent 可以实现父子组件通信**\
ref:可以在父组件内部获取子组件\-\--实现父子通信\
$children:可以在父组件内部获取全部的子组件【返回数组】
$parent:可以在子组件内部获取唯一的父组件【返回组件实例】

### 01.基础用法 {#01基础用法}

### **01.Vue的模板语法** {#01vue的模板语法}

-   插值语法:

    -   功能：用于解析标签体内容

    -   写法：{{xxx}}，xxx是js表达式, 可以直接读取到到data中的所有属性

-   指令语法:

    -   功能：用于解析标签（标签属性，标签体内容，绑定事件）

    -   写法：v-bind:href = \"xxx\" 或简写为 :href = \"xxx\",
        xxx也是表达式

------------------------------------------------------------------------

### 02.Vue数据的绑定 {#02vue数据的绑定}

1.**单向数据绑定** ：

语法：v-bind:href =\"xxx\" 或简写为 :href

特点：数据只能从 data 流向页面

2.**双向数据绑定** ：

语法：v-mode:value=\"xxx\" 或简写为 v-model=\"xxx\"

特点：数据不仅能从 data 流向页面，还能从页面流向 data

3.**MVVM 模型**：

M：模型(Model) ：对应 data 中的数据

V：视图(View) ：模板

VM：视图模型(ViewModel) ： Vue 实例对象

------------------------------------------------------------------------

### **02.Vue基本事件的绑定** {#02vue基本事件的绑定}

1.  使用 v-on:xxx 或 \@xxx 绑定事件，其中xxx是事件名

2.  事件的回调需要配合在methods对象中,最终会在vm上

3.  在methods中配置函数,不要使用箭头函数!（这里的箭头函数中this是指向windows）

4.  \@click = "demo" 和 \@click = \"demo(\$event)\"
    效果一致,但后者可以传参

------------------------------------------------------------------------

### **03.Vue事件修饰符** {#03vue事件修饰符}

1.  prevent：阻止默认行为/事件

2.  stop：阻止事件冒泡

3.  once：事件只触发一次

4.  capture：使用事件的捕获模式

5.  self：只有event.target是当前操作的元素时才触发事件

6.  passive：事件的默认行为立即执行,无需等待事件回调执行完毕

------------------------------------------------------------------------

### 04.Vue键盘事件 {#04vue键盘事件}

1.  **常用的按键别名:**

    -   回车 => enter

    -   删除 => delete (捕获 删除 和退格 键)

    -   退出 => esc

    -   空格 => space

    -   换行 => tab (必须配合keydown使用)

    -   上 => up

    -   右 => right

    -   下 => bdown

    -   左 => left

2.  **vue未提供别名的按键:**

    可以使用按键原始的key值绑定,但要转换为caps-lock来使用

    e.keyCode 查看对应的 ascii值

    e.key 获取到按键对应的 原始的key值

3.  **系统修饰键**

    ctrl shift alt mate

    -   配合keyup使用 : 先按下修饰键的同时，再按下其他键,
        随后释放其他键，事件才被触发;

    -   配合keydown使用: 正常触发即可

4.  **自定义: Vue.config.keyCodes.自定义键名 = 键码**

------------------------------------------------------------------------

### 05.computed和watch的区别 {#05computed和watch的区别}

-   computed能实现的功能，watch都可以完成

-   watch能完成的功能，computed不一定可以,watch可以进行异步操作

------------------------------------------------------------------------

### 06.条件渲染 {#06条件渲染}

1.  **v-if**

    -   写法:

        (1). v-if = \"表达式\"

        (2).x-else-if = \"表达式\"

        (3).x-else = \"表达式\"

    -   使用点: 切换频率较低的场景

    -   特点: 不展示DOM元素直接被移除

    -   注意: (1)(2)(3)可以一起使用,但结构不能被打乱

2.  **v-show**

    -   写法: v-show = \"表达式\"

    -   使用场景: 切换频率较高的场景

    -   特点: 不展示DOM元素，未被移除只是将样式隐藏掉

------------------------------------------------------------------------

### 07.**两个重要的小原则** {#07两个重要的小原则}

**两个重要的小原则**

-   所被Vue管理的函数,最好写成普通函数，这样this的指向才是vm 或
    组件实例对象

-   所有不被Vue所管理的函数（定时器的回调函数、ajax的回调函数、Promise的回调函数），最好写成箭头函数。这样this的指向才是vm
    或 组件的实例对象

------------------------------------------------------------------------

### 08.class，style样式的绑定 {#08classstyle样式的绑定}

1.class样式:

``` javascript
:class = "xxx"  xxx可以是字符串、对象、数组
```

-   字符串写法适用于：类名不确定，要动态获取的；

-   对象写法适用于：要绑定多个样式，个数不确定，名字也不确定

-   数组写法适用于：要绑定多个样式，个数确定，名字也确定，但不确定用不用；

2.style样式

``` javascript
:style = "{fonySize:xxx}"   其中xxx是动态值
:style = "[a,b]" 	其中a、b是样式对象
```

------------------------------------------------------------------------

### 09.收集表单数据 {#09收集表单数据}

1.`<input  type = "text" />`{=html}，则v-model收集的是value的值，用户输入的就是value值；

2.`<input  type = "radio" />`{=html}，则v-model收集的是value的值，且要给value配置；

3.`<input  type = "checkbox" />`{=html}:

①如果没有配置input的value属性；那m收集的就是checked(勾选 or
未勾选)，是布尔值；

②配置input的value属性：

==> v-model的初始值为非数组，那么收集到的就是checked(勾选 or
未勾选)，是布尔值；

==> v-model的初始值为数字，那么收集到的就是value组成的数组；

**备注：v-model的三个修饰符：**

lazy：失去焦点在收取数据；

number：输入字符串转换为有效的数字；

trim：输入收尾空格过滤

示例:

------------------------------------------------------------------------

### 10.Vue内置指令 {#10vue内置指令}

1.  #### **v-once指令:**

    -   v-once所在节点在初次渲染后就是为动态内容了；

    -   以后的数据改变不会引起v-once所在结构的更新；

2.  #### **v-pre指令:**

    -   跳过其所在节点的编译过程；

    -   可利用它跳过：没有使用指令语法的节点，会加快编译；

3.  #### **v-cloak指令:**

    -   本质上是一个特殊的属性，Vue示例创建完毕后并接管容器后，会删掉v-cloak属性；

    -   使用css配合v-cloak可以解决网速慢是页面展示出{{xxx}}的问题；

4.  #### **v-html指令：**

    1.  作用：向指定节点中渲染包含html结构的内容。

    2.  与插值语法的区别:

        -   v-html会替换掉节点中所有的内容，{{xxx}}则不会；

        -   v-html可以识别html结构；

    3.  严重注意:(v-html有安全性问题)

        -   在网站上动态渲染任意HTML是非常危险的，容易导致XSS攻击；

        -   一定要在可信的内容上使用v-html，不要用在用户提交的内容上；

------------------------------------------------------------------------

### 10.常用的生命周期钩子 {#10常用的生命周期钩子}

1.mounted：发送ajax请求、启动定时器、绑定自定义事件、订阅信息等（初始化操作）

2.beforeDestroy：消除定时器、绑定自定义事件、取消订阅消息（收尾工作）

关于销毁Vue示例:

-   销毁后借助Vue开发工具看不到任何信息；

-   销毁后自定义事件会失效，单但原生DOM事件依然有效；

-   一般不会在beforeDestroy操作数据，因为即便是操作数据，也不会再出发更新流程了；

------------------------------------------------------------------------

### 11.Vue组件 {#11vue组件}

1.  #### 组件的使用步骤:

    -   定义组件（创建组件）;

    -   注册组件；

    -   使用组件（写组件标签）；

2.  #### **定义组件（创建组件）：** {#定义组件创建组件）}

    ``` javascript
    Vue.extend(options)创建，其中options和new Vue(options)时传入的那个options几乎一样，但也有区别;
    区别如下:
    1.el不要写，最终的组件都要经过一个vm管理，由vm中el决定是哪个容器;
    2.data要写成函数;  避免被复用时，数据存在引用关系;
    备注: 使用template可以配置组件结构。
    ```

3.  #### **注册组件：**

    ``` javascript
    1.局部注册:靠new Vue的时候传入components选项
    2.全局注册:靠Vue.components("组件名"，"组件")
    ```

4.  #### **使用组件：**

    ``` javascript
    <组件名></组件名>
    ```

5.  ``` javascript
    //第一步创建组件:
           const school = Vue.extend({
               template:`
                   <div>
                       <h1>学校名称：{{schoolName}}</h1>
                       <h1>学校地址：{{address}}</h1>
                   </div>
               `,
               data(){
                   return {
                       schoolName:"轻工",
                       address:"天津"
                   }
               }
           })
    //注册组件
           new Vue({
               el:"#root",
               components:{
                   school:school,
                   student:student
               }
           })
           
    //使用组件
    		<school></school>
    ```

6.  #### 组件的命名：

    1.一个单词组成:

    -   首字母小写：school

    -   首字母大写：School

    2.多个单词组成:

    -   (key-case命名)：my-school

    -   (CameCase命名): MySchool (需要Vue脚手架支持)

    3.备注:

    -   组件的命名要避开HTML中已有的元素名称；（H2，h2都不可以）

    -   可以使用name配置项指定组件在开发者工具中呈现的名字

    4.关于组件标签：

    -   写法1：`<school>`{=html}`<school/>`{=html}

    -   写法2：`<schlool/>`{=html}

    -   不使用脚手架时`<school/>`{=html}会导致后续的组件不能渲染

    5.一个简写的方式:

    const school = Vue.extend(options) 可简写为：const school = options

------------------------------------------------------------------------

### 12.Vue初始化脚手架 {#12vue初始化脚手架}

**set-ExecutionPolicy RemoteSigned**

vue/cli \-\-\-\-\-\-\-\-\-\--cli ===> command line interface 命令行接口

``` vue
切换淘宝镜像    npm config set registry https://registry.npm.taobao.org
```

1.  ##### 第一步(**仅第一次执行**)：全局安装\@vue/cli

    ``` vue
    npm install -g @vue/cli
    ```

2.  ##### 第二步：（**切换到你要创建项目的目录**），然后使用命令创建项目 {#第二步切换到你要创建项目的目录）然后使用命令创建项目}

    ``` vue
    vue create 项目名称
    ```

3.  ##### 第三步：启动项目

    ``` 
    npm run serve
    ```

4.  安装脚手架失败解决方法1：

``` 
	C:\Users\ad....\AppData\Roaming\npm-cache   删除npm-cache
```

------------------------------------------------------------------------

### 13.脚手架中常用的属性 {#13脚手架中常用的属性}

1.  ##### ref属性: {#ref属性-1}

    -   被用来给元素或子组件注册引用信息 (id的替代者)

    -   应用在html标签上获取的是真实DOM元素，应用组件标签上是组件实例对象（vc）

    -   使用方式:

        -   打标识：`<h1 ref = "xxx">`{=html}\...`</h1>`{=html} 或
            `<School ref = "xxx">`{=html}`</School>`{=html}

        -   获取：this.\$refs.xxx

------------------------------------------------------------------------

### 14.配置项props {#14配置项props}

功能：让组件接收外部传过来的数据;

(1).传递数据:

`<School  name = "xxx"/>`{=html}

(2).接收数据:

1.第一种方式(只接受)：

props:\[\"name\"\];

2.第二种方式(限制类型):

props:{

name:{

type : String, //类型

required : true, //必要性

default : \"l老王\" //默认值

}

}

(3).备注:

props是只读的,如果进行了修改,就会发出警告；如果需要修改可复制一份到data中,然后修改data中的数据

------------------------------------------------------------------------

### 15.mixin混入(混合) {#15mixin混入混合}

功能可以：把多个组件共用的配置提取成一个混入对象；

使用方法:

1.定义混合,例如:

{

data(){},

methods(){}

}

2.使用混合,例如:\
(1).全局混入：Vue.mixin(xxx)

(2).局部混入：mixins:\[\"xxx\"\]

------------------------------------------------------------------------

### 16.scoped样式 {#16scoped样式}

1.作用：让样式在局部生效,防止冲突;

2.使用：`<style  scoped>`{=html}`</style>`{=html}\>

------------------------------------------------------------------------

### 17.全局事件总线（GlobalEventBus） {#17全局事件总线globaleventbus）}

1.使用全局安装:

``` javascript
main.js中
//安装全局事件总线
new Vue({
  el:"#app",
  render: h => h(App),
  beforeCreate(){
      Vue.prototype.$bus = this;
  }
})
```

2.实现：student向school组件传递数据

``` javascript
1.student.vue:
methods:{
    sendName(){
        this.$bus.$emit("nihao",数据)
    }
}

2.school.vue:
mounts(){
    this.$bus.$on("nihao",(data)=>{
         console.log("我是school组件，收到学生传来的数据：",data);
    })
}
```

3.最好在beforeDestroy钩子中，用\$off去解绑`<span style="color:red">`{=html}当前组件所用到的`</span>`{=html}事件

``` javascript
school.vue:

beforeDestroy(){
        this.$bus.$off("hello")
}
```

------------------------------------------------------------------------

### 18.消息订阅与发布（pubsub） {#18消息订阅与发布pubsub）}

1.  一种组件间通信的方式，适用于`<span style="color:red">`{=html}任意组件间通信`</span>`{=html}。

2.  使用步骤：

    1.  安装pubsub：`npm i pubsub-js`

    2.  引入: `import pubsub from 'pubsub-js'`

    3.  接收数据

        ``` javascript
        mounted() {
          this.pid = pubsub.subscribe('xxx',this.demo) //订阅消息
        }
        ```

    4.  提供数据：`pubsub.publish('xxx',数据)`

    5.  最好在beforeDestroy钩子中，用`PubSub.unsubscribe(pid)`去`<span style="color:red">`{=html}取消订阅。`</span>`{=html}

------------------------------------------------------------------------

### 19.nextTick {#19nexttick}

1.  语法：`this.$nextTick(回调函数)`

2.  作用：在下一次 DOM 更新结束后执行其指定的回调。

3.  什么时候用：当改变数据后，要基于更新后的新DOM进行某些操作时，要在nextTick所指定的回调函数中执行。

------------------------------------------------------------------------

### 20.vue-resource插件 {#20vue-resource插件}

1.安装: npm install vue-resource

2.mian.js中引入，并使用

``` 
main.js
----->  import vueResource from vue-resource
----->  Vue.use(vueResource)
----->   this.$http.get == this.$bus.$emit  ==  pubsub.publish
```

------------------------------------------------------------------------

### 21.插槽 {#21插槽}

1.  作用：让父组件可以向子组件指定位置插入html结构，也是一种组件间通信的方式，适用于
    `<strong style="color:red">`{=html}父组件 ===>
    子组件`</strong>`{=html} 。

2.  分类：默认插槽、具名插槽、作用域插槽

3.  使用方式：

    1.  默认插槽：

        ``` vue
        父组件中：
                <Category>
                   <div>html结构1</div>
                </Category>
        子组件中：
                <template>
                    <div>
                       <!-- 定义插槽 -->
                       <slot>插槽默认内容...</slot>
                    </div>
                </template>
        ```

    2.  具名插槽：

        ``` vue
        父组件中：
                <Category>
                    <template slot="center">
                      <div>html结构1</div>
                    </template>

                    <template v-slot:footer>
                       <div>html结构2</div>
                    </template>
                </Category>
        子组件中：
                <template>
                    <div>
                       <!-- 定义插槽 -->
                       <slot name="center">插槽默认内容...</slot>
                       <slot name="footer">插槽默认内容...</slot>
                    </div>
                </template>
        ```

    3.  作用域插槽：

        1.  理解：`<span style="color:red">`{=html}数据在组件的自身，但根据数据生成的结构需要组件的使用者来决定。`</span>`{=html}（games数据在Category组件中，但使用数据所遍历出来的结构由App组件决定）

        2.  具体编码：

            ``` vue
            父组件中：
            		<Category>
            			<template scope="scopeData">
            				<!-- 生成的是ul列表 -->
            				<ul>
            					<li v-for="g in scopeData.games" :key="g">{{g}}</li>
            				</ul>
            			</template>
            		</Category>

            		<Category>
            			<template slot-scope="scopeData">
            				<!-- 生成的是h4标题 -->
            				<h4 v-for="g in scopeData.games" :key="g">{{g}}</h4>
            			</template>
            		</Category>
            子组件中：
                    <template>
                        <div>
                            <slot :games="games"></slot>
                        </div>
                    </template>
            		
                    <script>
                        export default {
                            name:'Category',
                            props:['title'],
                            //数据在子组件自身
                            data() {
                                return {
                                    games:['红色警戒','穿越火线','劲舞团','超级玛丽']
                                }
                            },
                        }
                    </script>
            ```

### 22.技巧 {#22技巧}

1.在脚手架中eslintrc会和格式化代码产生语法冲突；例如（只能用单引号，不能用分号，函数中括号前要有空格）解决办法:

-   在项目根目录中创建 .esclintrc.js .prettierrc 文件；

    -   ``` javascript
        配置以下属性:
        {
        	"semi":false,    // 表示去掉分号
        	"singleQuote":true     // 表示使用引号
        }
        ```

    -   页面跳转过渡动画

        ``` javascript
         <transition name="fade" >
              <router-view></router-view>
         </transition>



        .fade-enter-active, .fade-leave-avtive {
            transition: opacity .7s;
        }
        .fade-enter, .fade-leave-to {
            opacity: 0
        }
        ```

    -   实现页面刷新

        ``` 
        mounted() {
            this.$router.afterEach(()=>{
            window.scrollTo(0,0)
        })
        },
        ```

        vue cli3使用bootstrap

        ``` javascript
        1.安装
        npm install jquery --save
        npm install bootstrap@3 --save   //高版本会出错

        2.在main.js中引入
        import "bootstrap";

        3.可创建vue.config.js并添加以下配置

        const webpack = require("webpack");
        module.exports = {
          lintOnSave : false,    //关闭语法检查
          configureWebpack: {
            plugins: [
              new webpack.ProvidePlugin({
                  jQuery: 'jquery',
                  $: 'jquery'
              })
          ]
          }
        }
        ```

# Vue2

## 脚手架文件结构

``` 
├── node_modules 
├── public
│   ├── favicon.ico: 页签图标
│   └── index.html: 主页面
├── src
│   ├── assets: 存放静态资源
│   │   └── logo.png
│   │── component: 存放组件
│   │   └── HelloWorld.vue
│   │── App.vue: 汇总所有组件
│   │── main.js: 入口文件
├── .gitignore: git版本管制忽略的配置
├── babel.config.js: babel的配置文件
├── package.json: 应用包配置文件 
├── README.md: 应用描述文件
├── package-lock.json：包版本控制文件
```

## 关于不同版本的Vue

1.  vue.js与vue.runtime.xxx.js的区别：

    1.  vue.js是完整版的Vue，包含：核心功能 + 模板解析器。

    2.  vue.runtime.xxx.js是运行版的Vue，只包含：核心功能；没有模板解析器。

2.  因为vue.runtime.xxx.js没有模板解析器，所以不能使用template这个配置项，需要使用render函数接收到的createElement函数去指定具体内容。

## vue.config.js配置文件 {#vueconfigjs配置文件}

1.  使用vue inspect \> output.js可以查看到Vue脚手架的默认配置。

2.  使用vue.config.js可以对脚手架进行个性化定制，详情见：<https://cli.vuejs.org/zh>

## ref属性 {#ref属性-2}

1.  被用来给元素或子组件注册引用信息（id的替代者）

2.  应用在html标签上获取的是真实DOM元素，应用在组件标签上是组件实例对象（vc）

3.  使用方式：

    1.  打标识：`<h1 ref="xxx">.....</h1>` 或
        `<School ref="xxx"></School>`

    2.  获取：`this.$refs.xxx`

## props配置项

1.  功能：让组件接收外部传过来的数据

2.  传递数据：`<Demo name="xxx"/>`

3.  接收数据：

    1.  第一种方式（只接收）：`props:['name']`

    2.  第二种方式（限制类型）：`props:{name:String}`

    3.  第三种方式（限制类型、限制必要性、指定默认值）：

        ``` javascript
        props:{
        	name:{
        	type:String, //类型
        	required:true, //必要性
        	default:'老王' //默认值
        	}
        }
        ```

    > 备注：props是只读的，Vue底层会监测你对props的修改，如果进行了修改，就会发出警告，若业务需求确实需要修改，那么请复制props的内容到data中一份，然后去修改data中的数据。

## mixin(混入)

1.  功能：可以把多个组件共用的配置提取成一个混入对象

2.  使用方式：

    第一步定义混合：

    ``` 
    {
        data(){....},
        methods:{....}
        ....
    }
    ```

    第二步使用混入：

    全局混入：`Vue.mixin(xxx)`\
    局部混入：`mixins:['xxx']`

## 插件

1.  功能：用于增强Vue

2.  本质：包含install方法的一个对象，install的第一个参数是Vue，第二个以后的参数是插件使用者传递的数据。

3.  定义插件：

    ``` javascript
    对象.install = function (Vue, options) {
        // 1. 添加全局过滤器
        Vue.filter(....)

        // 2. 添加全局指令
        Vue.directive(....)

        // 3. 配置全局混入(合)
        Vue.mixin(....)

        // 4. 添加实例方法
        Vue.prototype.$myMethod = function () {...}
        Vue.prototype.$myProperty = xxxx
    }
    ```

4.  使用插件：`Vue.use()`

## scoped样式 {#scoped样式}

1.  作用：让样式在局部生效，防止冲突。

2.  写法：`<style scoped>`

## 总结TodoList案例

1.  组件化编码流程：

    (1).拆分静态组件：组件要按照功能点拆分，命名不要与html元素冲突。

    (2).实现动态组件：考虑好数据的存放位置，数据是一个组件在用，还是一些组件在用：

    1).一个组件在用：放在组件自身即可。

    2).
    一些组件在用：放在他们共同的父组件上（`<span style="color:red">`{=html}状态提升`</span>`{=html}）。

    (3).实现交互：从绑定事件开始。

2.  props适用于：

    (1).父组件 ==> 子组件 通信

    (2).子组件 ==> 父组件 通信（要求父先给子一个函数）

3.  使用v-model时要切记：v-model绑定的值不能是props传过来的值，因为props是不可以修改的！

4.  props传过来的若是对象类型的值，修改对象中的属性时Vue不会报错，但不推荐这样做。

## webStorage

1.  存储内容大小一般支持5MB左右（不同浏览器可能还不一样）

2.  浏览器端通过 Window.sessionStorage 和 Window.localStorage
    属性来实现本地存储机制。

3.  相关API：

    1.  `xxxxxStorage.setItem('key', 'value');`\
        该方法接受一个键和值作为参数，会把键值对添加到存储中，如果键名存在，则更新其对应的值。

    2.  `xxxxxStorage.getItem('person');`

        该方法接受一个键名作为参数，返回键名对应的值。

    3.  `xxxxxStorage.removeItem('key');`

        该方法接受一个键名作为参数，并把该键名从存储中删除。

    4.  `xxxxxStorage.clear()`

        该方法会清空存储中的所有数据。

4.  备注：

    1.  SessionStorage存储的内容会随着浏览器窗口关闭而消失。

    2.  LocalStorage存储的内容，需要手动清除才会消失。

    3.  `xxxxxStorage.getItem(xxx)`如果xxx对应的value获取不到，那么getItem的返回值是null。

    4.  `JSON.parse(null)`的结果依然是null。

## 组件的自定义事件

1.  一种组件间通信的方式，适用于：`<strong style="color:red">`{=html}子组件
    ===> 父组件`</strong>`{=html}

2.  使用场景：A是父组件，B是子组件，B想给A传数据，那么就要在A中给B绑定自定义事件（`<span style="color:red">`{=html}事件的回调在A中`</span>`{=html}）。

3.  绑定自定义事件：

    1.  第一种方式，在父组件中：`<Demo @atguigu="test"/>` 或
        `<Demo v-on:atguigu="test"/>`

    2.  第二种方式，在父组件中：

        ``` javascript
        <Demo ref="demo"/>
        ......
        mounted(){
           this.$refs.xxx.$on('atguigu',this.test)
        }
        ```

    3.  若想让自定义事件只能触发一次，可以使用`once`修饰符，或`$once`方法。

4.  触发自定义事件：`this.$emit('atguigu',数据)`

5.  解绑自定义事件`this.$off('atguigu')`

6.  组件上也可以绑定原生DOM事件，需要使用`native`修饰符。

7.  注意：通过`this.$refs.xxx.$on('atguigu',回调)`绑定自定义事件时，回调`<span style="color:red">`{=html}要么配置在methods中`</span>`{=html}，`<span style="color:red">`{=html}要么用箭头函数`</span>`{=html}，否则this指向会出问题！

## 全局事件总线（GlobalEventBus） {#全局事件总线globaleventbus）}

1.  一种组件间通信的方式，适用于`<span style="color:red">`{=html}任意组件间通信`</span>`{=html}。

2.  安装全局事件总线：

    ``` javascript
    new Vue({
    	......
    	beforeCreate() {
    		Vue.prototype.$bus = this //安装全局事件总线，$bus就是当前应用的vm
    	},
        ......
    }) 
    ```

3.  使用事件总线：

    1.  接收数据：A组件想接收数据，则在A组件中给\$bus绑定自定义事件，事件的`<span style="color:red">`{=html}回调留在A组件自身。`</span>`{=html}

        ``` javascript
        methods(){
          demo(data){......}
        }
        ......
        mounted() {
          this.$bus.$on('xxxx',this.demo)
        }
        ```

    2.  提供数据：`this.$bus.$emit('xxxx',数据)`

4.  最好在beforeDestroy钩子中，用\$off去解绑`<span style="color:red">`{=html}当前组件所用到的`</span>`{=html}事件。

## 消息订阅与发布（pubsub） {#消息订阅与发布pubsub）}

1.  一种组件间通信的方式，适用于`<span style="color:red">`{=html}任意组件间通信`</span>`{=html}。

2.  使用步骤：

    1.  安装pubsub：`npm i pubsub-js`

    2.  引入: `import pubsub from 'pubsub-js'`

    3.  接收数据：A组件想接收数据，则在A组件中订阅消息，订阅的`<span style="color:red">`{=html}回调留在A组件自身。`</span>`{=html}

        ``` javascript
        methods(){
          demo(data){......}
        }
        ......
        mounted() {
          this.pid = pubsub.subscribe('xxx',this.demo) //订阅消息
        }
        ```

    4.  提供数据：`pubsub.publish('xxx',数据)`

    5.  最好在beforeDestroy钩子中，用`PubSub.unsubscribe(pid)`去`<span style="color:red">`{=html}取消订阅。`</span>`{=html}

## nextTick {#nexttick}

1.  语法：`this.$nextTick(回调函数)`

2.  作用：在下一次 DOM 更新结束后执行其指定的回调。

3.  什么时候用：当改变数据后，要基于更新后的新DOM进行某些操作时，要在nextTick所指定的回调函数中执行。

## Vue封装的过度与动画

1.  作用：在插入、更新或移除 DOM元素时，在合适的时候给元素添加样式类名。

2.  图示：`<img src="https://img04.sogoucdn.com/app/a/100520146/5990c1dff7dc7a8fb3b34b4462bd0105" style="width:60%" />`{=html}

3.  写法：

    1.  准备好样式：

        -   元素进入的样式：

            1.  v-enter：进入的起点

            2.  v-enter-active：进入过程中

            3.  v-enter-to：进入的终点

        -   元素离开的样式：

            1.  v-leave：离开的起点

            2.  v-leave-active：离开过程中

            3.  v-leave-to：离开的终点

    2.  使用`<transition>`包裹要过度的元素，并配置name属性：

        ``` vue
        <transition name="hello">
        	<h1 v-show="isShow">你好啊！</h1>
        </transition>
        ```

    3.  备注：若有多个元素需要过度，则需要使用：`<transition-group>`，且每个元素都要指定`key`值。

## vue脚手架配置代理

### 方法一 {#方法一-1}

在vue.config.js中添加如下配置：

``` javascript
devServer:{
  proxy:"http://localhost:5000"
}
```

说明：

1.  优点：配置简单，请求资源时直接发给前端（8080）即可。

2.  缺点：不能配置多个代理，不能灵活的控制请求是否走代理。

3.  工作方式：若按照上述配置代理，当请求了前端不存在的资源时，那么该请求会转发给服务器
    （优先匹配前端资源）

### 方法二 {#方法二-1}

编写vue.config.js配置具体代理规则：

``` javascript
module.exports = {
	devServer: {
      proxy: {
      '/api1': {// 匹配所有以 '/api1'开头的请求路径
        target: 'http://localhost:5000',// 代理目标的基础路径
        changeOrigin: true,
        pathRewrite: {'^/api1': ''}
      },
      '/api2': {// 匹配所有以 '/api2'开头的请求路径
        target: 'http://localhost:5001',// 代理目标的基础路径
        changeOrigin: true,
        pathRewrite: {'^/api2': ''}
      }
    }
  }
}
/*
   changeOrigin设置为true时，服务器收到的请求头中的host为：localhost:5000
   changeOrigin设置为false时，服务器收到的请求头中的host为：localhost:8080
   changeOrigin默认值为true
*/
```

说明：

1.  优点：可以配置多个代理，且可以灵活的控制请求是否走代理。

2.  缺点：配置略微繁琐，请求资源时必须加前缀。

## 插槽 {#插槽}

1.  作用：让父组件可以向子组件指定位置插入html结构，也是一种组件间通信的方式，适用于
    `<strong style="color:red">`{=html}父组件 ===>
    子组件`</strong>`{=html} 。

2.  分类：默认插槽、具名插槽、作用域插槽

3.  使用方式：

    1.  默认插槽：

        ``` vue
        父组件中：
                <Category>
                   <div>html结构1</div>
                </Category>
        子组件中：
                <template>
                    <div>
                       <!-- 定义插槽 -->
                       <slot>插槽默认内容...</slot>
                    </div>
                </template>
        ```

    2.  具名插槽：

        ``` vue
        父组件中：
                <Category>
                    <template slot="center">
                      <div>html结构1</div>
                    </template>

                    <template v-slot:footer>
                       <div>html结构2</div>
                    </template>
                </Category>
        子组件中：
                <template>
                    <div>
                       <!-- 定义插槽 -->
                       <slot name="center">插槽默认内容...</slot>
                       <slot name="footer">插槽默认内容...</slot>
                    </div>
                </template>
        ```

    3.  作用域插槽：

        1.  理解：`<span style="color:red">`{=html}数据在组件的自身，但根据数据生成的结构需要组件的使用者来决定。`</span>`{=html}（games数据在Category组件中，但使用数据所遍历出来的结构由App组件决定）

        2.  具体编码：

            ``` vue
            父组件中：
            		<Category>
            			<template scope="scopeData">
            				<!-- 生成的是ul列表 -->
            				<ul>
            					<li v-for="g in scopeData.games" :key="g">{{g}}</li>
            				</ul>
            			</template>
            		</Category>

            		<Category>
            			<template slot-scope="scopeData">
            				<!-- 生成的是h4标题 -->
            				<h4 v-for="g in scopeData.games" :key="g">{{g}}</h4>
            			</template>
            		</Category>
            子组件中：
                    <template>
                        <div>
                            <slot :games="games"></slot>
                        </div>
                    </template>
            		
                    <script>
                        export default {
                            name:'Category',
                            //数据在子组件自身
                            data() {
                                return {
                                    games:['红色警戒','穿越火线','劲舞团','超级玛丽']
                                }
                            },
                        }
                    </script>
            ```

    ``` 
    ```

## Vuex

### 1.概念 {#1概念}

在Vue中实现集中式状态（数据）管理的一个Vue插件，对vue应用中多个组件的共享状态进行集中式的管理（读/写），也是一种组件间通信的方式，且适用于任意组件间通信。

### 2.何时使用？ {#2何时使用}

多个组件需要共享数据时

### 3.搭建vuex环境 {#3搭建vuex环境}

1.  创建文件：`src/store/index.js`

    ``` javascript
    //引入Vue核心库
    import Vue from 'vue'
    //引入Vuex
    import Vuex from 'vuex'
    //应用Vuex插件
    Vue.use(Vuex)

    //准备actions对象——响应组件中用户的动作
    const actions = {}
    //准备mutations对象——修改state中的数据
    const mutations = {}
    //准备state对象——保存具体的数据
    const state = {}

    //创建并暴露store
    export default new Vuex.Store({
    	actions,
    	mutations,
    	state
    })
    ```

2.  在`main.js`中创建vm时传入`store`配置项

    ``` javascript
    ......
    //引入store
    import store from './store'
    ......

    //创建vm
    new Vue({
    	el:'#app',
    	render: h => h(App),
    	store
    })
    ```

### 4.基本使用 {#4基本使用}

1.  初始化数据、配置`actions`、配置`mutations`，操作文件`store.js`

    ``` javascript
    //引入Vue核心库
    import Vue from 'vue'
    //引入Vuex
    import Vuex from 'vuex'
    //引用Vuex
    Vue.use(Vuex)

    const actions = {
        //响应组件中加的动作
    	jia(context,value){
    		// console.log('actions中的jia被调用了',miniStore,value)
    		context.commit('JIA',value)
    	},
    }

    const mutations = {
        //执行加
    	JIA(state,value){
    		// console.log('mutations中的JIA被调用了',state,value)
    		state.sum += value
    	}
    }

    //初始化数据
    const state = {
       sum:0
    }

    //创建并暴露store
    export default new Vuex.Store({
    	actions,
    	mutations,
    	state,
    })
    ```

2.  组件中读取vuex中的数据：`$store.state.sum`

3.  组件中修改vuex中的数据：`$store.dispatch('action中的方法名',数据)`
    或 `$store.commit('mutations中的方法名',数据)`

    > 备注：若没有网络请求或其他业务逻辑，组件中也可以越过actions，即不写`dispatch`，直接编写`commit`

### 5.getters的使用 {#5getters的使用}

1.  概念：当state中的数据需要经过加工后再使用时，可以使用getters加工。

2.  在`store.js`中追加`getters`配置

    ``` javascript
    ......

    const getters = {
    	bigSum(state){
    		return state.sum * 10
    	}
    }

    //创建并暴露store
    export default new Vuex.Store({
    	......
    	getters
    })
    ```

3.  组件中读取数据：`$store.getters.bigSum`

### 6.四个map方法的使用 {#6四个map方法的使用}

1.  `<strong>`{=html}mapState方法：`</strong>`{=html}用于帮助我们映射`state`中的数据为计算属性

    ``` javascript
    computed: {
        //借助mapState生成计算属性：sum、school、subject（对象写法）
         ...mapState({sum:'sum',school:'school',subject:'subject'}),
             
        //借助mapState生成计算属性：sum、school、subject（数组写法）
        ...mapState(['sum','school','subject']),
    },
    ```

2.  `<strong>`{=html}mapGetters方法：`</strong>`{=html}用于帮助我们映射`getters`中的数据为计算属性

    ``` javascript
    computed: {
        //借助mapGetters生成计算属性：bigSum（对象写法）
        ...mapGetters({bigSum:'bigSum'}),

        //借助mapGetters生成计算属性：bigSum（数组写法）
        ...mapGetters(['bigSum'])
    },
    ```

3.  `<strong>`{=html}mapActions方法：`</strong>`{=html}用于帮助我们生成与`actions`对话的方法，即：包含`$store.dispatch(xxx)`的函数

    ``` javascript
    methods:{
        //靠mapActions生成：incrementOdd、incrementWait（对象形式）
        ...mapActions({incrementOdd:'jiaOdd',incrementWait:'jiaWait'})

        //靠mapActions生成：incrementOdd、incrementWait（数组形式）
        ...mapActions(['jiaOdd','jiaWait'])
    }
    ```

4.  `<strong>`{=html}mapMutations方法：`</strong>`{=html}用于帮助我们生成与`mutations`对话的方法，即：包含`$store.commit(xxx)`的函数

    ``` javascript
    methods:{
        //靠mapActions生成：increment、decrement（对象形式）
        ...mapMutations({increment:'JIA',decrement:'JIAN'}),
        
        //靠mapMutations生成：JIA、JIAN（对象形式）
        ...mapMutations(['JIA','JIAN']),
    }
    ```

> 备注：mapActions与mapMutations使用时，若需要传递参数需要：在模板中绑定事件时传递好参数，否则参数是事件对象。

### 7.模块化+命名空间 {#7模块化命名空间}

1.  目的：让代码更好维护，让多种数据分类更加明确。

2.  修改`store.js`

    ``` javascript
    const countAbout = {
      namespaced:true,//开启命名空间
      state:{x:1},
      mutations: { ... },
      actions: { ... },
      getters: {
        bigSum(state){
           return state.sum * 10
        }
      }
    }

    const personAbout = {
      namespaced:true,//开启命名空间
      state:{ ... },
      mutations: { ... },
      actions: { ... }
    }

    const store = new Vuex.Store({
      modules: {
        countAbout,
        personAbout
      }
    })
    ```

3.  开启命名空间后，组件中读取state数据：

    ``` javascript
    //方式一：自己直接读取
    this.$store.state.personAbout.list
    //方式二：借助mapState读取：
    ...mapState('countAbout',['sum','school','subject']),
    ```

4.  开启命名空间后，组件中读取getters数据：

    ``` javascript
    //方式一：自己直接读取
    this.$store.getters['personAbout/firstPersonName']
    //方式二：借助mapGetters读取：
    ...mapGetters('countAbout',['bigSum'])
    ```

5.  开启命名空间后，组件中调用dispatch

    ``` javascript
    //方式一：自己直接dispatch
    this.$store.dispatch('personAbout/addPersonWang',person)
    //方式二：借助mapActions：
    ...mapActions('countAbout',{incrementOdd:'jiaOdd',incrementWait:'jiaWait'})
    ```

6.  开启命名空间后，组件中调用commit

    ``` javascript
    //方式一：自己直接commit
    this.$store.commit('personAbout/ADD_PERSON',person)
    //方式二：借助mapMutations：
    ...mapMutations('countAbout',{increment:'JIA',decrement:'JIAN'}),
    ```

## 路由

1.  理解： 一个路由（route）就是一组映射关系（key -
    value），多个路由需要路由器（router）进行管理。

2.  前端路由：key是路径，value是组件。

### 1.基本使用 {#1基本使用}

1.  安装vue-router，命令：`npm i vue-router`

2.  应用插件：`Vue.use(VueRouter)`

3.  编写router配置项:

    ``` javascript
    //引入VueRouter
    import VueRouter from 'vue-router'
    //引入Luyou 组件
    import About from '../components/About'
    import Home from '../components/Home'

    //创建router实例对象，去管理一组一组的路由规则
    const router = new VueRouter({
    	routes:[
    		{
    			path:'/about',
    			component:About
    		},
    		{
    			path:'/home',
    			component:Home
    		}
    	]
    })

    //暴露router
    export default router
    ```

4.  实现切换（active-class可配置高亮样式）

    ``` vue
    <router-link active-class="active" to="/about">About</router-link>
    ```

5.  指定展示位置

    ``` vue
    <router-view></router-view>
    ```

### 2.几个注意点 {#2几个注意点}

1.  路由组件通常存放在`pages`文件夹，一般组件通常存放在`components`文件夹。

2.  通过切换，"隐藏"了的路由组件，默认是被销毁掉的，需要的时候再去挂载。

3.  每个组件都有自己的`$route`属性，里面存储着自己的路由信息。

4.  整个应用只有一个router，可以通过组件的`$router`属性获取到。

### 3.多级路由（多级路由） {#3多级路由多级路由）}

1.  配置路由规则，使用children配置项：

    ``` javascript
    routes:[
    	{
    		path:'/about',
    		component:About,
    	},
    	{
    		path:'/home',
    		component:Home,
    		children:[ //通过children配置子级路由
    			{
    				path:'news', //此处一定不要写：/news
    				component:News
    			},
    			{
    				path:'message',//此处一定不要写：/message
    				component:Message
    			}
    		]
    	}
    ]
    ```

2.  跳转（要写完整路径）：

    ``` vue
    <router-link to="/home/news">News</router-link>
    ```

### 4.路由的query参数 {#4路由的query参数}

1.  传递参数

    ``` vue
    <!-- 跳转并携带query参数，to的字符串写法 -->
    <router-link :to="/home/message/detail?id=666&title=你好">跳转</router-link>
    				
    <!-- 跳转并携带query参数，to的对象写法 -->
    <router-link 
    	:to="{
    		path:'/home/message/detail',
    		query:{
    		   id:666,
                title:'你好'
    		}
    	}"
    >跳转</router-link>
    ```

2.  接收参数：

    ``` javascript
    $route.query.id
    $route.query.title
    ```

### 5.命名路由 {#5命名路由}

1.  作用：可以简化路由的跳转。

2.  如何使用

    1.  给路由命名：

        ``` javascript
        {
        	path:'/demo',
        	component:Demo,
        	children:[
        		{
        			path:'test',
        			component:Test,
        			children:[
        				{
                              name:'hello' //给路由命名
        					path:'welcome',
        					component:Hello,
        				}
        			]
        		}
        	]
        }
        ```

    2.  简化跳转：

        ``` vue
        <!--简化前，需要写完整的路径 -->
        <router-link to="/demo/test/welcome">跳转</router-link>

        <!--简化后，直接通过名字跳转 -->
        <router-link :to="{name:'hello'}">跳转</router-link>

        <!--简化写法配合传递参数 -->
        <router-link 
        	:to="{
        		name:'hello',
        		query:{
        		   id:666,
                    title:'你好'
        		}
        	}"
        >跳转</router-link>
        ```

### 6.路由的params参数 {#6路由的params参数}

1.  配置路由，声明接收params参数

    ``` javascript
    {
    	path:'/home',
    	component:Home,
    	children:[
    		{
    			path:'news',
    			component:News
    		},
    		{
    			component:Message,
    			children:[
    				{
    					name:'xiangqing',
    					path:'detail/:id/:title', //使用占位符声明接收params参数
    					component:Detail
    				}
    			]
    		}
    	]
    }
    ```

2.  传递参数

    ``` vue
    <!-- 跳转并携带params参数，to的字符串写法 -->
    <router-link :to="/home/message/detail/666/你好">跳转</router-link>
    				
    <!-- 跳转并携带params参数，to的对象写法 -->
    <router-link 
    	:to="{
    		name:'xiangqing',
    		params:{
    		   id:666,
                title:'你好'
    		}
    	}"
    >跳转</router-link>
    ```

    > 特别注意：路由携带params参数时，若使用to的对象写法，则不能使用path配置项，必须使用name配置！

3.  接收参数：

    ``` javascript
    $route.params.id
    $route.params.title
    ```

### 7.路由的props配置 {#7路由的props配置}

作用：让路由组件更方便的收到参数

``` javascript
{
	name:'xiangqing',
	path:'detail/:id',
	component:Detail,

	//第一种写法：props值为对象，该对象中所有的key-value的组合最终都会通过props传给Detail组件
	// props:{a:900}

	//第二种写法：props值为布尔值，布尔值为true，则把路由收到的所有params参数通过props传给Detail组件
	// props:true
	
	//第三种写法：props值为函数，该函数返回的对象中每一组key-value都会通过props传给Detail组件
	props(route){
		return {
			id:route.query.id,
			title:route.query.title
		}
	}
}
```

### 8.`<router-link>`的replace属性 {#8router-link的replace属性}

1.  作用：控制路由跳转时操作浏览器历史记录的模式

2.  浏览器的历史记录有两种写入方式：分别为`push`和`replace`，`push`是追加历史记录，`replace`是替换当前记录。路由跳转时候默认为`push`

3.  如何开启`replace`模式：`<router-link replace .......>News</router-link>`

### 9.编程式路由导航 {#9编程式路由导航}

1.  作用：不借助`<router-link>`实现路由跳转，让路由跳转更加灵活

2.  具体编码：

    ``` javascript
    //$router的两个API
    this.$router.push({
    	name:'xiangqing',
    		params:{
    			id:xxx,
    			title:xxx
    		}
    })

    this.$router.replace({
    	name:'xiangqing',
    		params:{
    			id:xxx,
    			title:xxx
    		}
    })
    this.$router.forward() //前进
    this.$router.back() //后退
    this.$router.go() //可前进也可后退
    ```

### 10.缓存路由组件 {#10缓存路由组件}

1.  作用：让不展示的路由组件保持挂载，不被销毁。

2.  具体编码：

    ``` vue
    <keep-alive include="News"> 
        <router-view></router-view>
    </keep-alive>
    ```

### 11.两个新的生命周期钩子 {#11两个新的生命周期钩子}

1.  作用：路由组件所独有的两个钩子，用于捕获路由组件的激活状态。

2.  具体名字：

    1.  `activated`路由组件被激活时触发。

    2.  `deactivated`路由组件失活时触发。

### 12.路由守卫 {#12路由守卫}

1.  作用：对路由进行权限控制

2.  分类：全局守卫、独享守卫、组件内守卫

3.  全局守卫:

    ``` javascript
    //全局前置守卫：初始化时执行、每次路由切换前执行
    router.beforeEach((to,from,next)=>{
    	console.log('beforeEach',to,from)
    	if(to.meta.isAuth){ //判断当前路由是否需要进行权限控制
    		if(localStorage.getItem('school') === 'atguigu'){ //权限控制的具体规则
    			next() //放行
    		}else{
    			alert('暂无权限查看')
    			// next({name:'guanyu'})
    		}
    	}else{
    		next() //放行
    	}
    })

    //全局后置守卫：初始化时执行、每次路由切换后执行
    router.afterEach((to,from)=>{
    	console.log('afterEach',to,from)
    	if(to.meta.title){ 
    		document.title = to.meta.title //修改网页的title
    	}else{
    		document.title = 'vue_test'
    	}
    })
    ```

4.  独享守卫:

    ``` javascript
    beforeEnter(to,from,next){
    	console.log('beforeEnter',to,from)
    	if(to.meta.isAuth){ //判断当前路由是否需要进行权限控制
    		if(localStorage.getItem('school') === 'atguigu'){
    			next()
    		}else{
    			alert('暂无权限查看')
    			// next({name:'guanyu'})
    		}
    	}else{
    		next()
    	}
    }
    ```

5.  组件内守卫：

    ``` javascript
    //进入守卫：通过路由规则，进入该组件时被调用
    beforeRouteEnter (to, from, next) {
    },
    //离开守卫：通过路由规则，离开该组件时被调用
    beforeRouteLeave (to, from, next) {
    }
    ```

### 13.路由器的两种工作模式 {#13路由器的两种工作模式}

1.  对于一个url来说，什么是hash值？------ #及其后面的内容就是hash值。

2.  hash值不会包含在 HTTP 请求中，即：hash值不会带给服务器。

3.  hash模式：

    1.  地址中永远带着#号，不美观 。

    2.  若以后将地址通过第三方手机app分享，若app校验严格，则地址会被标记为不合法。

    3.  兼容性较好。

4.  history模式：

    1.  地址干净，美观 。

    2.  兼容性和hash模式相比略差。

    3.  应用部署上线时需要后端人员支持，解决刷新页面服务端404的问题。

    connect-history-api-fallback

### 技巧 {#技巧}

1.获取输入框中的内容:

①接收参数(event)，eg：event.target.value；

②v-model双向绑定；

2.实现单机id自增:

① uuid

② nanoid(迷你版) \-\--\> npm i nanoid ；注意它使用的是分别暴露； import
{nanoid} from \"nanoid\"

### **Vue UI 组件库**

**移动端常用 UI 组件库** ：

1.  Vant <https://youzan.github.io/vant>

2.  Cube UI <https://didi.github.io/cube-ui>

3.  Mint UI <http://mint-ui.github.io>

\*\* **PC 端常用 UI 组件库\***\* ：

1.  Element UI <https://element.eleme.cn>

2.  IView UI <https://www.iviewui.com>

3.  <https://www.antdv.com/docs/vue/introduce-cn/>

4.  <https://nutui.jd.com/#/start>

------------------------------------------------------------------------

# Vue3

`<img src="https://user-images.githubusercontent.com/499550/93624428-53932780-f9ae-11ea-8d16-af949e16a09f.png" style="width:200px" />`{=html}

## 1.Vue3简介 {#1vue3简介}

-   2020年9月18日，Vue.js发布3.0版本，代号：One Piece（海贼王）

-   耗时2年多、[2600+次提交](https://github.com/vuejs/vue-next/graphs/commit-activity)、[30+个RFC](https://github.com/vuejs/rfcs/tree/master/active-rfcs)、[600+次PR](https://github.com/vuejs/vue-next/pulls?q=is%3Apr+is%3Amerged+-author%3Aapp%2Fdependabot-preview+)、[99位贡献者](https://github.com/vuejs/vue-next/graphs/contributors)

-   github上的tags地址：<https://github.com/vuejs/vue-next/releases/tag/v3.0.0>

## 2.Vue3带来了什么 {#2vue3带来了什么}

### 1.性能的提升 {#1性能的提升}

-   打包大小减少41%

-   初次渲染快55%, 更新渲染快133%

-   内存减少54%

    \...\...

### 2.源码的升级 {#2源码的升级}

-   使用Proxy代替defineProperty实现响应式

-   重写虚拟DOM的实现和Tree-Shaking

    \...\...

### 3.拥抱TypeScript {#3拥抱typescript}

-   Vue3可以更好的支持TypeScript

### 4.新的特性 {#4新的特性}

1.  Composition API（组合API）

    -   setup配置

    -   ref与reactive

    -   watch与watchEffect

    -   provide与inject

    -   \...\...

2.  新的内置组件

    -   Fragment

    -   Teleport

    -   Suspense

3.  其他改变

    -   新的生命周期钩子

    -   data 选项应始终被声明为一个函数

    -   移除keyCode支持作为 v-on 的修饰符

    -   \...\...

## 一、创建Vue3.0工程 {#一创建vue30工程}

### 1.使用 vue-cli 创建 {#1使用-vue-cli-创建}

官方文档：<https://cli.vuejs.org/zh/guide/creating-a-project.html#vue-create>

``` shell
## 查看@vue/cli版本，确保@vue/cli版本在4.5.0以上
vue --version
## 安装或者升级你的@vue/cli
npm install -g @vue/cli
## 创建
vue create vue_test
## 启动
cd vue_test
npm run serve
```

### 2.使用 vite 创建 {#2使用-vite-创建}

官方文档：<https://v3.cn.vuejs.org/guide/installation.html#vite>

vite官网：<https://vitejs.cn>

-   什么是vite？------ 新一代前端构建工具。

-   优势如下：

    -   开发环境中，无需打包操作，可快速的冷启动。

    -   轻量快速的热重载（HMR）。

    -   真正的按需编译，不再等待整个应用编译完成。

-   传统构建 与 vite构建对比图

`<img src="https://cn.vitejs.dev/assets/bundler.37740380.png" style="width:500px;height:280px;float:left" />`{=html}`<img src="https://cn.vitejs.dev/assets/esm.3070012d.png" style="width:480px;height:280px" />`{=html}

``` shell
## 创建工程
npm init vite-app <project-name>
## 进入工程目录
cd <project-name>
## 安装依赖
npm install
## 运行
npm run dev
```

## 二、常用 Composition API

官方文档:
<https://v3.cn.vuejs.org/guide/composition-api-introduction.html>

### 1.拉开序幕的setup {#1拉开序幕的setup}

1.  理解：Vue3.0中一个新的配置项，值为一个函数。

2.  setup是所有`<strong style="color:#DD5145">`{=html}Composition
    API（组合API）`</strong>`{=html}`<i style="color:gray;font-weight:bold">`{=html}"
    表演的舞台 "`</i>`{=html}。

3.  组件中所用到的：数据、方法等等，均要配置在setup中。

4.  setup函数的两种返回值：

    1.  若返回一个对象，则对象中的属性、方法,
        在模板中均可以直接使用。（重点关注！）

    2.  `<span style="color:#aad">`{=html}若返回一个渲染函数：则可以自定义渲染内容。（了解）`</span>`{=html}

5.  注意点：

    1.  尽量不要与Vue2.x配置混用

        -   Vue2.x配置（data、methos、computed\...）中`<strong style="color:#DD5145">`{=html}可以访问到`</strong>`{=html}setup中的属性、方法。

        -   但在setup中`<strong style="color:#DD5145">`{=html}不能访问到`</strong>`{=html}Vue2.x配置（data、methos、computed\...）。

        -   如果有重名, setup优先。

    2.  setup不能是一个async函数，因为返回值不再是return的对象,
        而是promise,
        模板看不到return对象中的属性。（后期也可以返回一个Promise实例，但需要Suspense和异步组件的配合）

### 2.ref函数 {#2ref函数}

-   作用: 定义一个响应式的数据

-   语法: `const xxx = ref(initValue)`

    -   创建一个包含响应式数据的`<strong style="color:#DD5145">`{=html}引用对象（reference对象，简称ref对象）`</strong>`{=html}。

    -   JS中操作数据： `xxx.value`

    -   模板中读取数据: 不需要.value，直接：`<div>{{xxx}}</div>`

-   备注：

    -   接收的数据可以是：基本类型、也可以是对象类型。

    -   基本类型的数据：响应式依然是靠`Object.defineProperty()`的`get`与`set`完成的。

    -   对象类型的数据：内部
        `<i style="color:gray;font-weight:bold">`{=html}" 求助
        "`</i>`{=html} 了Vue3.0中的一个新函数------ `reactive`函数。

### 3.reactive函数 {#3reactive函数}

-   作用:
    定义一个`<strong style="color:#DD5145">`{=html}对象类型`</strong>`{=html}的响应式数据（基本类型不要用它，要用`ref`函数）

-   语法：`const 代理对象= reactive(源对象)`接收一个对象（或数组），返回一个`<strong style="color:#DD5145">`{=html}代理对象（Proxy的实例对象，简称proxy对象）`</strong>`{=html}

-   reactive定义的响应式数据是"深层次的"。

-   内部基于 ES6 的 Proxy 实现，通过代理对象操作源对象内部数据进行操作。

### 4.Vue3.0中的响应式原理 {#4vue30中的响应式原理}

#### vue2.x的响应式 {#vue2x的响应式}

-   实现原理：

    -   对象类型：通过`Object.defineProperty()`对属性的读取、修改进行拦截（数据劫持）。

    -   数组类型：通过重写更新数组的一系列方法来实现拦截。（对数组的变更方法进行了包裹）。

        ``` javascript
        Object.defineProperty(data, 'count', {
            get () {}, 
            set () {}
        })
        ```

-   存在问题：

    -   新增属性、删除属性, 界面不会更新。

    -   直接通过下标修改数组, 界面不会自动更新。

#### Vue3.0的响应式 {#vue30的响应式}

-   实现原理:

    -   通过Proxy（代理）: 拦截对象中任意属性的变化,
        包括：属性值的读写、属性的添加、属性的删除等。

    -   通过Reflect（反射）: 对源对象的属性进行操作。

    -   MDN文档中描述的Proxy与Reflect：

        -   Proxy：<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Proxy>

        -   Reflect：<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect>

            ``` javascript
            new Proxy(data, {
            	// 拦截读取属性值
                get (target, prop) {
                	return Reflect.get(target, prop)
                },
                // 拦截设置属性值或添加新属性
                set (target, prop, value) {
                	return Reflect.set(target, prop, value)
                },
                // 拦截删除属性
                deleteProperty (target, prop) {
                	return Reflect.deleteProperty(target, prop)
                }
            })

            proxy.name = 'tom'   
            ```

### 5.reactive对比ref {#5reactive对比ref}

-   从定义数据角度对比：

    -   ref用来定义：`<strong style="color:#DD5145">`{=html}基本类型数据`</strong>`{=html}。

    -   reactive用来定义：`<strong style="color:#DD5145">`{=html}对象（或数组）类型数据`</strong>`{=html}。

    -   备注：ref也可以用来定义`<strong style="color:#DD5145">`{=html}对象（或数组）类型数据`</strong>`{=html},
        它内部会自动通过`reactive`转为`<strong style="color:#DD5145">`{=html}代理对象`</strong>`{=html}。

-   从原理角度对比：

    -   ref通过`Object.defineProperty()`的`get`与`set`来实现响应式（数据劫持）。

    -   reactive通过使用`<strong style="color:#DD5145">`{=html}Proxy`</strong>`{=html}来实现响应式（数据劫持）,
        并通过`<strong style="color:#DD5145">`{=html}Reflect`</strong>`{=html}操作`<strong style="color:orange">`{=html}源对象`</strong>`{=html}内部的数据。

-   从使用角度对比：

    -   ref定义的数据：操作数据`<strong style="color:#DD5145">`{=html}需要`</strong>`{=html}`.value`，读取数据时模板中直接读取`<strong style="color:#DD5145">`{=html}不需要`</strong>`{=html}`.value`。

    -   reactive定义的数据：操作数据与读取数据：`<strong style="color:#DD5145">`{=html}均不需要`</strong>`{=html}`.value`。

### 6.setup的两个注意点 {#6setup的两个注意点}

-   setup执行的时机

    -   在beforeCreate之前执行一次，this是undefined。

-   setup的参数

    -   props：值为对象，包含：组件外部传递过来，且组件内部声明接收了的属性。

    -   context：上下文对象

        -   attrs:
            值为对象，包含：组件外部传递过来，但没有在props配置中声明的属性,
            相当于 `this.$attrs`。

        -   slots: 收到的插槽内容, 相当于 `this.$slots`。

        -   emit: 分发自定义事件的函数, 相当于 `this.$emit`。

### 7.计算属性与监视 {#7计算属性与监视}

#### 1.computed函数 {#1computed函数}

-   与Vue2.x中computed配置功能一致

-   写法

    ``` javascript
    import {computed} from 'vue'

    setup(){
        ...
    	//计算属性——简写
        let fullName = computed(()=>{
            return person.firstName + '-' + person.lastName
        })
        //计算属性——完整
        let fullName = computed({
            get(){
                return person.firstName + '-' + person.lastName
            },
            set(value){
                const nameArr = value.split('-')
                person.firstName = nameArr[0]
                person.lastName = nameArr[1]
            }
        })
    }
    ```

#### 2.watch函数 {#2watch函数}

-   与Vue2.x中watch配置功能一致

-   两个小"坑"：

    -   监视reactive定义的响应式数据时：oldValue无法正确获取、强制开启了深度监视（deep配置失效）。

    -   监视reactive定义的响应式数据中某个属性时：deep配置有效。

    ``` javascript
    //情况一：监视ref定义的响应式数据
    watch(sum,(newValue,oldValue)=>{
    	console.log('sum变化了',newValue,oldValue)
    },{immediate:true})

    //情况二：监视多个ref定义的响应式数据
    watch([sum,msg],(newValue,oldValue)=>{
    	console.log('sum或msg变化了',newValue,oldValue)
    }) 

    /* 情况三：监视reactive定义的响应式数据
    			若watch监视的是reactive定义的响应式数据，则无法正确获得oldValue！！
    			若watch监视的是reactive定义的响应式数据，则强制开启了深度监视 
    */
    watch(person,(newValue,oldValue)=>{
    	console.log('person变化了',newValue,oldValue)
    },{immediate:true,deep:false}) //此处的deep配置不再奏效

    //情况四：监视reactive定义的响应式数据中的某个属性
    watch(()=>person.job,(newValue,oldValue)=>{
    	console.log('person的job变化了',newValue,oldValue)
    },{immediate:true,deep:true}) 

    //情况五：监视reactive定义的响应式数据中的某些属性
    watch([()=>person.job,()=>person.name],(newValue,oldValue)=>{
    	console.log('person的job变化了',newValue,oldValue)
    },{immediate:true,deep:true})

    //特殊情况
    watch(()=>person.job,(newValue,oldValue)=>{
        console.log('person的job变化了',newValue,oldValue)
    },{deep:true}) //此处由于监视的是reactive素定义的对象中的某个属性，所以deep配置有效
    ```

#### 3.watchEffect函数 {#3watcheffect函数}

-   watch的套路是：既要指明监视的属性，也要指明监视的回调。

-   watchEffect的套路是：不用指明监视哪个属性，监视的回调中用到哪个属性，那就监视哪个属性。

-   watchEffect有点像computed：

    -   但computed注重的计算出来的值（回调函数的返回值），所以必须要写返回值。

    -   而watchEffect更注重的是过程（回调函数的函数体），所以不用写返回值。

    ``` javascript
    //watchEffect所指定的回调中用到的数据只要发生变化，则直接重新执行回调。
    watchEffect(()=>{
        const x1 = sum.value
        const x2 = person.age
        console.log('watchEffect配置的回调执行了')
    })
    ```

### 8.生命周期 {#8生命周期}

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><div style="border:1px solid black;width:380px;float:left;margin-right:20px;"><strong>vue2.x的生命周期</strong><img style="zoom:33%;width:1200px" alt="lifecycle_2" src="https://cn.vuejs.org/images/lifecycle.png" data-src="https://cn.vuejs.org/images/lifecycle.png" onerror="this.style.display = 'none';" /></div><div style="border:1px solid black;width:510px;height:985px;float:left"><strong>vue3.0的生命周期</strong><img style="zoom:33%;width:2500px" alt="lifecycle_2" src="https://v3.cn.vuejs.org/images/lifecycle.svg" data-src="https://v3.cn.vuejs.org/images/lifecycle.svg" onerror="this.style.display = 'none';" /></div></body></html>
```

1

-   Vue3.0中可以继续使用Vue2.x中的生命周期钩子，但有有两个被更名：

    -   `beforeDestroy`改名为 `beforeUnmount`

    -   `destroyed`改名为 `unmounted`

-   Vue3.0也提供了 Composition API
    形式的生命周期钩子，与Vue2.x中钩子对应关系如下：

    -   `beforeCreate`===>`setup()`

    -   `created``<mark>`{=html}=`</mark>`{=html}==>`setup()`

    -   `beforeMount` ===>`onBeforeMount`

    -   `mounted``<mark>`{=html}=`</mark>`{=html}==>`onMounted`

    -   `beforeUpdate`===>`onBeforeUpdate`

    -   `updated` `<mark>`{=html}=`</mark>`{=html}==>`onUpdated`

    -   `beforeUnmount` ==>`onBeforeUnmount`

    -   `unmounted` `<mark>`{=html}=`</mark>`{=html}\>`onUnmounted`

### 9.自定义hook函数 {#9自定义hook函数}

-   什么是hook？------ 本质是一个函数，把setup函数中使用的Composition
    API进行了封装。

-   类似于vue2.x中的mixin。

-   自定义hook的优势: 复用代码, 让setup中的逻辑更清楚易懂。

### 10.toRef {#10toref}

-   作用：创建一个 ref 对象，其value值指向另一个对象中的某个属性。

-   语法：`const name = toRef(person,'name')`

-   应用: 要将响应式对象中的某个属性单独提供给外部使用时。

```{=html}
<!-- -->
```
-   扩展：`toRefs` 与`toRef`功能一致，但可以批量创建多个 ref
    对象，语法：`toRefs(person)`

## 三、其它 Composition API

#### 1.shallowReactive 与 shallowRef {#1shallowreactive-与-shallowref}

-   shallowReactive：只处理对象最外层属性的响应式（浅响应式）。

-   shallowRef：只处理基本数据类型的响应式, 不进行对象的响应式处理。

-   什么时候使用?

    -   如果有一个对象数据，结构比较深, 但变化时只是外层属性变化 ===>
        shallowReactive。

    -   如果有一个对象数据，后续功能不会修改该对象中的属性，而是生新的对象来替换
        ===> shallowRef。

#### 2.readonly 与 shallowReadonly {#2readonly-与-shallowreadonly}

-   readonly: 让一个响应式数据变为只读的（深只读）。

-   shallowReadonly：让一个响应式数据变为只读的（浅只读）。

-   应用场景: 不希望数据被修改时。

#### 3.toRaw 与 markRaw {#3toraw-与-markraw}

-   toRaw：

    -   作用：将一个由`reactive`生成的`<strong style="color:orange">`{=html}响应式对象`</strong>`{=html}转为`<strong style="color:orange">`{=html}普通对象`</strong>`{=html}。

    -   使用场景：用于读取响应式对象对应的普通对象，对这个普通对象的所有操作，不会引起页面更新。

-   markRaw：

    -   作用：标记一个对象，使其永远不会再成为响应式对象。

    -   应用场景:

        1.  有些值不应被设置为响应式的，例如复杂的第三方类库等。

        2.  当渲染具有不可变数据源的大列表时，跳过响应式转换可以提高性能。

#### 4.customRef {#4customref}

-   作用：创建一个自定义的 ref，并对其依赖项跟踪和更新触发进行显式控制。

-   实现防抖效果：

    ``` vue
    <template>
    	<input type="text" v-model="keyword">
    	<h3>{{keyword}}</h3>
    </template>

    <script>
    	import {ref,customRef} from 'vue'
    	export default {
    		name:'Demo',
    		setup(){
    			// let keyword = ref('hello') //使用Vue准备好的内置ref
    			//自定义一个myRef
    			function myRef(value,delay){
    				let timer
    				//通过customRef去实现自定义
    				return customRef((track,trigger)=>{
    					return{
    						get(){
    							track() //告诉Vue这个value值是需要被“追踪”的
    							return value
    						},
    						set(newValue){
    							clearTimeout(timer)
    							timer = setTimeout(()=>{
    								value = newValue
    								trigger() //告诉Vue去更新界面
    							},delay)
    						}
    					}
    				})
    			}
    			let keyword = myRef('hello',500) //使用程序员自定义的ref
    			return {
    				keyword
    			}
    		}
    	}
    </script>
    ```

#### 5.provide 与 inject {#5provide-与-inject}

`<img src="https://v3.cn.vuejs.org/images/components_provide.png" style="width:300px" />`{=html}

-   作用：实现`<strong style="color:#DD5145">`{=html}祖与后代组件间`</strong>`{=html}通信

-   套路：父组件有一个 `provide` 选项来提供数据，后代组件有一个 `inject`
    选项来开始使用这些数据

-   具体写法：

    1.  祖组件中：

        ``` javascript
        setup(){
        	......
            let car = reactive({name:'奔驰',price:'40万'})
            provide('car',car)
            ......
        }
        ```

    2.  后代组件中：

        ``` javascript
        setup(props,context){
        	......
            const car = inject('car')
            return {car}
        	......
        }
        ```

#### 6.响应式数据的判断 {#6响应式数据的判断}

-   isRef: 检查一个值是否为一个 ref 对象

-   isReactive: 检查一个对象是否是由 `reactive` 创建的响应式代理

-   isReadonly: 检查一个对象是否是由 `readonly` 创建的只读代理

-   isProxy: 检查一个对象是否是由 `reactive` 或者 `readonly`
    方法创建的代理

## 四、Composition API 的优势

#### 1.Options API 存在的问题 {#1options-api-存在的问题}

使用传统OptionsAPI中，新增或者修改一个需求，就需要分别在data，methods，computed里修改
。

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><div style="width:600px;height:370px;overflow:hidden;float:left">
    <img style="width:600px;float:left" src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f84e4e2c02424d9a99862ade0a2e4114~tplv-k3u1fbpfcp-watermark.image" data-src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f84e4e2c02424d9a99862ade0a2e4114~tplv-k3u1fbpfcp-watermark.image" onerror="this.style.display = 'none';" />
</div>
<div style="width:300px;height:370px;overflow:hidden;float:left">
    <img style="zoom:50%;width:560px;left" src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e5ac7e20d1784887a826f6360768a368~tplv-k3u1fbpfcp-watermark.image" data-src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e5ac7e20d1784887a826f6360768a368~tplv-k3u1fbpfcp-watermark.image" onerror="this.style.display = 'none';" /> 
</div></body></html>
```

##### 2.Composition API 的优势 {#2composition-api-的优势}

我们可以更加优雅的组织我们的代码，函数。让相关功能的代码更加有序的组织在一起。

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><div style="width:500px;height:340px;overflow:hidden;float:left">
    <img style="height:360px" src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bc0be8211fc54b6c941c036791ba4efe~tplv-k3u1fbpfcp-watermark.image" data-src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bc0be8211fc54b6c941c036791ba4efe~tplv-k3u1fbpfcp-watermark.image" onerror="this.style.display = 'none';" />
</div>
<div style="width:430px;height:340px;overflow:hidden;float:left">
    <img style="height:360px" src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6cc55165c0e34069a75fe36f8712eb80~tplv-k3u1fbpfcp-watermark.image" data-src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6cc55165c0e34069a75fe36f8712eb80~tplv-k3u1fbpfcp-watermark.image" onerror="this.style.display = 'none';" />
</div></body></html>
```

## 五、新的组件

#### 1.Fragment {#1fragment}

-   在Vue2中: 组件必须有一个根标签

-   在Vue3中: 组件可以没有根标签,
    内部会将多个标签包含在一个Fragment虚拟元素中

-   好处: 减少标签层级, 减小内存占用

#### 2.Teleport {#2teleport}

-   什么是Teleport？------ `Teleport`
    是一种能够将我们的`<strong style="color:#DD5145">`{=html}组件html结构`</strong>`{=html}移动到指定位置的技术。

    ``` vue
    <teleport to="移动位置">
    	<div v-if="isShow" class="mask">
    		<div class="dialog">
    			<h3>我是一个弹窗</h3>
    			<button @click="isShow = false">关闭弹窗</button>
    		</div>
    	</div>
    </teleport>
    ```

#### 3.Suspense {#3suspense}

-   等待异步组件时渲染一些额外内容，让应用有更好的用户体验

-   使用步骤：

    -   异步引入组件

        ``` javascript
        import {defineAsyncComponent} from 'vue'
        const Child = defineAsyncComponent(()=>import('./components/Child.vue'))
        ```

    -   使用`Suspense`包裹组件，并配置好`default` 与 `fallback`

        ``` vue
        <template>
        	<div class="app">
        		<h3>我是App组件</h3>
        		<Suspense>
        			<template v-slot:default>
        				<Child/>
        			</template>
        			<template v-slot:fallback>
        				<h3>加载中.....</h3>
        			</template>
        		</Suspense>
        	</div>
        </template>
        ```

## 六、其他

#### 1.全局API的转移 {#1全局api的转移}

-   Vue 2.x 有许多全局 API 和配置。

    -   例如：注册全局组件、注册全局指令等。

        ``` javascript
        //注册全局组件
        Vue.component('MyButton', {
          data: () => ({
            count: 0
          }),
          template: '<button @click="count++">Clicked {{ count }} times.</button>'
        })

        //注册全局指令
        Vue.directive('focus', {
          inserted: el => el.focus()
        }
        ```

-   Vue3.0中对这些API做出了调整：

    -   将全局的API，即：`Vue.xxx`调整到应用实例（`app`）上

          2.x 全局 API（`Vue`）      3.x 实例 API (`app`)
          -------------------------- ---------------------------------------------------------------
          Vue.config.xxxx            app.config.xxxx
          Vue.config.productionTip   `<strong style="color:#DD5145">`{=html}移除`</strong>`{=html}
          Vue.component              app.component
          Vue.directive              app.directive
          Vue.mixin                  app.mixin
          Vue.use                    app.use
          Vue.prototype              app.config.globalProperties

#### 2.其他改变 {#2其他改变}

-   data选项应始终被声明为一个函数。

-   过度类名的更改：

    -   Vue2.x写法

        ``` css
        .v-enter,
        .v-leave-to {
          opacity: 0;
        }
        .v-leave,
        .v-enter-to {
          opacity: 1;
        }
        ```

    -   Vue3.x写法

        ``` css
        .v-enter-from,
        .v-leave-to {
          opacity: 0;
        }

        .v-leave-from,
        .v-enter-to {
          opacity: 1;
        }
        ```

-   `<strong style="color:#DD5145">`{=html}移除`</strong>`{=html}keyCode作为
    v-on 的修饰符，同时也不再支持`config.keyCodes`

-   `<strong style="color:#DD5145">`{=html}移除`</strong>`{=html}`v-on.native`修饰符

    -   父组件中绑定事件

        ``` vue
        <my-component
          v-on:close="handleComponentEvent"
          v-on:click="handleNativeClickEvent"
        />
        ```

    -   子组件中声明自定义事件

        ``` vue
        <script>
          export default {
            emits: ['close']
          }
        </script>
        ```

-   `<strong style="color:#DD5145">`{=html}移除`</strong>`{=html}过滤器（filter）

    > 过滤器虽然这看起来很方便，但它需要一个自定义语法，打破大括号内表达式是
    > "只是 JavaScript"
    > 的假设，这不仅有学习成本，而且有实现成本！建议用方法调用或计算属性去替换过滤器。

-   \...\...

# React

### 1.jsx语法 {#1jsx语法}

> 1.在定义虚拟dom时，不可以加引号
>
> 2.标签中混入js表达式时使用{}
>
> 3.样式的类名不能使用class,只能使用className
>
> 4.内联样式要使用style={{key:value\...}}的形式写,(且使用小驼峰)
>
> 5.虚拟DOM中只能有一个根标签
>
> 6.关于标签的首字母：
>
> -   若首字母为小写，需要和html本身的标签名一致，否则会报错
>
> -   若首字母为大写,
>     react会去渲染对应的组件，如果组件没有定义，则会报错

``` javascript
<div id="test"></div>

<!-- react的核心库 -->
<script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
<!-- 用于支持react的扩展库 -->
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>
<!-- 将jsx转化为js -->
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

<script type="text/babel">  
    const msg = "Hello React"

//创建虚拟DOM
const VDOM  = (
    <div>
    	<h1 className="bg" style={{color:'red',fontSize:'100px'}}>{msg}</h1>
		<h1>你好</h1>
	</div>
)
ReactDOM.render(VDOM,document.getElementById("test"))

</script>
```

### react脚手架配置代理

#### 方法一 {#方法一-2}

> 在package.json中追加如下配置

``` json
"proxy":"http://localhost:5000"
```

说明：

1.  优点：配置简单，前端请求资源时可以不加任何前缀。

2.  缺点：不能配置多个代理。

3.  工作方式：上述方式配置代理，当请求了3000不存在的资源时，那么该请求会转发给5000
    （优先匹配前端资源）

#### 方法二 {#方法二-2}

1.  第一步：创建代理配置文件

    ``` 
    在src下创建配置文件：src/setupProxy.js
    ```

2.  编写setupProxy.js配置具体代理规则：

    ``` javascript
    const proxy = require('http-proxy-middleware')

    module.exports = function(app) {
      app.use(
        proxy('/api1', {  //api1是需要转发的请求(所有带有/api1前缀的请求都会转发给5000)
          target: 'http://localhost:5000', //配置转发目标地址(能返回数据的服务器地址)
          changeOrigin: true, //控制服务器接收到的请求头中host字段的值
          /*
          	changeOrigin设置为true时，服务器收到的请求头中的host为：localhost:5000
          	changeOrigin设置为false时，服务器收到的请求头中的host为：localhost:3000
          	changeOrigin默认值为false，但我们一般将changeOrigin值设为true
          */
          pathRewrite: {'^/api1': ''} //去除请求前缀，保证交给后台服务器的是正常请求地址(必须配置)
        }),
        proxy('/api2', { 
          target: 'http://localhost:5001',
          changeOrigin: true,
          pathRewrite: {'^/api2': ''}
        })
      )
    }
    ```

说明：

1.  优点：可以配置多个代理，可以灵活的控制请求是否走代理。

2.  缺点：配置繁琐，前端请求资源时必须加前缀。

3.  # React Router 6 快速上手

    ## 1.概述 {#1概述-1}

    1.  React Router 以三个不同的包发布到 npm 上，它们分别为：

        1.  react-router: 路由的核心库，提供了很多的：组件、钩子。

        2.  `<strong style="color:#dd4d40">`{=html}**react-router-dom:**`</strong >`{=html}
            `<strong style="color:#dd4d40">`{=html}包含react-router所有内容，并添加一些专门用于
            DOM 的组件，例如 `<BrowserRouter>`等 `</strong>`{=html}。

        3.  react-router-native:
            包括react-router所有内容，并添加一些专门用于ReactNative的API，例如:`<NativeRouter>`等。

    2.  与React Router 5.x 版本相比，改变了什么？

        1.  内置组件的变化：移除`<Switch/>` ，新增 `<Routes/>`等。

        2.  语法的变化：`component={About}` 变为
            `element={<About/>}`等。

        3.  新增多个hook：`useParams`、`useNavigate`、`useMatch`等。

        4.  `<strong style="color:#dd4d40">`{=html}官方明确推荐函数式组件了！！！`</strong>`{=html}

            \...\...

    ## 2.Component {#2component-1}

    ### 1. `<BrowserRouter>` {#1-browserrouter-1}

    1.  说明：`<BrowserRouter>`用于包裹整个应用。

    2.  示例代码：

        ``` jsx
        import React from "react";
        import ReactDOM from "react-dom";
        import { BrowserRouter } from "react-router-dom";

        ReactDOM.render(
          <BrowserRouter>
            {/* 整体结构（通常为App组件） */}
          </BrowserRouter>,root
        );
        ```

    ### 2. `<HashRouter>` {#2-hashrouter-1}

    1.  说明：作用与`<BrowserRouter>`一样，但`<HashRouter>`修改的是地址栏的hash值。

    2.  备注：6.x版本中`<HashRouter>`、`<BrowserRouter>` 的用法与 5.x
        相同。

    ### 3. `<Routes/> 与 <Route/>` {#3-routes-与-route-1}

    1.  v6版本中移出了先前的`<Switch>`，引入了新的替代者：`<Routes>`。

    2.  `<Routes>` 和
        `<Route>`要配合使用，且必须要用`<Routes>`包裹`<Route>`。

    3.  `<Route>` 相当于一个 if 语句，如果其路径与当前 URL
        匹配，则呈现其对应的组件。

    4.  `<Route caseSensitive>`
        属性用于指定：匹配时是否区分大小写（默认为 false）。

    5.  当URL发生变化时，`<Routes>`都会查看其所有子`<Route>`
        元素以找到最佳匹配并呈现组件 。

    6.  `<Route>` 也可以嵌套使用，且可配合`useRoutes()`配置 "路由表"
        ，但需要通过 `<Outlet>` 组件来渲染其子路由。

    7.  示例代码：

        ``` jsx
        <Routes>
            /*path属性用于定义路径，element属性用于定义当前路径所对应的组件*/
            <Route path="/login" element={<Login />}></Route>

        		/*用于定义嵌套路由，home是一级路由，对应的路径/home*/
            <Route path="home" element={<Home />}>
               /*test1 和 test2 是二级路由,对应的路径是/home/test1 或 /home/test2*/
              <Route path="test1" element={<Test/>}></Route>
              <Route path="test2" element={<Test2/>}></Route>
        		</Route>
        	
        		//Route也可以不写element属性, 这时就是用于展示嵌套的路由 .所对应的路径是/users/xxx
            <Route path="users">
               <Route path="xxx" element={<Demo />} />
            </Route>
        </Routes>
        ```

    ### 4. `<Link>` {#4-link-1}

    1.  作用: 修改URL，且不发送网络请求（路由链接）。

    2.  注意: 外侧需要用`<BrowserRouter>`或`<HashRouter>`包裹。

    3.  示例代码：

        ``` jsx
        import { Link } from "react-router-dom";

        function Test() {
          return (
            <div>
            	<Link to="/路径">按钮</Link>
            </div>
          );
        }
        ```

    ### 5. `<NavLink>` {#5-navlink-1}

    1.  作用: 与`<Link>`组件类似，且可实现导航的"高亮"效果。

    2.  示例代码：

        ``` jsx
        // 注意: NavLink默认类名是active，下面是指定自定义的class

        //自定义样式
        <NavLink
            to="login"
            className={({ isActive }) => {
                console.log('home', isActive)
                return isActive ? 'base one' : 'base'
            }}
        >login</NavLink>

        /*
        	默认情况下，当Home的子组件匹配成功，Home的导航也会高亮，
        	当NavLink上添加了end属性后，若Home的子组件匹配成功，则Home的导航没有高亮效果。
        */
        <NavLink to="home" end >home</NavLink>
        ```

    ### 6. `<Navigate>` {#6-navigate-1}

    1.  作用：只要`<Navigate>`组件被渲染，就会修改路径，切换视图。

    2.  `replace`属性用于控制跳转模式（push 或 replace，默认是push）。

    3.  示例代码：

        ``` jsx
        import React,{useState} from 'react'
        import {Navigate} from 'react-router-dom'

        export default function Home() {
        	const [sum,setSum] = useState(1)
        	return (
        		<div>
        			<h3>我是Home的内容</h3>
        			{/* 根据sum的值决定是否切换视图 */}
        			{sum === 1 ? <h4>sum的值为{sum}</h4> : <Navigate to="/about" replace={true}/>}
        			<button onClick={()=>setSum(2)}>点我将sum变为2</button>
        		</div>
        	)
        }
        ```

    ### 7. `<Outlet>` {#7-outlet-1}

    1.  当`<Route>`产生嵌套时，渲染其对应的后续子路由。

    2.  示例代码：

        ``` jsx
        //根据路由表生成对应的路由规则
        const element = useRoutes([
          {
            path:'/about',
            element:<About/>
          },
          {
            path:'/home',
            element:<Home/>,
            children:[
              {
                path:'news',
                element:<News/>
              },
              {
                path:'message',
                element:<Message/>,
              }
            ]
          }
        ])

        //Home.js
        import React from 'react'
        import {NavLink,Outlet} from 'react-router-dom'

        export default function Home() {
        	return (
        		<div>
        			<h2>Home组件内容</h2>
        			<div>
        				<ul className="nav nav-tabs">
        					<li>
        						<NavLink className="list-group-item" to="news">News</NavLink>
        					</li>
        					<li>
        						<NavLink className="list-group-item" to="message">Message</NavLink>
        					</li>
        				</ul>
        				{/* 指定路由组件呈现的位置 */}
        				<Outlet />
        			</div>
        		</div>
        	)
        }
        ```

    ## 3.Hooks {#3hooks-1}

    ### 1. useRoutes() {#1-useroutes-1}

    1.  作用：根据路由表，动态创建`<Routes>`和`<Route>`。

    2.  示例代码：

        ``` jsx
        //路由表配置：src/routes/index.js
        import About from '../pages/About'
        import Home from '../pages/Home'
        import {Navigate} from 'react-router-dom'

        export default [
        	{
        		path:'/about',
        		element:<About/>
        	},
        	{
        		path:'/home',
        		element:<Home/>
        	},
        	{
        		path:'/',
        		element:<Navigate to="/about"/>
        	}
        ]

        //App.jsx
        import React from 'react'
        import {NavLink,useRoutes} from 'react-router-dom'
        import routes from './routes'

        export default function App() {
        	//根据路由表生成对应的路由规则
        	const element = useRoutes(routes)
        	return (
        		<div>
        			......
              {/* 注册路由 */}
              {element}
        		  ......
        		</div>
        	)
        }
        ```

    ### 2. useNavigate() {#2-usenavigate-1}

    1.  作用：返回一个函数用来实现编程式导航。

    2.  示例代码：

        ``` jsx
        import React from 'react'
        import {useNavigate} from 'react-router-dom'

        export default function Demo() {
          const navigate = useNavigate()
          const handle = () => {
            //第一种使用方式：指定具体的路径
            navigate('/login', {
              replace: false,
              state: {a:1, b:2}
            }) 
            //第二种使用方式：传入数值进行前进或后退，类似于5.x中的 history.go()方法
            navigate(-1)
          }
          
          return (
            <div>
              <button onClick={handle}>按钮</button>
            </div>
          )
        }
        ```

    ### 3. useParams() {#3-useparams-1}

    1.  作用：回当前匹配路由的`params`参数，类似于5.x中的`match.params`。

    2.  示例代码：

        ``` jsx
        import React from 'react';
        import { Routes, Route, useParams } from 'react-router-dom';
        import User from './pages/User.jsx'

        function ProfilePage() {
          // 获取URL中携带过来的params参数
          let { id } = useParams();
        }

        function App() {
          return (
            <Routes>
              <Route path="users/:id" element={<User />}/>
            </Routes>
          );
        }
        ```

    ### 4. useSearchParams() {#4-usesearchparams-1}

    1.  作用：用于读取和修改当前位置的 URL 中的查询字符串。

    2.  返回一个包含两个值的数组，内容分别为：当前的seaech参数、更新search的函数。

    3.  示例代码：

        ``` jsx
        import React from 'react'
        import {useSearchParams} from 'react-router-dom'

        export default function Detail() {
        	const [search,setSearch] = useSearchParams()
        	const id = search.get('id')
        	const title = search.get('title')
        	const content = search.get('content')
        	return (
        		<ul>
        			<li>
        				<button onClick={()=>setSearch('id=008&title=哈哈&content=嘻嘻')}>点我更新一下收到的search参数</button>
        			</li>
        			<li>消息编号：{id}</li>
        			<li>消息标题：{title}</li>
        			<li>消息内容：{content}</li>
        		</ul>
        	)
        }
        ```

    ### 5. useLocation() {#5-uselocation-1}

    1.  作用：获取当前 location
        信息，对标5.x中的路由组件的`location`属性。

    2.  示例代码：

        ``` jsx
        import React from 'react'
        import {useLocation} from 'react-router-dom'

        export default function Detail() {
        	const x = useLocation()
        	console.log('@',x)
          // x就是location对象: 
        	/*
        		{
              hash: "",
              key: "ah9nv6sz",
              pathname: "/login",
              search: "?name=zs&age=18",
              state: {a: 1, b: 2}
            }
        	*/
        	return (
        		<ul>
        			<li>消息编号：{id}</li>
        			<li>消息标题：{title}</li>
        			<li>消息内容：{content}</li>
        		</ul>
        	)
        }

          

        ```

    ### 6. useMatch() {#6-usematch-1}

    1.  作用：返回当前匹配信息，对标5.x中的路由组件的`match`属性。

    2.  示例代码：

        ``` jsx
        <Route path="/login/:page/:pageSize" element={<Login />}/>
        <NavLink to="/login/1/10">登录</NavLink>

        export default function Login() {
          const match = useMatch('/login/:x/:y')
          console.log(match) //输出match对象
          //match对象内容如下：
          /*
          	{
              params: {x: '1', y: '10'}
              pathname: "/LoGin/1/10"  
              pathnameBase: "/LoGin/1/10"
              pattern: {
              	path: '/login/:x/:y', 
              	caseSensitive: false, 
              	end: false
              }
            }
          */
          return (
          	<div>
              <h1>Login</h1>
            </div>
          )
        }
        ```

    ### 7. useInRouterContext() {#7-useinroutercontext-1}

    作用：如果组件在 `<Router>` 的上下文中呈现，则 `useInRouterContext`
    钩子返回 true，否则返回 false。

    ### 8. useNavigationType() {#8-usenavigationtype-1}

    1.  作用：返回当前的导航类型（用户是如何来到当前页面的）。

    2.  返回值：`POP`、`PUSH`、`REPLACE`。

    3.  备注：`POP`是指在浏览器中直接打开了这个路由组件（刷新页面）。

    ### 9. useOutlet() {#9-useoutlet-1}

    1.  作用：用来呈现当前组件中渲染的嵌套路由。

    2.  示例代码：

        ``` jsx
        const result = useOutlet()
        console.log(result)
        // 如果嵌套路由没有挂载,则result为null
        // 如果嵌套路由已经挂载,则展示嵌套的路由对象
        ```

    ### 10.useResolvedPath() {#10useresolvedpath-1}

    1.  作用：给定一个 URL值，解析其中的：path、search、hash值。

# React Router 6

## 1.概述 {#1概述-2}

1.  React Router 以三个不同的包发布到 npm 上，它们分别为：

    1.  react-router: 路由的核心库，提供了很多的：组件、钩子。

    2.  `<strong style="color:#dd4d40">`{=html}**react-router-dom:**`</strong >`{=html}
        `<strong style="color:#dd4d40">`{=html}包含react-router所有内容，并添加一些专门用于
        DOM 的组件，例如 `<BrowserRouter>`等 `</strong>`{=html}。

    3.  react-router-native:
        包括react-router所有内容，并添加一些专门用于ReactNative的API，例如:`<NativeRouter>`等。

2.  与React Router 5.x 版本相比，改变了什么？

    1.  内置组件的变化：移除`<Switch/>` ，新增 `<Routes/>`等。

    2.  语法的变化：`component={About}` 变为 `element={<About/>}`等。

    3.  新增多个hook：`useParams`、`useNavigate`、`useMatch`等。

    4.  `<strong style="color:#dd4d40">`{=html}官方明确推荐函数式组件了！！！`</strong>`{=html}

        \...\...

## 2.Component {#2component-2}

### 1. `<BrowserRouter>` {#1-browserrouter-2}

1.  说明：`<BrowserRouter>`用于包裹整个应用。

2.  示例代码：

    ``` jsx
    import React from "react";
    import ReactDOM from "react-dom";
    import { BrowserRouter } from "react-router-dom";

    ReactDOM.render(
      <BrowserRouter>
        {/* 整体结构（通常为App组件） */}
      </BrowserRouter>,root
    );
    ```

### 2. `<HashRouter>` {#2-hashrouter-2}

1.  说明：作用与`<BrowserRouter>`一样，但`<HashRouter>`修改的是地址栏的hash值。

2.  备注：6.x版本中`<HashRouter>`、`<BrowserRouter>` 的用法与 5.x 相同。

### 3. `<Routes/> 与 <Route/>` {#3-routes-与-route-2}

1.  v6版本中移出了先前的`<Switch>`，引入了新的替代者：`<Routes>`。

2.  `<Routes>` 和
    `<Route>`要配合使用，且必须要用`<Routes>`包裹`<Route>`。

3.  `<Route>` 相当于一个 if 语句，如果其路径与当前 URL
    匹配，则呈现其对应的组件。

4.  `<Route caseSensitive>` 属性用于指定：匹配时是否区分大小写（默认为
    false）。

5.  当URL发生变化时，`<Routes>`都会查看其所有子`<Route>`
    元素以找到最佳匹配并呈现组件 。

6.  `<Route>` 也可以嵌套使用，且可配合`useRoutes()`配置 "路由表"
    ，但需要通过 `<Outlet>` 组件来渲染其子路由。

7.  示例代码：

    ``` jsx
    <Routes>
        /*path属性用于定义路径，element属性用于定义当前路径所对应的组件*/
        <Route path="/login" element={<Login />}></Route>

    		/*用于定义嵌套路由，home是一级路由，对应的路径/home*/
        <Route path="home" element={<Home />}>
           /*test1 和 test2 是二级路由,对应的路径是/home/test1 或 /home/test2*/
          <Route path="test1" element={<Test/>}></Route>
          <Route path="test2" element={<Test2/>}></Route>
    		</Route>
    	
    		//Route也可以不写element属性, 这时就是用于展示嵌套的路由 .所对应的路径是/users/xxx
        <Route path="users">
           <Route path="xxx" element={<Demo />} />
        </Route>
    </Routes>
    ```

### 4. `<Link>` {#4-link-2}

1.  作用: 修改URL，且不发送网络请求（路由链接）。

2.  注意: 外侧需要用`<BrowserRouter>`或`<HashRouter>`包裹。

3.  示例代码：

    ``` jsx
    import { Link } from "react-router-dom";

    function Test() {
      return (
        <div>
        	<Link to="/路径">按钮</Link>
        </div>
      );
    }
    ```

### 5. `<NavLink>` {#5-navlink-2}

1.  作用: 与`<Link>`组件类似，且可实现导航的"高亮"效果。

2.  示例代码：

    ``` jsx
    // 注意: NavLink默认类名是active，下面是指定自定义的class

    //自定义样式
    <NavLink
        to="login"
        className={({ isActive }) => {
            console.log('home', isActive)
            return isActive ? 'base one' : 'base'
        }}
    >login</NavLink>

    /*
    	默认情况下，当Home的子组件匹配成功，Home的导航也会高亮，
    	当NavLink上添加了end属性后，若Home的子组件匹配成功，则Home的导航没有高亮效果。
    */
    <NavLink to="home" end >home</NavLink>
    ```

### 6. `<Navigate>` {#6-navigate-2}

1.  作用：只要`<Navigate>`组件被渲染，就会修改路径，切换视图。

2.  `replace`属性用于控制跳转模式（push 或 replace，默认是push）。

3.  示例代码：

    ``` jsx
    import React,{useState} from 'react'
    import {Navigate} from 'react-router-dom'

    export default function Home() {
    	const [sum,setSum] = useState(1)
    	return (
    		<div>
    			<h3>我是Home的内容</h3>
    			{/* 根据sum的值决定是否切换视图 */}
    			{sum === 1 ? <h4>sum的值为{sum}</h4> : <Navigate to="/about" replace={true}/>}
    			<button onClick={()=>setSum(2)}>点我将sum变为2</button>
    		</div>
    	)
    }
    ```

### 7. `<Outlet>` {#7-outlet-2}

1.  当`<Route>`产生嵌套时，渲染其对应的后续子路由。

2.  示例代码：

    ``` jsx
    //根据路由表生成对应的路由规则
    const element = useRoutes([
      {
        path:'/about',
        element:<About/>
      },
      {
        path:'/home',
        element:<Home/>,
        children:[
          {
            path:'news',
            element:<News/>
          },
          {
            path:'message',
            element:<Message/>,
          }
        ]
      }
    ])

    //Home.js
    import React from 'react'
    import {NavLink,Outlet} from 'react-router-dom'

    export default function Home() {
    	return (
    		<div>
    			<h2>Home组件内容</h2>
    			<div>
    				<ul className="nav nav-tabs">
    					<li>
    						<NavLink className="list-group-item" to="news">News</NavLink>
    					</li>
    					<li>
    						<NavLink className="list-group-item" to="message">Message</NavLink>
    					</li>
    				</ul>
    				{/* 指定路由组件呈现的位置 */}
    				<Outlet />
    			</div>
    		</div>
    	)
    }
    ```

## 3.Hooks {#3hooks-2}

### 1. useRoutes() {#1-useroutes-2}

1.  作用：根据路由表，动态创建`<Routes>`和`<Route>`。

2.  示例代码：

    ``` jsx
    //路由表配置：src/routes/index.js
    import About from '../pages/About'
    import Home from '../pages/Home'
    import {Navigate} from 'react-router-dom'

    export default [
    	{
    		path:'/about',
    		element:<About/>
    	},
    	{
    		path:'/home',
    		element:<Home/>
    	},
    	{
    		path:'/',
    		element:<Navigate to="/about"/>
    	}
    ]

    //App.jsx
    import React from 'react'
    import {NavLink,useRoutes} from 'react-router-dom'
    import routes from './routes'

    export default function App() {
    	//根据路由表生成对应的路由规则
    	const element = useRoutes(routes)
    	return (
    		<div>
    			......
          {/* 注册路由 */}
          {element}
    		  ......
    		</div>
    	)
    }
    ```

### 2. useNavigate() {#2-usenavigate-2}

1.  作用：返回一个函数用来实现编程式导航。

2.  示例代码：

    ``` jsx
    import React from 'react'
    import {useNavigate} from 'react-router-dom'

    export default function Demo() {
      const navigate = useNavigate()
      const handle = () => {
        //第一种使用方式：指定具体的路径
        navigate('/login', {
          replace: false,
          state: {a:1, b:2}
        }) 
        //第二种使用方式：传入数值进行前进或后退，类似于5.x中的 history.go()方法
        navigate(-1)
      }
      
      return (
        <div>
          <button onClick={handle}>按钮</button>
        </div>
      )
    }
    ```

### 3. useParams() {#3-useparams-2}

1.  作用：回当前匹配路由的`params`参数，类似于5.x中的`match.params`。

2.  示例代码：

    ``` jsx
    import React from 'react';
    import { Routes, Route, useParams } from 'react-router-dom';
    import User from './pages/User.jsx'

    function ProfilePage() {
      // 获取URL中携带过来的params参数
      let { id } = useParams();
    }

    function App() {
      return (
        <Routes>
          <Route path="users/:id" element={<User />}/>
        </Routes>
      );
    }
    ```

### 4. useSearchParams() {#4-usesearchparams-2}

1.  作用：用于读取和修改当前位置的 URL 中的查询字符串。

2.  返回一个包含两个值的数组，内容分别为：当前的seaech参数、更新search的函数。

3.  示例代码：

    ``` jsx
    import React from 'react'
    import {useSearchParams} from 'react-router-dom'

    export default function Detail() {
    	const [search,setSearch] = useSearchParams()
    	const id = search.get('id')
    	const title = search.get('title')
    	const content = search.get('content')
    	return (
    		<ul>
    			<li>
    				<button onClick={()=>setSearch('id=008&title=哈哈&content=嘻嘻')}>点我更新一下收到的search参数</button>
    			</li>
    			<li>消息编号：{id}</li>
    			<li>消息标题：{title}</li>
    			<li>消息内容：{content}</li>
    		</ul>
    	)
    }
    ```

### 5. useLocation() {#5-uselocation-2}

1.  作用：获取当前 location 信息，对标5.x中的路由组件的`location`属性。

2.  示例代码：

    ``` jsx
    import React from 'react'
    import {useLocation} from 'react-router-dom'

    export default function Detail() {
    	const x = useLocation()
    	console.log('@',x)
      // x就是location对象: 
    	/*
    		{
          hash: "",
          key: "ah9nv6sz",
          pathname: "/login",
          search: "?name=zs&age=18",
          state: {a: 1, b: 2}
        }
    	*/
    	return (
    		<ul>
    			<li>消息编号：{id}</li>
    			<li>消息标题：{title}</li>
    			<li>消息内容：{content}</li>
    		</ul>
    	)
    }

      

    ```

### 6. useMatch() {#6-usematch-2}

1.  作用：返回当前匹配信息，对标5.x中的路由组件的`match`属性。

2.  示例代码：

    ``` jsx
    <Route path="/login/:page/:pageSize" element={<Login />}/>
    <NavLink to="/login/1/10">登录</NavLink>

    export default function Login() {
      const match = useMatch('/login/:x/:y')
      console.log(match) //输出match对象
      //match对象内容如下：
      /*
      	{
          params: {x: '1', y: '10'}
          pathname: "/LoGin/1/10"  
          pathnameBase: "/LoGin/1/10"
          pattern: {
          	path: '/login/:x/:y', 
          	caseSensitive: false, 
          	end: false
          }
        }
      */
      return (
      	<div>
          <h1>Login</h1>
        </div>
      )
    }
    ```

### 7. useInRouterContext() {#7-useinroutercontext-2}

作用：如果组件在 `<Router>` 的上下文中呈现，则 `useInRouterContext`
钩子返回 true，否则返回 false。

### 8. useNavigationType() {#8-usenavigationtype-2}

1.  作用：返回当前的导航类型（用户是如何来到当前页面的）。

2.  返回值：`POP`、`PUSH`、`REPLACE`。

3.  备注：`POP`是指在浏览器中直接打开了这个路由组件（刷新页面）。

### 9. useOutlet() {#9-useoutlet-2}

1.  作用：用来呈现当前组件中渲染的嵌套路由。

2.  示例代码：

    ``` jsx
    const result = useOutlet()
    console.log(result)
    // 如果嵌套路由没有挂载,则result为null
    // 如果嵌套路由已经挂载,则展示嵌套的路由对象
    ```

### 10.useResolvedPath() {#10useresolvedpath-2}

1.  作用：给定一个 URL值，解析其中的：path、search、hash值。

------------------------------------------------------------------------

# React \* {#react-}

### 原理图

![](https://s3.bmp.ovh/imgs/2022/04/21/173d31b39cbb34ed.png)

![](https://s3.bmp.ovh/imgs/2022/04/21/26a7eb530db1e19f.png)

![](https://s3.bmp.ovh/imgs/2022/04/21/8efbb09cdc6ae0d3.png)

![](https://s3.bmp.ovh/imgs/2022/04/21/e5013e7b9d698c7f.png)

## 1. setState {#1-setstate}

### setState更新状态的2种写法

``` jsx
	(1). setState(stateChange, [callback])------对象式的setState
            1.stateChange为状态改变对象(该对象可以体现出状态的更改)
            2.callback是可选的回调函数, 它在状态更新完毕、界面也更新后(render调用后)才被调用
					
	(2). setState(updater, [callback])------函数式的setState
            1.updater为返回stateChange对象的函数。
            2.updater可以接收到state和props。
            4.callback是可选的回调函数, 它在状态更新、界面也更新后(render调用后)才被调用。
总结:
		1.对象式的setState是函数式的setState的简写方式(语法糖)
		2.使用原则：
				(1).如果新状态不依赖于原状态 ===> 使用对象方式
				(2).如果新状态依赖于原状态 ===> 使用函数方式
				(3).如果需要在setState()执行后获取最新的状态数据, 
					要在第二个callback函数中读取
```

jsx

------------------------------------------------------------------------

## 2. lazyLoad {#2-lazyload}

### 路由组件的lazyLoad

``` javascript
	//1.通过React的lazy函数配合import()函数动态加载路由组件 ===> 路由组件代码会被分开打包
	const Login = lazy(()=>import('@/pages/Login'))
	
	//2.通过<Suspense>指定在加载得到路由打包文件前显示一个自定义loading界面
	<Suspense fallback={<h1>loading.....</h1>}>
        <Switch>
            <Route path="/xxx" component={Xxxx}/>
            <Redirect to="/login"/>
        </Switch>
    </Suspense>
```

------------------------------------------------------------------------

## 3. Hooks {#3-hooks}

#### 1. React Hook/Hooks是什么? {#1-react-hookhooks是什么}

``` jsx
(1). Hook是React 16.8.0版本增加的新特性/新语法
(2). 可以让你在函数组件中使用 state 以及其他的 React 特性
```

#### 2. 三个常用的Hook {#2-三个常用的hook}

``` jsx
(1). State Hook: React.useState()
(2). Effect Hook: React.useEffect()
(3). Ref Hook: React.useRef()
```

#### 3. State Hook {#3-state-hook}

``` jsx
(1). State Hook让函数组件也可以有state状态, 并进行状态数据的读写操作
(2). 语法: const [xxx, setXxx] = React.useState(initValue)  
(3). useState()说明:
        参数: 第一次初始化指定的值在内部作缓存
        返回值: 包含2个元素的数组, 第1个为内部当前状态值, 第2个为更新状态值的函数
(4). setXxx()2种写法:
        setXxx(newValue): 参数为非函数值, 直接指定新的状态值, 内部用其覆盖原来的状态值
        setXxx(value => newValue): 参数为函数, 接收原本的状态值, 返回新的状态值, 内部用其覆盖原来的状态值
```

#### 4. Effect Hook {#4-effect-hook}

``` jsx
(1). Effect Hook 可以让你在函数组件中执行副作用操作(用于模拟类组件中的生命周期钩子)
(2). React中的副作用操作:
        发ajax请求数据获取
        设置订阅 / 启动定时器
        手动更改真实DOM
(3). 语法和说明: 
        useEffect(() => { 
          // 在此可以执行任何带副作用操作
          return () => { // 在组件卸载前执行
            // 在此做一些收尾工作, 比如清除定时器/取消订阅等
          }
        }, [stateValue]) // 如果指定的是[], 回调函数只会在第一次render()后执行
    
(4). 可以把 useEffect Hook 看做如下三个函数的组合
        componentDidMount()
        componentDidUpdate()
    	componentWillUnmount() 
```

#### 5. Ref Hook {#5-ref-hook}

``` jsx
(1). Ref Hook可以在函数组件中存储/查找组件内的标签或任意其它数据
(2). 语法: const refContainer = useRef()
(3). 作用:保存标签对象,功能与React.createRef()一样
```

------------------------------------------------------------------------

## 4. Fragment {#4-fragment}

### 使用 {#使用-1}

``` jsx
<Fragment><Fragment>  
```

### 作用

> 可以不用必须有一个真实的DOM根标签了

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><hr /></body></html>
```
## 5. Context {#5-context}

### 理解 {#理解-1}

> 一种组件间通信方式, 常用于【祖组件】与【后代组件】间通信

### 使用 {#使用-2}

``` javascript
1) 创建Context容器对象：
	const XxxContext = React.createContext()  
	
2) 渲染子组时，外面包裹xxxContext.Provider, 通过value属性给后代组件传递数据：
	<xxxContext.Provider value={数据}>
		子组件
    </xxxContext.Provider>
    
3) 后代组件读取数据：

	//第一种方式:仅适用于类组件 
	  static contextType = xxxContext  // 声明接收context
	  this.context // 读取context中的value数据
	  
	//第二种方式: 函数组件与类组件都可以
	  <xxxContext.Consumer>
	    {
	      value => ( // value就是context中的value数据
	        要显示的内容
	      )
	    }
	  </xxxContext.Consumer>
```

### 注意

``` 
在应用开发中一般不用context, 一般都用它的封装react插件
```

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><hr /></body></html>
```
## 6. 组件优化 {#6-组件优化}

### Component的2个问题 

> 1.  只要执行setState(),即使不改变状态数据, 组件也会重新render() ==>
>     效率低
>
> 2.  只当前组件重新render(),
>     就会自动重新render子组件，纵使子组件没有用到父组件的任何数据 ==>
>     效率低

### 效率高的做法

> 只有当组件的state或props数据发生改变时才重新render()

### 原因

> Component中的shouldComponentUpdate()总是返回true

### 解决

``` jsx
办法1: 
	重写shouldComponentUpdate()方法
	比较新旧state或props数据, 如果有变化才返回true, 如果没有返回false
办法2:  
	使用PureComponent
	PureComponent重写了shouldComponentUpdate(), 只有state或props数据有变化才返回true
	注意: 
		只是进行state和props数据的浅比较, 如果只是数据对象内部数据变了, 返回false  
		不要直接修改state数据, 而是要产生新数据
项目中一般使用PureComponent来优化
```

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><hr /></body></html>
```
## 7. render props {#7-render-props}

### 如何向组件内部动态传入带内容的结构(标签)?

``` jsx
Vue中: 
	使用slot技术, 也就是通过组件标签体传入结构  <A><B/></A>
React中:
	使用children props: 通过组件标签体传入结构
	使用render props: 通过组件标签属性传入结构,而且可以携带数据，一般用render函数属性
```

### children props

``` jsx
<A>
  <B>xxxx</B>
</A>
{this.props.children}
问题: 如果B组件需要A组件内的数据, ==> 做不到 
```

### render props {#render-props}

``` jsx
<A render={(data) => <C data={data}></C>}></A>
A组件: {this.props.render(内部state数据)}
C组件: 读取A组件传入的数据显示 {this.props.data} 
```

```{=html}
<html xmlns="http://www.w3.org/1999/xhtml"><head></head><body><hr /></body></html>
```
## 8. 错误边界 {#8-错误边界}

#### 理解： {#理解-2}

错误边界(Error boundary)：用来捕获后代组件错误，渲染出备用页面

#### 特点：

只能捕获后代组件生命周期产生的错误，不能捕获自己组件产生的错误和其他组件在合成事件、定时器中产生的错误

##### 使用方式：

getDerivedStateFromError配合componentDidCatch

``` javascript
// 生命周期函数，一旦后台组件报错，就会触发
static getDerivedStateFromError(error) {
    console.log(error);
    // 在render之前触发
    // 返回新的state
    return {
        hasError: true,
    };
}

componentDidCatch(error, info) {
    // 统计页面的错误。发送请求发送到后台去
    console.log(error, info);
}
```

## 9. 组件通信方式总结 {#9-组件通信方式总结}

#### 组件间的关系：

-   父子组件

-   兄弟组件（非嵌套组件）

-   祖孙组件（跨级组件）

#### 几种通信方式：

``` 
	1.props：
		(1).children props
		(2).render props
	2.消息订阅-发布：
		pubs-sub、event等等
	3.集中式管理：
		redux、dva等等
	4.conText:
		生产者-消费者模式
```

#### 比较好的搭配方式：

``` 
	父子组件：props
	兄弟组件：消息订阅-发布、集中式管理
	祖孙组件(跨级组件)：消息订阅-发布、集中式管理、conText(开发用的少，封装插件用的多)
```

# Mysql

### 01.查询 {#01查询}

``` mysql
1.查询语句所有数据:
	select * from 表名;
2.查询指定数据:
	select * from 表名 where 字段名 = '值';   (and / or)
3.关键字查询/模糊查询:
	select * from 表名 where 字段名 like "%值%" or 字段名 like "%值%";
4.倒叙查询
	select *  from 表名  order by 字段名 desc ;
5.关键字查询 + 倒叙查询
	顺序:  select--from--where--group by--having--order by
  	select *  from 表名  where 字段名 like "%值%" order by 字段名 desc;
6.分页
 select *  from 表名  limit (pageNo)-1）*pageSize,pageSize   pageNo:当前页码  pageSize:每页展示的条数
 `select * from Tong order by Tid desc limit ${(pageOn-1) * pageCount}, ${pageCount}`; //order by 字段名 desc;
```

### 02.插入 {#02插入}

``` mysql
1.插入多个内容:
	insert into 表名(字段1,字段2,字段3) values("值1","值2","值3");
```

### 03.修改 {#03修改}

``` mysql
1.修改内容:
	update 表名 set 字段名1 = "值1",字段名2 = "值2", where 字段名 = "值";
	
```

### 04.删除 {#04删除}

``` mysql
1.删除所有内容:
	delete from 表名;
2.删除指定内容:
	delete from 表名 where 字段名 = "值";
```

### 05.分页查询 {#05分页查询}

``` javascript
1. 	select * from 表名 limit  2,3     
	2: 表示第几页    3:表示每页显示的数量
2.	总页数计算
SELECT COUNT(*) FROM 表名;     获得数据总条数
SELECT CEIL(COUNT(*) / 10) AS pageTotal FROM 表名;        假设每页显示10条，则直接进行除法运算，然后向上取整
3.select * from articles order by artId desc limit 6  查询最新发布的6条数据
```

# *tool*

### 1.页面禁止复制和右键禁用功能 {#1页面禁止复制和右键禁用功能}

``` javascript
<body onmousemove=/HideMenu()/ oncontextmenu="return false" ondragstart="return false" onselectstart ="return false" onselect="document.selection.empty()" oncopy="document.selection.empty()" onbeforecopy="return false" onmouseup="document.selection.empty()">
```

### 2.页面禁止复制 {#2页面禁止复制}

``` javascript
1.<body οncοpy="aa();return false;">
2.<script type="text/javascript">
			function aa(){
				layer.msg('禁止复制!', {
				    time: 2000, //2s后自动关闭
				    area: ['300px', '150px']//宽高
				});
			};
			
//			方式二:js中加入这两行代码,使右键和复制失效.
			document.οncοntextmenu=new Function("event.returnValue=false"); 
			document.onselectstart=new Function("event.returnValue=false"); 
		</script>

<link rel="icon" href="images/icon.ico" title="" type="" />
<title>2021-Web</title>
```

### 3.上传码云并发布部署静态网站 {#3上传码云并发布部署静态网站}

-   如果是第一次利用git提交，请配置好全局选项

    ``` 
    git config --global user.name "用户名"
    git config --global user.email "你的邮箱地址"
    ```

-   初始化仓库

    ``` 
    git init
    ```

-   把本地文件放到暂存区

    ``` 
    git add .
    ```

-   把本地文件放到本地仓库里面

    ``` 
    git commit -m '自定义名称'
    ```

-   链接远程仓库

    ``` 
    git remote add origin 你新建的仓库地址
    ```

-   把本地仓库的文件推送到远程仓库 push

    ``` 
    git push -u origin master
    ```

### 4.npm安装任何包都报错的解决办法 {#4npm安装任何包都报错的解决办法}

``` csharp
解决办法：

1、执行：

npm config get proxy
npm config get https-proxy
如果返回值不为null，继续执行：
（这一步很重要，一定要保证两个命令的返回值都为null,话说回来，应该出现这个错误这两个返回值有不为null的）
npm config set proxy null
npm config set https-proxy null
2、执行：
npm config set registry http://registry.cnpmjs.org/
```

### 5.时间转化为多少秒 {#5时间转化为多少秒}

-   #### 兼容所有设备

``` javascript
export default function(data) {
  var str = data.replace(/-/g,"/");
  //将字符串转换成时间格式
  var timePublish = new Date(str);
  var timeNow = new Date();
  var minute = 1000 * 60;
  var hour = minute * 60;
  var day = hour * 24;
  var month = day * 30;
  var year = month * 12;
  var diffValue = timeNow - timePublish;
  var diffMonth = diffValue / month;
  var diffWeek = diffValue / (7 * day);
  var diffDay = diffValue / day;
  var diffHour = diffValue / hour;
  var diffMinute = diffValue / minute;
  var diffYear = diffValue / year;
  let result=""
  if (diffValue < 0) {
    result = "刚刚发表";
  } else if (diffYear > 1) {
    result = parseInt(diffYear) + "年前";
  } else if (diffMonth > 1) {
    result = parseInt(diffMonth) + "月前";
  } else if (diffWeek > 1) {
    result = parseInt(diffWeek) + "周前";
  } else if (diffDay > 1) {
    result = parseInt(diffDay) + "天前";
  } else if (diffHour > 1) {
    result = parseInt(diffHour) + "小时前";
  } else if (diffMinute > 1) {
    result = parseInt(diffMinute) + "分钟前";
  } else {
    result = "刚刚";
  }
  return result;
}
```

-   #### ios不兼容

``` javascript
export default function getTimeBefore(hisTime, nowTime) {
  if (!arguments.length) return "";
  var arg = arguments,
    now = arg[1] ? arg[1] : new Date().getTime(),
    diffValue = now - arg[0],
    result = "",
    minute = 1000 * 60,
    hour = minute * 60,
    day = hour * 24,
    halfamonth = day * 15,
    month = day * 30,
    year = month * 12,
    _year = diffValue / year,
    _month = diffValue / month,
    _week = diffValue / (7 * day),
    _day = diffValue / day,
    _hour = diffValue / hour,
    _min = diffValue / minute;

  if (_year >= 1) result = parseInt(_year) + "年前";
  else if (_month >= 1) result = parseInt(_month) + "个月前";
  else if (_week >= 1) result = parseInt(_week) + "周前";
  else if (_day >= 1) result = parseInt(_day) + "天前";
  else if (_hour >= 1) result = parseInt(_hour) + "小时前";
  else if (_min >= 1) result = parseInt(_min) + "分钟前";
  else result = "刚刚";
  return result;
}
```

### 6.时间转化 {#6时间转化}

``` javascript
function getTime() {
  var now = new Date();
  var year = now.getFullYear(); //得到年份
  var month = now.getMonth(); //得到月份
  var date = now.getDate(); //得到日期
  //   var day = now.getDay();//得到周几
  var hour = now.getHours(); //得到小时
  var minu = now.getMinutes(); //得到分钟
  var sec = now.getSeconds(); //得到秒
  month = month + 1;
  if (month < 10) month = "0" + month;
  if (date < 10) date = "0" + date;
  if (hour < 10) hour = "0" + hour;
  if (minu < 10) minu = "0" + minu;
  if (sec < 10) sec = "0" + sec;
  //   var time = "";
  //精确到天
  // console.log(time = year + "-" + month + "-" + date);
  //精确到分
  return year + "-" + month + "-" + date + " " + hour + ":" + minu + ":" + sec;
  // console.log(year + "-" + month + "-" + date+ " " + hour + ":" + minu);
}

export default getTime;
```

### 7.获取访问者城市的位置 {#7获取访问者城市的位置}

``` javascript
export function getCity() {
    return new Promise((resolve, reject) => {
        const geolocation = new BMap.Geolocation();
        geolocation.getCurrentPosition(
            function getinfo(position) {
                let city = position.address.city; //获取城市信息
                let province = position.address.province; //获取省份信息
                resolve({ province, city });
            },
            function (e) {
                // _this.LocationCity = "定位失败";
            },
            { provider: "baidu" }
        );
    });
}
```

### 8.获取访问者的ip {#8获取访问者的ip}

``` javascript
//1.命名为 getuserIp.js
export function GetCurrentBrowser () {
    let ua = navigator.userAgent.toLocaleLowerCase()
    let browserType = null
    if (ua.match(/msie/) != null || ua.match(/trident/) != null) {
        browserType = 'IE'
    } else if (ua.match(/firefox/) != null) {
        browserType = 'firefox'
    } else if (ua.match(/ucbrowser/) != null) {
        browserType = 'UC'
    } else if (ua.match(/opera/) != null || ua.match(/opr/) != null) {
        browserType = 'opera'
    } else if (ua.match(/bidubrowser/) != null) {
        browserType = 'baidu'
    } else if (ua.match(/metasr/) != null) {
        browserType = 'sougou'
    } else if (ua.match(/tencenttraveler/) != null || ua.match(/qqbrowse/) != null) {
        browserType = 'QQ'
    } else if (ua.match(/maxthon/) != null) {
        browserType = 'maxthon'
    } else if (ua.match(/chrome/) != null) {
        var is360 = _mime('type', 'application/vnd.chromium.remoting-viewer')
        if (is360) {
            browserType = '360'
        } else {
            browserType = 'chrome'
        }
    } else if (ua.match(/safari/) != null) {
        browserType = 'Safari'
    } else {
        browserType = 'others'
    }
    return browserType
}

function _mime (option, value) {
    var mimeTypes = navigator.mimeTypes
    for (var mt in mimeTypes) {
        if (mimeTypes[mt][option] === value) {
            return true
        }
    }
    return false
}

//2.命令为 getCity.js
export function GetOs () {
    let sUserAgent = navigator.userAgent.toLocaleLowerCase()
    let isWin = (navigator.platform === 'win32') || (navigator.platform === 'Windows')
    let isMac = (navigator.platform === 'Mac68k') || (navigator.platform === 'Macppc') || (navigator.platform === 'macintosh') || (navigator.platform === 'macintel')
    if (isMac) return 'Mac'
    var isUnix = (navigator.platform === 'x11') && !isWin && !isMac
    if (isUnix) return 'Unix'
    var isLinux = (String(navigator.platform).indexOf('linux') > -1)
    if (isLinux) return 'Linux'
    if (isWin) {
        var isWin2K = sUserAgent.indexOf('windows nt 5.0') > -1 || sUserAgent.indexOf('windows 2000') > -1
        if (isWin2K) return 'Win2000'
        var isWinXP = sUserAgent.indexOf('windows nt 5.1') > -1 || sUserAgent.indexOf('windows xp') > -1
        if (isWinXP) return 'WinXP'
        var isWin2003 = sUserAgent.indexOf('windows nt 5.2') > -1 || sUserAgent.indexOf('windows 2003') > -1
        if (isWin2003) return 'Win2003'
        var isWinVista = sUserAgent.indexOf('windows nt 6.0') > -1 || sUserAgent.indexOf('windows vista') > -1
        if (isWinVista) return 'WinVista'
        var isWin7 = sUserAgent.indexOf('windows nt 6.1') > -1 || sUserAgent.indexOf('windows 7') > -1
        if (isWin7) return 'Win7'
    }
    if (sUserAgent.indexOf('android') > -1) return 'Android'
    if (sUserAgent.indexOf('iphone') > -1) return 'iPhone'
    if (sUserAgent.indexOf('symbianos') > -1) return 'SymbianOS'
    if (sUserAgent.indexOf('windows') > -1) return 'Windows'
    if (sUserAgent.indexOf('ipad') > -1) return 'iPad'
    if (sUserAgent.indexOf('ipod') > -1) return 'iPod'
}




//3.在html中引用
<script src="https://pv.sohu.com/cityjson?ie=utf-8"></script>
<script type="text/javascript" src="https://api.map.baidu.com/api?v=2.0&ak=klXrECs3iPRi719fy2IFBImWTjSaaGtn"></script>
<script type="text/javascript">
    sessionStorage.setItem('ip', returnCitySN["cip"])
sessionStorage.setItem('area', returnCitySN["cname"])
</script>



//4.在main.js中引用.
//引入统计信息
import * as sysTool from "@/assets/js/getuserIp.js";
import { getCity } from "@/assets/js/getCity.js";
import debounce from "lodash/debounce.js";
import getTime from "@/assets/js/getTime";



//5.在全局路由守卫之前
let resObj;
let userId;
let getIpOrCity = debounce(function (){
    submitStatistics(resObj)
},8000)



//6.在路由守卫中
//获取用户的ip，所在位置
let tongInfo = sessionStorage.getItem("STATICSTICS");
if (tongInfo) {
    //判断用户是否进行登录，并给予身份
    let isUserId = localStorage.getItem("USERID");
    let userStatus = "";
    isUserId ? (userStatus = "user") : (userStatus = "guest");
    isUserId ? (userId = isUserId) : (userId = "-");

    if (tongInfo) {
        resObj = Object.assign(
            JSON.parse(tongInfo),
            { Tcontent: to.meta.title },
            { Tdate: getTime() },
            { userStatus: userStatus },
            { userId: userId }
        );
        if (userId != "3") {
            getIpOrCity();
        }
    }
} else {
    sysTool.GetCurrentBrowser();
    sysTool.GetOs();
    getCity().then((res) => {
        let cityAll = res.province + " · " + res.city;
        let objs = {
            Tip: returnCitySN["cip"],    //获取ip
            Tos: sysTool.GetOs(),      //操作系统获取
            Tbrowser: sysTool.GetCurrentBrowser(),  //获取访问的方式(浏览器)
            Tcity: cityAll,     //获取省份和城市
        };
        // localStorage.setItem("POSITION", cityAll);
        sessionStorage.setItem("STATICSTICS", JSON.stringify(objs));
    });
}
```

### 9.文本溢出 {#9文本溢出}

``` css
1.单行
overflow: hidden;            // 溢出隐藏
text-overflow: ellipsis;      // 溢出用省略号显示
white-space: nowrap;         // 规定段落中的文本不进行换行

2.多行
overflow: hidden;            // 溢出隐藏
text-overflow: ellipsis;     // 溢出用省略号显示
display: -webkit-box;         // 作为弹性伸缩盒子模型显示。
-webkit-box-orient: vertical; // 设置伸缩盒子的子元素排列方式：从上到下垂直排列
-webkit-line-clamp: 3;        // 显示的行数
```

### 10.单一图片上传 {#10单一图片上传}

``` javascript
const uploadRouter = require("express").Router();
const multer = require("multer");

const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, './public/static')
  },
  filename: function (req, file, cb) {
    const uniqueSuffix = Date.now() + Math.round(Math.random() * 1E9)
    cb(null, file.fieldname +''+ uniqueSuffix+"."+file.originalname.split(".")[1])
  }
})

const upload = multer({ storage: storage })


uploadRouter.post("/classManger/uploadImage",upload.single("file"),(req,res)=>{  //Miraitowa
  // console.log(req.file);
 let {filename,size,mimetype,originalname}  =req.file
 let fileType = ["jpg","jpeg","webp","png","gif"] 
   if(size>5000000) return res.send({code:400,msg:"图片上传失败:图片过大,请重新上传"})
 if(fileType.indexOf(mimetype.split("/")[1]) == -1) return res.send({code:401,msg:"图片上传失败:文件类型错误,请重新上传"})
 let path = `/public/static/${filename}`
   res.send({code:200,msg:"图片上传成功",tem_path:path,url:"http://localhost:3333"+path})
 
})

module.exports = uploadRouter

```

### 11.多张图片上传 {#11多张图片上传}

``` javascript
floorInfoImgRouter.post('/wb/uploadFloorInfoMany', upload.array('wb', 12), function (req, res) {
  let {floorId,others} = req.body
  let imgList;
  let imgListPath;
  imgListPath = req.files.map(item=>{
    return `/static/wb/images/${item.filename}`
  })
  imgList = req.files.map(item=>{
    return `http://localhost:3000/static/wb/images/${item.filename}`
  })
  for(let i=0;i<imgList.length;i++){
    // console.log(floorId,imgListPath,imgList);
    let sql = `insert into uploadimg(floorId,path,urls,others) values("${floorId}","${imgListPath[i]}","${imgList[i]}","${others}")`
    getQuery(sql,(result)=>{})
  }
  res.send({code:200,msg:"图片上传成功",imgListPath,imgList})
  
})
```

# api接口

### 1.开放接口 {#1开放接口}

``` 
目前接口列表：
新实时段子
https://api.apiopen.top/getJoke?page=1&count=2&type=video

通过Id查段子
https://api.apiopen.top/getSingleJoke?sid=28654780

快递查询：
https://api.apiopen.top/EmailSearch?number=1012002

随机单句诗词推荐：
https://api.apiopen.top/singlePoetry

随机一首诗词推荐：
https://api.apiopen.top/recommendPoetry

搜索古诗词：
https://api.apiopen.top/searchPoetry?name=古风二首%20二

搜索古诗词作者：
https://api.apiopen.top/searchAuthors?name=李白

模糊搜索古诗词（可搜索诗词名、诗词内容、诗词作者）：
https://api.apiopen.top/likePoetry?name=李白

获取宋朝古诗词：
https://api.apiopen.top/getSongPoetry?page=1&count=20

获取唐朝古诗词：
https://api.apiopen.top/getTangPoetry?page=1&count=20

音乐搜索接口：
https://api.apiopen.top/searchMusic?name=不要说话

音乐电台接口：
https://api.apiopen.top/musicBroadcasting

音乐电台详情接口：
https://api.apiopen.top/musicBroadcastingDetails?channelname=public_tuijian_spring

音乐详情接口：
https://api.apiopen.top/musicDetails?id=604392760

音乐排行榜接口：
https://api.apiopen.top/musicRankings

音乐排行榜详情接口：
https://api.apiopen.top/musicRankingsDetails?type=1

每日视频推荐接口：
https://api.apiopen.top/todayVideo

视频大纲获取接口：
https://api.apiopen.top/videoHomeTab

视频分类推荐接口：
https://api.apiopen.top/videoCategory

视频分类推荐接口：
https://api.apiopen.top/videoCategoryDetails?id=14

根据ID推荐接口：
https://api.apiopen.top/videoRecommend?id=127398

新闻接口：
https://www.apiopen.top/journalismApi

随机推荐热门段子（包含文字、图片、GIF、视频）：
https://www.apiopen.top/satinApi?type=1&page=1

随机推荐热门段子【神评版本】（包含文字、图片、GIF、视频）：
https://www.apiopen.top/satinGodApi?type=1&page=1

随机推荐热门段子【神评版本】评论列表：
https://www.apiopen.top/satinCommentApi?id=27610708&page=1

热门小说推荐列表
https://www.apiopen.top/novelApi

小说搜索接口
https://www.apiopen.top/novelSearchApi?name=盗墓笔记

小说详情接口
https://www.apiopen.top/novelInfoApi?name=盗墓笔记

天气获取接口
https://www.apiopen.top/weatherApi?city=成都

美图获取接口
https://www.apiopen.top/meituApi?page=1

个性网名获取接口
https://www.apiopen.top/femaleNameApi?page=1

创建应用接口
https://www.apiopen.top/createUserKey?appId=com.chat.peakchao&passwd=123456

增加统计信息接口
https://www.apiopen.top/addStatistics?appKey=00d91e8e0cca2b76f515926a36db68f5&type=点击统计&typeId=1&count=2

查询统计信息接口
https://www.apiopen.top/findStatistics?appKey=00d91e8e0cca2b76f515926a36db68f5

用户注册接口
https://www.apiopen.top/createUser?key=00d91e8e0cca2b76f515926a36db68f5&phone=13594347817&passwd=123654

用户登陆接口
https://www.apiopen.top/login?key=00d91e8e0cca2b76f515926a36db68f5&phone=13594347817&passwd=123456
————————————————
版权声明：本文为CSDN博主「peakchao」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/c__chao/article/details/78573737
```

# 代码片段

### 01.wxRouter部分代码 {#01wxrouter部分代码}

``` javascript
const express = require("express");
const wxRouter = express.Router();
const getQuery = require("../util/wxMysql");
const selfMail = require("../util/selfMail");
const sendMailer = require("../util/mail"); 
const getQueryFaxian = require("../util/faxianMysql")
const getQueryEndLogin = require("../util/endLogin")
const jwt = require("jsonwebtoken")
var codes = {};
var token;

// //接口重修
// apidoc -i ./ -o ../hehe/





/**
 * @api {post} /wx/user/endLogin 小程序后台登录(后台)  
 * @apiName   endLogin 小程序后台登录(后台)
 * @apiGroup H小程序(后台)
 *
 * @apiParam {String} user  账号
 * @apiParam {String} psd  密码

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */

wxRouter.post("/endLogin",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    let {user,psd} = req.body;
    var sql = `select * from endlogin where username= "${user}" and password = "${psd}"`;
    getQueryEndLogin(sql,(result)=>{
        console.log(result);
        if(result==false){
        res.send({"err":-1,"msg":"登录失败"})
        }else{
            token = jwt.sign({"user":user,"psd":psd},"nihao",{expiresIn:60*60*6})
            res.send({"err":1,"msg":"登录成功","token":token})

            

        }
    })
})



/**
 * @api {get} /wx/user/tests 小程序后台修改数据避开id查询(后台)
 * @apiName   tests 小程序后台修改数据避开id查询(后台)
 * @apiGroup T测试接口
 *


 * @apiSuccess {String} 1  成功
 * @apiSuccess {String} -999 未登录,请先登录
 */
//测试接口（后台修改数据避开id查询）
wxRouter.get("/tests",(req,res)=>{
    if(req.headers.authorization!=token) return  res.send({"err":-999,"msg":"请先登录"})
    res.send({"err":1,"msg":"后台修改数据避开id查询"})
})










/**
 * @api {post} /wx/user/delete 小程序发现页面数据查询删除(通过_id)(后台)   
 * @apiName   delete 小程序发现页面数据查询删除(通过_id)(后台)
 * @apiGroup  H小程序(后台)
 *
 * @apiParam {String} _id  唯一id

 *
 * @apiSuccess {String} 1 删除成功.
 * @apiSuccess {String} -1  删除失败.
 * @apiSuccess {String} -999  未登录,请先登录.
 */

//后台管理删除接口
wxRouter.post("/delete",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    if(req.headers.authorization!=token) return  res.send({"err":-999,"msg":"请先登录"})
    let {_id} = req.body;
    var sql1 = `delete from wxFaxian where _id = "${_id}" `;
    getQueryFaxian(sql1,(result)=>{
        console.log(result.affectedRows>0);
        if(result.affectedRows>0){
            res.send({"err":"1","msg":"删除成功"});
        }else{
            res.send({"err":"-1","msg":"删除失败"});
        }
    })
})











/**
 * @api {get} /wx/user/faXianSelect 小程序发现页面数据查询(倒序)(用户)
 * @apiName   faXianSelect 小程序发现页面数据查询(用户)
 * @apiGroup Y小程序(用户)
 *


 * @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */
//发现页面数据查询
wxRouter.get("/faXianSelect",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    var sql = "select *  from wxFaxian  order by _id desc";
    // var sql = "select *  from wxFaxian";
    getQueryFaxian(sql,(data)=>{
        
        if(data ==false){
            res.send({"err":-1,"msg":"请求失败"})
        }else{

            res.send({"err":1,"msg":"请求成功",list:data})
        }
    })

})





/**
 * @api {post} /wx/user/faXianSelectId 小程序通过id查询(后台)  
 * @apiName   faXianSelectId 小程序通过_id查询(后台)
 * @apiGroup H小程序(后台)
 *
 * @apiParam {String} _id  对应自增_id

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */

//通过id查询
wxRouter.post("/faXianSelectId",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.headers);
    let {_id} = req.body;
    var sql = `select * from wxFaxian where _id = '${_id}'`;
    getQueryFaxian(sql,(data)=>{
        
        // console.log(data);
        if(data ==false){
            res.send({"err":-1,"msg":"请求失败"})
        }else{

            res.send({"err":1,"msg":"请求成功",list:data})
        }
    })

})


/**
 * @api {post} /wx/user/faXianSelectId 小程序通过id查询(用户)  
 * @apiName   faXianSelectId 小程序通过_id查询(用户)
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} _id  对应自增_id

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */

//通过id查询
wxRouter.post("/faXianSelectId",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.headers);
    let {_id} = req.body;
    var sql = `select * from wxFaxian where _id = '${_id}'`;
    getQueryFaxian(sql,(data)=>{
        
        // console.log(data);
        if(data ==false){
            res.send({"err":-1,"msg":"请求失败"})
        }else{

            res.send({"err":1,"msg":"请求成功",list:data})
        }
    })

})



/**
 * @api {post} /wx/user/wxx/update 小程序后台修改数据(通过_id)(后台)
 * @apiName   /wxx/update 小程序后台修改数据(通过_id)(后台)
 * @apiGroup H小程序(后台)
 *
 * @apiParam {String} _id  详情页的来源
 * @apiParam {String} title  详情页标题
 * @apiParam {String} image1  发现及详情页图片
 * @apiParam {String} image2  详情页图片(已取消)
 * @apiParam {String} descs  发现页描述标题
 * @apiParam {String} time  详情页的时间
 * @apiParam {String} content  详情页的主要内容
 * @apiParam {String} source  详情页的来源

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */

    // wxRouter.gwt("../static/images/1636970483666.jpg")
    wxRouter.post("/wxx/update",(req,res)=>{

        res.setHeader("Access-Control-Allow-Origin","*");
        res.setHeader("Access-Control-Allow-Methods", "*");
        res.setHeader("Access-Control-Allow-Headers",  "*");
        // console.log(req.headers);
        // if(req.headers.authorization!=token) return  res.send({"err":-999,"msg":"请先登录"})

        let {title,image1,image2,descs,time,content,source,_id} = req.body;

        var sql = `update wxFaxian set title = "${title}" ,image1 = "${image1}",image2 = "${image2}" ,descs = "${descs}" ,time = "${time}", content = "${content}",source= "${source}" where _id = ${_id}`;
        getQueryFaxian(sql,(result)=>{
            // console.log(result);
            if(result.affectedRows>0){
                res.send({"err":1,"msg":"修改成功"})
            }else{
                res.send({"err":-1,"msg":"修改失败"})
            }
        })
    })
    





/**
 * @api {post} /wx/user/faXianSelectKw 小程序模糊查询(发现页搜索框)(用户)  
 * @apiName   faXianSelectKw 小程序模糊查询(发现页搜索框)(用户)  
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} kw  输入的内容

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */
//模糊查询
wxRouter.post("/faXianSelectKw",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    let {kw} = req.body;
    var sql = `select *  from wxFaxian  where descs like "%${kw}%" order by _id desc;`;
    getQueryFaxian(sql,(data)=>{
        // console.log(data);
        if(data ==false){
            res.send({"err":-1,"msg":"请求失败"})
        }else{
            res.send({"err":1,"msg":"请求成功",list:data})
        }
    })
})


/**
 * @api {post} /wx/user/faXianSelectKw 小程序模糊查询(发现页搜索框)(后台)  
 * @apiName   小程序模糊查询(发现页搜索框)(后台)  
 * @apiGroup H小程序(后台)
 *
 * @apiParam {String} kw  输入的内容

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 */
//模糊查询
wxRouter.post("/faXianSelectKw",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    let {kw} = req.body;
    var sql = `select *  from wxFaxian  where descs like "%${kw}%" order by _id desc;`;
    getQueryFaxian(sql,(data)=>{
        // console.log(data);
        if(data ==false){
            res.send({"err":-1,"msg":"请求失败"})
        }else{
            res.send({"err":1,"msg":"请求成功",list:data})
        }
    })
})






//发现页面
//上传数据至数据库

/**上传模板
 * {
    "id": 1,
    "title": "关于浮动",
    "image2": "https://s3.bmp.ovh/imgs/2021/10/a7f23159dd895bde.jpg",
    "image1": "https://s3.bmp.ovh/imgs/2021/10/a7f23159dd895bde.jpg",
    "descs": "浮动后产生影响的解决",
    "time": "2021-11-21",
    "content": "排除浮动的影响:",
    "source": "CSDN"
}
 */

/**
 * @api {post} /wx/user/message 小程序发现页面(数据上传)(后台)
 * @apiName  小程序发现页面 (数据上传)(后台)
 * @apiGroup H小程序(后台)
 
 * @apiParam {String} title  详情页标题
 * @apiParam {String} image1  发现及详情页图片
 * @apiParam {String} image2  详情页图片(已取消)
 * @apiParam {String} descs  发现页描述标题
 * @apiParam {String} time  详情页的时间
 * @apiParam {String} content  详情页的主要内容
 * @apiParam {String} source  详情页的来源

* @apiSuccess {String} -1  请求失败
 * @apiSuccess {String} 1  请求成功
 * @apiSuccess {String} -999  未登录,请先登录
 */

    // wxRouter.gwt("../static/images/1636970483666.jpg")
wxRouter.post("/message",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    if(req.headers.authorization!=token) return  res.send({"err":-999,"msg":"请先登录"})
    let {title,image1,image2,descs,time,content,source} = req.body;
    var sql = `insert into wxFaxian(title,image1,image2,descs,time,content,source) values("${title}","${image1}","${image2}","${descs}","${time}","${content}","${source}")`
    getQueryFaxian(sql,(result)=>{
        // console.log(result);
        if(result.affectedRows>0){
            res.send({"err":1,"msg":"插入成功"})
        }else{
            res.send({"err":-1,"msg":"插入失败"})
        }
    })
})










//测试接口
wxRouter.get("/",(req,res)=>{
    res.send("欢迎访问")
})


/**
 * @api {get} /wx/user/select 测试接口(表名为:wx)  
 * @apiName   select 测试接口(表名为:wx)  
 * @apiGroup T测试接口

 */
//查询所有
wxRouter.get("/select",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    var sql = "select * from wx"
    getQuery(sql,(result)=>{
        res.send(result)
    })
})


/**
 * @api {post} /wx/user/reg 小程序用户注册(用户)   
 * @apiName   reg 小程序用户注册(用户)
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} nicheng  昵称
 * @apiParam {String} username  账号(邮箱)
 * @apiParam {String} password  密码
 * @apiParam {String} code  邮箱验证码

 *
 * @apiSuccess {String} -3  账号已存在
 * @apiSuccess {String} -1  验证码错误
 * @apiSuccess {String} 1  注册成功
 */

//注册接口
wxRouter.post("/reg",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.body);
    var nicheng = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    var code = req.body.code;
    if(user!="" && psd !=""){
        if(nicheng==""){
            return res.send({"err":-1,"msg":"昵称不能为空"})
        }
        if(code==""){
            return res.send({"err":-1,"msg":"验证码不能为空"})
        }
        console.log("66",codes);
        console.log("67",codes[user]);
        console.log("68",code);
        var sql1 = `select * from wx where username= "${user}"` ;
        getQuery(sql1,(result)=>{
            // res.send(result);
            if(result==false){
                if(codes[user] != code){
                    res.send({"err":-1,"msg":"验证码不正确"});
                    return;
                }
                var sql2 = `insert into wx(nicheng,username,password) values("${nicheng}","${user}","${psd}")`;
                getQuery(sql2,(result)=>{
                    res.send({"err":1,"msg":"注册成功"});
                    selfMail("x709500@163.com",user)
                    console.log("成功注册",result);
                })
            }else{
                // console.log("result1",result1);
                res.send({"err":-3,"msg":"账号已存在"});
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})






/**
 * @api {post} /wx/user/login 小程序用户登录(用户)
 * @apiName   login 小程序用户登录(用户)
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} username  账号(邮箱)
 * @apiParam {String} password  密码

 *
 * @apiSuccess {String} -1 账号不存在
 * @apiSuccess {String} -2  账号或密码错误
 * @apiSuccess {String} 1  登陆成功
 */
//登录接口
wxRouter.post("/login",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // var name = req.body.nicheng;
    var user = req.body.username;
    var psd = req.body.password;
    
    if(user!="" && psd !=""){
        var sqls = `select * from wx where username = "${user}"` ;
        // var sqls = "select * from userInfo";

        getQuery(sqls,(result)=>{
            // res.send(result);
            if(result==false){
                res.send({"err":-1,"msg":"账号不存在,请前往注册"});
            }else{
                var sql5 = `select * from wx where username = "${user}" and password = "${psd}"`
                getQuery(sql5,(result2)=>{
                    if(result2==false){
                        res.send({"err":-2,"msg":"账号或密码错误"});
                    }else{  
                        res.send({"err":1,"msg":"登录成功"});
                        console.log("成功登录",result2);
                    }
                })
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})





/**
 * @api {post} /wx/user/getMail 小程序邮箱发送验证码(用户)
 * @apiName   getMail 小程序邮箱发送验证码(用户)
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} mail 邮箱

 *
 * @apiSuccess {String} 1  验证码发送成功.
 * @apiSuccess {String} -1  验证码发送失败.
 */
//发送邮箱验证码
wxRouter.post("/getMail",(req,res)=>{   //1565965166@qq.com
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    var mail = req.body.mail;
    var code="";
    for(var i=0;i<6;i++){
        code+= parseInt(Math.random()*10)
    }
    sendMailer(mail,code)
    .then((msg)=>{
        codes[mail] = code
        res.send({"err":1,"msg":"验证码发送成功"});
    })
    .catch((err)=>{
        res.send({"err":-1,"msg":"验证码发送失败"})
    })
})





/**
 * @api {post} /wx/user/update 小程序忘记密码(用户)   
 * @apiName   update 小程序忘记密码(用户)   
 * @apiGroup Y小程序(用户)
 *
 * @apiParam {String} user  账号(邮箱)
 * @apiParam {String} psd  密码
 * @apiParam {String} code  邮箱验证码

 *
 * @apiSuccess {String} -1 账号不存在
 * @apiSuccess {String} -2  验证码不正确
 * @apiSuccess {String}  1  修改成功
 */
//  var updateCodes = {};
//忘记密码接口
wxRouter.post("/update",(req,res)=>{
    res.setHeader("Access-Control-Allow-Origin","*");
    res.setHeader("Access-Control-Allow-Methods", "*");
    res.setHeader("Access-Control-Allow-Headers",  "*");
    // console.log(req.body);
    // var name = req.body.nicheng;
    
    var user = req.body.username;
    var psd = req.body.password;
    var code = req.body.code;
    if(user!="" && psd !=""){
        // if(nicheng==""){
        //     return res.send({"err":-1,"msg":"昵称不能为空"})
        // }
        if(code==""){
            return res.send({"err":-1,"msg":"验证码不能为空"})
        }
        console.log(codes);
        console.log(code);
        console.log(codes[user]);
        var sql1 = `select * from wx where username= "${user}"` ;
        getQuery(sql1,(result)=>{
            // res.send(result);
            console.log(result);
            if(result==false){
                res.send({"err":-1,"msg":"账号不存在"});
            }else{
                if(codes[user] != code){
                    res.send({"err":-2,"msg":"验证码不正确"});
                    return;
                }
                var sql2 = `update wx set password = "${psd}" where username = "${user}"` ;
                // update 表名 set 字段名1 = "值1",字段名2 = "值2", where 字段名 = "值";
                getQuery(sql2,(result)=>{
                    res.send({"err":1,"msg":"修改密码成功"});
                    console.log("成功修改密码",result);
                })
                // console.log("result1",result1);
                
            }
        })
    }else{
        res.send({"err":-1,"msg":"账号密码不能为空"});
    }

})







/**
 * @api {get} /wx/user/index 小程序首页及公告请求(用户) 
 * @apiName   index 小程序首页及公告请求(用户)
 * @apiGroup Y小程序(用户)


 *
 * @apiSuccess {String} -1 请求失败
 * @apiSuccess {String}  1  请求成功
 */

//首页及公告请求    //https://s3.bmp.ovh/imgs/2021/10/a79bc3fe2f4eb0a6.gif
wxRouter.get("/index",(req,res)=>{
    var obj = {
        desc:"你好生活",
        image:"public/images/index.gif",
    }
    try {
        res.send({"err":1,"msg":"请求成功",list:obj});
        
    } catch (error) {
        res.send({"err":-1,"msg":"请求失败"})
    }
    
})







/**
 * @api {get} /wx/user/about 小程序关于-图片请求(用户)  
 * @apiName   about 小程序关于-图片请求(用户)
 * @apiGroup Y小程序(用户)


 *
 * @apiSuccess {String} -1 请求失败
 * @apiSuccess {String}  1  请求成功
 */


//关于-图片请求    //https://s3.bmp.ovh/imgs/2021/10/a79bc3fe2f4eb0a6.gif
wxRouter.get("/about",(req,res)=>{
    var obj = {
        // desc:"你好生活",
        image:"public/images/about.gif",
    }
    try {
        res.send({"err":1,"msg":"请求成功",list:obj});
        
    } catch (error) {
        res.send({"err":-1,"msg":"请求失败"})
    }
})

module.exports = wxRouter;
```

### 02.mysql连接及封装代码 {#02mysql连接及封装代码}

``` javascript
const mysql = require("mysql");

const client = mysql.createConnection({
  
    host:"60.205.226.237",
    user:"one_helloxlj_top",
    password:"TPAnAekjGkjMP6df",
    database:"one_helloxlj_top",
    port:"3306"

})

//封装并抛出
function getQuery(sql,callback){
    client.query(sql,(err,result)=>{
        if(err){
            console.log("数据库连接失败");
        }else{
            callback(result);
        }
    })
}

module.exports = getQuery;
```

### 03.获取当前时间 {#03获取当前时间}

``` 
 function getTime(){
        var now = new Date();
      var year = now.getFullYear(); //得到年份
      var month = now.getMonth();//得到月份
      var date = now.getDate();//得到日期
      var day = now.getDay();//得到周几
      var hour = now.getHours();//得到小时
      var minu = now.getMinutes();//得到分钟
      var sec = now.getSeconds();//得到秒
      month = month + 1;
      if (month < 10) month = "0" + month;
      if (date < 10) date = "0" + date;
      if (hour < 10) hour = "0" + hour;
      if (minu < 10) minu = "0" + minu;
      if (sec < 10) sec = "0" + sec;
      var time = "";
      //精确到天
        // console.log(time = year + "-" + month + "-" + date);
      //精确到分
        return year + "-" + month + "-" + date+ " " + hour + ":" + minu
        // console.log(year + "-" + month + "-" + date+ " " + hour + ":" + minu);
    }
```

# 常用url

#### 1.demo {#1demo}

``` javascript
01、https://www.npmjs.com/?track=newUserCreated    -- npm安装第三方资源包
02、https://www.baidufe.com/fehelper/index/index.html      -- FeHelper ( 浏览器插件 )
03、https://www.bitbug.net/          -- icon图标制作及修改
04、https://imgurl.org/            -- 外网链接1 (everyday<=10)
06、https://sm.ms/                 -- 外网链接2
07、https://binaryify.github.io/NeteaseCloudMusicApi/#/?id=%e6%89%80%e6%9c%89%e6%a6%9c%e5%8d%95  -- 网易云API
08、https://lanhuapp.com/web/#/item    -- 蓝湖 
09、https://mirrors.tuna.tsinghua.edu.cn/help/pypi/    -- pip镜像
10、https://www.chaojiying.com/user/login/    -- 超级鹰验证码识别
11、https://sc.chinaz.com/tag_yinxiao/xiaoxi.html   -- 消息音效
12、https://www.extfans.com/       -- EXtfans(谷歌插件下载)
13、https://unsplash.dogedoge.com/   -- unsplash(高清图片)
14、https://www.pexels.com/zh-cn/    -- pexels(高清图片、视频)
15、https://apidocjs.com/    --apidoc接口文档生成
16.Learn CSS layout：			http://learnlayout.com
17.Flexbox Froggy：	http://flexboxfroggy.com
18.EnjoyCSS：	https://enjoycss.com     //css
19.Neumorphism：	https://neumorphism.io      //圆角盒阴影
20.uiGradients：	https://uigradients.com     // 渐变
21.JavaScript Fun：	https://www.javascript.fun
22.Share Icon ：	https://www.shareicon.net        //图标
23.tableconvert ：	https://tableconvert.com    
24.http://jeeweixin.com/        //软件集合
25.https://api.github.com/search/users?q=xxx    //开放接口
26.https://www.jq22.com/     //jQuery插件库
```

\#
