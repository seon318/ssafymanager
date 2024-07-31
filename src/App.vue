<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <header>
    <h1>SSAFY MANAGER</h1>
  </header>
  <button class="login-btn" @click="kakaoLogin()">
    <img class="kakao-logo" src="./assets/kakao-talk.png" />카카오톡으로
    시작하기
  </button>
</template>

<script>
export default {
  name: 'App',
  methods: {
    kakaoLogin: function () {
      const REST_API_KEY = import.meta.env.VITE_APP_REST_API_KEY;
      const REDIRECT_URI = encodeURIComponent(
        import.meta.env.VITE_APP_REDIRECT_URI
      );
      const REDIRECT_URL = `https://kauth.kakao.com/oauth/authorize?client_id=${REST_API_KEY}&redirect_uri=${REDIRECT_URI}&response_type=code`;
      console.log('눌렀음');
      window.location.href = REDIRECT_URL;
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
body {
  display: grid;
}
.login-btn {
  width: 200px;
  display: flex;
  border-radius: 10px;
  text-align: center;
  align-items: center;
  background-color: #fee500;
  box-shadow: 0;
  cursor: pointer;
  font-weight: 700;
}

.kakao-logo {
  width: 30px;
  margin: 5px;
}
</style>
