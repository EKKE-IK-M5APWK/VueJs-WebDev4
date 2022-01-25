<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h2>Adminsztrátor felület</h2>
    <administrator-list></administrator-list>
  </div>
</template>

<script>
import AdministratorList from "./components/AdministratorList.vue";
export default {
  name: "App",
  components: { AdministratorList },
  data() {
    return {};
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
