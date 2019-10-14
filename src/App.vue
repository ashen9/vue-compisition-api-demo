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
          <hr/> third computed component<hr/>
      </article>
      <ThirdComputeChild msg="third computed component"/>

      <article>
          <hr/> fourth watch component<hr/>
      </article>
      <FourthWatchChild msg="fourth watch component"/>
  </div>
</template>

<script>
import ReactiveChild from './components/ReactiveChild.vue'
import RefChild from "./components/RefChild";
import ThirdComputeChild from "./components/ThirdComputeChild";
import FourthWatchChild from "./components/FourthWatchChild";

export default {
  name: 'app',
  components: {
    RefChild,
    ReactiveChild,
	ThirdComputeChild,
	FourthWatchChild
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
