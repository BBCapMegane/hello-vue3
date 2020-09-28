<template>
  <p>{{ title }}</p>
  <p>{{ newTitle }}</p>
  <button @click="increment">increment</button>
  <p> {{ count }}</p>

</template>

<script>
import { ref } from 'vue'
export default {
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup(props) {
    const count = ref(0)

    const increment = () => {
      count.value++
    }

    return {
      count,
      increment,
      newTitle: '新しい' + props.title
    }
  }
}
</script>

<style scoped>

</style>