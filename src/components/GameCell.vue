<template>
  <td @click="click" v-text="symbolHere"></td>
</template>

<script>
export default {
  name: 'GameCell',
  props: {
    symbol: String
  },
  data() {
    return {
      symbolHere: ''
    }
  },
  methods: {
    click() {
      if (this.symbolHere !== '') return
      this.symbolHere = this.symbol
    }
  }
}
</script>

<style scoped>
td {
  border: 1px solid black;
  width: 60px;
  height: 60px;
  font-size: 30px;
}
</style>
