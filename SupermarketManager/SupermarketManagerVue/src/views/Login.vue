<template>
  <div id="login">
    <div class="loginForm">
      <el-form :model="loginForm" ref="loginForm" class="demo-ruleForm">
        <br />
        <i class="iconfont icon-r-building" style="font-size: 36px">
          <b style="font-size: 28px"> 上源资本基金资讯系统 </b>
        </i><br /><br />
        <el-form-item prop="username">
          <el-row>
            <el-col :span="5" style="text-align: right">
              <i class="iconfont icon-r-user1" style="font-size: 28px; color: grey"></i>
            </el-col>
            <el-col :span="19" style="text-align: left; padding-left: 10px">
              <el-input v-model="loginForm.username" placeholder="请输入用户名" clearable></el-input>
            </el-col>
          </el-row>
        </el-form-item>
        <el-form-item prop="password">
          <el-row>
            <el-col :span="5" style="text-align: right">
              <i class="iconfont icon-r-password" style="font-size: 28px; color: grey"></i>
            </el-col>
            <el-col :span="19" style="text-align: left; padding-left: 10px">
              <el-input v-model="loginForm.password" placeholder="请输入密码" type="password" clearable></el-input>
            </el-col>
          </el-row>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="handleLogin">登录</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginForm: {
        username: '',
        password: ''
      }
    };
  },
  methods: {
    handleLogin() {
      // 这里将会调用 API
      this.$axios.post('/api/login', this.loginForm)
          .then(response => {
            // 登录成功后的处理
          })
          .catch(error => {
            console.error('登录失败', error);
          });
    }
  }
}
</script>
