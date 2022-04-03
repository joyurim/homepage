<template>
  <popup
    :popup-name="popup.name"
    :title="popup.title"
    :width="popup.width"
    :height="popup.height"
    @confirm="handleClosed"
    @closed="handleClosed"
  >
    테스트 팝업
  </popup>
</template>

<script>
import popup from '@/components/Popup'

export default {
  name: 'ModalPopup',
  components: { popup },
  props: {
    visible: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      popup: {
        name: 'ModalPopup',
        title: '모달 팝업',
        width: '600',
        height: 'auto',
      },
    }
  },
  mounted() {
    this.open()
  },
  methods: {
    // ----------------------------- 팝업 -------------------------------
    open() {
      this.$modal.show(this.popup.name)
    },
    close() {
      this.$modal.hide(this.popup.name)
    },
    handleClosed() {
      this.$emit('closed')
    },
  },
}
</script>

<style lang="scss" scoped></style>
