<template>
  <h1>토마토 에듀 UI Guide</h1>

  <div class="guide-item">
    <div class="guide-txt">Margin</div>
    <div class="guide-cont">
      <ul>
        <li>4px $margin1</li>
        <li>8px $margin2</li>
        <li>16px $margin3</li>
        <li>32px $margin4</li>
        <li>40px $margin5</li>
        <li>sideMargin(16px) $margin-side</li>
        <li>Main Cont 간 여백 56px</li>
      </ul>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Writings</div>
    <div class="guide-cont">
      <div class="txt03">Color</div>
      <ul>
        <li class="color-main">메인 #111</li>
        <li class="color-point">포인트 (임의)</li>
        <li class="color-white" style="background-color: #111;">흰색</li>
        <li class="color-gray1">회색 #808080</li>
        <li class="color-gray2">회색 #ccc</li>
        <li class="color-gray3">회색 #b1b1b1</li>
        <li class="color-gray4">회색 #e1e1e8</li>
      </ul>
      <div class="txt03">Font</div>
      <ul>
        <li class="txt01">폰트 20px @mixin: txt-01</li>
        <li class="txt02">폰트 18px @mixin: txt-02</li>
        <li class="txt03">폰트 16px @mixin: txt-03</li>
        <li class="txt04">폰트 14px @mixin: txt-04</li>
        <li class="txt05">폰트 12px @mixin: txt-05</li>
        <li class="tit-h1">타이틀 16px</li>
        <li class="tit-page">페이지 타이틀 24px</li>
      </ul>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Title</div>
    <div class="guide-cont">
      <div class="txt03">main cont</div>
      <div class="title-area">
        <div class="tit-sub">
          현재 제일 인기 많은 강의를 소개합니다.
        </div>
        <button type="button" class="tit-main">
          프로그래밍 BEST 강의
        </button>
      </div>
      <div class="txt03">lecture list</div>
      <div class="title-area">
        <div class="tit-h1">
          프로그래밍 강좌 <em>(57)</em>
        </div>
      </div>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Button</div>
    <div class="guide-cont">
      <div class="txt03">btn sm</div>
      <button type="button" class="btn-s sm">btn-s sm</button>
      <button type="button" class="btn-p sm">btn-p sm</button>
      <button type="button" class="btn-b sm">btn-b sm</button>
      <button type="button" class="btn-disabled sm">btn-disabled sm</button>
      <div class="txt03">btn md</div>
      <button type="button" class="btn-s">btn-s</button>
      <button type="button" class="btn-p">btn-p</button>
      <button type="button" class="btn-b">btn-b</button>
      <button type="button" class="btn-disabled">btn-disabled</button>
      <div class="txt03">btn lg</div>
      <button type="button" class="btn-s lg">btn-s</button>
      <button type="button" class="btn-p lg">btn-p</button>
      <button type="button" class="btn-b lg">btn-b</button>
      <button type="button" class="btn-disabled lg">btn-disabled lg</button>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Checkbox</div>
    <div class="guide-cont">
      <label v-for="(item, idx) in checkItem" :key="'check' + idx" class="ipt-checkbox">
        <input class="check-input" type="checkbox" v-model="checked" :value="item.label" :disabled="item.disabled">
        <span class="check-label">{{ item.label }}</span>
      </label>
      <div class="txt03">check col</div>
      <div class="check-col">
        <label v-for="(item, idx) in checkItem" :key="'check' + idx" class="ipt-checkbox">
          <input class="check-input" type="checkbox" v-model="checked2" :disabled="item.disabled" :value="item.label">
          <span class="check-label">{{ item.label }}</span>
        </label>
      </div>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Radio</div>
    <div class="guide-cont">
      <label v-for="(item, idx) in rdoItem" :key="'radio' + idx" class="ipt-radio">
        <input class="radio-input" type="radio" v-model="radioVal" :value="item.label" :disabled="item.disabled">
        <span class="radio-label">{{ item.label }}</span>
      </label>
      <div class="txt03">radio col</div>
      <div class="radio-col">
        <label v-for="(item, idx) in rdoItem" :key="'radio' + idx" class="ipt-radio">
          <input class="radio-input" type="radio" v-model="radioVal2" :value="item.label" :disabled="item.disabled">
          <span class="radio-label">{{ item.label }}</span>
        </label>
      </div>
    </div>
  </div>

  <div class="guide-item">
    <div class="guide-txt">Input</div>
    <div class="guide-cont">
      <div class="txt03">normal</div>
      <input type="text" v-model="input">
      <div class="txt03">readonly</div>
      <input type="text" v-model="input" readonly>
      <div class="txt03">disabled</div>
      <input type="text" v-model="input" disabled>
      <div class="txt03">clearable</div>
      <span class="input-clear">
        <input type="text" v-model="input2" placeholder="내용을 입력해주세요">
        <button v-if="input2.length > 0" type="button" class="clear-btn" @click="clearInput()">
          <span class="hidden-text">내용 삭제</span>
        </button>
      </span>
      <div class="txt03">password</div>
      <span class="input-pw">
        <input :type="inputPw.show ? 'text' : 'password'" v-model="inputPw.value">
        <button type="button" :class="inputPw.show ? 'pw-view' : 'pw-hide'" @click="ctrlPwInput()">
          <span class="hidden-text">비밀번호 {{ inputPw.show ? '보이기' : '숨기기' }}</span>
        </button>
      </span>
    </div>
  </div>
</template>

<script setup lang='ts'>
  definePageMeta({
    layout: 'guide'
  })

  type input = {
    value: string,
    show: boolean | 'true' | 'false'
  }

  type inputOther = {
    label: string,
    disabled: boolean | 'true' | 'false'
  }

  let input:Ref<string> = ref('tomato');
  let input2:Ref<string> = ref('tomato');
  let inputPw:Ref<input> = ref({
    value: '',
    show: false
  })

  let checkItem:inputOther[] = [
    {
      label: 'check',
      disabled: false,
    },
    {
      label: 'check checked',
      disabled: false,
    },
    {
      label: 'check disabled',
      disabled: true,
    },
    {
      label: 'check checked + disabled',
      disabled: true,
    }
  ]
  let checked:Ref<Array<string>> = ref(['check checked', 'check checked + disabled']);
  let checked2:Ref<Array<string>> = ref(['check checked', 'check checked + disabled']);

  let rdoItem:inputOther[] = [
    {
      label: 'radio',
      disabled: false,
    },
    {
      label: 'radio2',
      disabled: false,
    },
    {
      label: 'radio disabled',
      disabled: true,
    },
    {
      label: 'radio check + disabled',
      disabled: true,
    }
  ]
  let radioVal:Ref<string> = ref('radio check + disabled');
  let radioVal2:Ref<string> = ref('radio check + disabled');

  function clearInput() {
    input2.value = '';
  }

  function ctrlPwInput() {
    inputPw.value.show = !inputPw.value.show
  }
</script>

<style lang='scss'>
  @import url(../../assets/scss/guide/index.scss);
</style>