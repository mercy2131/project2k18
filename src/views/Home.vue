<template>
  <div class="home">
    <Navbar :user="user" v-on:toggleLogin="toggle" />
    <el-main>
      <Carousel />
      <Ride :user="user" />
      <Fare />
      <AuthModal :type="type" v-on:loggedIn="passdata" ref="login" />
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
      type: null,
      user: null,
      route: null
    }
  },
  methods: {
    toggle (val) {
      this.type = val;
      this.$refs.login.dialogFormVisible = !this.$refs.login.dialogFormVisible;
    },
    passdata (value) {
      this.user = value;
    }
  }
}
</script>
