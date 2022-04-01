<template>
  <nav>
    <h1>ㅈㅇㄹ</h1>
    <article v-for="nav in navBox" :key="`sidebar-nav-${nav.navId}`">
      <h2 class="nav__title">{{ nav.navTitle }}</h2>
      <ul>
        <li
          v-for="gnb in nav.gnbList"
          :key="`sidebar-gnb-${gnb.menuId}`"
          class="nav__list"
        >
          <nuxt-link :to="gnb.menuUrl">{{ gnb.menuNm }}</nuxt-link>
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
              menuNm: '기본정보',
              menuUrl: '/profile/info',
            },
            {
              menuId: 'nav0001-2',
              menuNm: '경력사항',
              menuUrl: '/profile/career',
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
              menuNm: 'TextField',
              menuUrl: '/base/textField',
            },
            {
              menuId: 'nav0002-4',
              menuNm: 'Radio',
              menuUrl: '/base/radio',
            },
            {
              menuId: 'nav0002-5',
              menuNm: 'Checkbox',
              menuUrl: '/base/checkbox',
            },
            {
              menuId: 'nav0002-6',
              menuNm: 'Select',
              menuUrl: '/base/select',
            },
          ],
        },
        {
          navId: 'nav0003',
          navTitle: 'Util Component',
          gnbList: [
            {
              menuId: 'nav0003-1',
              menuNm: 'Accordian',
              menuUrl: '/util/accordian',
            },
            {
              menuId: 'nav0003-2',
              menuNm: 'Grid',
              menuUrl: '/util/grid',
            },
            {
              menuId: 'nav0003-3',
              menuNm: 'Picker',
              menuUrl: '/util/picker',
            },
            {
              menuId: 'nav0003-4',
              menuNm: 'Popup',
              menuUrl: '/util/popup',
            },
            {
              menuId: 'nav0003-5',
              menuNm: 'Etc',
              menuUrl: '/util/etc',
            },
          ],
        },
        {
          navId: 'nav0004',
          navTitle: 'Layout',
          gnbList: [
            {
              menuId: 'nav0004-1',
              menuNm: 'Responsive',
              menuUrl: '/layout/responsive',
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

<style lang="scss" scoped></style>
