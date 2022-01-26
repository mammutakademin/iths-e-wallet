<template>
    <div class="addcard">
        <h1>ADD A NEW BANK CARD</h1>
        <p>NEW CARD</p>
        <BankCardForm @click="$emit('toProcessCard')" />
        <button @click="jumpTo">ADD CARD</button>
    </div>
</template>

<script>
import BankCardForm from '../components/BankCardForm';

export default {
    name: "AddCard",
    components: { BankCardForm },
    data() {
        return {
            infoEntered: []
        }
    },
    methods: {
        jumpTo() {
            this.$emit("toggleToMain")
        },
        toProcessCard() {
            this.infoEntered
        }
    }
}
</script>

<style scoped>
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
</style>