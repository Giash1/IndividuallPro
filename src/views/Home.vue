<template>
  <section>
    <div class="e-wallet">
      <h1>E-WALLET</h1>
      <br />
      <article>
        <p>ACTIVE CARD</p>
      <Card :card="activeCard"/>
      </article>
    </div>
    <br />
    <div class="card-list">
      <a @click="activeCard=card" v-for="card in cards" :key="card.card"> 
        <Card :card="card" />
      </a>
      </div>
    
    <div>
   <button @click="$emit('show')" class="addbtn">ADD A NEW CARD</button>
    </div>
  </section>
  
</template>

<script>
import Card from "../components/Card.vue";
export default {
  components: {
   Card,

  },
  data() {
    return {
      activeCard:this.cards[0]
    }
  },
  props:["cards"],

  
};
</script>

<style scoped>
section {
  margin: auto;
  
  max-height: 600px;
  align-items: center;
  text-align: center;
  position: relative;
  width: 350px;
}

.addbtn {
  background-color:white;
  width:350px;
  height:60px;
  color:black;
  font-size: 1.2rem;
   transform: translateY(20rem);
   position: relative;
   border-radius: 20px;
  
}
.card-list{
  width: 358px;
 position:relative;
  
  
}
div .card-list:nth-child(1){
  border:1px;
 transform: translateY(50px);
  position:relative;
}
div .card-list:nth-child(2){

  position: relative;
   transform: translateY(5%);
}
div .card-list:nth-child(3){
  position: relative;
   transform: translateY(5%);
}
.card-list:nth-child(4){
  position: relative;
   transform: translateY(5%);
}
.card-list:nth-child(5){
  position: relative;
   transform: translateY(5%);
}



</style>