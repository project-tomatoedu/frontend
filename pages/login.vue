<template>
    <div class="login-container">
        <div class="login-box">
            <h1 class="tit-page align2">TOMATO EDU</h1>
            <div class="txt-01 align2">하나의 아이디로 토마토 서비스를 이용하세요.</div>
            <div class="txt-01 top-margin1 align2">다른 서비스로 로그인</div>
            <div class="align1 top-margin2">
                <button type="button" class="social-login-btn google"></button>
                <button type="button" class="social-login-btn "></button>
                <button type="button" class="social-login-btn "></button>
                <button type="button" class="social-login-btn "></button>
                <button type="button" class="social-login-btn "></button>
                <button type="button" class="social-login-btn "></button>
            </div>
            <div class="txt-01 color-gray1 top-margin2 align2">또는</div>
            <input type="text" class="expanded top-margin2 bottom-margin" id="username" placeholder="이메일">
            <span class="input-pw">
                <input :type="inputPw.show ? 'text' : 'password'" v-model="inputPw.value" placeholder="비밀번호">
                <button type="button" :class="inputPw.show ? 'pw-view' : 'pw-hide'" @click="ctrlPwInput()">
                    <span class="hidden-text">비밀번호 {{ inputPw.show ? '보이기' : '숨기기' }}</span>
                </button>
            </span>
            <button type="button" class="btn-p lg expanded top-margin1">로그인</button>
            <div class="align1">
                <label class="ipt-checkbox">
                    <input class="check-input" type="checkbox" value="check" :disabled="false">
                    <span class="check-label">로그인 상태 유지</span>
                </label>
                <button type="button">비밀번호 재설정</button>
                <button type="button">회원가입</button>
            </div>
            <div class="underline top-margin1"></div>
            <div class="txt-02 color-gray1 align2 top-margin1">회원가입 시 goorm의 서비스 약관 및</div>
            <div class="txt-02 color-gray1 align2">개인정보 처리방침을 확인하였으며, 동의합니다.
            </div>
        </div>
    </div>
</template>
  
<script  setup lang='ts'>
type input = {
    value: string,
    show: boolean | 'true' | 'false'
}
let inputPw: Ref<input> = ref({
    value: '',
    show: false
})
function ctrlPwInput() {
    inputPw.value.show = !inputPw.value.show
}
</script>
  
<style scoped >
.login-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.login-box {
    width: 300px;
    padding: 20px;
}

.expanded {
    width: 100%;
}

.top-margin1 {
    margin-top: 16px;
}

.top-margin2 {
    margin-top: 8px;
}

.bottom-margin {
    margin-bottom: 8px;
}

.social-login-btn {
    width: 40px;
    height: 40px;
    padding: 0px;
    margin-bottom: 10px;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    background-size: contain;
    box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.1);

}

.google {
    background-image: url('/google.svg');
}

.align1 {
    width: 100%;
    display: flex;
    justify-content: space-between;
}

.align2 {
    width: 100%;
    display: flex;
    justify-content: center;
}

.underline {
    border-bottom: 0.5px solid gray;
}
</style>
  