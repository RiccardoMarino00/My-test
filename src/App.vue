<script>
// import HelloWorld from './components/HelloWorld.vue'
// import tt from "@tomtom-international/web-sdk-maps"
import { onMounted, ref } from 'vue'
// import SearchBoxS from 'node_modules/@tomtom-international/web-sdk-plugin-searchbox/dist/SearchBox.css'
// import { services } from '@tomtom-international/web-sdk-services';
// import SearchBox from '@tomtom-international/web-sdk-plugin-searchbox';


export default {
  name: 'map',
  setup() {
    const mapRef = ref(null);
    onMounted(() => {

      const tt = window.tt;
      var map = tt.map({
        key: 'MpaHGo7EnupZJUAyN8RITwmX6hU3i9Rz',
        container: mapRef.value,
        style: 'tomtom://vector/1/basic-main',
      });
      map.addControl(new tt.FullscreenControl());
      map.addControl(new tt.NavigationControl());
    })
    function addMarker(map) {
      const tt = window.tt;
      var location = [-121.91595, 37.36729];
      var popupOffset = 25;

      var marker = new tt.Marker().setLngLat(location).addTo(map);
      var popup = new tt.Popup({ offset: popupOffset }).setHTML("10");
      marker.setPopup(popup).togglePopup();
    }

    return {
      mapRef,
    }
  },
  data() {
    return {

    }
  },
  methods: {
    //   mappa() {
    //     let center = [41.87194, 12.56738];
    //     const map = tt.map({
    //       key: "MpaHGo7EnupZJUAyN8RITwmX6hU3i9Rz",
    //       container: "map",
    //       center: center,
    //       zoom: 10
    //     })
    //     map.on('load', () => {
    //       new tt.Marker().setLngLat(center).addTo(map)
    //     })

    //   }

    // },
    // mounted() {
    //   this.mappa
    // setup() {
    //   const mapRef = ref(null);
    //   onMounted(() => {

    //     const tt = window.tt;
    //     var map = tt.map({
    //       key: '<INSERT API KEY HERE>',
    //       container: mapRef.value,
    //       style: 'tomtom://vector/1/basic-main',
    //     });
    //     map.addControl(new tt.FullscreenControl());
    //     map.addControl(new tt.NavigationControl());
    //   })

    //   return {
    //     mapRef,
    //   }
    // }
  }
}

</script>

<template>

  <head>
    <link rel="stylesheet" type="text/css"
      href="https://api.tomtom.com/maps-sdk-for-web/cdn/6.x/6.25.0/maps/maps.css" />
  </head>
  <div class="container-my">
    <nav class="navbar-my">
      <ul class="navbar-list-my">
        <li class="navbar-item-my">
          <span>
            GitHUb
          </span>
          <span class="text">&#9730;</span>
        </li>
        <li class="navbar-item-my">
          <span>Contatti</span>
          <span class="text">&#9730;</span>
        </li>
        <li class="navbar-item-my">
          <span>Info</span>
          <span class="text">&#9730;</span>
        </li>
        <li class="navbar-item-my last">
          <span>Profilo</span>
          <span class="text">&#9730;</span>
        </li>
      </ul>
    </nav>
    <div id='map' ref="mapRef"></div>
    <div class="container-slider">
      <div class="slider-wrapper">
        <div class="slider">
          <img id="slide-1" src="../public/demo-takeout-600x450.jpg" alt="">
          <img id="slide-2" src="../public/demo_landscaper-600x450.jpg" alt="">
          <img id="slide-3" src="../public/demo_nightclub-600x450.jpg" alt="">
        </div>
        <div class="slider-nav">
          <a href="#slide-1"></a>
          <a href="#slide-2"></a>
          <a href="#slide-3"></a>
        </div>
      </div>
    </div>
  </div>
  <div class="container-house">
    <header class="header-house">
      <p class="logo-house">LOGO</p>
      <ul class="list-nav-house">
        <li><a href="#">About</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">About</a></li>
      </ul>
    </header>
    <main>
      <div class="container-main">
        <div class="description">

          <p>5 mq </p> <br>
          <h1><strong>Salotto</strong></h1><span>10$/Notte</span>
          <p>Accogliente e moderno</p>
          <button>See more</button>
        </div>
        <div class="img-hero">
          <img src="../public/Minimalist-interior-yellow-living-room,-3D-render-on-transparent-background-PNG.png"
            alt="">
        </div>

      </div>
    </main>

  </div>

  <!-- <HelloWorld /> -->

</template>

<style scoped>
.img-hero img {
  width: 500px;
}

.description {
  text-align: left;
  line-height: 30px;
}

.description span {
  margin-left: 20px;
}

.description h1 {
  font-size: 60px;
  font-family: Georgia, 'Times New Roman', Times, serif;
  font-weight: bold;
  display: inline-block;
}

.description button {
  background-color: #D09E25;
  border-radius: 5px;
  border: none;
  padding: 10px;
  font-size: medium;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  cursor: pointer;

}

.container-main {
  display: grid;
  height: 100%;
  width: 100%;
  position: relative;
  grid-template-columns: repeat(2, 1fr);
  align-items: center;
  text-align: center;
  margin-top: 50px;
  padding: 0 19%;
}

.container-house {
  height: 100vh;
  background: rgb(0, 0, 0);
  background: linear-gradient(162deg, rgba(0, 0, 0, 1) 51%, rgba(159, 131, 13, 1) 100%);
  color: white;
}

.header-house {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  z-index: 1000;
  width: 100%;
}

.list-nav-house {
  display: flex;
}

.list-nav-house li {
  margin-right: 40px;
}

.logo-house {
  margin-left: 40px;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

#map {
  height: 50vh;
  width: 50vw;
}

.icon {
  color: black;
}

.navbar-my {
  width: 60px;
  transition: 300ms width ease-out;
  background-color: chocolate;
  color: white;
}

.navbar-my:hover {
  width: 150px;
}

.navbar-my:hover .text {
  display: inline-block;
  margin-left: 10px;
  transform: rotate(-180deg);
}

.container-my {
  display: flex;
}

.navbar-list-my {
  display: flex;
  flex-direction: column;
  height: 100vh;
  align-items: center;


}

.navbar-item-my {
  margin-top: 20px;
}

/* .navbar-list-my:last-child {
  margin-top: auto;
} */

.last {
  margin-top: auto;
  margin-bottom: 20px;
}

.text {
  display: none;
  transform: rotate(0deg);
  transition: transform 1s;
}

.container-slider {
  padding: 10px;
  scrollbar-width: 0;
}

.slider-wrapper {
  position: relative;
  max-width: 600px;
  margin: 0 auto;
}

::-webkit-scrollbar {
  width: 0px;
  background: transparent;
  /* make scrollbar transparent */
}

.slider {
  display: flex;
  aspect-ratio: 16 / 9;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-behavior: smooth;
  border-radius: 10px;
}

.slider img {
  /* flex-grow flex-shrink flex-basis */
  flex: 1 0 100%;
  scroll-snap-align: start;
  object-fit: cover;
}

.slider-nav {
  display: flex;
  column-gap: 1rem;
  position: absolute;
  bottom: 1.25rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1;
}

.slider-nav a {
  width: 0.5rem;
  height: 0.5rem;
  border-radius: 50%;
  background-color: #fff;
  opacity: 0.75;
  transition: opacity ease 250ms;
}

.slider-nav a:hover {
  opacity: 1;
}
</style>
