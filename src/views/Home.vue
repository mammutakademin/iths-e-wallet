<template>
  <div class="home">
    <h1>E-WALLET</h1>
    <p>ACTIVE CARD</p>
    <!-- <BankCard class="active-card" /> -->
    <button @click="jumpTo">ADD A NEW CARD</button>
  </div>
</template>

<script>
// import BankCard from "../components/BankCard"

export default {
    // components: {
    //     BankCard
    // },

    methods: {
        jumpTo() {
            this.$emit("goto")
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
    /* min-height: 100vh; */
}

p {
    font-size: 0.8rem;
    font-weight: 600;
    text-align: center;
    color: rgb(100, 100, 100);
    margin-bottom: 1rem;
}

</style>