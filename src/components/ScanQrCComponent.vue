<!-- CameraComponent.vue -->
<template>
  <div>
    <h1>Application Vue avec Webcam</h1>
      <video ref="videoElement" autoplay></video>
      <button @click="toggleCamera">{{ cameraActive ? 'Arrêter la Caméra' : 'Activer la Caméra' }}</button>

  </div>
</template>

<script setup>
import { ref, onBeforeUnmount } from 'vue';

const isCameraAvailable = ref(false);
const cameraActive = ref(false);
let videoElement = null;

const toggleCamera = async () => {
  try {
    if (!cameraActive.value) {
      const stream = await navigator.mediaDevices.getUserMedia({ video: true });
      videoElement.srcObject = stream;
      isCameraAvailable.value = true;
      cameraActive.value = true;
    } else {
      const stream = videoElement.srcObject;
      if (stream) {
        const tracks = stream.getTracks();
        tracks.forEach(track => track.stop());
      }
      videoElement.srcObject = null;
      isCameraAvailable.value = false;
      cameraActive.value = false;
    }
  } catch (error) {
    console.error('Erreur lors de l\'accès à la caméra :', error);
    isCameraAvailable.value = false;
    cameraActive.value = false;
  }
};

// Nettoyer les ressources à la destruction du composant
onBeforeUnmount(() => {
  if (videoElement) {
    const stream = videoElement.srcObject;
    if (stream) {
      const tracks = stream.getTracks();
      tracks.forEach(track => track.stop());
    }
  }
});
</script>

<style scoped>
/* Styles CSS (facultatif) */
h1 {
  font-size: 24px;
  margin-bottom: 20px;
}

video {
  width: 100%;
  max-width: 640px;
  height: 100%;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  color: #ffffff;
  background: #6E7DAB;

  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
  font-size: 22px;
}

button:hover {
  background: #6E7DAB;

}
</style>
