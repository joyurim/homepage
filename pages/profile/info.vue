<template>
  <section aside aria-label="기본정보" class="ProfileInfo">
    <!-- 타이틀ㄴ -->
    <article class="title mb-8">
      <ul class="tag">
        <li># 기획</li>
        <li># 디자인</li>
        <li># 웹 퍼블리싱</li>
        <li># PL 경험 다수</li>
        <li># 10년차 직장인</li>
      </ul>
      <h2>
        <span class="point-color">Component Publishing이 가능한</span> UI/UX
        실력자 <span class="point-color">조유림</span>입니다.
      </h2>
    </article>
    <div class="flex flex-start">
      <!-- 사진 -->
      <article class="profile">
        <img src="/img/yurim2.jpg" alt="조유림" />
      </article>
      <!-- 정보 -->
      <article class="info">
        <h3 class="info__title">About Me</h3>
        <p class="mb-7">
          안녕하세요.<br />저는 10년차 기획자 겸 웹 퍼블리셔로 컴포넌트 단위의
          짜임세 있는 마크업을 지향합니다. <br />웹디자이너에서 기획, 퍼블리싱까
          다양한 분야에서의 경험으로 디자이너, 개발자와 가깝게 일하면서 원할한
          협업을 이끌어 내려고 노력하고있습니다.<br />
          앞으로도 최고의 결과물을 만들기 위해 노력하고 공부하는 사람이
          되겠습니다. 감사합니다.
        </p>
        <h3 class="info__title">PROFILE</h3>
        <ul class="info__profile mb-7">
          <li>
            <div class="flex items-center w-1/2">
              <p class="info__label">Name</p>
              <p>조유림</p>
            </div>
            <div class="flex items-center w-1/2">
              <p class="info__label">Date</p>
              <p>1989.02.14</p>
            </div>
          </li>
          <li>
            <div class="flex items-center w-1/2">
              <p class="info__label">Email</p>
              <p>
                <a href="mailto:joyurim1989@naver.com">joyurim1989@naver.com</a>
              </p>
            </div>
            <div class="flex items-center w-1/2">
              <p class="info__label">Phone</p>
              <p>
                <a href="tel:+82-010-3754-6773">010-3754-6773</a>
              </p>
            </div>
          </li>
        </ul>
        <h3 class="info__title">Skill</h3>
        <ul class="info__skill">
          <li>
            <p class="info__label">HTML5</p>
            <div class="progress">
              <span class="bar" style="width: 100%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">CSS/SCSS</p>
            <div class="progress">
              <span class="bar" style="width: 90%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">Photoshop</p>
            <div class="progress">
              <span class="bar" style="width: 80%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">Vue publishing</p>
            <div class="progress">
              <span class="bar" style="width: 70%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">PowerPoint</p>
            <div class="progress">
              <span class="bar" style="width: 80%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">Git 형상관리</p>
            <div class="progress">
              <span class="bar" style="width: 60%"></span>
            </div>
          </li>
          <li>
            <p class="info__label">Notion</p>
            <div class="progress">
              <span class="bar" style="width: 90%"></span>
            </div>
          </li>
        </ul>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProfileInfo',
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped></style>
