<template>
  <h1>Basic Mapbox application to display Jordan Map !</h1>
  <div id="map" class="basemap" style='width: 100%; height: 900px;'></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
  name: "BaseMap",
  data() {
    return {
      accessToken:YOURTOKEN,
      center: [35.5, 31.9]
    };
  },

  mounted() {
  this.createMap()
},

methods: {
  async createMap() {
    try {
      mapboxgl.accessToken = this.accessToken;
      this.map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v11",
        center: this.center,
        zoom: 8,
      });

    } catch (err) {
      console.log("map error", err);
    }
  },
},

};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
