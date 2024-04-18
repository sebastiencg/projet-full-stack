<script setup lang="ts">
const name = "pierre Lacroix";
</script>

<template>
  <div class="flex  justify-center">
    <h1 class="tittle-donation">Donation to {{name}}</h1>
  </div>
  <div class="flex  justify-center">
    <p class="text-donation text-start">How much do you want to give to this actor ?</p>
  </div>
  <div class="flex  justify-center">
    <div class="flex ">
      <!-- Colonne de gauche -->
      <div class="w-1/4 p-4 text-start ">
        <p>5 $</p>
      </div>
      <div class="w-1/4 p-4 text-start ">
        <p>10 $</p>
      </div>
      <div class="w-1/4 p-4 text-start ">
        <p> 50$</p>
      </div>
      <div class="w-1/4 p-4 text-start ">
        <p>other</p>
      </div>
    </div>
  </div>
</template>


<style scoped>
.tittle-donation {
  padding-bottom: 100px;
  padding-top: 50px;
  font-size: 25px;
  font-weight: bold;
  width: 70%;
}
.text-donation {
  font-size: 16px;
  font-weight: bold;
  width: 70%;
}
</style>
