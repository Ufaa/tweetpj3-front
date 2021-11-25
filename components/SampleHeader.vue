<template>
  <div class="header2">
      <li class="logo">
        <a href="/">
        <img src="/img/logo.png">
        </a>
      </li>
      <li class="link1">      
        <NuxtLink to="/register">新規登録</NuxtLink>
        <NuxtLink to="/login">ログイン</NuxtLink>
      </li>
  <header>
    <h1 class="title">{{ $route.name }}</h1>
    <nav class="nav">
      <ul class="menu-group">
        <li class="menu-item" v-if="!$auth.loggedIn">
          <NuxtLink to="/register">Register</NuxtLink>
        </li>
        <li class="menu-item" v-if="!$auth.loggedIn">
          <NuxtLink to="/login">Login</NuxtLink>
        </li>
        <li class="menu-item" v-else>
          <a @click="logout">Logout</a>
        </li>
      </ul>
    </nav>
  </header>
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
    },
  },
};
</script>


<style>
body {
  background-color: rgb(1, 18, 26);
}
.header2 {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: space-between;
}
.header2 li {
  padding: 5px;
  text-decoration: none;
}
.header2 img {
  width: 100px;
}
a {
  color: white;
  text-decoration: none;
}

header {
  display: flex;
  height: 100px;
  padding: 0 50px;
  /*margin-bottom: 30px;*/
  background-color: darkgrey;
  align-items: center;
}
.title {
  margin-right: auto;
}
.menu-item {
  list-style: none;
  display: inline-block;
  padding: 10px;
}
.menu-item a {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

</style>