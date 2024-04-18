<script setup lang="ts">

</script>

<template>
  <div class="flex justify-center">
    <img src="../assets/success.png" alt="logo" class="success-img" />
  </div>
  <div class="flex justify-center">
    <h3 class="success-text-tittle">Congratulations, your transaction was successful! 🎉</h3>
  </div>
  <div class="flex justify-center">
    <h3 class="success-text-span">Payment successfully processed! 🎉 Thank you for your order. Enjoy the show! 🎭😊</h3>
  </div>
  <div class="flex justify-center">
    <h3 class="success-text-second-tittle">COD (Payment made via Apple Pay) Total amount: $12.30 💸</h3>
  </div>
  <div class="flex justify-center div-button-form">
    <button type="submit" class="button text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Tickets</button>
  </div>
</template>


<style scoped>
.success-img {
  width: 90%;
  padding-top: 55px;
}
.success-text-tittle{
  font-weight: bold;
  font-size: 20px;
  width: 70%;
  padding-bottom: 20px;
}
.success-text-span{
  font-size: 14px;
  width: 42%;
  padding-bottom: 40px;
}
.success-text-second-tittle{
  font-weight: bold;
  font-size: 18px;
  width: 75%;
  padding-bottom: 50px;
}
.button{
  background: #6E7DAB;
  width: 70%;
  font-size: 22px;
}
</style>
