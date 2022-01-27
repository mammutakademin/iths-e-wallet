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
            newCard: {
                cardNumber: "",
                cardHolderName: "",
                vendor: "",
                validMonth: "MM",
                validYear: "YY"
            },
        }
    },
    methods: {
        jumpTo() {
            this.$emit("toggleToMain")
        },
        processCard(cardDetail) {
            this.card = cardDetail
            this.$emit('toWallet', this.card)
        }
    }
}
</script>

<style lang="scss" scoped>
.addcard {
    max-width: 30rem;
}

p {
    font-size: 0.8rem;
    font-weight: 600;
    text-align: center;
    color: rgb(100, 100, 100);
    margin-bottom: 1rem;
}
.card{
    box-shadow: 0 0.1rem 0.4rem 0 rgba(0, 0, 0, 0.5);
}
</style>