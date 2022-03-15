<template>
<div>
    <h1>Reaction Timer </h1>
  <button @click="start()" :disabled="isPlaying "> play </button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Result v-if="showresults" :score="score" />
  <!-- <p v-if="showresults">score  dyalk : {{score}} ms</p> -->
  <!-- <p></p> -->
</div>

</template>

<script>
import Block from './components/Block.vue';
import Result from './components/Results';
export default {
  name: 'App',
  components: {Block,Result},
  data() {
    return {
        isPlaying: false,
        delay:null,
        score:null,
        showresults:false,
    }
  },
  methods: {
    start (){
      // console.log('you click mr')
      this.delay =2000 + Math.random() * 5000
      this.isPlaying=true
      this.showresults=false
      // console.log(this.showresults)
      
    },
    endGame (reactTime){
      this.score=reactTime
      this.isPlaying=false
      this.showresults=true
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
