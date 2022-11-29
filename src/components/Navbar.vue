<script setup>
import { onMounted, ref } from "vue";

const navbar = ref('')
const showMenu = ref(false)
onMounted(() => {
  window.onscroll = () => {
  if(window.scrollY === 0) {
    navbar.value.classList.remove('bg-primary-200')
  } else {
    navbar.value.classList.add('bg-primary-200')
  }
}
})
</script>

<template>
  <nav ref="navbar" class="fixed top-0 left-0 w-full bg-white z-20 transition duration-300"> 
    <div class="container flex items-center justify-between h-20">
      <div class="relative z-30 flex items-center gap-2 mb-2 lg:mb-0">
        <h1 class="fill-gray-500 font-bold lg:text-2xl">AkuPeta</h1>
      </div>
      <div
        class="
          absolute lg:static top-20 inset-x-0
          flex flex-col lg:flex-row items-center gap-5 lg:gap-10
          bg-primary-200 lg:bg-transparent pt-2 pb-10 px-5 lg:p-0
          transition duration-500 lg:duration-200 lg:-translate-y-0
        "
        :class="!showMenu ? 'translate-y-[-150%]' : '-translate-y-0'"
      >
        <a @click="showMenu = false" class="fill-gray-500 font-medium" href="#home">Home</a>
        <a @click="showMenu = false" class="fill-gray-500 font-medium" href="#feature">Feature</a>
        <a @click="showMenu = false" class="fill-gray-500 font-medium" href="#about">About</a>
        <a @click="showMenu = false" class="fill-gray-500 font-medium" href="#sosmed">Social Media</a>
        <button class="hidden md:block px-8 py-2 rounded-full text-white font-medium tracking-wider uppercase bg-secondary w-full lg:w-auto">GET MAPS</button>
      </div>
    </div>
  </nav>
</template>

<style>
.fill-gray-500 {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
.fill-green-500 {
  --tw-fill-opacity: 1;
  fill: rgba(16, 185, 129, var(--tw-fill-opacity));
}
.fill-gray-bk {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
</style>