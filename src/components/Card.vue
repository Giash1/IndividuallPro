

<template>
  <div id="card" :class="card.vendor">
    <div class="header">
      <div>
        <div class="icon-one">
          <img src="../assets/wifi_white.svg" alt="" />
        </div>
        <div :class="chip"><img src= "../assets/chip.svg" alt=""/></div>
      </div>
      <div>
        <img
          v-if="card.vendor"
          :src="require('../assets/' + card.vendor + '.svg')"
          alt=""
        />
      </div>
    </div>

    <div class="main">
      <p v-if="card.cardNumber">{{ spaceNumber }}</p>
      <p v-else> XXXX  XXXX  XXXX  XXXX</p>
    </div>
    <div class="footer">
      <div class="cardholder">
        <p>CARDHOLDER NAME</p>
        <p v-if="card.cardHolder">{{ card.cardHolder }}</p>
        <p class="firstname" v-else>FIRSTNAME LASTNAME</p>
      </div>
      <div class="validthru">
        <p>VALID THRU</p>
        <p v-if="card.cardYear">{{ date }}</p>
        <p class="mm" v-else>MM/YY</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ["card"],
  computed: {
    spaceNumber() {
      return (
        this.card.cardNumber.slice(0, 4) +
        " " +
        this.card.cardNumber.slice(4, 8) +
        " " +
        this.card.cardNumber.slice(8, 12) +
        " " +
        this.card.cardNumber.slice(12, 16)
      );
    },
   
    date(){
      return(
        this.card.cardYear.slice(5,7) + 
        "/" + 
        this.card.cardYear.slice(2,4) 

      )
    },
    chip(){
     if (this.vendor)
      return "chipWhite" 
      return ""
   }

  },
};
</script>

<style scoped>
#card {
  height: 241px;
  width:350;
  border: 0.2px snow;
  border-radius: 10px;
  padding: 1.4rem;
  color: whitesmoke;
  font-family: "PT Mono", monospace;
  
}
.chipWhite{
  background-color: white;
  border-radius: 8px;
  height: 40px;
}
.bitcoin {
  background-color: #ffae34;
}
.blockchain {
  background-color: #8b58f9;
}
.evil {
  background-color: #f33355;
}
.ninja {
  background-color: #222222;
  color: white;
}
.icon-one {
  text-align: start;
}
.header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  color: black;
}
.main {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
  padding-top: 5px;
  width: 100%;
}
.footer {
  display: flex;
flex-direction: row;
  justify-content: space-between;
  position: relative;
  padding-top: 25px;
}
.cardholder{
  display: flex;
  padding-left: 0px;
  align-items: flex-start;
  flex-direction: column;
  font-family: "PT Mono", monospace;
  font-weight: 100;
  font-size: 12px;
}
.firstname{
  color:black;
}
 .validthru{
  display: flex;
  padding-left: 0px;
  align-items: flex-start;
  flex-direction: column;
  font-family: "PT Mono", monospace;
  font-weight: 100;
  font-size: 12px;
} 
.mm{
  color:black;
}
</style>