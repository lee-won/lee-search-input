# uni-app搜索框封装

主要功能：

1. 可自定义输入框样式
2. 可自定义按钮样式
3. 可自定义引入图标
4. 微信小程序增加语音输入和扫码功能



样例展示：

![1557835691914](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557835691914.png)

![1557835802443](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557835802443.png)

![1557837372201](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557837372201.png)

![1557838157287](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557838157287.png)



用法事：



搜索框自定义属性说明： 

| 属性名       | 类型    | 默认值 | 说明                                              |
| :----------- | ------- | ------ | ------------------------------------------------- |
| btnLinkInput | Boolean | false  | 按钮是否与input框相连，只有开启按钮的时候才生效   |
| inputAttr    | Object  | null   | 输入框的样式                                      |
| btnAttr      | Object  | null   | 按钮样式                                          |
| voiceAttr    | Object  | null   | 语音输入模块样式，只对微信 开启语音功能图标时有效 |
| iconAttr     | Object  | null   | 图标样式                                          |
| iconSrc      | Object  | null   | 图标地址                                          |

inputAttr属性说明：

| 属性名              | 类型   | 默认值              | 说明                                    |
| ------------------- | ------ | ------------------- | --------------------------------------- |
| height              | Number | 60                  | 输入框高度，默认为最小高度60，单位为upx |
| borderRadius        | Number | 30                  | 输入框的圆角， 单位upx                  |
| border              | String | 1px  solid  #c8c7cc | 边框样式                                |
| borderWidth         | Number | 1                   | 边框宽度，单位upx                       |
| backgroundColor     | String | #ffffff             | 背景颜色                                |
| fontSize            | Number | 28                  | 字体大小，单位upx                       |
| color               | String | #333                | 字体颜色                                |
| paddingLeft         | Number | 0                   | 左边填充 ，单位upx                      |
| placeholderText     | String | 请输入搜索内容      | 输入框未输入时的提示文本                |
| placeholderPosition | String | left                | 提示文本位置  值： left   、 center     |
| placeholderColor    | String | #808080             | 输入框的提示文本的颜色                  |

btnAttr属性说明：

| 属性名             | 类型    | 默认值        | 说明                                   |
| ------------------ | ------- | ------------- | -------------------------------------- |
| enable             | Boolean | true          | 是否启用按钮                           |
| text               | String  | 取消          | 按钮显示的文本                         |
| paddingLeft        | Number  | 10            | 按钮左边填充，  单位upx                |
| paddingRight       | Number  | 0             | 按钮右边填充，单位upx                  |
| fontSize           | Number  | 28            | 按钮字体大小，单位upx                  |
| backgroundColor    | String  | #ffffff       | 按钮背景颜色                           |
| borderRadius       | Number  | 30            | 按钮圆角，单位 upx                     |
| color              | String  | #333          | 字体颜色                               |
| border             | String  | none          | 按钮边框                               |
| borderWidth        | Number  | 1             | 边框宽度，单位upx                      |
| backgroundImage    | String  | 空            | 按钮背景图片，只能为base64位或远程图片 |
| backgroundPosition | String  | center center | 背景图位置                             |
| backgroundSize     | String  | contain       | 背景图尺寸                             |

voiceAttr属性说明：(仅在微信小程序中开启语音图标时有效)

| 属性名                   | 类型   | 默认值    | 说明                     |
| ------------------------ | ------ | --------- | ------------------------ |
| btnColor                 | String | #fff      | 录音按钮文本颜色         |
| btnActiveColor           | String | #fff      | 录音按钮按住时的文本颜色 |
| listenColor              | String | #fff      | 聆听容器的文本颜色       |
| btnBackgroundColor       | Sting  | #f1f1f1   | 录音按钮的背景色         |
| btnBackgroundActiveColor | String | #c8c7cc   | 录音按钮按住时的背景色   |
| listenBackgroundColor    | String | #c8c7cc   | 聆听容器的背景色         |
| text                     | String | 按住 说话 | 录音按钮的文本           |
| activeText               | String | 松开 结束 | 录音按钮按下时的文本     |

iconAttr属性说明：

| 属性名  | 类型               | 默认值 | 说明                |
| ------- | ------------------ | ------ | ------------------- |
| width   | Number             | 60     | 图标宽度，单位upx   |
| height  | Number             | 60     | 图标高度，单位upx   |
| padding | Number             | 10     | 图标内填充，单位upx |
| scale   | Number \|\| String | 1      | 图标缩放            |

iconSrc属性说明：(属性有值时开启对应图标)

| 属性名      | 类型   | 默认值 | 说明                             |
| ----------- | ------ | ------ | -------------------------------- |
| logo        | String | 无     | logo图标相对地址或远程地址       |
| voice       | String | 无     | 语音图标相对地址或远程地址       |
| scan        | String | 无     | 扫码图标相对地址或远程地址       |
| clear       | String | 无     | 清空图标相对地址或远程地址       |
| placeholder | String | 无     | 输入框提示图标相对地址或远程地址 |
| search      | String | 无     | 搜索图标相对地址或远程地址       |

其它属性为uni-app中 input组件原生属性，参考链接 

[https://uniapp.dcloud.io/component/input]: 



可触发的事件列表：

| 属性名    | 类型        | 默认值 | 说明                                     |
| --------- | ----------- | ------ | ---------------------------------------- |
| @scan     | EventHandle |        | 点击扫码图标时触发事件，可接收扫码的结果 |
| @search   | EventHandle |        | 点击搜索图标触发事件                     |
| @btnClick | EventHandle |        | 点击按钮时触发事件，可接收按钮的文本     |
| @clear    | EventHandle |        | 点击清空按钮时触发事件                   |
| @voice    | EventHandle |        | 点击语音图标触发事件                     |
| @input    | EventHandle |        | 当键盘输入时触发事件                     |
| @blur     | EventHandle |        | 输入框失去焦点时触发                     |
| @focus    | EventHandle |        | 输入框聚焦时触发                         |
| @confirm  | EventHandle |        | 点击完成按钮时触发                       |

关于语音功能的配置

1.在manifest.json文件中添加语音插件

​		![](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557834411296.png)

2.在小程序管理平台添加插件

![1557834603691](C:\Users\leewon\AppData\Roaming\Typora\typora-user-images\1557834603691.png)



语音插件文档链接：

[https://mp.weixin.qq.com/wxopen/plugindevdoc?appid=wx069ba97219f66d99&amp;token=2051927552&amp;lang=zh_CN#-]: 

