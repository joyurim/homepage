<template>
  <main class="flex flex-start h-screen">
    <Sidebar class="flex-none" />
    <div class="flex-1 h-full overflow-y-auto">
      <Nuxt />
    </div>
  </main>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style lang="scss" scoped></style>
