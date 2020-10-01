<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/1.jpg" />
    <iTune />
  </div>
</template>

<script>
import iTune from "@/components/iTune.vue";

export default {
  name: "App",
  components: {
    //HelloWorld,
    iTune,
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
