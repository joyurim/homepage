<template>
  <section aside aria-label="초기 index page"></section>
</template>

<script>
export default {
  name: 'IndexPage',
  layout() {
    return 'blink'
  },
  mounted() {
    this.$router.push('/profile')
  },
}
</script>
