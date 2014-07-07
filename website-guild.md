# 无线建站指南 - 5分钟入门

- pubdate: 2014-01-23
- tags: 规范, 指南
- author: 轩与

---
5分钟构建一个无线站点，为了便于大家理解，我们举一个账号登陆页面的例子
## 第一步 新建页面

新建一个文件，把后缀名改成html结尾，用任意一款编辑器打开此html页面，粘贴以下代码
```
	<!DOCTYPE html>
	<html>
	<head>
	<meta charset="utf-8">
    <title></title>
    <meta name="apple-mobile-web-app-capable" content="yes"/>
    <meta name="apple-mobile-web-app-status-bar-style" content="black"/>
    <meta name="format-detection" content="telephone=no"/>
    <meta name="format-detection" content="email=no"/>
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=0"/>
	</head>
	<body>
	</body>
	</html>
```
### *注意事项*

1. 页面中utf-8的编码需要放在头部第一行
2. 对于telephone和email视页面中是否需要
3. viewport建议使用该配置，如果需要修改，建议[参考文档](https://developer.apple.com/library/ios/documentation/appleapplications/reference/safariwebcontent/usingtheviewport/usingtheviewport.html)

## 第二步 加入CSS样式

光秃秃的页面非常不好看，为此我们设计了一个完整的UI，提供了各类丰富的组件，只要简单地引入一个CSS链接即可.在viewport标签下引入一个CSS地址，参考代码如下

```
	<!DOCTYPE html>
	<html>
	<head>
	<meta charset="utf-8">
    <title></title>
    <meta name="apple-mobile-web-app-capable" content="yes"/>
    <meta name="apple-mobile-web-app-status-bar-style" content="black"/>
    <meta name="format-detection" content="telephone=no"/>
    <meta name="format-detection" content="email=no"/>
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=0"/>
    <link rel="stylesheet" type="text/css" href="https://a.alipayobjects.com/amui/dpl/1.0.2/amui.css" media="all"/>
	</head>
	<body>
	</body>
	</html>
```

引入该css之后，就可以开始进行布局和设计各种控件类型了，具体内容可以参考如下[文档地址](http://aliceui.org/mobile/openapi.html)

登陆页面需要一个用户名和密码的输入列表，我们在amui中找到相应的控件，将其html贴入页面中，示例代码如下
```
	<!DOCTYPE html>
	<html>
	<head>
	<meta charset="utf-8">
    <title></title>
    <meta name="apple-mobile-web-app-capable" content="yes"/>
    <meta name="apple-mobile-web-app-status-bar-style" content="black"/>
    <meta name="format-detection" content="telephone=no"/>
    <meta name="format-detection" content="email=no"/>
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=0"/>
	</head>
	<body>
	</body>
	</html>
```
### *注意事项*

1. 页面中utf-8的编码需要放在头部第一行
2. 对于telephone和email视页面中是否需要
3. viewport建议使用该配置，如果需要修改，建议[参考文档](https://developer.apple.com/library/ios/documentation/appleapplications/reference/safariwebcontent/usingtheviewport/usingtheviewport.html)

登陆页面需要一个用户名和密码的输入列表，我们在amui中找到相应的控件，将其html贴入页面中，示例代码如下
```
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>演示示例</title>
        <meta name="apple-mobile-web-app-capable" content="yes"/>
        <meta name="apple-mobile-web-app-status-bar-style" content="black"/>
        <meta name="format-detection" content="telephone=no"/>
        <meta name="format-detection" content="email=no"/>
        <meta name="viewport"
              content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=0"/>
        <link rel="stylesheet" type="text/css" href="https://a.alipayobjects.com/amui/dpl/1.0.2/amui.css" media="all"/>
        <style>
            .am-list{
                margin: 20px;
            }
            .button-grps{
                margin: 20px;
            }
        </style>
    </head>
    <body>
    <div class="am-header">
        <h1>用户登录</h1>
        <a href="#" class="am-header-reverse am-header-reverse-btn">返回</a>
        <a href="#" class="am-header-operate am-header-operate-btn">注册</a>
    </div>
    <div class="am-list">
        <div class="am-list-item am-list-item-form am-flexbox">
            <div class="am-flexbox-item">
                <input type="text" placeholder="手机号/会员名" value="">
            </div>
        </div>
        <div class="am-list-item am-list-item-form am-flexbox">
            <div class="am-flexbox-item">
                <input type="text" placeholder="登录密码" value="">
            </div>
        </div>
    </div>
    <div class="am-flexbox am-flexbox-average button-grps">
        <div class="am-flexbox-item ">
            <button type="button" class="am-button am-button-white">忘记密码</button>
        </div>
        <div class="am-flexbox-item">
            <button type="button" class="am-button am-button-blue">登录</button>
        </div>
    </div>
    </body>
    </html>
```
 登陆页面就好了，效果图如下：
 ![登陆效果图](https://i.alipayobjects.com/i/localhost/jpg/201406/2n4ibcN40L.jpg)
 一个完整的页面已经呈现在我们面前了

## 第三步 加入脚本

 当页面都完成之后，接下来就需要加入务逻辑了，让这个页面能够响应用户的操作，这时候，就需要javascript出场了，在PC时候，用的最多的是jQuery，它的好处毋庸置疑，在移动端，有个类似的类库叫Zepto，功能强大，并且简单易用，兼容jQuery常用API。以下是它的地址：[zeptojs](http://zeptojs.com)。

 通过zepto的api，在各个按钮上加上事件，整个页面就此完成

 *移动端做页面就那么简单!*