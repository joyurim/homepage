<template>
  <div class="dialog">
    <div class="dialog__header">
      {{ title }}
    </div>
    <div
      class="dialog__contents"
      style="white-space: pre-line;"
      v-text="text"
    ></div>
    <div class="dialog__footer">
      <button
        v-for="(button, index) in buttons"
        :key="`button-${index}`"
        class="btn"
        :class="[button.class]"
        @click="handleClick(button)"
      >
        {{ button.title }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dialog',
  props: {
    title: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    buttons: {
      type: Array,
      required: false,
      default() {
        return [];
      }
    }
  },
  data() {
    return {};
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
    handleClick(button) {
      button.handler();
      this.$emit('close');
    },
    brToNewLine(value) {
      return value.split('<br />').join('\n');
    }
  }
};
</script>

<style lang="scss">
.vm--modal {
  border-radius: 6px;
  .dialog {
    @apply flex flex-col h-full;
    font-size: 14px;

    &__header {
      padding: 10px 20px;
      color: $gray-80;
      font-weight: 700;
      font-size: 18px;
      border-bottom: 1px solid $gray-20;
    }

    &__contents {
      padding: 20px;
    }

    &__footer {
      padding: 5px 20px 10px;
      text-align: center;
    }
  }
}
</style>
