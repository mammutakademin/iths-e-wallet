<template>
  <div class="home">
    <HeaderSection :heading="title"/>
    <p v-if="cards.length > 0">ACTIVE CARD</p>
    <BankCard v-if="cards.length > 0" :cardData="activeCard" class="active-card">
    <ButtonCta class="add-card-button" :text="buttonTxt" />
  </div>
</template>

<script>
import BankCard from "../components/BankCard.vue"
import ButtonCta from "../components/ButtonCta.vue"

export default {
    components: {
        BankCard,
        ButtonCta
    },
    data() {
        return {
            title: "E-WALLET",
            buttonTxt: "ADD NEW CARD",
            activeCard: this.$root.cards[0]
        }
    },
    computed: {
        cards() {
            return this.$root.cards
        }
    },
    methods: {
        getCard(clickedCard) {
            this.activeCard = clickedCard
        },
        resetActiveCard() {
            this.activeCard = this.$root.cards[0]
        },
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
    /* min-height: 100vh; */
}

p {
    font-size: 0.8rem;
    font-weight: 600;
    text-align: center;
    color: rgb(100, 100, 100);
    margin-bottom: 1rem;
}

.active-card {
    box-shadow: 0 0.1rem 0.04rem 0 rgba(0, 0, 0, 0.5);
    margin-bottom: 1rem;
}
</style>