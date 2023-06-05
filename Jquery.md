

## JQuery常用API ##

**1.jQuery选择器**

  - 原生 JS 获取元素方式很多，很杂，而且兼容性情况不一致，因此 jQuery 给我们做了封装，使获取元素统一标准
  - 语法：$(“选择器”)   // 里面选择器直接写 CSS 选择器即可，但是要加引号
  - 层级选择器

     - 子代选择器：$("ul>li") 使用>号 获取亲儿子层级的元素 注意 并不会获取孙子层级的元素
     - 后代选择器：$("ul li") 使用空格 代表后代选择器 获ul下的所有li元素 包括孙子等

  - jQuery设置样式：$('div').css('属性', '值')
  - 隐式迭代

     - 内部遍历DOM元素（伪数组形式存储）的过程就叫做隐式迭代
     - 简单理解：给匹配到的所有元素进行遍历循环 执行相应的方法 而不用我们再进行循环 简化我们的操作 方便我们调用 

  - 筛选选择器

     - $("li:first")： 获取第一个li元素
     - $("li:last")： 获取最后一个li元素
     - $("li:eq（2）")： 获取到的li元素中 选择索引号为2的元素
     - $("li:odd")：获取到的li元素中 选择索引号为奇数的元素
     - $("li:even")：获取到的li元素中 选择索引号为偶数的元素

  - 筛选方法（重点）

     - parent（）：查找父级
     - children（selector）：最近一级（亲儿子）
     - find（selector）：相当于后代选择器
     - siblings（selector）：查找兄弟节点 不包括自己本身
     - eq（index）：相当于$("li:eq（2）")
     - nextAll（【expr】）：查找当前元素之后所有的同辈元素
     - prevtAll（【expr】）：查找当前元素之前所有的同辈元素
     - hasClass（class）：检查当前的元素是否含有某个特定的类 如果有 则返回true

  - 排他思想：当前元素设置样式 其余的兄弟元素清除样式
  - 链式编程：为了节省代码量 看起来更优雅

**2.样式操作**

  - 操作css方法

      - jQuery 可以使用 css 方法来修改简单元素样式； 也可以操作类，修改多个样式。
      - 参数只写属性名 则是返回属性值：$(this).css(''color'');
      -  参数是属性名，属性值，逗号分隔，是设置一组样式，属性必须加引号，值如果是数字可以不用跟单位和引号：$(this).css(''color'', ''red'');
      -   参数可以是对象形式，方便设置多组样式。属性名和属性值用冒号隔开， 属性可以不用加引号：$(this).css({ "color":"white","font-size":"20px"});

  - 设置类样式方法

      - 作用等同于以前的 classList，可以操作类样式， 注意操作类里面的参数不要加点。
      - 添加类：$(“div”).addClass(''current'');
      - 移除类：$(“div”).removeClass(''current'');
      - 切换类：$(“div”).toggleClass(''current'');

 - 类操作与className区别

      - 原生js中className会覆盖元素原先里面的类名
      - jQuery 里面类操作只是对指定类进行操作，不影响原先的类名

