<template>
  <div class="block">
    <p>Click Here {{delay}}</p>
  </div>
</template>

<script>
export default {
    props:['delay']
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