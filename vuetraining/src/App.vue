<template>
  <div id="app">
    <h2>{{title}}</h2>
    <Navbar></Navbar>
    <Hook></Hook>
  </div>
</template>

<script>


import Navbar from './components/Navbar.vue'
import Hook from './components/Hook.vue'
export default {
  name: 'App',
  data(){
    return {
      title:'Wow Our Vue Website are runing',
      friends:[
        {name:'A',online:true},
        {name:'B',online:true},
        {name:'C',online:false},
        {name:'D',online:true},
        {name:'E',online:false},
      ]
    }
  },
  components:{
    Navbar,
    Hook
  },
  methods: {
    
  },
}
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
