<template>
  <div class="hello">
    <h1>count:{{state.count}}, name: {{state.name}}</h1>
    <h1>count:{{count}}, name: {{name}}</h1>
  </div>
</template>

<script>
import { ref, reactive, watch, toRefs, onMounted, onUpdated, onUnmounted} from '@vue/composition-api'
export default {
  setup (props, context) {
    const state = reactive({count: 0, name: 'ashen'});
    watch(
            [() => state.count, () => state.name],
            ([count, name], [prevCount, prevName]) => {
              console.log(count); // 新的 count 值
              console.log(name); // 新的 name 值
              console.log('------------');
              console.log(prevCount); // 旧的 count 值
              console.log(prevName); // 新的 name 值
            },{
              lazy: true // 在 watch 被创建的时候，不执行回调函数中的代码
            }
    );

    const count = ref(0);
    const name = ref('1');
    watch(
            [count, name],
            ([count, name], [prevCount, prevName]) => {
              console.log(count); // 新的 count 值
              console.log(name); // 新的 name 值
              console.log('------------');
              console.log(prevCount); // 旧的 count 值
              console.log(prevName); // 新的 name 值
            },{
              lazy: true // 在 watch 被创建的时候，不执行回调函数中的代码
            }
    );

    setTimeout(() => {
      state.count++;
      state.name = 'ls';
      count.value++;
      name.value = '一个相信你的人';
    }, 1000);

    onMounted(() => {
      console.log('mounted!')
    });
    onUpdated(() => {
      console.log('updated!')
    });
    onUnmounted(() => {
      console.log('unmounted!')
    });

    return {count, name , state};
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
