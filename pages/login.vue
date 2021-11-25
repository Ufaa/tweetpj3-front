<template>
  <div class="login-box">
    <div class="form-box">
    <p>ログイン</p>
      <form @submit.prevent="login">
        <div class="email-form">
          <input type="email" style="width:350px; height:40px; border-radius:5px; border-width : 1px;" v-model="email" placeholder="メールアドレス" required />
        </div>
        <div class="password-form">
          <input type="password" style="width:350px; height:40px; border-radius:5px;  border-width : 1px;" v-model="password" placeholder="パスワード" required />
        </div>
        <button type="submit">ログイン</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: null,
      password: null,
    };
  },
  methods: {
    async login() {
      try {
        await this.$auth.loginWith("laravelJWT", {
          data: {
            email: this.email,
            password: this.password,
          },
        });
        this.$router.push("/");
      } catch {
        alert("メールアドレスまたはパスワードが間違っております");
      }
    },
  },
};
</script>

<style>
</style>