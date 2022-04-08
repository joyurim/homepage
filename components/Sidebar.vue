<template>
  <nav class="nav">
    <h1 class="logo"><nuxt-link to="/profile/info">ㅈㅇㄹ</nuxt-link></h1>
    <article
      v-for="nav in navBox"
      :key="`sidebar-nav-${nav.navId}`"
      class="mt-8"
    >
      <h2 class="nav__title">{{ nav.navTitle }}</h2>
      <ul class="mt-3">
        <li
          v-for="gnb in nav.gnbList"
          :key="`sidebar-gnb-${gnb.menuId}`"
          class="nav__list"
        >
          <nuxt-link :to="gnb.menuUrl" class="nav__list--menu">{{
            gnb.menuNm
          }}</nuxt-link>
        </li>
      </ul>
    </article>
  </nav>
</template>

<script>
export default {
  name: 'SidebarIndex',
  data() {
    return {
      navBox: [
        {
          navId: 'nav0001',
          navTitle: 'Profile',
          gnbList: [
            {
              menuId: 'nav0001-1',
              menuNm: 'I`s me',
              menuUrl: '/profile',
            },
          ],
        },
        {
          navId: 'nav0002',
          navTitle: 'Base Component',
          gnbList: [
            {
              menuId: 'nav0002-1',
              menuNm: 'Color',
              menuUrl: '/base/color',
            },
            {
              menuId: 'nav0002-2',
              menuNm: 'Typography',
              menuUrl: '/base/typography',
            },
            {
              menuId: 'nav0002-3',
              menuNm: 'Form',
              menuUrl: '/base/form',
            },
            {
              menuId: 'nav0002-4',
              menuNm: 'Button',
              menuUrl: '/base/button',
            },
          ],
        },
        {
          navId: 'nav0003',
          navTitle: 'Util Component',
          gnbList: [
            {
              menuId: 'nav0003-1',
              menuNm: 'Grid',
              menuUrl: '/util/grid',
            },
            {
              menuId: 'nav0003-2',
              menuNm: 'Popup',
              menuUrl: '/util/popup',
            },
          ],
        },
        {
          navId: 'nav0004',
          navTitle: 'Layout',
          gnbList: [
            {
              menuId: 'nav0004-1',
              menuNm: '반응형 웹',
              menuUrl: '/layout/testgut',
            },
            {
              menuId: 'nav0004-2',
              menuNm: 'Mobile',
              menuUrl: '/layout/mobile',
            },
          ],
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.nav {
  min-width: 230px;
  padding: 20px;
  background: $bg-color;
  .logo {
    font-size: 20px;
    font-weight: 700;
    padding: 5px 10px;
    border: 2px solid;
    display: inline;
  }
  &__title {
    color: $blue-1;
    font-size: 14px;
    font-weight: 700;
  }
  &__list {
    &--menu {
      display: block;
      padding: 3px 12px;
      font-size: 16px;
      border-left: 1px solid $blue-3;
      &.nuxt-link-active {
        color: $primary;
        border-left-color: $primary;
      }
      &:hover {
        color: $blue-2;
        border-left-color: $blue-2;
      }
    }
  }
}
</style>
