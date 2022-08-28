<template>
  <div id="app"><New /><Todos /><Status /></div>
</template>

<script>
import Status from "./components/Status";
import Todos from "./components/Todos";
import New from "./components/New";

export default {
  name: "App",
  components: {
    New,
    Todos,
    Status,
  },
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
