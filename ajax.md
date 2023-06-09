# DAay01 #

## 服务器的基本概念与初始Ajax ##

**1.客户端与服务器**

  - 上网的本质目的：通过互联网的形式来获取和消费资源
  - 服务器：上网过程中 负责存放和对外提供资源的电脑 叫服务器
  - 客户端：上网过程中 负责获取和消费资源的电脑 叫做客户端

**2.URL地址**

  - URL（UniformResourceLocator）：中文叫统一资源定位符 用于标识互联网上每个资源的唯一存放位置 浏览器只有通过URL地址 才能正确定位资源的存放位置 从而成功访问到对应的资源
  - 组成部分

     - 客户端与服务器之间的通信协议
     - 存有该资源的服务器名称
     - 资源在服务器上具体的存放位置
     
**3.分析网页的打开过程**

  - 客户端与服务端的通信过程

       - 请求-处理-响应三个步骤
       - 客户端请求服务器 服务器处理这次请求 服务器响应客户端
       - 网页中的每一个资源 都是通过这三个步骤的方式从服务器获取回来的

  - 基于浏览器的开发者工具分析通信过程

       - 打开浏览器
       - ctrl+shift+i打开chrome的开发者工具
       - 切换到network面板
       - 选中Doc页签
       - 刷新页面 分析客户端与服务器的通信过程

**4.服务器对外提供了哪些资源**

  - 常见的：文字内容 image图片 audio音频 video视频等
  - 网页中的数据 也是服务器对外提供的一种资源
  - 数据-网页的灵魂
  - 网页中如何请求数据

      - 如果要在网页中请求服务器上的数据资源 则需要用到XMLHttpRequest对象
      - XMLHttpRequest（简称xhr）是浏览器提供的js成员 通过它 可以请求服务器上的数据资源
      - 最简单的用法 const xhrObj = new XMLHttpRequest（）

  - 资源的请求方式

      - 客户端请求服务器时 请求的方式有很多种 最常见的方式分别为get和post请求
      - get请求通常用于获取服务端资源（向服务器要资源）：例如根据url地址 从服务器获取html文件 css文件 js文件 图片文件 数据资源等
      - post请求通常用于向服务器提交数据（往服务器发送资源）：例如登陆时向服务器提交的登录信息 注册时向服务器提交的注册信息 添加用户时向服务器提交的用户信息等各种数据提交操作

**5.了解ajax**

  - Ajax的全称是asynchronous JavaScript and XML（异步js和XML） 通俗的理解就是 在网页中利用 XMLHttpRequest 对象和服务器进行数据交互的方式，就是Ajax
  - 之前所学的技术，只能把网页做的更美观漂亮，或添加一些动画效果，但是，Ajax能让我们轻松实现网页与服务器之间的数据交互
  - 应用场景：

       - 用户名检测：注册用户时 通过ajax的形式 动态检测用户名是否被占用
       - 搜索提示：当输入关键字时 通过ajax的形式 动态加载搜索提示列表
       - 数据分页显示：当点击页码值的时候 通过ajax的形式 根据页码值动态刷新表格的数据
       - 数据的增删改查：数据的添加 删除 修改 查询操作 都需要通过ajax的形式 来实现数据的交互

**6。了解jQuery中的Ajax**

  - 浏览器中提供的 XMLHttpRequest 用法比较复杂，所以 jQuery 对 XMLHttpRequest 进行了封装，提供了一系列 Ajax 相关的函数，极大地降低了 Ajax 的使用难度
  - jQuery 中发起 Ajax 请求最常用的三个方法如下：

     - $.get()

          - jQuery中$.get()函数的功能单一 专门用来发起get请求 从而将服务器上的资源请求到客户端来进行使用
          - 语法：$.get(url,[data],[callback])
          - url:字符串型 必选 要请求的资源地址
          - data：对象型 请求资源期间要携带的参数
          - callback 函数类型 请求成功时的回调函数
          - 使用$.get()函数发起不带参数的请求时 直接提供请求的url地址和请求成功之后的回调函数即可
           
     - $.post()

          - jQuery 中 $.post() 函数的功能单一，专门用来发起 post 请求，从而向服务器提交数据
          - 语法：$.post(url,[data],[callback])
          - url：字符串类型 必选 提交数据的地址
          - data：对象类型 要提交的数据
          - callback：函数类型 数据提交成功时的回调函数
     - $.ajax()

          - 相比于 $.get() 和 $.post() 函数，jQuery 中提供的 $.ajax() 函数，是一个功能比较综合的函数，它允许我们对Ajax 请求进行更详细的配置  
          - 语法：$.ajax(type，url，data，success)
          - type：请求的方式 例如GET或POST
          - url：请求的地址
          - data：这次请求要携带的数据
          - success：请求成功之后的回调函数
           
          
**7.接口**

  - 使用 Ajax 请求数据时，被请求的 URL 地址，就叫做数据接口（简称接口）。同时，每个接口必须有请求方式     
  - 接口测试工具
  
     - 为了验证接口能否被正常被访问，我们常常需要使用接口测试工具，来对数据接口进行检测 好处：接口测试工具能让我们在不写任何代码的情况下，对接口进行调用和测试
     
  - 接口文档
  
     - 接口文档，顾名思义就是接口的说明文档，它是我们调用接口的依据。好的接口文档包含了对接口URL，参数以及输出内容的说明，我们参照接口文档就能方便的知道接口的作用，以及接口如何进行调用 
     - 组成部分

         - 接口名称：用来标识各个接口的简单说明 如登录接口，获取图书列表接口等
         - 接口URL：接口的调用地址
         - 调用方式：接口的调用方式，如 GET 或 POST
         - 参数格式：接口需要传递的参数，每个参数必须包含参数名称、参数类型、是否必选、参数说明这4项内容
         - 响应格式：接口的返回值的详细描述，一般包含数据名称、数据类型、说明3项内容
         - 返回示例（可选）：通过对象的形式，例举服务器返回数据的结构


# Day 02 #

## form表单与模板引擎 ##

