<template>
  <section>
    <div class="e-wallet">
      <h1>E-WALLET</h1>
      <br />
      <article>
        <p>ACTIVE CARD</p>
        <div class="active"></div>
      </article>
    </div>
    <br />
    <div class="card-list">
      <a v-for="card in cards" :key="card">
        <Card :card="card" />
      </a>
      
      </div>
    
    <div>
   <button class="addbtn">ADD A NEW CARD</button>
    </div>
  </section>
</template>

<script>

export default {
  components: {
   

  },
  props:["cards"],

  
};
</script>

<style>
section {
  margin: auto;
  padding: 10px;
  height: auto;
  align-items: center;
  text-align: center;
}
.active {
  height: 200px;
  width: 300px;
  background: grey;
  padding-left: 400px;
}
form {
  margin-left: 0px;
  text-align: start;
}
.addbtn {
  background-color: green;
  width:300px;
  height:40px;
  color:white;
  font-size: 1.2rem;
}
</style>