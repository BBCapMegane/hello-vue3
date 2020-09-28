<template>
  <p class="text">style</p>
</template>

<script>
import { ref } from  'vue'
export default {
  name: "CssStyle",
  setup() {
    const color = ref('red')
    return {
      color
    }
  }
}
</script>

<style scoped vars="{ color }">
.text {
  color: var(--color);
}

</style>