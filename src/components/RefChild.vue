<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ msger }}</h1>
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'
export default {
  props: {
    msg: String
  },
  setup (props, context) {
    const msger = ref(props.msg);
    msger.value += ' / child component';
    return {msger};
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
