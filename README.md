# vue-popup
popup for vue.js

require [underscore](https://github.com/jashkenas/underscore) and [css-builder](https://github.com/johnnyGoo/css-builder)

# setting
| 名称                    |类型               |默认       | 说明                                     |
| ----------------------- | ----------------- | -------- | ---------------------------------------- |
|mask-close               |Boolean            |true      | 点击空白处是否关闭                                        |
|z-index                  |Number/String      |100       | z-index                                  |
|title                    |String             |""        | 标题 如果''隐藏标题                               |
|title-color              |String             |'#000'    | 标题颜色                            |
|title-background         |String             |'#fff'    | 标题背景颜色                                        |
|title-border-bottom      |String             |'1px solid #f0f0f0'|  标题下边框                                        |
|close-button             |Boolean            |true      | 是否现实关闭按钮                           |
|close-color              |String             |'#fff'    | 关闭按钮颜色                              |
|content-background       |String             |'#000'    | 内容背景颜色                              |
|content                  |String             |""        | 内容 支持html                              |
|button-background        |String             |'#337ab7' | 按钮背景                             |
|button-color             |String             |'#fff'       |  按钮颜色                                         |
|button-border            |String             |'1px solid #2e6da4'       |  按钮边框                                         |
|confirm-button           |String             |'OK'       | 确认按钮文字                                        |
|cancel-button            |String             |'Cancel'       | 取消按钮文字                                        |
|popup                    |String             |{show: false, shaking: false}       |  控制popUp对象                                        |
|transition-object        |String             |{transition:{transition:'all .4s cubic-bezier(.35,1.43,.56,1.02)',opacity:1,scale:1,'transition-delay': '.2s'},enter:{'transition-delay': '.2s',opacity:0,scale:1.2},leave:{'transition-delay': '.0s',opacity:0,scale:0.8}}       | transition 对象 ,详见CssBuilder                                      |
|box-shadow               |string             |'0 2px 3px #000'| 窗口投影
|title-align              |string             |'left'    | 标题文字对齐
|mask-background          |string             |'rgba(0,0,0,0.6)'| 蒙板背景



#Event
| 名称                    |说明                |
| ----------------------- | ----------------- |
| popup-close             |callback on close  |
| popup-confirm           |callback on confirm|
| popup-cancel            |callback on cancel |


#Example
* html
```html
  <vue-popup title="确认?" :popup.sync="popup2" z-index="100">
     Do this?
  </vue-popup>
```
* js
```js
 new Vue({
         el: '#example',
         data: {msg: 'aaa', picked: '1122', popup: {show: false,shaking:false},popup2: {show: false,shaking:false}},
         events: {
             'popup-confirm': function (obj) {
                 // 事件回调内的 `this` 自动绑定到注册它的实例上
               //  obj.show=false;
                 obj.shaking=true;
                console.log(obj)
             }
         }
     });
```


