

<template>
  <div id="card">
    <div class="header">
      <div class="icon-one"><img src="../assets/wifi_white.svg" alt="" /></div>
      <div class="icon-two"><img src="../assets/chip.svg" alt="" /></div>
    </div>
    <div class="main">
      <p id="cardNumber">{{ card.cardNumber }}</p>
      <p id="cardHolder">{{ card.cardHolder }}</p>
    </div>
    <div class="footer">
      <p id="expireMonth">{{ card.cardYear }}</p>
      <p id="ccv">{{ card.cardCCV }}</p>
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
  background-color: rgba(67, 23, 223, 0.822);
}
.icon-one{
text-align: start;
}
.icon-two{
  text-align: start;
}
#cardNumber {
  width: 300px;
  text-align: center;
  align-items: center;
  padding-top: 10px;
  color: aqua;
  font-size: 20px;
}
#cardHolder {
  width: 300px;
  text-align: left;
  align-items: center;
  padding-top: 20px;
  color: aqua;
  font-size: 20px;
}
#expireMonth{
  text-align: right;
  padding-top: 8px;
}
#ccv{
  text-align: right;
  padding-top: 5px;
  
}
</style>