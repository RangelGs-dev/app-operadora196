<template>
  <div id="app">
    <HeaderMenuComponent />
    <CarouselComponent />
  </div>
</template>

<script>
import CarouselComponent from "./components/CarouselComponent.vue";
import HeaderMenuComponent from "./components/HeaderMenuComponent.vue";

export default {
  name: "App",
  components: {
    HeaderMenuComponent,
    CarouselComponent,
  },
};
</script>

<style>
body {
  margin: 0px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 800px;
  margin: 0 auto;
}
</style>
