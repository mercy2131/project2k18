<template>
<div>
  <div id='geocoder' class='geocoder' ref="geocoder"></div>
  <div id="cabmap">
  </div>
</div>
</template>

<script>
import mapboxgl from 'mapbox-gl';

import * as MapboxDirections from  '@/../node_modules/@mapbox/mapbox-gl-directions/dist/mapbox-gl-directions.js';
import '@/../node_modules/@mapbox/mapbox-gl-directions/dist/mapbox-gl-directions.css';
import '@/../node_modules/mapbox-gl/dist/mapbox-gl.css';

export default {
  name: 'Map',
  data() {
    return {
      lat: null,
      long: null,
      map: null,
      directions: null,
      distance: null,
      marker: null,
    }
  },
  mounted() {
    mapboxgl.accessToken = 'pk.eyJ1Ijoic3c0cG4xbCIsImEiOiJjam1kZGsxMWk2MGhyM3FsaWl1MHZvYjR2In0.EtwlHoTqOHGOG41YRkZzkQ';
    this.directions = new MapboxDirections({
      accessToken: mapboxgl.accessToken,
      unit: 'metric',
      profile: 'mapbox/driving',
      controls: {
        instructions: false,
        profileSwitcher: false
      }
    });

    this.directions.on('route', (e) => {
      this.distance = e.route[0].distance;
    });
    this.map = new mapboxgl.Map({
      container: 'cabmap',
      style: 'mapbox://sprites/mapbox/streets-v10',
      zoom: 0,
    });
    this.map.addControl(this.directions, 'top-left');

    this.map.on('load', () => {
      this.directions.setOrigin([this.long, this.lat]);
    });

    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition((position) => {
        this.lat = position.coords.latitude;
        this.long = position.coords.longitude;
        
        this.map.jumpTo({
          center: [this.long, this.lat],
          zoom: 17,
        });
      });
    }
  },
};
</script>

<style lang="scss" scoped>
#cabmap {
  width: 100%;
  height: 400px;
}
.geocoder {
}
.mapboxgl-ctrl-geocoder { min-width:100%; }
</style>
