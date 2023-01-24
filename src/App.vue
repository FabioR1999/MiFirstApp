<template>
  <div id="app">
    <h1>Hola Mundo</h1>
    <!-- <Home msg=" Hola Fabio !!!!!" /> -->

    <nav>
      <ul>
        <li>
          <router-link to="/home">
            Home
          </router-link>
        </li>
        <li>
          <router-link to="/">
            User
          </router-link>
        </li>
      </ul>
    </nav>
    <hr />
    <router-view></router-view>
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import User from "./components/User.vue";

export default {
  name: "App",
  components: {
    Home,
    User
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
