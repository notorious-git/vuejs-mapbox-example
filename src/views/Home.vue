<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div id="map"></div>
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
}
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
      message: "Welcome to Vue.js!",
      places: [
        { lat: -25.363, lng: 131.044, description: "A place in Australia" },
        { lat: -33.8675, lng: 151.207, description: "The main city!" }
      ]
    };
  },
  created: function() {},
  mounted: function() {
    mapboxgl.accessToken =
      "pk.eyJ1IjoicGV0ZXJ4amFuZyIsImEiOiJjam94YWZieXExYnQ0M3BucXZwbmV2Y2VsIn0.pmLbX0YPw86c5r8YlyZr7w";
    var map = new mapboxgl.Map({
      container: "map", // container id
      style: "mapbox://styles/mapbox/streets-v9", // stylesheet location
      center: [this.places[0].lng, this.places[0].lat], // starting position [lng, lat]
      zoom: 3 // starting zoom
    });

    // for (var i = 0; i < this.places.length; i++) {
    //   var place = this.places[i];
    //   var popup = new mapboxgl.Popup({ offset: 25 }).setText(place.description);
    //   var marker = new mapboxgl.Marker()
    //     .setLngLat([place.lng, place.lat])
    //     .setPopup(popup)
    //     .addTo(map);
    // }

    this.places.forEach(function(place) {
      var popup = new mapboxgl.Popup({ offset: 25 }).setText(place.description);
      var marker = new mapboxgl.Marker()
        .setLngLat([place.lng, place.lat])
        .setPopup(popup)
        .addTo(map);
    });
  },
  methods: {},
  computed: {}
};
</script>
