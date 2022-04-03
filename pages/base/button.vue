<template>
  <section aside aria-label="button">
    <div class="flex mb-10">
      <!-- Primary -->
      <div class="flex flex-col w-1/4">
        <h2 class="mb-5 font-bold text-xl">btn__primary</h2>
        <div class="flex flex-col">
          <div class="flex items-center mb-3">
            <button class="btn__primary">등록</button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__primary--lg">Large</button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__primary">
              <span class="mr-2 el-icon-user" />
              Icon
            </button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__primary btn--hover">Hover State</button>
          </div>
          <div class="flex items-center">
            <button class="btn__primary" disabled>Disabled State</button>
          </div>
        </div>
      </div>

      <!-- secondary -->
      <div class="flex flex-col w-1/4">
        <h2 class="mb-5 font-bold text-xl">btn__secondary</h2>
        <div class="flex flex-col">
          <div class="flex items-center mb-3">
            <button class="btn__secondary">삭제</button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__secondary--lg">Large</button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__secondary">
              <span class="mr-2 el-icon-user" />
              Icon
            </button>
          </div>
          <div class="flex items-center mb-3">
            <button class="btn__secondary btn--hover">Hover State</button>
          </div>
          <div class="flex items-center">
            <button class="btn__secondary" disabled>Disabled State</button>
          </div>
        </div>
      </div>

      <!-- Primary Line -->
      <div class="flex w-1/4">
        <div class="flex flex-col">
          <h2 class="mb-5 font-bold text-xl">btn__primary-line</h2>
          <div class="flex flex-col">
            <div class="flex items-center mb-3">
              <button class="btn__primary-line">Normal</button>
            </div>
            <div class="flex items-center mb-3">
              <button class="btn__primary-line--lg">Large</button>
            </div>
            <div class="flex items-center mb-3">
              <button class="btn__primary-line">
                <span class="mr-2 el-icon-user" />
                Icon
              </button>
            </div>
            <div class="flex items-center mb-3">
              <button type="button" class="btn__primary-line btn--hover">
                Hover State
              </button>
            </div>
            <div class="flex items-center">
              <button class="btn__primary-line" disabled>Disabled State</button>
            </div>
          </div>
        </div>
      </div>

      <!-- secondary Line -->
      <div class="flex w-1/4">
        <div class="flex flex-col">
          <h2 class="mb-5 font-bold text-xl">btn__secondary-line</h2>
          <div class="flex flex-col">
            <div class="flex items-center mb-3">
              <button class="btn__secondary-line">Normal</button>
            </div>
            <div class="flex items-center mb-3">
              <button class="btn__secondary-line--lg">Large</button>
            </div>
            <div class="flex items-center mb-3">
              <button class="btn__secondary-line">
                <span class="mr-2 el-icon-user" />
                Icon
              </button>
            </div>
            <div class="flex items-center mb-3">
              <button type="button" class="btn__secondary-line btn--hover">
                Hover State
              </button>
            </div>
            <div class="flex items-center">
              <button class="btn__secondary-line" disabled>
                Disabled State
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseButton',
}
</script>

<style lang="scss" scoped>
.btn--hover {
  box-shadow: 2px 4px 7px 0 rgba(0, 0, 0, 0.2);
}
</style>
