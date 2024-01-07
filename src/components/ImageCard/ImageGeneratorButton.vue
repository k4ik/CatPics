<template>
    <form @submit.prevent>
      <button class="h-auto px-4 py-1 rounded-lg bg-green-500" @click="generateImage">Generate pictures</button>
    </form>
  </template>
  
  <script>
  export default {
    methods: {
      async generateImage() {
        const req = await fetch("https://api.thecatapi.com/v1/images/search");
        const data = await req.json();
  
        this.$emit("image-generated", data[0].url);
      },
    },
  };
  </script>