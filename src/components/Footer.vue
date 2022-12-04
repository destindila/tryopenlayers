<template>
<footer>
    <div>
      
      <div class="grid lg:grid-cols-3 justify-center gap-12">
        <div>
          <h3 class=" font-bold text-2xl md:text-lg fill-gray-500">About</h3>
        </div>
        <div>
          <h3 class=" font-bold text-2xl md:text-lg fill-gray-500">Company</h3>
        </div>
        <div>
          <h3 class="font-bold text-2xl md:text-lg fill-gray-500">Service</h3>
        </div>
      </div>
    </div>

    <div class="grid place-items-center w-full ">
      <div class="flex items-center gap-10">
        <a href="#" class="bg-secondary h-12 w-12 grid place-items-center rounded-md">
          <img :src="twitter">
        </a>
          
      </div>
    </div>
    </footer>
</template>

<script>
  export default {
    data(){
      return{
        twitter: '/twitter.png'
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
.fill-gray-bk {
  color:rgba(107, 114, 128, var(--tw-fill-opacity));
  fill: rgba(107, 114, 128, var(--tw-fill-opacity));
}
</style>