<template>
    <div>
      <img :src="imageUrl" alt="image cat" class="w-72 h-72 object-cover mb-4" v-show="imageUrl">
    </div>
  </template>
  
  <script>
  export default {
    props: {
      imageUrl: String,
    },
  };
  </script>