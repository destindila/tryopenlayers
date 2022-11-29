<script setup>

</script>

<template>
  <section id="category" class="flex flex-col items-center py-32">
    <h2 class="my-10 text-5xl md:text-6xl font-bold fill-gray-500">Feature</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 place-items-center">
      <div v-for="category of categories" :key="category.title" class="fill-gray-500 grid place-items-center gap-5 text-center">
        <div class="p-10">
          <img v-bind:src="maps1" alt="" class="w-full" />
        </div>
        <h3 class="text-3xl font-bold">Fitur 1</h3>
        <p class="w-3/4">ya ya yaaa ye yee</p>
      </div>
    </div>
  </section>
  <section class="grid grid-flow-col grid-cols-1 md:grid-cols-2 md:gap-10 items-center">
    <div class="md:p-10">
     <img v-bind:src="maps3" alt="" class="w-full" />
    </div>
    <div class="text-center flex flex-col items-center">
      <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">Fitur 2</h2>
      <div class="flex items-center gap-5">
        <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">yeaaaaay</h2>
        <img v-bind:src="maps4" alt="" class="w-full" />
      </div>
      <p class="mt-8 md:mt-12 fill-gray-500 text-lg md:text-xl w-full md:w-[80%]">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Id id consequat, eu faucibus nulla. Ultrices mattis lacus, sed maecenas nascetur.</p>
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