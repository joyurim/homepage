<template>
  <section aside aria-label="form">
    <!-- ===========Input========== -->
    <div class="content-box pb-10">
      <h2 class="mb-6 font-bold text-xl">Input</h2>
      <!-- Basic -->
      <div class="flex items-center mb-5">
        <label class="form__label">Basic</label>
        <input
          v-model="form.input1"
          type="text"
          class="form__input"
          placeholder="input box disabled 입니다."
        />
      </div>

      <!-- Error -->
      <div class="mb-5 flex items-center">
        <label class="form__label">Error</label>
        <div class="flex-1">
          <input
            v-model="form.input2"
            type="text"
            class="form__input"
            :class="{ form__error: isErrorMsg }"
            placeholder="input box 입니다."
          />
          <p v-if="isErrorMsg" class="form__error">에러 메세지입니다.</p>
        </div>
      </div>

      <!-- Disabled -->
      <div class="flex items-center mb-5">
        <label class="form__label">Disabled</label>
        <input
          v-model="form.input3"
          type="text"
          class="form__input"
          disabled
          placeholder="input box disabled 입니다."
        />
      </div>

      <!-- Readonly -->
      <div class="flex items-center mb-5">
        <label class="form__label">Readonly</label>
        <input
          v-model="form.input4"
          type="text"
          class="form__input"
          readonly
          placeholder="input box readonly 입니다."
        />
      </div>
    </div>

    <!-- ===========Textarea========== -->
    <div class="content-box pb-10">
      <h2 class="mb-6 font-bold text-xl">Textarea</h2>

      <!-- Basic -->
      <div class="flex items-center mb-5">
        <label class="form__label">Basic</label>
        <textarea
          v-model="form.textarea1"
          class="form__textarea"
          placeholder="최소 5자 이상 입력해 주세요."
        ></textarea>
      </div>

      <!-- Error -->
      <div class="flex items-center mb-5">
        <label class="form__label">Error</label>
        <div class="flex-1">
          <textarea
            v-model="form.textarea2"
            class="form__textarea"
            placeholder="최소 5자 이상 입력해 주세요."
            :class="{ form__error: isErrorMsg }"
          ></textarea>
          <p v-if="isErrorMsg" class="form__error">에러 메세지입니다.</p>
        </div>
      </div>

      <!-- Disabled -->
      <div class="flex items-center mb-5">
        <label class="form__label">Disabled</label>
        <textarea
          v-model="form.textarea3"
          class="form__textarea"
          placeholder="최소 5자 이상 입력해 주세요."
          disabled
        ></textarea>
      </div>

      <!-- Readonly -->
      <div class="flex items-center mb-5">
        <label class="form__label">Readonly</label>
        <textarea
          v-model="form.textarea4"
          class="form__textarea"
          placeholder="최소 5자 이상 입력해 주세요."
          readonly
        ></textarea>
      </div>
    </div>

    <!-- ===============Select================ -->
    <div class="content-box flex-col pb-10">
      <h2 class="mb-6 font-bold text-xl">Select</h2>
      <div class="flex items-start">
        <!-- Basic -->
        <div class="w-1/4 mr-2 mb-5 flex items-center">
          <label class="form__label">Basic </label>
          <div class="w-48">
            <vue-select
              v-model="form.selectbox1"
              :options="options"
              :label="'name'"
              :searchable="false"
            />
          </div>
        </div>

        <!-- Error -->
        <div class="w-1/4 mr-2 mb-5 flex items-center">
          <label class="form__label">Error </label>
          <div class="w-48">
            <vue-select
              v-model="form.selectbox2"
              :options="options"
              :label="'name'"
              :searchable="false"
              :class="{ form__error: isErrorMsg }"
            />
            <p v-if="isErrorMsg" class="form__error">에러 메세지입니다.</p>
          </div>
        </div>

        <!-- Disabled -->
        <div class="w-1/4 mr-2 mb-5 flex items-center">
          <label class="form__label">Disabled </label>
          <div class="w-48">
            <vue-select
              v-model="form.selectbox3"
              :options="options"
              :label="'name'"
              :searchable="false"
              disabled
            />
          </div>
        </div>

        <!-- Readonly -->
        <!-- 
          **************************************************************************
          페이지에 적용할 경우 조건을 활용하여 클래스 바인딩을 통해select--readonly  적용 
          **************************************************************************
        -->
        <div class="mb-5 flex items-center">
          <label class="form__label">ReadOnly </label>
          <div class="w-48">
            <vue-select
              v-model="form.selectbox4"
              :options="options"
              :label="'name'"
              :searchable="false"
              readonly
              class="select--readonly"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- ===========Radio=========== -->
    <div class="content-box flex-col pb-10">
      <h2 class="mb-6 font-bold text-xl">Radio</h2>
      <div class="flex-1 ml-30">
        <!-- label이 없을 경우 -->
        <div class="flex items-center mb-5">
          <div class="form__radio">
            <input v-model="form.radio1" type="radio" value="radio1" />
          </div>
          <div class="mx-4 form__radio">
            <input v-model="form.radio2" type="radio" value="radio2" />
          </div>
          <div class="form__radio">
            <input v-model="form.radio3" type="radio" value="radio3" disabled />
          </div>
        </div>

        <!-- label이 있을 경우 -->
        <div class="flex items-start">
          <!-- Basic -->
          <div class="form__radio">
            <input
              id="example-textFieldExample-radio1"
              v-model="form.radio4"
              type="radio"
              value="radio4"
            />
            <label for="example-textFieldExample-radio1">Basic</label>
          </div>

          <!-- Error -->
          <div class="error__container">
            <div class="flex items-center mb-2">
              <div class="form__radio">
                <input
                  id="example-textFieldExample-radio2"
                  v-model="form.radio1"
                  type="radio"
                  value="radio5"
                />
                <label for="example-textFieldExample-radio2">Error</label>
              </div>
            </div>
            <p v-if="isErrorMsg" class="form__error">에러 메세지입니다.</p>
          </div>

          <!-- Disabled -->
          <div class="form__radio">
            <input
              id="example-textFieldExample-radio3"
              v-model="form.radio1"
              type="radio"
              disabled
              value="radio1"
            />
            <label for="example-textFieldExample-radio3">Disabled</label>
          </div>

          <!-- RaedOnly -->
          <!-- 
          **************************************************************************
          페이지에 적용할 경우 조건을 활용하여 클래스 바인딩을 통해 radio--readonly  적용 
          **************************************************************************
        -->
          <div class="form__radio">
            <input
              id="example-textFieldExample-radio3"
              v-model="form.radio1"
              type="radio"
              disabled
              value="radio1"
              class="radio--readonly"
            />
            <label for="example-textFieldExample-radio3">readonly</label>
          </div>
        </div>
      </div>
    </div>

    <!-- ===========Checkbox============ -->
    <div class="content-box flex-col pb-10">
      <h2 class="mb-6 font-bold text-xl">Checkbox</h2>
      <div class="flex-1 ml-15">
        <!-- label 없이 쓰일 때 -->
        <div class="flex items-center mb-5">
          <div class="form__checkbox">
            <input v-model="form.checkbox1" type="checkbox" />
          </div>
          <div class="mx-4 form__checkbox">
            <input v-model="form.checkbox2" type="checkbox" />
          </div>
          <div class="form__checkbox">
            <input v-model="form.checkbox3" type="checkbox" disabled />
          </div>
        </div>

        <div class="flex items-start">
          <!-- Basic -->
          <div class="form__checkbox">
            <input
              id="example-textFieldExample-checkbox1"
              v-model="form.checkbox4"
              type="checkbox"
            />
            <label for="example-textFieldExample-checkbox1">Basic</label>
          </div>

          <div class="error__container">
            <!-- Error -->
            <div class="flex items-center mb-2">
              <div class="form__checkbox">
                <input
                  id="example-textFieldExample-checkbox1"
                  v-model="form.checkbox5"
                  type="checkbox"
                />
                <label for="example-textFieldExample-checkbox1">Error</label>
              </div>
            </div>
            <p v-if="isErrorMsg" class="form__error">에러 메세지입니다.</p>
          </div>

          <!-- Disabled -->
          <div class="form__checkbox">
            <input
              id="example-textFieldExample-checkbox3"
              v-model="form.checkbox6"
              type="checkbox"
              disabled
            />
            <label for="example-textFieldExample-checkbox3">Disabled</label>
          </div>

          <!-- ReadOnly -->
          <!-- 
          ******************************************************************************
          페이지에 적용할 경우 조건을 활용하여 클래스 바인딩을 통해 checkbox--readonly  적용 
          ******************************************************************************
        -->
          <div class="form__checkbox">
            <input
              id="example-textFieldExample-checkbox3"
              v-model="form.checkbox7"
              type="checkbox"
              disabled
              class="checkbox--readonly"
            />
            <label for="example-textFieldExample-checkbox3">checkbox</label>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseForm',
  data() {
    return {
      isErrorMsg: true,
      options: [
        { name: '예시1', code: 'example1' },
        { name: '예시2', code: 'example2' },
        { name: '예시3', code: 'example3' },
        { name: '예시4', code: 'example4' },
      ],
      selectbox1: {
        name: '',
        code: 'example',
      },
      radio: {
        mode: 'ReadOnly',
      },
      checkbox: {
        mode: 'ReadOnly',
      },
      form: {
        input1: '',
        input2: '',
        input3: '',
        input4: '',
        textarea1: '',
        textarea2: '',
        textarea3: '',
        textarea4: '',
        selectbox1: '',
        selectbox2: '',
        selectbox3: '',
        selectbox4: '예시',
        radio1: 'radio1',
        radio3: 'radio3',
        radio4: 'radio4',
        checkbox1: 'checkbox1',
        checkbox2: '',
        checkbox3: 'checkbox3',
        checkbox4: 'checkbox4',
        checkbox5: '',
        checkbox6: 'checkbox6',
        checkbox7: 'checkbox7',
      },
    }
  },
}
</script>

<style lang="scss" scoped></style>
