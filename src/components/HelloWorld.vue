<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
  <fragment/>
  <teleport-test/>
  <css-style/>
  <setup-test
      title="タイトル"
  />
  <ReactivityAPITest/>
</template>

<script>
import { onMounted, onUpdated, onUnmounted, onRenderTracked, onRenderTriggered } from 'vue'
import Fragment from "./Fragment.vue";
import TeleportTest from "./TeleportTest.vue";
import CssStyle from "./CssStyle.vue";
import SetupTest from "./SetupTest.vue";
import ReactivityAPITest from "./ReactivityAPITest.vue";
export default {
  name: 'HelloWorld',
  components: {
    Fragment,
    TeleportTest,
    CssStyle,
    SetupTest,
    ReactivityAPITest
  },
  setup() {
    onMounted(() => {
      console.log('mounted')
    })

    onUpdated(() => {
      console.log('onUpdated')
    })

    onUnmounted(() => {
      console.log('onUnmounted')
    })

    // デバック用のフック
    onRenderTracked(() => {
      console.log('onRenderTracked')
    })
    onRenderTriggered(() => {
      console.log('onRenderTriggered')
    })
  },
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  }
}
</script>
