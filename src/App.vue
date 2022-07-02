<template>

   <h1>How fast can you catch me?</h1> 


  <button @click="start" :disabled="isPlaying">Play</button>
 
  <div v-if="isPlaying" >
     <MyBlock :delay="delay" @endGame="endGame"/>
  </div>
  <div v-if="end && !isPlaying">
    <MyResult :score='score'/>
  </div>
  
 </template>

<script>
import MyBlock from "./components/MyBlock.vue"
import MyResult from "./components/MyResult.vue"

export default {
  name: 'App',
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: 0,
      end: false
    }
  },
  components: {
    MyBlock,MyResult
  },
  methods:{
    start(){
      this.isPlaying=true;
      this.delay=2000+Math.random()*5000;
    },
    endGame(score){
      this.isPlaying=false;
      this.score = score;
      this.end = true;

    }
  }
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
