<template>
  <div id="app">
    <h2>{{title}}</h2>
    <Navbar></Navbar>
    <AllFriends :friends="friends" @delete="deleteFriend"></AllFriends>
    <OnlineFriends :friends="friends"></OnlineFriends>
  </div>
</template>

<script>


import Navbar from './components/Navbar.vue'
import AllFriends from './components/AllFriend.vue'
import OnlineFriends from './components/OnlineFriend.vue'
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
    Navbar,AllFriends,OnlineFriends
  },
  methods: {
    deleteFriend(payload){
      console.log(payload)
      this.friends=this.friends.filter(friend=>{
        return friend.name!==payload.name
      })
    }
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
