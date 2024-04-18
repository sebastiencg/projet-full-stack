
<script setup>
import { ref } from 'vue';

const name = "Pierre Lacroix";
const amount = ref('');
const description = ref('');
const showOtherAmountInput = ref(false);

const handleSubmit = () => {
  const amountValue = amount.value;
  const descriptionValue = description.value;

  // Effectuer une action avec les données du formulaire (ex : envoyer à un serveur)
  console.log('Montant saisi :', amountValue);
  console.log('Description saisie :', descriptionValue);

  // Réinitialiser les champs du formulaire après la soumission (facultatif)
  amount.value = '';
  description.value = '';
};

// Fonction pour définir le montant sélectionné
const setAmount = (selectedAmount) => {
  amount.value = selectedAmount.toString();
  showOtherAmountInput.value = false; // Cacher le champ "Autre montant"
};

// Fonction pour activer/désactiver le champ "Autre montant"
const toggleOtherAmountInput = () => {
  showOtherAmountInput.value = true; // Afficher le champ "Autre montant"
  amount.value = '';
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
      <!-- Boutons pour les montants fixes -->
      <button class="decoration-button-donation" @click="setAmount(5)">5 $</button>
    </div>
    <div class="w-1/4 p-4 text-start">
      <button class="decoration-button-donation" @click="setAmount(10)">10 $</button>
    </div>
    <div class="w-1/4 p-4 text-start">
      <button class="decoration-button-donation" @click="setAmount(50)">50 $</button>
    </div>
    <div class="w-1/4 p-4 text-start">
      <!-- Bouton "other" pour un montant personnalisé -->
      <button class="decoration-button-donation" @click="toggleOtherAmountInput">other</button>
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
  border-radius: 10px;
  width: 70px;
  height: 40px;
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
