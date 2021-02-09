<template>
  <div class="module">
    <popupOverlay @click="$emit('close')" />
    <div class="popup-module --register">
      <div class="header_reg">Registration</div>
      <div class="reg-input">
        <input
          class="reg-input -text --log"
          type="text"
          placeholder="enter login"
        />
        <input
          class="reg-input -text --pass"
          type="text"
          placeholder="enter password"
        />
        <input
          class="reg-input -text --pass"
          type="text"
          placeholder="enter password confirmation"
        />
      </div>
      <div class="fotter_reg" @click="$emit('regclose')">register</div>
    </div>
  </div>
</template>

<script>
import popupOverlay from './popupOverlay'

export default {
  components: {
    popupOverlay,
  },
  name: 'popupRegister',
  props: {},

  data() {
    return {}
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
