<template>
  <section aside aria-label="grid" class="grid">
    <div class="grid__countbox">
      <div class="grid__count">
        총
        <span class="grid__count--point">{{ grid.page.totalCount }}</span> 건
      </div>
      <div class="flex items-center">
        <button type="button" class="btn__primary">등록</button>
      </div>
    </div>
    <grid
      :grid-id="grid.gridId"
      :col-width="grid.colWidth"
      :columns="grid.gridColumns"
      :data-list="grid.gridData"
      :checkbox="grid.checkbox"
    >
    </grid>
  </section>
</template>

<script>
export default {
  name: 'UtilGrid',
  data() {
    return {
      grid: {
        gridId: 'grodTest',
        colWidth: '100%',
        gridColumns: [
          { codeNm: '이름', code: 'name', colWidth: '20%' },
          { codeNm: '나이', code: 'age', colWidth: '20%' },
          { codeNm: '성별', code: 'gender', colWidth: '20%' },
          { codeNm: '테스트', code: 'test', colWidth: '20%' },
        ],
        checkbox: true,
        gridData: [
          {
            name: '홍길동',
            age: '19',
            gender: '남',
            test: 123,
          },
          {
            name: '홍길동2',
            age: '19',
            gender: '남',
            test: 123,
          },
          {
            name: '홍길동3',
            age: '19',
            gender: '남',
            test: 123,
          },
          {
            name: '홍길동4',
            age: '19',
            gender: '남',
            test: 123,
          },
          {
            name: '홍길동5',
            age: '19',
            gender: '남',
            test: 123,
          },
          {
            name: '홍길동6',
            age: '19',
            gender: '남',
            test: 123,
          },
        ],
        page: {
          totalCount: 10,
        },
      },
    }
  },
}
</script>

<style lang="scss" scoped></style>
