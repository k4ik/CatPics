<template>
    <div class="max-w-80 w-full flex flex-col items-center bg-white py-4 rounded-2xl shadow-2xl">
      <ImageDisplay :imageUrl="imageUrl"/>
      <ImageGeneratorButton @image-generated="updateImageUrl"/>
    </div>
  </template>
  
  <script>
  import ImageDisplay from './ImageDisplay.vue';
  import ImageGeneratorButton from './ImageGeneratorButton.vue';
  
  export default {
    components: {
      ImageDisplay,
      ImageGeneratorButton,
    },
    data() {
      return {
        imageUrl: '',
      };
    },
    methods: {
      updateImageUrl(newImageUrl) {
        this.imageUrl = newImageUrl;
      },
    },
  };
  </script>
  