<template>
  <section>
    <article v-if="this.cardNumber !=undefined"
    @click="activeCard"
    class="card"
    :class="vendor" 
    >
    <img class ="chip-logo" src="../assets/chip.svg" alt/>
    <img class = "vendor" src="../assets/bitcoin.svg" alt="">
     <img class = "vendor" src="../assets/bitcoin.svg" alt="">

    </article>
  </section>
</template>

<script>
export default {};
</script>

<style>
</style>