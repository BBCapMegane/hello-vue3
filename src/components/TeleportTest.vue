<template>
  <div id='teleport-target'></div>
  <p>テレポート</p>
  <teleport to="#teleport-target">
    <p>テレポートされたやつ</p>
  </teleport>
</template>

<script>

export default {
  name: "TeleportTest",
}
</script>

<style scoped>

</style>