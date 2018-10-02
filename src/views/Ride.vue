<template>
  <div id="ride">
    <div style="text-align: center;">
      <h1 style="padding-top: 5vh;">Book your ride</h1>
    </div>
    <Map v-on:updateRoute="getRoute"/>
    <el-carousel arrow="never" type="card" height="200px" :autoplay="false">
      <el-carousel-item>
        <img src="@/assets/auto-rishaw.png" />
        <span>Auto</span>
        <el-button type="primary" round @click.native="bookride('auto')">Book</el-button>
      </el-carousel-item>
      <el-carousel-item>
        <img src="@/assets/frontal-taxi-cab.png" />
        <span>Eco</span>
        <el-button type="primary" round @click.native="bookride('eco')">Book</el-button>
      </el-carousel-item>
      <el-carousel-item>
        <img src="@/assets/limousine-side-view.png" />
        <span>Luxury</span>
        <el-button type="primary" round @click.native="bookride('luxury')">Book</el-button>
      </el-carousel-item>
    </el-carousel>
    <Ridetimer ref="timer"/>
  </div>
</template>
<script>
import axios from 'axios';
import Map from '@/components/Map.vue';
import Ridetimer from '@/components/Ridetime.vue';

export default{
  name: 'Ride',
  props: ['user'],
  data() {
    return {
      route: {
        userId: '',
        type: '',
        source: '',
        destination: '',
        distance: ''
      }
    }
  },
  components: {
    Map,
    Ridetimer,
  },
  methods: {
    bookride(type) {
      if(this.user === null){
        return alert('User must be logged in');
      }
      if(this.source === '' || this.destination === '' || this.distance === '') {
        return alert('Enter a destination');
      }
      this.route.userId = this.user._id;
      this.route.type = type;
      axios.post('http://localhost:3000/book', this.route)
      .then(response => {
        if (response.data.success) {
          this.$refs.timer.timerVisible= !this.$refs.timer.timerVisible;
        }
      })
      .catch(err => {

      })
    },
    getRoute(newroute) {
      this.route.source = newroute.source;
      this.route.destination = newroute.destination;
      this.route.distance = newroute.distance;
    }
  }
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
  margin-top: 15vh;
  font-family: 'Amaranth', sans-serif;
  font-size: 1.3rem;
}
.el-carousel__item:nth-child(2n) {
  background-color: #d3d3d3;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3d3d3;
}

.el-button {
  position: absolute;
  bottom: 0;
  left: 44%;
}
</style>

