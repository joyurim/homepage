<template>
  <section aside aria-label="color">
    <div class="flex-col mb-5">
      <!-- Color chart -->
      <div class="mb-10 primary">
        <h2 class="mb-5 text-xl font-bold">Main</h2>
        <ul class="flex form color">
          <li v-for="pri in primaryList" :key="`name-${pri.num}`">
            <p class="color__info">
              {{ pri.variable }}
              <span class="color__num">{{ pri.num }}</span>
            </p>
          </li>
        </ul>
      </div>
      <div class="mb-10 secondary">
        <h2 class="mb-5 text-xl font-bold">Point</h2>
        <ul class="flex form color">
          <li v-for="point in pointList" :key="`name-${point.num}`">
            <p class="color__info">
              {{ point.variable }}
              <span class="color__num">{{ point.num }}</span>
            </p>
          </li>
        </ul>
      </div>
      <!-- Other -->
      <div class="mb-10 gray">
        <h2 class="mb-5 text-xl font-bold">Gray scale</h2>
        <ul class="flex justify-start form color">
          <li v-for="gray in grayList" :key="`name-${gray.num}`">
            <p class="color__info">
              {{ gray.variable }}
              <span class="color__num">{{ gray.num }}</span>
            </p>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseColor',
  data() {
    return {
      primaryList: [
        { variable: '$primary90', num: '#484d5b' },
        { variable: '$primary80', num: '#828692' },
        { variable: '$primary70', num: '#577bd6' },
        { variable: '$primary60', num: '#618bf3' },
        { variable: '$primary20', num: '#ecf0fc' },
      ],
      pointList: [
        { variable: '$error', num: '#f04d1b' },
        { variable: '$validation', num: '#ff5469' },
        { variable: '$white', num: '#ffffff' },
      ],
      grayList: [
        { variable: '$gray-80', num: '#111111' },
        { variable: '$gray-70', num: '#333333' },
        { variable: '$gray-60', num: '#555555' },
        { variable: '$gray-50', num: '#888888' },
        { variable: '$gray-40', num: '#b9b9b9' },
        { variable: '$gray-30', num: '#bcc2d2' },
        { variable: '$gray-20', num: '#dddddd' },
        { variable: '$gray-10', num: '#d4d4d4' },
        { variable: '$gray-5', num: '#f3f3f3' },
        { variable: '$gray-3', num: '#d5d7dc' },
        { variable: '$gray-2', num: '#f2f2f2' },
        { variable: '$gray-1', num: '#f8f8f8' },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.primary {
  .color {
    li {
      &:first-child {
        background: $primary90;
      }
      &:nth-child(2) {
        background: $primary80;
      }
      &:nth-child(3) {
        background: $primary70;
      }
      &:nth-child(4) {
        background: $primary60;
      }
      &:nth-child(5) {
        background: $primary20;
      }
    }
  }
}
.secondary {
  .color {
    li {
      &:first-child {
        background: $error;
      }
      &:nth-child(2) {
        background: $validation;
      }
    }
  }
}
.gray {
  .color {
    > li {
      &:first-child {
        background: $gray-70;
      }
      &:nth-child(2) {
        background: $gray-60;
      }
      &:nth-child(3) {
        background: $gray-50;
      }
      &:nth-child(4) {
        background: $gray-40;
      }
      &:nth-child(5) {
        background: $gray-30;
      }
      &:nth-child(6) {
        background: $gray-20;
      }
      &:nth-child(7) {
        background: $gray-10;
      }
      &:nth-child(8) {
        background: $gray-5;
      }
      &:nth-child(9) {
        background: $gray-3;
      }
      &:nth-child(10) {
        background: $gray-2;
      }
      &:nth-child(11) {
        background: $white;
      }
    }
  }
}

.color {
  li {
    @apply flex flex-col items-center justify-end;
    width: 120px;
    height: 150px;
    margin-right: 10px;
    font-size: 12px;
    border-radius: 6px;
    &:last-child {
      margin-right: 0;
    }
  }

  &__info {
    @apply flex flex-col;
    width: 100%;
    height: 60px;
    background-color: $white;
    font-weight: 700;
    font-size: 14px;
    border: 1px solid $gray-20;
    border-radius: 0 0 5px 5px;
    padding: 15px;

    .color__num {
      margin-top: 3px;
      font-weight: 500;
      font-size: 12px;
    }
  }
}
</style>
