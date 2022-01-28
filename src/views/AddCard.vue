<template>
  <div class="full-view">
     <div class="e-wallet">
      <h1>ADD A NEW <p> BANK CARD</p></h1>
      <br />
      <article>
        <p>NEW CARD</p>
      <Card :card="activeCard"/>
      </article>
    </div>
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
        maxlength="18"
      />
      <br />
     
      
      <div class="valid-thru">
        <span class="year">
           <label for="year">EXPIRE DATE</label>
      <input class="year"
        v-model="card.cardYear"
        type="month"
        name=""
        placeholder=""
      />
        </span>

         <!-- <span class="cvc">
          <label for="cvc">CCV</label>
      <input class="cardcvc"
        v-model="card.cardCCV"
        type="text"
        name=""
        placeholder=""
      />
           </span>  -->
      </div>
      <br />
      <label for="vendor">VENDOR</label>
      <select v-model="card.vendor" class="vendor-option" type="options">
         <option value="bitcoin">Bitcoin Inc</option>
        <option value="blockchain">Blockchain Inc</option>
        <option value="evil">Evil Corp</option>
        <option value="ninja">Ninja Bank</option>
        <!-- <option v-for="vendor in vendors" :key="vendor.name" name="vendor" :value="vendor" >
          {{ vendor.name }}
        </option> -->
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
 this.$emit('send', this.card)
 console.log(this.card)
}
  },
  data() {
    return {
      
      card:
        {
          vendor: "",
          cardNumber: "",
          cardHolder: "",
          cardYear:"",
          
    
      },

    };
  },
};
</script>

<style scoped>
.full-view {
  margin: auto;
}
.card {
  width: 382px;
  height: 241px;
  background-color: #D6D6D6;
  border-radius: 10px;
}
form {
  display: flex;
  flex-direction: column;
}
input {
  width: 382px;
  height: 30px;
  text-align: center;
  font-size: 1.1rem;
  letter-spacing: 0.2rem;
}

.valid-thru {
  display: flex;
  width: 200px;
}
input.year{
  width: 382px;
}

/* .month select {
  width: 140px;
  height: 30px;
  text-align: center;
}
.year select {
  width: 140px;
  height: 30px;
  margin-right: 15px;
} */
.vendor-option {
  width: 382px;
  height: 30px;
  text-align: center;
  font-size: 1.1rem;
}
.addbtn {
  margin: 0;
  position: absolute;
  transform: translateY(280px);
  width: 382px;
  color: white;
  background-color: black;
  font-family: "PT Mono", monospace;
  font-weight: bold;

}
</style>