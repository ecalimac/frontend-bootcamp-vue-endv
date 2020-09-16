<template>
  <div id="app">
    <div class="header">
      <Header />
    </div>
    <div style="display: none">
      <Home />
    </div>
    <div class="container">
      <Menu />
    </div>
  </div>
</template>

<script>
import Home from "./components/Home";
import Header from "./components/Header";
import Menu from "./components/Menu";

export default {
  name: "App",
  components: {
    Home,
    Header,
    Menu
  }
};
</script>

<style>
body,
html {
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}
* {
  font-family: "Nunito", sans-serif;
}
#app {
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.header {
  flex: 0 0 60px;
}
.container {
  display: flex;
  flex: 1 1 100%;
  width: 100%;
  overflow-y: auto;
  margin-top: 3%;
}
.item {
  font-weight: bold;
  text-align: center;
}
</style>
