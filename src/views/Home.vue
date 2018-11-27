<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div id='map'></div>
  </div>
</template>

<style>
  body { margin:0; padding:0; }
  #map { 
    height: 400px;
    width: 100%;
  }
</style>

<script>
/* global mapboxgl */
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!"
    };
  },
  created: function() {},
  mounted: function() {
    mapboxgl.accessToken = 'pk.eyJ1IjoicGV0ZXJ4amFuZyIsImEiOiJjam94YWZieXExYnQ0M3BucXZwbmV2Y2VsIn0.pmLbX0YPw86c5r8YlyZr7w';
    var map = new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/streets-v9', // stylesheet location
      center: [-74.50, 40], // starting position [lng, lat]
      zoom: 9 // starting zoom
    });
  },
  methods: {},
  computed: {}
};
</script>
