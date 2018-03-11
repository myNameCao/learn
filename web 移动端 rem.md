

## meta 的基础知识 
+ h5 页面窗口自动调整到设备的宽度 并禁止用户缩放页面
```html
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no" />
```
+ 忽略将页面的中的数字识别为电话号码
```html
<meta name="format-detection" content="telephone=no" />
```
+ 忽略Andorid 平台对邮箱地址的识别 
```html
<meta name="format-detection" content="email=no" />
```

## 移动端使用系统默认的字体
```css
body{font-family:Helvetica;}
```
## 移动端字体单位 font-size 选择px还是 rem 
+ 对于只需要适配少部分手机设备，且分辨率对页面影响不大的，使用px即可
+ 对于需要适配各种移动设备，使用rem 例如只需要适配iphone和ipad 等分辨率差别比较大的设备 
rem 配置参考 适配视觉稿宽度为640 px 
```css
html{font-size:10px}
@media screen and (min-width:321px) and (max-width:375px){html{font-size:11px}}
@media screen and (min-width:376px) and (max-width:414px){html{font-size:12px}}
@media screen and (min-width:415px) and (max-width:639px){html{font-size:15px}}
@media screen and (min-width:640px) and (max-width:719px){html{font-size:20px}}
@media screen and (min-width:720px) and (max-width:749px){html{font-size:22.5px}}
@media screen and (min-width:750px) and (max-width:799px){html{font-size:23.5px}}
@media screen and (min-width:800px){html{font-size:25px}}

```
### 横竖时使用的样式

```css
//竖屏时使用的样式
@media all and (orientation:portrait) {
.css{}
}

//横屏时使用的样式
@media all and (orientation:landscape) {
.css{}
}
```
