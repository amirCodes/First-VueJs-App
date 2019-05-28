<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Todos v-bind:todos="todos"/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>here we can start hiking</h1>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Todos
  },
  data(){
    return{
      todos:[
        {
          id:1,
          title:'learn vue',
          completed:false,
        },{
          id:2,
          title:'learn reactjs',
          completed:false,
        },{
          id:3,
          title:'do cooking',
          completed:false,
        },{
          id:4,
          title:'fix the bugs',
          completed:false,
        },{
          id:5,
          title:'find out the errors',
          completed:false,
        },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
