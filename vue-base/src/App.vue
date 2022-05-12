<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <h3>模板语法</h3>
    <p>{{msg}}</p>
    <div v-html="price"></div>
    <div :class="active">{{count + 1}}</div>
    <div v-if="flag">孙悟空</div>
    <div v-else>六耳猕猴</div>
  <Hello :num = '1'></Hello>
  <hello @onMyevent="getMessage"></hello>
  {{dddd}}
    <div>
        <h3>列表渲染</h3>
        <button @click="addItemHandel">添加数据</button>
        <ul>
          <li v-for="item in message" :key="item.id">{{item.text}} </li>
        </ul>
    </div>
    <div :class="{'ca': false}">
      <h3>表单的输入和绑定</h3>
      <p>{{username}}</p>
      <input type="text" v-model.lazy="username">
      <button @click="clickInputHandel">获取</button>    
    </div>  
</div>

</template>

<script>
import hello from"./components/hello.vue";
import Hello from "./components/hello.vue";
export default {
  name: "App",
  data() 
  {
    return {
      dddd:"",
    msg:"这是一个模板语法",
      price:"<h3>300</h3>",
      active:"",
      count:0,
      flag : false,
      username: "",
      message:[
      {id : 1001,
        text :"Ribeiro"
      },
      {
        id : 1002,
        text:"ddddd",
      }
      ],
  }
  
  
  },
     methods: {
       getMessage(data){
         console.log(data);
        this.dddd = data;
       },
        addItemHandel() {
         this.message =  this.message.concat([{
            id : 1005,
            text: "dddd"
          }])
        },
        clickInputHandel(){
            console.log(this.username);
        }
      },
  components: {
    hello,
    Hello
},
  computed: {
     getMessage () {
      return this.username.split("").reverse().join("");
    },
  
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
