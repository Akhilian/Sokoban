<template>
  <div class="cell">
      <img v-bind:src="cellImage" alt="toto" />
  </div>
</template>

<script>
const Tiles = {
  WALL: require('../assets/sprites/blocks/block_08.png'),
  GROUND: require('../assets/sprites/ground/ground_00.png'),
  PLAYER: require('../assets/sprites/player/player_02.png'),
  BOX: require('../assets/sprites/crates/crate_02.png'),
  TARGET: require('../assets/sprites/environments/environment_02.png')
}

export default {
  name: 'Cell',

  props: ['type'],

  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },

  computed: {
    cellImage: function () {
      if (this.type === '#') {
        return Tiles.WALL
      } else if (this.type === ' ') {
        return Tiles.GROUND
      } else if (this.type === '@') {
        return Tiles.PLAYER
      } else if (this.type === '$') {
        return Tiles.BOX
      } else if (this.type === '.') {
        return Tiles.TARGET
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cell {
  width: 64px;
  height: 64px;
}
</style>
