<template>
  <div id="app">
    <ReactiveChild msg="reactive component"/>
    <RefChild msg="ref component"/>
  </div>
</template>

<script>
import ReactiveChild from './components/ReactiveChild.vue'
import RefChild from "./components/RefChild";

export default {
  name: 'app',
  components: {
    RefChild,
    ReactiveChild
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