**3.jQuery效果**

  - 显示隐藏效果

     - 显示语法：show([speed,[easing],[fn]])
     - 显示参数

         - 参数都可以省略 无动画直接显示
         - speed：三种预定速度之一的字符串（slow normal fast）或表示动画时长的毫秒数值
         - easing：（Optional）用来指定切换效果 默认是swing 可用参数linear
         - fn：回调函数  在动画完成时执行的函数 每个元素执行一次

     - 隐藏语法： hide([speed,[easing],[fn]])
     - 隐藏参数

         - 参数都可以省略， 无动画直接显示。
         - speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)
         - easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”
         - fn: 回调函数，在动画完成时执行的函数，每个元素执行一次

     - 切换语法：toggle([speed,[easing],[fn]])
     - 切换参数

         - 参数都可以省略， 无动画直接显示。
         - speed：三种预定速度之一的字符串(“slow”,“normal”, or “fast”)或表示动画时长的毫秒数值(如：1000)
         - easing：(Optional) 用来指定切换效果，默认是“swing”，可用参数“linear”
         - fn: 回调函数，在动画完成时执行的函数，每个元素执行一次
         - 建议：平时一般不带参数 直接显示隐藏即可

  - 滑动效果

       - 下滑效果语法：slideDown([speed,[easing],[fn]])
       - 上滑效果语法：slideUp([speed,[easing],[fn]])
       - 滑动切换效果语法：slideToggle([speed,[easing],[fn]])

  - 事件切换

       - 语法：hover（【over，】out）
       - over:鼠标移到元素上要触发的函数（相当于mouseenter）
       - out:鼠标移出元素要触发的函数（相当于mouseleave）
       - 如果只写一个函数，则鼠标经过和离开都会触发它

  - 动画队列及其停止排队方法

      - 动画或效果队列：动画或者效果一旦触发就会执行 如果多次触发 就造成多个动画或者效果排队执行
      - 停止排队

         - 语法：stop（）
         - stop() 方法用于停止动画或效果
         -  注意： stop() 写到动画或者效果的前面， 相当于停止结束上一次的动画

  - 淡入淡出效果

      - 淡入效果：fadeIn([speed,[easing],[fn]])
      - 淡出效果：fadeOut([speed,[easing],[fn]])
      - 淡入淡出切换效果：fadeToggle([speed,[easing],[fn]])
      - 渐进方式调整到指定的不透明度

         - 语法：fadeTo([[speed],opacity,[easing],[fn]])
         - 参数：opacity透明度必须写 取值0-1之间 速度必须写

  - 自定义动画animate

      - 语法：animate(params,[speed],[easing],[fn])
      - 参数

          - params：想要更改的样式属性 以对象形式传递 必须写 属性名可以不带引号如果是复合属性则需要采取驼峰命名法 borderLeft 其余参数都可以省略

**4.jQuery属性操作**

  - 设置或获取元素固有属性值prop（）

       - 所谓元素固有属性就是元素本身自带的属性，比如 `<a>` 元素里面的 href ，比如 `<input>` 元素里面的 type
       - 获取属性语法：prop(''属性'')
       - 设置属性语法：prop(''属性'', ''属性值'')

  - 设置或获取元素自定义属性值attr（）

       - 用户自己给元素添加的属性，我们称为自定义属性。 比如给 div 添加 index =“1”
       - 获取属性语法：attr(''属性'') // 类似原生 getAttribute()
       - 设置属性语法：attr(''属性'', ''属性值'') // 类似原生 setAttribute()

  - 数据缓存data（）

       - data() 方法可以在指定的元素上存取数据，并不会修改 DOM 元素结构。一旦页面刷新，之前存放的数据都将被移除
       - 附加数据语法：data(''name'',''value'') // 向被选元素附加数据
       - 获取数据语法：date(''name'') // 向被选元素获取数据
       - 同时，还可以读取 HTML5 自定义属性 data-index ，得到的是数字型

**5.jQuery内容文本值**

  - 主要针对元素内容还有表单的值操作
  - 普通元素内容html（）（ 相当于原生inner HTML)

      - html() // 获取元素的内容
      - html(''内容'') // 设置元素的内容

  -  普通元素文本内容 text() (相当与原生 innerText)

      - text() // 获取元素的文本内容
      - text(''文本内容'') // 设置元素的文本内容

  - 表单的值val（）（ 相当于原生value)

      - val() // 获取表单的值
      - val(''内容'') // 设置表单的值

