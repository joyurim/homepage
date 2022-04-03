<template>
  <section aside aria-label="Popup">
    <div class="flex mb-5 text-xl font-bold">Basic</div>
    <!----------------- Alert ------------------>
    <div class="flex mb-2 text-l font-bold">alert</div>

    <button type="button" class="btn__primary mb-3" @click="openAlert">
      Alert Popup
    </button>

    <!----------------- Confirm ------------------>
    <div class="flex mb-2 text-l font-bold">confirm</div>

    <button type="button" class="btn__primary mb-3" @click="openConfirm">
      Confirm Popup
    </button>

    <!----------------- Modal ------------------>
    <div class="flex mb-2 text-l font-bold">modal</div>
    <button type="button" class="btn__primary mb-12" @click="openModalPopup">
      Modal Popup
    </button>

    <!-- 모달 팝업 -->
    <modal-popup
      v-if="popup.show.modal"
      :visible.sync="popup.show.modal"
      @closed="closedPopup"
    />
  </section>
</template>

<script>
import ModalPopup from '@/components/ModalPopupExample'

export default {
  name: 'UtilPopup',
  components: {
    ModalPopup,
  },
  data() {
    return {
      popup: {
        show: {
          modal: false,
        },
      },
    }
  },
  methods: {
    openModalPopup() {
      this.popup.show.modal = true
    },
    // 팝업 종료
    closedPopup() {
      this.popup.show.modals = false
    },
    openAlert() {
      this.$alert('alert popup')
    },
    openConfirm() {
      this.$confirm('confirm popup')
    },
  },
}
</script>

<style lang="scss" scoped></style>
