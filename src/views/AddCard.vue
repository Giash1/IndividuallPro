<template>
  <div class="full-view">
    <div class="card">
      <Card :card="card" />
      
      
      
    </div>
    <br />
    <br />
    <form @submit.prevent="addCard">
      <label for="card-number">CARD NUMBER</label>
      <input
        v-model="card.cardNumber"
        type="text"
        name="user-name"
        placeholder=""
        maxlength="16"
      />
      <br />
      <label for="card-name">CARDHOLDER NAME</label>
      <input
        v-model="card.cardHolder"
        type="text"
        name="user-name"
        placeholder=""
      />
      <br />
     
      
      <div class="valid-thru">
        <span class="year">
           <label for="year">Year</label>
      <input class="year"
        v-model="card.cardYear"
        type="month"
        name=""
        placeholder=""
      />
        </span>

         <span class="cvc">
          <label for="cvc">CCV</label>
      <input class="cardcvc"
        v-model="card.cardCCV"
        type="text"
        name=""
        placeholder=""
      />
           </span> 
      </div>
      <br />
      <label for="vendor">VENDOR</label>
      <select v-model="card.vendor" class="vendor-option" type="options">
        <!-- <option value="vendor">Bitcoin Inc</option>
        <option value="vendor">Block Chain Inc</option>
        <option value="vendor">Evil Corp</option>
        <option value="vendor">Ninja Bank</option> -->
        <option v-for="vendor in vendors" :key="vendor.name" name="vendor" :value="vendor" >
          {{ vendor.name }}
        </option>
      </select>

      <br />
      <button class="addbtn" type="submit">ADD CARD</button>
    </form>
  </div>
</template>

<script>
import Card from "../components/Card.vue";

export default {
  components: {
    Card,
  
  },
  methods:{
addCard(){
 this.$emit('send', {...this.card})
 console.log(this.card)
}
  },
  data() {
    return {
      
      card:
        {
          vendor: [],
          cardNumber: "",
          cardHolder: "",
          cardYear:"",
          cardCCV: "",
        
      vendors: [
        {
          name: "Bitcoin Inc",
          backgroundColor:"blue",
          fontColor: "white",
          logo: require("../assets/bitcoin.svg"),
        },
        {
          name: "Ninja Bank",
          backgroundColor: "black",
          fontColor: "white",
          logo: require("../assets/ninja.svg"),
        },
        {
          name: "Block Chain Inc",
          backgroundColor: "green",
          fontColor: "red",
          logo: require("../assets/blockchain.svg"),
        },
        {
          name: "Evil Corp",
          backgroundColor: "grey",
          fontColor: "white",
          logo: require("../assets/evil.svg"),
        },
      ],
      },

    };
  },
};
</script>

<style scoped >
.full-view {
  margin: auto;
}
.card {
  width: 350px;
  height: 200px;
  background-color: #aaa;
}
form {
  display: flex;
  flex-direction: column;
}
input {
  width: 350px;
  height: 30px;
  text-align: center;
  font-size: 1.1rem;
}

.valid-thru {
  display: flex;
  width: 200px;
}
input.year{
  width: 200px;
}
input.cardcvc{
width: 150px;
}


.month select {
  width: 140px;
  height: 30px;
  text-align: center;
}
.year select {
  width: 140px;
  height: 30px;
  margin-right: 15px;
}
.vendor-option {
  width: 300px;
  height: 30px;
  text-align: center;
  font-size: 1.1rem;
}
.addbtn {
  width: 300px;
  height: 30px;
  background-color: grey;
  color: white;
}
</style>