<template>
  <button @click="increment">increment</button>
  <div>
    <p> state.name: {{ state.name }}</p>
    <p> state.count: {{ state.count }}</p>
  </div>

  <div>
    <p> count: {{ count }}</p>
  </div>

  <div>
    <p> countPlusOne: {{ countPlusOne }}</p>
  </div>

  <div>
    <p> countCopy: {{ countCopy }}</p>
  </div>

</template>

<script>
import { reactive, ref, computed, readonly, watchEffect, watch } from 'vue'

export default {
  setup() {

    // reactive
    // object を リアクティブにする
    const state = reactive({
      name: 0,
      count: 0
    })

    // ref
    // プリミティブな値をリアクティブに
    const count = ref(0)
    console.log(count.value) // .value で値にアクセス可能

    // computed
    // 今まで computed の動き getとset も使える
    const countPlusOne = computed(() => count.value + 1)

    // readonly
    // 読み取り専用にする
    const countCopy = readonly(count)

    // watchEffect
    // 変更を検知して実行
    watchEffect(() => console.log('watchEffect: ' + count.value))

    //  watch
    //  v2.x の watch と同じ 監視する値を指定する
    watch(count, () => console.log('watch: ' + count.value))


    const increment = () => {
      count.value++
      // countCopy.value++
    }

    return {
      state,
      count,
      countPlusOne,
      countCopy,
      increment
    }
  }
}
</script>

<style scoped>

</style>