<template>
    <div class="register-box">
      <div class="form-box">
        <p>新規登録</p>
        <form @submit.prevent="register">
          <div class="text-form">
            <input type="text" style="width:350px; height:40px; border-radius:5px; border-width : 1px; " v-model="name" placeholder="ユーザーネーム" required />
          </div>
          <div class="email-form">
            <input type="email" style="width:350px; height:40px; border-radius:5px; border-width : 1px;" v-model="email" placeholder="メールアドレス" required />
          </div>
          <div class="password-form">
            <input type="password" style="width:350px; height:40px; border-radius:5px; border-width : 1px;" v-model="password" placeholder="パスワード" required />
          </div>
          <button type="submit">新規登録</button>
        </form>
      </div>
  </div>
</template>

<script>
export default {
  auth: false,
  data() {
    return {
      name: null,
      email: null,
      password: null,
    };
  },
  methods: {
    async register() {
      try {
        await this.$axios.post("http://localhost:8000/api/auth/register", {
          name: this.name,
          email: this.email,
          password: this.password,
        });
        this.$router.push("/login");
      } catch {
        alert("メールアドレスがすでに登録されています");
      }
    },
  },
};
</script>

<style>
.register-box {
  width: 100%;
  position: relative;
}
.form-box {
  width: 500px;
  background-color: white;
  text-align : center ;
  inset: 0;
  margin: 100px auto; 
  padding: 20px;
  border-radius: 5px;
}
p {
  text-align : center ; 
}
.text-form {
  padding: 10px 0;
}
.email-form {
  padding: 10px 0;
}
.password-form {
  padding: 10px 0 15px 0;
}
button {
  background-color: rgb(91, 32, 168);
  color: white;
  border-radius: 15px;
  border: 1px;
  padding: 5px 25px;
}
</style>