**1.form表单的基本使用**

  - 表单在网页中主要负责数据采集功能 html中的<form>标签 就是用于采集用户输入的信息 并通过<form>标签的提交操作 把采集到的信息提交到服务器端进行处理
  - 组成部分
  
     - 表单标签
     - 表单域

         - 包含了文本框 密码框 隐藏域 多行文本框 复选框 单选框 下拉选择框和文件上传框等
     - 表单按钮

  - <form>标签的属性

      - <form>标签用来采集数据，<form>标签的属性则是用来规定如何把采集到的数据发送到服务器
      - action：
         - 属性值为url地址 
         - 规定当提交表单时 向何处发送表单数据
         - action 属性的值应该是后端提供的一个 URL 地址，这个 URL 地址专门负责接收表单提交过来的数据
         - 当 <form> 表单在未指定 action 属性值的情况下，action 的默认值为当前页面的 URL 地址
         - 注意：当提交表单后，页面会立即跳转到 action 属性指定的 URL 地址
      - method：
      
         - 属性值为get或post 
         - 规定以何种方式把表单数据提交到 action URL
         - 默认情况下，method 的值为 get，表示通过URL地址的形式，把表单数据提交到 action URL
         - get 方式适合用来提交少量的、简单的数据
         - post 方式适合用来提交大量的、复杂的、或包含文件上传的数据
         - 在实际开发中，<form> 表单的 post 提交方式用的最多，很少用 get。例如登录、注册、添加数据等表单操作，都需要使用 post 方式来提交表单
      - enctype：
       
         - 属性值为application/x-www-form-urlencodedmultipart/form-datatext/plain 
         - 规定在发送表单数据之前如何对其进行编码
         - application/x-www-form-urlencoded：在发送前编码所有字符（默认）
         - multipart/form-data：不对字符编码 在使用包含文件上传控件的表单时 必须使用该值
         - text/plain：空格转换为 “+” 加号，但不对特殊字符编码。（很少用）
         - 在涉及到文件上传的操作时，必须将 enctype 的值设置为 multipart/form-data
         - 如果表单的提交不涉及到文件上传操作，则直接将 enctype 的值设置为 application/x-www-form-urlencoded 即可！
      - target：
       
         - 属性值为_blank_self _parent _top framename 
         - 规定在何处打开 action URL
         - _blank：在新窗口中打开
         - _self：默认 在相同的框架中打开
         - _parent：在父框架集中打开（很少用）
         - _top：在整个窗口中打开（很少用）
         - framename ：在指定的框架中打开（很少用）

  - 表单的同步提交及缺点

     - 通过点击 submit 按钮，触发表单提交的操作，从而使页面跳转到 action URL 的行为，叫做表单的同步提交
     - 缺点

          - <form>表单同步提交后，整个页面会发生跳转，跳转到 action URL 所指向的地址，用户体验很差
          - <form>表单同步提交后，页面之前的状态和数据会丢失

     - 解决方案：表单只负责采集数据，Ajax 负责将数据提交到服务器

**2.通过ajax提交表单数据**

  - 监听表单提交事件
  - 阻止表单默认提交行为

      - 当监听到表单的提交事件以后，可以调用事件对象的 event.preventDefault() 函数，来阻止表单的提交和页面的跳转

  - 快速获取表单中的数据

      - serialize（）函数
      - 语法：$(selector).serialize()
      - serialize() 函数的好处：可以一次性获取到表单中的所有的数据
      - 注意：在使用 serialize() 函数快速获取表单数据时，必须为每个表单元素添加 name 属性
          
      
**3.模板引擎的基本概念**

  - 渲染ui结构时遇到的问题：代码是通过字符串拼接的形式，来渲染UI结构 如果UI结构比较复杂，则拼接字符串的时候需要格外注意引号之前的嵌套。且一旦需求发生变化，修改起来也非常麻烦
  - 模板引擎：它可以根据程序员指定的模板结构和数据，自动生成一个完整的HTML页面
  - 好处

      - 减少了字符串的拼接操作
      - 使代码结构更清晰
      - 使代码更易于阅读与维护

**4.art-template模板引擎**

  - art-template 是一个简约、超快的模板引擎
  - 使用步骤

      - 导入art-template
      - 定义数据
      - 定义模板
      - 调用template函数
      - 渲染html结构

  - 标准语法

      - art-template 提供了 {{ }} 这种语法格式，在 {{ }} 内可以进行变量输出，或循环数组等操作，这种 {{ }} 语法在 art-template中被称为标准语法。
      - 输出：在 {{ }} 语法中，可以进行变量的输出、对象属性的输出、三元表达式输出、逻辑或输出、加减乘除等表达式输出
      
        - 原文输出：{{@ value }}  如果要输出的 value 值中，包含了 HTML 标签结构，则需要使用原文输出语法，才能保证 HTML 标签被正常渲染
       - 条件输出：如果要实现条件输出，则可以在 {{ }} 中使用 if … else if … /if 的方式，进行按需输出
       - 循环输出：如果要实现循环输出，则可以在 {{ }} 内，通过 each 语法循环数组，当前循环的索引使用 $index 进行访问，当前的循环项使用 $value 进行访问
       - 过滤器：{{value | filterName}}
       - 过滤器基本语法：template.defaults.imports.filterName = function(value){/*return处理的结果*/}

**5.模板引擎的实现原理**

  - 正则与字符串操作

      - 基本语法

        - exec() 函数用于检索字符串中的正则表达式的匹配
        - 如果字符串中有匹配的值，则返回该匹配值，否则返回 null
       - RegExpObject.exec(string)

      - 分组：正则表达式中 ( ) 包起来的内容表示一个分组，可以通过分组来提取自己想要的内容
      - 字符串的replace函数：

         - replace() 函数用于在字符串中用一些字符替换另一些字符
         - 语法：var result = '123456'.replace('123', 'abc') // 得到的 result 的值为字符串 'abc456'
         
      - 多次replace
      - 使用while循环replace
      - replace替换为真值

  - 实现简易的模板引擎

      - 实现步骤

         - 定义模板结构
         - 预调用模板引擎
         - 封装template函数
         - 导入并使用自定义的模板引擎

# Day 03 #
## Ajax加强 ##

