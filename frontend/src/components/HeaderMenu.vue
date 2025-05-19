<template>
  <div class="absolute top-2 left-4">
    <button @click="changeHeaderVisibility" class="relative bg-[var(--cold-turkey)] p-1 flex items-center justify-center rounded-lg hover:bg-[var(--ebb)] z-9 transition duration-400 ease-in-out">
      <img src="../assets/images/menu.png" alt="menu" class="w-[25px] h-[25px]" />
    </button>

    <Transition
      enter-active-class="transition-all duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2 scale-95"
      enter-to-class="opacity-100 translate-y-0 scale-100"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0 scale-100"
      leave-to-class="opacity-0 -translate-y-2 scale-95"
    >
      <header
        v-show="headerVisibility"
        class="flex flex-col gap-2 px-2 py-4 absolute top-[27px] bg-[var(--cold-turkey)] rounded-bl-lg rounded-br-lg rounded-tr-lg shadow-lg"
      >
        <RouterLink to="/" class="text-[14px] hover:bg-[var(--ebb)] px-1 transition duration-500 ease-in-out">Home</RouterLink>
        <RouterLink to="/saved" class="text-[14px] hover:bg-[var(--ebb)] px-1 transition duration-500 ease-in-out">Saved</RouterLink>
        <RouterLink to="/community" class="text-[14px] hover:bg-[var(--ebb)] px-1 transition duration-500 ease-in-out">Community</RouterLink>
        <span class="w-[100px] h-[1px] bg-zinc-800 my-1"></span>
        <RouterLink to="/profile" class="text-[14px] hover:bg-[var(--ebb)] px-1 transition duration-500 ease-in-out">Profile</RouterLink>
      </header>
    </Transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const headerVisibility = ref(false)
const changeHeaderVisibility = () => {
  headerVisibility.value = !headerVisibility.value
}
</script>

