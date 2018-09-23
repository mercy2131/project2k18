<template>
<el-dialog title="Hotcabs" :visible.sync="dialogFormVisible">
  <el-form :model="login" v-if="type === true">
    <el-form-item label="Username" :label-width="formLabelWidth">
      <el-input v-model="login.name" autocomplete="off"></el-input>
    </el-form-item>
    <el-form-item label="Password" :label-width="formLabelWidth">
      <el-input v-model="login.password" autocomplete="off"></el-input>
    </el-form-item>
  </el-form>
  <span slot="footer" class="dialog-footer" v-if="type === true">
    <el-button type="primary" @click="dialogFormVisible = false">Login</el-button>
  </span>
  <el-form :model="signup" v-if="type === false">
    <el-form-item label="Username" :label-width="formLabelWidth">
      <el-input v-model="signup.name" autocomplete="off"></el-input>
    </el-form-item>
    <el-form-item label="Password" :label-width="formLabelWidth">
      <el-input v-model="signup.password" autocomplete="off"></el-input>
    </el-form-item>
    <el-form-item label="Contact" :label-width="formLabelWidth">
      <el-input v-model="signup.contact" autocomplete="off"></el-input>
    </el-form-item>
    <el-form-item label="Email" :label-width="formLabelWidth">
      <el-input v-model="signup.email" autocomplete="off"></el-input>
    </el-form-item>
  </el-form>
  <span slot="footer" class="dialog-footer" v-if="type === false">
    <el-button type="primary" @click="dialogFormVisible = false">Sign up</el-button>
  </span>
</el-dialog>  
</template>

<script>
export default {
  name: 'AuthModal',
  props: ['type'],
  data () {
    return {
      dialogFormVisible: false,
      login: {
        name: '',
        password: '',
      },
      signup: {
        name: '',
        password: '',
        contact: '',
        email: ''
      },
      formLabelWidth: '120px'
    }
  },
}
</script>

<style lang="scss" scoped>

</style>
