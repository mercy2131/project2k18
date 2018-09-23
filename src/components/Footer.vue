<template>
  <div class="footer">
    <el-row style="padding: 20px;">
      <h1>Hotcabs</h1>
      <h4>Premier cab service at your doorstep</h4>
      <hr>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="12">
        <div>
          <h4>Contact us:</h4>
          <span>support@hotcabs.com</span><br>
          <span>+91 1234 567 890</span>
        </div>
      </el-col>
      <el-col :span="12">
        <div>
          <h4>Social media</h4>
          <span>Facebook</span><br>
          <span>Twitter</span><br>
          <span>Instagram</span>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default{
  
}
</script>


<style lang="scss" scoped>
.footer {
  background: black;
  color: white;
  font-family: 'Amaranth', sans-serif;
  padding-bottom: 5vh;
  text-align: center;
}
</style>
