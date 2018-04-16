<template>
  <div class="hello">
    <grid></grid>
    <!-- <h1>{{ msg }}</h1> -->
  </div>
</template>

<script>

import Grid from './Grid'

export default {
  name: 'HelloWorld',

  components: {
    Grid
  },

  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