**6.jQuery元素操作**

  - 主要是遍历 创建 添加 删除元素操作
  - 语法1：$("div").each(function (index, domEle) { xxx; }）

     - each()方法遍历匹配的每一个元素 主要用DOM处理 each每一个
     - 里面的回调函数有2个参数：index是每个元素的索引号 demEle是每个DOM元素对象 不是jquery对象
     - 所以想要使用jquery方法 需要给这个dom元素转换为jquery对象$(domEle)

  - 语法2：$.each(object，function (index, element) { xxx; }）

     - . $.each()方法可用于遍历任何对象。主
     - 要用于数据处理，比如数组，对象
     - 里面的函数有2个参数： index 是每个元素的索引号; element 遍历内容

  - 创建元素：$(''`<li></li>`'');
  - 添加元素

      - 内部添加：
       
         - element.append(''内容'')把内容放入匹配元素内部最后面，类似原生 appendChild
         - element.prepend(''内容'')把内容放入匹配元素内部最前面

      - 外部添加

         - element.after(''内容'') // 把内容放入目标元素后面
         - element.before(''内容'') // 把内容放入目标元素前面

      - 内部添加元素：生成之后他们是父子关系
      - 外部添加元素：生成之后 他们是兄弟关系

  - 删除元素

      - element.remove() // 删除匹配的元素（本身）
      - element.empty() // 删除匹配的元素集合中所有的子节点
      - element.html('''') // 清空匹配的元素内容
      - remove删除元素本身
      - empt() 和 html('''') 作用等价，都可以删除元素里面的内容，只不过 html 还可以设置内容


## jQuery事件 ##


**1.jQuery事件注册**

  - 单个事件注册

     - 语法：element.事件(function(){})  

  - 其他事件和原生基本一致 比如mouseover、mouseout、blur、focus、change、keydown、keyup、resize、scroll 等

**2.jQuery事件处理**

  - 事件处理on（）绑定事件

     - on() 方法在匹配元素上绑定一个或多个事件的事件处理函数
     - 语法：element.on(events,[selector],fn)

         - events:一个或多个用空格分隔的事件类型，如"click"或"keydown"
         -  selector: 元素的子元素选择器
         -  fn:回调函数 即绑定在元素身上的侦听函数

     - on（）方法优势

         - 可以绑定多个事件，多个处理事件处理程序
         - 可以事件委派操作 。事件委派的定义就是，把原来加给子元素身上的事件绑定在父元素身上，就是把事件委派给父元素
         - 动态创建的元素，click() 没有办法绑定事件， on() 可以给动态生成的元素绑定事件

  - 事件处理 off（）解绑事件

     - off() 方法可以移除通过 on() 方法添加的事件处理程序
     - 如果有的事件只想触发一次， 可以使用 one() 来绑定事件

  - 自动触发事件 trigger（）

      - 有些事件希望自动触发, 比如轮播图自动播放功能跟点击右侧按钮一致。可以利用定时器自动触发右侧按钮点击事件，不必鼠标点击触发
      - 语法：
      
        - element.click() // 第一种简写形式
        - element.trigger("type") // 第二种自动触发模式
        - element.triggerHandler(type) // 第三种自动触发模式
        - triggerHandler模式不会触发元素的默认行为，这是和前面两种的区别

**3.jQuery事件对象**

  - 事件被触发，就会有事件对象的产生
  - element.on(events,[selector],function(event) {})
  - 阻止默认行为：event.preventDefault() 或者 return false
  - 阻止冒泡： event.stopPropagation()


## jQuery其他方法 ##


**1.jQuery拷贝对象**

 - 如果想要把某个对象拷贝（合并） 给另外一个对象使用，此时可以使用 $.extend() 方法
 - 语法：$.extend([deep], target, object1, [objectN])

     - deep: 如果设为true 为深拷贝， 默认为false 浅拷贝
     - target：要拷贝的目标对象
     - object1：待拷贝的第一个对象的对象
     - objectN:待拷贝到第N个对象的对象
     - 浅拷贝是把被拷贝的对象复杂数据类型中的地址拷贝给目标对象，修改目标对象会影响被拷贝对象
     - 深拷贝，前面加true， 完全克隆(拷贝的对象,而不是地址)，修改目标对象不会影响被拷贝对象

**2.多库共存**

  - 把里面的 $ 符号 统一改为 jQuery。 比如 jQuery(''div'')
  -  jQuery 变量规定新的名称：$.noConflict() var xx = $.noConflict();

**3.jQuery插件**

  - 使用步骤

     -  引入相关文件。（jQuery 文件 和 插件文件）
     -   复制相关html、css、js (调用插件)