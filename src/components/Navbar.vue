<template>
  <el-menu
  class="hotcabs-menu"
  mode="horizontal"
  background-color="#000"
  text-color="#fff"
  router
  active-text-color="#fff">
    <el-menu-item index="/" style="font-size: 1.5rem !important;font-weight: 700;">Hotcabs</el-menu-item>
    <el-menu-item index="/#ride" style="margin-left: 1vw;">Ride</el-menu-item>
    <el-menu-item index="/#about">About us</el-menu-item>
    <div id="guestMode" v-if="user === null">
      <el-menu-item index="/" style="float: right;" @click.native="$emit('toggleLogin', false)">Sign up</el-menu-item>
      <el-menu-item index="/" style="float: right;" @click.native="$emit('toggleLogin', true)">Login</el-menu-item>
    </div>
    <div id="loggedIn" v-if="user !== null">
      <el-submenu style="float: right;" index="2">
        <template slot="title">User</template>
        <el-menu-item index="2-1" style="font-size: 14px;">Logout</el-menu-item>
      </el-submenu>
    </div>
  </el-menu>
</template>

<script>

export default {
  name: 'Navbar',
  data () {
    return {
      user: null
    }
  },
}
</script>

<style lang="scss" scoped>
.hotcabs-menu .el-menu-item {
  font-family: 'Amaranth', sans-serif;
  font-size: 1.2rem;
}
</style>
