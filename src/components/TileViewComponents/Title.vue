<template>
  <div class="hello">
    <h1 v-html="text"></h1>
  </div>
</template>

<script>
export default {
  name: 'TitleComponent',
    props: ['text']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    margin: 0;
    font-size: 10.5vw;
    text-align: right;
    /*text-shadow: 1px 1px #ddd, 2px 2px #ddd, 3px 3px #ddd,4px 4px #ddd, 10px 10px 10px rgba(0,0,0,0.2);*/
  }
</style>
