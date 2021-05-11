# CSS 基础

### 1. BFC

* 创建规则
  * 根元素
  * 浮动元素
  * 绝对定位元素
  * display取值为  `inline-block`  `table-cell`  `table-caption`  `flex`  `inline-flex`
  * `overflow` 不取值为 `visible` 的元素
* 作用
  * 可以包含浮动元素
  * 不被浮动元素覆盖
  * 阻止父子元素的 `margin` 折叠

### 2. 常见的三种布局

* 流体布局

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <title>流体布局</title>
          <style>
              .left{
                  float: left;
                  width: 100px;
                  height: 200px;
                  background: red;
              }
              .right {
                  float: right;
                  width: 200px;
                  height: 200px;
                  background: blue;
              }
              .main {
                  margin-left: 120px;
                  margin-right: 220px;
                  height: 200px;
                  background: green;
              }
          </style>
      </head>
      <body>
          <div class='left'></div>
          <div class='right'></div>
          <div class='main'></div>
      </body>
  </html>
  ```

  ![流体布局](C:\Users\San\AppData\Roaming\Typora\typora-user-images\image-20210507154106511.png)

* 两列布局

  ```html
  <body>
      <div class='left'></div>
      <div class='right'></div>
  </body>
  <style>
  	 .left {
                float: left;
                width: 200px;
                background-color: red;
              }
      .right {
          background-color: yellow;
          margin-left: 220px;
      }
  </style>
  ```

  ![image-20210507155008175](C:\Users\San\AppData\Roaming\Typora\typora-user-images\image-20210507155008175.png)

* 圣杯布局

  ```html
  <style>
      article {
          padding: 0 220px;
      }
      .left {
          float: left;
          background: red;
          width: 200px;
          height: 400px;
          position: relative;
          margin-left: -100%;
          left: -220px;
      }
      .main {
          float: left;
          width: 100%;
          height: 400px;
          background: green;
      }
      .right {
          float: left;
          width: 200px;
          height: 400px;
          position: relative;
          margin-left: -200px;
          right: -220px;
          background: blue;
      }
  </style>
  <body>
      <article>
      	<div class="main"></div>
          <div class="left"></div>
          <div class="right"></div>
      </article>
  </body>
  ```

  ![image-20210507193711094](C:\Users\San\AppData\Roaming\Typora\typora-user-images\image-20210507193711094.png)

* 双飞翼布局

  ```html
  <style>
      .left {
          float: left;
          background: red;
          width: 200px;
          height: 400px;
          margin-left: -100%;
      }
      .main {
          float: left;
          width: 100%;
          height: 400px;
          background: green;
      }
      .inner {
          padding: 0 220px;
      }
      .right {
          float: left;
          background: yellow;
          width: 200px;
          height: 300px;
          margin-left: -200px;
      }
  </style>
  <body>
      <div class='main'>
      	<div class='inner'></div>
      </div>
      <div class='left'></div>
      <div class='right'></div>
  </body>
  ```

  ![image-20210507194527251](C:\Users\San\AppData\Roaming\Typora\typora-user-images\image-20210507194527251.png)

### 3. animation 写幻灯片

```html
.animation {
      width: 400px;
      height: 300px;
      margin: 50px auto;
      overflow: hidden;
      box-shadow: 0 0 5px rgba(0, 0, 0, 1);
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      -webkit-animation: "loops"10s infinite;
    }
@-webkit-keyframes loops {
      0% {
        background: url("https://img1.baidu.com/it/u=1485012388,2380514454&fm=26&fmt=auto&gp=0.jpg")
      }

      20% {
        background: url("https://img0.baidu.com/it/u=233301930,3031623456&fm=11&fmt=auto&gp=0.jpg")
      }

      40% {
        background: url("https://img1.baidu.com/it/u=2496571732,442429806&fm=26&fmt=auto&gp=0.jpg")
      }

      60% {
        background: url("https://img2.baidu.com/it/u=454433451,1062788669&fm=26&fmt=auto&gp=0.jpg");
      }

      80% {
        background: url("https://img1.baidu.com/it/u=3558357902,2576143131&fm=15&fmt=auto&gp=0.jpg")
      }

      100% {
        background: url("https://img2.baidu.com/it/u=1323880827,1335155297&fm=26&fmt=auto&gp=0.jpg");
      }
    }
```

### 4.  盒模型（box-sizing）

* `content-box`: 默认值， 宽度 = `content`
* `border-box`: 宽度 = `content` + `2 * border` + `2 * margin`

### 5.  什么样的前端代码是最好的

* 高夫用低耦合
* 具有可用性，健壮性，可靠性，宽容性

