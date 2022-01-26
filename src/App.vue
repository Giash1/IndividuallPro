<template>
  <div id="app">
    <nav>
   <button v-on:click="route='home'">Home</button>
   <button v-on:click="route='addcard'">Add Card</button>
   </nav>
  <Home :cards="cards" v-if="route ==='home'" @show="shown"/>
  <AddCard v-if="route ==='addcard'" @send="send"/>
    
   
  </div>
</template>

<script>
import Home from "./views/Home.vue"
import AddCard from "./views/AddCard.vue"
export default {
  name: 'App',
   methods: {
   shown(){
    if(this.route=="home"){
      this.route="addcard";
    }else{
      this.route="home";
    }
    },
    send(card){
      console.log(card)
      this.cards.push(card)
      this.route= 'home'
    }
  },
  
  components: {
  Home,
  AddCard,
  },

  data() {
    return {
      route:"home",
      cards:[
                {
          vendor: "bitcoin",
          cardNumber: "XXXXX",
          cardHolder: "MMMMMMMMM",
          cardYear:"YYYYY",
          cardCCV: "CCCCC",
    
      },
      ],
      
        }
      
  },
  };
  
</script>

<style >
@import url('https://fonts.googleapis.com/css?family=PT+Mono|Source+Sans+Pro&display=swap');

* {
  margin: 0;
  padding:0;
  box-sizing: border-box;
  text-transform: uppercase;
  
}
#app {
font-family: PT Mono;
text-align: center;
height: 100%;
display: flex;
justify-content: center;
flex-direction: column;}
body{
  font-family: 'PT Mono', monospace;
}
h1{
  font-family: 'Source Sans Pro', sans-serif;

}

button{
  width: 100px;
  height: 40px;
  margin: 1rem;
}

</style>
