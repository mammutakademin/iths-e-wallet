<template>
  <div id="app">
    <Home v-if="currentPage == 'Home'" :cards="cards" @toggleToAddCard="currentPage = 'AddCard'" />
    <AddCard v-else-if="currentPage == 'AddCard'" @toWallet="addCard" />
  </div>
</template>

<script>
import Home from './views/Home'
import AddCard from './views/AddCard'

export default {
  name: 'App',
  components: { Home, AddCard },
  data() {
    return {
      currentPage: "Home",
      cards: [],
    }
  },
  methods: {
    addCard(cardData) {
      console.log(cardData)
      this.card = cardData
      this.cards.push(cardData)
      localStorage.setItem("cards", JSON.stringify(this.cards))
      this.currentPage = "Home"
    },
  },
  beforeMount() {
    const savedCards=localStorage.getItem("cards")
    if(savedCards) {
      this.cards = JSON.parse(savedCards)
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=PT+Mono&family=Source+Sans+Pro:wght@300;400&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  background-color: #fdf6cf;
  color: #2c3e50;
  margin: 10rem 15rem;
  width: 33rem;
  height: 896px;
}

h1, h2, h3 {
  font-family: 'Source Sans Pro', sans-serif;
}
p {
  font-family: 'PT Mono', monospace;
}

</style>
