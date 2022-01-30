<template>
    <div class="addcard">
        <h1>ADD A NEW BANK CARD</h1>
        <p>NEW CARD</p>
        <BankCardForm @submittedForm="processCard" />
    </div>
</template>

<script>
import BankCardForm from '../components/BankCardForm';

export default {
    name: "AddCard",
    components: { BankCardForm },
    data() {
        return {
            newCard: []
        }
    },
    methods: {
        processCard(cardDetail) {
            this.newCard = cardDetail
            this.$emit('toWallet', cardDetail)
        }
    }
}
</script>

<style lang="scss" scoped>
.addcard {
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

</style>