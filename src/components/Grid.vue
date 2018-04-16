<template>
  <div class="grid">
    <div v-for="row in formattedMap" class="grid-row">
      <div v-for="cell in row">
        <Cell v-bind:type="cell"></Cell>
      </div>
    </div>
  </div>
</template>

<script>

import Cell from './Cell'

const levelOne = [
  [' ', ' ', ' ', ' ', '#', '#', '#', '#', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
  [' ', ' ', ' ', ' ', '#', ' ', ' ', ' ', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
  [' ', ' ', ' ', ' ', '#', '$', ' ', ' ', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
  [' ', ' ', '#', '#', '#', ' ', ' ', '$', '#', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
  [' ', ' ', '#', ' ', ' ', '$', ' ', '$', ' ', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
  ['#', '#', '#', ' ', '#', ' ', '#', '#', ' ', '#', ' ', ' ', ' ', '#', '#', '#', '#', '#', '#'],
  ['#', ' ', ' ', ' ', '#', ' ', '#', '#', ' ', '#', '#', '#', '#', '#', ' ', ' ', '.', '.', '#'],
  ['#', ' ', '$', ' ', ' ', '$', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '.', '.', '#'],
  ['#', '#', '#', '#', '#', ' ', '#', '#', '#', ' ', '#', '@', '#', '#', ' ', ' ', '.', '.', '#'],
  [' ', ' ', ' ', ' ', '#', ' ', ' ', ' ', ' ', ' ', '#', '#', '#', '#', '#', '#', '#', '#', '#'],
  [' ', ' ', ' ', ' ', '#', '#', '#', '#', '#', '#', '#', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ']
]

export default {
  name: 'Grid',

  components: {
    Cell
  },

  data () {
    return {
      levelOne
    }
  },

  computed: {

    formattedMap: function () {
      const translatedMap = []

      for (let i = 0; i < levelOne[0].length; i++) {
        const row = []
        for (let nbOfRows = 0; nbOfRows < levelOne.length; nbOfRows++) {
          row.push(levelOne[nbOfRows][i])
        }

        translatedMap.push(row)
      }

      return translatedMap
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.grid-row {
  display: inline-block;
}

</style>
