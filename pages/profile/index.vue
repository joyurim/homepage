<template>
  <section class="container ProfileInfo" aside aria-label="기본정보">
    <div class="section-wrapper">
      <div class="section-container profile">
        <section class="section flex-col">
          <div class="profile__img mb-16">
            <img src="/img/profile/profile__main--img.png" alt="" />
          </div>
          <vue-typer
            class="display-3 profile__info-text"
            :text="[
              '인생은 모두가 함께하는 여행이다.\n 매일매일 우리가 할 수 있는건 최선을 다해 이 멋진 여행을 만끽하는 것이다.',
            ]"
            :repeat="1"
            initial-action="typing"
            :pre-type-delay="100"
            :type-delay="200"
            :pre-erase-delay="1000"
            :erase-delay="250"
            erase-style="backspace"
            :erase-on-complete="false"
            caret-animation="blink"
          ></vue-typer>
        </section>
        <section class="section">
          <div class="flex flex-start mb-20">
            <!-- 사진 -->
            <article class="profile-img">
              <img src="/img/yurim.jpg" alt="조유림" />
              <!-- 연락처 -->
              <ul class="profile__info">
                <li>
                  <p class="info__label">Email</p>
                  <p>
                    <a href="mailto:joyurim1989@naver.com"
                      >joyurim1989@naver.com</a
                    >
                  </p>
                </li>
                <li>
                  <p class="info__label">Phone</p>
                  <p>
                    <a href="tel:+82-010-3754-6773">010-3754-6773</a>
                  </p>
                </li>
              </ul>
            </article>
            <!-- 정보 -->
            <article class="info">
              <!-- 타이틀 -->
              <div class="title mb-10">
                <ul class="tag">
                  <li># 기획</li>
                  <li># 디자인</li>
                  <li># 웹 퍼블리싱</li>
                  <li># PL 경험 다수</li>
                  <li># 10년차 직장인</li>
                </ul>
                <h2>
                  <span class="point-color">Component Publishing이 가능한</span>
                  UI/UX 실력자 <span class="point-color">조유림</span>입니다.
                </h2>
              </div>
              <h3 class="sub-title">About Me</h3>
              <div class="info__text">
                <p class="mb-10">
                  안녕하세요.<br />저는 10년차 기획자 겸 웹 퍼블리셔로<br />컴포넌트
                  단위의 짜임세 있는 마크업을 지향합니다.
                </p>
                <p class="mb-10">
                  웹디자이너에서 기획, 퍼블리싱까 다양한 분야에서의 경험으로<br />디자이너,
                  개발자와 가깝게 일하면서 원할한 협업을 이끌어 내면서<br />최고의
                  결과물을 만들기 위해 노력하고있습니다.<br />
                </p>
                <p class="">
                  앞으로도 최고의 결과물을 만들기 위해 발전하는<br />UI/UX
                  전문가가 되기 위하여 노력하겠습니다.<br />감사합니다.
                </p>
              </div>
            </article>
          </div>
        </section>
        <section class="section">1</section>
        <section class="section">1</section>
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
  &__img {
    width: 250px;
    &::after {
      content: '';
      display: block;
      width: 250px;
      height: 20px;
      margin: 10px 0;
      background: url(/img/profile/profile__triangle.png) no-repeat center
        center / 40px;
    }
  }
  &__info-text {
    font-size: 16px;
    text-align: center;
  }
}
</style>
