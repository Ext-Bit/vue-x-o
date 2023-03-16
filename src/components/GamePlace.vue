<template>
  <h3 v-show="!whoWin">Сейчас ходит {{ symbol }}</h3>
  <h2 v-show="whoWin">Win player {{ whoWin }}</h2>
  <table>
    <tr>
      <GameCell ref="1" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="2" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="3" @click="clickOnCell" :symbol="symbol" />
    </tr>
    <tr>
      <GameCell ref="4" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="5" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="6" @click="clickOnCell" :symbol="symbol" />
    </tr>
    <tr>
      <GameCell ref="7" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="8" @click="clickOnCell" :symbol="symbol" />
      <GameCell ref="9" @click="clickOnCell" :symbol="symbol" />
    </tr>
  </table>
  <br>
  <button @click="reload">Начать заного</button>
</template>

<script>
import GameCell from './GameCell.vue'

export default {
  name: 'GamePlace',
  props: {
    win: String
  },
  components: {
    GameCell
  },
  data() {
    return {
      symbol: 'X',
      whoWin: ''
    }
  },
  methods: {
    clickOnCell(event) {
      console.log(event)
      if (this.symbol === 'X') this.symbol = 'O';
      else this.symbol = 'X';
    },
    reload() {
      // this.symbol = 'X'
      // this.whoWin = ''
      // for (let i in this.$refs) {
      //     this.$refs[i]['symbolHere'] = ''
      // }
      window.location.reload()
    }
  },
  beforeUpdate() {
    if (this.$refs['1']['symbolHere'] === 'X' && 
      this.$refs['2']['symbolHere'] === 'X' && 
      this.$refs['3']['symbolHere'] === 'X' ||
      this.$refs['4']['symbolHere'] === 'X' && 
      this.$refs['5']['symbolHere'] === 'X' && 
      this.$refs['6']['symbolHere'] === 'X' ||
      this.$refs['7']['symbolHere'] === 'X' && 
      this.$refs['8']['symbolHere'] === 'X' && 
      this.$refs['9']['symbolHere'] === 'X' ||
      this.$refs['1']['symbolHere'] === 'X' && 
      this.$refs['4']['symbolHere'] === 'X' && 
      this.$refs['7']['symbolHere'] === 'X' ||
      this.$refs['2']['symbolHere'] === 'X' && 
      this.$refs['5']['symbolHere'] === 'X' && 
      this.$refs['8']['symbolHere'] === 'X' ||
      this.$refs['3']['symbolHere'] === 'X' && 
      this.$refs['6']['symbolHere'] === 'X' && 
      this.$refs['9']['symbolHere'] === 'X' ||
      this.$refs['1']['symbolHere'] === 'X' && 
      this.$refs['5']['symbolHere'] === 'X' && 
      this.$refs['9']['symbolHere'] === 'X' ||
      this.$refs['3']['symbolHere'] === 'X' && 
      this.$refs['5']['symbolHere'] === 'X' && 
      this.$refs['7']['symbolHere'] === 'X') {
        this.whoWin = 'X'
        for (let i in this.$refs) {
          delete this.$refs[i].click
        }
      }
    else if (this.$refs['1']['symbolHere'] === 'O' && 
      this.$refs['2']['symbolHere'] === 'O' && 
      this.$refs['3']['symbolHere'] === 'O' ||
      this.$refs['4']['symbolHere'] === 'O' && 
      this.$refs['5']['symbolHere'] === 'O' && 
      this.$refs['6']['symbolHere'] === 'O' ||
      this.$refs['7']['symbolHere'] === 'O' && 
      this.$refs['8']['symbolHere'] === 'O' && 
      this.$refs['9']['symbolHere'] === 'O' ||
      this.$refs['1']['symbolHere'] === 'O' && 
      this.$refs['4']['symbolHere'] === 'O' && 
      this.$refs['7']['symbolHere'] === 'O' ||
      this.$refs['2']['symbolHere'] === 'O' && 
      this.$refs['5']['symbolHere'] === 'O' && 
      this.$refs['8']['symbolHere'] === 'O' ||
      this.$refs['3']['symbolHere'] === 'O' && 
      this.$refs['6']['symbolHere'] === 'O' && 
      this.$refs['9']['symbolHere'] === 'O' ||
      this.$refs['1']['symbolHere'] === 'O' && 
      this.$refs['5']['symbolHere'] === 'O' && 
      this.$refs['9']['symbolHere'] === 'O' ||
      this.$refs['3']['symbolHere'] === 'O' && 
      this.$refs['5']['symbolHere'] === 'O' && 
      this.$refs['7']['symbolHere'] === 'O') {
        this.whoWin = 'O'
        for (let i in this.$refs) {
          delete this.$refs[i].click
        }
      }
  }
}
</script>

<style scoped>
table {
  border-collapse: collapse;
}
</style>
