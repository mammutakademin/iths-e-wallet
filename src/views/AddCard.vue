<template>
    <div class="add-card">
        <h1>ADD A NEW BANK CARD</h1>
        <p class="new-card">NEW CARD</p>
        <BankCardForm @click="$emit('toProcessCard')" />
        <button @click="jumpTo">ADD CARD</button>
    </div>
</template>

<script>
import BankCardForm from '../components/BankCardForm';
export default {
    name: "AddCard",
    components: { BankCardForm },
    methods: {
        jumpTo() {
            this.$emit("goto")
        }
    }
}
</script>

<style scoped>
.add-card {
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