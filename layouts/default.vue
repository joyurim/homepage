<template>
  <main class="flex flex-start h-screen">
    <Sidebar class="flex-none" />
    <div class="flex-1 h-full overflow-y-auto">
      <Nuxt class="h-full" />
    </div>
  </main>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style lang="scss" scoped>
main {
  background: $blue-6;
  section {
    height: 100%;
    padding: 40px 20px;
  }
}
</style>
