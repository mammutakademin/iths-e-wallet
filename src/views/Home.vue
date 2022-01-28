<template>
  <div class="home">
	<h1>E-WALLET</h1>
    <p>ACTIVE CARD</p>
    <BankCard v-if="cards.length > 0" :card="cards[activeCardIndex]" />
    <p>All Cards</p>
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
  display: grid;
  grid-auto-rows: 3rem;

}
.card-tray {
	margin-top: 3rem;
	display: grid;
	grid-auto-rows: 4rem
}

button {
	width: 30rem;
  margin-top: 240px;
  font-weight: 100;
	padding: 1rem;
}
</style>