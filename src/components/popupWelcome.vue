<template>
  <div class="module">
    <popupOverlay @click="$emit('close')" />
    <div class="popup-module --welcome">
      <div class="text">Welcome {{ nameLogin }}!</div>
      <div class="textWait">please wait a second to login...</div>
    </div>
  </div>
</template>

<script>
import popupOverlay from './popupOverlay'

export default {
  components: {
    popupOverlay,
  },
  name: 'popupWelcome',
  props: {
    nameLogin: String,
  },

  data() {
    return {}
  },
  methods: {
    closePopup() {
      this.$emit('close')
    },
  },
}
</script>

<style>
.text {
  width: 200px;
  height: 70px;
  text-align: center;
  font-size: 29px;
}
.textWait {
  font-size: 18px;
}
</style>
