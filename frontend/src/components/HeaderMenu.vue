<script setup>
import { ref } from 'vue';

const headerVisibility = ref(false);

const changeHeaderVisibility = () => {
  headerVisibility.value = !headerVisibility.value;
}
</script>

<template>
  <button @click="changeHeaderVisibility">
    <img src="../assets/images/menu.png" alt="menu" />
  </button>

  <header v-if="headerVisibility">
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/saved">Saved</RouterLink>
    <RouterLink to="/community">Community</RouterLink>
    <span></span>
    <RouterLink to="/profile">Profile</RouterLink>
  </header>
</template>
