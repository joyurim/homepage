<template>
  <div class="grid__wrap">
    <table v-if="dataList.length > 0" :ref="gridId" class="grid__base">
      <colgroup>
        <slot name="col">
          <col v-if="checkbox" width="*" />
          <col
            v-for="(c, index) in columns"
            :key="`columns-key-${index}`"
            :width="c.colWidth"
          />
        </slot>
      </colgroup>
      <thead>
        <tr>
          <th v-if="checkbox">선택</th>
          <th v-for="(c, idx) in columns" :key="`columns-key-${idx}`">
            {{ c.codeNm }}
          </th>
        </tr>
      </thead>

      <tbody>
        <tr
          v-for="(data, idx) in dataList"
          :key="`columns-key-${idx}`"
          :class="{ 'grid--active': selectedData === data }"
          @click="selectRow(data)"
          @dblclick="goToDetail(data)"
        >
          <td v-if="checkbox">
            <div class="form__checkbox">
              <input
                ref="checkbox"
                type="checkbox"
                :disabled="mode === 'read'"
                :class="{ 'checkbox--readonly': mode === ' read' }"
                @change="checkedRow($event, data)"
              />
            </div>
          </td>
          <td
            v-for="(c, index) in columns"
            :key="`columns-key-${index}`"
            :title="data[c.code]"
            class="cursor-pointer"
            :class="c.addClass"
            @click="$emit('checkedRow', data)"
          >
            {{ data[c.code] }}
          </td>
        </tr>
      </tbody>
    </table>
    <div v-else class="nodata">
      <span class="el-icon-circle-close"> 검색된 데이터가 없습니다.</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BaseGrid',

  props: {
    gridId: {
      type: String,
      require: false,
      default: '',
    },
    columns: {
      type: Array,
      require: false,
      default() {
        return []
      },
    },
    dataList: {
      type: Array,
      require: false,
      default() {
        return []
      },
    },
    colWidth: {
      type: String,
      require: false,
      default: '*',
    },
    addClass: {
      type: String,
      require: false,
      default: '',
    },
    checkbox: {
      type: Boolean,
      require: false,
      default: false,
    },
    mode: {
      type: String,
      require: false,
      default: '',
    },
  },
  data() {
    return {
      selectedData: '',

      page: {
        totalCount: 10,
      },
      checkedRows: [],
    }
  },
  watch: {
    'dataList.length'(dataListLength) {
      if (dataListLength === 0) {
        this.clearCheckedRows()
      }
    },
  },
  mounted() {
    this.loaded()
  },
  methods: {
    // row 선택 시 하이라이트
    selectRow(data) {
      this.selectedData = data
      this.$emit('selectRow', data)
    },
    // 상세 페이지로 이동
    goToDetail(data) {
      this.$emit('goToDetail', data)
    },
    // check 된 row data 값
    checkedRow(e, data) {
      if (e.target.checked) {
        this.checkedRows.push(data)
      } else {
        this.checkedRows = this.checkedRows.filter((r) => r !== data)
      }
      // check한 row 부모컴포넌트에게 emit
      this.$emit('checkedRow', data)

      // check된 row들 부모컴포넌트에게 emit
      this.$emit('checkedRows', this.checkedRows)
    },
    // index의 row 체크박스 체크
    checkRow(index) {
      if (this.$refs && this.$refs.checkbox && this.$refs.checkbox[index]) {
        this.$refs.checkbox[index].checked = true
        this.checkedRows.push(this.dataList[index])
      }
    },
    // check 된 row 초기화
    clearCheckedRows() {
      this.selectedData = ''
      this.checkedRows = []
      this.$emit('checkedRows', this.checkedRows)
    },
    // 그리드 load 된 이후 이벤트 발생
    loaded() {
      this.$nextTick(() => {
        this.$emit('loaded')
      })
    },
  },
}
</script>

<style lang="scss">
.grid {
  display: flex;
  flex-flow: column;

  &__countbox {
    @apply flex items-end justify-between mb-2;
    // 그리드 카운트
    .grid__count {
      line-height: initial;

      &--point {
        display: inline-block;
        color: $primary70;
        font-weight: 700;
      }
    }
  }

  // 테이블 (리스트) 스타일
  .grid__base {
    table-layout: fixed;
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    border: {
      top: 1px solid #a2a2a2;
      bottom: 1px solid $gray-20;
    }
    text-align: center;

    .form__checkbox {
      justify-content: center;
    }

    th,
    td {
      word-break: break-all;
      border-right: 1px solid $gray-20;
      box-sizing: border-box;
      cursor: default;
      &:last-child {
        border-right: 1px solid transparent;
      }
    }

    thead {
      background: $gray-5;
      th {
        height: 35px;
        padding: 0 3px;
        border-bottom: 1px solid $gray-20;
        box-sizing: border-box;
        text-align: center;
        word-break: break-all;
        &:first-child {
          border-left: none;
        }
      }
    }

    tbody {
      tr {
        border-bottom: 1px solid $gray-20;
        border-collapse: separate;
        background: transparent;

        &:last-child {
          border-bottom: none;
        }

        td {
          height: 35px;
          padding: 0 3px;
          border-bottom: 1px solid $gray-20;
          color: $gray-60;
          word-break: break-all;
          cursor: default;
          box-sizing: border-box;
          //말줄임표 스타일
          &.omission {
            padding: 0 5px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            word-wrap: normal;
          }

          &.link-style,
          &.cursor-pointer {
            cursor: pointer;
          }
        }

        &:hover,
        &.grid--active {
          td {
            background: #ecf0fb78;
            cursor: default;
          }
        }

        &.cursor-default {
          &:hover,
          &.grid--active {
            td {
              cursor: default;
            }
          }
        }

        &:last-child {
          border: none;
        }
      }
    }
  }
}
.nodata {
  @apply flex items-center justify-center;
  padding: 9px 0;
  width: 100%;
  height: 100%;
  text-align: center;

  color: $gray-50;
  font-size: 15px;
  border: 1px solid $gray-20;
}
</style>
