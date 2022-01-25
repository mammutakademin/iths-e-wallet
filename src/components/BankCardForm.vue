<template>
  <div class="register-form">
    <form class="card-form" @submit.prevent="toCreateCard">
        <label for="cardnumber">CARD NUMBER</label>
        <input required
            class="card-number"
            type="text"
            v-model="cardDetail.cardNumber"
            placeholder="XXXX XXXX XXXX XXXX"
        />
        
        <label for="cardholder-name">CARDHOLDER NAME</label>
        <input required
            class="cardholder-name"
            type="text"
            v-model="cardDetail.cardHolderName"
            placeholder="FIRSTNAME LASTNAME"
        />
        
        <div class="validity-date">
            <label for="month">MONTH</label>
            <select name="month" id="month" v-model="cardDetail.month">
                <option name="month" value="month" v-for="month in months" :key="month">
                    {{ month }}
                </option>
            </select>
        </div>
        
        <label for="year">YEAR</label>
            <select name="year" id="year" v-model="cardDetail.year">
                <option name="year" value="year" v-for="year in years" :key="year">
                    {{ year }}
                </option>
            </select>
        
        <label for="vendor">VENDOR</label>
        <select class="vendor" v-model="cardDetail.vendor" name="vendor" id="vendor">
            <option value="00">-</option>
            <option value="bitcoin">Bitcoin Inc</option>
            <option value="blockchain">Blockchain Inc</option>
            <option value="evilcorp">Evil Corp</option>
            <option value="ninja">Ninja Bank</option>
        </select>
    
        <label for="ccv">CCV</label>
        <input v-model="cardDetail.CCV" type="text" placeholder="">
        
        <button @click="addCard">CREATE THIS CARD RIGHT NOW</button>
    </form>
    <Bankard />
  </div>
</template>

<script>
// import BankCard from "./BankCard"

export default {
    // components: { BankCard },
    
    data() {
        return {
            cardArray: [],
            cardDetail: {
                vendor: "",
                cardNumber: "",
                cardHolder: "",
                expireMonth: "",
                expireYear: "",
                ccv: ""
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