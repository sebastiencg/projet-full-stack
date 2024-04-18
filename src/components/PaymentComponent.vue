<script setup lang="ts">

</script>

<template>
  <div class="payment-body ">
    <div class="flex  justify-center">
      <h1 class="tittle-payment">Payment</h1>
    </div>
    <div class="flex  justify-center">
      <div class="flex card-payment">
        <!-- Colonne de gauche -->
        <div class="w-1/2 p-4 text-start">
          <p class=" font-bold  text-gauche-payment-top">Total amount</p>
          <p> 12,30 $</p>
          <br>
          <p class=" font-bold  text-gauche-paymenboldt-top" >Date</p>
          <p> june 15</p>
        </div>

        <!-- Colonne de droite -->
        <div class="w-1/2 p-4  ">
          <h2 class="text-lg font-bold mb-4 flex justify-end  text-droite-payment-top">Details</h2>
          <div class="flex justify-end">
            <img src="../assets/Apple-Pay-Logo.png" alt="logo" class="logo-apple  flex justify-end " height="" />
          </div>
        </div>

      </div>
    </div>
    <br>
    <br>
    <div class="flex  justify-center ">
      <div class="flex card-payment">
        <div class="flex card-payment">

          <div class="w-1/2 p-4">
            <p class=" font-bold mb-4 text-gauche-payment-top text-start">COD</p>
          </div>
          <div class="w-1/2 p-4">
            <h2 class="text-lg font-bold mb-4 flex justify-end  text-droite-payment-top">Details</h2>
          </div>

        </div>


      </div>

    </div>
    <div class="flex  justify-center  card-payment-variant-payment ">
      <div class="flex card-payment-variant justify-center">
        <p class="p-card-info">Enjoy a hassle-free purchase with Apple Pay! When your order arrives, you can conveniently pay using Apple Pay. No need to enter details, it's quick and secure. The total amount includes Apple Pay service fees.</p>

      </div>
    </div>

  </div>
  <div class="flex justify-center div-button-form">
    <button type="submit" class="button text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Pay</button>
  </div>
</template>


<style scoped>

.tittle-payment {
  padding-bottom: 25px;
  padding-top: 50px;
  font-size: 25px;
  font-weight: bold;
}
.card-payment{
  background-color: white;
  border-radius: 10px;
  width: 95%;
}
.card-payment-variant{
  background-color: white;
  border-radius: 10px;
  width: 95%;
  position: relative;
  top: -15px;
}
.card-payment-variant-payment{
  padding-bottom: 230px;

}
.text-droite-payment-top{
  font-size: 12px;
  color: #3887FF;
}
.logo-apple{
  width: 80%;
}
.p-card-info{
  font-size: 12px;
  width: 70%;
  padding-bottom: 15px;
}
.text-gauche-payment-top{
  font-weight: bolder;
}
.button{
  background: #6E7DAB;
  width: 80%;
  font-size: 22px;
}
</style>
