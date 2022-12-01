<script setup>
import HelloWorld from './components/HelloWorld.vue'
import MapContainer from './components/MapContainer.vue'
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import Feature from './components/Feature.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'
</script>
<template>
  <div>
    <Navbar/>
    <Home/>    
    <Feature/>
    <MapContainer/>    
    <Footer/>
  </div>
</template>

<script>
  export default {
    name: 'App'
  }
</script>

<style>
  html, body {
    height: 100%;
    margin: 0;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    height: full;
    display: grid;
    box-sizing: border-box;
  }
  .cell {
    border-radius: 4px;
    background-color: lightgrey;
  }
  .cell-map {
    grid-column: 1;
    grid-row-start: 1;
    grid-row-end: 3;
  }
  .cell-edit {
    grid-column: 2;
    grid-row: 1;
  }
  .cell-inspect {
    grid-column: 2;
    grid-row: 2;
  }
</style>