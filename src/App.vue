<template>
  <h1>How fast can you catch me?</h1>
  <button class="btn btn-info text-white my-3" @click="start" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame"/> 
  </div>
  <div v-if="end">
    <Result :score="score"/>
  </div>

  <div class="rules">

    <h3>Rules</h3>
    <ul>
      <li>Click the play button and box will display in a random second.</li>
      <li>Click the displayed box and your score will be resulted.</li>
    </ul>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"

export default {
  name: 'App',
  components: {
   Block,
   Result
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: 0,
      end: false,
    }
  },
  methods: {
    start(){
      this.isPlaying= true;
      this.delay= 1000+Math.random()*4000;
    },
    endGame(score){
      this.score= score;
      this.isPlaying= false;
      this.end= true;
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
.rules{
  width: 500px;
  height: 300px;
  margin: 20px auto;
  padding: 10px;
  text-align: left;
}

</style>
