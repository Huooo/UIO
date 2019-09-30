<template>
  <div class="uioi-login">
    <div class="form-item">
      <input v-model="loginId" name="account" type="text" placeholder="账号">
    </div>
    <div class="form-item">
      <input v-model="loginPwd" name="password" type="text" placeholder="密码">
    </div>
    <div class="form-item">
      <button @click="submit">submit</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'uioi-login',
  data() {
    return {
      merchantId: '201905293103484',
      loginType: 0,
      loginId: '14000000001',
      loginPwd: 'qwer1234'
    }
  },
  methods: {
    submit() {
      const { merchantId, loginType, loginId, loginPwd } = this;
      const API_HOST = process.env.NODE_ENV !== 'development' ? 'http://192.168.130.27:8080' : '';
      const API_URL = `${API_HOST}/cb-sso-web/login`;

      axios.post(API_URL, {
        merchantId,
        loginId,
        loginType,
        loginPwd
      }).then((res => {
        alert(`${res.data.msg}`);
      }))
    }
  }
}
</script>

<style scoped>
.uioi-login {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: 300px;
  min-height: 300px;
  border: 1px solid #ccc;
}

.form-item {
  margin-bottom: 10px;
}
</style>