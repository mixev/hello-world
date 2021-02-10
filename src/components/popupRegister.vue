<template>
  <div class="module">
    <popupOverlay @click="$emit('close')" />
    <div class="popup-module --register">
      <div class="header_reg">Registration</div>
      <div class="reg-input">
        <div class="input-margin-bottom">
          <inputText :text="textLogin" />
        </div>
        <inputText :text="textPass" />
        <inputText :text="textConfirm" />
      </div>
      <div class="fotter_reg" @click="$emit('regclose')">register</div>
    </div>
  </div>
</template>

<script>
import popupOverlay from './popupOverlay'
import inputText from './inputText'

export default {
  components: {
    popupOverlay,
    inputText,
  },
  name: 'popupRegister',
  props: {},

  data() {
    return {
      textLogin: 'enter login',
      textPass: 'enter password',
      textConfirm: 'enter password confirmation',
    }
  },
  methods: {
    // closePopuppp() {
    //   this.$emit('close')
    // },
    // registerAndClose() {
    //   this.$emit('rclose')
    // },
  },
}
</script>
