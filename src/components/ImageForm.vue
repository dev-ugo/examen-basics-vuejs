<script setup>
import { reactive } from "vue";

const emit = defineEmits(['image-submitted']);

const image = reactive({
  url: "",
});

const onSubmit = () => {
  // Validate the URL format
  const urlPattern = /^(http:\/\/|https:\/\/).+$/;
  if (image.url == "" || !urlPattern.test(image.url)) {
    alert("URL is invalid or empty. Please enter a valid image URL.");
    return;
  }

  const imageSubmit = {
    url: image.url
  }

  emit('image-submitted', imageSubmit);

  image.url = ''
};
</script>

<template>
  <form class="image-form" @submit.prevent="onSubmit">
    <h3>Add image</h3>
    <label for="url">Image URL:</label>
    <input id="url" v-model="image.url" />

    <input class="button" type="submit" value="Add" />
  </form>
</template>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
</style>