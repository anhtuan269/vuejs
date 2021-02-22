<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Menu />
    <input type = "text" v-model="name"> 
    <div> 
      {{name}}
    </div>
    <div v-show="isShow"> 
      <h2> Lap trinh vien tap su </h2>
    </div>
    <button @click="isShow = ! isShow"> An / Hien</button>
    <div id = "conca">
      <h1 :id="id" :class = "{dacho: selected}"> TML Tuan ngu nhu cho</h1>
      <input type = "text" :disabled="inputDisabled" v-model="nema"> 
      <button @click="inputDisabled = !inputDisabled" > mo / khoa </button>
      <button id="click" @click="selected = !selected"> click  </button>

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
      nema: 'Nguyen Tat Anh Tuan'

    
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

#click {
 max-width: 1200px;
  margin: 50px auto ;
  display: block;
}
#conca {
  margin-bottom: 300px;
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