**1.XMLHttpRequest的基本使用**

  - 什么XMLHttpRequest

      - XMLHttpRequest（简称 xhr）是浏览器提供的 Javascript 对象，通过它，可以请求服务器上的数据资源。之前所学的 jQuery 中的 Ajax 函数，就是基于 xhr 对象封装出来的


  - 使用xhr发起GET请求步骤

     - 创建xhr对象：var xhr = new XMLHttpRequest()
     - 调用xhr.open()函数 ：指定请求方式和URL地址  xhr.open('GET', 'http://www.liulongbin.top:3006/api/getbooks')
     - 调用xhr.send()函数：发起Ajax请求 xhr.send()
     - 监听xhr.onreadystatechange事件  xhr.onreadystatechange = function() {
// 4.1 监听 xhr 对象的请求状态 readyState ；与服务器响应的状态 status
if (xhr.readyState === 4 && xhr.status === 200) {
// 4.2 打印服务器响应回来的数据
console.log(xhr.responseText)
}
}

  - 了解xhr对象的readyState属性

     - XMLHttpRequest 对象的 readyState 属性，用来表示当前 Ajax 请求所处的状态。每个 Ajax 请求必然处于以下状态中的一个：

         - 值为0：状态UNSENT XNLHttpRequest对象已被创建 但尚未调用open方法
         - 值为1：状态OPENED open() 方法已经被调用
         - 值为2：状态HEADERS_RECEIVED send() 方法已经被调用，响应头也已经被接收
         - 值为3：状态LOADING 数据接收中，此时 response 属性中已经包含部分数据
         - 值为4：状态DONE Ajax 请求完成，这意味着数据传输已经彻底完成或失败

  - 使用xhr发起带参数的GET请求

     - 使用 xhr 对象发起带参数的 GET 请求时，只需在调用 xhr.open 期间，为 URL 地址指定参数即可 这种在 URL 地址后面拼接的参数，叫做查询字符串
     - 例如：xhr.open('GET', 'http://www.liulongbin.top:3006/api/getbooks?id=1')

  - 查询字符串

      - 定义：查询字符串（URL 参数）是指在 URL 的末尾加上用于向服务器发送信息的字符串（变量）
      - 格式：将英文的 ? 放在URL 的末尾，然后再加上 参数＝值 ，想加上多个参数的话，使用 & 符号进行分隔。以这个形式，可以将想要发送给服务器的数据添加到 URL 中。
      - GET请求携带参数的本质

          - 无论使用 $.ajax()，还是使用 $.get()，又或者直接使用 xhr 对象发起 GET 请求，当需要携带参数的时候，本质上，都是直接将参数以查询字符串的形式，追加到 URL 地址的后面，发送到服务器的

  - URL编码与解码

      - URL 地址中，只允许出现英文相关的字母、标点符号、数字，因此，在 URL 地址中不允许出现中文字符。如果 URL 中需要包含中文这样的字符，则必须对中文字符进行编码（转义）
      - URL编码的原则：使用安全的字符（没有特殊用途或者特殊意义的可打印字符）去表示那些不安全的字符 即使用英文字符去表示非英文字符
      - 如何进行编码和解码

          - 浏览器提供了 URL 编码与解码的 API，分别是：
          - encodeURI() 编码的函数
          - decodeURI() 解码的函数

      - URL编码的注意事项：由于浏览器会自动对 URL 地址进行编码操作，因此，大多数情况下，程序员不需要关心 URL 地址的编码与解码操作

 - 使用xhr发起POST请求步骤

     - 创建xhr对象：var xhr = new XMLHttpRequest()
     - 调用xhr.open()函数：xhr.open('POST', 'http://www.liulongbin.top:3006/api/addbook')
     - 设置Content-type属性（固定写法）：xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded')
     - 调用xhr.send()函数 同时指定要发送的数据：xhr.send('bookname=水浒传&author=施耐庵&publisher=天津图书出版社')（将数据以查询字符串的形式，提交给服务器）
     - 调用xhr.onreadystatechange 事件：xhr.onreadystatechange = function() {
if (xhr.readyState === 4 && xhr.status === 200) {
console.log(xhr.responseText)
}
}

**2.数据交换格式**

  - 数据交换格式，就是服务器端与客户端之间进行数据传输与交换的格式  前端领域，经常提及的两种数据交换格式分别是 XML 和 JSON。其中 XML 用的非常少，所以，我们重点要学的数据交换格式就是 JSON
  - XML:
   
     - 是 EXtensible Markup Language即可扩展标记语言 XML 和 HTML 类似，也是一种标记语言

     - XML和HTML的区别 

          - XML 和 HTML 虽然都是标记语言，但是，它们两者之间没有任何的关系
          - HTML 被设计用来描述网页上的内容，是网页内容的载体
          - XML 被设计用来传输和存储数据，是数据的载体

     - XML的缺点

         - XML 格式臃肿，和数据无关的代码多，体积大，传输效率低
         - 在 Javascript 中解析 XML 比较麻烦

  - JSON：
   
      - JSON 的英文全称是 JavaScript Object Notation，即“JavaScript 对象表示法”

      - JSON 就是 Javascript 对象和数组的字符串表示法，它使用文本表示一个 JS 对象或数组的信息，因此，JSON 的本质是字符串
      - 作用：JSON 是一种轻量级的文本数据交换格式，在作用上类似于 XML，专门用于存储和传输数据，但是 JSON 比 XML 更小、更快、更易解析
      - JSON的两种结构

         - JSON 就是用字符串来表示 Javascript 的对象和数组。所以，JSON 中包含对象和数组两种结构，通过这两种结构的相互嵌套，可以表示各种复杂的数据结构
         - 对象结构：对象结构在 JSON 中表示为 { } 括起来的内容。数据结构为 { key: value, key: value, … } 的键值对结构。其中，key 必须是使用英文的双引号包裹的字符串，value 的数据类型可以是数字、字符串、布尔值、null、数组、对象6种类型
         - 数组结构：数组结构在 JSON 中表示为 [ ] 括起来的内容。数据结构为 [ "java", "javascript", 30, true … ] 。数组中数据的类型可以是数字、字符串、布尔值、null、数组、对象6种类型
         
      - JSON语法注意事项

          - 属性名必须使用双引号包裹
          - 字符串类型的值必须使用双引号包裹
          - JSON中不允许使用单引号表示字符串
          - JSON中不能写注释
          - JSON的最外层必须是对象或数组格式
          - 不能使用undefined或函数作为JSON的值

      - JSON和JS对象的关系：JSON 是 JS 对象的字符串表示法，它使用文本表示一个 JS 对象的信息，本质是一个字符串
      - JSON和JS对象的互转：
       
        - 要实现从 JSON 字符串转换为 JS 对象，使用 JSON.parse() 方法 
        - 要实现从 JS 对象转换为 JSON 字符串，使用JSON.stringify() 方法

     - 序列化和反序列化

         - 把数据对象转换为字符串的过程，叫做序列化，例如：调用 JSON.stringify() 函数的操作，叫做 JSON 序列化
         - 把字符串转换为数据对象的过程，叫做反序列化，例如：调用 JSON.parse() 函数的操作，叫做 JSON 反序列化


