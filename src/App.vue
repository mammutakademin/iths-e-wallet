<template>
  <div id="app">
    <Home v-if="currentView == 'show-home'" @gotoaddcard="currentView = 'show-addcard'" />
    <AddCard v-else-if="currentView == 'show-addcard'" @gotohome="currentView = 'show-home'" />
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
    }
  },
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@300&family=Source+Sans+Pro:wght@900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@300&family=PT+Mono&family=Source+Sans+Pro:wght@900&display=swap");

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
  width: 414px;
  height: 896px;
}

h1, h2, h3 {
  font-family: "Source Sans Pro", sans-serif;
}
p {
  font-family: "PT Mono", monospace;
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
