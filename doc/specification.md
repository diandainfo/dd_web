
# 编码规范

## 前端编码规范
### 1. 规范的规范
- 以下JavaScript中:
  - 以 `// - ` 开头的注释为 `注释的注释`，即说明此部分注释、代码应该写明的内容
  - `注释的注释` 下的代码为 `示例代码` ，其中包括 `代码` 和 `代码的注释` 两部分，格式遵循标准规范，应予以遵循，code review时根据规范确定代码的整洁度
  - `代码的注释` 可在 `代码` 的上一行，亦可在“代码”的行后缀，但不能超出可视范围内 

### 2. JavaScript
- 通用规则
  - 文件名：
    - JavaScript文件名应尽可能的使用一个便于识别该js文件功能的单词（不要使用拼音）,若一个英文单词无法命名，则应进行分层
    - 模块、功能的主文件、入口文件应以“index.js”命名，便于webpack打包压缩和require时读取
  - 大小写：
  - 代码可读性：
    - 单行代码不应超过可视范围内，以 font-size=16 时，字符 **100** 为限
    - 多行代码间，若无明显相关性，应使用单个空行进行分割，便于区分逻辑； `代码` 和 `代码的注释` 之间无需加空行
    
- 文件标准头部，**设置webstorm的js文件模板**
```
/**
 * Created by [创建作者] on [时间].
 * @version [创建版本] created [本JavaScript内容：模块 - 功能 - 操作，如：frame - 下拉购物车 - dom]
 * @version [更新版本] updated by[更新作者] on [更新时间] [更新内容]
 */
 
"use strict";
```
- 全局变量
```
//- 全局变量分为常量、变量、封装构造体、通用函数
 
//- 常量，全大写，应写明该常量的内容
var GRE=<%=user.GRE%>;//用户等级
 
//- 变量，全小写，或通用函数、调用函数
// 拼装dom
var dom=require('./dom');
// 通用函数
var fun1=function(){
    //- 具体逻辑...
}
 
//- 封装结构体，首字母大写，前端模块内封装某层(dom/data/listener/table)
// 拼装table
var Table=(function(){
    //- 具体逻辑...
}());
 
exports.Table=Table;
```

## 参考文档
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