**3.封装自己的Ajax函数**

  - 定义options参数选项

     - itheima() 函数是我们自定义的 Ajax 函数，它接收一个配置对象作为参数，配置对象中可以配置如下属性
     - method 请求的类型
     - url 请求的 URL 地址
     - data 请求携带的数据
     - success 请求成功之后的回调函数

  - 处理data参数

     - 需要把 data 对象，转化成查询字符串的格式，从而提交给服务器，因此提前定义 resolveData 函数

  - 定义itheima函数

     - 在 itheima() 函数中，需要创建 xhr 对象，并监听 onreadystatechange 事件

  - 判断请求的类型

     - 不同的请求类型，对应 xhr 对象的不同操作，因此需要对请求类型进行 if … else … 的判断

**4.XMLHttpRequest Level2的新特性**

  - 旧版XMLHttpRequest的缺点

      - 只支持文本数据的传输，无法用来读取和上传文件
      - 传送和接收数据时，没有进度信息，只能提示有没有完成

  - 新功能

      - 可以设置 HTTP 请求的时限

         - 新版本的XMLHttpRequest 对象，增加了 timeout 属性，可以设置 HTTP 请求的时限：xhr.timeout = 3000 
         - 与之配套的还有一个timeout 事件，用来指定回调函数：xhr.ontimeout = function(event){alert('请求超时！')}
      - 可以使用 FormData 对象管理表单数据
      - 可以上传文件

          - 定义UI结构
          - 验证是否选择了文件
          - 向FormData中追加文件
          - 使用xhr发起上传文件的请求
          - 监听onreadystatechage事件
      - 可以获得数据传输的进度信息

          - 可以通过监听 xhr.upload.onprogress 事件，来获取到文件的上传进度

 **5.jQuery高级用法**

  - 定义UI结构
  - 验证是否选择了文件
  - 向FormData中追加文件
  - 使用jQuery发起上传文件的请求
  - jQuery实现loading效果

       - ajaxStart（callback）：Ajax 请求开始时，执行 ajaxStart 函数。可以在 ajaxStart 的 callback 中显示 loading 效果
       - ajaxStop(callback)：Ajax 请求结束时，执行 ajaxStop 函数。可以在 ajaxStop 的 callback 中隐藏 loading 效果

**6.axios**

  - Axios 是专注于网络数据请求的库
  - 相比于原生的 XMLHttpRequest 对象，axios 简单易用
  - 相比于 jQuery，axios 更加轻量化，只专注于网络数据请求
  - axios发起GET请求

      - 语法：axios.get('url', { params: { /*参数*/ } }).then(callback)

  - axios发起POST请求

      - axios.post('url', { /*参数*/ }).then(callback)

  - 直接使用axios发起请求

      - axios 也提供了类似于 jQuery 中 $.ajax() 的函数
      - 语法：axios({method: '请求类型',url: '请求的URL地址',data: { /* POST数据 */ },params: { /* GET参数 */ }}) .then(callback)

# Day04 #

## 跨域和JSONP ##

**1.了解同源策略和跨域**

  - 同源策略

     - 同源：如果两个页面的协议，域名和端口都相同，则两个页面具有相同的源
     - 同源策略（英文全称 Same origin policy）是浏览器提供的一个安全功能 浏览器规定，A 网站的 JavaScript，不允许和非同源的网站 C 之间，进行资源的交互
     - 无法读取非同源网页的 Cookie、LocalStorage 和 IndexedDB
     - 无法接触非同源网页的 DOM
     - 无法向非同源地址发送 Ajax 请求

  - 跨域

     - 同源指的是两个 URL 的协议、域名、端口一致，反之，则是跨域
     - 出现跨域的根本原因：浏览器的同源策略不允许非同源的 URL 之间进行资源的交互
     - 浏览器允许发起跨域请求，但是，跨域请求回来的数据，会被浏览器拦截，无法被页面获取到
     - 实现跨域数据请求，最主要的两种解决方案，分别是 JSONP 和 CORS
     - JSONP：出现的早，兼容性好（兼容低版本IE）。是前端程序员为了解决跨域问题，被迫想出来的一种临时解决方案。缺点是只支持 GET 请求，不支持 POST 请求
     - CORS：出现的较晚，它是 W3C 标准，属于跨域 Ajax 请求的根本解决方案。支持 GET 和 POST 请求。缺点是不兼容某些低版本的浏览器

**2.JSONP**

  - JSONP (JSON with Padding) 是 JSON 的一种“使用模式”，可用于解决主流浏览器的跨域数据访问的问题
  - 实现原理：由于浏览器同源策略的限制，网页中无法通过 Ajax 请求非同源的接口数据。但是 `<script>` 标签不受浏览器同源策略的影响，可以通过 src 属性，请求非同源的 js 脚本 因此，JSONP 的实现原理，就是通过 `<script>` 标签的 src 属性，请求跨域的数据接口，并通过函数调用的形式，接收跨域接口响应回来的数据
  - JSONP的缺点：由于 JSONP 是通过 `<script>` 标签的 src 属性，来实现跨域数据获取的，所以，JSONP 只支持 GET 数据请求，不支持 POST 请求
  - JSONP 和 Ajax 之间没有任何关系，不能把 JSONP 请求数据的方式叫做 Ajax，因为 JSONP 没有用到XMLHttpRequest 这个对象
  - jQuery中的JSONP

      - jQuery 提供的 $.ajax() 函数，除了可以发起真正的 Ajax 数据请求之外，还能够发起 JSONP 数据请求
      - 默认情况下，使用 jQuery 发起 JSONP 请求，会自动携带一个 callback=jQueryxxx 的参数，jQueryxxx 是随机生成的一个回调函数名称

  - 自定义参数及回调函数名称

      - 在使用 jQuery 发起 JSONP 请求时，如果想要自定义 JSONP 的参数以及回调函数名称，可以通过如下两个参数来指定 jsonp: 'callback'  jsonpCallback: 'abc'

 - jQuery中JSONP的实现过程

      - jQuery 中的 JSONP，也是通过 `<script> `标签的 src 属性实现跨域数据访问的，只不过，jQuery 采用的是动态创建和移除 `<script>` 标签的方式，来发起 JSONP 数据请求
      - 在发起 JSONP 请求的时候，动态向 `<header>` 中 append 一个 `<script>` 标签
      - 在 JSONP 请求成功以后，动态从 `<header>` 中移除刚才append 进去的 `<script>` 标签

