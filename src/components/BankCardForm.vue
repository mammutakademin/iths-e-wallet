<template>
  <div class="register-form">
	<BankCard :card="cardDetail" />
    <form class="card-form" @submit.prevent="addCard">
        <label for="cardNumber">CARD NUMBER</label>
		<input required
			class="card-number"
			type="text"
			v-model="cardDetail.cardNumber"
			placeholder="XXXX XXXX XXXX XXXX"
		/>

        <label for="cardHolder-name">CARDHOLDER NAME</label>
        <input required
			class="cardholder-name"
			type="text"
			v-model="cardDetail.cardHolderName"
			placeholder="FIRSTNAME LASTNAME"
		/>
        
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
	name: "BankCardForm",
    components: { BankCard },
	props: [""],	
    data() {
        return {
            cardArray: [],
            cardDetail: {
                vendor: "",
                cardNumber: "",
                cardHolderName: "",
                validMonth: "",
                validYear: "",
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
	.register-form {
		margin: auto;
		width: 400px;
	}

	.card-form {
		display: flex;
		flex-direction: column;
		width: 380px;
		margin-left: 10px;
        margin-top: 40px;
    }

	label {
		align-self: flex-start;
		font-size: 12px;
		font-family: 'PT Mono', monospace;
	}

	input, select {
		border-radius: 5px;
		font-size: 12px;
		padding: 10px;
		border-width: 1px;
		margin-top: 5px;
		margin-bottom: 15px;
	}

	input[type=text]:focus {
		border: 1px solid gainsboro;
	}

	select {
		width: 170px;
	}

	button {
		font-size: 22px;
		padding: 1rem;
		border-radius: 5px;
		margin-top: 2rem;
		border-width: 2px;
		background-color: whitesmoke;
		font-weight: bold;
	}

	button:hover {
		background-color: thistle;
		color: brown;
	}


</style>