<template>
  <h1>Omar Reaction game</h1>
  <button @click="start" :disabled="isPlay">Play</button>
  <Block v-if="isPlay" :delay="delay" @reactiontime="endgame" />
  <Results v-if="showResults" :time="scor" />

</template>

<script>

import Block from './components/Block'
import Results from './components/Results'
export default {
  name: 'App',
  components:{ 
    Block,
    Results
  },
  data(){
    return{
      isPlay:false,
      delay:null,
      scor:0,
      showResults:false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000,
      this.isPlay = true
  
    },
    endgame(reactiontime){
      this.scor=reactiontime;
      this.isPlay = false
      // console.log(this.scor)
      this.showResults=true;

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
button{
      background: #0faf87;
      color:white;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      letter-spacing: 1px;
      cursor: pointer;
      margin: 10PX;
      padding: 10px;

}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
