<template>
  <div id="app">
    <div class="topbar">
      <a
        target="_blank"
        href="https://github.com/RaveloMevaSoavina/Vue-Calculator-self-training"
      >https://github.com/RaveloMevaSoavina/Vue-Calculator-self-training</a>
    </div>
    <br />
    <Calculator />
  </div>
</template>

<script>
import Calculator from "./components/Calculator.vue";

export default {
  name: "App",
  components: {
    Calculator
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.topbar {
  height: 4rem;
  width: 100vw;
  background-color: #2c3e50;
  color: #fff;
  padding: 1.2rem 0;
}

.topbar a {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
</style>
