<template>
  <section aside aria-label="responsive" class="testgut">
    <!-- 최상단 gnb -->
    <article class="top-gnb">
      <div class="testgut__inner flex items-center justify-between">
        <div class="w-32">
          <vue-select
            v-model="topGnb"
            :options="topGnbList"
            :label="'name'"
            :searchable="false"
          />
        </div>
        <ul class="top-gnb--right flex items-center">
          <li>로그인</li>
          <li>회원가입</li>
          <li>고객센터</li>
          <li>리얼후기</li>
        </ul>
      </div>
    </article>
    <header class="testgut__inner">
      <h1 class="logo">
        <img src="/img/testgut/logo.png" alt="테스트굿 로고" />
      </h1>
    </header>
  </section>
</template>

<script>
export default {
  name: 'LayoutTestgut',
  layout() {
    return 'web'
  },
  data() {
    return {
      topGnb: 'Family Site',
      topGnbList: [
        {
          code: '0001',
          name: '시드니 캥거루',
        },
        {
          code: '0002',
          name: '아로니아 오리지날',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/testgut.scss';
</style>
