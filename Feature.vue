<script setup>
</script>

<template>
  <h2 class="my-5 text-5xl md:text-6xl font-bold fill-gray-500">Feature</h2>
  <br/>
  <section id="feature" class="grid md:grid-cols-2 items-left">
    <div>
     <img v-bind:src="maps3" alt="" class="w-full h-auto" />
    </div>
    <div class="text-left flex flex-col items-left">
      <h2 class="text-2xl md:text-6xl font-bold fill-gray-500">Fitur Pertama</h2>
      <p class="mt-8 md:mt-12 fill-gray-500 text-lg md:text-xl w-full ">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Id id consequat, eu faucibus nulla. Ultrices mattis lacus, sed maecenas nascetur.</p>
    </div>
  </section>
  <br/>
  <section class="grid md:grid-cols-2 items-left">
    <div class="text-left flex flex-col items-left">
      <h2 class="text-2xl md:text-6xl font-bold fill-gray-500">Fitur Kedua</h2>
      <p class="mt-8 md:mt-12 fill-gray-500 text-lg md:text-xl w-full ">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Id id consequat, eu faucibus nulla. Ultrices mattis lacus, sed maecenas nascetur.</p>
    </div>
    <div>
     <img v-bind:src="maps1" alt="" class="w-full h-auto" />
    </div>
  </section>
</template>

<script>
  export default {
    data(){
      return{
        maps1: 'data/maps1.jpg',
        maps3: 'data/maps3.PNG',
        maps4: 'data/maps4.PNG'
      }
    }
  }
</script>
<style>
fill-gray-500 {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
.fill-green-500 {
  --tw-fill-opacity: 1;
  fill: rgba(16, 185, 129, var(--tw-fill-opacity));
}
</style>