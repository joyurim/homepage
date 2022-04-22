<template>
  <section class="container" aside aria-label="기본정보">
    <div class="section-wrapper">
      <div class="section-container">
        <section class="section">1</section>
        <section class="section">2</section>
        <section class="section">3</section>
      </div>
      <div class="pagination-wrapper">
        <div
          class="pagination"
          :class="{ active: pageIndex === index }"
          @click="moveEvent(index)"
          v-for="(n, index) in page"
          :key="'pagination' + index"
        ></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FullPage',
  layout() {
    return 'blink'
  },
  data() {
    return {
      page: null,
      pageIndex: 0,
      initialX: null,
      initialY: null,
      nowMoving: false,
    }
  },
  mounted() {
    this.page = this.$el.querySelectorAll('.section')
    this.catchAction()
  },
  methods: {
    catchAction() {
      window.addEventListener('wheel', this.wheelEvent)
      window.addEventListener('touchstart', this.touchEventInit)
      window.addEventListener('touchmove', this.touchEvent)
      window.addEventListener('mousedown', (e) => {
        this.touchEventInit(e)
        window.addEventListener('mousemove', this.touchEvent)
      })
      window.addEventListener('mouseup', () => {
        window.removeEventListener('mousemove', this.touchEvent)
      })
    },
    wheelEvent(e) {
      // 마우스 휠 이벤트
      if (this.nowMoving) return
      this.nowMoving = true

      // e.deltaY > 0 ---> 스크롤 내릴 때 true 올릴 때 false
      const scrollDown = e.deltaY > 0
      this.getPageIndex(scrollDown)
    },
    touchEventInit(e) {
      // 터치 시작 위치
      this.initialX = `${e.touches ? e.touches[0].clientX : e.clientX}`
      this.initialY = `${e.touches ? e.touches[0].clientY : e.clientY}`
    },
    touchEvent(e) {
      // 터치, 마우스 드래그 이벤트
      if (this.nowMoving) return
      this.nowMoving = true
      const currentX = `${e.touches ? e.touches[0].clientX : e.clientX}`
      const currentY = `${e.touches ? e.touches[0].clientY : e.clientY}`
      const diffX = this.initialX - currentX
      const diffY = this.initialY - currentY
      let touchDown = null
      if (Math.abs(diffX) < Math.abs(diffY)) {
        touchDown = diffY > 0
      }
      this.getPageIndex(touchDown)
    },
    getPageIndex(down) {
      // 현재 페이지 인덱스 구하기
      if (down) {
        this.pageIndex === this.page.length - 1
          ? (this.pageIndex = this.page.length - 1)
          : ++this.pageIndex
      } else {
        this.pageIndex <= 0 ? (this.pageIndex = 0) : --this.pageIndex
      }
      this.moveEvent(this.pageIndex)
    },
    moveEvent(number) {
      // 페이지 움직이는 이벤트
      this.pageIndex = number
      this.$el.querySelector(
        '.section-container'
      ).style.transform = `translateY(-${number}00%)`
      setTimeout(() => {
        // .section-wrapper의 transition 시간만큼은 중복되지 않게
        this.nowMoving = false
      }, 400)
    },
  },
  watch: {
    pageIndex(idx) {
      console.log(idx)
    },
  },
  destroyed() {
    window.removeEventListener('wheel', this.wheelEvent)
    window.removeEventListener('touchstart', this.touchEventInit)
    window.removeEventListener('touchmove', this.touchEvent)
    window.removeEventListener('mousedown', this.touchEventInit)
    window.removeEventListener('mousemove', this.touchEvent)
  },
}
</script>

<style lang="scss" scoped>
.container {
  overflow: hidden;
  max-width: 100%;
  * {
    transition: all 0.1s;
  }
  .section-wrapper {
    width: 100%;
    height: 100vh;
    .section-container {
      width: 100%;
      height: 100%;
      transition: all 0.5s;
      .section {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 33px;
        font-weight: bold;
        position: relative;
        color: $gray-70;
        background-color: $gray-5;
      }
    }
    .pagination-wrapper {
      position: fixed;
      right: 30px;
      top: 50%;
      transform: translateY(-50%);
      .pagination {
        width: 14px;
        height: 14px;
        border: 1px solid $blue-2;
        border-radius: 50%;
        & + .pagination {
          margin-top: 20px;
        }
        &.active {
          background-color: $primary60;
        }
      }
    }
  }
}
.profile {
}
</style>
