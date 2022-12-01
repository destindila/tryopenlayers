<script setup>
import { ref } from 'vue'
import View from 'ol/View'
import Map from 'ol/Map'
import TileLayer from 'ol/layer/Tile'
import OSM from 'ol/source/OSM'
import 'ol/ol.css'
import VectorLayer from 'ol/layer/Vector'
import VectorSource from 'ol/source/Vector'
import GeoJSON from 'ol/format/GeoJSON'
</script>
<template>
  <textarea v-model="geojsonEdit"></textarea>
</template>

<script>
  export default {
    name: 'Edit',
    props: {
      geojson: Object
    },
    computed: {
      geojsonEdit: {
        set(value) {
          this.$emit('change', JSON.parse(value))
        },
        get() {
          return JSON.stringify(this.geojson, null, ' ')
        }
      }
    }
  }
</script>

<style scoped>
  textarea {
    width: 100%;
    height: 100%;
    resize: none;
  }
</style>