<template>
  <div id="app">
     <article>
       <hr/>first reactive component<hr/>
     </article>
     <ReactiveChild msg="reactive component"/>

     <article>
       <hr/> second ref component<hr/>
     </article>
     <RefChild msg="ref component"/>

      <article>
          <hr/> third computed&&watch component<hr/>
      </article>
      <ThirdChild msg="third computed&&watch component"/>
  </div>
</template>

<script>
import ReactiveChild from './components/ReactiveChild.vue'
import RefChild from "./components/RefChild";
import ThirdChild from "./components/ThirdChild";

export default {
  name: 'app',
  components: {
    RefChild,
    ReactiveChild,
	ThirdChild
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
