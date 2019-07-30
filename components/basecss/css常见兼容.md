CSS常见兼容性问题
    浏览器的兼容性问题，通常是因为不同的浏览器对同一段代码有不同的解析，造成页面显示不一致的情况。

常见问题：
    1、IE6双边距bug: 块属性标签添加了浮动float之后，若在浮动方向上也有margin值，则margin值会加倍。其实这种问题主要就是会把某些元素挤到了第二行；
        解决办法：给float元素添加display：inline 即可正常显示
    2、标签属性min-height是不兼容的，所以使用的时候也要稍微改改。这样吧 .box{min-height:100px;height:auto !important; height:100px; overflow:visible;}
    3、很多时候可能会纳闷超链接访问过后 样式就混乱了，hover样式不出现了。其实主要是其CSS属性的排序问题。一般来说，最好按照这个顺序：L-V-H-A
        a:link{}  a:visited{}  a:hover{}  a:active{}
    4、chrome下默认会将小于12px的文本强制按照12px来解析。解决办法是给其添加属性：-webkit-text-size-adjust: none; 
    5、因为存在两种盒子模式：IE盒子模式和W3C标准模式，所以对象的实际宽度也要注意。
    6、鼠标的手势也有问题：FireFox的cursor属性不支持hand，但是支持pointer，IE两个都支持；所以为了兼容都用pointer
    7、消除ul、ol等列表的缩进时，样式应写成:list-style:none;margin:0px;padding:0px; 其中margin属性对IE有效，padding属性对FireFox有效
    8、CSS控制透明度问题：一般就直接 opacity: 0.6 ; IE就 filter: alpha(opacity=60)

CSS Hack：
    CSS hack主要有三种：IE条件注释法、CSS属性前缀法、选择器前缀法。
        1、<!--  lt是小于 gt是大于 lte是小于等于 gte是不小于 !是不等于 -->

            <!-- [if IE]>
               你想要执行的代码 
            <![endif]-->

            <!-- [if lt IE 8]>
               你想要执行的代码 
            <![endif]-->

            <!-- [if ! IE 8]>
               你想要执行的代码 
            <![endif]-->

        2、CSS属性前缀法，即是给css的属性添加前缀。比如 * 可以被IE6/IE7识别，但 _ 只能被IE6识别，IE6-IE10都可以识别 "\9"，IE6不能识别!important  FireFox不能识别 * _  \9

        3、选择器前缀法，顾名思义，就是给选择器加上前缀。
            @media screen\9{...}只对IE6/7生效
            @media \0screen {body { background: red; }}只对IE8有效
            @media \0screen\,screen\9{body { background: blue; }}只对IE6/7/8有效
            @media screen\0 {body { background: green; }} 只对IE8/9/10有效
            @media screen and (min-width:0\0) {body { background: gray; }} 只对IE9/10有效
            @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {body { background: orange; }} 只对IE10有效 等等