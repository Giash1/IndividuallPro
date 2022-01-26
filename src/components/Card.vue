

<template>
  <div id="card" :class="card.vendor">
    <div class="header">
      <div class="icon-one"><img src="../assets/wifi_white.svg" alt="" /></div>
      <div class="icon-two"><img src="../assets/chip.svg" alt="" /></div>
      <img v-if="card.vendor" :src="require('../assets/'+card.vendor+'.svg')" alt="">
    </div>
    <div class="main">
      
      <p id="cardNumber">{{ card.cardNumber }}</p>
      <p class="holdername">CARDHOLDER NAME</p>
      <p id="cardHolder">{{ card.cardHolder }}</p>
    </div>
    <div class="footer">
      <p class="cardvalid">VALID THRU</p>
      <p id="expireMonth">{{ card.cardYear }}</p>
      
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
    expireDate() {
      return {};
    },
  },
};
</script>

<style scoped>
#card {
  width: 350px;
  height: 200px;
  
  
 
}
.bitcoin{
  background-color: gold;
}
.blockchain{
  background-color: rgba(200, 219, 22, 0.925);
}
.evil{
  background-color: rgb(62, 202, 19);
}
.ninja{
  background-color: rgb(116, 8, 98);
}
.icon-one{
text-align: start;
}
.icon-two{
  text-align: start;
}
#cardNumber {
  width: 300px;
  letter-spacing: 0.2rem;
  align-items: flex-start;
  padding-top: 10px;
  font-size: 20px;
  position: absolute;
  transform: translateY(-70px);
}
#cardHolder {
  width: 300px;
  text-align: left;
  align-items: center;
  padding-top: 20px;
  font-size: 20px;
  transform: translateY(-10px);
}
.holdername{
  text-align: left;
  opacity: 100%;
  font-weight: bold;
  position: absolute;
  transform: translateY(-15px);
}
.cardvalid{
  text-align: right;
  opacity: 100%;
  font-weight: bold;
  transform: translateY(-60px);
}
#expireMonth{
  text-align: right;
  padding-bottom: 3px;
  transform: translateY(-55px);
}
#ccv{
  text-align: right;
  padding-bottom: 0px;
  
  
}

</style>