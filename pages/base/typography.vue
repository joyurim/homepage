<template>
  <section aside aria-label="typography" class="typography">
    <div class="flex mb-4 form">
      <ul class="typography__name">
        <li v-for="(name, index) in typoName" :key="`name-${index}`">
          {{ name }}
        </li>
      </ul>
      <ul class="typography__semantic">
        <li
          v-for="(semantic, index) in typoSemantic"
          :key="`semantic-${index}`"
        >
          {{ semantic }}
        </li>
      </ul>
      <ul class="typography__size">
        <li v-for="(size, index) in typoSize" :key="`font-size-${index}`">
          {{ size }}
        </li>
      </ul>
      <ul class="typography__class">
        <li v-for="(cls, index) in typoClass" :key="`line-height-${index}`">
          {{ cls }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseTypography',
  data() {
    return {
      typoName: [
        'Name',
        'title',
        'subtitle',
        'Body 1',
        'Body 2',
        'Body 3',
        'Body 4',
      ],
      typoSemantic: ['Semantic', 'H1', 'H2', '-', '-', '-', '-'],
      typoSize: ['Font Size', '22px', '16px', '15px', '14px', '13px', '12px'],
      typoClass: ['Class', 'font__title', 'font__subtitle', '-', '-', '-', '-'],
    }
  },
}
</script>

<style lang="scss" scoped>
.typography {
  @apply flex;

  li {
    height: 45px;
    line-height: 45px;

    &:not(:last-child) {
      margin-bottom: 20px;
    }

    &:first-child {
      font-weight: 700;
      font-size: 20px;
    }
  }

  &__name {
    width: 150px;

    li {
      &:nth-child(2) {
        font-size: 22px;
        font-weight: 700;
      }
      &:nth-child(3) {
        font-size: 16px;
        font-weight: 700;
      }
      &:nth-child(4) {
        font-size: 15px;
        font-weight: 700;
      }
      &:nth-child(5) {
        font-size: 14px;
        font-weight: 400;
      }
      &:nth-child(6) {
        font-size: 13px;
        font-weight: 400;
      }
      &:nth-child(7) {
        font-size: 12px;
        font-weight: 400;
      }
    }
  }

  &__semantic {
    width: 150px;

    li {
      &:nth-child(2) {
        font-size: 22px;
        font-weight: 700;
      }
      &:nth-child(3) {
        font-size: 16px;
        font-weight: 700;
      }
      &:nth-child(4) {
        font-size: 15px;
        font-weight: 700;
      }
      &:nth-child(5) {
        font-size: 14px;
        font-weight: 400;
      }
      &:nth-child(6) {
        font-size: 13px;
        font-weight: 400;
      }
      &:nth-child(7) {
        font-size: 12px;
        font-weight: 400;
      }
    }
  }

  &__size {
    width: 150px;

    li {
      &:nth-child(2) {
        font-size: 22px;
        font-weight: 700;
      }
      &:nth-child(3) {
        font-size: 16px;
        font-weight: 700;
      }
      &:nth-child(4) {
        font-size: 15px;
        font-weight: 700;
      }
      &:nth-child(5) {
        font-size: 14px;
        font-weight: 400;
      }
      &:nth-child(6) {
        font-size: 13px;
        font-weight: 400;
      }
      &:nth-child(7) {
        font-size: 12px;
        font-weight: 400;
      }
    }
  }

  &__class {
    width: 170px;

    li {
      &:nth-child(2) {
        font-size: 22px;
        font-weight: 700;
      }
      &:nth-child(3) {
        font-size: 16px;
        font-weight: 700;
      }
      &:nth-child(4) {
        font-size: 15px;
        font-weight: 700;
      }
      &:nth-child(5) {
        font-size: 14px;
        font-weight: 400;
      }
      &:nth-child(6) {
        font-size: 13px;
        font-weight: 400;
      }
      &:nth-child(7) {
        font-size: 12px;
        font-weight: 400;
      }
    }
  }
}
</style>
