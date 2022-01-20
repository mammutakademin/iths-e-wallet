<template>
  <div id="app">
    <Home v-if="currentView == 'show-home'" />
    <AddCard v-else-if="currentView == 'show-addcard'" />
  </div>
</template>

<script>
import Home from './views/Home.vue'
import AddCard from './views/AddCard.vue'

export default {
  name: 'App',
  components: {
    Home,
    AddCard
  },
  data() {
    return {
      currentView: "show-home",
      currentButton: "card"
    }
  },
  methods: {
      addCard() {
          this.currentView = "show-addcard"
      }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
body {
    display: flex;
    align-items: center;
    flex-direction: column;
    background: white;
    width: 414px;
    height: 896px;
}

p {
  font-family: 'Source Sans Pro', sans-serif;
}
</style>
