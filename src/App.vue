<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Menu />
    // 2 way binding thông qua v-model và value binding
    <input type = "text" v-model="name"> 
    <div> 
      {{name}}
    </div>
    // ẩn hiện el thông qua v-show, nếu isShow =tru thì hiện el và nguoecj lại 
    <div v-show="isShow"> 
      <h2> Lap trinh vien tap su </h2>
    </div>
    <button @click="isShow = ! isShow"> An / Hien</button>

    <div id = "conca">
      // property binding , style and class binding
      <h1 :id="id" :class = "{dacho: selected}"> TML Tuan ngu nhu cho</h1>
      <input type = "text" :disabled="inputDisabled" v-model="nema"> 
      // bắt sự kiện v-on click
      <button @click="inputDisabled = !inputDisabled" > mo / khoa </button>
      <button id="click" @click="selected = !selected"> click  </button>

    </div>

    <div>
      <input type="text" v-model="chanel.name">
      <button @click="chanel.name= 'Me Thi Ngoc Thao'" style = " margin-bottom: 40px;"> click</button>
    </div>
    // list rendering v-for
    <div class="render">
      // add content vao tasks
      <input type="text" v-model="newTask">
      <button @click="tasks.push({content: newTask, done: false})">add</button>
      // render len componet qua v-for 
      <div v-for="(task, index) in tasks" v-bind:key="index" class="list" >
          <input type="checkbox" v-model="task.done">
          <span v-bind:class="{done: task.done}"> {{task.content}}</span>
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Menu from './components/Menu.vue'

export default {
  name: 'App',
  data(){
    return {
      name: 'Nguyen Tat Anh Tuan',
      isShow: true,
      id: 'dachon',
      inputDisabled: true,
      selected: true,
      nema: 'Nguyen Tat Anh Tuan',
      chanel: {
        name: 'lap trinh vien tv'
      }, 
      newTask: '',
      tasks: [
        {content: 'javascript', done: false},
        {content: 'javascript advanced', done: false},
        {content: 'nodejs', done: false},
        {content: 'vuejs', done: false},
      ],
      // xu li truoc khi update len Html
      beforeUpdate(){

      },
      // xu ly sau khi update 
      updated(){

      }    
    }
  },
  components: {
    HelloWorld,
    Menu
  }
}
</script>

<style>
.dacho {
  color: red  !important;
}
.render {
 max-width: 1200px;
 margin: 0  auto;
 justify-content: center;
 display: grid;
 text-align: center;
}
.render .list {
  text-align: left;
}
.render .done {
  text-decoration: line-through;
}

#click {
 max-width: 1200px;
  margin: 50px auto ;
  display: block;
}
#conca {
  margin-bottom: 200px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
