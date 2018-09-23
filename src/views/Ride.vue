<template>
  <div id="ride">
    <div style="text-align: center;">
      <h1 style="padding-top: 5vh;">Book your ride</h1>
    </div>
    <Map />
    <el-carousel arrow="never" type="card" height="200px" :autoplay="false">
      <el-carousel-item @click.native="bookride">
        <img src="@/assets/auto-rishaw.png" />
        <span>Auto</span>
      </el-carousel-item>
      <el-carousel-item @click.native="bookride">
        <img src="@/assets/frontal-taxi-cab.png" />
        <span>Eco</span>
      </el-carousel-item>
      <el-carousel-item @click.native="bookride">
        <img src="@/assets/limousine-side-view.png" />
        <span>Luxury</span>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script>
import axios from 'axios';

import Map from '@/components/Map.vue';


export default{
  name: 'Ride',
  data () {
    return {

    }
  },
  components: {
    Map,
  },
}
</script>
<style lang="scss" scoped>
#ride {
  padding: 20px;
}

.el-input {
  width: 25%;
  margin-bottom: 10px;
}

.el-carousel {
  z-index: 999;
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
  text-align: center;
}

.el-carousel__item img {
  position: absolute;
  margin-left: 40%;
  width: 120px;
}

.el-carousel__item span {
  position: absolute;
  margin-left: 21.5vw;
  margin-top: 20vh;
  font-family: 'Amaranth', sans-serif;
  font-size: 1.3rem;
}
.el-carousel__item:nth-child(2n) {
  background-color: #d3d3d3;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3d3d3;
}
</style>

