<script setup>
  
 
</script>

<template>
  <section id="home" class="container mx-auto md:mt-20 ">
    <div>
      <div  class="grid-flow-row">
       <img v-bind:src="maps2" alt="" class="w-full" />
      </div>
      <div class="font-bold fill-gray-500 w-full text-left md:mt-2">
        <h2 class="text-4xl md:text-5xl">AKU PETAAA!!</h2>
        <p class="py-8 text-base loading-6">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Id id consequat, eu faucibus nulla. Ultrices mattis lacus, sed maecenas nascetur. </p>
      </div>
      
    </div>
  </section>
</template>

<script>
  export default {
    data(){
      return{
        maps2: 'data/maps2.PNG'
      }
    }
  }
</script>

<style>
.fill-gray-500 {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
.fill-green-500 {
  --tw-fill-opacity: 1;
  fill: rgba(16, 185, 129, var(--tw-fill-opacity));
}
</style>