**4.节流和防抖**

  - 节流阀

     - 节流阀为空，表示可以执行下次操作；不为空，表示不能执行下次操作
     - 当前操作执行完，必须将节流阀重置为空，表示可以执行下次操作了
     - 每次执行操作前，必须先判断节流阀是否为空

  - 防抖：如果事件被频繁触发，防抖能保证只有最有一次触发生效！前面 N 多次的触发都会被忽略
  - 节流：如果事件被频繁触发，节流能够减少事件触发的频率，因此，节流是有选择性地执行一部分事件

#Day 05#

## HTTP协议加强 ##

**1.HTTP协议简介**

  - 通信

      - 就是信息的传递和交换
      - 三要素：通信的主体 通信的内容 通信的方式
      
  - 通信协议：通信协议（Communication Protocol）是指通信的双方完成通信所必须遵守的规则和约定 
      - 客户端与服务器之间要实现网页内容的传输，则通信的双方必须遵守网页内容的传输协议
      - 网页内容又叫做超文本，因此网页内容的传输协议又叫做超文本传输协议（HyperText Transfer Protocol） ，简称 HTTP 协议

  - HTTP 协议
   
    - 即超文本传送协议 (HyperText TransferProtocol) ，它规定了客户端与服务器之间进行网页内容传输时，所必须遵守的传输格式
    - 客户端要以HTTP协议要求的格式把数据提交到服务器 服务器要以HTTP协议要求的格式把内容响应给客户端

**2.HTTP请求消息**

  - 由于 HTTP 协议属于客户端浏览器和服务器之间的通信协议。因此，客户端发起的请求叫做 HTTP 请求，客户端发送到服务器的消息，叫做 HTTP 请求消息
  - 注意：HTTP 请求消息又叫做 HTTP 请求报文
  - 组成部分：
   
    - 请求行（request line）

         - 请求行由请求方式、URL 和 HTTP 协议版本 3 个部分组成，他们之间使用空格隔开
    - 请求头部（ header ） 

         - 请求头部用来描述客户端的基本信息，从而把客户端相关的信息告知服务器
         - User-Agent 用来说明当前是什么类型的浏览器 
         - Content-Type 用来描述发送到服务器的数据格式
         - Accept 用来描述客户端能够接收什么类型的返回内容
         - Accept-Language 用来描述客户端期望接收哪种人类语言的文本内容
         - 请求头部由多行 键/值对 组成，每行的键和值之间用英文的冒号分隔
    - 空行 

         - 最后一个请求头字段的后面是一个空行，通知服务器请求头部至此结束
         - 请求消息中的空行，用来分隔请求头部与请求体
    - 请求体 

         - 请求体中存放的，是要通过 POST 方式提交到服务器的数据
         - 注意：只有 POST 请求才有请求体，GET 请求没有请求体

**3.HTTP响应消息**

  - 响应消息就是服务器响应给客户端的消息内容，也叫作响应报文
  - 组成部分

      - 状态行

          - 状态行由 HTTP 协议版本、状态码和状态码的描述文本 3 个部分组成，他们之间使用空格隔开

      - 响应头部

          - 响应头部用来描述服务器的基本信息。响应头部由多行 键/值对 组成，每行的键和值之间用英文的冒号分隔

      - 空行

          - 在最后一个响应头部字段结束之后，会紧跟一个空行，用来通知客户端响应头部至此结束
          - 响应消息中的空行，用来分隔响应头部与响应体

      - 响应体

          - 响应体中存放的，是服务器响应给客户端的资源内容

**4.HTTP请求方法**

  - HTTP 请求方法，属于 HTTP 协议中的一部分，请求方法的作用是：用来表明要对服务器上的资源执行的操作。最常用的请求方法是 GET 和 POST
  - GET：(查询)发送请求来获得服务器上的资源，请求体中不会包含请求数据，请求数据放在协议头中
  - POST：(新增)向服务器提交资源（例如提交表单或上传文件）。数据被包含在请求体中提交给服务器
  - PUT：(修改)向服务器提交资源，并使用提交的新资源，替换掉服务器对应的旧资源
  - DELETE：(删除)请求服务器删除指定的资源

**5.HTTP响应状态码**

  - HTTP 响应状态码（HTTP Status Code），也属于 HTTP 协议的一部分，用来标识响应的状态
  - 响应状态码会随着响应消息一起被发送至客户端浏览器，浏览器根据服务器返回的响应状态码，就能知道这次HTTP 请求的结果是成功还是失败了
  - HTTP 状态码由三个十进制数字组成，第一个十进制数字定义了状态码的类型，后两个数字用来对状态码进行细分
  - 分类

      - 1** ：信息，服务器收到请求，需要请求者继续执行操作（实际开发中很少遇到 1** 类型的状态码）
      - 2** ：成功，操作被成功接收并处理

         - 2** 范围的状态码，表示服务器已成功接收到请求并进行处理
         - 200：英文名称OK 请求成功 已创建 成功请求并创建了新的资源，通常用于 POST 或 PUT 请求一般用于 GET 与 POST 请求
         - 201：Created 
      - 3** ：重定向，需要进一步的操作以完成请求

         - 3** 范围的状态码，表示表示服务器要求客户端重定向，需要客户端进一步的操作以完成资源的请求
         - 301：Moved Permanently 永久移动。请求的资源已被永久的移动到新URL，返回信息会包括新的URL，浏览器会自动定向到新URL。今后任何新的请求都应使用新的URL代替
         - 302：Found 临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI
         - 304：Not Modified 未修改。所请求的资源未修改，服务器返回此状态码时，不会返回任何资源（响应消息中不包含响应体）。客户端通常会缓存访问过的资源
      - 4** ：客户端错误，请求包含语法错误或无法完成请求

         - 4** 范围的状态码，表示客户端的请求有非法内容，从而导致这次请求失败
         - 400：Bad Request 

             - 语义有误，当前请求无法被服务器理解。除非进行修改，否则客户端不应该重复提交这个请求
             - 请求参数有误

         - 401：Unauthorized 当前请求需要用户验证
         - 403：Forbidden 服务器已经理解请求，但是拒绝执行它
         - 404：Not Found 服务器无法根据客户端的请求找到资源（网页）
         - 408：Request Timeout 请求超时。服务器等待客户端发送的请求时间过长，超时
      - 5** ：服务器错误，服务器在处理请求的过程中发生了错误

         - 5** 范围的状态码，表示服务器未能正常处理客户端的请求而出现意外错误
         - 500：Internal Server Error 服务器内部错误，无法完成请求
         - 501：Not Implemented 服务器不支持该请求方法，无法完成请求。只有 GET 和 HEAD 请求方法是要求每个服务器必须支持的，其它请求方法在不支持的服务器上会返回501
         - 503：Service Unavailable 由于超载或系统维护，服务器暂时的无法处理客户端的请求

