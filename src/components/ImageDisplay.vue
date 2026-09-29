<script setup>
import ImageForm from "@/components/ImageForm.vue";
import ImageList from "@/components/ImageList.vue";
import { ref } from "vue";

const images = ref([]);
// const emit = defineEmits(['add-to-array'])

const addImage = (image) => {
  images.value.push(image);
};

</script>

<template>
  <ImageList :images="images"></ImageList>
  <ImageForm @image-submitted="addImage"></ImageForm>
</template>
