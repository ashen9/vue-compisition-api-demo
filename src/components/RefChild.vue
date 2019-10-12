<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ msger }}</h1>
    <h1>{{state.msger}}</h1>
    <h1>{{msgerRef}}</h1>
  </div>
</template>

<script>
import { ref, reactive, isRef, toRefs} from '@vue/composition-api'
export default {
  props: {
    msg: String
  },
  setup (props, context) {
    const msger = ref(props.msg);
    console.log(':' + isRef(msger));
    const state = reactive({
	    msger
    });
    const stater = reactive({
        msgerRef: props.msg
    });
    state.msger = ref('new ref');
    msger.value += ' / child component';
    return {msger, state, ...toRefs(stater)};
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
