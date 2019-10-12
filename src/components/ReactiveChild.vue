<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ msger }}</h1>
  </div>
</template>

<script>
import { reactive } from '@vue/composition-api'
export default {
  props: {
    msg: String
  },
  setup (props, context) {
    const state = reactive({
      msger: props.msg,

    });
    state.msger += ' / child component';
    console.log(props.msg);
    console.log(context.slots, context.parent);
    return state;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
