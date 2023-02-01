<template>
  <p>Result is {{score}} ms.</p>
  <div v-if="score < 200">
      <p>You are too fast.</p>
    </div>
    <div v-else-if="score > 200 && score < 500">
        <p>You are just normal.</p>
    </div>
    <div v-else="score > 500">
        <p>You are too slow. Try again.</p>
    </div>
</template>
<script>
export default {
    props:['score']
}
</script>

<style>

</style>