# Day 06 #
## Git ##

**1.起步**

  - 版本控制软件：版本控制软件是一个用来记录文件变化，以便将来查阅特定版本修订情况的系统，因此有时也叫做“版本控制系统”
  - 把手工管理文件版本的方式，改为由软件管理文件的版本；这个负责管理文件版本的软件，叫做“版本控制软件”
  - 使用版本控制软件的好处

       - 操作简便：只需识记几组简单的终端命令，即可快速上手常见的版本控制软件
       - 易于对比：基于版本控制软件提供的功能，能够方便地比较文件的变化细节，从而查找出导致问题的原因
       - 易于回溯：可以将选定的文件回溯到之前的状态，甚至将整个项目都回退到过去某个时间点的状态
       - 不易丢失：在版本控制软件中，被用户误删除的文件，可以轻松的恢复回来
       - 协作方便：基于版本控制软件提供的分支功能，可以轻松实现多人协作开发时的代码合并操作

  - 版本控制系统的分类

      - 分布式版本控制系统：联网运行，支持多人协作开发；性能优秀、用户体验好

          - 特点：基于服务器、客户端的运行模式；服务器保存文件的所有更新版本；客户端是服务器的完整备份，并不是只保留文件的最新版本
          - 优点：联网运行，支持多人协作开发；客户端断网后支持离线本地提交版本更新；服务器故障或损坏后，可使用任何一个客户端的备份进行恢复
      - 集中化的版本控制系统：联网运行，支持多人协作开发；性能差、用户体验不好

          - 特点：基于服务器、客户端的运行模式；服务器保存文件的所有更新记录；客户端只保留最新的文件版本
          - 优点：联网运行，支持多人协作开发
          - 缺点：不支持离线提交版本更新；中心服务器崩溃后，所有人无法正常工作；版本数据库故障后，所有历史更新记录会丢失
      - 本地版本控制系统：单机运行，使维护文件版本的操作工具化

          - 特点：使用软件来记录文件的不同版本，提高了工作效率，降低了手动维护版本的出错率
          - 缺点：单机运行，不支持多人协作开发；版本数据库故障后，所有历史更新记录会丢失

  - Git

      - Git 是一个开源的分布式版本控制系统，是目前世界上最先进、最流行的版本控制系统。可以快速高效地处理从很小到非常大的项目版本管理
      - 特点：：项目越大越复杂，协同开发者越多，越能体现出 Git 的高性能和高可用性
      - 特点

         - 直接记录快照，而非差异比较

             - Git 快照是在原有文件版本的基础上重新生成一份新的文件，类似于备份为了效率，如果文件没有修改，Git不再重新存储该文件，而是只保留一个链接指向之前存储的文件

             - 缺点：占用磁盘空间较大
             - 优点：版本切换时非常快，因为每个版本都是完整的文件快照，切换版本时直接恢复目标版本的快照即可
             - 特点：空间换时间

         - 近乎所有操作都是本地执行

              - 在 Git 中的绝大多数操作都只需要访问本地文件和资源，一般不需要来自网络上其它计算机的信息
              - 特性：断网后依旧可以在本地对项目进行版本管理；联网后，把本地修改的记录同步到云端服务器即可

      - 使用 Git 管理的项目，拥有三个区域，分别是工作区、暂存区、Git 仓库
      - Git中的三种状态

         - 已修改 modified：表示修改了文件，但还没将修改的结果放到暂存区
         - 已暂存 staged：表示对已修改文件的当前版本做了标记，使之包含在下次提交的列表中
         - 已提交 committed：表示文件已经安全地保存在本地的 Git 仓库中
         - 工作区的文件被修改了，但还没有放到暂存区，就是已修改状态
         - 如果文件已修改并放入暂存区，就属于已暂存状态
         - 如果 Git 仓库中保存着特定版本的文件，就属于已提交状态

     - 基本的Git工作流程

         - 在工作区中修改文件
         - 将你想要下次提交的更改进行暂存
         - 提交更新，找到暂存区的文件，将快照永久性存储到 Git 仓库

