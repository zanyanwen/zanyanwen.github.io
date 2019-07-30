window对象属性：
    http://www.w3school.com.cn/jsref/dom_obj_window.asp

    location:  列子:                                       https://www.w3.org/WAI/WCAG21/quickref/?showtechniques=131#adaptable
        href: 设置或返回 完整的url                          https://www.w3.org/WAI/WCAG21/quickref/?showtechniques=131#adaptable
        hash：设置或返回 从井号 (#) 开始的 URL（锚）,hash、hashchange事件           #adaptable   
        host：设置或返回 主机名+端口号                       www.w3.org
        hostname: 设置或返回 主机名                         www.w3.org
        pathname: 属性是一个可读可写的字符串，可设置或返回当前 URL 的路径部分       /WAI/WCAG21/quickref/
        origin: https://www.w3.org
        protocol：https
        port: ''

        assign()  	加载新的文档 效果类似设置href
        reload()    重新加载文档 刷新页面
        replace()   用新的文档替换当前文档 效果类似assign()

    Navigator 对象包含有关浏览器的信息。
        http://www.w3school.com.cn/jsref/dom_obj_navigator.asp

    Screen 对象包含有关客户端显示屏幕的信息。
        http://www.w3school.com.cn/jsref/dom_obj_screen.asp

    History 对象包含用户（在浏览器窗口中）访问过的 URL
        length 	返回浏览器历史列表中的 URL 数量。

        back() 	加载 history 列表中的前一个 URL。
        forward() 	加载 history 列表中的下一个 URL。
        go() 	加载 history 列表中的某个具体页面。