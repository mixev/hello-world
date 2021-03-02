<template>
  <popupType :className="regClass">
    <template v-slot:regist-form>
      <div class="header_reg">Registration</div>
      <div class="reg-input">
        <div class="input-margin-bottom">
          <inputText :placeholder="textLogin" />
        </div>
        <inputText :placeholder="textPass" />
        <inputText :placeholder="textConfirm" />
      </div>
      <div class="fotter_reg" @click="$emit('regclose')">register</div>
    </template>
  </popupType>
</template>

<script>
import inputText from './inputText'
import popupType from './popupType'

export default {
  components: {
    popupType,
    inputText,
  },
  name: 'popupRegister',
  props: {},

  data() {
    return {
      textLogin: 'enter login',
      textPass: 'enter password',
      textConfirm: 'enter password confirmation',
      regClass: 'popup-module --register',
    }
  },
}
</script>
