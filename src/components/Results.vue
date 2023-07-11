<template>
     <p > Reaction Time is : {{ time }} ms</p>
     <p class="rank">{{ rank }}</p>
  </template>
  
 <script>
  export default {
    name: 'results',
    props:['time'],
    data(){
        return{
           rank:null,
        }
    },
    mounted(){
        if(this.time < 250){
            this.rank='Ninja Figers...'
        }
        else if (this.time < 400){
            this.rank='Raipid Reflex..'
        }
        else{
            this.rank='Snail pace...'
        }

    }
  }
 </script>
  
  <style>
    .rank{
        color:#0faf87;
        font-size: 1.4em;
        font-weight: bold;
    }
  </style>
  