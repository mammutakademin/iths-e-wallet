<template>
  <div id="app">
  
    <Home v-if="thePage == 'home'" @goto=thisDirection />
    <AddCard v-else-if="thePage == 'addcard'" @goto=thisDirection />
  </div>
</template>

<script>
import Home from './views/Home'
import AddCard from './views/AddCard'

export default {
  name: "App",
  components: { Home, AddCard },
  data() {
    return {
      thePage: "home",
      creditCardList: []
    }
  },
  methods: {
    thisDirection() {
      this.thePage == "home" ? this.thePage = "addcard" : this.thePage = "home"
    },
    addCardPayload(cardpayload) {
      this.creditCardList.push(cardpayload)
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

div {
  display: flex;
  align-items: center;
  flex-direction: column;
  background-color: burlywood;
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
/* #app {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  margin-top: 1rem;
} */
</style>
