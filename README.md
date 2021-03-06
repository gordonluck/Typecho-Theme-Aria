# Typecho-Theme-Aria  
> 书写属于自己的篇章  

![screenshot](https://github.com/Siphils/Typecho-Theme-Aria/blob/master/screenshot.png?raw=true)
***  
## 使用方法
### Typecho版本  
`Typecho 1.1/17.10.30` 版本下测试正常  
### 安装
1.下载  
2.文件夹命名为`Aria`并上传到`/usr/themes/`目录  
3.后台启用  
### 导航栏配置  
需要按照如下方式填写配置信息  
```json  
{
    "text": "首页",
    "href": "#",
    "icon": "icon-aria-home"
},
{
    "text": "归档",
    "href": "#",
    "icon": "icon-aria-archives",
    "sub": [
        {
            "text": "子菜单1",
            "href": "",
            "icon": ""
        },
        {
            "text": "子菜单2",
            "href": "",
            "icon": ""
        }
    ]
},
{
    "text": "朋友",
    "href": "#",
    "icon": "icon-aria-friends"
},
{
    "text": "留言",
    "href": "#",
    "icon": "icon-aria-guestbook"
},
{
    "text": "关于",
    "href": "#",
    "icon": "icon-aria-about"
}
```  
**`text`为显示的文字，`href`为链接地址**  
**新增`icon`的值，在[iconfont](https://iconfont.cn)建立项目后选择`Font Class`的方式，在icon中输入对应的代码，如`icon-test`**  
**新增`target`的值，填写`_blank`可在新窗口打开**  
**`sub` 为子菜单的配置，目前仅支持二级菜单。需要注意格式严格填写，否则不会菜单有输出**
### 文章打赏功能配置 
需要按照如下方式填写配置信息
```json
"QQ钱包":"qrcodeUrl",
"支付宝":"qrcodeUrl",
"微信":"qrcodeUrl"
```  
对应输出
```html
<li src="{qrcodeUrl}">QQ钱包</li>
<li src="{qrcodeUrl}">支付宝</li>
<li src="{qrcodeUrl}">微信</li>
```
### 链接盒子  
新建一个链接盒子`[link-box][/link-box]`  
新建一个链接项目`[link-item href="链接地址" title="鼠标悬停时显示文字" img="友情链接图像地址" name="友情链接名称"]`。注意属性都需要按顺序填写，`[link-item]`之间不要有空格。
每一个`[link-item]`都要被包括在`[link-box][/link-box]`之间，并会被解析为如下`html`格式  
```html
<a href="链接地址" title="鼠标悬停时显示文字" target="_blank">
    <div class="link-item">
        <img class="link-avatar" src="友情链接图像地址">
        <span class="link-name">友情链接名称</span>
    </div>
</a>
```  
**由于Typecho 1.1正式版的编辑器解析问题，需要用`!!!`包裹`[link-box][/link-box]`**，例如  
```sh
!!!
[link-box][/link-box]
!!!
```
***  
填写示例  
```sh  
[link-box][link-item href="https://x.x/" title="悬停时显示我！" img="https://x.x/x.jpg" name="我是名字！"][link-item href="https://x.x/" title="悬停时显示我！" img="https://x.x/x.jpg" name="我是名字！"][/link-box]
```  
### 归档页面  
创建一个独立页面并选择使用模板`归档页面 时间轴`,**`slug`设置为`archives`**  
不需要填写任何内容，写了也不会有输出（逃  
### PJAX  
后台可以选择开启或者关闭  
如果开启需要在后台关闭`设置->评论->开启反垃圾保护`  
### AJAX评论  
后台可以选择开启或者关闭  
### 底部链接组件  
配置方法  
```json
{"text":"","href":"","target":"","title":""},
{"text":"","href":"","target":"","title":""}
```
*除`text`外均可留空*  
`text` 为显示的文字, `href` 为链接地址，`target` 设置为`_blank` 时链接在新窗口打开， `title` 为鼠标悬停时显示的文字
***  
## 更新  
### 2018-10-11 1.8.1  
* 增加了自定义「一言」接口地址的设置项，现在你可以使用自己的接口了  
* 增加了PJAX重载函数的接口  
* 现在评论回复日期是根据你自己的设定进行输出了  
* 修复了一个短代码注册函数的bug  
* 修复了第一篇文章上下篇的显示bug(若只有一篇文章则不会显示上一篇/下一篇)  
* 对部分样式的细节进行优化处理  
* 处理部分css动画  
* 优化部分js代码  
* 对文章的代码块进行美化（css风格来自[Mashiro](https://2heng.xin)）  
### 2018-10-2 1.8.0  
* 增加了对导航二级菜单的支持  
* 增加了代码高亮块的语言类型提示  
* 修复了一个底部链接组件的bug  
* 重写显示上下篇的代码  
* 微调部分样式  
### 2018-9-27 1.7.1  
* 增加了`底部链接组件`的设置项  
* 增加了评论的 `useragent` 和对应的设置开关  
* 增加了主题最新版本检测的后台按钮  
* 重写归档页面的样式  
* 修复了一个后台开关设置的bug  
### 2018-9-12 1.7.0  
* 修改大部分样式  
* 评论区重写  
* 友情链接页面的样式整合到全局css（可以在任意文章/页面使用`[link-box]` `[link-item]`）  
* 文章短代码优化  
* 删除部分函数  
* 修复部分BUG  
### 2018-8-12 1.6.1  
* 优化了ajax评论代码  
* 后台主题设置使用semantic-ui进行美化  
* 部分细节微调  
* 增加了notyf对于评论成功或者失败的提示（可以配合SmartSpam插件使用）  
* 增加了图片懒加载的开关  
* 增加了对统计代码的重载(目前支持谷歌分析和百度统计)  
### 2018-8-7 1.6.0
* `友情链接`页面部分样式微调  
* css和js文件改为本地调用  
* 增加了pjax页面切换特效  
* 增加了ajax评论选择开关   
* 移除了底部的页面加载时间  
### 2018-7-30 1.5
* 增加了文章底部打赏功能和文章二维码功能
* 增加了评论部分**不接收邮件回复**的按钮（需要配合插件[CommentToMail](https://9sb.org/58 "CommentToMail")使用）  
* 修复了一个无法输出缩略图和预览内容的bug  
* `iconfont`的使用方式从`Unicode`修改为`Font Class`的方式  
* 修改部分样式  
* 重写部分代码  
### 2018-7-9 1.4  
* 增加了一些设置的开关  
* 增加了处理主题配置信息相关功能  
* 增加了导航栏的配置功能  
* 修改大部分样式  
* 重写一部分函数  
* `Prism.js`更换为`highlight.js`  
* ......
### 2018-6-24 1.3  
* 修改部分字体样式  
* 修改首页卡片样式  
* 修改部分文章样式  
* 修改底部样式  
* 底部添加了一言  
* 去除了思源黑体
### 2018-6-20 1.2  
* 更新了友情链接页面短代码匹配以及部分样式  
* 增加了pjax无刷新加载  
* 增加页面进度条  
* 去除了首页文章预览内容的显示  
### 2018-6-15 1.1 Beta  
* 评论头像换用cn.gravatar.org的源  
* 增加了用户评论的UA显示  
* 更新了文章底部上一篇/下一篇的样式  
* 更新了默认随机缩略图的显示  
* 更新了部分样式  
* 修复了归档页面输出时光轴的BUG  
*** 
## 使用的开源项目:  
* [highlight.js](https://highlightjs.org/ "highlight.js")  
* [Bootstrap grid.css](https://www.bootcss.com/ "Bootstrap grid.css")  
* [Fancybox](https://fancyapps.com/fancybox/3/ "fancybox")  
* [jQuery](https://jquery.com/ "jQuery")  
* [DIYgod/OwO](https://github.com/DIYgod/OwO "OwO")  
* [headroom.js](https://www.bootcss.com/p/headroom.js/ "headroom.js")  
* [jquery-pjax](https://github.com/defunkt/jquery-pjax "jquery-pjax")  
* [NProgress](https://github.com/rstacruz/nprogress "NProgress")  
* [animate.css](https://daneden.github.io/animate.css/ "animate.css")     
* [jquery-lazyload](https://appelsiini.net/projects/lazyload/ "jquery-lazyload")  
*** 
## 部分插件推荐（非必需）
* [CommentToMail](https://9sb.org/58 "CommentToMail")  
* [SmartSpam](http://www.yovisun.com/archive/typecho-plugin-smartspam.html "SmartSpam")  
* [Sticky](https://github.com/hitop/typechoSticky "Sticky")