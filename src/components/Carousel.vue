<template>
  <div class="block" style="text-align: center;">
    <el-carousel trigger="click">
      <el-carousel-item>
        <img src="https://gstindiaguide.com/wp-content/uploads/2016/09/Rent-a-Cab-Services.jpg" />
      </el-carousel-item>
      <el-carousel-item>
        <img src="http://newzoogle.com/wp-content/uploads/2017/01/Top-10-Safest-Taxi-Finding-Apps-for-Android.jpg" />
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script lang="ts">

export default {
  name: 'Carousel'
}
</script>

<style lang="scss" scoped>
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }
</style>

