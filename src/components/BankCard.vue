<template>
<div class="card-layout">
    <div class="card" :class="[card.vendor]" @click="$emit('click')">      
        <div class="icons">
            <div class="wifiAndChip">
                <img class="iconImg" src="../assets/wifi_white.svg" width="50px">
                <img class="iconImg" src="../assets/chip.svg" width="50px">
            </div>
                 <img v-if="card.vendor" :src="require(`../assets/${card.vendor}.svg`)" class="iconImg">            
                 <img v-else :src="require(`../assets/bitcoin.svg`)" class="iconImg">            
        </div>
        <div class="cardNumber">
            <h3>{{spaceNumbers}}</h3>
        </div>
        <div class="cardHolder">
            <div class="cardNameWrapper">
                <p>CARDHOLDER NAME</p>
                <div class="cardNames">
                    <p>{{card.cardHolderName}}</p>
                </div>     
            </div>
            <div class="validWrapper">
              <p>VALID UNTIL</p>
              <div class="expiremonthWrapper">
                  {{validDate}}
              </div>          
            </div>           
        </div>   
    </div> 
</div>  
</template>

<script>
export default {
    props: ['card'],
    methods:{  
        activeCardFunction(){
            this.card.activecard = true
            console.log(this.card)
        }
    },
    computed:{
        validDate(){
            return this.card.validMonth + '/' + this.card.validYear
        },
        spaceNumbers(){
            let space =''
            for(let i=0; i < this.card.cardNumber.length; i++){
                if(i % 4 == 0){
                    space +=" ";
                }
                space +=this.card.cardNumber[i]
                if(space.length>19){
                    return space
                }
            }
	return space
        }
    }
}
</script>

<style lang="scss" scoped>

.card{
     
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 380px;
    height: 240px;
    background-color: #D0D0D0;
    border-radius: 8px;
    padding: 10px;
    box-shadow:  0px 0px 32px rgba(0, 0, 0, 0.1);
       
}
.bitcoin  {
  background-color: #ffae34;
   text-shadow: 0.5px 0.5px #5a5a5a;
}
.blockchain {
  background-color: #8b58f9;
  color: white;
  text-shadow: 0.5px 0.5px #918f8f;
}
.evil {
  background-color: #f33355;
  color: white;
  text-shadow: 0.5px 0.5px #918f8f;
}
.ninja {
  background-color: #222222;
  color: white;
  text-shadow: 0.5px 0.5px #918f8f;
}
.icons{
    display: flex;
    justify-content: space-between;
 
}
.wifiAndChip{
    display: flex;
    flex-direction: column;
}
.cardNumber{
    font-size: 24px;
    text-align: center;

}
.cardHolder{
    display: flex;
    justify-content: space-between;
}
.cardNameWrapper p{
    padding: 5px;
}
.cardNames{
    display: flex;
}
.cardNames p{
    padding: 5px;
}
.validWrapper p{
padding: 5px;
}
.iconImg{
    width: 40px;
    height: 50px;
}
.expiremonthWrapper{
    text-align: end;
}
.expiremonthWrapper span{
padding:5px
}

</style>