<template>
  <div>

    <!-- <head>
      
      <script src="https://api.tomtom.com/maps-sdk-for-web/cdn/6.x/6.25.0/maps/maps-web.min.js"></script>
    </head> -->
    <div id="map"></div>



  </div>
</template>

<script>
import tt from "@tomtom-international/web-sdk-maps"

export default {
  data() {
    return {

    }
  },
  //   methods: {
  //     mappa() {
  //       let center = [41.87194, 12.56738];
  //       const map = tt.map({
  //         key: "MpaHGo7EnupZJUAyN8RITwmX6hU3i9Rz",
  //         container: "map",
  //         center: center,
  //         zoom: 10
  //       })
  //       map.on('load', () => {
  //         new tt.Marker().setLngLat(center).addTo(map)
  //       })

  //     }

  //   },
  //   mounted() {
  //     this.mappa
  //   }
}
</script>

<style>
#mpa {
  width: 500px;
  height: 400px;
}
</style>