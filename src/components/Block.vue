<template>
    <div class="block" v-if="blockShow" @click="stopTimer">
        click me
    </div>
  </template>
  
 <script>
  export default {
    name: 'block',
    data(){
        return{
            blockShow:false,
            timer:null,
            reactiontime:0,
        }
    },
    props:['delay'],
    mounted(){
        setTimeout( () =>{
            this.blockShow= true;
            this.startTimer()
        } , this.delay)
    },
    methods:{
        startTimer(){
            this.timer= setInterval(() => { 
                this.reactiontime += 10;
            },10);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("reactiontime",this.reactiontime)
        }
    }
  }
 </script>
  
  <style>
    .block{
        width:400px;
        border-radius: 20px;
        background: #0faf87;
        color:white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;

    }
  </style>
  