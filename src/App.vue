<template>
  <h1>OpenCode Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <p v-if="showTime">Reaction Time : {{ score }} ms </p>
  <Block v-if="isPlaying" :delayProps="delay" @end="endGame"/>
</template>


<script>
import Block from "./components/Block.vue"
export default {
  name: 'App',
  components: {Block},
  data(){
    return{
      delay:null,
      isPlaying:false,
      score:null,
      showTime:false
    }
    
  },
  methods:{
    start(){
      this.isPlaying=true
      this.delay=2000 + Math.random()*5000
      console.log(this.delay);
      this.showTime=false
    },

    endGame(reactionTime){
      this.score=reactionTime
      this.isPlaying=false
      this.showTime=true
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
  color: #444;
  margin-top: 60px;
}
</style>
