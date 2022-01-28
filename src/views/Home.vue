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
      <a class="card-item" @click="activeCard=card" v-for="card in cards" :key="card.card"> 
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
  align-items: center;
  text-align: center;
  position: relative;

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
  width: 100%;
 display: flex;
 flex-direction: column;
}
.card-item{
  width: 100%;
  align-content: flex-start;
}
.card-item:nth-of-type(2){
  transform: translateY(-80%);
}
.card-item:nth-of-type(3){
  transform: translateY(-160%);
}
.card-item:nth-of-type(4){
  transform: translateY(-240%);
}



/* div .card-list:nth-child(1){

  position:relative;
}
div .card-list:nth-child(2){

  position: absolute;
   transform: translateY(25%);
}
div .card-list:nth-child(3){
    border:1px solid blue;
  position: relative;
   transform: translateY(5%);

}
.card-list:nth-child(4){
  position: absolute;
   transform: translateY(75%);
}
.card-list:nth-child(5){
  position: absolute;
   transform: translateY(100%);
} */



</style>