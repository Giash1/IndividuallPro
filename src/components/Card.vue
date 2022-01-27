

<template>
  <div id="card" :class="card.vendor">
    <div class="header">
      <div>
        <div class="icon-one">
          <img src="../assets/wifi_white.svg" alt="" />
        </div>
        <div><img src="../assets/chip.svg" alt="" /></div>
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
      <p v-else>XXXXXXXXXXXXX</p>
    </div>
    <div class="footer">
      <div class="cardholder">
        <p>CARDHOLDER NAME</p>
        <p>{{ card.cardHolder }}</p>
      </div>
      <div class="validthru">
        <p>VALID THRU</p>
        <p>{{ date }}</p>
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
    }
  },
};
</script>

<style scoped>
#card {
  width: 350px;
  height: 200px;
  border: 0.2px snow
  
}

.bitcoin {
  background-color: gold;
}
.blockchain {
  background-color: rgba(200, 219, 22, 0.925);
}
.evil {
  background-color: rgb(62, 202, 19);
}
.ninja {
  background-color: rgb(116, 8, 98);
}
.icon-one {
  text-align: start;
}
.header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.main {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
}
.footer {
  display: flex;
flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
}

/* #cardNumber {
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
} */
/* .cardvalid{
  text-align: right;
  opacity: 100%;
  font-weight: bold;
  transform: translateY(-55px);
} */
</style>