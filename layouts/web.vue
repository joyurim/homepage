<template>
  <main class="h-screen">
    <div class="h-full overflow-y-auto">
      <Nuxt />
    </div>
  </main>
</template>

<script>
export default {
  name: 'WebLayout',
}
</script>

<style lang="scss" scoped>
main {
  background: $blue-6;
  section {
    height: 100%;
    // padding: 40px 20px;
  }
}
</style>
