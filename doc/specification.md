
# 编码规范
- **代码优雅、追求卓越**
- 相关书籍，公司已有实体书
  - 《javascript语言精粹》
  - 《编写可维护的javascript》
  - 《javascript dom编程艺术》
  - 《高性能JavaScript》

## 一、jsHint配置
- docs
  - 配置说明：[JSHint Documentation](http://jshint.com/docs/)
  - 参数说明：[JSHint Options](http://jshint.com/docs/options/)
- 中文docs：
  > - [JSHint配置项说明](http://www.jianshu.com/p/4cb23f9e19d3)
  > - [JSHint 配置浅析](http://jinlong.github.io/2014/10/25/jshint-configuration/?utm_source=tuicool&utm_medium=referral)
  > - [jshint 配置说明](http://blog.csdn.net/u013261261/article/details/50236651)
- webstorm配置
  - ` git clone https://github.com/diandainfo/dd_web.git ` 到本地
  - ` WebStorm >> Settings >> Languages & Frameworks >> JavaScript >> Code Quality Tools >> JSHint`
    - 选中 `Enable` + `Use config files` 
    - 配置 ` Custom configuration file `，选择上一步下载路径中 `/doc/.jshintrc`
      ![webstorm中配置jshint图示](./.jshintrc.jpeg)
    - apply设定后，查看项目中任意一个js文件，可以看到对应的错误提示和警告  
- 特例配置，开发中遇到以下报错允许单独配置
  - 参考[《JSHint配置项说明》 - 文／9I（简书作者）](http://www.jianshu.com/p/4cb23f9e19d3)
  - 内联配置
    - 除了使用配置文件,您可以在你的文件中使用jshint或者globals开头，并跟着配置项以冒号分隔值列表来配置JSHint。
    - 例如,下面的代码片段将启用警告未定义的和未使用的变量，告诉JSHint全局变量命名MY_GLOBAL1、MY_GLOBAL2。
    
	  ```
      // -jshint- 此处说明以下为jshint的特例注释，即“注释的注释”
      /* jshint undef: true, unused: true */
	  /* globals MY_GLOBAL1,MY_GLOBAL2 */
	  ```
    - 可以使用单行或者多行来配置JSHint，如果放在函数里面，则只影响该函数。
  - JSHint 忽略
    - ignore 告诉jshint忽略一个代码块,在jshint ignore:start和 ignore:end之间的所有代码都将被JSHint忽略
    
      ```
	  // Code here will be linted with JSHint.
	  /* jshint ignore:start */
	  // Code here will be ignored by JSHint.
	  /* jshint ignore:end */
	  ``` 
    - 可以忽略一行:
    
      ```
	  ignoreThis(); // jshint ignore:line
	  ```

## 二、前端编码规范
### 1. 规范的规范
- 以下：
  - **实义** : 即为与业务相关联，而非技术关键词；如商品信息表，使用 `goods-info` 而非 `list-table` 
- 以下JavaScript中:
  - 以 `// - ` 开头的注释为 `注释的注释`，即说明此部分注释、代码应该写明的内容
  - `注释的注释` 下的代码为 `示例代码` ，其中包括 `代码` 和 `代码的注释` 两部分，格式遵循标准规范，应予以遵循，code review时根据规范确定代码的整洁度
  - `代码的注释` 可在 `代码` 的上一行，亦可在“代码”的行后缀，但不能超出可视范围内 
  - `反例`、`反模式` 中说明的为违反规范的例子，请注意不要使用

### 2. 工具的规范
- #### svn的使用
  > # 先下载，后上传 ！
- #### 开发工具
   - ##### 快捷键
   - ##### wakatime插件

### 4. Html
- **基于HTML5进行实现**
- 所有的target标签需小写
- 使用语义化标签

### 6. JavaScript
- **高内聚，低耦合**
  > - [什么是高内聚、低耦合？](http://www.cnblogs.com/robnetcn/archive/2012/04/15/2449008.html)
  > - [图解7种耦合关系](https://zhuanlan.zhihu.com/p/22281389)
  > - [如何使JS代码达到低耦合，高内聚？](https://www.zhihu.com/question/35527487)
  > - [程序员们总说的代码要优雅，这个优雅到底指什么？](https://www.zhihu.com/question/33320738)
- #### 模块化与复用
  - 相同逻辑代码不允许出现两次
    - 严格控制局部变量的使用范围
    - 常量的声明范围

- IDE的提示
  - **单词拼写错误（绿色波浪下划线）**
  - 代码提交前必须进行`格式化`
  - 注意IDE（webStorm）的提示和报错信息
  - 注意JSHint的提示和报错信息
- 通用规则
  - 文件名：
    - JavaScript文件名应尽可能的使用一个便于识别该js文件功能的英文单词（不要使用拼音）,若一个英文单词无法命名，则应进行分层，如：`goodsInfo.js` 拆分为 `goods/info/index.js`
    - 模块、功能的主文件、入口文件应以“index.js”命名，便于webpack打包压缩和require时读取
  - 大小写：

    |用法|首字母|后缀（单词间连接）|
    |:--|--:|--:|
    |常量|大写|大写|
    |变量|小写|驼峰|
    |方法、函数|小写|驼峰|
    |对象|大写|驼峰|
    |id选择器|小写|_|
    |class选择|小写|-|

  - 代码可读性：
    - 单行代码不应超过可视范围内，以 font-size=16 时，字符 **100** 为限
    - 多行代码间，若无明显相关性，应使用单个空行进行分割，便于区分逻辑； `代码` 和 `代码的注释` 之间无需加空行
    - 使用`三目运算符`（`? :`）
  - 单一权责:
    - 每个function只能进行3个功能的逻辑运行，行数不得超过10行，否则应分拆为闭包函数
- jQuery语法
  - 选择器
    - 同文件出现2次以上的选择器，应使用变量赋值，但应注意input等元素的侦听问题
    - 同文件内出现相同字符串，应使用变量赋值
    - 同文件内出现动态key，超过5个使用for进行初始化，如modal的form中有多个input，reset的触发事件
    - 跨文件，复杂度较高的方法应提取公用方法
    - 选择器链式写法不超过3段链
    - 选择器内不超过3个层级
- #### 注释
  - ##### 文件标准头部，**设置webstorm的js文件模板**
  
    ```
	/**
	 * Created by [创建作者] on [时间].
	 * @version [创建版本] created [本JavaScript内容：模块 - 功能 - 操作，如：frame - 下拉购物车 - dom]
	 * @version [更新版本] updated by[更新作者] on [更新时间] [更新内容]
	 */
	 
	"use strict";
    ```
  - ##### function上要有注释，说明此方法的主要功能
  
    ```
	/**
     * 加载中效果
     * @param boo 默认为false，显示加载块
     */
    var setLoading = function (boo) {
		//- 具体的业务逻辑
	}
    ```
- 全局变量
  - **禁止非必要（即有限作用域）的全局变量**
  - 使用`let`进行变量声明
	```
	//- 全局变量分为常量、变量、封装构造体、通用函数
	
	//- 原则上全局变量只允许存在一个，若需要缓存某个特定值，可重新开辟一个全局变量Object来存放所有的key
	 
	//- 常量，全大写，应写明该常量的内容
	var GRE=<%=user.GRE%>;//用户等级
	 
	//- 变量，全小写，或通用函数、调用函数
	// 拼装dom
	var dom=require('./dom');
	// 通用函数
	var fun1=function(){
	    //- 具体的业务逻辑
	}
	 
	//- 封装结构体，首字母大写，前端模块内封装某层(dom/data/listener/table)
	// 拼装table
	var Table=(function(){
	    //- 具体逻辑...
	}());
	 
	exports.Table=Table;
	```
- 语法
  - dom 
    - dom选择器尽可能的使用id选择器，公用元素监听使用class选择 
    - dom拼接中使用 `'`(单引号)进行连接
    - dom的拼接与ajax获取data相分离，dom拼接应提取抽象类和公用方法 
    - 使用 ` for(var o in Obj){} ` 遍历对象时，必须使用 `hasOwnProperty()` 进行自属性检查
    
      ```
		for (var d in data) {
		    if (data.hasOwnProperty(d)) {
		        //- 具体的业务逻辑
		    }
		}
      ```
  - data
    - ajax应进行error的处理，success中只允许复制，返回或回调只允许在`complete`中完成
  - listener 
	 - 事件绑定使用 jQuery的 `on` ，绑定在ejs中存在的元素中，ajax拼接的元素可在元素拼装完成后进行`on`的监听绑定
	 - 表单事件应使用 `one` 事件进行防重;在ajax的complete中，注意重新绑定一次`one`事件
	 - 不再建议使用`delegate`进行事件绑定
- 安全
  - 表单
    - 表单的提交需要进行前端验证（是否输入内容）和校验（输入内容是否为正确类型）
    - `input`应进行`XSS`等防注入攻击
  - `request` & `response`
    - 后端路由层应进行字段的转换，不允许数据字段直接暴露在页面请求中
    - 请求参数应进行加密和校验

### 8. SCSS/CSS
- 语法:
  - **反例** ： 不允许使用 **!important**
  - 选择器:
    - 选择器的迭代和嵌套尽量在3层以内，如 : table>tbody>tr 
    - 不要使用id、标签选择器，建议使用class选择器
    - class选择器
      - 使用至少两个小写英文实义单词，使用语义化标签
      - 尽量和业务相关联，根据层次关系进行 `a-b`、`b-c`、`c-d`的递进
      - **反例** ： 不要使用`table-tbody`、`tbody-tr` 等毫无业务关联性的标签化class
- sprite:
  - 遵循 8\*8 原则,即sprite图的每个icon的高宽组合应是 8\*8 的倍率（16\*16 ...）
  - 使用icon应使用通用的scss的function来提取sprite对应位置

## 三、参考文档
- Bootstrap
  - [BootCss编码规范](http://codeguide.bootcss.com/#html-syntax)
  - [GitHub : necolas/idiomatic-css](https://github.com/necolas/idiomatic-css)
- Baidu EFE team
  - [编码规范](https://github.com/ecomfe/spec)
  - [前端代码风格工具](https://github.com/ecomfe/fecs/)
- web前端开发
  - [Web Styleguide - Style guide to harmonize HTML, Javascript and CSS / Sass coding style](https://github.com/gionkunz/chartist-js/blob/develop/CODINGSTYLE.md) 
  - [前端编码规范（1）—— 一般规范](http://www.css88.com/archives/5361) 
  - [前端编码规范（2）—— HTML 规范](http://www.css88.com/archives/5364)
  - [前端编码风格规范（3）—— JavaScript 规范](http://www.css88.com/archives/5366)
  - [前端编码规范（4）—— CSS 和 Sass (SCSS) 规范](http://www.css88.com/archives/5505)
- [前端页面规范](http://bj.jjj.qq.com/zt/guifan/index.htm)


# 四、 路线图
- 所有文件的头部注释必须包括（源作者/改动者、创建/更新时间、此文件作用），具体参见 [ >> 注释](#注释) 部分
- 获知开发工具的快捷键，具体参见 [ >> 快捷键](#快捷键) 部分