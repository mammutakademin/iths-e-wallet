<template>
  <header class="title">
    <h1>E-wallet</h1>
    <p>Active card</p>
    <button @click="addCard">Add new card</button>
  </header>
</template>

<script>
export default {
    data() {
        return{
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

}
<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
body {
    display: flex;

}
</style>