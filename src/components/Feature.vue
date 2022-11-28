<<<<<<< HEAD
<script setup>
  
</script>

<template>
  <section id="category" class="flex flex-col items-center py-32">
    <h2 class="my-10 text-5xl md:text-6xl font-bold fill-gray-500">FEATURE</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 place-items-center">
      <div v-for="category of categories" :key="category.title" class="fill-gray-500 grid place-items-center gap-5 text-center">
        <div class="p-10">
          <img src="data/maps4.PNG" class="w-full">
        </div>
        <h3 class="text-3xl font-bold">yeeaay</h3>
        <p class="w-3/4">ini adalah fitur pertama</p>
      </div>
    </div>
  </section>
  <section class="grid grid-flow-col grid-cols-1 md:grid-cols-2 md:gap-10 items-center">
    <div class="md:p-10">
      <img src="data/maps3.PNG">
    </div>
    <div class="text-center flex flex-col items-center">
      <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">BLALALALAA</h2>
      <div class="flex items-center gap-5">
        <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">yeaaaaay</h2>
        <img src="data/maps4.PNG" class="w-9 md:w-12" alt="head2">
      </div>
      <p class="mt-8 md:mt-12 fill-gray-500 text-lg md:text-xl w-full md:w-[80%]">ini adalah fitur kedua.</p>
    </div>
  </section>
</template>


<style>
fill-gray-500 {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
.fill-green-500 {
  --tw-fill-opacity: 1;
  fill: rgba(16, 185, 129, var(--tw-fill-opacity));
}
=======
<script setup>
  
</script>

<template>
  <section id="category" class="flex flex-col items-center py-32">
    <h2 class="my-10 text-5xl md:text-6xl font-bold fill-gray-500">FEATURE</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 place-items-center">
      <div v-for="category of categories" :key="category.title" class="fill-gray-500 grid place-items-center gap-5 text-center">
        <div class="p-10">
          <img src="data/maps4.PNG" class="w-full">
        </div>
        <h3 class="text-3xl font-bold">yeeaay</h3>
        <p class="w-3/4">ini adalah fitur pertama</p>
      </div>
    </div>
  </section>
  <section class="grid grid-flow-col grid-cols-1 md:grid-cols-2 md:gap-10 items-center">
    <div class="md:p-10">
      <img src="data/maps3.PNG">
    </div>
    <div class="text-center flex flex-col items-center">
      <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">BLALALALAA</h2>
      <div class="flex items-center gap-5">
        <h2 class="text-5xl md:text-6xl font-bold fill-gray-500">yeaaaaay</h2>
        <img src="data/maps4.PNG" class="w-9 md:w-12" alt="head2">
      </div>
      <p class="mt-8 md:mt-12 fill-gray-500 text-lg md:text-xl w-full md:w-[80%]">ini adalah fitur kedua.</p>
    </div>
  </section>
</template>


<style>
fill-gray-500 {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
.fill-green-500 {
  --tw-fill-opacity: 1;
  fill: rgba(16, 185, 129, var(--tw-fill-opacity));
}
>>>>>>> 222b48a (windicss update)
</style>