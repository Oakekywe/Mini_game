<template>
  <div class="block" v-if="showBlock">
    <p>Click Here {{delay}}</p>
  </div>
</template>

<script>
import { onUnmounted } from '@vue/runtime-core';
export default {
    props:['delay'],
    data(){
        return{
            showBlock: false
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock= true;
        }, this.delay);
    },
    updated(){
        console.log("updated")
    },
    unmounted(){
        console.log("component unmounted")
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