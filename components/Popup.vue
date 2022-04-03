<template>
  <modal
    :name="popupName"
    :width="popupWidth"
    :height="popupHeight"
    :draggable="draggable"
    :click-to-close="clickToClose"
    @opened="handleOpened"
    @closed="handleClosed"
  >
    <div class="flex flex-col h-full">
      <!-- header -->
      <div v-if="useHeader" class="popup__header">
        <slot name="header">
          <div class="popup__header__title">
            {{ title }}
          </div>

          <button
            class="icon__popup-close"
            title="팝업닫기"
            @click="handleClosed"
          >
            <span class="hide">
              닫기
            </span>
          </button>
        </slot>
      </div>
      <!-- // header -->

      <!-- contents -->
      <div class="flex-1 popup__contents">
        <slot></slot>
      </div>
      <!-- // contents -->

      <!-- footer -->
      <div v-if="useFooter" class="popup__footer">
        <slot name="footer">
          <button class="mr-2 btn__secondary-line" @click="handleClosed">
            {{ cancelButtonText }}
          </button>
          <button
            v-if="useDeleteButton && useModifyButton"
            class="mr-2 btn__secondary"
            @click="deleted"
          >
            {{ deleteButtonText }}
          </button>

          <button v-if="!useModifyButton" class="btn__primary" @click="confirm">
            {{ confirmButtonText }}
          </button>
          <button v-if="useModifyButton" class="btn__primary" @click="modify">
            변경
          </button>
        </slot>
      </div>
      <!-- // footer-->
    </div>
  </modal>
</template>

<script>
export default {
  name: 'Popup',
  components: {},
  props: {
    popupName: {
      type: [String],
      required: true
    },
    title: {
      type: String,
      required: false,
      default: ''
    },
    clickToClose: {
      type: [Boolean],
      required: false,
      default: false
    },
    draggable: {
      type: [Boolean],
      required: false,
      default: false
    },
    width: {
      type: [String],
      required: false,
      default: '1024'
    },
    height: {
      type: [String],
      required: false,
      default: 'auto'
    },
    useHeader: {
      type: [Boolean],
      required: false,
      default: true
    },
    useFooter: {
      type: [Boolean],
      required: false,
      default: true
    },
    cancelButtonText: {
      type: [String],
      required: false,
      default: '취소'
    },
    deleteButtonText: {
      type: [String],
      required: false,
      default: '삭제'
    },
    confirmButtonText: {
      type: [String],
      required: false,
      default: '확인'
    },
    useDeleteButton: {
      type: [Boolean],
      required: false,
      default: false
    },
    useModifyButton: {
      type: [Boolean],
      required: false,
      default: false
    }
  },
  data() {
    return {};
  },
  computed: {
    popupWidth() {
      return this.width;
    },
    popupHeight() {
      return this.height;
    }
  },
  watch: {},

  methods: {
    confirm() {
      this.$emit('confirm');
    },
    modify() {
      this.$emit('modify');
    },
    deleted() {
      this.$emit('deleted');
    },
    handleClosed() {
      this.$modal.hide(this.popupName);
      this.$emit('handleClosed');
    },
    handleOpened() {
      this.$emit('opened');
    }
  }
};
</script>

<style lang="scss" scoped>
// 팝업
::v-deep {
  .popup {
    @apply flex flex-col h-full;
    .vm--overlay {
      opacity: 0.7;
    }
    &.vm--modal {
      @apply flex flex-col h-full;
      background: $white;
    }
    &__header {
      @apply flex flex-none items-center justify-between;
      padding: 16px 15px 15px 20px;
      border-bottom: 1px solid $gray-20;
      color: $gray-80;
      &__title {
        font-size: 18px;
        font-weight: 700;
        text-align: left;
      }
      .icon {
        &__popup-close {
          min-width: 17px;
          min-height: 17px;
          cursor: pointer;
          background: url('/icon/icon__close.png') no-repeat center / 15px;
        }
      }
    }
    &__contents {
      @apply flex-1 overflow-y-auto;
      padding: 25px 25px 10px;
    }
    &__footer {
      @apply flex-none;
      padding: 10px 15px 25px;
      text-align: center;
    }
  }
}
</style>
