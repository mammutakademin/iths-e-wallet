<template>
    <div class="add-card">
        <h1>{{ title }}</h1>
        <p>NEW CARD</p>
        <BankCard :cardInfo="cardInfo" />
        <button @click="toggleView">ADD CARD</button>
    </div>
</template>

<script>
import BankCard from '../components/BankCard.vue';
export default {
    components: {
        BankCard
    },
    data() {
        return {
            title: "ADD A NEW BANK CARD",
        }
    },
    methods: {
        toggleView() {
            this.$emit("gotohome")
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