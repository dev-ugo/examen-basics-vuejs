<script setup>
import { computed } from "vue";
const props = defineProps({
  images: {
    type: Array,
    required: true,
  },
});

const lengthImages = computed(() => props.images.length);
</script>

<template>
  <div class="image-container">
    <h3>Images :</h3>
    <p>Number of images: {{ lengthImages }}</p>
    <p v-if="lengthImages > 0">Voici les images :</p>
      <div v-for="(image, index) in images" :key="index" class="image-card">
          <img :src="image.url" alt="Image" width="200" height="200" />
          <button @click="images.splice(index, 1)">Delete</button>
      </div>
    <p v-if="lengthImages == 0">Aucune image disponible</p>
  </div>
</template>

<style scoped>

.image-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.image-card {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}

.image-card img {
  border: 1px solid #ccc;
  border-radius: 5px;
}
.image-card button {
  margin-top: 10px;
  padding: 5px 10px;
  background-color: #f44336;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

</style>
