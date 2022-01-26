<template>
  <div id="app">
    <Home v-if="currentPage == 'Home'" 
    :cards="cards" 
    @toggleToAddCard="currentPage = 'AddCard'" 
    />

    <AddCard v-else-if="currentPage == 'AddCard'" 
    @toggleToMain="addCard" 
    />
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
      cards: [
        {
          vendorName: "blockchain",
          cardNumber: "1111 2222 3333 4444",
          cardHolderName: "Austin Powers",
          validMonth: "03",
          validYear: "24"
        },
        {
          vendorName: "evil",
          cardNumber: "0661 6226 0333 0020",
          cardHolderName: "Megan Markle",
          validMonth: "08",
          validYear: "23"
        },
        {
          vendorName: "ninja",
          cardNumber: "1213 1234 5555 1908",
          cardHolderName: "O Ren Shii",
          validMonth: "12",
          validYear: "26"
        },
      ],
    }
  },
  methods: {
    // changeView() {
    //   this.currentPage == "Home" ? this.currentPage == "AddCard" : this.currentPage == "Home"
    // },
    addCard(cardData) {
      this.cards.push(cardData)
      this.currentPage = "Home"
    }
  }
}
</script>

<style scoped>
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
