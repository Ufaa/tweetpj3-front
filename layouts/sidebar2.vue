<template>

  <div class="sidebar-container">
      <li class="logo">
        <a href="/">
        <img src="/img/logo.png">
        </a>
      </li>
      <p>《ログイン情報》</p>
      <p v-if="$auth.loggedIn">ID番号：{{ $auth.user.id }}</p>    
      <p v-if="$auth.loggedIn">ログイン名：{{ $auth.user.name }}</p>
      <p v-if="$auth.loggedIn">メールアドレス：{{ $auth.user.email }}</p>

      <div class="sidebar-container2">
        <div class="home">
          <img src="/img/home.png">
          <NuxtLink to="/">ホーム</NuxtLink>
        </div>
        <div class="logout">
          <img src="/img/logout.png">
          <a @click="logout">ログアウト</a>
        </div>

        <div class="sidebar-container3">
          <h4>あたらしいTweet</h4>
            <form @submit.prevent="tweet">
              <div class="form-group">

                <div class="tweet">
                  <input type="text" name="content" class="form-control" placeholder="" style="width:300px; height:200px; border-radius:10px; border:1px; background-color:none; margin-bottom:5px;">
                </div>
                <button type="submit" class="btn btn-primary">シェアする</button>
              </div>
            </form>
        </div>
      </div>

        <div class="comment">
          <NuxtLink to="/comment">→コメント画面へ</NuxtLink>
        </div>

    <Nuxt />
  </div>

</template>

<script>
export default {
  methods: {
    async logout() {
      try {
        await this.$auth.logout();
        this.$router.push("/login");
      } catch (error) {
        console.log(error);
      }
    }
  },
};
</script>

<style　scoped>
.sidebar-container {
  width: 30%;
}
.container {
  padding: 30px;
}
p {
  color: white;
  text-align: left;
}
.sidebar-area {
  /* 左側に固定 */
  float: left;
}
h4 {
  color: white;
}
table {
  color: white;
}
.sidebar-container img {
  width: 100px;
}
button {
  position: absolute;
}
.home {
  padding-top: 75px;
  padding-bottom: 10px;
}
.home img {
  width: 25px;
}
.logout {
  padding-bottom: 30px;
}
.logout img {
  width: 25px;
}
.comment {
  font-weight: bold;
  padding-top: 75px;
}
</style>

