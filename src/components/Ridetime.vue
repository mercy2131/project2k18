<template>
  <el-dialog :visible.sync="timerVisible" style="text-align: center;">
    <h1>Confirmation !</h1>
    <span>Your ride is on the way, estimated ETA is</span>
    <h3>05: 00 minutes</h3>
  </el-dialog>
</template>

<script>

export default {
  name: 'RideTimer',
  data() {
    return {
      timerVisible : true
    }
  }
}
</script>

<style lang="scss" scoped>
h2 {
  font-family: 'Amaranth', sans-serif;
}
</style>