**2.Git基础**

  - 获取Git仓库的两种方式

     - 将尚未进行版本控制的本地目录转换为 Git 仓库
     - 从其它服务器克隆一个已存在的 Git 仓库

  - 在现有目录中初始化仓库

     - 在项目目录中，通过鼠标右键打开“Git Bash”
     - 执行 git init 命令将当前的目录转化为 Git 仓库
     - git init 命令会创建一个名为 .git 的隐藏目录，这个 .git 目录就是当前项目的 Git 仓库，里面包含了初始的必要文件，这些文件是 Git 仓库的必要组成部分

  - 工作区中文件的4种状态

     - 未跟踪 Untracked：不被 Git 所管理的文件
     - 未修改（Unmodified）：工作区中文件的内容和 Git 仓库中文件的内容保持一致
     - 已修改（Modified）：工作区中文件的内容和 Git 仓库中文件的内容不一致
     - 已暂存（Staged）：工作区中被修改的文件已被放到暂存区，准备将修改后的文件保存到 Git 仓库中

  - 检查文件的状态
   
    - 可以使用 git status 命令查看文件处于什么状态
    - 在状态报告中可以看到新建的 index.html 文件出现在Untracked files（未跟踪的文件） 下面
    - 未跟踪的文件意味着 Git 在之前的快照（提交）中没有这些文件；Git 不会自动将之纳入跟踪范围，除非明确地告诉它“我需要使用 Git 跟踪管理该文件”

  - 以精简的方式显示文件状态

    - 如果希望以精简的方式显示文件的状态，其中 -s 是 --short 的简写形式

         - git status -s
         - git status --short
         - 未跟踪文件前面有红色的 ?? 标记

  - 跟踪新文件

     - 使用命令 git add 开始跟踪一个文件。 所以，要跟index.html 文件，运行如下的命令即可：git add index.html
     - 此时再运行 git status 命令，会看到 index.html 文件在 Changes to be committed 这行的下面，说明已被跟踪，并处于暂存状态
     - 以精简的方式显示文件的状态：新添加到暂存区中的文件前面有绿色的 A 标记

  - 提交更新

     - 现在暂存区中有一个 index.html 文件等待被提交到 Git 仓库中进行保存。可以执行 git commit 命令进行提交,其中 -m 选项后面是本次的提交消息，用来对提交的内容做进一步的描述
     - 证明工作区中所有的文件都处于“未修改”的状态，没有任何文件需要被提交

  - 对已提交的文件进行修改

     - 目前，index.html 文件已经被 Git 跟踪，并且工作区和 Git 仓库中的 index.html 文件内容保持一致。当我们修改了工作区中 index.html 的内容之后，再次运行 git status 和 git status -s 命令
     - 文件 index.html 出现在 Changes not staged for commit 这行下面，说明已跟踪文件的内容发生了变化，但还没有放到暂存区
     - 注意：修改过的、没有放入暂存区的文件前面有红色的 M 标记

  - 暂存已修改的文件

     - 目前，工作区中的 index.html 文件已被修改，如果要暂存这次修改，需要再次运行 git add 命令，这个命令是个多功能的命令，主要有如下 3 个功效

         - 可以用它开始跟踪新文件
         - 把已跟踪的、且已修改的文件放到暂存区
         - 把有冲突的文件标记为已解决状态

      - 绿色的M表示文件已修改且已放入暂存区中

  - 提交已暂存的文件

     - 再次运行 git commit -m "提交消息" 命令，即可将暂存区中记录的 index.html 的快照，提交到 Git 仓库中进行保存

  - 撤销对文件的修改

     - 撤销对文件的修改指的是：把对工作区中对应文件的修改，还原成 Git 仓库中所保存的版本
     - 操作的结果：所有的修改会丢失，且无法恢复！危险性比较高，请慎重操作
     - 撤销操作的本质：用 Git 仓库中保存的文件，覆盖工作区中指定的文件
     - 使用 git checkout -- index.html命令 撤销对文件的修改

  - 向暂存区中一次性添加多个文件

     - 如果需要被暂存的文件个数比较多，可以使用如下的命令，一次性将所有的新增和修改过的文件加入暂存区： git add .
     - 今后在项目开发中，会经常使用这个命令，将新增和修改过后的文件加入暂存区

  - 取消暂存的文件

     - 如果需要从暂存区中移除对应的文件，可以使用如下的命令：git reset HEAD 要移除的文件名称

  - 跳过使用暂存区域

     - Git 标准的工作流程是工作区 → 暂存区 → Git 仓库，但有时候这么做略显繁琐，此时可以跳过暂存区，直接将工作区中的修改提交到 Git 仓库，这时候 Git 工作的流程简化为了工作区 → Git 仓库
     - Git 提供了一个跳过使用暂存区域的方式， 只要在提交的时候，给 git commit 加上 -a 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤
     - 语法：git commit -a -m “描述信息”

  - 移除文件

     - 从 Git 仓库和工作区中同时移除对应的文件

         - 语法： git rm -f 文件名

     - 只从 Git 仓库中移除指定的文件，但保留工作区中对应的文件

         - 语法：git rm --cached 文件名

  - 忽略文件

     - 一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。 在这种情况下，我们可以创建一个名为 .gitignore 的配置文件，列出要忽略的文件的匹配模式
     - 文件 .gitignore 的格式规范如下

         - 以 # 开头的是注释
         - 以 / 结尾的是目录
         - 以 / 开头防止递归
         - 以 ! 开头表示取反
         - 可以使用 glob 模式进行文件和文件夹的匹配（glob 指简化了的正则表达式）

  - glob模式

     - 星号 * 匹配零个或多个任意字符
     - [abc] 匹配任何一个列在方括号中的字符 （此案例匹配一个 a 或匹配一个 b 或匹配一个 c）
     - 问号 ? 只匹配一个任意字符
     - 在方括号中使用短划线分隔两个字符， 表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到 9 的数字）
     - 两个星号 ** 表示匹配任意中间目录（比如 a/**/z 可以匹配 a/z 、 a/b/z 或 a/b/c/z 等）

  - .gitignore文件的例子

     - 忽略所有的.a文件：*.a
     - 但跟踪所有的lib.a 即便你在前面忽略了.a文件：！lib.a
     - 之忽略当前目录下的TODO文件 而不忽略subdir/TODO：/TODO
     - 忽略任何目录下名为build的文件夹：build/
     - 忽略doc/notes.txt 但不忽略子目录下的.txt：doc/*.txt
     - 忽略doc/目录及其所有子目录下的.pdf文件：doc/**/*pdf
  - 查看提交历史

     - 如果希望回顾项目的提交历史，可以使用 git log 这个简单且有效的命令
     - 只展示最新的n条提交历史：git log -n
     - 在一行上展示最近n条提交历史：git log -n --pretty=oneline
     - 在一行上展示最近n条提交历史并自定义输出的格式：git log -n --pretty=format:""

          - %h 提交的简写哈希值
          - %an 作者名字
          - %ar 作者修订日期 按多久以前的方式显示
          - %s 提交说明

  - 回退到指定的版本

     - 在一行上展示所有的提交历史：git log --pretty=oneline
     - 根据指定的提交ID回退到指定版本：git reset --hard<CommitID>
     - 在就版本中 查看命令操作的历史：git reflog --pretty=oneline
     - 再次根据最新提交的ID 跳转到最新的版本：git reset --hard<CommitID>

