# Vue 开发环境构建
### 相关环境
1、Node
2、npm 中国镜像
3、webpack 构建工具
4、vscode
5、高亮实现 ： Vetur

#Vue 环境
1、vuecli工具

```js
cnpm install -g @vue/cli
vue create 项目名字
npm run serve
```

#基础知识
1、 模板语法
        1、插值
            1、文本  {{}}
            2、原始html v-html
            3、属性 v-bind:attr
            4、{{}} : 表达式必须是单个表达式
        2、指令：
            1、

        3、缩写： v-bind   ====>  ：
                 v-on

###条件渲染 
    1、v-if  这块东西显示与否  元素的移除和添加
    2、v-else  
    3、template  显示一组不想渲染父元素的
    4、v-show : 基于元素的显示与隐藏

###列表渲染
    1、 v-for ：
```js
          <li v-for="item in message" :key="item.id">{{item.text}} -- </li>
```
```js
 addItemHandel() {
         this.message =  this.message.concat([{
            id : 1005,
            text: "dddd"
          }])
```
```concat()  非变更数组的方法```
```push() pop 变更数组方法 直接用```
```详情 vue 文档```
    2、 数组更新检测
### 事件处理
 v-on:click : 缩写 @click
 methods:承载事件函数
事件传参。
### 表单输入绑定
```html
 <div>
      <h3>表单的输入和绑定</h3>
      <p>{{username}}</p>
      <input type="text" v-model.lazy="username">
      <button @click="clickInputHandel">获取</button>    
    </div>
```
修饰符 :   1、lazy （懒加载 回车之后才显示）  2、number   3、trim
### 计算数学 和 监听器
1、 computed
2、 watch
### Class 与 Style 的绑定
```js
  <div :class="{'ca': false}">
      <h3>表单的输入和绑定</h3>
      <p>{{username}}</p>
      <input type="text" v-model.lazy="username">
      <button @click="clickInputHandel">获取</button>    
      {{getMessage}}  
    </div>
    ：class = "{}" 可以是 对象、数组、
```
### 组件
```创建组件```
```components 中创建.vue 组件```
```引入组件```
```js
import hello from"./components/hello.vue";
 注入组件
 computed: {
     getMessage () {
      return this.username.split("").reverse().join("");
    },
```
```使用组件```
标签直接用
```js
    <hello></hello>
```