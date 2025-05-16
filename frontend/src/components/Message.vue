<script setup>
import { ref, onMounted } from 'vue';
defineProps(['message', 'status']);

const visible = ref(true);

onMounted(() => {
  setTimeout(() => {
    visible.value = false;
  }, 3000);
})
</script>

<template>
  <div v-if="visible" :class="status" class="fixed right-[20px] top-[40px] py-1 px-4 max-w-[180px] w-full text-center text-[14px]">
    <p>{{ message }}</p>
  </div>
</template>

<style>
.error {
  border: 1px solid #b91c1c;
  background-color: #f87171;
}

.success {
  border: 1px solid #10b981;
  background-color: #d1fae5;
}
</style>
