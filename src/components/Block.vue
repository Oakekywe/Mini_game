<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    <p>Click Here {{delay}}</p>
  </div>
</template>

<script>
import { onUnmounted } from '@vue/runtime-core';
export default {
    props:['delay'],
    data(){
        return{
            showBlock: false,
            score: 0,
            timer: null,
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock= true;
            this.setTimer()
        }, this.delay);
    },
    methods:{
        setTimer(){
            this.timer= setInterval(() => {
                this.score +=50;
            }, 50);
        },
        stopTimer(){
            clearInterval(this.timer);
            console.log(this.score);
        }
    }
    
}

</script>

<style>
 .block{
    background-color: aqua;
    width: 400px;
    height: 300px;
    padding-top: 30px;
    margin: 20px auto;
 }
</style>