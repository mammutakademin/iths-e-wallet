<template>
  <div class="registerForm">
	<BankCard :card="cardDetail" />
    <form class="cardForm" @submit.prevent="addCard">
        <label for="cardNumber">CARD NUMBER</label>
		<input required
			type="text"
			pattern="[0-9]{16}"
			v-model="cardDetail.cardNumber"
			minlength="16"
			maxlength="16"
			placeholder="XXXX XXXX XXXX XXXX"
		/>

        <label for="cardHolder-name">CARDHOLDER NAME</label>
        <input required
			type="text"
			maxlength="30"
			v-model="cardDetail.cardHolderName"
			placeholder="FIRSTNAME LASTNAME"
		/>
        
		<div class="expirySection">
			<div class="card-validity">
				<label for="month">MONTH</label>
				<input type="number" v-model="cardDetail.validMonth" min="1" max="12" placeholder="MM">
			</div>
			<div class="card-validity">
				<label for="year">YEAR</label>
				<input type="number" v-model="cardDetail.validYear" min="2022" placeholder="YYYY">
			</div>
		</div>
        
        <label>VENDOR</label>
        <select class="vendor" v-model="cardDetail.vendor">
            <option>-</option>
            <option value="bitcoin">Bitcoin Inc</option>
            <option value="blockchain">Blockchain Inc</option>
            <option value="evil">Evil Corp</option>
            <option value="ninja">Ninja Bank</option>
        </select>
    
        <button type="submit">ADD CARD</button>
    </form>
  </div>
</template>

<script>
import BankCard from "./BankCard"

export default {
	name: "BankCardForm",
    components: { BankCard },	
    data() {
        return {
            cardArray: [],
            cardDetail: {
                vendor: "",
                cardNumber: "",
                cardHolderName: "",
                validMonth: "",
                validYear: "",
                ccv: "",
				valid: "",
            }
        }
    },
    
    methods: {
        addCard() {
            this.$emit("submittedForm", this.cardDetail)
        }
    }
}
</script>

<style lang="scss" scoped>
.registerForm {
	margin: auto;
	width: 400px;
}

.cardForm {
	display: flex;
	flex-direction: column;
	width: 380px;
	margin-left: 10px;
    margin-top: 40px;
}

.expirySection {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
}

.expirySection .card-validity {
	display: flex;
	flex-direction: column;

	input {
		width: 150px;
	}
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
	margin-top: 3px;
	margin-bottom: 15px;
}

input[type=text]:focus {
	border: 1px solid gainsboro;
}

select {
	width: 170px;
}

button {
	font-family: 'PT Mono', monospace;
	font-size: 22px;
	padding: 1rem;
	border-radius: 8px;
	margin-top: 240px;
	border-width: 2px;
	background-color: rgb(7, 7, 7);
	font-weight: bold;
	color: whitesmoke
}

.vendor {
	width: 380px;
}

</style>