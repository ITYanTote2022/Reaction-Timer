<template>
  <p> Your result is {{score}}</p>
  <div v-if="score<=200">
    <p>OMG!!!<br>
        You are the God in catching!!! 
    </p>
  </div>
  <div v-else-if="score>200 && score<=500">
    <p>You can catch within normal speed.</p>
  </div>
  <div v-else>
    <p>You are too slow! Try faster.</p>
  </div>
</template>

<script>
export default {
    props:['score']

}
</script>

<style>

</style>