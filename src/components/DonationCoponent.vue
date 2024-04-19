
<script setup>
import { ref } from 'vue';

const name = "Pierre Lacroix";
const amount = ref(5);
const description = ref('');
const showOtherAmountInput = ref(false);
const decoration = ref(5);

const handleSubmit = () => {
  const amountValue = amount.value;
  const descriptionValue = description.value;

  console.log('Montant saisi :', amountValue);
  console.log('Description saisie :', descriptionValue);
  amount.value = '';
  description.value = '';
};

const setAmount = (selectedAmount) => {
  amount.value = selectedAmount.toString();
  showOtherAmountInput.value = false;
  decoration.value= amount.value;
};

const toggleOtherAmountInput = () => {
  showOtherAmountInput.value = true;
  amount.value = '';
  decoration.value= 0
};
</script>

<template>
  <div class="flex justify-center">
    <h1 class="tittle-donation">Donation to {{ name }}</h1>
  </div>
  <div class="flex justify-center">
    <p class="text-donation text-start">How much do you want to give to this actor?</p>
  </div>
  <br>
  <br>
  <div class="flex justify-center">
    <div class="w-1/4 p-4 text-start">
      <template v-if="decoration == 5">
        <button class="decoration-button-donation-variant" @click="setAmount(5)">5 $</button>
      </template>
      <template v-else>
        <button class="decoration-button-donation" @click="setAmount(5)">5 $</button>
      </template>
    </div>
    <div class="w-1/4 p-4 text-start">
      <template v-if="decoration == 10">
        <button class="decoration-button-donation-variant" @click="setAmount(10)">10 $</button>
      </template>
      <template v-else>
        <button class="decoration-button-donation" @click="setAmount(10)">10 $</button>
      </template>
    </div>
    <div class="w-1/4 p-4 text-start">
      <template v-if="decoration == 50">
        <button class="decoration-button-donation-variant" @click="setAmount(50)">50 $</button>
      </template>
      <template v-else>
        <button class="decoration-button-donation" @click="setAmount(50)">10 $</button>
      </template>
    </div>
    <div class="w-1/4 p-4 text-start">
      <template v-if="decoration == 0">
        <button class="decoration-button-donation-variant" @click="toggleOtherAmountInput">other</button>
      </template>
      <template v-else>
        <button class="decoration-button-donation" @click="toggleOtherAmountInput">other</button>
      </template>
    </div>
  </div>

  <!-- Formulaire de donation -->
  <div class="container mx-auto mt-10">
    <form @submit.prevent="handleSubmit">
      <!-- Champ Montant -->
      <div class="mb-4">
        <input v-if="showOtherAmountInput" type="number" id="amount" v-model="amount" placeholder="Entrez le montant" class="input-text-donation mt-1 p-2 border border-gray-300 rounded-md w-full" required>
      </div>

      <!-- Zone de texte (optionnelle) -->
      <div class="mb-4">
        <textarea id="description" v-model="description" placeholder="Message (optional)" rows="4" class="input-text-donation mt-1 p-2 border border-gray-300 rounded-md w-full"></textarea>
      </div>

      <!-- Bouton Soumettre -->
      <button type="submit" class="button-submit-donation bg-blue-500 text-white font-bold py-2 px-4 rounded">Send</button>
    </form>
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
.decoration-button-donation{

  border: solid 1px #6E7DAB;
  border-radius: 10px;
  width: 70px;
  height: 40px;
  }
.decoration-button-donation-variant{
  border: solid 1px #6E7DAB;
  background: #6E7DAB;
  border-radius: 10px;
  width: 70px;
  height: 40px;
  color: white;
}
.input-text-donation{
  color: #6E7DAB;
  border:  1px solid #6E7DAB;
  background: #D1E3DD;

}
.button-submit-donation{
  background: #D1E3DD;
  width: 100%;
  color: #6E7DAB;
  border:  1px solid #6E7DAB;
}
</style>
