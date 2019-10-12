<template>
  <div class="hello">
    <h1>count:{{count}},  plusOne:{{plusOne}} ,plusTwo:{{ plusTwo }}</h1>
  </div>
</template>

<script>
import { ref, computed} from '@vue/composition-api'
export default {
  setup (props, context) {
    const count = ref(1);
    const plusOne = computed(() => count.value + 1);
    const plusTwo = computed({
       get: () => count.value + 1,
       set: val => {
         count.value = val - 1
       }
    });
    setTimeout(_ => {
      plusTwo.value = 9;
    }, 1000);
    // 触发 set 函数后，count 的值会被更新
    console.log(count.value);
    return {plusTwo, plusOne, count};
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
