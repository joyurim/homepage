<template>
  <section aside aria-label="기본정보" class="ProfileInfo">
    <div class="flex flex-start mb-20">
      <!-- 사진 -->
      <article class="profile-img">
        <img src="/img/yurim.jpg" alt="조유림" />
        <!-- 연락처 -->
        <ul class="profile profile__info">
          <li>
            <p class="info__label">Email</p>
            <p>
              <a href="mailto:joyurim1989@naver.com">joyurim1989@naver.com</a>
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
            <span class="point-color">Component Publishing이 가능한</span> UI/UX
            실력자 <span class="point-color">조유림</span>입니다.
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
            앞으로도 최고의 결과물을 만들기 위해 발전하는<br />UI/UX 전문가가
            되기 위하여 노력하겠습니다.<br />감사합니다.
          </p>
        </div>
      </article>
    </div>
    <div class="flex items-start mb-20">
      <!-- 이렇게 일해요 -->
      <article class="info">
        <h3 class="sub-title mb-1">저는 이렇게 일합니다.</h3>
        <ol class="info__work">
          <li class="mb-10">
            <p class="info__label">실무로 다져진 경험</p>
            <p>
              로봇, 홈 플랫폼, 프레임워크, 인사서비스 등<br />
              실무로 다져진 다양한 프로젝트의 기획 및 웹 퍼블리싱 경험이
              풍부합니다.
            </p>
          </li>
          <li class="mb-10">
            <p class="info__label">계속해서 발전하는 스킬 업</p>
            <p>
              vue.js, nuxt.js, Git Lab, Notion, Zeplin, SCSS/LESS 등<br />
              생산성과 협업을 위한 스킬들을 배우고 프로젝트에 적용하고 있습니다.
            </p>
          </li>
          <li>
            <p class="info__label">다년간 근무한 SI</p>
            <p>
              다년간 근무한 SI 회사의 경험과 웹 디자이너로 근무한 경력을
              바탕으로<br />디자이너, 개발자, 기획자와의 원활한 커뮤니케이션이
              가능합니다.
            </p>
          </li>
        </ol>
      </article>
      <!-- 사진 -->
      <article class="info__work--img">
        <img src="/img/development.jpg" alt="이렇게 일합니다" />
      </article>
    </div>
    <!-- 스킬 -->
    <!-- <article class="info">
      <h3 class="sub-title">Skill</h3>
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
    </article> -->
    <article class="career">
      <h3 class="sub-title">열심히 만들었습니다</h3>
      <p class="career__title">
        최근 3년간 진행한 프로젝트 중 대표적인 작업물입니다.
      </p>
      <ul class="career__box">
        <li>
          <a
            href="https://lghomin.com/"
            target="_blank"
            rel="noopener noreferrer"
          >
            <div
              class="career__img"
              style="background-image: url('/img/homin.jpg')"
            >
              <span class="hide">집안일 해결 플랫폼 LG Homin</span>
            </div>
            <div class="career__text">
              <p class="career__text--title">LG Homin 집안일 해결 플랫폼</p>
              <p class="career__text--info">
                컴포넌트 분리 작업 100%, 모바일 웹 퍼블리싱 50% 참여
              </p>
            </div>
          </a>
        </li>
        <li>
          <a
            href="https://place.uplus.co.kr/shop/U5872444?utm_source=uplushome&utm_medium=findstore"
            target="_blank"
            rel="noopener noreferrer"
          >
            <div
              class="career__img"
              style="background-image: url('/img/o2o.jpg')"
            >
              <span class="hide">매장 마이크로 사이트</span>
            </div>
            <div class="career__text">
              <p class="career__text--title">LG U+ 매장 마이크로 사이트</p>
              <p class="career__text--info">PC, Mobile 웹 퍼블리싱 100%</p>
            </div>
          </a>
        </li>
        <li>
          <div
            class="career__img"
            style="background-image: url('/img/robot-mon.jpg')"
          >
            <span class="hide">로봇 플랫폼 모니터링</span>
          </div>
          <div class="career__text">
            <p class="career__text--title">LG Iot 로봇 플랫폼 모니터링</p>
            <p class="career__text--info">웹 기획 100%, PC 웹 퍼블리싱 100%</p>
          </div>
        </li>
        <li>
          <div
            class="career__img"
            style="background-image: url('/img/robot-admin.jpg')"
          >
            <span class="hide">로봇 플랫폼 관리자</span>
          </div>
          <div class="career__text">
            <p class="career__text--title">LG Iot 로봇 플랫폼 관리자</p>
            <p class="career__text--info">웹 기획 100%, PC 웹 퍼블리싱 100%</p>
          </div>
        </li>
        <li>
          <div
            class="career__img"
            style="background-image: url('/img/datafarm.jpg')"
          >
            <span class="hide">LG 빅테이터 데이터팜</span>
          </div>
          <div class="career__text">
            <p class="career__text--title">LG 빅 데이터 플랫폼 데이터팜</p>
            <p class="career__text--info">
              웹 기획 100%, 웹 디자인 30%, 웹 퍼블리싱 50%
            </p>
          </div>
        </li>
        <li>
          <div
            class="career__img"
            style="background-image: url('/img/kkpc.jpg')"
          >
            <span class="hide">금호석유화학 인사서비스</span>
          </div>
          <div class="career__text">
            <p class="career__text--title">
              금호석유화학 인사서비스 관리자/사용자
            </p>
            <p class="career__text--info">
              웹 기획 100%, 웹 디자인 100%, 웹 퍼블리싱 50%
            </p>
          </div>
        </li>
      </ul>
      <div class="mt-14 text-center">
        <nuxt-link to="/profile/career" class="career__more"
          >경력 자세히 보기</nuxt-link
        >
      </div>
    </article>
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
