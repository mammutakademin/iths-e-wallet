<template>
  <div class="home">
	<h1>E-WALLET</h1>
    <p>ACTIVE CARD</p>
    <BankCard v-if="cards.length > 0" :card="cards[activeCardIndex]" />
    <section>
      <BankCard v-for="(card, index) in cards" :key="index" :card="card" @click="activeCardIndex=index" />
    </section>
    <button @click="toggleView">ADD A NEW CARD</button>
  </div>
</template>

<script>
import BankCard from "../components/BankCard"

export default {
    components: { BankCard },
    data() {
      return {
        activeCardIndex: 0
      }
    },
    props: ['cards'],
    methods: {
		toggleView() {
			this.$emit("toggleToAddCard")
		}
  }
}
</script>

<style scoped>
.home {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 30rem;
    height: 100vh;
    box-sizing: border-box;
    margin: 8px;
    padding: 8px 10px;
}

p {
    font-size: 0.8rem;
    font-weight: 600;
    text-align: center;
    color: rgb(100, 100, 100);
    margin-bottom: 1rem;
}

section {
  margin-top: 3rem;
  display: grid;
  grid-auto-rows: 3rem;
}

button {
  font-family: 'PT Mono', monospace;
	width: 380px;
  height: 72px;
  margin-top: 240px;
  font-size: 22px;
  font-weight: bold;
	padding: 1rem;
  border-radius: 8px;
}

</style>