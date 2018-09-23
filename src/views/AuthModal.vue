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
    <el-button type="primary" @click="loginUser">Login</el-button>
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
    <el-button type="primary" @click="signupUser">Sign up</el-button>
  </span>
</el-dialog>  
</template>

<script>
import axios from 'axios';

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
  methods: {
    loginUser: function() {
      axios.post('http://localhost:3000/users/login', this.login)
      .then(response => {
        if (response.data.success) {
          this.$emit('loggedIn',response.data.data);
          this.dialogFormVisible = false;
          this.$router.replace('/');
        }else{
          alert(response.data.message);
        }
      })
      .catch(err => {
        console.error(err);
      })
    },
    signupUser: function() {
      axios.post('http://localhost:3000/users/signup', this.signup)
      .then(response => {
        if (response.data.success) {
          this.$emit('loggedIn',response.data.data);
          this.dialogFormVisible = false;
          this.$router.replace('/');
        }else{
          alert(response.data.message);
        }
      })
      .catch(err => {
        console.error(err);
      })
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
