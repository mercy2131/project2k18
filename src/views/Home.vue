<template>
  <div class="home">
    <Navbar v-on:toggleLogin="toggle" />
    <el-main>
      <Carousel />
      <Ride />
      <Fare />
      <AuthModal :type="type"  ref="login" />
    </el-main>
    <el-footer>
      <Footer />
    </el-footer>
  </div>
</template>

<script>

import Navbar from '@/components/Navbar.vue';
import Carousel from '@/components/Carousel.vue';
import Footer from '@/components/Footer.vue';
import AuthModal from '@/views/AuthModal.vue';

import Ride from './Ride.vue';
import Fare from './Fare.vue';

export default {
  name: 'Home',
  components: {
    Navbar,
    Carousel,
    Ride,
    Fare,
    Footer,
    AuthModal,
  },
  data() {
    return{
      type: null
    }
  },
  methods: {
    toggle (val) {
      this.type = val;
      this.$refs.login.dialogFormVisible = !this.$refs.login.dialogFormVisible;
    }
  }
}
</script>
