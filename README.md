# README
## 介绍
这是一个小小的Visaul Studio Code 扩展应用，主要的功能就是进行px向rem以及根据你输入的基准值进行px向em的等价转换。

## 使用场景
目前，基于rem单位的[移动Web自适应方案](http://www.alloyteam.com/2016/03/mobile-web-adaptation-tool-rem/)可以很好的解决移动设备屏幕碎片化带来的适配问题。同时，手机淘宝团队开发了一个解决方案库 [lib.flexible](https://github.com/amfe/lib-flexible)，但是该方案的有个问题就是设计稿中px单位转换为rem单位比较麻烦，心算基本不可能，计算器算又非常麻烦，这个插件就是解决这个问题的（在 Sublime Text 3 中已有该团队提供的 [CSSREM](https://github.com/flashlizi/cssrem) 插件支持）。

本插件出了提供 px 向 rem 的转换外，还提供了 px 向 em 转换的功能。有时候，有些地方的尺寸需要根据字体的大小来确定的，而设计稿中的尺寸一般都只会标上px单位的尺寸。此时，该插件可以跟你你提供的字体基准值自动把 px 单位换算为 em 单位。

## 使用方法

用光标点击所需要转换的数值（可以不用准确的选定整个数值，程序可以自动的识别所要转换的数值），然后按相应的快捷键或者执行相应的命令即可。

> **小提示** 可以按住 `alt` 然后依次点击所要转换的数值，一次性选择多个数值，批量转换。

### 安装

目前该插件没有在 VS Code 的 Marketplace 上架，所以无法直接通过 VS Code 的扩展安装命令在线安装。必须现下载到本地来手动安装。

安装方法非常简单，在仓库中找到 px2rem-\*.\*.\*.vsix 文件并下载到本地。用 VS Code 打开这个文件就安装成功了。

### 命令

* px转rem： `px2rem`
* px转em： `px2em`

### 快捷键

* px转rem： `alt+c`
* px转em： `shift+alt+c`

### 设置

本插件默认html的font-size为24px。用户可以根据项目中的设计稿尺寸设置html的font-size值。设置方法跟 VS Code 的设置方法一样，可以全局设置也可以根据工作区设置，设置字段为 `px2rem.htmlFontSize: 24px` 。

### 注意

* 在使用 px2em 功能的时候，当执行 `px2em` 命令的时候会要求用户输入基准 font-size 值，这个值接受2种单位的值，一种是 px 值，当要输入 px 值，由于程序默认按照 px 值进行转换，所以此时单位是可选的，也就是说可以仅输入数值即可，不需要单位。另一种是 rem 值，由于工作中可能出现相对的字体大小已经设置为 rem 单位的值，此时要先转换为 px 值再换算为 em 值，程序已经考虑了该情况，所以也可输入以 rem 为单位的数值，程序会自动根据 html 的 font-size 值进行换算。
* 在执行 px 转 em 操作时，如果直接按回车的话，则以上次输入的有效值为基准。
