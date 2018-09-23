<template>
  <div id="about">
    <h1 align="center">Something about us...</h1>
      <el-col :span="8" style="padding-left: 1.5vw; margin-top: 5vh;">
        <el-card :body-style="{ padding: '0px' }">
        <img src="https://d1goeicueq33a8.cloudfront.net/chameleon-assets/v1.0.0/9ed473d1-4aa2-4d2d-a024-bef50204c2b4/desk.png" class="image">
        <div style="padding: 14px;">
          <h3>Safe rides, safer cities</h3>
          <span>Whether you’re in the back seat or behind the wheel, your safety is essential. We are committed to doing our part, and technology is at the heart of our approach. We partner with safety advocates and develop new technologies and systems to help create a world where it’s safe and easy for everyone to get around.</span>
          <div class="bottom clearfix">
          </div>
        </div>
      </el-card>
    </el-col>
    <el-col :span="8" style="margin-top: 5vh;" id="estimate">
      <el-card :body-style="{ padding: '0px' }">
        <img src="https://d1goeicueq33a8.cloudfront.net/chameleon-assets/v1.0.0/98309784-19e3-41e1-b8db-6ec9d0ab1157/desk.jpg" class="image" width="95%">
        <div style="padding: 14px;">
          <h3>Rides and beyond</h3>
          <span>In addition to helping you get from point A to point B, we're working to bring the future closer with self-driving technology and urban air transport, helping people order food quickly and affordably, removing barriers to healthcare, creating new freight-booking solutions, and helping companies provide a seamless employee travel experience.</span>
          <div class="bottom clearfix">
          </div>
        </div>
      </el-card>
    </el-col>
    <el-col :span="8" style="margin-top: 5vh;" id="estimate">
      <el-card :body-style="{ padding: '0px' }">
        <img src="https://d1goeicueq33a8.cloudfront.net/chameleon-assets/v1.0.0/370bc9db-57b0-4284-bff7-d7eb378753a7/desk.jpg" class="image" width="95%">
        <div style="padding: 14px;">
          <h3>Access to rides, on demand</h3>
          <span>Giving riders—and drivers—the power to get where they want to go
From clear navigation options to cashless payments, the app is designed to help people get to their destinations.Whether it’s employee travel or customer rides, Uber for Business gives you an easy way to manage your transportation needs. Built for work, it offers a clear view into employee trip activity</span>
          <div class="bottom clearfix">
          </div>
        </div>
      </el-card>
    </el-col>
  </div>
</template>

<script>
export default {
  name: 'Fare'
}
</script>

<style lang="scss" scoped>
#fare {
  margin-top: 5vh;
}
</style>
