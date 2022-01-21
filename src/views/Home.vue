<template>
  <div class="home">
    <h1>{{ title }}</h1>
    <p>Active Card</p>
    <button @click="toggleView">ADD A NEW CARD</button>
  </div>
</template>

<script>
export default {
    data() {
        return{
            title: "E-WALLET"
        }
    },
    methods: {
        toggleView() {
            this.$emit("gotoaddcard")
        }
    }
}
</script>

<style scoped>
.home {
    /* display: flex;
    flex-direction: column;
    align-items: center; */
    max-width: 30rem;
    min-height: 100vh;
}

p {
    font-size: 0.8rem;
    font-weight: 600;
    text-align: center;
    color: rgb(100, 100, 100);
    margin-bottom: 1rem;
}
</style>