**3.Github**

  - 开源

      - 开源即开放源代码 代码是公开的 任何人都可以去查看修改和使用开源代码
      - 闭源则软件的代码是封闭的 只有作者能看到闭源软件的代码 只有作者能对源代码进行修改 

  - 开源许可协议：开源并不意味着完全没有限制，为了限制使用者的使用范围和保护作者的权利，每个开源项目都应该遵守开源许可协议（ Open Source License ）

      - BSD（Berkeley Software Distribution）
      - Apache Licence 2.0
      - GPL（GNU General Public License）

          - 具有传染性的一种开源协议，不允许修改后和衍生的代码做为闭源的商业软件发布和销售
          - 使用 GPL 的最著名的软件项目是：Linux

      - LGPL（GNU Lesser General Public License）
      - MIT（Massachusetts Institute of Technology, MIT）

          - 是目前限制最少的协议，唯一的条件：在修改后的代码或者发行包中，必须包含原作者的许可信息
          - 使用 MIT 的软件项目有：jquery、Node.js

  - 开源项目托管平台

       - 专门用于免费存放开源项目源代码的网站，叫做开源项目托管平台
       - Github（全球最牛的开源项目托管平台，没有之一）
       - Gitlab（对代码私有性支持较好，因此企业用户较多）
       - Gitee（又叫做码云，是国产的开源项目托管平台。访问速度快、纯中文界面、使用友好）
       - 以上 3 个开源项目托管平台，只能托管以 Git 管理的项目源代码，因此，它们的名字都以 Git 开头

  - Github远程仓库的使用

       - Github 上的远程仓库，有两种访问方式，分别是 HTTPS 和 SSH
       - HTTPS：零配置；但是每次访问仓库时，需要重复输入 Github 的账号和密码才能访问成功
       - SSH：需要进行额外的配置；但是配置成功后，每次访问仓库时，不需重复输入 Github 的账号和密码
       - 注意：在实际开发中，推荐使用 SSH 的方式访问远程仓库

       -  SSH key

         - 作用：实现本地仓库和 Github 之间免登录的加密数据传输
         - 好处：免登录身份认证、数据加密传输
         - 组成部分：id_rsa（私钥文件，存放于客户端的电脑中即可）和id_rsa.pub（公钥文件，需要配置到 Github 中）

       - 生成 SSH Key

         - 打开 Git Bash
         - 粘贴如下的命令，并将 your_email@example.com 替换为注册 Github 账号时填写的邮箱：ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
         - 连续敲击 3 次回车，即可在 C:\Users\用户名文件夹\.ssh 目录中生成 id_rsa 和 id_rsa.pub 两个文件

       - 配置SSH Key
       - 检测GitHub中的SSH Key是否配置成功

          - 打开Git Bash 输入如下命令并回车执行：ssh -T git@github.com

       - 基于SSH将本地仓库上传到Github
       - 将远程仓库克隆到本地

          - 打开Git Bash 输入如下的命令并回车执行：git clone 远程仓库的地址

**4.Git分支**

  - 在初始化本地 Git 仓库的时候，Git 默认已经帮我们创建了一个名字叫做 master 的分支。通常我们把这个master 分支叫做主分支
  - 在实际工作中，master 主分支的作用是：用来保存和记录整个项目已完成的功能代码
  - 由于程序员不能直接在 master 分支上进行功能的开发，所以就有了功能分支的概念 功能分支指的是专门用来开发新功能的分支，它是临时从 master 主分支上分叉出来的，当新功能开发且测试完毕后，最终需要合并到 master 主分支上

  - 本地分支操作
    - 查看分支列表
   
      - git branch  注意：分支名字前面的 * 号表示当前所处的分支
   - 创建新分支
   
      - 使用如下的命令，可以基于当前分支，创建一个新的分支，此 时，新分支中的代码和当前分支完全一样：git branch 分支名称
   - 切换分支
  
      - 使用如下的命令，可以切换到指定的分支上进行开发：git checkout 分支名称
   - 分支的快速创建和切换

      - 使用如下的命令，可以创建指定名称的新分支，并立即切换到新分支上
      - git checkout -b
      - "git checkout -b 分支名称" 是下面两条命令的简写形式：① git branch 分支名称 ② git checkout 分支名称

   - 合并分支

      - 功能分支的代码开发测试完毕之后，可以使用如下的命令，将完成后的代码合并到 master 主分支上
      - git checkout master
      - git merge login
      - 合并分支时的注意点：假设要把 C 分支的代码合并到 A 分支，则必须先切换到 A 分支上，再运行 git merge 命令，来合并 C 分支

   - 删除分支

      - 当把功能分支的代码合并到 master 主分支上以后，就可以使用如下的命令，删除对应的功能分支：git branch -d 分支名称

   - 遇到冲突时的分支合并

      - 如果在两个不同的分支中，对同一个文件进行了不同的修改，Git 就没法干净的合并它们。 此时，我们需要打开这些包含冲突的文件然后手动解决冲突
      - 解决冲突之后再执行如下的命令：git add . 和 git commit -m “解决了分支合并冲突的问题”

  - 远程分支操作

      - 将本地分支推送到远程仓库

         - 如果是第一次将本地分支推送到远程仓库，需要运行如下的命令： git push -u 远程仓库的别名 本地分支名称：远程分支名称 
         - 如果希望远程分支的名称和本地分支名称保持一致 可以对命令进行简化：git push -u origin payment
         - 第一次推送分支需要带 -u 参数，此后可以直接使用 git push 推送代码到远程分支

      - 查看远程仓库中所有的分支列表

         - git remote show 远程仓库名称

      - 跟踪分支
      
         - 跟踪分支指的是：从远程仓库中，把远程分支下载到本地仓库中 需要运行的命令如下：
         - 从远程仓库中 把对应的远程分支下载到本地仓库 保持本地分支和远程分支名称相同：git checkout 远程分支的名称
         - 从远程仓库中 把对应的远程分支下载到本地仓库 并把下载的本地分支进行重命名：git checkout -b 本地分支名称 远程仓库名称/远程分支名称

      - 拉取远程分支的最新的代码


         - git pull

      -  删除远程分支

         - git push 远程仓库名称 --delete 远程仓库名称

             

     
 
     
      
  
  
