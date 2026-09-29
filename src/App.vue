<script setup>
import ImageDisplay from '@/components/ImageDisplay.vue';
</script>

<template>
  <h1>Home</h1>
  <div>
      <ImageDisplay></ImageDisplay>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
</style>
