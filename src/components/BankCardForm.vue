<template>
  <div>
    <Bankard />
    <form class="card-form" @submit.prevent="submit">
        <label for="cardNumber">CARD NUMBER</label>
        <input type="number" v-model="cardDetail.cardNumber" placeholder="Card number">
        
        <label for="cardHolder">CARDHOLDER NAME</label>
        <input type="text" v-model="cardDetail.cardHolder" placeholder="Cardholder's name">
        
        <label for="month">MONTH</label>
        <input type="number" placeholder="Month" v-model="cardDetail.validMonth" min="1" max="12">
        
        <label for="year">YEAR</label>
        <input type="number" placeholder="Year" v-model="cardDetail.validYear" min="2022">
        
        <label for="vendor">VENDOR</label>
        <select v-model="cardDetail.vendor" name="vendor" id="vendor">
            <option value="00">-</option>
            <option value="bitcoin">Bitcoin Inc</option>
            <option value="blockchain">Blockchain Inc</option>
            <option value="evilcorp">Evil Corp</option>
            <option value="ninja">Ninja Bank</option>
        </select>
    
        <label for="ccv">CCV</label>
        <input v-model="cardDetail.CCV" type="text" placeholder="">
        
        <button @click="addCard">ADD CARD</button>
    </form>
  </div>
</template>

<script>
import BankCard from "./BankCard.vue"

export default {
    components: {
        BankCard
        },
    data() {
        return {
            cardArray: [],
            cardDetail: {
                vendor: "",
                cardNumber: "",
                cardHolder: "",
                expireMonth: "",
                expireYear: "",
                CCV: ""
            }
        }
    },
    
    methods: {
        addCard() {
            this.$root.data.cardArray.push(this.cardDetail)
            this.cardDetail = {}
        }
    }
}
</script>

<style scoped>
    form {
        margin-top: 400px;
    }

    input[type=text] {
        background-color: white;
        background-position: 10px 10px;
        background-repeat: no-repeat;
        padding-left: 40px;
        height: 40px;
    }
</style>