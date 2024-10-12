<script setup>
import { onMounted, ref } from "vue";
import mapboxgl from "mapbox-gl";
import "mapbox-gl/dist/mapbox-gl.css";
import style from "./mapbox/style.json";

mapboxgl.accessToken = "pk.eyJ1IjoianNlc3RyYWRhIiwiYSI6ImNpaWkzMHBnbzAwaW10bWtudjg2czRseTQifQ.Zy_bkLuDadySkJz9t37Rxg";

const mapContainer = ref();

onMounted(() => {
  const map = new mapboxgl.Map({
    "container": mapContainer.value,
    "style": style,
    "zoom": 2.5,
  });

  map.addControl(new mapboxgl.NavigationControl());
});
</script>

<template>
  <div ref="mapContainer" class="map"></div>
</template>

<style scoped>
.map {
  height: 100%;
}
</style>